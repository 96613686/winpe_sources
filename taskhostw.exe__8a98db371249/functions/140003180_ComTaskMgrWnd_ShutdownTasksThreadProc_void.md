# ComTaskMgrWnd::ShutdownTasksThreadProc(void *)

- ea: `0x140003180`
- end: `0x140003197`
- name: `?ShutdownTasksThreadProc@ComTaskMgrWnd@@CAKPEAX@Z`
- size: `23`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003b10`

## pseudocode

```c
__int64 __fastcall ComTaskMgrWnd::ShutdownTasksThreadProc(PVOID Parameter)
{
  ComTaskMgrWnd::ShutdownTasksWorker(ComTaskMgrBase::s_pVirtualSingleton);
  return 0;
}

```

## disassembly

```asm
0x140003180  sub     rsp, 28h
0x140003184  mov     rcx, cs:?s_pVirtualSingleton@ComTaskMgrBase@@0PEAV1@EA; this
0x14000318b  call    ?ShutdownTasksWorker@ComTaskMgrWnd@@AEAAJXZ; ComTaskMgrWnd::ShutdownTasksWorker(void)
0x140003190  xor     eax, eax
0x140003192  add     rsp, 28h
0x140003196  retn
```
