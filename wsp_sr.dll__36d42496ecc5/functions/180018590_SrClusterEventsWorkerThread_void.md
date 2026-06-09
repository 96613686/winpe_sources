# SrClusterEventsWorkerThread(void *)

- ea: `0x180018590`
- end: `0x180018595`
- name: `?SrClusterEventsWorkerThread@@YAKPEAX@Z`
- size: `5`
- prototype: `ULONG __fastcall(CSrClusterEventListener *Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180018b74`

## pseudocode

```c
// attributes: thunk
ULONG __fastcall SrClusterEventsWorkerThread(CSrClusterEventListener *Parameter)
{
  return CSrClusterEventListener::StartTracing(Parameter);
}

```

## disassembly

```asm
0x180018590  jmp     ?StartTracing@CSrClusterEventListener@@QEAAKXZ; CSrClusterEventListener::StartTracing(void)
```
