# _std::_List_alloc_0_std::_List_base_types_Microsoft::Windows::Performance::CCvDDCache::CCvDD_std::allocator_Microsoft::Windows::Performance::CCvDDCache::CCvDD_____::_Buynode0_::_1_::catch$0

- ea: `0x180032c3b`
- end: `0x180032c5b`
- name: `_std::_List_alloc_0_std::_List_base_types_Microsoft::Windows::Performance::CCvDDCache::CCvDD_std::allocator_Microsoft::Windows::Performance::CCvDDCache::CCvDD_____::_Buynode0_::_1_::catch$0`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001d4c`
- `0x18001ce38`

## pseudocode

```c
void __fastcall __noreturn std::_List_alloc_0_std::_List_base_types_Microsoft::Windows::Performance::CCvDDCache::CCvDD_std::allocator_Microsoft::Windows::Performance::CCvDDCache::CCvDD_____::_Buynode0_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::_Tree_buy<unsigned short const *>::_Freenode0(a1, *(_QWORD *)(a2 + 64));
  throw;
}

```

## disassembly

```asm
0x180032c3b  mov     [rsp+arg_8], rdx
0x180032c40  push    rbp
0x180032c41  sub     rsp, 20h
0x180032c45  mov     rbp, rdx
0x180032c48  mov     rdx, [rbp+40h]
0x180032c4c  call    ?_Freenode0@?$_Tree_buy@PEBGV?$allocator@PEBG@std@@@std@@QEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z; std::_Tree_buy<ushort const *>::_Freenode0(std::_Tree_node<ushort const *,void *> *)
0x180032c51  xor     edx, edx; pThrowInfo
0x180032c53  xor     ecx, ecx; pExceptionObject
0x180032c55  call    _CxxThrowException_0
```
