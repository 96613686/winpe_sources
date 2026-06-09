# std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>,void *>> &,std::_Tree_node<std::pair<uchar const,std::unique_ptr<KEY_MAP_RECORD_CACHE,std::default_delete<KEY_MAP_RECORD_CACHE>>>,void *> *)

- ea: `0x18000cd48`
- end: `0x18000cd6c`
- name: `??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEV?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z`
- size: `36`
- prototype: `void __fastcall(__int64, char *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cca0`
- `0x180014cbc`

## callees

- `0x180006238`
- `0x18000dc5c`

## pseudocode

```c
void __fastcall std::_Tree_node<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::unique_ptr<KEY_MAP_RECORD_CACHE>>,void *>>>(
        __int64 a1,
        char *a2)
{
  std::unique_ptr<KEY_MAP_RECORD_CACHE>::~unique_ptr<KEY_MAP_RECORD_CACHE>(a2 + 40);
  std::_Deallocate<16>(a2, 0x30u);
}

```

## disassembly

```asm
0x18000cd48  push    rbx
0x18000cd4a  sub     rsp, 20h
0x18000cd4e  lea     rcx, [rdx+28h]
0x18000cd52  mov     rbx, rdx
0x18000cd55  call    ??1?$unique_ptr@UKEY_MAP_RECORD_CACHE@@U?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@@std@@QEAA@XZ; std::unique_ptr<KEY_MAP_RECORD_CACHE>::~unique_ptr<KEY_MAP_RECORD_CACHE>(void)
0x18000cd5a  mov     edx, 30h ; '0'
0x18000cd5f  mov     rcx, rbx
0x18000cd62  add     rsp, 20h
0x18000cd66  pop     rbx
0x18000cd67  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
