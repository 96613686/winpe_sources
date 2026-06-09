# Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.InstallationDetailsFooterViewModel::OnModelChanged

- ea: `0x48820`
- end: `0x4885b`
- name: `Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.InstallationDetailsFooterViewModel::OnModelChanged`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x9180`
- `0x48820`

## string_xrefs

- `0x48826`: `InstallationPath`
- `0x48833`: `InstallationPath`

## pseudocode

```c

```

## disassembly

```asm
0x48820  ldarg.2
0x48821  callvirt instance string [System]System.ComponentModel.PropertyChangedEventArgs::get_PropertyName()
0x48826  ldstr    aInstallationpa// "InstallationPath"
0x4882b  callvirt instance bool [mscorlib]System.String::Equals(string)
0x48830  brfalse.s loc_4883D
0x48832  ldarg.0
0x48833  ldstr    aInstallationpa// "InstallationPath"
0x48838  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x4883d  ldarg.2
0x4883e  callvirt instance string [System]System.ComponentModel.PropertyChangedEventArgs::get_PropertyName()
0x48843  ldstr    aOperationmode// "OperationMode"
0x48848  callvirt instance bool [mscorlib]System.String::Equals(string)
0x4884d  brfalse.s loc_4885A
0x4884f  ldarg.0
0x48850  ldstr    aOperationmode// "OperationMode"
0x48855  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x4885a  ret
```
