# <HandleAsync>d__5::MoveNext

- ea: `0x82290`
- end: `0x82579`
- name: `<HandleAsync>d__5::MoveNext`
- size: `745`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x2d6b0`
- `0x37ae0`
- `0x3b5f0`
- `0x3d430`
- `0x46430`
- `0x464e0`
- `0x82290`

## string_xrefs

- `0x8239a`: `remove`
- `0x822c1`: `Trying to remove out-of-support components.`

## pseudocode

```c

```

## disassembly

```asm
0x82290  ldarg.0
0x82291  ldfld    int32 <HandleAsync>d__5::<>1__state
0x82296  stloc.0
0x82297  ldarg.0
0x82298  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.RemoveOosCommand <HandleAsync>d__5::<>4__this
0x8229d  stloc.1
0x8229e  ldloc.0
0x8229f  switch   loc_82377, loc_82425, loc_82518
0x822b0  ldloc.1
0x822b1  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallationDetailsServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.RemoveOosCommand::serviceOptions
0x822b6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x822bb  dup
0x822bc  brtrue.s loc_822C1
0x822be  pop
0x822bf  br.s     loc_822D0
0x822c1  ldstr    aTryingToRemove// "Trying to remove out-of-support compone"...
0x822c6  call     T0x2B000010
0x822cb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x822d0  ldarg.0
0x822d1  ldloc.1
0x822d2  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel Microsoft.VisualStudio.Setup.Installer.InstallationDetails.RemoveOosCommand::product
0x822d7  callvirt instance class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel> Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel::get_Components()
0x822dc  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel, bool> <>c::<>9__5_0
0x822e1  dup
0x822e2  brtrue.s loc_822FB
0x822e4  pop
0x822e5  ldsfld   class <>c <>c::<>9
0x822ea  ldftn    instance bool <>c::<HandleAsync>b__5_0(class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel c)
0x822f0  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel, bool>::.ctor(object, native int)
0x822f5  dup
0x822f6  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel, bool> <>c::<>9__5_0
0x822fb  call     T0x2B0002A5
0x82300  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel> <HandleAsync>d__5::<components>5__2
0x82305  ldarg.0
0x82306  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel> <HandleAsync>d__5::<components>5__2
0x8230b  call     T0x2B0002F6
0x82310  brfalse  loc_824E1
0x82315  ldloc.1
0x82316  ldarg.0
0x82317  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel> <HandleAsync>d__5::<components>5__2
0x8231c  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel, string> <>c::<>9__5_1
0x82321  dup
0x82322  brtrue.s loc_8233B
0x82324  pop
0x82325  ldsfld   class <>c <>c::<>9
0x8232a  ldftn    instance string <>c::<HandleAsync>b__5_1(class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel x)
0x82330  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel, string>::.ctor(object, native int)
0x82335  dup
0x82336  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel, string> <>c::<>9__5_1
0x8233b  call     T0x2B0002A6
0x82340  call     instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.Installer.InstallationDetails.RemoveOosCommand::GetConfirmationAsync(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> components)
0x82345  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x8234a  stloc.2
0x8234b  ldloca.s 2
0x8234d  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x82352  brtrue.s loc_82393
0x82354  ldarg.0
0x82355  ldc.i4.0
0x82356  dup
0x82357  stloc.0
0x82358  stfld    int32 <HandleAsync>d__5::<>1__state
0x8235d  ldarg.0
0x8235e  ldloc.2
0x8235f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <HandleAsync>d__5::<>u__1
0x82364  ldarg.0
0x82365  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsync>d__5::<>t__builder
0x8236a  ldloca.s 2
0x8236c  ldarg.0
0x8236d  call     T0x2B000574
0x82372  leave    loc_82578
0x82377  ldarg.0
0x82378  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <HandleAsync>d__5::<>u__1
0x8237d  stloc.2
0x8237e  ldarg.0
0x8237f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <HandleAsync>d__5::<>u__1
0x82384  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x8238a  ldarg.0
0x8238b  ldc.i4.m1
0x8238c  dup
0x8238d  stloc.0
0x8238e  stfld    int32 <HandleAsync>d__5::<>1__state
0x82393  ldloca.s 2
0x82395  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x8239a  ldstr    aRemove// "remove"
0x8239f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x823a4  brfalse  loc_8253C
0x823a9  ldarg.0
0x823aa  ldarg.0
0x823ab  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel> <HandleAsync>d__5::<components>5__2
0x823b0  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel, string> <>c::<>9__5_2
0x823b5  dup
0x823b6  brtrue.s loc_823CF
0x823b8  pop
0x823b9  ldsfld   class <>c <>c::<>9
0x823be  ldftn    instance string <>c::<HandleAsync>b__5_2(class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel x)
0x823c4  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel, string>::.ctor(object, native int)
0x823c9  dup
0x823ca  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel, string> <>c::<>9__5_2
0x823cf  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel, class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel> <>c::<>9__5_3
0x823d4  dup
0x823d5  brtrue.s loc_823EE
0x823d7  pop
0x823d8  ldsfld   class <>c <>c::<>9
0x823dd  ldftn    instance class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel <>c::<HandleAsync>b__5_3(class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel x)
0x823e3  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel, class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel>::.ctor(object, native int)
0x823e8  dup
0x823e9  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel, class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel> <>c::<>9__5_3
0x823ee  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x823f3  call     T0x2B0002EB
0x823f8  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel> <HandleAsync>d__5::<selectablesToRemove>5__3
0x823fd  ldarg.0
0x823fe  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel> <HandleAsync>d__5::<selectablesToRemove>5__3
0x82403  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel>::get_Keys()
0x82408  ldloc.1
0x82409  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel Microsoft.VisualStudio.Setup.Installer.InstallationDetails.RemoveOosCommand::product
0x8240e  callvirt instance class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel> Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel::get_Components()
0x82413  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.Utilities.CommandLineUtilities::TopologicalSort(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> selectablesToSort, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IUISelectableModel> allSelectables)
0x82418  stloc.3
0x82419  ldarg.0
0x8241a  ldloc.3
0x8241b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x82420  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<string> <HandleAsync>d__5::<>7__wrap3
0x82425  nop
0x82426  ldloc.0
0x82427  ldc.i4.1
0x82428  beq.s    loc_82483
0x8242a  br.s     loc_824A7
0x8242c  ldarg.0
0x8242d  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<string> <HandleAsync>d__5::<>7__wrap3
0x82432  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x82437  stloc.s  4
0x82439  ldarg.0
0x8243a  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel> <HandleAsync>d__5::<selectablesToRemove>5__3
0x8243f  ldloc.s  4
0x82441  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel>::get_Item(void)
0x82446  ldc.i4.0
0x82447  ldc.i4.0
0x82448  ldc.i4.0
0x82449  ldnull
0x8244a  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IUISelectableModel::SelectAsync(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState newState, bool includeRecommended, bool includeOptional, [opt] class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> additionalTelemetryProperties)
0x8244f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x82454  stloc.s  5
0x82456  ldloca.s 5
0x82458  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x8245d  brtrue.s loc_824A0
0x8245f  ldarg.0
0x82460  ldc.i4.1
0x82461  dup
0x82462  stloc.0
0x82463  stfld    int32 <HandleAsync>d__5::<>1__state
0x82468  ldarg.0
0x82469  ldloc.s  5
0x8246b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsync>d__5::<>u__2
0x82470  ldarg.0
0x82471  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsync>d__5::<>t__builder
0x82476  ldloca.s 5
0x82478  ldarg.0
0x82479  call     T0x2B000575
0x8247e  leave    loc_82578
0x82483  ldarg.0
0x82484  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsync>d__5::<>u__2
0x82489  stloc.s  5
0x8248b  ldarg.0
0x8248c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsync>d__5::<>u__2
0x82491  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x82497  ldarg.0
0x82498  ldc.i4.m1
0x82499  dup
0x8249a  stloc.0
0x8249b  stfld    int32 <HandleAsync>d__5::<>1__state
0x824a0  ldloca.s 5
0x824a2  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x824a7  ldarg.0
0x824a8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<string> <HandleAsync>d__5::<>7__wrap3
0x824ad  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x824b2  brtrue   loc_8242C
0x824b7  leave.s  loc_824D1
0x824b9  ldloc.0
0x824ba  ldc.i4.0
0x824bb  bge.s    loc_824D0
0x824bd  ldarg.0
0x824be  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<string> <HandleAsync>d__5::<>7__wrap3
0x824c3  brfalse.s loc_824D0
0x824c5  ldarg.0
0x824c6  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<string> <HandleAsync>d__5::<>7__wrap3
0x824cb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x824d0  endfinally
0x824d1  ldarg.0
0x824d2  ldnull
0x824d3  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<string> <HandleAsync>d__5::<>7__wrap3
0x824d8  ldarg.0
0x824d9  ldnull
0x824da  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel> <HandleAsync>d__5::<selectablesToRemove>5__3
0x824df  br.s     loc_8253C
0x824e1  ldloc.1
0x824e2  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.InstallationDetails.RemoveOosCommand::ShowNoComponentsErrorAsync()
0x824e7  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x824ec  stloc.s  5
0x824ee  ldloca.s 5
0x824f0  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x824f5  brtrue.s loc_82535
0x824f7  ldarg.0
0x824f8  ldc.i4.2
0x824f9  dup
0x824fa  stloc.0
0x824fb  stfld    int32 <HandleAsync>d__5::<>1__state
0x82500  ldarg.0
0x82501  ldloc.s  5
0x82503  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsync>d__5::<>u__2
0x82508  ldarg.0
0x82509  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsync>d__5::<>t__builder
0x8250e  ldloca.s 5
0x82510  ldarg.0
0x82511  call     T0x2B000575
0x82516  leave.s  loc_82578
0x82518  ldarg.0
0x82519  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsync>d__5::<>u__2
0x8251e  stloc.s  5
0x82520  ldarg.0
0x82521  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsync>d__5::<>u__2
0x82526  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x8252c  ldarg.0
0x8252d  ldc.i4.m1
0x8252e  dup
0x8252f  stloc.0
0x82530  stfld    int32 <HandleAsync>d__5::<>1__state
0x82535  ldloca.s 5
0x82537  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x8253c  leave.s  loc_8255E
0x8253e  stloc.s  6
0x82540  ldarg.0
0x82541  ldc.i4.s 0xFE
0x82543  stfld    int32 <HandleAsync>d__5::<>1__state
0x82548  ldarg.0
0x82549  ldnull
0x8254a  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel> <HandleAsync>d__5::<components>5__2
0x8254f  ldarg.0
0x82550  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsync>d__5::<>t__builder
0x82555  ldloc.s  6
0x82557  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x8255c  leave.s  loc_82578
0x8255e  ldarg.0
0x8255f  ldc.i4.s 0xFE
0x82561  stfld    int32 <HandleAsync>d__5::<>1__state
0x82566  ldarg.0
0x82567  ldnull
0x82568  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IComponentModel> <HandleAsync>d__5::<components>5__2
0x8256d  ldarg.0
0x8256e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsync>d__5::<>t__builder
0x82573  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x82578  ret
```
