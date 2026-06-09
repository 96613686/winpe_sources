# TimeZoneSyncTask.OneSettings.DynamicDSTRules::RemoveDSTRulesInRange

- ea: `0xe050`
- end: `0xe0b0`
- name: `TimeZoneSyncTask.OneSettings.DynamicDSTRules::RemoveDSTRulesInRange`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xde10`

## callees

- `0xe050`

## string_xrefs

- `0xe067`: `Deleted registry data for {0}`
- `0xe083`: `Error deleting registry data for {0}: {1}`

## pseudocode

```c

```

## disassembly

```asm
0xe050  ldarg.2
0xe051  stloc.0
0xe052  br.s     loc_E0AB
0xe054  nop
0xe055  ldarg.1
0xe056  ldloca.s 0
0xe058  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe05d  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xe062  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteValue(string)
0xe067  ldstr    aDeletedRegistr_0// "Deleted registry data for {0}"
0xe06c  ldc.i4.1
0xe06d  newarr   [mscorlib]System.Object
0xe072  dup
0xe073  ldc.i4.0
0xe074  ldloc.0
0xe075  box      [mscorlib]System.Int32
0xe07a  stelem.ref
0xe07b  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0xe080  leave.s  loc_E0A7
0xe082  stloc.1
0xe083  ldstr    aErrorDeletingR// "Error deleting registry data for {0}: {"...
0xe088  ldc.i4.2
0xe089  newarr   [mscorlib]System.Object
0xe08e  dup
0xe08f  ldc.i4.0
0xe090  ldloc.0
0xe091  box      [mscorlib]System.Int32
0xe096  stelem.ref
0xe097  dup
0xe098  ldc.i4.1
0xe099  ldloc.1
0xe09a  callvirt instance string [mscorlib]System.Exception::get_Message()
0xe09f  stelem.ref
0xe0a0  call     void [System]System.Diagnostics.Trace::TraceError(string, object[])
0xe0a5  leave.s  loc_E0A7
0xe0a7  ldloc.0
0xe0a8  ldc.i4.1
0xe0a9  add
0xe0aa  stloc.0
0xe0ab  ldloc.0
0xe0ac  ldarg.3
0xe0ad  ble.s    loc_E054
0xe0af  ret
```
