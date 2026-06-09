# PnpServiceStopCallback

- ea: `0x1800142b0`
- end: `0x1800142bb`
- name: `PnpServiceStopCallback`
- size: `11`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000ea20`

## pseudocode

```c
__int64 PnpServiceStopCallback()
{
  return PnpServiceStop(PnpServiceStopError);
}

```

## disassembly

```asm
0x1800142b0  mov     ecx, cs:PnpServiceStopError
0x1800142b6  jmp     PnpServiceStop
```
