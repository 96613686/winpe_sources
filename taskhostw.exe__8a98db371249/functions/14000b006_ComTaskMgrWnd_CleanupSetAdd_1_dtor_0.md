# _ComTaskMgrWnd::CleanupSetAdd_::_1_::dtor$0

- ea: `0x14000b006`
- end: `0x14000b012`
- name: `_ComTaskMgrWnd::CleanupSetAdd_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140007244`

## pseudocode

```c
void __fastcall ComTaskMgrWnd::CleanupSetAdd_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  SrwLockExclusiveScope::~SrwLockExclusiveScope((SrwLockExclusiveScope *)(a2 + 88));
}

```

## disassembly

```asm
0x14000b006  lea     rcx, [rdx+58h]; this
0x14000b00d  jmp     ??1SrwLockExclusiveScope@@QEAA@XZ; SrwLockExclusiveScope::~SrwLockExclusiveScope(void)
```
