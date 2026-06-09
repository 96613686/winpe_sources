# Microsoft.VisualStudio.Setup.Installer.FocusedUi.FocusedViewModelFactory::GetViewModelFromInstallOptions

- ea: `0x4bf80`
- end: `0x4bfc9`
- name: `Microsoft.VisualStudio.Setup.Installer.FocusedUi.FocusedViewModelFactory::GetViewModelFromInstallOptions`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4bf40`

## callees

- `0x4bf80`
- `0x4c030`
- `0x4c040`
- `0x5a590`

## string_xrefs

- `0x4bf90`: `Neither an installed or available product is available from given options.`
- `0x4bfbe`: `An available product is required for a focused install.`

## pseudocode

```c

```

## disassembly

```asm
0x4bf80  ldarg.0
0x4bf81  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.FocusedUi.FocusedViewModelFactory::serviceOptions
0x4bf86  ldarg.1
0x4bf87  ldloca.s 0
0x4bf89  call     bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::TryGetInstalledOrAvailableProductSummary(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ISelectInstanceOptions options, [out] class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel& product)
0x4bf8e  brtrue.s loc_4BF9B
0x4bf90  ldstr    aNeitherAnInsta// "Neither an installed or available produ"...
0x4bf95  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x4bf9a  throw
0x4bf9b  ldloc.0
0x4bf9c  isinst   Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel
0x4bfa1  brfalse.s loc_4BFAB
0x4bfa3  ldarg.0
0x4bfa4  ldarg.1
0x4bfa5  call     instance class Microsoft.VisualStudio.Setup.Installer.ViewModels.IViewModel Microsoft.VisualStudio.Setup.Installer.FocusedUi.FocusedViewModelFactory::HandleInstallForInstalledProduct(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions options)
0x4bfaa  ret
0x4bfab  ldloc.0
0x4bfac  isinst   Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel
0x4bfb1  stloc.1
0x4bfb2  ldloc.1
0x4bfb3  brfalse.s loc_4BFBE
0x4bfb5  ldarg.0
0x4bfb6  ldarg.1
0x4bfb7  ldloc.1
0x4bfb8  call     instance class Microsoft.VisualStudio.Setup.Installer.ViewModels.IViewModel Microsoft.VisualStudio.Setup.Installer.FocusedUi.FocusedViewModelFactory::HandleInstall(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallOptions options, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IAvailableProductSummaryModel availableProduct)
0x4bfbd  ret
0x4bfbe  ldstr    aAnAvailablePro// "An available product is required for a "...
0x4bfc3  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x4bfc8  throw
```
