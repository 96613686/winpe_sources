# CommandArguments::GetOption(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x140011904`
- end: `0x140011951`
- name: `?GetOption@CommandArguments@@AEBA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z`
- size: `77`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000eeb4`
- `0x14000f940`
- `0x14000fa70`
- `0x140011850`
- `0x140011a38`
- `0x140011bbc`
- `0x140024b00`

## callees

- `0x140011904`
- `0x140011958`

## pseudocode

```c
__int64 *__fastcall CommandArguments::GetOption(_QWORD *a1, __int64 *a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rax

  v7 = std::_Tree<std::_Tmap_traits<std::wstring,CommandOption,tlx::istring_less_ordinal,std::allocator<std::pair<std::wstring const,CommandOption>>,0>>::_Find<std::wstring_view>(
         (__int64)a1,
         a3);
  if ( v7 == *a1 && *(_QWORD *)(a4 + 8) )
    v7 = std::_Tree<std::_Tmap_traits<std::wstring,CommandOption,tlx::istring_less_ordinal,std::allocator<std::pair<std::wstring const,CommandOption>>,0>>::_Find<std::wstring_view>(
           (__int64)a1,
           a4);
  *a2 = v7;
  return a2;
}

```

## disassembly

```asm
0x140011904  mov     [rsp+arg_0], rbx
0x140011909  mov     [rsp+arg_8], rsi
0x14001190e  push    rdi
0x14001190f  sub     rsp, 20h
0x140011913  mov     rbx, rdx
0x140011916  mov     rdi, r9
0x140011919  mov     rdx, r8
0x14001191c  mov     rsi, rcx
0x14001191f  call    ??$_Find@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@@2@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@PEAX@1@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CommandOption,tlx::istring_less_ordinal,std::allocator<std::pair<std::wstring const,CommandOption>>,0>>::_Find<std::wstring_view>(std::wstring_view const &)
0x140011924  cmp     rax, [rsi]
0x140011927  jnz     short loc_14001193B
0x140011929  cmp     qword ptr [rdi+8], 0
0x14001192e  jz      short loc_14001193B
0x140011930  mov     rdx, rdi
0x140011933  mov     rcx, rsi
0x140011936  call    ??$_Find@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@@2@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@PEAX@1@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CommandOption,tlx::istring_less_ordinal,std::allocator<std::pair<std::wstring const,CommandOption>>,0>>::_Find<std::wstring_view>(std::wstring_view const &)
0x14001193b  mov     rsi, [rsp+28h+arg_8]
0x140011940  mov     [rbx], rax
0x140011943  mov     rax, rbx
0x140011946  mov     rbx, [rsp+28h+arg_0]
0x14001194b  add     rsp, 20h
0x14001194f  pop     rdi
0x140011950  retn
```
