# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent>>>::_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent>,void *>>>::~_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent>,void *>>>(void)

- ea: `0x18003f958`
- end: `0x18003f9df`
- name: `??1?$_Erase_tree_and_orphan_guard@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@@std@@@std@@QEAA@XZ`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003f1bc`
- `0x18004d2af`

## callees

- `0x18000f84c`
- `0x180029644`
- `0x18003b274`
- `0x18003f958`
- `0x180042bc4`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,UusComponent>>>::_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *>>>::~_Erase_tree_and_orphan_guard<std::allocator<std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *>>>(
        __int64 *a1)
{
  __int64 v1; // rbp
  char *v2; // r14
  __int64 v3; // r15
  char *v4; // rsi

  v1 = *a1;
  if ( *a1 )
  {
    v2 = (char *)a1[2];
    v3 = a1[1];
    while ( !v2[25] )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,UusComponent>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *>>>(
        v1,
        v3,
        *((char **)v2 + 2));
      v4 = v2;
      v2 = *(char **)v2;
      std::vector<enum UusCapability>::~vector<enum UusCapability>(v4 + 96);
      std::wstring::_Tidy_deallocate(v4 + 64);
      std::wstring::_Tidy_deallocate(v4 + 32);
      operator delete(v4);
    }
  }
}

```

## disassembly

```asm
0x18003f958  mov     [rsp+arg_8], rbx
0x18003f95d  mov     [rsp+arg_10], rbp
0x18003f962  mov     [rsp+arg_18], rsi
0x18003f967  push    rdi
0x18003f968  push    r14
0x18003f96a  push    r15
0x18003f96c  sub     rsp, 20h
0x18003f970  mov     rbp, [rcx]
0x18003f973  test    rbp, rbp
0x18003f976  jz      short loc_18003F9C6
0x18003f978  mov     r14, [rcx+10h]
0x18003f97c  mov     r15, [rcx+8]
0x18003f980  jmp     short loc_18003F9BF
0x18003f982  mov     r8, [r14+10h]
0x18003f986  mov     rdx, r15
0x18003f989  mov     rcx, rbp
0x18003f98c  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,UusComponent>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *>> &,std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *> *)
0x18003f991  mov     rsi, r14
0x18003f994  mov     r14, [r14]
0x18003f997  lea     rcx, [rsi+60h]
0x18003f99b  call    ??1?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@XZ; std::vector<UusCapability>::~vector<UusCapability>(void)
0x18003f9a0  lea     rcx, [rsi+40h]
0x18003f9a4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003f9a9  lea     rcx, [rsi+20h]
0x18003f9ad  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003f9b2  mov     edx, 88h; unsigned __int64
0x18003f9b7  mov     rcx, rsi; void *
0x18003f9ba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003f9bf  cmp     byte ptr [r14+19h], 0
0x18003f9c4  jz      short loc_18003F982
0x18003f9c6  mov     rbx, [rsp+38h+arg_8]
0x18003f9cb  mov     rbp, [rsp+38h+arg_10]
0x18003f9d0  mov     rsi, [rsp+38h+arg_18]
0x18003f9d5  add     rsp, 20h
0x18003f9d9  pop     r15
0x18003f9db  pop     r14
0x18003f9dd  pop     rdi
0x18003f9de  retn
```
