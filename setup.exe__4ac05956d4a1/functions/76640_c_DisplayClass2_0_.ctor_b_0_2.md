# <>c__DisplayClass2_0::<.ctor>b__0_2

- ea: `0x76640`
- end: `0x76680`
- name: `<>c__DisplayClass2_0::<.ctor>b__0_2`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2d6b0`
- `0x76640`

## string_xrefs

- `0x76651`: `Executing update command from {0}`
- `0x7665e`: `ProductCardUpdateMainPageViewModel`

## pseudocode

```c

```

## disassembly

```asm
0x76640  ldarg.0
0x76641  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerViewModelServiceOptions <>c__DisplayClass2_0::serviceOptions
0x76646  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x7664b  dup
0x7664c  brtrue.s loc_76651
0x7664e  pop
0x7664f  br.s     loc_76669
0x76651  ldstr    aExecutingUpdat// "Executing update command from {0}"
0x76656  ldc.i4.1
0x76657  newarr   [mscorlib]System.Object
0x7665c  dup
0x7665d  ldc.i4.0
0x7665e  ldstr    aProductcardupd_1// "ProductCardUpdateMainPageViewModel"
0x76663  stelem.ref
0x76664  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x76669  ldarg.0
0x7666a  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel> <>c__DisplayClass2_0::updateCommand
0x7666f  ldarg.0
0x76670  ldfld    class Microsoft.VisualStudio.Setup.Installer.ProductCard.ViewModels.ProductCardUpdateMainPageViewModel <>c__DisplayClass2_0::<>4__this
0x76675  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel Microsoft.VisualStudio.Setup.Installer.ProductCard.ViewModels.ProductCardUpdateMainPageViewModel::product
0x7667a  callvirt instance void class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel>::Execute(var<u1>)
0x7667f  ret
```
