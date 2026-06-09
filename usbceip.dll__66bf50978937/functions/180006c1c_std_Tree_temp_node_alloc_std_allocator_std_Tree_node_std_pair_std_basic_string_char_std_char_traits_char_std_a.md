# std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,ulong>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,ulong>,void *>>>(void)

- ea: `0x180006c1c`
- end: `0x180006c21`
- name: `??1?$_Tree_temp_node_alloc@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010330`

## callees

- `0x180006bc8`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall std::_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::string const,unsigned long>,void *>>>::~_Tree_temp_node_alloc<std::allocator<std::_Tree_node<std::pair<std::string const,unsigned long>,void *>>>(
        __int64 a1)
{
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,unsigned long>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,unsigned long>,void *>>>(a1);
}

```

## disassembly

```asm
0x180006c1c  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,ulong>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,ulong>,void *>>>(void)
```
