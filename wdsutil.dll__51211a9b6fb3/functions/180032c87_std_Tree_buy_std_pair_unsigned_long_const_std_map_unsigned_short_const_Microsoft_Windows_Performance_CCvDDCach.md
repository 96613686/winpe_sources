# _std::_Tree_buy_std::pair_unsigned_long_const__std::map_unsigned_short_const___Microsoft::Windows::Performance::CCvDDCache::CCvDD_const___Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci_std::allocator_std::pair_unsigned_short_const___const_Microsoft::Windows::Performance::CCvDDCache::CCvDD_const__________std::allocator_std::pair_unsigned_long_const__std::map_unsigned_short_const___Microsoft::Windows::Performance::CCvDDCache::CCvDD_const___Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci_std::allocator_std::pair_unsigned_short_const___const_Microsoft::Windows::Performance::CCvDDCache::CCvDD_const_____________::_Buynode0_::_1_::catch$0

- ea: `0x180032c87`
- end: `0x180032ca7`
- name: `_std::_Tree_buy_std::pair_unsigned_long_const__std::map_unsigned_short_const___Microsoft::Windows::Performance::CCvDDCache::CCvDD_const___Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci_std::allocator_std::pair_unsigned_short_const___const_Microsoft::Windows::Performance::CCvDDCache::CCvDD_const__________std::allocator_std::pair_unsigned_long_const__std::map_unsigned_short_const___Microsoft::Windows::Performance::CCvDDCache::CCvDD_const___Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci_std::allocator_std::pair_unsigned_short_const___const_Microsoft::Windows::Performance::CCvDDCache::CCvDD_const_____________::_Buynode0_::_1_::catch$0`
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
void __fastcall __noreturn std::_Tree_buy_std::pair_unsigned_long_const__std::map_unsigned_short_const___Microsoft::Windows::Performance::CCvDDCache::CCvDD_const___Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci_std::allocator_std::pair_unsigned_short_const___const_Microsoft::Windows::Performance::CCvDDCache::CCvDD_const__________std::allocator_std::pair_unsigned_long_const__std::map_unsigned_short_const___Microsoft::Windows::Performance::CCvDDCache::CCvDD_const___Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci_std::allocator_std::pair_unsigned_short_const___const_Microsoft::Windows::Performance::CCvDDCache::CCvDD_const_____________::_Buynode0_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::_Tree_buy<unsigned short const *>::_Freenode0(a1, *(_QWORD *)(a2 + 72));
  throw;
}

```

## disassembly

```asm
0x180032c87  mov     [rsp+arg_8], rdx
0x180032c8c  push    rbp
0x180032c8d  sub     rsp, 20h
0x180032c91  mov     rbp, rdx
0x180032c94  mov     rdx, [rbp+48h]
0x180032c98  call    ?_Freenode0@?$_Tree_buy@PEBGV?$allocator@PEBG@std@@@std@@QEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z; std::_Tree_buy<ushort const *>::_Freenode0(std::_Tree_node<ushort const *,void *> *)
0x180032c9d  xor     edx, edx; pThrowInfo
0x180032c9f  xor     ecx, ecx; pExceptionObject
0x180032ca1  call    _CxxThrowException_0
```
