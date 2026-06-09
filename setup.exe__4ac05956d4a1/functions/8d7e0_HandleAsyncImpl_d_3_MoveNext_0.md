# <HandleAsyncImpl>d__3::MoveNext_0

- ea: `0x8d7e0`
- end: `0x8d98d`
- name: `<HandleAsyncImpl>d__3::MoveNext_0`
- size: `429`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x216b0`
- `0x2bb50`
- `0x2bbf0`
- `0x59c30`
- `0x5b6c0`
- `0x8d7e0`

## string_xrefs

- `0x8d840`: `No operation performed. No channel found corresponding to channel URI: {0}`
- `0x8d8f9`: `Channel could not be removed for {0}`

## pseudocode

```c

```

## disassembly

```asm
0x8d7e0  ldarg.0
0x8d7e1  ldfld    int32 <HandleAsyncImpl>d__3::<>1__state
0x8d7e6  stloc.0
0x8d7e7  ldarg.0
0x8d7e8  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.RemoveChannelCommandLineHandler <HandleAsyncImpl>d__3::<>4__this
0x8d7ed  stloc.1
0x8d7ee  ldloc.0
0x8d7ef  brfalse  loc_8D8BB
0x8d7f4  ldarg.0
0x8d7f5  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <HandleAsyncImpl>d__3::token
0x8d7fa  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x8d7ff  ldarg.0
0x8d800  ldloc.1
0x8d801  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.RemoveChannelCommandLineHandler::serviceOptions
0x8d806  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_Logger()
0x8d80b  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <HandleAsyncImpl>d__3::<logger>5__2
0x8d810  ldarg.0
0x8d811  ldarg.0
0x8d812  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.RemoveChannelOptions <HandleAsyncImpl>d__3::options
0x8d817  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.RemoveChannelOptions::get_ChannelUri()
0x8d81c  newobj   instance void [System]System.Uri::.ctor(string)
0x8d821  stfld    class [System]System.Uri <HandleAsyncImpl>d__3::<channelUri>5__3
0x8d826  ldloc.1
0x8d827  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.RemoveChannelCommandLineHandler::serviceOptions
0x8d82c  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IChannelProvider Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_ChannelProvider()
0x8d831  ldarg.0
0x8d832  ldfld    class [System]System.Uri <HandleAsyncImpl>d__3::<channelUri>5__3
0x8d837  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel Microsoft.VisualStudio.Setup.Installer.Services.IChannelProvider::GetChannel(class [System]System.Uri)
0x8d83c  stloc.2
0x8d83d  ldloc.2
0x8d83e  brtrue.s loc_8D87B
0x8d840  ldstr    aNoOperationPer_0// "No operation performed. No channel foun"...
0x8d845  ldarg.0
0x8d846  ldfld    class [System]System.Uri <HandleAsyncImpl>d__3::<channelUri>5__3
0x8d84b  call     string [mscorlib]System.String::Format(string, object)
0x8d850  stloc.3
0x8d851  ldarg.0
0x8d852  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <HandleAsyncImpl>d__3::<logger>5__2
0x8d857  dup
0x8d858  brtrue.s loc_8D85D
0x8d85a  pop
0x8d85b  br.s     loc_8D868
0x8d85d  ldloc.3
0x8d85e  call     T0x2B000010
0x8d863  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x8d868  ldloc.1
0x8d869  ldarg.0
0x8d86a  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.RemoveChannelOptions <HandleAsyncImpl>d__3::options
0x8d86f  ldc.i4.0
0x8d870  ldnull
0x8d871  call     instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.RemoveChannelCommandLineHandler::HandleShutdown(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.RemoveChannelOptions options, int32 code, [opt] string message)
0x8d876  leave    loc_8D96B
0x8d87b  ldloc.1
0x8d87c  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.RemoveChannelCommand Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.RemoveChannelCommandLineHandler::removeChannelCommand
0x8d881  ldloc.2
0x8d882  callvirt instance class [mscorlib]System.Threading.Tasks.Task class Microsoft.VisualStudio.Setup.Installer.Commands.CommandHandlerBase`1<class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel>::HandleAsync(var<u1>)
0x8d887  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x8d88c  stloc.s  4
0x8d88e  ldloca.s 4
0x8d890  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x8d895  brtrue.s loc_8D8D8
0x8d897  ldarg.0
0x8d898  ldc.i4.0
0x8d899  dup
0x8d89a  stloc.0
0x8d89b  stfld    int32 <HandleAsyncImpl>d__3::<>1__state
0x8d8a0  ldarg.0
0x8d8a1  ldloc.s  4
0x8d8a3  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__3::<>u__1
0x8d8a8  ldarg.0
0x8d8a9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsyncImpl>d__3::<>t__builder
0x8d8ae  ldloca.s 4
0x8d8b0  ldarg.0
0x8d8b1  call     T0x2B0005EC
0x8d8b6  leave    loc_8D98C
0x8d8bb  ldarg.0
0x8d8bc  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__3::<>u__1
0x8d8c1  stloc.s  4
0x8d8c3  ldarg.0
0x8d8c4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__3::<>u__1
0x8d8c9  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x8d8cf  ldarg.0
0x8d8d0  ldc.i4.m1
0x8d8d1  dup
0x8d8d2  stloc.0
0x8d8d3  stfld    int32 <HandleAsyncImpl>d__3::<>1__state
0x8d8d8  ldloca.s 4
0x8d8da  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x8d8df  ldloc.1
0x8d8e0  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.RemoveChannelCommandLineHandler::serviceOptions
0x8d8e5  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IChannelProvider Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_ChannelProvider()
0x8d8ea  ldarg.0
0x8d8eb  ldfld    class [System]System.Uri <HandleAsyncImpl>d__3::<channelUri>5__3
0x8d8f0  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel Microsoft.VisualStudio.Setup.Installer.Services.IChannelProvider::GetChannel(class [System]System.Uri)
0x8d8f5  stloc.2
0x8d8f6  ldloc.2
0x8d8f7  brfalse.s loc_8D934
0x8d8f9  ldstr    aChannelCouldNo// "Channel could not be removed for {0}"
0x8d8fe  ldarg.0
0x8d8ff  ldfld    class [System]System.Uri <HandleAsyncImpl>d__3::<channelUri>5__3
0x8d904  call     string [mscorlib]System.String::Format(string, object)
0x8d909  stloc.s  5
0x8d90b  ldarg.0
0x8d90c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <HandleAsyncImpl>d__3::<logger>5__2
0x8d911  dup
0x8d912  brtrue.s loc_8D917
0x8d914  pop
0x8d915  br.s     loc_8D923
0x8d917  ldloc.s  5
0x8d919  call     T0x2B000010
0x8d91e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x8d923  ldloc.1
0x8d924  ldarg.0
0x8d925  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.RemoveChannelOptions <HandleAsyncImpl>d__3::options
0x8d92a  ldc.i4.1
0x8d92b  ldloc.s  5
0x8d92d  call     instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.RemoveChannelCommandLineHandler::HandleShutdown(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.RemoveChannelOptions options, int32 code, [opt] string message)
0x8d932  leave.s  loc_8D96B
0x8d934  ldloc.1
0x8d935  ldarg.0
0x8d936  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.RemoveChannelOptions <HandleAsyncImpl>d__3::options
0x8d93b  ldc.i4.0
0x8d93c  ldnull
0x8d93d  call     instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.RemoveChannelCommandLineHandler::HandleShutdown(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.RemoveChannelOptions options, int32 code, [opt] string message)
0x8d942  leave.s  loc_8D96B
0x8d944  stloc.s  6
0x8d946  ldarg.0
0x8d947  ldc.i4.s 0xFE
0x8d949  stfld    int32 <HandleAsyncImpl>d__3::<>1__state
0x8d94e  ldarg.0
0x8d94f  ldnull
0x8d950  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <HandleAsyncImpl>d__3::<logger>5__2
0x8d955  ldarg.0
0x8d956  ldnull
0x8d957  stfld    class [System]System.Uri <HandleAsyncImpl>d__3::<channelUri>5__3
0x8d95c  ldarg.0
0x8d95d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsyncImpl>d__3::<>t__builder
0x8d962  ldloc.s  6
0x8d964  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x8d969  leave.s  loc_8D98C
0x8d96b  ldarg.0
0x8d96c  ldc.i4.s 0xFE
0x8d96e  stfld    int32 <HandleAsyncImpl>d__3::<>1__state
0x8d973  ldarg.0
0x8d974  ldnull
0x8d975  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <HandleAsyncImpl>d__3::<logger>5__2
0x8d97a  ldarg.0
0x8d97b  ldnull
0x8d97c  stfld    class [System]System.Uri <HandleAsyncImpl>d__3::<channelUri>5__3
0x8d981  ldarg.0
0x8d982  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsyncImpl>d__3::<>t__builder
0x8d987  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x8d98c  ret
```
