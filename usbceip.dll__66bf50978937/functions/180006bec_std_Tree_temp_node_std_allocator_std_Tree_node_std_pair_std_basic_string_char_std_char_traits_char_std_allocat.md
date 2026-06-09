# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,ulong>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,ulong>,void *>>>(void)

- ea: `0x180006bec`
- end: `0x180006c14`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `40`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006a88`

## callees

- `0x180006808`
- `0x180006bc8`
- `0x180006bec`

## pseudocode

```c
__int64 __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,unsigned long>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::string const,unsigned long>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    std::string::_Tidy_deallocate(v2 + 32);
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,unsigned long>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,unsigned long>,void *>>>(a1);
}

```

## disassembly

```asm
0x180006bec  push    rbx
0x180006bee  sub     rsp, 20h
0x180006bf2  mov     rbx, rcx
0x180006bf5  mov     rcx, [rcx+8]
0x180006bf9  test    rcx, rcx
0x180006bfc  jz      short loc_180006C07
0x180006bfe  add     rcx, 20h ; ' '
0x180006c02  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180006c07  mov     rcx, rbx
0x180006c0a  add     rsp, 20h
0x180006c0e  pop     rbx
0x180006c0f  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,ulong>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::string const,ulong>,void *>>>(void)
```
