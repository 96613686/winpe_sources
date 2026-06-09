# _std::_Tree_alloc_0_std::_Tree_base_types_ComTaskHost___std::allocator_ComTaskHost_______::_Buyheadnode_::_1_::catch$0

- ea: `0x14000af00`
- end: `0x14000af21`
- name: `_std::_Tree_alloc_0_std::_Tree_base_types_ComTaskHost___std::allocator_ComTaskHost_______::_Buyheadnode_::_1_::catch$0`
- size: `33`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x14000894c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000af11`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000af11`

## pseudocode

```c
void __fastcall __noreturn std::_Tree_alloc_0_std::_Tree_base_types_ComTaskHost___std::allocator_ComTaskHost_______::_Buyheadnode_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 48));
  throw;
}

```

## disassembly

```asm
0x14000af00  mov     [rsp+arg_8], rdx
0x14000af05  push    rbp
0x14000af06  sub     rsp, 20h
0x14000af0a  mov     rbp, rdx
0x14000af0d  mov     rcx, [rbp+30h]
0x14000af11  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000af17  xor     edx, edx; pThrowInfo
0x14000af19  xor     ecx, ecx; pExceptionObject
0x14000af1b  call    _CxxThrowException_0
```
