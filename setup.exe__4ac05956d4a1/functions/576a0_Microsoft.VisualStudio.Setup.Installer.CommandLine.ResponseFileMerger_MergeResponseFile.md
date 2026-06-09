# Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::MergeResponseFile

- ea: `0x576a0`
- end: `0x57a04`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::MergeResponseFile`
- size: `868`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2bc50`
- `0x2bc80`
- `0x576a0`
- `0x57a10`
- `0x57ab0`
- `0x57b40`
- `0x57b70`
- `0x57ba0`
- `0x57c70`
- `0x57cd0`
- `0x593e0`
- `0x59a10`
- `0x59a20`
- `0x8b5a0`

## string_xrefs

- `0x5794a`: `comment`

## pseudocode

```c

```

## disassembly

```asm
0x576a0  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x576a5  stloc.0
0x576a6  ldloc.0
0x576a7  ldarg.0
0x576a8  stfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger <>c__DisplayClass4_0::<>4__this
0x576ad  ldloc.0
0x576ae  ldarg.1
0x576af  stfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions <>c__DisplayClass4_0::options
0x576b4  ldloc.0
0x576b5  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions <>c__DisplayClass4_0::options
0x576ba  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions::get_ResponseFilePath()
0x576bf  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x576c4  brtrue   loc_579F7
0x576c9  ldarg.0
0x576ca  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineParserServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::serviceOptions
0x576cf  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineParserServiceOptions::get_FileSystem()
0x576d4  ldloc.0
0x576d5  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions <>c__DisplayClass4_0::options
0x576da  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions::get_ResponseFilePath()
0x576df  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x576e4  brtrue.s loc_57701
0x576e6  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_FileNotFound_Args1()
0x576eb  ldloc.0
0x576ec  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions <>c__DisplayClass4_0::options
0x576f1  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions::get_ResponseFilePath()
0x576f6  call     string [mscorlib]System.String::Format(string, object)
0x576fb  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x57700  throw
0x57701  ldarg.0
0x57702  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineParserServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::serviceOptions
0x57707  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineParserServiceOptions::get_FileSystem()
0x5770c  ldloc.0
0x5770d  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions <>c__DisplayClass4_0::options
0x57712  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions::get_ResponseFilePath()
0x57717  callvirt instance class [mscorlib]System.IO.TextReader [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenText(string)
0x5771c  stloc.s  5
0x5771e  ldloc.s  5
0x57720  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader::.ctor(class [mscorlib]System.IO.TextReader)
0x57725  stloc.s  6
0x57727  ldloc.s  6
0x57729  call     class [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::Load(class [Newtonsoft.Json]Newtonsoft.Json.JsonReader)
0x5772e  stloc.1
0x5772f  leave.s  loc_57749
0x57731  ldloc.s  6
0x57733  brfalse.s loc_5773C
0x57735  ldloc.s  6
0x57737  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5773c  endfinally
0x5773d  ldloc.s  5
0x5773f  brfalse.s loc_57748
0x57741  ldloc.s  5
0x57743  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x57748  endfinally
0x57749  ldarg.0
0x5774a  ldloc.0
0x5774b  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions <>c__DisplayClass4_0::options
0x57750  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Reflection.PropertyInfo> Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::GetSupportedResponseFileOptions(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions options)
0x57755  stloc.2
0x57756  ldarg.0
0x57757  call     instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::GetSupportedOptionsForResponseFile()
0x5775c  stloc.3
0x5775d  ldloc.0
0x5775e  ldnull
0x5775f  stfld    class [System]System.Uri <>c__DisplayClass4_0::layoutUri
0x57764  ldloc.0
0x57765  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions <>c__DisplayClass4_0::options
0x5776a  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase
0x5776f  stloc.s  4
0x57771  ldloc.s  4
0x57773  brfalse.s loc_57791
0x57775  ldloc.s  4
0x57777  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_LayoutUri()
0x5777c  ldnull
0x5777d  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x57782  brfalse.s loc_57791
0x57784  ldloc.0
0x57785  ldloc.s  4
0x57787  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_LayoutUri()
0x5778c  stfld    class [System]System.Uri <>c__DisplayClass4_0::layoutUri
0x57791  ldloc.1
0x57792  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty> [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::Properties()
0x57797  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty>::GetEnumerator()
0x5779c  stloc.s  7
0x5779e  br       loc_579DD
0x577a3  ldloc.s  7
0x577a5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty>::get_Current()
0x577aa  stloc.s  8
0x577ac  ldloc.2
0x577ad  ldloc.s  8
0x577af  callvirt instance string [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty::get_Name()
0x577b4  ldloca.s 9
0x577b6  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Reflection.PropertyInfo>::TryGetValue(var<u1>, !!T0)
0x577bb  brfalse  loc_57943
0x577c0  ldloc.s  8
0x577c2  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty::get_Value()
0x577c7  ldloc.s  9
0x577c9  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x577ce  stloc.s  0xA
0x577d0  ldloc.s  0xA
0x577d2  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::ToObject(class [mscorlib]System.Type)
0x577d7  stloc.s  0xB
0x577d9  ldarg.0
0x577da  ldloc.s  9
0x577dc  call     instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::OptionSupportsMerging(class [mscorlib]System.Reflection.PropertyInfo propertyInfo)
0x577e1  brfalse.s loc_57805
0x577e3  ldloc.s  0xB
0x577e5  isinst   class [mscorlib]System.Collections.Generic.IEnumerable`1<string>
0x577ea  stloc.s  0xC
0x577ec  ldloc.s  0xC
0x577ee  brfalse.s loc_57805
0x577f0  ldarg.0
0x577f1  ldloc.0
0x577f2  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions <>c__DisplayClass4_0::options
0x577f7  ldloc.s  9
0x577f9  ldloc.s  0xC
0x577fb  call     instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::MergeArray(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions options, class [mscorlib]System.Reflection.PropertyInfo propertyInfo, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> newValues)
0x57800  br       loc_57907
0x57805  ldarg.0
0x57806  ldloc.0
0x57807  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions <>c__DisplayClass4_0::options
0x5780c  ldloc.s  9
0x5780e  call     instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::CanSetValue(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions options, class [mscorlib]System.Reflection.PropertyInfo propertyInfo)
0x57813  brfalse  loc_578C3
0x57818  ldloc.s  0xB
0x5781a  isinst   class [mscorlib]System.Collections.Generic.IEnumerable`1<string>
0x5781f  stloc.s  0xD
0x57821  ldloc.s  0xD
0x57823  brfalse  loc_578C3
0x57828  ldloc.s  0xD
0x5782a  ldsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__4_0
0x5782f  dup
0x57830  brtrue.s loc_57849
0x57832  pop
0x57833  ldsfld   class <>c <>c::<>9
0x57838  ldftn    instance bool <>c::<MergeResponseFile>b__4_0(string x)
0x5783e  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x57843  dup
0x57844  stsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__4_0
0x57849  call     T0x2B0000C3
0x5784e  stloc.s  0xD
0x57850  ldarg.0
0x57851  ldloc.s  9
0x57853  call     instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::OptionSupportsRelativePath(class [mscorlib]System.Reflection.PropertyInfo propertyInfo)
0x57858  brfalse.s loc_578B2
0x5785a  ldloc.s  0xD
0x5785c  ldloc.0
0x5785d  ldfld    class [mscorlib]System.Func`2<string, string> <>c__DisplayClass4_0::<>9__1
0x57862  dup
0x57863  brtrue.s loc_5787D
0x57865  pop
0x57866  ldloc.0
0x57867  ldloc.0
0x57868  ldftn    instance string <>c__DisplayClass4_0::<MergeResponseFile>b__1(string x)
0x5786e  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x57873  dup
0x57874  stloc.s  0xE
0x57876  stfld    class [mscorlib]System.Func`2<string, string> <>c__DisplayClass4_0::<>9__1
0x5787b  ldloc.s  0xE
0x5787d  call     T0x2B000376
0x57882  ldsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__4_2
0x57887  dup
0x57888  brtrue.s loc_578A1
0x5788a  pop
0x5788b  ldsfld   class <>c <>c::<>9
0x57890  ldftn    instance bool <>c::<MergeResponseFile>b__4_2(string x)
0x57896  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x5789b  dup
0x5789c  stsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__4_2
0x578a1  call     T0x2B0000C3
0x578a6  call     T0x2B000377
0x578ab  call     T0x2B000034
0x578b0  stloc.s  0xD
0x578b2  ldloc.s  9
0x578b4  ldloc.0
0x578b5  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions <>c__DisplayClass4_0::options
0x578ba  ldloc.s  0xD
0x578bc  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object)
0x578c1  br.s     loc_57907
0x578c3  ldarg.0
0x578c4  ldloc.0
0x578c5  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions <>c__DisplayClass4_0::options
0x578ca  ldloc.s  9
0x578cc  call     instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::CanSetValue(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions options, class [mscorlib]System.Reflection.PropertyInfo propertyInfo)
0x578d1  brfalse.s loc_57907
0x578d3  ldarg.0
0x578d4  ldloc.s  9
0x578d6  call     instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::OptionSupportsRelativePath(class [mscorlib]System.Reflection.PropertyInfo propertyInfo)
0x578db  brfalse.s loc_578F8
0x578dd  ldarg.0
0x578de  ldloc.s  0xB
0x578e0  ldloc.0
0x578e1  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions <>c__DisplayClass4_0::options
0x578e6  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions::get_ResponseFilePath()
0x578eb  ldloc.0
0x578ec  ldfld    class [System]System.Uri <>c__DisplayClass4_0::layoutUri
0x578f1  call     instance object Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::ResolveRelativePath(object deserializedValue, string filePath, class [System]System.Uri layoutUri)
0x578f6  stloc.s  0xB
0x578f8  ldloc.s  9
0x578fa  ldloc.0
0x578fb  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions <>c__DisplayClass4_0::options
0x57900  ldloc.s  0xB
0x57902  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object)
0x57907  leave    loc_579DD
0x5790c  stloc.s  0xF
0x5790e  ldarg.0
0x5790f  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineParserServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::serviceOptions
0x57914  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineParserServiceOptions::get_Logger()
0x57919  dup
0x5791a  brtrue.s loc_5791F
0x5791c  pop
0x5791d  br.s     loc_57941
0x5791f  ldloc.s  0xF
0x57921  ldstr    aExceptionWhile// "Exception while merging response file f"...
0x57926  ldloc.s  8
0x57928  callvirt instance string [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty::get_Name()
0x5792d  ldstr    asc_9EBEA// "."
0x57932  call     string [mscorlib]System.String::Concat(string, string, string)
0x57937  call     T0x2B000010
0x5793c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x57941  rethrow
0x57943  ldloc.s  8
0x57945  callvirt instance string [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty::get_Name()
0x5794a  ldstr    aComment// "comment"
0x5794f  ldc.i4.3
0x57950  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x57955  brtrue   loc_579DD
0x5795a  ldloc.3
0x5795b  ldloc.s  8
0x5795d  callvirt instance string [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty::get_Name()
0x57962  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x57967  brfalse.s loc_579C6
0x57969  ldarg.0
0x5796a  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineParserServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.ResponseFileMerger::serviceOptions
0x5796f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineParserServiceOptions::get_Logger()
0x57974  dup
0x57975  brtrue.s loc_5797A
0x57977  pop
0x57978  br.s     loc_579DD
0x5797a  ldc.i4.5
0x5797b  newarr   [mscorlib]System.String
0x57980  dup
0x57981  ldc.i4.0
0x57982  ldstr    aUnsupportedOpt// "Unsupported option in response file for"...
0x57987  stelem.ref
0x57988  dup
0x57989  ldc.i4.1
0x5798a  ldloc.0
0x5798b  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions <>c__DisplayClass4_0::options
0x57990  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x57995  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x5799a  stelem.ref
0x5799b  dup
0x5799c  ldc.i4.2
0x5799d  ldstr    asc_A79F8// ": "
0x579a2  stelem.ref
0x579a3  dup
0x579a4  ldc.i4.3
0x579a5  ldloc.s  8
0x579a7  callvirt instance string [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty::get_Name()
0x579ac  stelem.ref
0x579ad  dup
0x579ae  ldc.i4.4
0x579af  ldstr    aTheOptionWillB// ". The option will be ignored."
0x579b4  stelem.ref
0x579b5  call     string [mscorlib]System.String::Concat(string[])
0x579ba  call     T0x2B000010
0x579bf  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x579c4  br.s     loc_579DD
0x579c6  ldstr    aUnsupportedOpt_0// "Unsupported option in response file: "
0x579cb  ldloc.s  8
0x579cd  callvirt instance string [Newtonsoft.Json]Newtonsoft.Json.Linq.JProperty::get_Name()
0x579d2  call     string [mscorlib]System.String::Concat(string, string)
0x579d7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x579dc  throw
0x579dd  ldloc.s  7
0x579df  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x579e4  brtrue   loc_577A3
0x579e9  leave.s  loc_579F7
0x579eb  ldloc.s  7
0x579ed  brfalse.s loc_579F6
0x579ef  ldloc.s  7
0x579f1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x579f6  endfinally
0x579f7  ldloc.0
0x579f8  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions <>c__DisplayClass4_0::options
0x579fd  ldnull
0x579fe  callvirt instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions::set_ResponseFilePath(string value)
0x57a03  ret
```
