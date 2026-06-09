# TimeZoneSyncTask.Data.RegistryTimeZoneData::FromBlob

- ea: `0xfdf0`
- end: `0xfe7c`
- name: `TimeZoneSyncTask.Data.RegistryTimeZoneData::FromBlob`
- size: `140`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0xde10`
- `0xe310`
- `0x11030`
- `0x112f0`

## callees

- `0xce40`
- `0xfe80`

## string_xrefs

- `0xfe04`: `Registry`
- `0xfe64`: `Registry`
- `0xfe69`: `expecting valid RegistryTimeZoneData`

## pseudocode

```c

```

## disassembly

```asm
0xfdf0  ldarg.0
0xfdf1  ldlen
0xfdf2  conv.i4
0xfdf3  ldtoken  TimeZoneSyncTask.Data.RegistryTimeZoneData
0xfdf8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfdfd  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(class [mscorlib]System.Type)
0xfe02  ceq
0xfe04  ldstr    aRegistry// "Registry"
0xfe09  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfe0e  ldstr    aExpectingSize0// "expecting size {0} bytes, got size {1} "...
0xfe13  ldtoken  TimeZoneSyncTask.Data.RegistryTimeZoneData
0xfe18  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfe1d  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(class [mscorlib]System.Type)
0xfe22  box      [mscorlib]System.Int32
0xfe27  ldarg.0
0xfe28  ldlen
0xfe29  conv.i4
0xfe2a  box      [mscorlib]System.Int32
0xfe2f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0xfe34  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string exceptiontype, string msg)
0xfe39  ldarg.0
0xfe3a  ldc.i4.3
0xfe3b  call     valuetype [mscorlib]System.Runtime.InteropServices.GCHandle [mscorlib]System.Runtime.InteropServices.GCHandle::Alloc(object, valuetype [mscorlib]System.Runtime.InteropServices.GCHandleType)
0xfe40  stloc.0
0xfe41  ldloca.s 0
0xfe43  call     instance native int [mscorlib]System.Runtime.InteropServices.GCHandle::AddrOfPinnedObject()
0xfe48  ldtoken  TimeZoneSyncTask.Data.RegistryTimeZoneData
0xfe4d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfe52  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0xfe57  unbox.any TimeZoneSyncTask.Data.RegistryTimeZoneData
0xfe5c  stloc.1
0xfe5d  ldloca.s 1
0xfe5f  call     instance bool TimeZoneSyncTask.Data.RegistryTimeZoneData::IsValid()
0xfe64  ldstr    aRegistry// "Registry"
0xfe69  ldstr    aExpectingValid_4// "expecting valid RegistryTimeZoneData"
0xfe6e  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string exceptiontype, string msg)
0xfe73  ldloca.s 0
0xfe75  call     instance void [mscorlib]System.Runtime.InteropServices.GCHandle::Free()
0xfe7a  ldloc.1
0xfe7b  ret
```
