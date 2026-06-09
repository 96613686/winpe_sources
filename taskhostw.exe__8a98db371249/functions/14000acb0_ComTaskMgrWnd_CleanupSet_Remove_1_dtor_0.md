# _ComTaskMgrWnd::CleanupSet::Remove_::_1_::dtor$0

- ea: `0x14000acb0`
- end: `0x14000acbc`
- name: `_ComTaskMgrWnd::CleanupSet::Remove_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140007244`

## pseudocode

```c
void __fastcall ComTaskMgrWnd::CleanupSet::Remove_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  SrwLockExclusiveScope::~SrwLockExclusiveScope((SrwLockExclusiveScope *)(a2 + 80));
}

```

## disassembly

```asm
0x14000acb0  lea     rcx, [rdx+50h]; this
0x14000acb7  jmp     ??1SrwLockExclusiveScope@@QEAA@XZ; SrwLockExclusiveScope::~SrwLockExclusiveScope(void)
```
