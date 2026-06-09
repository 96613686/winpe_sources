# CCSPNodeImpl::PersistRollbackDeletePropertyState(_GUID const &,ISequentialStream *,ISequentialStream *)

- ea: `0x1800199e0`
- end: `0x1800199e6`
- name: `?PersistRollbackDeletePropertyState@CCSPNodeImpl@@UEAAJAEBU_GUID@@PEAUISequentialStream@@1@Z`
- size: `6`
- prototype: `__int64 __fastcall(CCSPNodeImpl *__hidden this, const struct _GUID *, struct ISequentialStream *, struct ISequentialStream *)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
__int64 __fastcall CCSPNodeImpl::PersistRollbackDeletePropertyState(
        CCSPNodeImpl *this,
        const struct _GUID *a2,
        struct ISequentialStream *a3,
        struct ISequentialStream *a4)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x1800199e0  mov     eax, 80004001h
0x1800199e5  retn
```
