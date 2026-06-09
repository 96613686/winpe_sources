# MicrosoftTelemetryAssertTriggeredNoArgsKM

- ea: `0x14000caa0`
- end: `0x14000cacb`
- name: `MicrosoftTelemetryAssertTriggeredNoArgsKM`
- size: `43`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `161`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001120`
- `0x140001190`
- `0x1400011e0`
- `0x140001c30`
- `0x1400020e0`
- `0x140003830`
- `0x140004094`
- `0x1400042a0`
- `0x140004648`
- `0x140004ed0`
- `0x140005714`
- `0x1400057b0`
- `0x140005a18`
- `0x140005cf0`
- `0x140006030`
- `0x140006340`
- `0x140006558`
- `0x140006764`
- `0x140006c80`
- `0x140006f04`
- `0x140007610`
- `0x140007bb0`
- `0x1400085d0`
- `0x140008928`
- `0x140008a7c`
- `0x140008df0`
- `0x140009620`
- `0x140009b04`
- `0x14000a7dc`
- `0x14000a9d0`
- `0x14000b220`
- `0x14000b770`
- `0x14000b8d0`
- `0x14000bdf0`
- `0x14000c03c`
- `0x14000c618`
- `0x14000c8e4`
- `0x14000c948`
- `0x14000db20`
- `0x14000dcfc`
- `0x14000dda0`
- `0x14000e980`
- `0x14000ee40`
- `0x14000f130`
- `0x14000f428`
- `0x14000fae0`
- `0x14000fc88`
- `0x140010000`
- `0x1400101b0`
- `0x140010230`

## callees

- `0x14000cad4`

## pseudocode

```c
__int64 MicrosoftTelemetryAssertTriggeredNoArgsKM()
{
  _UNKNOWN *retaddr; // [rsp+38h] [rbp+0h]

  return MicrosoftTelemetryAssertTriggeredWorker((_DWORD)retaddr, 0, 0, -1, -1, 0);
}

```

## disassembly

```asm
0x14000caa0  sub     rsp, 38h
0x14000caa4  mov     rcx, [rsp+38h]
0x14000caa9  or      r9d, 0FFFFFFFFh
0x14000caad  mov     [rsp+38h+var_10], 0
0x14000cab6  xor     r8d, r8d
0x14000cab9  xor     edx, edx
0x14000cabb  mov     [rsp+38h+var_18], r9d
0x14000cac0  call    MicrosoftTelemetryAssertTriggeredWorker
0x14000cac5  add     rsp, 38h
0x14000cac9  retn
```
