# Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.AdvancedSettingsPageViewModel::OnValidationErrorChanged

- ea: `0x47190`
- end: `0x471c3`
- name: `Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.AdvancedSettingsPageViewModel::OnValidationErrorChanged`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x9180`
- `0x47210`

## string_xrefs

- `0x47197`: `TargetInstallSizeText`
- `0x471a2`: `CacheSizeText`
- `0x471ad`: `SharedInstallSizeText`
- `0x471b8`: `SystemCacheInstallSizeText`

## pseudocode

```c

```

## disassembly

```asm
0x47190  ldarg.0
0x47191  call     instance void Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ViewModels.AdvancedSettingsPageViewModel::CalculateInstallSize()
0x47196  ldarg.0
0x47197  ldstr    aTargetinstalls// "TargetInstallSizeText"
0x4719c  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x471a1  ldarg.0
0x471a2  ldstr    aCachesizetext// "CacheSizeText"
0x471a7  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x471ac  ldarg.0
0x471ad  ldstr    aSharedinstalls// "SharedInstallSizeText"
0x471b2  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x471b7  ldarg.0
0x471b8  ldstr    aSystemcacheins// "SystemCacheInstallSizeText"
0x471bd  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x471c2  ret
```
