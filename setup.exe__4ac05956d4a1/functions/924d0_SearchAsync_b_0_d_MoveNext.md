# <<SearchAsync>b__0>d::MoveNext

- ea: `0x924d0`
- end: `0x92943`
- name: `<<SearchAsync>b__0>d::MoveNext`
- size: `1139`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config`

## callees

- `0x2c130`
- `0x2c140`
- `0x4e460`
- `0x4e4a0`
- `0x4eab0`
- `0x4eae0`
- `0x4eb00`
- `0x4eb20`
- `0x4eb40`
- `0x4eb60`
- `0x4eb80`
- `0x4f010`
- `0x4f030`
- `0x4f050`
- `0x4f070`
- `0x4f090`
- `0x4f0b0`
- `0x4f0d0`
- `0x4f0e0`
- `0x4f100`
- `0x4f3a0`
- `0x4f3c0`
- `0x4f3e0`
- `0x4f440`
- `0x924d0`

## string_xrefs

- `0x92699`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0x924d0  ldarg.0
0x924d1  ldfld    int32 <<SearchAsync>b__0>d::<>1__state
0x924d6  stloc.0
0x924d7  ldarg.0
0x924d8  ldfld    class <>c__DisplayClass7_0 <<SearchAsync>b__0>d::<>4__this
0x924dd  stloc.1
0x924de  ldloc.0
0x924df  ldc.i4.1
0x924e0  ble.un.s loc_9250C
0x924e2  ldarg.0
0x924e3  ldloc.1
0x924e4  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackService <>c__DisplayClass7_0::<>4__this
0x924e9  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FeedbackManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackService::serviceOptions
0x924ee  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FeedbackManagerServiceOptions::get_Telemetry()
0x924f3  dup
0x924f4  brtrue.s loc_924FA
0x924f6  pop
0x924f7  ldnull
0x924f8  br.s     loc_92507
0x924fa  ldsfld   string FeedbackService::SearchProblemsEvent
0x924ff  ldnull
0x92500  ldc.i4.0
0x92501  ldc.i4.0
0x92502  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x92507  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <<SearchAsync>b__0>d::<telemetryOperation>5__2
0x9250c  nop
0x9250d  ldloc.0
0x9250e  ldc.i4.1
0x9250f  pop
0x92510  pop
0x92511  nop
0x92512  ldloc.0
0x92513  brfalse.s loc_9256A
0x92515  ldloc.0
0x92516  ldc.i4.1
0x92517  beq      loc_9263C
0x9251c  ldloc.1
0x9251d  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackService <>c__DisplayClass7_0::<>4__this
0x92522  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackService::SearchApiUri
0x92527  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [System]System.Uri> Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackService::GetApiUri(string apiUri)
0x9252c  ldc.i4.0
0x9252d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System]System.Uri>::ConfigureAwait(!!T0)
0x92532  stloc.s  7
0x92534  ldloca.s 7
0x92536  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [System]System.Uri>::GetAwaiter()
0x9253b  stloc.s  6
0x9253d  ldloca.s 6
0x9253f  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Uri>::get_IsCompleted()
0x92544  brtrue.s loc_92587
0x92546  ldarg.0
0x92547  ldc.i4.0
0x92548  dup
0x92549  stloc.0
0x9254a  stfld    int32 <<SearchAsync>b__0>d::<>1__state
0x9254f  ldarg.0
0x92550  ldloc.s  6
0x92552  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Uri> <<SearchAsync>b__0>d::<>u__1
0x92557  ldarg.0
0x92558  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackItemPreview>> <<SearchAsync>b__0>d::<>t__builder
0x9255d  ldloca.s 6
0x9255f  ldarg.0
0x92560  call     T0x2B000622
0x92565  leave    loc_92942
0x9256a  ldarg.0
0x9256b  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Uri> <<SearchAsync>b__0>d::<>u__1
0x92570  stloc.s  6
0x92572  ldarg.0
0x92573  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Uri> <<SearchAsync>b__0>d::<>u__1
0x92578  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Uri>
0x9257e  ldarg.0
0x9257f  ldc.i4.m1
0x92580  dup
0x92581  stloc.0
0x92582  stfld    int32 <<SearchAsync>b__0>d::<>1__state
0x92587  ldloca.s 6
0x92589  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [System]System.Uri>::GetResult()
0x9258e  stloc.3
0x9258f  ldnull
0x92590  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSearchRequestSerializer::.ctor([opt] class [mscorlib]System.IServiceProvider services)
0x92595  stloc.s  4
0x92597  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSearchRequest::.ctor()
0x9259c  dup
0x9259d  ldloc.1
0x9259e  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackService <>c__DisplayClass7_0::<>4__this
0x925a3  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.IFeedbackTemplateProvider Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackService::templateProvider
0x925a8  ldloc.1
0x925a9  ldfld    string <>c__DisplayClass7_0::title
0x925ae  ldsfld   string [mscorlib]System.String::Empty
0x925b3  ldnull
0x925b4  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackTemplate Microsoft.VisualStudio.Setup.Installer.Feedback.IFeedbackTemplateProvider::GetTemplate(string, string title, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackTag> text)
0x925b9  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSearchRequest::set_SearchFor(class Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackTemplate value)
0x925be  dup
0x925bf  ldloc.1
0x925c0  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackService <>c__DisplayClass7_0::<>4__this
0x925c5  ldloc.1
0x925c6  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.SearchOptions <>c__DisplayClass7_0::options
0x925cb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackTag> Microsoft.VisualStudio.Setup.Installer.Feedback.SearchOptions::get_TopicsToFilterBy()
0x925d0  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackService::GetTopicsToFilterBy(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackTag>)
0x925d5  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSearchRequest::set_TopicsToFilterBy(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> value)
0x925da  dup
0x925db  ldloc.1
0x925dc  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.SearchOptions <>c__DisplayClass7_0::options
0x925e1  callvirt instance valuetype Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackFilter Microsoft.VisualStudio.Setup.Installer.Feedback.SearchOptions::get_Filter()
0x925e6  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSearchRequest::set_Filter(valuetype Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackFilter value)
0x925eb  dup
0x925ec  ldloc.1
0x925ed  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.SearchOptions <>c__DisplayClass7_0::options
0x925f2  callvirt instance int32 Microsoft.VisualStudio.Setup.Installer.Feedback.SearchOptions::get_Skip()
0x925f7  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSearchRequest::set_Skip(int32 value)
0x925fc  dup
0x925fd  ldloc.1
0x925fe  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.SearchOptions <>c__DisplayClass7_0::options
0x92603  callvirt instance valuetype Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSort Microsoft.VisualStudio.Setup.Installer.Feedback.SearchOptions::get_Sort()
0x92608  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSearchRequest::set_Sort(valuetype Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSort value)
0x9260d  dup
0x9260e  ldloc.1
0x9260f  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.SearchOptions <>c__DisplayClass7_0::options
0x92614  callvirt instance int32 Microsoft.VisualStudio.Setup.Installer.Feedback.SearchOptions::get_Take()
0x92619  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSearchRequest::set_Take(int32 value)
0x9261e  dup
0x9261f  ldloc.1
0x92620  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.SearchOptions <>c__DisplayClass7_0::options
0x92625  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Feedback.SearchOptions::get_StateToFilterBy()
0x9262a  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSearchRequest::set_StateGroup(string value)
0x9262f  stloc.s  5
0x92631  ldarg.0
0x92632  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x92637  stfld    class [mscorlib]System.IO.MemoryStream <<SearchAsync>b__0>d::<contentStream>5__3
0x9263c  nop
0x9263d  ldloc.0
0x9263e  ldc.i4.1
0x9263f  beq.s    loc_92652
0x92641  ldarg.0
0x92642  ldarg.0
0x92643  ldfld    class [mscorlib]System.IO.MemoryStream <<SearchAsync>b__0>d::<contentStream>5__3
0x92648  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(class [mscorlib]System.IO.Stream)
0x9264d  stfld    class [mscorlib]System.IO.StreamWriter <<SearchAsync>b__0>d::<contentWriter>5__4
0x92652  nop
0x92653  ldloc.0
0x92654  ldc.i4.1
0x92655  beq      loc_926F3
0x9265a  ldloc.s  4
0x9265c  ldarg.0
0x9265d  ldfld    class [mscorlib]System.IO.StreamWriter <<SearchAsync>b__0>d::<contentWriter>5__4
0x92662  ldloc.s  5
0x92664  callvirt instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackSearchRequest>::Serialize(class [mscorlib]System.IO.TextWriter, var<u1>)
0x92669  ldarg.0
0x9266a  ldfld    class [mscorlib]System.IO.MemoryStream <<SearchAsync>b__0>d::<contentStream>5__3
0x9266f  ldc.i4.0
0x92670  conv.i8
0x92671  ldc.i4.0
0x92672  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x92677  pop
0x92678  newobj   instance void [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.WebRequestSettings::.ctor()
0x9267d  stloc.s  8
0x9267f  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SearchResponseSerializer::.ctor()
0x92684  newobj   instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializerAdapter`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SearchResponse>::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>)
0x92689  stloc.s  9
0x9268b  ldloc.1
0x9268c  ldfld    class Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackService <>c__DisplayClass7_0::<>4__this
0x92691  ldfld    class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IFetchService Microsoft.VisualStudio.Setup.Installer.Feedback.FeedbackService::fetchService
0x92696  ldloc.3
0x92697  ldloc.s  8
0x92699  ldstr    aApplicationJso// "application/json"
0x9269e  ldarg.0
0x9269f  ldfld    class [mscorlib]System.IO.MemoryStream <<SearchAsync>b__0>d::<contentStream>5__3
0x926a4  ldloc.s  9
0x926a6  ldloca.s 0xC
0x926a8  initobj  [mscorlib]System.Threading.CancellationToken
0x926ae  ldloc.s  0xC
0x926b0  callvirt T0x2B000623
0x926b5  ldc.i4.0
0x926b6  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SearchResponse>::ConfigureAwait(!!T0)
0x926bb  stloc.s  0xD
0x926bd  ldloca.s 0xD
0x926bf  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SearchResponse>::GetAwaiter()
0x926c4  stloc.s  0xB
0x926c6  ldloca.s 0xB
0x926c8  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SearchResponse>::get_IsCompleted()
0x926cd  brtrue.s loc_92710
0x926cf  ldarg.0
0x926d0  ldc.i4.1
0x926d1  dup
0x926d2  stloc.0
0x926d3  stfld    int32 <<SearchAsync>b__0>d::<>1__state
0x926d8  ldarg.0
0x926d9  ldloc.s  0xB
0x926db  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SearchResponse> <<SearchAsync>b__0>d::<>u__2
0x926e0  ldarg.0
0x926e1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackItemPreview>> <<SearchAsync>b__0>d::<>t__builder
0x926e6  ldloca.s 0xB
0x926e8  ldarg.0
0x926e9  call     T0x2B000624
0x926ee  leave    loc_92942
0x926f3  ldarg.0
0x926f4  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SearchResponse> <<SearchAsync>b__0>d::<>u__2
0x926f9  stloc.s  0xB
0x926fb  ldarg.0
0x926fc  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SearchResponse> <<SearchAsync>b__0>d::<>u__2
0x92701  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SearchResponse>
0x92707  ldarg.0
0x92708  ldc.i4.m1
0x92709  dup
0x9270a  stloc.0
0x9270b  stfld    int32 <<SearchAsync>b__0>d::<>1__state
0x92710  ldloca.s 0xB
0x92712  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SearchResponse>::GetResult()
0x92717  stloc.s  0xA
0x92719  ldarg.0
0x9271a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <<SearchAsync>b__0>d::<telemetryOperation>5__2
0x9271f  dup
0x92720  brtrue.s loc_92726
0x92722  pop
0x92723  ldnull
0x92724  br.s     loc_9272B
0x92726  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x9272b  dup
0x9272c  dup
0x9272d  brtrue.s loc_92732
0x9272f  pop
0x92730  br.s     loc_9277B
0x92732  ldsfld   string FeedbackService::HasFeedbackItemsProperty
0x92737  ldloc.s  0xA
0x92739  brtrue.s loc_92747
0x9273b  ldloca.s 0xE
0x9273d  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x92743  ldloc.s  0xE
0x92745  br.s     loc_92768
0x92747  ldloc.s  0xA
0x92749  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackItemPreview> Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SearchResponse::get_Results()
0x9274e  dup
0x9274f  brtrue.s loc_9275E
0x92751  pop
0x92752  ldloca.s 0xE
0x92754  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x9275a  ldloc.s  0xE
0x9275c  br.s     loc_92768
0x9275e  call     T0x2B0004DE
0x92763  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x92768  stloc.s  0xE
0x9276a  ldloca.s 0xE
0x9276c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x92771  box      [mscorlib]System.Boolean
0x92776  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x9277b  dup
0x9277c  dup
0x9277d  brtrue.s loc_92782
0x9277f  pop
0x92780  br.s     loc_927CB
0x92782  ldsfld   string FeedbackService::FeedbackCountProperty
0x92787  ldloc.s  0xA
0x92789  brtrue.s loc_92797
0x9278b  ldloca.s 0xF
0x9278d  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x92793  ldloc.s  0xF
0x92795  br.s     loc_927B8
0x92797  ldloc.s  0xA
0x92799  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.FeedbackItemPreview> Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SearchResponse::get_Results()
0x9279e  dup
0x9279f  brtrue.s loc_927AE
0x927a1  pop
0x927a2  ldloca.s 0xF
0x927a4  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x927aa  ldloc.s  0xF
0x927ac  br.s     loc_927B8
0x927ae  call     T0x2B000625
0x927b3  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x927b8  stloc.s  0xF
0x927ba  ldloca.s 0xF
0x927bc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x927c1  box      [mscorlib]System.Int32
0x927c6  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x927cb  dup
0x927cc  dup
0x927cd  brtrue.s loc_927D2
0x927cf  pop
0x927d0  br.s     loc_927EF
0x927d2  ldsfld   string FeedbackService::IsDecliningFeedbackProperty
0x927d7  ldloc.s  0xA
0x927d9  brtrue.s loc_927DE
0x927db  ldc.i4.0
0x927dc  br.s     loc_927E5
0x927de  ldloc.s  0xA
0x927e0  call     instance bool Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SearchResponse::get_IsDecliningFeedback()
0x927e5  box      [mscorlib]System.Boolean
0x927ea  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x927ef  dup
0x927f0  brtrue.s loc_927F5
0x927f2  pop
0x927f3  br.s     loc_92812
0x927f5  ldsfld   string FeedbackService::IsPrivateBuildProperty
0x927fa  ldloc.s  0xA
0x927fc  brtrue.s loc_92801
0x927fe  ldc.i4.0
0x927ff  br.s     loc_92808
0x92801  ldloc.s  0xA
0x92803  call     instance bool Microsoft.VisualStudio.Setup.Installer.Feedback.Serialization.SearchResponse::get_IsPrivateBuild()
0x92808  box      [mscorlib]System.Boolean
0x9280d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x92812  ldarg.0
  ... truncated ...
```
