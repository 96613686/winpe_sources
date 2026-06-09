# _std::_List_buy_Microsoft::Windows::Performance::CCvDDCache::CCvDD_std::allocator_Microsoft::Windows::Performance::CCvDDCache::CCvDD___::_Buynode_Microsoft::Windows::Performance::CCvDDCache::CCvDD__::_1_::catch$6

- ea: `0x1800322eb`
- end: `0x18003230b`
- name: `_std::_List_buy_Microsoft::Windows::Performance::CCvDDCache::CCvDD_std::allocator_Microsoft::Windows::Performance::CCvDDCache::CCvDD___::_Buynode_Microsoft::Windows::Performance::CCvDDCache::CCvDD__::_1_::catch$6`
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
void __fastcall __noreturn std::_List_buy_Microsoft::Windows::Performance::CCvDDCache::CCvDD_std::allocator_Microsoft::Windows::Performance::CCvDDCache::CCvDD___::_Buynode_Microsoft::Windows::Performance::CCvDDCache::CCvDD__::_1_::catch_6(
        __int64 a1,
        __int64 a2)
{
  std::_Tree_buy<unsigned short const *>::_Freenode0(a1, *(_QWORD *)(a2 + 96));
  throw;
}

```

## disassembly

```asm
0x1800322eb  mov     [rsp+arg_8], rdx
0x1800322f0  push    rbp
0x1800322f1  sub     rsp, 20h
0x1800322f5  mov     rbp, rdx
0x1800322f8  mov     rdx, [rbp+60h]
0x1800322fc  call    ?_Freenode0@?$_Tree_buy@PEBGV?$allocator@PEBG@std@@@std@@QEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z; std::_Tree_buy<ushort const *>::_Freenode0(std::_Tree_node<ushort const *,void *> *)
0x180032301  xor     edx, edx; pThrowInfo
0x180032303  xor     ecx, ecx; pExceptionObject
0x180032305  call    _CxxThrowException_0
```
