# Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::GetUpdateOptionsLog

- ea: `0x3c8a0`
- end: `0x3cb0a`
- name: `Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::GetUpdateOptionsLog`
- size: `618`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3c780`
- `0x3c8a0`

## string_xrefs

- `0x3c8b8`: `\nLayoutPath: {0}`
- `0x3c8e5`: `\nUpdateFromVS: {0}`
- `0x3caa7`: `\nTelemetryContext: InstallSessionId={0}, SerializedCorrelations={1}, UserRequestedOperation={2}`
- `0x3caec`: `\nUpdateVersion: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3c8a0  ldarg.0
0x3c8a1  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3c8a6  ldarg.0
0x3c8a7  call     instance string Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::GetStandardOptionsLogContent()
0x3c8ac  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3c8b1  pop
0x3c8b2  ldarg.0
0x3c8b3  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3c8b8  ldstr    aLayoutpath0// "\nLayoutPath: {0}"
0x3c8bd  ldarg.1
0x3c8be  dup
0x3c8bf  brtrue.s loc_3C8C7
0x3c8c1  pop
0x3c8c2  ldsfld   string [mscorlib]System.String::Empty
0x3c8c7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x3c8cc  pop
0x3c8cd  ldarg.0
0x3c8ce  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3c8d3  ldstr    aProductkey0// "\nProductKey: {0}"
0x3c8d8  ldarg.2
0x3c8d9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x3c8de  pop
0x3c8df  ldarg.0
0x3c8e0  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3c8e5  ldstr    aUpdatefromvs0// "\nUpdateFromVS: {0}"
0x3c8ea  ldarg.3
0x3c8eb  box      [mscorlib]System.Boolean
0x3c8f0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x3c8f5  pop
0x3c8f6  ldarg.s  4
0x3c8f8  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState>>::get_Count()
0x3c8fd  ldc.i4.0
0x3c8fe  ble      loc_3C993
0x3c903  ldarg.0
0x3c904  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3c909  ldstr    aSelectedpackag// "\nSelectedPackages:"
0x3c90e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x3c913  pop
0x3c914  ldarg.s  4
0x3c916  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState>>::GetEnumerator()
0x3c91b  stloc.0
0x3c91c  br.s     loc_3C97F
0x3c91e  ldloc.0
0x3c91f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState>>::get_Current()
0x3c924  stloc.1
0x3c925  ldarg.0
0x3c926  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3c92b  ldstr    a0Selectedstate// "[{0}: SelectedState={1}, UserSelectedSt"...
0x3c930  ldloca.s 1
0x3c932  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState>::get_Key()
0x3c937  ldloca.s 1
0x3c939  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState>::get_Value()
0x3c93e  dup
0x3c93f  brtrue.s loc_3C945
0x3c941  pop
0x3c942  ldnull
0x3c943  br.s     loc_3C958
0x3c945  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState::get_SelectedState()
0x3c94a  stloc.2
0x3c94b  ldloca.s 2
0x3c94d  constrained. [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState
0x3c953  callvirt instance string [mscorlib]System.Object::ToString()
0x3c958  ldloca.s 1
0x3c95a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState>::get_Value()
0x3c95f  dup
0x3c960  brtrue.s loc_3C966
0x3c962  pop
0x3c963  ldnull
0x3c964  br.s     loc_3C979
0x3c966  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UserSelectedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState::get_UserSelectedState()
0x3c96b  stloc.3
0x3c96c  ldloca.s 3
0x3c96e  constrained. [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UserSelectedState
0x3c974  callvirt instance string [mscorlib]System.Object::ToString()
0x3c979  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object, object)
0x3c97e  pop
0x3c97f  ldloc.0
0x3c980  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3c985  brtrue.s loc_3C91E
0x3c987  leave.s  loc_3C9A4
0x3c989  ldloc.0
0x3c98a  brfalse.s loc_3C992
0x3c98c  ldloc.0
0x3c98d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3c992  endfinally
0x3c993  ldarg.0
0x3c994  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3c999  ldstr    aSelectedpackag_0// "\nSelectedPackages: None"
0x3c99e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3c9a3  pop
0x3c9a4  ldarg.s  5
0x3c9a6  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState>>::get_Count()
0x3c9ab  ldc.i4.0
0x3c9ac  ble      loc_3CA42
0x3c9b1  ldarg.0
0x3c9b2  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3c9b7  ldstr    aSelectedadvert// "\nSelectedAdvertisedPackages:"
0x3c9bc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3c9c1  pop
0x3c9c2  ldarg.s  5
0x3c9c4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState>>::GetEnumerator()
0x3c9c9  stloc.0
0x3c9ca  br.s     loc_3CA2E
0x3c9cc  ldloc.0
0x3c9cd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState>>::get_Current()
0x3c9d2  stloc.s  4
0x3c9d4  ldarg.0
0x3c9d5  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3c9da  ldstr    a0Selectedstate// "[{0}: SelectedState={1}, UserSelectedSt"...
0x3c9df  ldloca.s 4
0x3c9e1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState>::get_Key()
0x3c9e6  ldloca.s 4
0x3c9e8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState>::get_Value()
0x3c9ed  dup
0x3c9ee  brtrue.s loc_3C9F4
0x3c9f0  pop
0x3c9f1  ldnull
0x3c9f2  br.s     loc_3CA07
0x3c9f4  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState::get_SelectedState()
0x3c9f9  stloc.2
0x3c9fa  ldloca.s 2
0x3c9fc  constrained. [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.SelectedState
0x3ca02  callvirt instance string [mscorlib]System.Object::ToString()
0x3ca07  ldloca.s 4
0x3ca09  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState>::get_Value()
0x3ca0e  dup
0x3ca0f  brtrue.s loc_3CA15
0x3ca11  pop
0x3ca12  ldnull
0x3ca13  br.s     loc_3CA28
0x3ca15  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UserSelectedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ISelectionState::get_UserSelectedState()
0x3ca1a  stloc.3
0x3ca1b  ldloca.s 3
0x3ca1d  constrained. [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.UserSelectedState
0x3ca23  callvirt instance string [mscorlib]System.Object::ToString()
0x3ca28  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object, object)
0x3ca2d  pop
0x3ca2e  ldloc.0
0x3ca2f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3ca34  brtrue.s loc_3C9CC
0x3ca36  leave.s  loc_3CA58
0x3ca38  ldloc.0
0x3ca39  brfalse.s loc_3CA41
0x3ca3b  ldloc.0
0x3ca3c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3ca41  endfinally
0x3ca42  ldarg.0
0x3ca43  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3ca48  ldstr    aSelectedadvert_0// "\nSelectedAdvertisedPackages: None"
0x3ca4d  call     T0x2B000010
0x3ca52  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object[])
0x3ca57  pop
0x3ca58  ldarg.0
0x3ca59  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::installerFlight
0x3ca5e  call     T0x2B000074
0x3ca63  brfalse.s loc_3CA90
0x3ca65  ldarg.0
0x3ca66  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3ca6b  ldstr    aVisualstudiofl// "\nVisualStudioFlight: "
0x3ca70  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3ca75  pop
0x3ca76  ldarg.0
0x3ca77  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::installerFlight
0x3ca7c  ldarg.0
0x3ca7d  ldftn    instance class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::<GetUpdateOptionsLog>b__9_0(string x)
0x3ca83  newobj   instance void class [mscorlib]System.Func`2<string, class [mscorlib]System.Text.StringBuilder>::.ctor(object, native int)
0x3ca88  call     T0x2B00026A
0x3ca8d  pop
0x3ca8e  br.s     loc_3CAA1
0x3ca90  ldarg.0
0x3ca91  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3ca96  ldstr    aVisualstudiofl_0// "\nVisualStudioFlight: None"
0x3ca9b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3caa0  pop
0x3caa1  ldarg.0
0x3caa2  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3caa7  ldstr    aTelemetryconte// "\nTelemetryContext: InstallSessionId={0"...
0x3caac  ldarg.s  6
0x3caae  ldfld    string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.TelemetryContext::InstallSessionId
0x3cab3  ldarg.s  6
0x3cab5  ldfld    string[] [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.TelemetryContext::SerializedCorrelations
0x3caba  call     T0x2B00002F
0x3cabf  brtrue.s loc_3CAD4
0x3cac1  ldstr    asc_9D4A4// " "
0x3cac6  ldarg.s  6
0x3cac8  ldfld    string[] [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.TelemetryContext::SerializedCorrelations
0x3cacd  call     string [mscorlib]System.String::Join(string, string[])
0x3cad2  br.s     loc_3CAD9
0x3cad4  ldsfld   string [mscorlib]System.String::Empty
0x3cad9  ldarg.s  6
0x3cadb  ldfld    string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.TelemetryContext::UserRequestedOperation
0x3cae0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object, object)
0x3cae5  pop
0x3cae6  ldarg.0
0x3cae7  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3caec  ldstr    aUpdateversion0// "\nUpdateVersion: {0}"
0x3caf1  ldarg.s  7
0x3caf3  callvirt instance string [mscorlib]System.Object::ToString()
0x3caf8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x3cafd  pop
0x3cafe  ldarg.0
0x3caff  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.VisualStudio.Setup.Installer.Utilities.OptionsLog::builder
0x3cb04  callvirt instance string [mscorlib]System.Object::ToString()
0x3cb09  ret
```
