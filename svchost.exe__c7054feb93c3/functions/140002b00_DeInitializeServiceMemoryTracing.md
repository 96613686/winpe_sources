# DeInitializeServiceMemoryTracing

- ea: `0x140002b00`
- end: `0x140002b55`
- name: `DeInitializeServiceMemoryTracing`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x140002a40`

## callees

- `0x140002b00`

## import_xrefs

- `ntdll!TpSetTimerEx` at `0x140002b1d`
- `ntdll!TpSetTimerEx` at `0x140002b1d`
- `ntdll!TpWaitForTimer` at `0x140002b4d`
- `ntdll!TpWaitForTimer` at `0x140002b4d`
- `ntdll!TpReleaseTimer` at `0x140002b2e`
- `ntdll!TpReleaseTimer` at `0x140002b2e`

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
0x140002b00  sub     rsp, 28h
0x140002b04  mov     rcx, cs:g_TelemetryTimer
0x140002b0b  test    rcx, rcx
0x140002b0e  jnz     short loc_140002B15
0x140002b10  add     rsp, 28h
0x140002b14  retn
0x140002b15  xor     r9d, r9d
0x140002b18  xor     r8d, r8d
0x140002b1b  xor     edx, edx
0x140002b1d  call    cs:__imp_TpSetTimerEx
0x140002b23  test    eax, eax
0x140002b25  jz      short loc_140002B41
0x140002b27  mov     rcx, cs:g_TelemetryTimer
0x140002b2e  call    cs:__imp_TpReleaseTimer
0x140002b34  mov     cs:g_TelemetryTimer, 0
0x140002b3f  jmp     short loc_140002B10
0x140002b41  mov     rcx, cs:g_TelemetryTimer
0x140002b48  mov     edx, 1
0x140002b4d  call    cs:__imp_TpWaitForTimer
0x140002b53  jmp     short loc_140002B27
```
