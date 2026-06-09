# ComTaskMgrWnd::CleanupSetRemove(ComTaskHost *)

- ea: `0x140009670`
- end: `0x140009679`
- name: `?CleanupSetRemove@ComTaskMgrWnd@@UEAAXPEAVComTaskHost@@@Z`
- size: `9`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct ComTaskHost *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1400043a0`

## pseudocode

```c
void __fastcall ComTaskMgrWnd::CleanupSetRemove(RTL_SRWLOCK *this, struct ComTaskHost *a2)
{
  ComTaskMgrWnd::CleanupSet::Remove(this + 9, a2);
}

```

## disassembly

```asm
0x140009670  add     rcx, 48h ; 'H'; SRWLock
0x140009674  jmp     ?Remove@CleanupSet@ComTaskMgrWnd@@QEAAXPEAVComTaskHost@@@Z; ComTaskMgrWnd::CleanupSet::Remove(ComTaskHost *)
```
