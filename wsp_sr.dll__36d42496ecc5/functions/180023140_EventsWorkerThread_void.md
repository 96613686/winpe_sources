# EventsWorkerThread(void *)

- ea: `0x180023140`
- end: `0x180023145`
- name: `?EventsWorkerThread@@YAKPEAX@Z`
- size: `5`
- prototype: `ULONG __fastcall(CSrEtwEventManager *Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180023c7c`

## pseudocode

```c
// attributes: thunk
ULONG __fastcall EventsWorkerThread(CSrEtwEventManager *Parameter)
{
  return CSrEtwEventManager::StartTracingInternal(Parameter);
}

```

## disassembly

```asm
0x180023140  jmp     ?StartTracingInternal@CSrEtwEventManager@@QEAAKXZ; CSrEtwEventManager::StartTracingInternal(void)
```
