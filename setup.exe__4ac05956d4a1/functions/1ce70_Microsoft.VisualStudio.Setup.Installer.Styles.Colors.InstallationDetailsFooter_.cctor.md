# Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::.cctor

- ea: `0x1ce70`
- end: `0x1cf1b`
- name: `Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::.cctor`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x1ce84`: `ComboBox.`
- `0x1ce70`: `InstallationDetails.`

## pseudocode

```c

```

## disassembly

```asm
0x1ce70  ldstr    aInstallationde// "InstallationDetails."
0x1ce75  stsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::Prefix
0x1ce7a  ldstr    aFooter// "Footer."
0x1ce7f  stsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::Footer
0x1ce84  ldstr    aCombobox// "ComboBox."
0x1ce89  stsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::Combobox
0x1ce8e  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::Prefix
0x1ce93  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::Footer
0x1ce98  ldstr    aFill// "Fill"
0x1ce9d  call     string [mscorlib]System.String::Concat(string, string, string)
0x1cea2  stsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::Fill
0x1cea7  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::Prefix
0x1ceac  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::Footer
0x1ceb1  ldstr    aStroke// "Stroke"
0x1ceb6  call     string [mscorlib]System.String::Concat(string, string, string)
0x1cebb  stsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::Stroke
0x1cec0  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::Prefix
0x1cec5  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::Footer
0x1ceca  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::Combobox
0x1cecf  ldstr    aFill// "Fill"
0x1ced4  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1ced9  stsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::ComboBoxFill
0x1cede  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::Prefix
0x1cee3  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::Footer
0x1cee8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::Combobox
0x1ceed  ldstr    aStroke// "Stroke"
0x1cef2  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1cef7  stsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::ComboBoxStroke
0x1cefc  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::Prefix
0x1cf01  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::Footer
0x1cf06  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::Combobox
0x1cf0b  ldstr    aText// "Text"
0x1cf10  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1cf15  stsfld   string Microsoft.VisualStudio.Setup.Installer.Styles.Colors.InstallationDetailsFooter::ComboBoxText
0x1cf1a  ret
```
