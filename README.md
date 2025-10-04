# 👻 Ghost Sekuriteitsmodule
**PowerShell-Gebaseerde Windows & Azure Sekuriteitsverharding Instrument**

> **Proaktiewe sekuriteitsverharding vir Windows eindpunte en Azure omgewings.** Ghost bied PowerShell-gebaseerde verhardingsfunksies wat kan help om algemene aanvalsvektore te verminder deur onnodige dienste en protokolle te deaktiveer.

## ⚠️ Belangrike Vrywaring

**TOETSING VEREIS**: Toets altyd Ghost in nie-produksie omgewings eerste. Die deaktivering van dienste kan wettige besigheidsfunksies beïnvloed.

**GEEN WAARBORGE**: Alhoewel Ghost algemene aanvalsvektore teiken, kan geen sekuriteitsinstrument alle aanvalle voorkom nie. Dit is een komponent van 'n omvattende sekuriteitsstrategie.

**OPERASIONELE IMPAK**: Sommige funksies kan stelselfunksionaliteit beïnvloed. Hersien elke instelling sorgvuldig voor ontplooiing.

**PROFESSIONELE EVALUERING**: Vir produksie omgewings, raadpleeg met sekuriteitsprofessionals om te verseker dat instellings in lyn is met jou organisasie se behoeftes.

## 📊 Die Sekuriteitslandskap

Ransomware skade het **$57 miljard in 2025** bereik, met navorsing wat aandui dat baie suksesvolle aanvalle basiese Windows dienste en verkeerde konfigurasies uitbuit. Algemene aanvalsvektore sluit in:

- **90% van ransomware insidente** behels RDP uitbuiting
- **SMBv1 kwesbaarhede** het aanvalle soos WannaCry en NotPetya moontlik gemaak
- **Dokument makros** bly 'n primêre malware afleweringsmetode
- **USB-gebaseerde aanvalle** teiken steeds lugafgesnyde netwerke
- **PowerShell misbruik** het beduidend toegeneem in onlangse jare

## 🛡️ Ghost Sekuriteitsfunksies

Ghost bied **16 Windows verhardingsfunksies** plus **Azure sekuriteitsintegrasie**:

### Windows Eindpunt Verharding

| Funksie | Doel | Oorwegings |
|---------|------|------------|
| `Set-RDP` | Bestuur Afgeleë Desktop toegang | Kan afgeleë administrasie beïnvloed |
| `Set-SMBv1` | Beheer erfenis SMB protokol | Vereis vir baie ou stelsels |
| `Set-AutoRun` | Beheer AutoPlay/AutoRun | Kan gebruikersgemak beïnvloed |
| `Set-USBStorage` | Beperk USB bergingstoestelle | Kan wettige USB gebruik beïnvloed |
| `Set-Macros` | Beheer Office makro uitvoering | Kan makro-geaktiveerde dokumente beïnvloed |
| `Set-PSRemoting` | Bestuur PowerShell afstandbeheer | Kan afgeleë bestuur beïnvloed |
| `Set-WinRM` | Beheer Windows Afgeleë Bestuur | Kan afgeleë administrasie beïnvloed |
| `Set-LLMNR` | Bestuur naam resolusie protokol | Gewoonlik veilig om te deaktiveer |
| `Set-NetBIOS` | Beheer NetBIOS oor TCP/IP | Kan erfenis toepassings beïnvloed |
| `Set-AdminShares` | Bestuur administratiewe delings | Kan afgeleë lêertoegang beïnvloed |
| `Set-Telemetry` | Beheer data insameling | Kan diagnostiese vermoëns beïnvloed |
| `Set-GuestAccount` | Bestuur Gasrekening | Gewoonlik veilig om te deaktiveer |
| `Set-ICMP` | Beheer ping response | Kan netwerkdiagnostiek beïnvloed |
| `Set-RemoteAssistance` | Bestuur Afgeleë Bystand | Kan helpdesk operasies beïnvloed |
| `Set-NetworkDiscovery` | Beheer netwerkontdekking | Kan netwerkblaaiïng beïnvloed |
| `Set-Firewall` | Bestuur Windows Firewall | Kritiek vir netwerksekuriteit |

### Azure Wolk Sekuriteit

| Funksie | Doel | Vereistes |
|---------|------|-----------|
| `Set-AzureSecurityDefaults` | Aktiveer basiese Azure AD sekuriteit | Microsoft Graph toestemmings |
| `Set-AzureConditionalAccess` | Konfigureer toegangsbeleide | Azure AD P1/P2 lisensiëring |
| `Set-AzurePrivilegedUsers` | Ouditeer bevoorregte rekeninge | Globale Admin toestemmings |

### Onderneming Ontplooiingsopsies

| Metode | Gebruiksgeval | Vereistes |
|--------|---------------|-----------|
| **Direkte Uitvoering** | Toetsing, klein omgewings | Plaaslike admin regte |
| **Groep Beleid** | Domein omgewings | Domein admin, GP bestuur |
| **Microsoft Intune** | Wolk-bestuurde toestelle | Intune lisensiëring, Graph API |

## 🚀 Vinnige Begin

### Sekuriteitsvasstelling
```powershell
# Laai Ghost module
IEX(Invoke-WebRequest 'https://raw.githubusercontent.com/jimrtyler/Ghost/main/Ghost.ps1')

# Kontroleer huidige sekuriteitshouding
Get-Ghost
```

### Basiese Verharding (Toets Eerste)
```powershell
# Noodsaaklike verharding - toets in laboratorium omgewing eerste
Set-Ghost -SMBv1 -AutoRun -Macros

# Hersien veranderinge
Get-Ghost
```

### Onderneming Ontplooiing
```powershell
# Groep Beleid ontplooiing (domein omgewings)
Set-Ghost -SMBv1 -AutoRun -GroupPolicy

# Intune ontplooiing (wolk-bestuurde toestelle)
Set-Ghost -SMBv1 -RDP -USBStorage -Intune
```

## 📋 Installasie Metodes

### Opsie 1: Direkte Aflaai (Toetsing)
```powershell
IEX(Invoke-WebRequest 'https://raw.githubusercontent.com/jimrtyler/Ghost/main/Ghost.ps1')
```

### Opsie 2: Module Installasie
```powershell
# Installeer van PowerShell Gallery (wanneer beskikbaar)
Install-Module Ghost -Scope CurrentUser
Import-Module Ghost
```

### Opsie 3: Onderneming Ontplooiing
```powershell
# Kopieer na netwerkligging vir Groep Beleid ontplooiing
# Konfigureer Intune PowerShell skrifte vir wolk ontplooiing
```

## 💼 Gebruiksgeval Voorbeelde

### Klein Besigheid
```powershell
# Basiese beskerming met minimale impak
Set-Ghost -SMBv1 -AutoRun -Macros -ICMP
```

### Gesondheidsorg Omgewing
```powershell
# HIPAA-gefokusde verharding
Set-Ghost -SMBv1 -RDP -USBStorage -AdminShares -Telemetry
```

### Finansiële Dienste
```powershell
# Hoë-sekuriteit konfigurasie
Set-Ghost -RDP -SMBv1 -AutoRun -USBStorage -Macros -PSRemoting -AdminShares
```

### Wolk-Eerste Organisasie
```powershell
# Intune-bestuurde ontplooiing
Connect-IntuneGhost -Interactive
Set-Ghost -SMBv1 -RDP -AutoRun -Macros -Intune
```

## 🔍 Funksie Besonderhede

### Kern Verhardingsfunksies

#### Netwerkdienste
- **RDP**: Blokkeer afgeleë desktop toegang of randomiseer poort
- **SMBv1**: Deaktiveer erfenis lêerdeling protokol
- **ICMP**: Voorkom ping response vir verkenning
- **LLMNR/NetBIOS**: Blokkeer erfenis naam resolusie protokolle

#### Toepassingsekuriteit
- **Makros**: Deaktiveer makro uitvoering in Office toepassings
- **AutoRun**: Voorkom outomatiese uitvoering van verwyderbare media

#### Afgeleë Bestuur
- **PSRemoting**: Deaktiveer PowerShell afgeleë sessies
- **WinRM**: Stop Windows Afgeleë Bestuur
- **Afgeleë Bystand**: Blokkeer afgeleë bystand verbindings

#### Toegangsbeheer
- **Admin Delings**: Deaktiveer C$, ADMIN$ delings
- **Gasrekening**: Deaktiveer Gasrekening toegang
- **USB Berging**: Beperk USB toestel gebruik

### Azure Integrasie
```powershell
# Verbind na Azure tenant
Connect-AzureGhost -Interactive

# Aktiveer sekuriteit verstekwaardes
Set-AzureSecurityDefaults -Enable

# Konfigureer voorwaardelike toegang
Set-AzureConditionalAccess -BlockLegacyAuth -RequireMFA

# Ouditeer bevoorregte gebruikers
Set-AzurePrivilegedUsers -AuditOnly
```

### Intune Integrasie (Nuut in v2)
```powershell
# Verbind na Intune
Connect-IntuneGhost -Interactive

# Ontplooi via Intune beleide
Set-IntuneGhost -Settings @{
    RDP = $true
    SMBv1 = $true
    USBStorage = $true
    Macros = $true
}
```

## ⚠️ Belangrike Oorwegings

### Toetsing Vereistes
- **Laboratorium Omgewing**: Toets alle instellings in geïsoleerde omgewing eerste
- **Gefaseerde Ontplooiing**: Rol geleidelik uit om probleme te identifiseer
- **Terugrol Plan**: Verseker jy kan veranderinge omkeer indien nodig
- **Dokumentasie**: Noteer watter instellings werk vir jou omgewing

### Potensiële Impak
- **Gebruiker Produktiwiteit**: Sommige instellings kan daaglikse werksvloei beïnvloed
- **Erfenis Toepassings**: Ouer stelsels mag sekere protokolle benodig
- **Afgeleë Toegang**: Oorweeg impak op wettige afgeleë administrasie
- **Besigheidsprosesse**: Verifieer dat instellings nie kritieke funksies breek nie

### Sekuriteit Beperkings
- **Verdediging in Diepte**: Ghost is een laag van sekuriteit, nie 'n volledige oplossing nie
- **Voortdurende Bestuur**: Sekuriteit vereis kontinue monitering en opdaterings
- **Gebruiker Opleiding**: Tegniese beheer moet gepaar word met sekuriteitsbewustheid
- **Bedreiging Evolusie**: Nuwe aanvalsmetodes kan huidige beskerming omseil

## 🎯 Voorbeeld Aanval Scenario's

Terwyl Ghost algemene aanvalsvektore teiken, hang spesifieke voorkoming af van behoorlike implementering en toetsing:

### WannaCry-Styl Aanvalle
- **Vermindering**: `Set-Ghost -SMBv1` deaktiveer die kwesbare protokol
- **Oorweging**: Verseker geen erfenis stelsels vereis SMBv1 nie

### RDP-Gebaseerde Ransomware
- **Vermindering**: `Set-Ghost -RDP` blokkeer afgeleë desktop toegang
- **Oorweging**: Mag alternatiewe afgeleë toegangsmetodes vereis

### Dokument-Gebaseerde Malware
- **Vermindering**: `Set-Ghost -Macros` deaktiveer makro uitvoering
- **Oorweging**: Mag wettige makro-geaktiveerde dokumente beïnvloed

### USB-Afgelewerde Bedreigings
- **Vermindering**: `Set-Ghost -USBStorage -AutoRun` beperk USB funksionaliteit
- **Oorweging**: Mag wettige USB toestel gebruik beïnvloed

## 🏢 Onderneming Kenmerke

### Groep Beleid Ondersteuning
```powershell
# Pas instellings toe via Groep Beleid register
Set-Ghost -SMBv1 -RDP -AutoRun -GroupPolicy

# Instellings pas domeinwyd toe na GP verfris
gpupdate /force
```

### Microsoft Intune Integrasie
```powershell
# Skep Intune beleide vir Ghost instellings
Set-IntuneGhost -Settings $GhostSettings -Interactive

# Beleide ontplooi outomaties na bestuurde toestelle
```

### Nalewingsrapportering
```powershell
# Genereer sekuriteitsvasstelling verslag
Get-Ghost | Export-Csv -Path "SecurityAudit-$(Get-Date -Format 'yyyy-MM-dd').csv"

# Azure sekuriteitshouding verslag
Get-AzureGhost | Out-File "AzureSecurityReport.txt"
```

## 📚 Beste Praktyke

### Voor-Ontplooiing
1. **Dokumenteer Huidige Toestand**: Hardloop `Get-Ghost` voor veranderinge
2. **Toets Deeglik**: Valideer in nie-produksie omgewing
3. **Beplan Terugrol**: Weet hoe om elke instelling om te keer
4. **Belanghebber Hersiening**: Verseker besigheidseenhede keur veranderinge goed

### Tydens Ontplooiing
1. **Gefaseerde Benadering**: Ontplooi na loods groepe eerste
2. **Monitor Impak**: Kyk uit vir gebruiker klagtes of stelsel probleme
3. **Dokumenteer Probleme**: Noteer enige probleme vir toekomstige verwysing
4. **Kommunikeer Veranderinge**: Lig gebruikers in oor sekuriteitsverbeteringe

### Na-Ontplooiing
1. **Gereelde Vasstelling**: Hardloop periodiek `Get-Ghost` om instellings te verifieer
2. **Opdateer Dokumentasie**: Hou sekuriteit konfigurasies aktueel
3. **Hersien Effektiwiteit**: Monitor vir sekuriteit insidente
4. **Kontinue Verbetering**: Stel instellings aan gebaseer op bedreiging landskap

## 🔧 Foutopsporing

### Algemene Probleme
- **Toestemming Foute**: Verseker verhoogte PowerShell sessie
- **Diens Afhanklikhede**: Sommige dienste mag afhanklikhede hê
- **Toepassings Verenigbaarheid**: Toets met besigheidstoepassings
- **Netwerk Verbinding**: Verifieer afgeleë toegang werk steeds

### Herstel Opsies
```powershell
# Heraktiveer spesifieke dienste indien nodig
Set-RDP -Enable
Set-SMBv1 -Enable
Set-AutoRun -Enable
Set-Macros -Enable
```

## 👨‍💻 Oor die Outeur

**Jim Tyler** - Microsoft MVP vir PowerShell
- **YouTube**: [@PowerShellEngineer](https://youtube.com/@PowerShellEngineer) (10,000+ intekenare)
- **Nuusbrief**: [PowerShell.News](https://powershell.news) - Weeklikse sekuriteit intelligensie
- **Outeur**: "PowerShell for Systems Engineers"
- **Ervaring**: Dekades van PowerShell outomatisering en Windows sekuriteit

## 📄 Lisensie & Vrywaring

### MIT Lisensie
Ghost word verskaf onder die MIT Lisensie vir gratis gebruik, wysiging, en verspreiding.

### Sekuriteit Vrywaring
- **Geen Waarborg**: Ghost word verskaf "soos-is" sonder waarborg van enige aard
- **Toetsing Vereis**: Toets altyd in nie-produksie omgewings eerste
- **Professionele Leiding**: Raadpleeg sekuriteitsprofessionals vir produksie ontplooiings
- **Operasionele Impak**: Die outeurs is nie verantwoordelik vir enige operasionele ontwrigting nie
- **Omvattende Sekuriteit**: Ghost is een komponent van 'n volledige sekuriteitsstrategie

### Ondersteuning
- **GitHub Probleme**: [Rapporteer foute of versoek kenmerke](https://github.com/jimrtyler/Ghost/issues)
- **Dokumentasie**: Gebruik `Get-Help <function> -Full` vir gedetailleerde hulp
- **Gemeenskap**: PowerShell en sekuriteit gemeenskap forums

---

**🔐 Versterk jou sekuriteitshouding met Ghost - maar toets altyd eerste.**

```powershell
# Begin met vasstelling, nie aannames nie
Get-Ghost
```

**⭐ Sterre hierdie bewaarplek as Ghost help om jou sekuriteitshouding te verbeter!**