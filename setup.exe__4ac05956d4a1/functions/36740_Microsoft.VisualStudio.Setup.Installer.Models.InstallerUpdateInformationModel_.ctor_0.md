# Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::.ctor_0

- ea: `0x36740`
- end: `0x36788`
- name: `Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::.ctor_0`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x282a0`
- `0x28710`

## callees

- `0x36740`

## string_xrefs

- `0x36751`: `bootstrapperUrl cannot be null or empty when an update is required.`
- `0x3675f`: `opcVersion cannot be null when an update is required.`

## pseudocode

```c

```

## disassembly

```asm
0x36740  ldarg.0
0x36741  call     instance void [mscorlib]System.Object::.ctor()
0x36746  ldarg.1
0x36747  brfalse.s loc_3676A
0x36749  ldarg.2
0x3674a  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3674f  brfalse.s loc_3675C
0x36751  ldstr    aBootstrapperur// "bootstrapperUrl cannot be null or empty"...
0x36756  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3675b  throw
0x3675c  ldarg.3
0x3675d  brtrue.s loc_3676A
0x3675f  ldstr    aOpcversionCann// "opcVersion cannot be null when an updat"...
0x36764  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x36769  throw
0x3676a  ldarg.0
0x3676b  ldarg.1
0x3676c  stfld    bool Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::<IsUpdateRequired>k__BackingField
0x36771  ldarg.0
0x36772  ldarg.2
0x36773  stfld    string Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::<BootstrapperUrl>k__BackingField
0x36778  ldarg.0
0x36779  ldarg.3
0x3677a  stfld    class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::<OpcVersion>k__BackingField
0x3677f  ldarg.0
0x36780  ldarg.s  4
0x36782  stfld    string Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::<OpcUrl>k__BackingField
0x36787  ret
```
