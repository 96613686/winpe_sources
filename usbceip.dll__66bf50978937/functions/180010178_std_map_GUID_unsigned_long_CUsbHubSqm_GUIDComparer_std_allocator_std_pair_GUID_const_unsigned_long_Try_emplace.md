# _std::map__GUID_unsigned_long_CUsbHubSqm::GUIDComparer_std::allocator_std::pair__GUID_const__unsigned_long_____::_Try_emplace__GUID_const_&__::_1_::dtor$2

- ea: `0x180010178`
- end: `0x180010184`
- name: `_std::map__GUID_unsigned_long_CUsbHubSqm::GUIDComparer_std::allocator_std::pair__GUID_const__unsigned_long_____::_Try_emplace__GUID_const_&__::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005170`

## pseudocode

```c
__int64 __fastcall std::map__GUID_unsigned_long_CUsbHubSqm::GUIDComparer_std::allocator_std::pair__GUID_const__unsigned_long_____::_Try_emplace__GUID_const____::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,unsigned long>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,unsigned long>,void *>>>(a2 + 64);
}

```

## disassembly

```asm
0x180010178  lea     rcx, [rdx+40h]
0x18001017f  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,ulong>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_GUID const,ulong>,void *>>>(void)
```
