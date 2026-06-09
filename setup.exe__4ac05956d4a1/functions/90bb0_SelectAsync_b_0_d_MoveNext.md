# <<SelectAsync>b__0>d::MoveNext

- ea: `0x90bb0`
- end: `0x91160`
- name: `<<SelectAsync>b__0>d::MoveNext`
- size: `1456`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x21750`
- `0x21820`
- `0x22940`
- `0x265e0`
- `0x26690`
- `0x266e0`
- `0x26790`
- `0x267f0`
- `0x26960`
- `0x26970`
- `0x26980`
- `0x26990`
- `0x2d240`
- `0x2d260`
- `0x501b0`
- `0x90bb0`

## string_xrefs

- `0x90d24`: `SelectionCommand: We couldn't get a plan when trying to set package {0} to state {1}`
- `0x90dcd`: `Trying to remove a component required by the following: `
- `0x90e1f`: `Showing an error dialog with an option to remove it or cancel.`
- `0x90e6c`: `SelectionCommand.ShowingErrorDialog`
- `0x90f90`: `Graph.CommitSelection`
- `0x90fb2`: `Committing graph selection`
- `0x90fef`: `Graph.UpdateSelection`
- `0x91053`: `Notifying VMs with the updated selections: {0}`
- `0x910da`: `SelectionCommand: Couldn't find the correct package: `

## pseudocode

```c

```

## disassembly

```asm
0x90bb0  ldarg.0
0x90bb1  ldfld    int32 <<SelectAsync>b__0>d::<>1__state
0x90bb6  stloc.0
0x90bb7  ldarg.0
0x90bb8  ldfld    class <>c__DisplayClass12_0 <<SelectAsync>b__0>d::<>4__this
0x90bbd  stloc.1
0x90bbe  ldloc.0
0x90bbf  brfalse.s loc_90C11
0x90bc1  ldloc.0
0x90bc2  ldc.i4.1
0x90bc3  beq.s    loc_90C3C
0x90bc5  ldloc.1
0x90bc6  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler <>c__DisplayClass12_0::<>4__this
0x90bcb  ldfld    class [Microsoft.VisualStudio.Threading]Microsoft.VisualStudio.Threading.AsyncSemaphore Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::graphLock
0x90bd0  ldloca.s 4
0x90bd2  initobj  [mscorlib]System.Threading.CancellationToken
0x90bd8  ldloc.s  4
0x90bda  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<valuetype [Microsoft.VisualStudio.Threading]Microsoft.VisualStudio.Threading.AsyncSemaphore/Releaser> [Microsoft.VisualStudio.Threading]Microsoft.VisualStudio.Threading.AsyncSemaphore::EnterAsync(valuetype [mscorlib]System.Threading.CancellationToken)
0x90bdf  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<valuetype [Microsoft.VisualStudio.Threading]Microsoft.VisualStudio.Threading.AsyncSemaphore/Releaser>::GetAwaiter()
0x90be4  stloc.3
0x90be5  ldloca.s 3
0x90be7  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype [Microsoft.VisualStudio.Threading]Microsoft.VisualStudio.Threading.AsyncSemaphore/Releaser>::get_IsCompleted()
0x90bec  brtrue.s loc_90C2D
0x90bee  ldarg.0
0x90bef  ldc.i4.0
0x90bf0  dup
0x90bf1  stloc.0
0x90bf2  stfld    int32 <<SelectAsync>b__0>d::<>1__state
0x90bf7  ldarg.0
0x90bf8  ldloc.3
0x90bf9  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype [Microsoft.VisualStudio.Threading]Microsoft.VisualStudio.Threading.AsyncSemaphore/Releaser> <<SelectAsync>b__0>d::<>u__1
0x90bfe  ldarg.0
0x90bff  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<SelectAsync>b__0>d::<>t__builder
0x90c04  ldloca.s 3
0x90c06  ldarg.0
0x90c07  call     T0x2B00060E
0x90c0c  leave    loc_9115F
0x90c11  ldarg.0
0x90c12  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype [Microsoft.VisualStudio.Threading]Microsoft.VisualStudio.Threading.AsyncSemaphore/Releaser> <<SelectAsync>b__0>d::<>u__1
0x90c17  stloc.3
0x90c18  ldarg.0
0x90c19  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype [Microsoft.VisualStudio.Threading]Microsoft.VisualStudio.Threading.AsyncSemaphore/Releaser> <<SelectAsync>b__0>d::<>u__1
0x90c1e  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype [Microsoft.VisualStudio.Threading]Microsoft.VisualStudio.Threading.AsyncSemaphore/Releaser>
0x90c24  ldarg.0
0x90c25  ldc.i4.m1
0x90c26  dup
0x90c27  stloc.0
0x90c28  stfld    int32 <<SelectAsync>b__0>d::<>1__state
0x90c2d  ldloca.s 3
0x90c2f  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<valuetype [Microsoft.VisualStudio.Threading]Microsoft.VisualStudio.Threading.AsyncSemaphore/Releaser>::GetResult()
0x90c34  stloc.2
0x90c35  ldarg.0
0x90c36  ldloc.2
0x90c37  stfld    valuetype [Microsoft.VisualStudio.Threading]Microsoft.VisualStudio.Threading.AsyncSemaphore/Releaser <<SelectAsync>b__0>d::<lockDisposer>5__2
0x90c3c  nop
0x90c3d  ldloc.0
0x90c3e  ldc.i4.1
0x90c3f  beq      loc_90E7B
0x90c44  ldarg.0
0x90c45  ldloc.1
0x90c46  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler <>c__DisplayClass12_0::<>4__this
0x90c4b  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.IDependencyGraphProvider Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::graphProvider
0x90c50  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph Microsoft.VisualStudio.Setup.Installer.Services.IDependencyGraphProvider::GetDependencyGraph()
0x90c55  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph <<SelectAsync>b__0>d::<graph>5__3
0x90c5a  ldarg.0
0x90c5b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph <<SelectAsync>b__0>d::<graph>5__3
0x90c60  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph::get_DependencyNodes()
0x90c65  ldloc.1
0x90c66  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionParameters <>c__DisplayClass12_0::selectionParameters
0x90c6b  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Services.SelectionParameters::get_Id()
0x90c70  callvirt instance bool class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::ContainsKey(var<u1>)
0x90c75  brfalse  loc_910DA
0x90c7a  ldarg.0
0x90c7b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph <<SelectAsync>b__0>d::<graph>5__3
0x90c80  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph::get_DependencyNodes()
0x90c85  ldloc.1
0x90c86  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionParameters <>c__DisplayClass12_0::selectionParameters
0x90c8b  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Services.SelectionParameters::get_Id()
0x90c90  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::get_Item(void)
0x90c95  stloc.s  5
0x90c97  ldloc.1
0x90c98  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionParameters <>c__DisplayClass12_0::selectionParameters
0x90c9d  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState Microsoft.VisualStudio.Setup.Installer.Services.SelectionParameters::get_State()
0x90ca2  ldc.i4.2
0x90ca3  ldloc.1
0x90ca4  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionParameters <>c__DisplayClass12_0::selectionParameters
0x90ca9  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Services.SelectionParameters::get_IncludeRecommended()
0x90cae  ldloc.1
0x90caf  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionParameters <>c__DisplayClass12_0::selectionParameters
0x90cb4  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Services.SelectionParameters::get_IncludeOptional()
0x90cb9  ldloc.1
0x90cba  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler <>c__DisplayClass12_0::<>4__this
0x90cbf  ldfld    bool Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::useReducedScope
0x90cc4  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.SelectionOptions::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UserSelectedState, bool, bool, bool)
0x90cc9  stloc.s  6
0x90ccb  ldloc.1
0x90ccc  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler <>c__DisplayClass12_0::<>4__this
0x90cd1  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::options
0x90cd6  ldstr    aGraphPlanselec// "Graph.PlanSelection"
0x90cdb  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Tracer::.ctor(class [mscorlib]System.IServiceProvider, string)
0x90ce0  stloc.s  8
0x90ce2  ldloc.1
0x90ce3  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler <>c__DisplayClass12_0::<>4__this
0x90ce8  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::options
0x90ced  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionHandlerServiceOptions::get_Logger()
0x90cf2  dup
0x90cf3  brtrue.s loc_90CF8
0x90cf5  pop
0x90cf6  br.s     loc_90D07
0x90cf8  ldstr    aPlanningGraphS// "Planning graph selection"
0x90cfd  call     T0x2B000010
0x90d02  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x90d07  ldarg.0
0x90d08  ldarg.0
0x90d09  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph <<SelectAsync>b__0>d::<graph>5__3
0x90d0e  ldloc.s  5
0x90d10  ldloc.s  6
0x90d12  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.ISelectionPlan [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyGraph::PlanSelection(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionOptions)
0x90d17  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.ISelectionPlan <<SelectAsync>b__0>d::<plan>5__4
0x90d1c  ldarg.0
0x90d1d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.ISelectionPlan <<SelectAsync>b__0>d::<plan>5__4
0x90d22  brtrue.s loc_90D4F
0x90d24  ldstr    aSelectioncomma// "SelectionCommand: We couldn't get a pla"...
0x90d29  ldloc.1
0x90d2a  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionParameters <>c__DisplayClass12_0::selectionParameters
0x90d2f  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Services.SelectionParameters::get_Id()
0x90d34  ldloc.1
0x90d35  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionParameters <>c__DisplayClass12_0::selectionParameters
0x90d3a  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState Microsoft.VisualStudio.Setup.Installer.Services.SelectionParameters::get_State()
0x90d3f  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState
0x90d44  call     string [mscorlib]System.String::Format(string, object, object)
0x90d49  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x90d4e  throw
0x90d4f  leave.s  loc_90D61
0x90d51  ldloc.0
0x90d52  ldc.i4.0
0x90d53  bge.s    loc_90D60
0x90d55  ldloc.s  8
0x90d57  brfalse.s loc_90D60
0x90d59  ldloc.s  8
0x90d5b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x90d60  endfinally
0x90d61  ldloc.s  6
0x90d63  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.SelectionOptions::get_SelectedState()
0x90d68  ldc.i4.0
0x90d69  cgt.un
0x90d6b  ldloc.1
0x90d6c  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler <>c__DisplayClass12_0::<>4__this
0x90d71  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::options
0x90d76  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionHandlerServiceOptions::get_Logger()
0x90d7b  dup
0x90d7c  brtrue.s loc_90D81
0x90d7e  pop
0x90d7f  br.s     loc_90D90
0x90d81  ldstr    aBuildingTheReq// "Building the required chain"
0x90d86  call     T0x2B000010
0x90d8b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x90d90  ldloc.1
0x90d91  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler <>c__DisplayClass12_0::<>4__this
0x90d96  ldloc.s  5
0x90d98  ldarg.0
0x90d99  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.ISelectionPlan <<SelectAsync>b__0>d::<plan>5__4
0x90d9e  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::BuildRequiredChain(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.ISelectionPlan plan)
0x90da3  stloc.s  7
0x90da5  brtrue   loc_90F85
0x90daa  ldloc.s  7
0x90dac  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::get_Count()
0x90db1  ldc.i4.0
0x90db2  ble      loc_90F85
0x90db7  ldloc.1
0x90db8  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler <>c__DisplayClass12_0::<>4__this
0x90dbd  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::options
0x90dc2  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionHandlerServiceOptions::get_Logger()
0x90dc7  dup
0x90dc8  brtrue.s loc_90DCD
0x90dca  pop
0x90dcb  br.s     loc_90DDC
0x90dcd  ldstr    aTryingToRemove_0// "Trying to remove a component required b"...
0x90dd2  call     T0x2B000010
0x90dd7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x90ddc  ldloc.1
0x90ddd  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler <>c__DisplayClass12_0::<>4__this
0x90de2  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::options
0x90de7  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionHandlerServiceOptions::get_Logger()
0x90dec  dup
0x90ded  brtrue.s loc_90DF2
0x90def  pop
0x90df0  br.s     loc_90E09
0x90df2  ldloc.1
0x90df3  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler <>c__DisplayClass12_0::<>4__this
0x90df8  ldloc.s  7
0x90dfa  call     instance string Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::GetRequiredComponentRemoveOptionLog(class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> requiredList)
0x90dff  call     T0x2B000010
0x90e04  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x90e09  ldloc.1
0x90e0a  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler <>c__DisplayClass12_0::<>4__this
0x90e0f  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::options
0x90e14  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionHandlerServiceOptions::get_Logger()
0x90e19  dup
0x90e1a  brtrue.s loc_90E1F
0x90e1c  pop
0x90e1d  br.s     loc_90E2E
0x90e1f  ldstr    aShowingAnError// "Showing an error dialog with an option "...
0x90e24  call     T0x2B000010
0x90e29  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x90e2e  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_RemoveComponentsDialogTitle()
0x90e33  ldloc.1
0x90e34  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler <>c__DisplayClass12_0::<>4__this
0x90e39  ldloc.s  7
0x90e3b  call     instance string Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::ConstructRemoveDialogText(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> nodesToBeRemoved)
0x90e40  stloc.s  9
0x90e42  ldloc.1
0x90e43  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler <>c__DisplayClass12_0::<>4__this
0x90e48  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton> Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::GetRemoveComponentDialogButtons()
0x90e4d  stloc.s  0xA
0x90e4f  ldloc.s  9
0x90e51  ldloc.s  0xA
0x90e53  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::DeselectRequiredPackagePrompt
0x90e58  ldc.i4.0
0x90e59  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorDialogResources::.ctor(string title, string message, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton> buttons, string recordedName, [opt] bool showTroubleshootingTipsLink)
0x90e5e  stloc.s  0xB
0x90e60  ldarg.0
0x90e61  ldloc.1
0x90e62  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler <>c__DisplayClass12_0::<>4__this
0x90e67  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::options
0x90e6c  ldstr    aSelectioncomma_0// "SelectionCommand.ShowingErrorDialog"
0x90e71  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Tracer::.ctor(class [mscorlib]System.IServiceProvider, string)
0x90e76  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Tracer <<SelectAsync>b__0>d::<>7__wrap4
0x90e7b  nop
0x90e7c  ldloc.0
0x90e7d  ldc.i4.1
0x90e7e  beq.s    loc_90ECB
0x90e80  ldloc.1
0x90e81  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler <>c__DisplayClass12_0::<>4__this
0x90e86  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::options
0x90e8b  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionHandlerServiceOptions::get_ErrorDialogService()
0x90e90  ldloc.s  0xB
0x90e92  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService::ShowError(class Microsoft.VisualStudio.Setup.Installer.Dialogs.IErrorDialogResources resources)
0x90e97  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x90e9c  stloc.s  0xC
0x90e9e  ldloca.s 0xC
0x90ea0  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x90ea5  brtrue.s loc_90EE8
0x90ea7  ldarg.0
0x90ea8  ldc.i4.1
0x90ea9  dup
0x90eaa  stloc.0
0x90eab  stfld    int32 <<SelectAsync>b__0>d::<>1__state
0x90eb0  ldarg.0
0x90eb1  ldloc.s  0xC
0x90eb3  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <<SelectAsync>b__0>d::<>u__2
0x90eb8  ldarg.0
0x90eb9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<SelectAsync>b__0>d::<>t__builder
0x90ebe  ldloca.s 0xC
0x90ec0  ldarg.0
0x90ec1  call     T0x2B00060F
0x90ec6  leave    loc_9115F
0x90ecb  ldarg.0
0x90ecc  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <<SelectAsync>b__0>d::<>u__2
0x90ed1  stloc.s  0xC
0x90ed3  ldarg.0
0x90ed4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <<SelectAsync>b__0>d::<>u__2
0x90ed9  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x90edf  ldarg.0
0x90ee0  ldc.i4.m1
0x90ee1  dup
0x90ee2  stloc.0
0x90ee3  stfld    int32 <<SelectAsync>b__0>d::<>1__state
0x90ee8  ldloca.s 0xC
0x90eea  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x90eef  ldstr    aCancel// "cancel"
0x90ef4  callvirt instance bool [mscorlib]System.String::Equals(string)
0x90ef9  brfalse.s loc_90F64
0x90efb  ldloc.1
0x90efc  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler <>c__DisplayClass12_0::<>4__this
0x90f01  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::options
0x90f06  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.SelectionHandlerServiceOptions::get_Logger()
0x90f0b  dup
0x90f0c  brtrue.s loc_90F11
0x90f0e  pop
0x90f0f  br.s     loc_90F20
0x90f11  ldstr    aUserCanceledBa// "User canceled. Bailing out and notifyin"...
0x90f16  call     T0x2B000010
0x90f1b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x90f20  ldloc.1
0x90f21  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler <>c__DisplayClass12_0::<>4__this
0x90f26  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.ISelectionNotificationManager Microsoft.VisualStudio.Setup.Installer.Services.SelectionHandler::manager
0x90f2b  ldarg.0
0x90f2c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.ISelectionPlan <<SelectAsync>b__0>d::<plan>5__4
0x90f31  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Dependencies.ISelectionPlan::get_UpdatedSelections()
0x90f36  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState>, string> <>c::<>9__12_2
0x90f3b  dup
0x90f3c  brtrue.s loc_90F55
0x90f3e  pop
0x90f3f  ldsfld   class <>c <>c::<>9
0x90f44  ldftn    instance string <>c::<SelectAsync>b__12_2(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState> x)
0x90f4a  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState>, string>::.ctor(object, native int)
0x90f4f  dup
0x90f50  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState>, string> <>c::<>9__12_2
0x90f55  call     T0x2B000610
  ... truncated ...
```
