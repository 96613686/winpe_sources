# MicrosoftTelemetryAssertTriggeredNoArgsKM

- ea: `0x140008138`
- end: `0x140008163`
- name: `MicrosoftTelemetryAssertTriggeredNoArgsKM`
- size: `43`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000e1d0`
- `0x14000e778`
- `0x14000eb68`
- `0x14001f6c0`
- `0x140022078`

## callees

- `0x14000816c`

## pseudocode

```c
__int64 MicrosoftTelemetryAssertTriggeredNoArgsKM()
{
  void *retaddr; // [rsp+38h] [rbp+0h]

  return MicrosoftTelemetryAssertTriggeredWorker(retaddr, 0, 0);
}

```

## disassembly

```asm
0x140008138  sub     rsp, 38h
0x14000813c  mov     rcx, [rsp+38h]
0x140008141  or      r9d, 0FFFFFFFFh
0x140008145  mov     [rsp+38h+var_10], 0
0x14000814e  xor     r8d, r8d
0x140008151  xor     edx, edx
0x140008153  mov     [rsp+38h+var_18], r9d
0x140008158  call    MicrosoftTelemetryAssertTriggeredWorker
0x14000815d  add     rsp, 38h
0x140008161  retn
```
