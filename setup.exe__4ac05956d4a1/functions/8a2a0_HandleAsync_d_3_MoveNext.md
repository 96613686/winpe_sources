# <HandleAsync>d__3::MoveNext

- ea: `0x8a2a0`
- end: `0x8a4fd`
- name: `<HandleAsync>d__3::MoveNext`
- size: `605`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0xa930`
- `0x22770`
- `0x2b9c0`
- `0x2bab0`
- `0x36450`
- `0x55220`
- `0x552d0`
- `0x55310`
- `0x8a2a0`

## string_xrefs

- `0x8a3f0`: `Removed channel for {0}`
- `0x8a43b`: `Failed to remove channel with {0}`

## pseudocode

```c

```

## disassembly

```asm
0x8a2a0  ldarg.0
0x8a2a1  ldfld    int32 <HandleAsync>d__3::<>1__state
0x8a2a6  stloc.0
0x8a2a7  ldarg.0
0x8a2a8  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.RemoveChannelCommand <HandleAsync>d__3::<>4__this
0x8a2ad  stloc.1
0x8a2ae  ldloc.0
0x8a2af  switch   loc_8A328, loc_8A39A, loc_8A4A1
0x8a2c0  ldloc.1
0x8a2c1  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.RemoveChannelCommand::serviceOptions
0x8a2c6  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IProductsRepository Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions::get_ProductsRepository()
0x8a2cb  ldarg.0
0x8a2cc  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel <HandleAsync>d__3::channel
0x8a2d1  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel> Microsoft.VisualStudio.Setup.Installer.Extensions::GetExistingProductSummaries(class Microsoft.VisualStudio.Setup.Installer.Services.IProductsProviderService productsProvider, class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel channel)
0x8a2d6  stloc.2
0x8a2d7  ldloc.2
0x8a2d8  call     T0x2B0000AB
0x8a2dd  brfalse.s loc_8A350
0x8a2df  ldloc.1
0x8a2e0  ldarg.0
0x8a2e1  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel <HandleAsync>d__3::channel
0x8a2e6  ldloc.2
0x8a2e7  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.Commands.RemoveChannelCommand::ShowChannelWarning(class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel channel, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel> installedProducts)
0x8a2ec  ldc.i4.0
0x8a2ed  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x8a2f2  stloc.s  4
0x8a2f4  ldloca.s 4
0x8a2f6  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x8a2fb  stloc.3
0x8a2fc  ldloca.s 3
0x8a2fe  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x8a303  brtrue.s loc_8A344
0x8a305  ldarg.0
0x8a306  ldc.i4.0
0x8a307  dup
0x8a308  stloc.0
0x8a309  stfld    int32 <HandleAsync>d__3::<>1__state
0x8a30e  ldarg.0
0x8a30f  ldloc.3
0x8a310  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleAsync>d__3::<>u__1
0x8a315  ldarg.0
0x8a316  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsync>d__3::<>t__builder
0x8a31b  ldloca.s 3
0x8a31d  ldarg.0
0x8a31e  call     T0x2B0005CA
0x8a323  leave    loc_8A4FC
0x8a328  ldarg.0
0x8a329  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleAsync>d__3::<>u__1
0x8a32e  stloc.3
0x8a32f  ldarg.0
0x8a330  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <HandleAsync>d__3::<>u__1
0x8a335  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x8a33b  ldarg.0
0x8a33c  ldc.i4.m1
0x8a33d  dup
0x8a33e  stloc.0
0x8a33f  stfld    int32 <HandleAsync>d__3::<>1__state
0x8a344  ldloca.s 3
0x8a346  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x8a34b  leave    loc_8A4E9
0x8a350  ldloc.1
0x8a351  ldarg.0
0x8a352  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel <HandleAsync>d__3::channel
0x8a357  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.VisualStudio.Setup.Installer.Commands.RemoveChannelCommand::ShowRemoveConfirmationPrompt(class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel channel)
0x8a35c  ldc.i4.0
0x8a35d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0x8a362  stloc.s  6
0x8a364  ldloca.s 6
0x8a366  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0x8a36b  stloc.s  5
0x8a36d  ldloca.s 5
0x8a36f  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::get_IsCompleted()
0x8a374  brtrue.s loc_8A3B7
0x8a376  ldarg.0
0x8a377  ldc.i4.1
0x8a378  dup
0x8a379  stloc.0
0x8a37a  stfld    int32 <HandleAsync>d__3::<>1__state
0x8a37f  ldarg.0
0x8a380  ldloc.s  5
0x8a382  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <HandleAsync>d__3::<>u__2
0x8a387  ldarg.0
0x8a388  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsync>d__3::<>t__builder
0x8a38d  ldloca.s 5
0x8a38f  ldarg.0
0x8a390  call     T0x2B0005CB
0x8a395  leave    loc_8A4FC
0x8a39a  ldarg.0
0x8a39b  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <HandleAsync>d__3::<>u__2
0x8a3a0  stloc.s  5
0x8a3a2  ldarg.0
0x8a3a3  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <HandleAsync>d__3::<>u__2
0x8a3a8  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>
0x8a3ae  ldarg.0
0x8a3af  ldc.i4.m1
0x8a3b0  dup
0x8a3b1  stloc.0
0x8a3b2  stfld    int32 <HandleAsync>d__3::<>1__state
0x8a3b7  ldloca.s 5
0x8a3b9  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::GetResult()
0x8a3be  brfalse  loc_8A4CE
0x8a3c3  ldc.i4.0
0x8a3c4  stloc.s  7
0x8a3c6  ldc.i4.0
0x8a3c7  stloc.s  9
0x8a3c9  ldloc.1
0x8a3ca  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.RemoveChannelCommand::serviceOptions
0x8a3cf  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IProductsRepository Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions::get_ProductsRepository()
0x8a3d4  ldarg.0
0x8a3d5  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel <HandleAsync>d__3::channel
0x8a3da  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.IProductsRepository::RemoveChannel(class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel channel)
0x8a3df  ldloc.1
0x8a3e0  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.RemoveChannelCommand::serviceOptions
0x8a3e5  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerBaseServiceOptions::get_Logger()
0x8a3ea  dup
0x8a3eb  brtrue.s loc_8A3F0
0x8a3ed  pop
0x8a3ee  br.s     loc_8A40E
0x8a3f0  ldstr    aRemovedChannel// "Removed channel for {0}"
0x8a3f5  ldc.i4.1
0x8a3f6  newarr   [mscorlib]System.Object
0x8a3fb  dup
0x8a3fc  ldc.i4.0
0x8a3fd  ldarg.0
0x8a3fe  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel <HandleAsync>d__3::channel
0x8a403  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Models.IChannelModelSummary::get_UpdateUri()
0x8a408  stelem.ref
0x8a409  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x8a40e  leave.s  loc_8A417
0x8a410  stloc.s  8
0x8a412  ldc.i4.1
0x8a413  stloc.s  9
0x8a415  leave.s  loc_8A417
0x8a417  ldloc.s  9
0x8a419  ldc.i4.1
0x8a41a  bne.un   loc_8A4C7
0x8a41f  ldloc.s  8
0x8a421  castclass [mscorlib]System.Exception
0x8a426  stloc.s  0xA
0x8a428  ldloc.1
0x8a429  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.RemoveChannelCommand::serviceOptions
0x8a42e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerBaseServiceOptions::get_Logger()
0x8a433  dup
0x8a434  brtrue.s loc_8A439
0x8a436  pop
0x8a437  br.s     loc_8A45A
0x8a439  ldloc.s  0xA
0x8a43b  ldstr    aFailedToRemove_2// "Failed to remove channel with {0}"
0x8a440  ldc.i4.1
0x8a441  newarr   [mscorlib]System.Object
0x8a446  dup
0x8a447  ldc.i4.0
0x8a448  ldloc.s  0xA
0x8a44a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x8a44f  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x8a454  stelem.ref
0x8a455  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x8a45a  ldloc.1
0x8a45b  ldarg.0
0x8a45c  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel <HandleAsync>d__3::channel
0x8a461  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.VisualStudio.Setup.Installer.Commands.RemoveChannelCommand::ShowChannelRemoveFailure(class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel channel)
0x8a466  ldc.i4.0
0x8a467  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0x8a46c  stloc.s  6
0x8a46e  ldloca.s 6
0x8a470  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0x8a475  stloc.s  5
0x8a477  ldloca.s 5
0x8a479  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::get_IsCompleted()
0x8a47e  brtrue.s loc_8A4BE
0x8a480  ldarg.0
0x8a481  ldc.i4.2
0x8a482  dup
0x8a483  stloc.0
0x8a484  stfld    int32 <HandleAsync>d__3::<>1__state
0x8a489  ldarg.0
0x8a48a  ldloc.s  5
0x8a48c  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <HandleAsync>d__3::<>u__2
0x8a491  ldarg.0
0x8a492  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsync>d__3::<>t__builder
0x8a497  ldloca.s 5
0x8a499  ldarg.0
0x8a49a  call     T0x2B0005CB
0x8a49f  leave.s  loc_8A4FC
0x8a4a1  ldarg.0
0x8a4a2  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <HandleAsync>d__3::<>u__2
0x8a4a7  stloc.s  5
0x8a4a9  ldarg.0
0x8a4aa  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <HandleAsync>d__3::<>u__2
0x8a4af  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>
0x8a4b5  ldarg.0
0x8a4b6  ldc.i4.m1
0x8a4b7  dup
0x8a4b8  stloc.0
0x8a4b9  stfld    int32 <HandleAsync>d__3::<>1__state
0x8a4be  ldloca.s 5
0x8a4c0  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::GetResult()
0x8a4c5  stloc.s  7
0x8a4c7  ldloc.s  7
0x8a4c9  brtrue   loc_8A3C3
0x8a4ce  leave.s  loc_8A4E9
0x8a4d0  stloc.s  0xB
0x8a4d2  ldarg.0
0x8a4d3  ldc.i4.s 0xFE
0x8a4d5  stfld    int32 <HandleAsync>d__3::<>1__state
0x8a4da  ldarg.0
0x8a4db  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsync>d__3::<>t__builder
0x8a4e0  ldloc.s  0xB
0x8a4e2  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x8a4e7  leave.s  loc_8A4FC
0x8a4e9  ldarg.0
0x8a4ea  ldc.i4.s 0xFE
0x8a4ec  stfld    int32 <HandleAsync>d__3::<>1__state
0x8a4f1  ldarg.0
0x8a4f2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsync>d__3::<>t__builder
0x8a4f7  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x8a4fc  ret
```
