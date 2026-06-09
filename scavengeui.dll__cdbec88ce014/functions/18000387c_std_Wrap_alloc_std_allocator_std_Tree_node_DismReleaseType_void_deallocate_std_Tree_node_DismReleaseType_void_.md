# std::_Wrap_alloc<std::allocator<std::_Tree_node<_DismReleaseType,void *>>>::deallocate(std::_Tree_node<_DismReleaseType,void *> *,unsigned __int64)

- ea: `0x18000387c`
- end: `0x180003886`
- name: `?deallocate@?$_Wrap_alloc@V?$allocator@U?$_Tree_node@W4_DismReleaseType@@PEAX@std@@@std@@@std@@QEAAXPEAU?$_Tree_node@W4_DismReleaseType@@PEAX@2@_K@Z`
- size: `10`
- prototype: `void __fastcall(__int64, void *)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180003f66`
- `0x180003ff1`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000387f`

## pseudocode

```c
void __fastcall std::_Wrap_alloc<std::allocator<std::_Tree_node<enum _DismReleaseType,void *>>>::deallocate(
        __int64 a1,
        void *a2)
{
  operator delete(a2);
}

```

## disassembly

```asm
0x18000387c  mov     rcx, rdx
0x18000387f  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
