# ComTaskHost::StopTaskThread(void *)

- ea: `0x140007330`
- end: `0x140007335`
- name: `?StopTaskThread@ComTaskHost@@CAKPEAX@Z`
- size: `5`
- prototype: `__int64 __fastcall(ComTaskHost *Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004ec0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ComTaskHost::StopTaskThread(ComTaskHost *Parameter)
{
  return ComTaskHost::StopTaskWorker(Parameter);
}

```

## disassembly

```asm
0x140007330  jmp     ?StopTaskWorker@ComTaskHost@@AEAAJXZ; ComTaskHost::StopTaskWorker(void)
```
