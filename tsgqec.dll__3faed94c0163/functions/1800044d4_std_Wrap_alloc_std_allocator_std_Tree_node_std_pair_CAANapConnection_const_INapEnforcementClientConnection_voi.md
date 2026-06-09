# std::_Wrap_alloc<std::allocator<std::_Tree_node<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>,void *>>>::deallocate(std::_Tree_node<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>,void *> *,unsigned __int64)

- ea: `0x1800044d4`
- end: `0x1800044de`
- name: `?deallocate@?$_Wrap_alloc@V?$allocator@U?$_Tree_node@U?$pair@QEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@@std@@PEAX@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@U?$pair@QEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@@std@@PEAX@2@_K@Z`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18000b296`
- `0x18000b30f`
- `0x18000b335`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800044d7`

## pseudocode

```c
void __fastcall std::_Wrap_alloc<std::allocator<std::_Tree_node<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>,void *>>>::deallocate(
        __int64 a1,
        void *a2)
{
  operator delete(a2);
}

```

## disassembly

```asm
0x1800044d4  mov     rcx, rdx
0x1800044d7  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
