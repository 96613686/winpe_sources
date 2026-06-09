# _std::_Tree_buy_std::pair_unsigned_long_const__std::map_unsigned_short_const___Microsoft::Windows::Performance::CCvDDCache::CCvDD_const___Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci_std::allocator_std::pair_unsigned_short_const___const_Microsoft::Windows::Performance::CCvDDCache::CCvDD_const__________std::allocator_std::pair_unsigned_long_const__std::map_unsigned_short_const___Microsoft::Windows::Performance::CCvDDCache::CCvDD_const___Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci_std::allocator_std::pair_unsigned_short_const___const_Microsoft::Windows::Performance::CCvDDCache::CCvDD_const_____________::_Buynode_std::pair_unsigned_long_std::map_unsigned_short_const___Microsoft::Windows::Performance::CCvDDCache::CCvDD_const___Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci_std::allocator_std::pair_unsigned_short_const___const_Microsoft::Windows::Performance::CCvDDCache::CCvDD_const____________::_1_::catch$5

- ea: `0x18003228d`
- end: `0x1800322ad`
- name: `_std::_Tree_buy_std::pair_unsigned_long_const__std::map_unsigned_short_const___Microsoft::Windows::Performance::CCvDDCache::CCvDD_const___Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci_std::allocator_std::pair_unsigned_short_const___const_Microsoft::Windows::Performance::CCvDDCache::CCvDD_const__________std::allocator_std::pair_unsigned_long_const__std::map_unsigned_short_const___Microsoft::Windows::Performance::CCvDDCache::CCvDD_const___Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci_std::allocator_std::pair_unsigned_short_const___const_Microsoft::Windows::Performance::CCvDDCache::CCvDD_const_____________::_Buynode_std::pair_unsigned_long_std::map_unsigned_short_const___Microsoft::Windows::Performance::CCvDDCache::CCvDD_const___Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci_std::allocator_std::pair_unsigned_short_const___const_Microsoft::Windows::Performance::CCvDDCache::CCvDD_const____________::_1_::catch$5`
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
void __fastcall __noreturn std::_Tree_buy_std::pair_unsigned_long_const__std::map_unsigned_short_const___Microsoft::Windows::Performance::CCvDDCache::CCvDD_const___Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci_std::allocator_std::pair_unsigned_short_const___const_Microsoft::Windows::Performance::CCvDDCache::CCvDD_const__________std::allocator_std::pair_unsigned_long_const__std::map_unsigned_short_const___Microsoft::Windows::Performance::CCvDDCache::CCvDD_const___Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci_std::allocator_std::pair_unsigned_short_const___const_Microsoft::Windows::Performance::CCvDDCache::CCvDD_const_____________::_Buynode_std::pair_unsigned_long_std::map_unsigned_short_const___Microsoft::Windows::Performance::CCvDDCache::CCvDD_const___Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci_std::allocator_std::pair_unsigned_short_const___const_Microsoft::Windows::Performance::CCvDDCache::CCvDD_const____________::_1_::catch_5(
        __int64 a1,
        __int64 a2)
{
  std::_Tree_buy<unsigned short const *>::_Freenode0(a1, *(_QWORD *)(a2 + 72));
  throw;
}

```

## disassembly

```asm
0x18003228d  mov     [rsp+arg_8], rdx
0x180032292  push    rbp
0x180032293  sub     rsp, 20h
0x180032297  mov     rbp, rdx
0x18003229a  mov     rdx, [rbp+48h]
0x18003229e  call    ?_Freenode0@?$_Tree_buy@PEBGV?$allocator@PEBG@std@@@std@@QEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z; std::_Tree_buy<ushort const *>::_Freenode0(std::_Tree_node<ushort const *,void *> *)
0x1800322a3  xor     edx, edx; pThrowInfo
0x1800322a5  xor     ecx, ecx; pExceptionObject
0x1800322a7  call    _CxxThrowException_0
```
