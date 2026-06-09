# SrClusterEventsWorkerThread(void *)

- ea: `0x180018440`
- end: `0x180018445`
- name: `?SrClusterEventsWorkerThread@@YAKPEAX@Z`
- size: `5`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180018a88`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall SrClusterEventsWorkerThread(CSrClusterEventListener *Parameter)
{
  return CSrClusterEventListener::StartTracing(Parameter);
}

```

## disassembly

```asm
0x180018440  jmp     ?StartTracing@CSrClusterEventListener@@QEAAKXZ; CSrClusterEventListener::StartTracing(void)
```
