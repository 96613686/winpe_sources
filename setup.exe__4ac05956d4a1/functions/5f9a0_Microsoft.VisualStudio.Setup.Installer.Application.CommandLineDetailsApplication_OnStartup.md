# Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::OnStartup

- ea: `0x5f9a0`
- end: `0x5fc8e`
- name: `Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::OnStartup`
- size: `750`
- prototype: ``
- caller_count: `0`
- callee_count: `39`
- tags: `installer_update, broker_com_uri`

## callees

- `0xb2c0`
- `0xb2f0`
- `0x13790`
- `0x26a30`
- `0x26a80`
- `0x26ae0`
- `0x28a80`
- `0x28f30`
- `0x2b7a0`
- `0x2bca0`
- `0x2c110`
- `0x2d2f0`
- `0x2d510`
- `0x2d690`
- `0x2d6b0`
- `0x2d730`
- `0x4da40`
- `0x4e6c0`
- `0x54e30`
- `0x55080`
- `0x558c0`
- `0x55a20`
- `0x55a60`
- `0x55aa0`
- `0x55ab0`
- `0x5c020`
- `0x5c070`
- `0x5c0a0`
- `0x5c0d0`
- `0x5c180`
- `0x5f8b0`
- `0x5f9a0`
- `0x5fc90`
- `0x5fca0`
- `0x5fcf0`
- `0x5fd60`
- `0x5fd80`
- `0x8fc40`
- `0x8fd10`

## string_xrefs

- `0x5fba1`: `{0} completed, Navigating to the main window`
- `0x5fc0c`: `Failed to parse the command line arguments: {0}{1}{2}`

## pseudocode

```c

```

## disassembly

```asm
0x5f9a0  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x5f9a5  stloc.0
0x5f9a6  ldloc.0
0x5f9a7  ldarg.0
0x5f9a8  stfld    class Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication <>c__DisplayClass4_0::<>4__this
0x5f9ad  ldarg.0
0x5f9ae  ldarg.1
0x5f9af  call     instance void [PresentationFramework]System.Windows.Application::OnStartup(class [PresentationFramework]System.Windows.StartupEventArgs)
0x5f9b4  ldarg.0
0x5f9b5  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::get_Services()
0x5f9ba  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ShutdownRequestServiceOptions::.ctor(class [mscorlib]System.IServiceProvider services)
0x5f9bf  stloc.1
0x5f9c0  ldloc.0
0x5f9c1  ldarg.0
0x5f9c2  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::get_Services()
0x5f9c7  ldc.i4.1
0x5f9c8  call     T0x2B0003BF
0x5f9cd  stfld    class Microsoft.VisualStudio.Setup.Installer.Services.IDispatcher <>c__DisplayClass4_0::dispatcher
0x5f9d2  ldloc.0
0x5f9d3  ldloc.1
0x5f9d4  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Services.ShutdownRequestService::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ShutdownRequestServiceOptions serviceOptions)
0x5f9d9  stfld    class Microsoft.VisualStudio.Setup.Installer.Services.ShutdownRequestService <>c__DisplayClass4_0::shutdownService
0x5f9de  ldloc.0
0x5f9df  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.ShutdownRequestService <>c__DisplayClass4_0::shutdownService
0x5f9e4  ldloc.0
0x5f9e5  ldftn    instance void <>c__DisplayClass4_0::<OnStartup>b__0(object _, int32 exitCode)
0x5f9eb  newobj   instance void class [mscorlib]System.EventHandler`1<int32>::.ctor(object, native int)
0x5f9f0  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.ShutdownRequestService::add_ShutdownRequested(class [mscorlib]System.EventHandler`1<int32> value)
0x5f9f5  ldarg.0
0x5f9f6  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::get_Services()
0x5f9fb  ldloc.0
0x5f9fc  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.ShutdownRequestService <>c__DisplayClass4_0::shutdownService
0x5fa01  ldc.i4.0
0x5fa02  ldc.i4.0
0x5fa03  callvirt T0x2B0003C9
0x5fa08  ldarg.0
0x5fa09  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::get_Services()
0x5fa0e  ldsfld   class [mscorlib]System.Func`1<class Microsoft.VisualStudio.Setup.Installer.Services.IGraphicsSystem> <>c::<>9__4_1
0x5fa13  dup
0x5fa14  brtrue.s loc_5FA2D
0x5fa16  pop
0x5fa17  ldsfld   class <>c <>c::<>9
0x5fa1c  ldftn    instance class Microsoft.VisualStudio.Setup.Installer.Services.IGraphicsSystem <>c::<OnStartup>b__4_1()
0x5fa22  newobj   instance void class [mscorlib]System.Func`1<class Microsoft.VisualStudio.Setup.Installer.Services.IGraphicsSystem>::.ctor(object, native int)
0x5fa27  dup
0x5fa28  stsfld   class [mscorlib]System.Func`1<class Microsoft.VisualStudio.Setup.Installer.Services.IGraphicsSystem> <>c::<>9__4_1
0x5fa2d  call     T0x2B0003AE
0x5fa32  pop
0x5fa33  ldarg.0
0x5fa34  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::get_Services()
0x5fa39  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ApplicationViewModelServiceOptions::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x5fa3e  stloc.2
0x5fa3f  ldloc.0
0x5fa40  ldftn    instance void <>c__DisplayClass4_0::<OnStartup>b__2()
0x5fa46  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x5fa4b  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Commands.RelayCommand::.ctor(class [mscorlib]System.Action execute)
0x5fa50  stloc.3
0x5fa51  ldarg.0
0x5fa52  ldarg.1
0x5fa53  callvirt instance string[] [PresentationFramework]System.Windows.StartupEventArgs::get_Args()
0x5fa58  call     instance bool Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::ShouldShowErrorUI(string[] args)
0x5fa5d  brfalse  loc_5FBC5
0x5fa62  newobj   instance void <>c__DisplayClass4_2::.ctor()
0x5fa67  ldloc.2
0x5fa68  ldarg.0
0x5fa69  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions> Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::parserResult
0x5fa6e  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_Close()
0x5fa73  ldloc.3
0x5fa74  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ApplicationViewModelServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions> parserResult, string buttonText, class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand closeCommand)
0x5fa79  stloc.s  4
0x5fa7b  ldloc.s  4
0x5fa7d  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::InitializeAsync()
0x5fa82  callvirt instance void [mscorlib]System.Threading.Tasks.Task::Wait()
0x5fa87  ldarg.0
0x5fa88  call     instance void Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::Initialize()
0x5fa8d  ldarg.1
0x5fa8e  callvirt instance string[] [PresentationFramework]System.Windows.StartupEventArgs::get_Args()
0x5fa93  call     valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.Theme> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::GetThemeFromUnparsedArgs(string[] args)
0x5fa98  stloc.s  5
0x5fa9a  ldarg.1
0x5fa9b  callvirt instance string[] [PresentationFramework]System.Windows.StartupEventArgs::get_Args()
0x5faa0  call     valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.Theme> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::GetSessionThemeFromUnparsedArgs(string[] args)
0x5faa5  stloc.s  6
0x5faa7  ldarg.0
0x5faa8  ldloc.s  5
0x5faaa  ldloc.s  6
0x5faac  call     instance void Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::CreateTheme(valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.Theme> theme, valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.Theme> sessionTheme)
0x5fab1  ldarg.0
0x5fab2  ldarg.0
0x5fab3  ldloc.2
0x5fab4  ldloc.s  4
0x5fab6  call     instance class [PresentationFramework]System.Windows.Window Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::CreateWindow(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ApplicationViewModelServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.ICommandLineDetailsViewModel commandLineDetailsViewModel)
0x5fabb  call     instance void [PresentationFramework]System.Windows.Application::set_MainWindow(class [PresentationFramework]System.Windows.Window)
0x5fac0  ldloc.2
0x5fac1  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.WindowSignalServiceOptions::.ctor(class [mscorlib]System.IServiceProvider services)
0x5fac6  ldnull
0x5fac7  call     class Microsoft.VisualStudio.Setup.Installer.Services.IWindowSignalService Microsoft.VisualStudio.Setup.Installer.Services.WindowSignalService::CreateDefault(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.WindowSignalServiceOptions serviceOptions, string pipeName)
0x5facc  stloc.s  7
0x5face  ldloc.2
0x5facf  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::.ctor(class [mscorlib]System.IServiceProvider services)
0x5fad4  ldloc.s  7
0x5fad6  ldarg.0
0x5fad7  call     instance class [PresentationFramework]System.Windows.Window [PresentationFramework]System.Windows.Application::get_MainWindow()
0x5fadc  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Services.WindowService::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.Services.IWindowSignalService windowSignal, class [PresentationFramework]System.Windows.Window mainWindow)
0x5fae1  stloc.s  8
0x5fae3  ldarg.0
0x5fae4  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::get_Services()
0x5fae9  ldloc.s  8
0x5faeb  ldc.i4.0
0x5faec  ldc.i4.0
0x5faed  callvirt T0x2B0003AC
0x5faf2  ldloc.2
0x5faf3  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FeedbackManagerServiceOptions::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x5faf8  dup
0x5faf9  ldsfld   string Microsoft.VisualStudio.Setup.Installer.ProgramConstants::InstallerExeName
0x5fafe  call     string Microsoft.VisualStudio.Setup.Installer.InstallerInfo::get_InstallerVersion()
0x5fb03  call     string Microsoft.VisualStudio.Setup.Installer.InstallerInfo::get_Branch()
0x5fb08  ldsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::SetupExeName
0x5fb0d  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackTemplateProvider::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FeedbackManagerServiceOptions serviceOptions, string exeName, string exeVersion, string branch, string setupExeName)
0x5fb12  stloc.s  9
0x5fb14  ldloc.s  9
0x5fb16  ldnull
0x5fb17  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackManager::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FeedbackManagerServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.Feedback.IFeedbackTemplateProvider templateProvider, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.IFeedbackDiagnosticFileProvider> diagnosticFileProviders)
0x5fb1c  stloc.s  0xA
0x5fb1e  dup
0x5fb1f  ldarg.0
0x5fb20  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::get_Services()
0x5fb25  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x5fb2a  ldloc.s  0xA
0x5fb2c  ldc.i4.0
0x5fb2d  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Commands.ProvideFeedbackCommand::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.Feedback.IFeedbackManager feedbackManager, bool isSuggestion)
0x5fb32  stfld    class Microsoft.VisualStudio.Setup.Installer.Commands.ProvideFeedbackCommand <>c__DisplayClass4_2::reportProblemHandler
0x5fb37  dup
0x5fb38  ldftn    instance void <>c__DisplayClass4_2::<OnStartup>b__4()
0x5fb3e  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x5fb43  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Commands.RelayCommand::.ctor(class [mscorlib]System.Action execute)
0x5fb48  stloc.s  0xB
0x5fb4a  dup
0x5fb4b  ldarg.0
0x5fb4c  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::get_Services()
0x5fb51  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x5fb56  ldloc.s  0xA
0x5fb58  ldc.i4.1
0x5fb59  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Commands.ProvideFeedbackCommand::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.Feedback.IFeedbackManager feedbackManager, bool isSuggestion)
0x5fb5e  stfld    class Microsoft.VisualStudio.Setup.Installer.Commands.ProvideFeedbackCommand <>c__DisplayClass4_2::provideSuggestionHandler
0x5fb63  ldftn    instance void <>c__DisplayClass4_2::<OnStartup>b__5()
0x5fb69  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x5fb6e  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Commands.RelayCommand::.ctor(class [mscorlib]System.Action execute)
0x5fb73  stloc.s  0xC
0x5fb75  ldloc.2
0x5fb76  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.TitleBarViewModelServiceOptions::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x5fb7b  stloc.s  0xD
0x5fb7d  ldloc.s  4
0x5fb7f  ldloc.s  0xD
0x5fb81  ldsfld   string Microsoft.VisualStudio.Setup.Installer.ProgramConstants::InstallerBrandingName
0x5fb86  ldloc.s  0xB
0x5fb88  ldloc.s  0xC
0x5fb8a  ldloc.3
0x5fb8b  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ViewModels.TitleBarViewModel::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.TitleBarViewModelServiceOptions serviceOptions, string title, class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand reportProblemCommand, class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand provideSuggestionCommand, class [System]System.Windows.Input.ICommand closeWindowCommand)
0x5fb90  callvirt instance void Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::set_TitleBarViewModel(class Microsoft.VisualStudio.Setup.Installer.ViewModels.ITitleBarViewModel value)
0x5fb95  ldloc.2
0x5fb96  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x5fb9b  dup
0x5fb9c  brtrue.s loc_5FBA1
0x5fb9e  pop
0x5fb9f  br.s     loc_5FBB9
0x5fba1  ldstr    a0CompletedNavi// "{0} completed, Navigating to the main w"...
0x5fba6  ldc.i4.1
0x5fba7  newarr   [mscorlib]System.Object
0x5fbac  dup
0x5fbad  ldc.i4.0
0x5fbae  ldstr    aOnstartup// "OnStartup"
0x5fbb3  stelem.ref
0x5fbb4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5fbb9  ldarg.0
0x5fbba  call     instance class [PresentationFramework]System.Windows.Window [PresentationFramework]System.Windows.Application::get_MainWindow()
0x5fbbf  callvirt instance void [PresentationFramework]System.Windows.Window::Show()
0x5fbc4  ret
0x5fbc5  ldarg.0
0x5fbc6  call     instance bool Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::IsVersionError()
0x5fbcb  brtrue   loc_5FC66
0x5fbd0  ldarg.1
0x5fbd1  callvirt instance string[] [PresentationFramework]System.Windows.StartupEventArgs::get_Args()
0x5fbd6  call     bool Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::IsQuietOrPassive(string[] args)
0x5fbdb  brfalse  loc_5FC66
0x5fbe0  ldloc.2
0x5fbe1  ldarg.0
0x5fbe2  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions> Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::parserResult
0x5fbe7  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_Close()
0x5fbec  ldloc.3
0x5fbed  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ApplicationViewModelServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions> parserResult, string buttonText, class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand closeCommand)
0x5fbf2  stloc.s  0xE
0x5fbf4  ldloc.s  0xE
0x5fbf6  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::InitializeAsync()
0x5fbfb  callvirt instance void [mscorlib]System.Threading.Tasks.Task::Wait()
0x5fc00  ldloc.2
0x5fc01  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x5fc06  dup
0x5fc07  brtrue.s loc_5FC0C
0x5fc09  pop
0x5fc0a  br.s     loc_5FC66
0x5fc0c  ldstr    aFailedToParseT// "Failed to parse the command line argume"...
0x5fc11  ldc.i4.3
0x5fc12  newarr   [mscorlib]System.Object
0x5fc17  dup
0x5fc18  ldc.i4.0
0x5fc19  ldloc.s  0xE
0x5fc1b  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::get_ErrorText()
0x5fc20  stelem.ref
0x5fc21  dup
0x5fc22  ldc.i4.1
0x5fc23  call     string [mscorlib]System.Environment::get_NewLine()
0x5fc28  stelem.ref
0x5fc29  dup
0x5fc2a  ldc.i4.2
0x5fc2b  call     string [mscorlib]System.Environment::get_NewLine()
0x5fc30  ldloc.s  0xE
0x5fc32  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineDetail> Microsoft.VisualStudio.Setup.Installer.CommandLineDetails.ViewModels.CommandLineDetailsViewModel::get_CommandLineDetails()
0x5fc37  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineDetail, string> <>c::<>9__4_6
0x5fc3c  dup
0x5fc3d  brtrue.s loc_5FC56
0x5fc3f  pop
0x5fc40  ldsfld   class <>c <>c::<>9
0x5fc45  ldftn    instance string <>c::<OnStartup>b__4_6(class Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineDetail x)
0x5fc4b  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineDetail, string>::.ctor(object, native int)
0x5fc50  dup
0x5fc51  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineDetail, string> <>c::<>9__4_6
0x5fc56  call     T0x2B0003CA
0x5fc5b  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x5fc60  stelem.ref
0x5fc61  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5fc66  ldloc.0
0x5fc67  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.ShutdownRequestService <>c__DisplayClass4_0::shutdownService
0x5fc6c  ldarg.0
0x5fc6d  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions> Microsoft.VisualStudio.Setup.Installer.Application.CommandLineDetailsApplication::parserResult
0x5fc72  callvirt instance class Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineErrorInformation class Microsoft.VisualStudio.Setup.Installer.CommandLine.ICommandLineParserResult`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.IInstallerCommandLineOptions>::get_ErrorInformation()
0x5fc77  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineError> Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineErrorInformation::get_Errors()
0x5fc7c  call     bool Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineParser::IsAnyHelpOrVersionError(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.CommandLine.CommandLineError> errors)
0x5fc81  brtrue.s loc_5FC87
0x5fc83  ldc.i4.s 0x57
0x5fc85  br.s     loc_5FC88
0x5fc87  ldc.i4.0
0x5fc88  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.ShutdownRequestService::Shutdown(int32 exitCode)
0x5fc8d  ret
```
