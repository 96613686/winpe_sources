# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>,void *>>>(void)

- ea: `0x18000db58`
- end: `0x18000db80`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d1b4`

## callees

- `0x18000db18`
- `0x18000db58`
- `0x18000dc5c`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    std::unique_ptr<KEY_MAP_RECORD_CACHE>::~unique_ptr<KEY_MAP_RECORD_CACHE>(v2 + 40);
  std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>(a1);
}

```

## disassembly

```asm
0x18000db58  push    rbx
0x18000db5a  sub     rsp, 20h
0x18000db5e  mov     rbx, rcx
0x18000db61  mov     rcx, [rcx+8]
0x18000db65  test    rcx, rcx
0x18000db68  jz      short loc_18000DB73
0x18000db6a  add     rcx, 28h ; '('
0x18000db6e  call    ??1?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@QEAA@XZ; std::unique_ptr<KEY_MAP_RECORD_CACHE>::~unique_ptr<KEY_MAP_RECORD_CACHE>(void)
0x18000db73  mov     rcx, rbx
0x18000db76  add     rsp, 20h
0x18000db7a  pop     rbx
0x18000db7b  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>(void)
```
