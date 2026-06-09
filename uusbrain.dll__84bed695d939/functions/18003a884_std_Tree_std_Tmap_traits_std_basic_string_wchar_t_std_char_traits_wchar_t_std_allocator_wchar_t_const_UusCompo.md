# std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent>>,0>>::~_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent>>,0>>(void)

- ea: `0x18003a884`
- end: `0x18003a907`
- name: `??1?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@U?$less@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `131`
- prototype: `void __fastcall(void **)`
- caller_count: `6`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180035bf0`
- `0x180036ca8`
- `0x180036e60`
- `0x180037064`
- `0x18004d1f8`
- `0x18004dbf0`

## callees

- `0x18000f84c`
- `0x180029644`
- `0x18003a884`
- `0x18003b274`
- `0x180042bc4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall std::_Tree<std::_Tmap_traits<std::wstring const,UusComponent,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,UusComponent>>,0>>::~_Tree<std::_Tmap_traits<std::wstring const,UusComponent,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,UusComponent>>,0>>(
        void **a1)
{
  char *v2; // r15
  char *v3; // rsi

  v2 = (char *)*((_QWORD *)*a1 + 1);
  while ( !v2[25] )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,UusComponent>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *>>>(
      (__int64)a1,
      (__int64)a1,
      *((char **)v2 + 2));
    v3 = v2;
    v2 = *(char **)v2;
    std::vector<enum UusCapability>::~vector<enum UusCapability>(v3 + 96);
    std::wstring::_Tidy_deallocate(v3 + 64);
    std::wstring::_Tidy_deallocate(v3 + 32);
    operator delete(v3, 0x88u);
  }
  operator delete(*a1, 0x88u);
}

```

## disassembly

```asm
0x18003a884  mov     [rsp+arg_8], rbx
0x18003a889  mov     [rsp+arg_10], rsi
0x18003a88e  push    rdi
0x18003a88f  push    r14
0x18003a891  push    r15
0x18003a893  sub     rsp, 20h
0x18003a897  mov     rax, [rcx]
0x18003a89a  mov     r14, rcx
0x18003a89d  mov     r15, [rax+8]
0x18003a8a1  jmp     short loc_18003A8E0
0x18003a8a3  mov     r8, [r15+10h]
0x18003a8a7  mov     rdx, r14
0x18003a8aa  mov     rcx, r14
0x18003a8ad  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,UusComponent>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *>> &,std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *> *)
0x18003a8b2  mov     rsi, r15
0x18003a8b5  mov     r15, [r15]
0x18003a8b8  lea     rcx, [rsi+60h]
0x18003a8bc  call    ??1?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@XZ; std::vector<UusCapability>::~vector<UusCapability>(void)
0x18003a8c1  lea     rcx, [rsi+40h]
0x18003a8c5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a8ca  lea     rcx, [rsi+20h]
0x18003a8ce  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a8d3  mov     edx, 88h; unsigned __int64
0x18003a8d8  mov     rcx, rsi; void *
0x18003a8db  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003a8e0  cmp     byte ptr [r15+19h], 0
0x18003a8e5  jz      short loc_18003A8A3
0x18003a8e7  mov     rcx, [r14]; void *
0x18003a8ea  mov     edx, 88h; unsigned __int64
0x18003a8ef  mov     rbx, [rsp+38h+arg_8]
0x18003a8f4  mov     rsi, [rsp+38h+arg_10]
0x18003a8f9  add     rsp, 20h
0x18003a8fd  pop     r15
0x18003a8ff  pop     r14
0x18003a901  pop     rdi
0x18003a902  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
