# TimeZoneSyncTask.EventProviderVersionTwo::TemplateEventDescriptor

- ea: `0xdb00`
- end: `0xdb24`
- name: `TimeZoneSyncTask.EventProviderVersionTwo::TemplateEventDescriptor`
- size: `36`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `service_task`

## callers

- `0xd8d0`
- `0xd900`
- `0xd930`
- `0xd960`
- `0xd990`
- `0xd9c0`
- `0xda30`
- `0xda80`
- `0xdab0`

## callees

- `0xdb00`

## pseudocode

```c

```

## disassembly

```asm
0xdb00  ldarg.0
0xdb01  ldarg.1
0xdb02  call     instance unsigned int8 [System.Core]System.Diagnostics.Eventing.EventDescriptor::get_Level()
0xdb07  ldarg.1
0xdb08  call     instance int64 [System.Core]System.Diagnostics.Eventing.EventDescriptor::get_Keywords()
0xdb0d  call     instance bool [System.Core]System.Diagnostics.Eventing.EventProvider::IsEnabled(unsigned int8, int64)
0xdb12  brfalse.s loc_DB22
0xdb14  ldarg.0
0xdb15  ldarg.1
0xdb16  ldc.i4.0
0xdb17  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xdb1c  call     instance bool [System.Core]System.Diagnostics.Eventing.EventProvider::WriteEvent(valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor&, int32, native int)
0xdb21  ret
0xdb22  ldc.i4.1
0xdb23  ret
```
