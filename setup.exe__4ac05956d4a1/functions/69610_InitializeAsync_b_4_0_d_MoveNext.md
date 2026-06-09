# <<InitializeAsync>b__4_0>d::MoveNext

- ea: `0x69610`
- end: `0x698ad`
- name: `<<InitializeAsync>b__4_0>d::MoveNext`
- size: `669`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `installer_update`

## callees

- `0x6ee0`
- `0x9180`
- `0x9b50`
- `0x19500`
- `0x19580`
- `0x195a0`
- `0x195b0`
- `0x19750`
- `0x2c7e0`
- `0x2d660`
- `0x2d6b0`
- `0x2d6c0`
- `0x36440`
- `0x36e80`
- `0x3a7f0`
- `0x3a860`
- `0x3b530`
- `0x3b590`
- `0x3b5a0`
- `0x3c1c0`
- `0x3c200`
- `0x3c210`
- `0x59220`
- `0x69610`

## string_xrefs

- `0x69669`: `Update is available.`

## pseudocode

```c

```

## disassembly

```asm
0x69610  ldarg.0
0x69611  ldfld    int32 <<InitializeAsync>b__4_0>d::<>1__state
0x69616  stloc.0
0x69617  ldarg.0
0x69618  ldfld    class Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel <<InitializeAsync>b__4_0>d::<>4__this
0x6961d  stloc.1
0x6961e  ldloc.0
0x6961f  brfalse.s loc_69646
0x69621  ldarg.0
0x69622  ldloc.1
0x69623  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateViewModelServiceOptions Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::options
0x69628  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Telemetry()
0x6962d  dup
0x6962e  brtrue.s loc_69634
0x69630  pop
0x69631  ldnull
0x69632  br.s     loc_69641
0x69634  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::InitializeUpdateDetails
0x69639  ldnull
0x6963a  ldc.i4.0
0x6963b  ldc.i4.0
0x6963c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x69641  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <<InitializeAsync>b__4_0>d::<telemetryOperation>5__2
0x69646  nop
0x69647  ldloc.0
0x69648  brfalse  loc_69821
0x6964d  ldloc.1
0x6964e  call     instance bool Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::get_IsUpdateAvailable()
0x69653  brfalse  loc_69858
0x69658  ldloc.1
0x69659  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateViewModelServiceOptions Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::options
0x6965e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x69663  dup
0x69664  brtrue.s loc_69669
0x69666  pop
0x69667  br.s     loc_69678
0x69669  ldstr    aUpdateIsAvaila// "Update is available."
0x6966e  call     T0x2B000010
0x69673  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x69678  ldloc.1
0x69679  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateViewModelServiceOptions Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::options
0x6967e  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.ICommandLineOptionsService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerViewModelServiceOptions::get_CommandLineOptionsService()
0x69683  callvirt T0x2B000374
0x69688  dup
0x69689  brtrue.s loc_6968F
0x6968b  pop
0x6968c  ldc.i4.0
0x6968d  br.s     loc_69694
0x6968f  call     instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_Quiet()
0x69694  brfalse.s loc_696E0
0x69696  ldarg.0
0x69697  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <<InitializeAsync>b__4_0>d::<telemetryOperation>5__2
0x6969c  dup
0x6969d  brtrue.s loc_696A2
0x6969f  pop
0x696a0  br.s     loc_696B7
0x696a2  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x696a7  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::AdvertisedPackagesShown
0x696ac  ldc.i4.0
0x696ad  box      [mscorlib]System.Boolean
0x696b2  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x696b7  ldarg.0
0x696b8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <<InitializeAsync>b__4_0>d::<telemetryOperation>5__2
0x696bd  dup
0x696be  brtrue.s loc_696C6
0x696c0  pop
0x696c1  br       loc_69858
0x696c6  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x696cb  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ReleaseNotesShown
0x696d0  ldc.i4.0
0x696d1  box      [mscorlib]System.Boolean
0x696d6  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x696db  br       loc_69858
0x696e0  ldloc.1
0x696e1  ldloc.1
0x696e2  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::productModel
0x696e7  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.UpdateInformationModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_UpdateInformation()
0x696ec  callvirt instance valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.BackgroundDownloadStatus Microsoft.VisualStudio.Setup.Installer.Models.Products.UpdateInformationModel::get_BackgroundDownloadStatus()
0x696f1  stfld    valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.BackgroundDownloadStatus Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::backgroundDownloadStatus
0x696f6  ldloc.1
0x696f7  ldloc.1
0x696f8  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::productModel
0x696fd  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.UpdateInformationModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_UpdateInformation()
0x69702  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.VisualStudio.Setup.Installer.Models.Products.UpdateInformationModel::get_DownloadSize()
0x69707  stloc.2
0x69708  ldloca.s 2
0x6970a  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x6970f  brtrue.s loc_69714
0x69711  ldnull
0x69712  br.s     loc_69731
0x69714  ldloc.1
0x69715  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::productModel
0x6971a  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.UpdateInformationModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_UpdateInformation()
0x6971f  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.VisualStudio.Setup.Installer.Models.Products.UpdateInformationModel::get_DownloadSize()
0x69724  stloc.2
0x69725  ldloca.s 2
0x69727  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x6972c  call     string Microsoft.VisualStudio.Setup.Installer.CommonUtilities::FormatSizeText(int64 sizeInBytes)
0x69731  call     instance void Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::set_DownloadSizeText(string value)
0x69736  ldloc.1
0x69737  ldloc.1
0x69738  call     instance string Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::get_DownloadSizeText()
0x6973d  brfalse.s loc_69746
0x6973f  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_DownloadSize()
0x69744  br.s     loc_69747
0x69746  ldnull
0x69747  call     instance void Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::set_DownloadSizeLabel(string value)
0x6974c  ldarg.0
0x6974d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <<InitializeAsync>b__4_0>d::<telemetryOperation>5__2
0x69752  dup
0x69753  brtrue.s loc_69758
0x69755  pop
0x69756  br.s     loc_69777
0x69758  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x6975d  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::IncludeRecommendedProperty
0x69762  ldloc.1
0x69763  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::productModel
0x69768  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_IncludeRecommendedOnUpdate()
0x6976d  box      [mscorlib]System.Boolean
0x69772  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x69777  ldarg.0
0x69778  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <<InitializeAsync>b__4_0>d::<telemetryOperation>5__2
0x6977d  dup
0x6977e  brtrue.s loc_69783
0x69780  pop
0x69781  br.s     loc_69798
0x69783  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x69788  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ReleaseNotesShown
0x6978d  ldc.i4.1
0x6978e  box      [mscorlib]System.Boolean
0x69793  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x69798  ldloc.1
0x69799  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateViewModelServiceOptions Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::options
0x6979e  callvirt instance class Microsoft.VisualStudio.Setup.IReleaseNotesProvider Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateViewModelServiceOptions::get_ReleaseNotesProvider()
0x697a3  ldloc.1
0x697a4  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::productModel
0x697a9  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.VersionBundle Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductBaseModel::get_Versions()
0x697ae  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Installer.Models.VersionBundle::get_BuildVersion()
0x697b3  ldloc.1
0x697b4  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::productModel
0x697b9  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.UpdateInformationModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_UpdateInformation()
0x697be  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.VersionBundle Microsoft.VisualStudio.Setup.Installer.Models.Products.UpdateInformationModel::get_LatestVersion()
0x697c3  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Installer.Models.VersionBundle::get_BuildVersion()
0x697c8  ldloc.1
0x697c9  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::productModel
0x697ce  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Id()
0x697d3  ldloc.1
0x697d4  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::productModel
0x697d9  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Channel()
0x697de  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.IChannelModelSummary::get_Id()
0x697e3  ldc.i4   0x1388
0x697e8  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.IReleaseNotesProvider::GetHighlightedReleaseNotes(class [mscorlib]System.Version, class [mscorlib]System.Version currentVersion, string updateVersion, string sku, int32 channel)
0x697ed  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x697f2  stloc.s  4
0x697f4  ldloca.s 4
0x697f6  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x697fb  brtrue.s loc_6983E
0x697fd  ldarg.0
0x697fe  ldc.i4.0
0x697ff  dup
0x69800  stloc.0
0x69801  stfld    int32 <<InitializeAsync>b__4_0>d::<>1__state
0x69806  ldarg.0
0x69807  ldloc.s  4
0x69809  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <<InitializeAsync>b__4_0>d::<>u__1
0x6980e  ldarg.0
0x6980f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<InitializeAsync>b__4_0>d::<>t__builder
0x69814  ldloca.s 4
0x69816  ldarg.0
0x69817  call     T0x2B000443
0x6981c  leave    loc_698AC
0x69821  ldarg.0
0x69822  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <<InitializeAsync>b__4_0>d::<>u__1
0x69827  stloc.s  4
0x69829  ldarg.0
0x6982a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <<InitializeAsync>b__4_0>d::<>u__1
0x6982f  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x69835  ldarg.0
0x69836  ldc.i4.m1
0x69837  dup
0x69838  stloc.0
0x69839  stfld    int32 <<InitializeAsync>b__4_0>d::<>1__state
0x6983e  ldloca.s 4
0x69840  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x69845  stloc.3
0x69846  ldloc.1
0x69847  ldloc.3
0x69848  call     instance void Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDetailsViewModel::set_WhatsNewDetails(string value)
0x6984d  ldloc.1
0x6984e  ldstr    aProgresstext// "ProgressText"
0x69853  call     instance void Microsoft.VisualStudio.Setup.Installer.BindableObject::OnPropertyChanged([opt] string propertyName)
0x69858  leave.s  loc_69892
0x6985a  ldloc.0
0x6985b  ldc.i4.0
0x6985c  bge.s    loc_69871
0x6985e  ldarg.0
0x6985f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <<InitializeAsync>b__4_0>d::<telemetryOperation>5__2
0x69864  brfalse.s loc_69871
0x69866  ldarg.0
0x69867  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <<InitializeAsync>b__4_0>d::<telemetryOperation>5__2
0x6986c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69871  endfinally
0x69872  stloc.s  5
0x69874  ldarg.0
0x69875  ldc.i4.s 0xFE
0x69877  stfld    int32 <<InitializeAsync>b__4_0>d::<>1__state
0x6987c  ldarg.0
0x6987d  ldnull
0x6987e  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <<InitializeAsync>b__4_0>d::<telemetryOperation>5__2
0x69883  ldarg.0
0x69884  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<InitializeAsync>b__4_0>d::<>t__builder
0x69889  ldloc.s  5
0x6988b  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x69890  leave.s  loc_698AC
0x69892  ldarg.0
0x69893  ldc.i4.s 0xFE
0x69895  stfld    int32 <<InitializeAsync>b__4_0>d::<>1__state
0x6989a  ldarg.0
0x6989b  ldnull
0x6989c  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <<InitializeAsync>b__4_0>d::<telemetryOperation>5__2
0x698a1  ldarg.0
0x698a2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<InitializeAsync>b__4_0>d::<>t__builder
0x698a7  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x698ac  ret
```
