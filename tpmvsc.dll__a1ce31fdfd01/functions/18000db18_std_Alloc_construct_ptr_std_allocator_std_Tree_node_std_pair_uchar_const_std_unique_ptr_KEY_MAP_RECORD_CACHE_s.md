# std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>,void *>>>(void)

- ea: `0x18000db18`
- end: `0x18000db34`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000db58`
- `0x1800355d3`

## callees

- `0x180006238`
- `0x18000db18`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    std::_Deallocate<16>(v1, 0x30u);
}

```

## disassembly

```asm
0x18000db18  sub     rsp, 28h
0x18000db1c  mov     rcx, [rcx+8]
0x18000db20  test    rcx, rcx
0x18000db23  jz      short loc_18000DB2F
0x18000db25  mov     edx, 30h ; '0'
0x18000db2a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000db2f  add     rsp, 28h
0x18000db33  retn
```
