# DeInitializeServiceMemoryTracing

- ea: `0x140002d90`
- end: `0x140002de2`
- name: `DeInitializeServiceMemoryTracing`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x140002cb0`

## callees

- `0x140002d90`

## import_xrefs

- `ntdll!TpSetTimerEx` at `0x140002dae`
- `ntdll!TpSetTimerEx` at `0x140002dae`
- `ntdll!TpWaitForTimer` at `0x140008e58`
- `ntdll!TpWaitForTimer` at `0x140008e58`
- `ntdll!TpReleaseTimer` at `0x140002dc9`
- `ntdll!TpReleaseTimer` at `0x140002dc9`

## pseudocode

```c
void DeInitializeServiceMemoryTracing()
{
  if ( g_TelemetryTimer )
  {
    if ( !(unsigned int)TpSetTimerEx(g_TelemetryTimer, 0, 0, 0) )
      TpWaitForTimer(g_TelemetryTimer, 1);
    TpReleaseTimer(g_TelemetryTimer);
    g_TelemetryTimer = 0;
  }
}

```

## disassembly

```asm
0x140002d90  sub     rsp, 28h
0x140002d94  mov     rcx, cs:g_TelemetryTimer
0x140002d9b  test    rcx, rcx
0x140002d9e  jnz     short loc_140002DA6
0x140002da0  add     rsp, 28h
0x140002da4  retn
0x140002da6  xor     r9d, r9d
0x140002da9  xor     r8d, r8d
0x140002dac  xor     edx, edx
0x140002dae  call    cs:__imp_TpSetTimerEx
0x140002db5  nop     dword ptr [rax+rax+00h]
0x140002dba  test    eax, eax
0x140002dbc  jz      loc_140008E4C
0x140002dc2  mov     rcx, cs:g_TelemetryTimer
0x140002dc9  call    cs:__imp_TpReleaseTimer
0x140002dd0  nop     dword ptr [rax+rax+00h]
0x140002dd5  mov     cs:g_TelemetryTimer, 0
0x140002de0  jmp     short loc_140002DA0
0x140008e4c  mov     rcx, cs:g_TelemetryTimer
0x140008e53  mov     edx, 1
0x140008e58  call    cs:__imp_TpWaitForTimer
0x140008e5f  nop     dword ptr [rax+rax+00h]
0x140008e64  nop
0x140008e65  jmp     loc_140002DC2
```
