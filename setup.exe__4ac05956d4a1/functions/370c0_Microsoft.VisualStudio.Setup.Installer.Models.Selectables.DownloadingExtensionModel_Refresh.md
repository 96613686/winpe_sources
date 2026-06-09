# Microsoft.VisualStudio.Setup.Installer.Models.Selectables.DownloadingExtensionModel::Refresh

- ea: `0x370c0`
- end: `0x3717c`
- name: `Microsoft.VisualStudio.Setup.Installer.Models.Selectables.DownloadingExtensionModel::Refresh`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x77990`

## callees

- `0x9180`

## string_xrefs

- `0x370c1`: `LocalPath`
- `0x370cc`: `LicenseUri`
- `0x37119`: `IsInstalled`
- `0x37145`: `ComponentDependencies`

## pseudocode

```c

```

## disassembly

```asm
0x370c0  ldarg.0
0x370c1  ldstr    aLocalpath// "LocalPath"
0x370c6  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x370cb  ldarg.0
0x370cc  ldstr    aLicenseuri// "LicenseUri"
0x370d1  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x370d6  ldarg.0
0x370d7  ldstr    aVersion_0// "Version"
0x370dc  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x370e1  ldarg.0
0x370e2  ldstr    aId// "Id"
0x370e7  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x370ec  ldarg.0
0x370ed  ldstr    aName_0// "Name"
0x370f2  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x370f7  ldarg.0
0x370f8  ldstr    aDescription// "Description"
0x370fd  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x37102  ldarg.0
0x37103  ldstr    aLongdescriptio// "LongDescription"
0x37108  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x3710d  ldarg.0
0x3710e  ldstr    aKeywords// "Keywords"
0x37113  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x37118  ldarg.0
0x37119  ldstr    aIsinstalled// "IsInstalled"
0x3711e  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x37123  ldarg.0
0x37124  ldstr    aIsrequired// "IsRequired"
0x37129  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x3712e  ldarg.0
0x3712f  ldstr    aOutofsupport// "OutOfSupport"
0x37134  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x37139  ldarg.0
0x3713a  ldstr    aApplicability// "Applicability"
0x3713f  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x37144  ldarg.0
0x37145  ldstr    aComponentdepen// "ComponentDependencies"
0x3714a  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x3714f  ldarg.0
0x37150  ldstr    aVerificationre_0// "VerificationResult"
0x37155  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x3715a  ldarg.0
0x3715b  ldstr    aSha256hash// "Sha256Hash"
0x37160  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x37165  ldarg.0
0x37166  ldstr    aCertificate// "Certificate"
0x3716b  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x37170  ldarg.0
0x37171  ldstr    aVsixid// "VsixId"
0x37176  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x3717b  ret
```
