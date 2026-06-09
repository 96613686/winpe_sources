# <<GetSolutionsAsync>b__1>d::MoveNext

- ea: `0x92970`
- end: `0x92c27`
- name: `<<GetSolutionsAsync>b__1>d::MoveNext`
- size: `695`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config`

## callees

- `0x2c130`
- `0x4ebd0`
- `0x4ebf0`
- `0x4ec10`
- `0x4ece0`
- `0x4ef60`
- `0x4f200`
- `0x4f220`
- `0x4f240`
- `0x4f260`
- `0x4f280`
- `0x4f2a0`
- `0x4f2c0`
- `0x4f2e0`
- `0x4f300`
- `0x4f320`
- `0x4f340`
- `0x4f350`
- `0x4f480`
- `0x4f4c0`
- `0x92970`

## string_xrefs

- `0x92b16`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0x92970  ldarg.0
0x92971  ldfld    int32 <<GetSolutionsAsync>b__1>d::<>1__state
0x92976  stloc.0
0x92977  ldarg.0
0x92978  ldfld    class <>c__DisplayClass8_1 <<GetSolutionsAsync>b__1>d::<>4__this
0x9297d  stloc.1
0x9297e  ldloc.0
0x9297f  brfalse  loc_92AA4
0x92984  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSolutionRequest::.ctor()
0x92989  dup
0x9298a  ldloc.1
0x9298b  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackItemPreview <>c__DisplayClass8_1::item
0x92990  callvirt instance int32 Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackItemPreview::get_AnswerHubId()
0x92995  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSolutionRequest::set_AnswerHubId(int32 value)
0x9299a  dup
0x9299b  ldloc.1
0x9299c  ldfld    class <>c__DisplayClass8_0 <>c__DisplayClass8_1::CS$<>8__locals1
0x929a1  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.SolutionSearchOptions <>c__DisplayClass8_0::options
0x929a6  callvirt instance valuetype Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSort Microsoft.VisualStudio.Setup.Installer.Feedback.SolutionSearchOptions::get_OrderBy()
0x929ab  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSolutionRequest::set_OrderBy(valuetype Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSort value)
0x929b0  dup
0x929b1  ldc.i4.1
0x929b2  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSolutionRequest::set_RequestVersion(int32 value)
0x929b7  dup
0x929b8  ldloc.1
0x929b9  ldfld    class <>c__DisplayClass8_0 <>c__DisplayClass8_1::CS$<>8__locals1
0x929be  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.SolutionSearchOptions <>c__DisplayClass8_0::options
0x929c3  callvirt instance int32 Microsoft.VisualStudio.Setup.Installer.Feedback.SolutionSearchOptions::get_Skip()
0x929c8  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSolutionRequest::set_Skip(int32 value)
0x929cd  dup
0x929ce  ldloc.1
0x929cf  ldfld    class <>c__DisplayClass8_0 <>c__DisplayClass8_1::CS$<>8__locals1
0x929d4  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.SolutionSearchOptions <>c__DisplayClass8_0::options
0x929d9  callvirt instance int32 Microsoft.VisualStudio.Setup.Installer.Feedback.SolutionSearchOptions::get_Take()
0x929de  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSolutionRequest::set_Take(int32 value)
0x929e3  dup
0x929e4  ldloc.1
0x929e5  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackItemPreview <>c__DisplayClass8_1::item
0x929ea  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackItemPreview::get_TrackingId()
0x929ef  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSolutionRequest::set_TrackingId(string value)
0x929f4  dup
0x929f5  ldloc.1
0x929f6  ldfld    class <>c__DisplayClass8_0 <>c__DisplayClass8_1::CS$<>8__locals1
0x929fb  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackService <>c__DisplayClass8_0::<>4__this
0x92a00  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FeedbackManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackService::serviceOptions
0x92a05  dup
0x92a06  brtrue.s loc_92A0C
0x92a08  pop
0x92a09  ldnull
0x92a0a  br.s     loc_92A40
0x92a0c  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FeedbackManagerServiceOptions::get_Telemetry()
0x92a11  dup
0x92a12  brtrue.s loc_92A18
0x92a14  pop
0x92a15  ldnull
0x92a16  br.s     loc_92A40
0x92a18  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::get_UserId()
0x92a1d  stloc.3
0x92a1e  ldloca.s 3
0x92a20  dup
0x92a21  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x92a26  brtrue.s loc_92A2C
0x92a28  pop
0x92a29  ldnull
0x92a2a  br.s     loc_92A40
0x92a2c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x92a31  stloc.s  4
0x92a33  ldloca.s 4
0x92a35  constrained. [mscorlib]System.Guid
0x92a3b  callvirt instance string [mscorlib]System.Object::ToString()
0x92a40  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSolutionRequest::set_UserIdMakingRequest(string value)
0x92a45  dup
0x92a46  ldloc.1
0x92a47  ldfld    class <>c__DisplayClass8_0 <>c__DisplayClass8_1::CS$<>8__locals1
0x92a4c  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.SolutionSearchOptions <>c__DisplayClass8_0::options
0x92a51  callvirt instance int32 Microsoft.VisualStudio.Setup.Installer.Feedback.SolutionSearchOptions::get_Skip()
0x92a56  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSolutionRequest::set_AnswersSkip(int32 value)
0x92a5b  dup
0x92a5c  ldloc.1
0x92a5d  ldfld    class <>c__DisplayClass8_0 <>c__DisplayClass8_1::CS$<>8__locals1
0x92a62  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.SolutionSearchOptions <>c__DisplayClass8_0::options
0x92a67  callvirt instance int32 Microsoft.VisualStudio.Setup.Installer.Feedback.SolutionSearchOptions::get_Take()
0x92a6c  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSolutionRequest::set_AnswersTake(int32 value)
0x92a71  dup
0x92a72  ldloc.1
0x92a73  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackItemPreview <>c__DisplayClass8_1::item
0x92a78  callvirt instance int32 Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackItemPreview::get_AnswerHubId()
0x92a7d  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSolutionRequest::set_DetailsRequestId(int32 value)
0x92a82  dup
0x92a83  ldloc.1
0x92a84  ldfld    class <>c__DisplayClass8_0 <>c__DisplayClass8_1::CS$<>8__locals1
0x92a89  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.SolutionSearchOptions <>c__DisplayClass8_0::options
0x92a8e  callvirt instance valuetype Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSort Microsoft.VisualStudio.Setup.Installer.Feedback.SolutionSearchOptions::get_OrderBy()
0x92a93  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSolutionRequest::set_Ordering(valuetype Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSort value)
0x92a98  stloc.2
0x92a99  ldarg.0
0x92a9a  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x92a9f  stfld    class [mscorlib]System.IO.MemoryStream <<GetSolutionsAsync>b__1>d::<contentStream>5__2
0x92aa4  nop
0x92aa5  ldloc.0
0x92aa6  brfalse.s loc_92AB9
0x92aa8  ldarg.0
0x92aa9  ldarg.0
0x92aaa  ldfld    class [mscorlib]System.IO.MemoryStream <<GetSolutionsAsync>b__1>d::<contentStream>5__2
0x92aaf  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(class [mscorlib]System.IO.Stream)
0x92ab4  stfld    class [mscorlib]System.IO.StreamWriter <<GetSolutionsAsync>b__1>d::<contentWriter>5__3
0x92ab9  nop
0x92aba  ldloc.0
0x92abb  brfalse  loc_92B66
0x92ac0  ldloc.1
0x92ac1  ldfld    class <>c__DisplayClass8_0 <>c__DisplayClass8_1::CS$<>8__locals1
0x92ac6  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSolutionRequestSerializer <>c__DisplayClass8_0::serializer
0x92acb  ldarg.0
0x92acc  ldfld    class [mscorlib]System.IO.StreamWriter <<GetSolutionsAsync>b__1>d::<contentWriter>5__3
0x92ad1  ldloc.2
0x92ad2  callvirt instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSolutionRequest>::Serialize(class [mscorlib]System.IO.TextWriter, var<u1>)
0x92ad7  ldarg.0
0x92ad8  ldfld    class [mscorlib]System.IO.MemoryStream <<GetSolutionsAsync>b__1>d::<contentStream>5__2
0x92add  ldc.i4.0
0x92ade  conv.i8
0x92adf  ldc.i4.0
0x92ae0  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x92ae5  pop
0x92ae6  newobj   instance void [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.WebRequestSettings::.ctor()
0x92aeb  stloc.s  5
0x92aed  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SolutionResponseSerializer::.ctor()
0x92af2  newobj   instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializerAdapter`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SolutionResponse>::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>)
0x92af7  stloc.s  6
0x92af9  ldloc.1
0x92afa  ldfld    class <>c__DisplayClass8_0 <>c__DisplayClass8_1::CS$<>8__locals1
0x92aff  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackService <>c__DisplayClass8_0::<>4__this
0x92b04  ldfld    class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IFetchService Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackService::fetchService
0x92b09  ldloc.1
0x92b0a  ldfld    class <>c__DisplayClass8_0 <>c__DisplayClass8_1::CS$<>8__locals1
0x92b0f  ldfld    class [System]System.Uri <>c__DisplayClass8_0::uri
0x92b14  ldloc.s  5
0x92b16  ldstr    aApplicationJso// "application/json"
0x92b1b  ldarg.0
0x92b1c  ldfld    class [mscorlib]System.IO.MemoryStream <<GetSolutionsAsync>b__1>d::<contentStream>5__2
0x92b21  ldloc.s  6
0x92b23  ldloca.s 9
0x92b25  initobj  [mscorlib]System.Threading.CancellationToken
0x92b2b  ldloc.s  9
0x92b2d  callvirt T0x2B000627
0x92b32  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SolutionResponse>::GetAwaiter()
0x92b37  stloc.s  8
0x92b39  ldloca.s 8
0x92b3b  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SolutionResponse>::get_IsCompleted()
0x92b40  brtrue.s loc_92B83
0x92b42  ldarg.0
0x92b43  ldc.i4.0
0x92b44  dup
0x92b45  stloc.0
0x92b46  stfld    int32 <<GetSolutionsAsync>b__1>d::<>1__state
0x92b4b  ldarg.0
0x92b4c  ldloc.s  8
0x92b4e  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SolutionResponse> <<GetSolutionsAsync>b__1>d::<>u__1
0x92b53  ldarg.0
0x92b54  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<GetSolutionsAsync>b__1>d::<>t__builder
0x92b59  ldloca.s 8
0x92b5b  ldarg.0
0x92b5c  call     T0x2B000628
0x92b61  leave    loc_92C26
0x92b66  ldarg.0
0x92b67  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SolutionResponse> <<GetSolutionsAsync>b__1>d::<>u__1
0x92b6c  stloc.s  8
0x92b6e  ldarg.0
0x92b6f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SolutionResponse> <<GetSolutionsAsync>b__1>d::<>u__1
0x92b74  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SolutionResponse>
0x92b7a  ldarg.0
0x92b7b  ldc.i4.m1
0x92b7c  dup
0x92b7d  stloc.0
0x92b7e  stfld    int32 <<GetSolutionsAsync>b__1>d::<>1__state
0x92b83  ldloca.s 8
0x92b85  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SolutionResponse>::GetResult()
0x92b8a  stloc.s  7
0x92b8c  ldloc.s  7
0x92b8e  brfalse.s loc_92BB6
0x92b90  ldloc.s  7
0x92b92  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSolution> Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SolutionResponse::get_Answers()
0x92b97  brfalse.s loc_92BB6
0x92b99  ldloc.1
0x92b9a  ldfld    class <>c__DisplayClass8_0 <>c__DisplayClass8_1::CS$<>8__locals1
0x92b9f  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackItemPreview, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSolution>> <>c__DisplayClass8_0::solutions
0x92ba4  ldloc.1
0x92ba5  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackItemPreview <>c__DisplayClass8_1::item
0x92baa  ldloc.s  7
0x92bac  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSolution> Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SolutionResponse::get_Answers()
0x92bb1  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackItemPreview, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSolution>>::set_Item(var<u1>, !!T0)
0x92bb6  leave.s  loc_92BD0
0x92bb8  ldloc.0
0x92bb9  ldc.i4.0
0x92bba  bge.s    loc_92BCF
0x92bbc  ldarg.0
0x92bbd  ldfld    class [mscorlib]System.IO.StreamWriter <<GetSolutionsAsync>b__1>d::<contentWriter>5__3
0x92bc2  brfalse.s loc_92BCF
0x92bc4  ldarg.0
0x92bc5  ldfld    class [mscorlib]System.IO.StreamWriter <<GetSolutionsAsync>b__1>d::<contentWriter>5__3
0x92bca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x92bcf  endfinally
0x92bd0  ldarg.0
0x92bd1  ldnull
0x92bd2  stfld    class [mscorlib]System.IO.StreamWriter <<GetSolutionsAsync>b__1>d::<contentWriter>5__3
0x92bd7  leave.s  loc_92BF1
0x92bd9  ldloc.0
0x92bda  ldc.i4.0
0x92bdb  bge.s    loc_92BF0
0x92bdd  ldarg.0
0x92bde  ldfld    class [mscorlib]System.IO.MemoryStream <<GetSolutionsAsync>b__1>d::<contentStream>5__2
0x92be3  brfalse.s loc_92BF0
0x92be5  ldarg.0
0x92be6  ldfld    class [mscorlib]System.IO.MemoryStream <<GetSolutionsAsync>b__1>d::<contentStream>5__2
0x92beb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x92bf0  endfinally
0x92bf1  ldarg.0
0x92bf2  ldnull
0x92bf3  stfld    class [mscorlib]System.IO.MemoryStream <<GetSolutionsAsync>b__1>d::<contentStream>5__2
0x92bf8  leave.s  loc_92C13
0x92bfa  stloc.s  0xA
0x92bfc  ldarg.0
0x92bfd  ldc.i4.s 0xFE
0x92bff  stfld    int32 <<GetSolutionsAsync>b__1>d::<>1__state
0x92c04  ldarg.0
0x92c05  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<GetSolutionsAsync>b__1>d::<>t__builder
0x92c0a  ldloc.s  0xA
0x92c0c  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x92c11  leave.s  loc_92C26
0x92c13  ldarg.0
0x92c14  ldc.i4.s 0xFE
0x92c16  stfld    int32 <<GetSolutionsAsync>b__1>d::<>1__state
0x92c1b  ldarg.0
0x92c1c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<GetSolutionsAsync>b__1>d::<>t__builder
0x92c21  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x92c26  ret
```
