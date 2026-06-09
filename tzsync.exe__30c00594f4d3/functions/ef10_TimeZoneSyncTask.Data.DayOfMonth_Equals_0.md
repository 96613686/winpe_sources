# TimeZoneSyncTask.Data.DayOfMonth::Equals_0

- ea: `0xef10`
- end: `0xef40`
- name: `TimeZoneSyncTask.Data.DayOfMonth::Equals_0`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0xeef0`

## callees

- `0xee20`
- `0xee40`
- `0xee60`
- `0xef10`

## pseudocode

```c

```

## disassembly

```asm
0xef10  ldarg.0
0xef11  call     instance valuetype TimeZoneSyncTask.Data.DayType TimeZoneSyncTask.Data.DayOfMonth::get_Type()
0xef16  ldarga.s 1
0xef18  call     instance valuetype TimeZoneSyncTask.Data.DayType TimeZoneSyncTask.Data.DayOfMonth::get_Type()
0xef1d  bne.un.s loc_EF3E
0xef1f  ldarg.0
0xef20  call     instance int32 TimeZoneSyncTask.Data.DayOfMonth::get_Day()
0xef25  ldarga.s 1
0xef27  call     instance int32 TimeZoneSyncTask.Data.DayOfMonth::get_Day()
0xef2c  bne.un.s loc_EF3E
0xef2e  ldarg.0
0xef2f  call     instance int32 TimeZoneSyncTask.Data.DayOfMonth::get_DayOfWeek()
0xef34  ldarga.s 1
0xef36  call     instance int32 TimeZoneSyncTask.Data.DayOfMonth::get_DayOfWeek()
0xef3b  ceq
0xef3d  ret
0xef3e  ldc.i4.0
0xef3f  ret
```
