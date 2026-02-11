# Rozwiązywanie Problemów (Troubleshooting) 

## Problemy z połączeniem z API (Windows) 

Jeśli aplikacja mobilna lub frontend nie może połączyć się z API uruchomionym na systemie Windows (np. przez WSL2 lub bezpośrednio), może to być spowodowane blokadą przez systemową zaporę ogniową.

### Kroki naprawcze:

1. **Zmień profil sieci na Prywatny:** 
   Windows domyślnie blokuje połączenia przychodzące w profilu "Publiczny". Upewnij się, że Twoja sieć (Wi-Fi lub Ethernet) jest ustawiona jako **Prywatna** w ustawieniach systemowych (Ustawienia -> Sieć i Internet -> Stan -> Właściwości połączenia).

2. **Tymczasowe wyłączenie Zapory Windows:** 
   Jeśli zmiana profilu nie pomoże, spróbuj tymczasowo wyłączyć Zaporę Windows (Windows Firewall), aby zweryfikować, czy to ona blokuje ruch. Jeśli po wyłączeniu system działa, należy dodać odpowiednią regułę (patrz punkt 3).

3. **Dodanie reguły w zaporze (Zalecane):** 
   Zamiast wyłączać całą zaporę, dodaj regułę zezwalającą na ruch przychodzący (Inbound Rule) dla portu, na którym nasłuchuje bramka NGINX (standardowo port **80** lub **443**).
