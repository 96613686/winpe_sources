# std::_Tree<std::_Tmap_traits<std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,TEMPLATE_ENTRY *,std::less<std::basic_string_view<wchar_t,std::char_traits<wchar_t>>>,std::allocator<std::pair<std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const,TEMPLATE_ENTRY *>>,0>>::_Emplace<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,TEMPLATE_ENTRY *>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,TEMPLATE_ENTRY * &&)

- ea: `0x18002d2ac`
- end: `0x18002d3bb`
- name: `??$_Emplace@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAVTEMPLATE_ENTRY@@@?$_Tree@V?$_Tmap_traits@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@@std@@PEAX@std@@_N@1@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAPEAVTEMPLATE_ENTRY@@@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800193cc`

## callees

- `0x1800207e4`
- `0x18002d2ac`
- `0x18002f104`
- `0x18002f574`
- `0x180032964`
- `0x180033df0`
- `0x18003c534`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002d36c`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002d36c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Tree<std::_Tmap_traits<std::wstring_view,TEMPLATE_ENTRY *,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,TEMPLATE_ENTRY *>>,0>>::_Emplace<std::wstring &,TEMPLATE_ENTRY *>(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v8; // rdi
  _QWORD *v9; // r12
  _QWORD *v10; // rax
  __int128 v11; // xmm6
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int128 v15; // [rsp+20h] [rbp-78h] BYREF
  _QWORD v16[4]; // [rsp+30h] [rbp-68h] BYREF

  v8 = *a1;
  *(_QWORD *)&v15 = a1;
  v9 = operator new(0x38u);
  *((_QWORD *)&v15 + 1) = v9;
  std::wstring::operator std::wstring_view(a3, v9 + 4);
  v9[6] = *a4;
  *v9 = v8;
  v9[1] = v8;
  v9[2] = v8;
  *((_WORD *)v9 + 12) = 0;
  v10 = std::_Tree<std::_Tmap_traits<std::wstring_view,TEMPLATE_ENTRY *,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,TEMPLATE_ENTRY *>>,0>>::_Find_lower_bound<std::wstring_view>(
          (__int64)a1,
          v16,
          (__int64)(v9 + 4));
  v11 = *(_OWORD *)v10;
  v12 = v10[2];
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring_view,TASK_ENTRY *,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,TASK_ENTRY *>>,0>>::_Lower_bound_duplicate<std::wstring_view>(
                          v13,
                          v12,
                          v9 + 4) )
  {
    *(_QWORD *)a2 = v12;
    *(_BYTE *)(a2 + 8) = 0;
    std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>,void *>>>((__int64)&v15);
  }
  else
  {
    if ( a1[1] == 0x492492492492492LL )
      std::_Xlength_error("map/set too long");
    *((_QWORD *)&v15 + 1) = 0;
    std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>,void *>>>((__int64)&v15);
    v15 = v11;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<unsigned __int64>>::_Insert_node(a1, &v15, v9);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x18002d2ac  push    rbx
0x18002d2ae  push    rbp
0x18002d2af  push    rsi
0x18002d2b0  push    rdi
0x18002d2b1  push    r12
0x18002d2b3  push    r14
0x18002d2b5  push    r15
0x18002d2b7  sub     rsp, 60h
0x18002d2bb  movaps  [rsp+98h+var_48], xmm6
0x18002d2c0  mov     rsi, r9
0x18002d2c3  mov     rbx, r8
0x18002d2c6  mov     r14, rdx
0x18002d2c9  mov     r15, rcx
0x18002d2cc  mov     rdi, [rcx]
0x18002d2cf  mov     qword ptr [rsp+98h+var_78], rcx
0x18002d2d4  mov     qword ptr [rsp+98h+var_78+8], 0
0x18002d2dd  mov     ecx, 38h ; '8'; Size
0x18002d2e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d2e7  mov     r12, rax
0x18002d2ea  mov     qword ptr [rsp+98h+var_78+8], rax
0x18002d2ef  lea     rbp, [rax+20h]
0x18002d2f3  mov     rdx, rbp
0x18002d2f6  mov     rcx, rbx
0x18002d2f9  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18002d2fe  mov     rcx, [rsi]
0x18002d301  mov     [rbp+10h], rcx
0x18002d305  mov     [r12], rdi
0x18002d309  mov     [r12+8], rdi
0x18002d30e  mov     [r12+10h], rdi
0x18002d313  mov     word ptr [r12+18h], 0
0x18002d31b  mov     r8, rbp
0x18002d31e  lea     rdx, [rsp+98h+var_68]
0x18002d323  mov     rcx, r15
0x18002d326  call    ??$_Find_lower_bound@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@@std@@PEAX@std@@@1@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring_view,TEMPLATE_ENTRY *,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,TEMPLATE_ENTRY *>>,0>>::_Find_lower_bound<std::wstring_view>(std::wstring_view const &)
0x18002d32b  movups  xmm6, xmmword ptr [rax]
0x18002d32e  mov     rbx, [rax+10h]
0x18002d332  mov     r8, rbp
0x18002d335  mov     rdx, rbx
0x18002d338  call    ??$_Lower_bound_duplicate@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTASK_ENTRY@@@std@@PEAX@1@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring_view,TASK_ENTRY *,std::less<std::wstring_view>,std::allocator<std::pair<std::wstring_view const,TASK_ENTRY *>>,0>>::_Lower_bound_duplicate<std::wstring_view>(std::_Tree_node<std::pair<std::wstring_view const,TASK_ENTRY *>,void *> * const,std::wstring_view const &)
0x18002d33d  test    al, al
0x18002d33f  jz      short loc_18002D355
0x18002d341  mov     [r14], rbx
0x18002d344  mov     byte ptr [r14+8], 0
0x18002d349  lea     rcx, [rsp+98h+var_78]
0x18002d34e  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>,void *>>>(void)
0x18002d353  jmp     short loc_18002D3A4
0x18002d355  mov     rax, 492492492492492h
0x18002d35f  cmp     [r15+8], rax
0x18002d363  jnz     short loc_18002D373
0x18002d365  lea     rcx, aMapSetTooLong; "map/set too long"
0x18002d36c  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002d373  mov     qword ptr [rsp+98h+var_78+8], 0
0x18002d37c  lea     rcx, [rsp+98h+var_78]
0x18002d381  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$unique_ptr@VSTRING_ENTRY@@U?$default_delete@VSTRING_ENTRY@@@std@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring_view const,std::unique_ptr<STRING_ENTRY>>,void *>>>(void)
0x18002d386  movdqu  [rsp+98h+var_78], xmm6
0x18002d38c  mov     r8, r12
0x18002d38f  lea     rdx, [rsp+98h+var_78]
0x18002d394  mov     rcx, r15
0x18002d397  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@_K@std@@@std@@QEAAPEAU?$_Tree_node@_KPEAX@2@U?$_Tree_id@PEAU?$_Tree_node@_KPEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<unsigned __int64>>::_Insert_node(std::_Tree_id<std::_Tree_node<unsigned __int64,void *> *>,std::_Tree_node<unsigned __int64,void *> * const)
0x18002d39c  mov     [r14], rax
0x18002d39f  mov     byte ptr [r14+8], 1
0x18002d3a4  mov     rax, r14
0x18002d3a7  movaps  xmm6, [rsp+98h+var_48]
0x18002d3ac  add     rsp, 60h
0x18002d3b0  pop     r15
0x18002d3b2  pop     r14
0x18002d3b4  pop     r12
0x18002d3b6  pop     rdi
0x18002d3b7  pop     rsi
0x18002d3b8  pop     rbp
0x18002d3b9  pop     rbx
0x18002d3ba  retn
```
