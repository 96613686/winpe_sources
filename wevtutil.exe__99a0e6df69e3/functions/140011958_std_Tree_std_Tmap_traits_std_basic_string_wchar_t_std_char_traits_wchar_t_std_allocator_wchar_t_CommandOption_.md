# std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,CommandOption,tlx::istring_less_ordinal,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,CommandOption>>,0>>::_Find<std::basic_string_view<wchar_t,std::char_traits<wchar_t>>>(std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const &)

- ea: `0x140011958`
- end: `0x1400119f7`
- name: `??$_Find@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@@2@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@PEAX@1@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@@Z`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140011904`

## callees

- `0x140011958`
- `0x140022d2c`
- `0x140022dac`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400119d6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400119d6`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<std::wstring,CommandOption,tlx::istring_less_ordinal,std::allocator<std::pair<std::wstring const,CommandOption>>,0>>::_Find<std::wstring_view>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  unsigned __int64 v4; // r10
  __int64 v5; // r11
  __int64 v6; // rcx
  const WCHAR *v7; // r8
  bool v8; // zf
  __int64 result; // rax
  LPCWCH lpString2; // [rsp+30h] [rbp-28h] BYREF
  int cchCount2[2]; // [rsp+38h] [rbp-20h]
  __int64 v12; // [rsp+40h] [rbp-18h]

  std::_Tree<std::_Tmap_traits<std::wstring,CommandOption,tlx::istring_less_ordinal,std::allocator<std::pair<std::wstring const,CommandOption>>,0>>::_Find_lower_bound<std::wstring_view>(
    a1,
    &lpString2,
    a2);
  v3 = v12;
  if ( *(_BYTE *)(v12 + 25) )
    return *(_QWORD *)a1;
  tlx::_CharSpan<wchar_t const>::_CharSpan<wchar_t const>(&lpString2, v12 + 32);
  if ( (*(_QWORD *)cchCount2 | v4) > 0x7FFFFFFF )
    __int2c();
  v6 = 2;
  v7 = (const WCHAR *)2;
  if ( lpString2 )
    v7 = lpString2;
  if ( v5 )
    v6 = v5;
  v8 = CompareStringOrdinal((LPCWCH)v6, v4, v7, cchCount2[0], 1) == 1;
  result = v3;
  if ( v8 )
    return *(_QWORD *)a1;
  return result;
}

```

## disassembly

```asm
0x140011958  mov     [rsp+arg_0], rbx
0x14001195d  mov     [rsp+arg_8], rsi
0x140011962  push    rdi
0x140011963  sub     rsp, 50h
0x140011967  mov     rdi, rdx
0x14001196a  mov     r8, rdx
0x14001196d  lea     rdx, [rsp+58h+lpString2]
0x140011972  mov     rsi, rcx
0x140011975  call    ??$_Find_lower_bound@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@PEAX@std@@@1@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CommandOption,tlx::istring_less_ordinal,std::allocator<std::pair<std::wstring const,CommandOption>>,0>>::_Find_lower_bound<std::wstring_view>(std::wstring_view const &)
0x14001197a  mov     rbx, [rsp+58h+var_18]
0x14001197f  cmp     byte ptr [rbx+19h], 0
0x140011983  jnz     short loc_1400119E4
0x140011985  mov     r11, [rdi]
0x140011988  lea     rdx, [rbx+20h]
0x14001198c  mov     r10, [rdi+8]
0x140011990  lea     rcx, [rsp+58h+lpString2]
0x140011995  call    ??$?0$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@?$_CharSpan@$$CB_W@tlx@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; tlx::_CharSpan<wchar_t const>::_CharSpan<wchar_t const>(std::wstring const &)
0x14001199a  mov     r9, qword ptr [rsp+58h+cchCount2]; cchCount2
0x14001199f  mov     rcx, r10
0x1400119a2  or      rcx, r9
0x1400119a5  cmp     rcx, 7FFFFFFFh
0x1400119ac  jbe     short loc_1400119B0
0x1400119ae  int     2Ch; Windows NT - assertion failure
0x1400119b0  mov     rax, [rsp+58h+lpString2]
0x1400119b5  mov     ecx, 2
0x1400119ba  test    rax, rax
0x1400119bd  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x1400119c5  mov     r8d, ecx
0x1400119c8  mov     edx, r10d; cchCount1
0x1400119cb  cmovnz  r8, rax; lpString2
0x1400119cf  test    r11, r11
0x1400119d2  cmovnz  rcx, r11; lpString1
0x1400119d6  call    cs:__imp_CompareStringOrdinal
0x1400119dc  cmp     eax, 1
0x1400119df  mov     rax, rbx
0x1400119e2  jnz     short loc_1400119E7
0x1400119e4  mov     rax, [rsi]
0x1400119e7  mov     rbx, [rsp+58h+arg_0]
0x1400119ec  mov     rsi, [rsp+58h+arg_8]
0x1400119f1  add     rsp, 50h
0x1400119f5  pop     rdi
0x1400119f6  retn
```
