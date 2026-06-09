# ArmTheServiceMemoryTracingTimer

- ea: `0x140002150`
- end: `0x1400021af`
- name: `ArmTheServiceMemoryTracingTimer`
- size: `95`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, service_task`

## callers

- `0x140006520`
- `0x1400086f8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000215d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000215d`
- `ntdll!TpSetTimer` at `0x14000219d`
- `ntdll!TpSetTimer` at `0x14000219d`

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
0x140002150  sub     rsp, 28h
0x140002154  mov     [rsp+28h+arg_0], 0
0x14000215d  call    cs:__imp_GetTickCount64
0x140002164  nop     dword ptr [rax+rax+00h]
0x140002169  mov     rcx, cs:g_TelemetryTimer
0x140002170  lea     rdx, [rsp+28h+arg_0]
0x140002175  sub     rax, 1499700h
0x14000217b  mov     r9d, 7530h
0x140002181  mov     cs:g_LastTelemetryUploadTime, rax
0x140002188  mov     r8d, 927C0h
0x14000218e  mov     rax, 0FFFFFFFE9A5F4400h
0x140002198  mov     [rsp+28h+arg_0], rax
0x14000219d  call    cs:__imp_TpSetTimer
0x1400021a4  nop     dword ptr [rax+rax+00h]
0x1400021a9  add     rsp, 28h
0x1400021ad  retn
```
