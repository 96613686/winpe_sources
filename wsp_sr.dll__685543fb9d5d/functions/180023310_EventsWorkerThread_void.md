# EventsWorkerThread(void *)

- ea: `0x180023310`
- end: `0x180023315`
- name: `?EventsWorkerThread@@YAKPEAX@Z`
- size: `5`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180023f08`

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
0x180023310  jmp     ?StartTracingInternal@CSrEtwEventManager@@QEAAKXZ; CSrEtwEventManager::StartTracingInternal(void)
```
