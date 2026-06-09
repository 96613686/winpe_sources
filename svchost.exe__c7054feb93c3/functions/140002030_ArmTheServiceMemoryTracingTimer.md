# ArmTheServiceMemoryTracingTimer

- ea: `0x140002030`
- end: `0x140002082`
- name: `ArmTheServiceMemoryTracingTimer`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, service_task`

## callers

- `0x140008124`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000203d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000203d`
- `ntdll!TpSetTimer` at `0x140002077`
- `ntdll!TpSetTimer` at `0x140002077`

## pseudocode

```c
__int64 ArmTheServiceMemoryTracingTimer()
{
  __int64 v1; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  g_LastTelemetryUploadTime = GetTickCount64() - 21600000;
  v1 = -6000000000LL;
  return TpSetTimer(g_TelemetryTimer, &v1, 600000, 30000);
}

```

## disassembly

```asm
0x140002030  sub     rsp, 28h
0x140002034  mov     [rsp+28h+arg_0], 0
0x14000203d  call    cs:__imp_GetTickCount64
0x140002043  mov     rcx, cs:g_TelemetryTimer
0x14000204a  lea     rdx, [rsp+28h+arg_0]
0x14000204f  sub     rax, 1499700h
0x140002055  mov     r9d, 7530h
0x14000205b  mov     cs:g_LastTelemetryUploadTime, rax
0x140002062  mov     r8d, 927C0h
0x140002068  mov     rax, 0FFFFFFFE9A5F4400h
0x140002072  mov     [rsp+28h+arg_0], rax
0x140002077  call    cs:__imp_TpSetTimer
0x14000207d  add     rsp, 28h
0x140002081  retn
```
