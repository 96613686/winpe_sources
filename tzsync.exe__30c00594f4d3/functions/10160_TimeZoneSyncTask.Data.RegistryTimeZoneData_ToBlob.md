# TimeZoneSyncTask.Data.RegistryTimeZoneData::ToBlob

- ea: `0x10160`
- end: `0x10193`
- name: `TimeZoneSyncTask.Data.RegistryTimeZoneData::ToBlob`
- size: `51`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config, service_task`

## callers

- `0xde10`
- `0x11030`
- `0x112f0`
- `0x11550`

## pseudocode

```c

```

## disassembly

```asm
0x10160  ldarg.0
0x10161  ldobj    TimeZoneSyncTask.Data.RegistryTimeZoneData
0x10166  call     T0x2B000021
0x1016b  newarr   [mscorlib]System.Byte
0x10170  dup
0x10171  ldc.i4.3
0x10172  call     valuetype [mscorlib]System.Runtime.InteropServices.GCHandle [mscorlib]System.Runtime.InteropServices.GCHandle::Alloc(object, valuetype [mscorlib]System.Runtime.InteropServices.GCHandleType)
0x10177  stloc.0
0x10178  ldarg.0
0x10179  ldobj    TimeZoneSyncTask.Data.RegistryTimeZoneData
0x1017e  ldloca.s 0
0x10180  call     instance native int [mscorlib]System.Runtime.InteropServices.GCHandle::AddrOfPinnedObject()
0x10185  ldc.i4.0
0x10186  call     T0x2B000022
0x1018b  ldloca.s 0
0x1018d  call     instance void [mscorlib]System.Runtime.InteropServices.GCHandle::Free()
0x10192  ret
```
