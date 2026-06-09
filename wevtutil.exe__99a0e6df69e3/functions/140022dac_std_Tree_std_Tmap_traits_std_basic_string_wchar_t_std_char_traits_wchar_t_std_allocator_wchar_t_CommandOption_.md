# std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,CommandOption,tlx::istring_less_ordinal,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,CommandOption>>,0>>::_Find_lower_bound<std::basic_string_view<wchar_t,std::char_traits<wchar_t>>>(std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const &)

- ea: `0x140022dac`
- end: `0x140022e70`
- name: `??$_Find_lower_bound@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCommandOption@@@std@@PEAX@std@@@1@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@@Z`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140011958`

## callees

- `0x140022d2c`
- `0x140022dac`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140022e35`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140022e35`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<std::wstring,CommandOption,tlx::istring_less_ordinal,std::allocator<std::pair<std::wstring const,CommandOption>>,0>>::_Find_lower_bound<std::wstring_view>(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 *v5; // r9
  __int64 *v6; // rbx
  __int64 v7; // r9
  __int64 v8; // r8
  const WCHAR *v9; // rcx
  int v10; // eax
  LPCWCH lpString1; // [rsp+30h] [rbp-18h] BYREF
  int cchCount1[4]; // [rsp+38h] [rbp-10h]

  v5 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  *a2 = v5;
  v6 = v5;
  a2[1] = 0;
  for ( a2[2] = *(_QWORD *)a1; !*((_BYTE *)v6 + 25); v6 = (__int64 *)*v6 )
  {
    *a2 = v6;
    tlx::_CharSpan<wchar_t const>::_CharSpan<wchar_t const>(&lpString1, v6 + 4);
    v7 = a3[1];
    if ( (*(_QWORD *)cchCount1 | (unsigned __int64)v7) > 0x7FFFFFFF )
      __int2c();
    v8 = 2;
    v9 = (const WCHAR *)2;
    if ( *a3 )
      v8 = *a3;
    if ( lpString1 )
      v9 = lpString1;
    if ( CompareStringOrdinal(v9, cchCount1[0], (LPCWCH)v8, v7, 1) == 1 )
    {
      v6 += 2;
      v10 = 0;
    }
    else
    {
      a2[2] = v6;
      v10 = 1;
    }
    *((_DWORD *)a2 + 2) = v10;
  }
  return a2;
}

```

## disassembly

```asm
0x140022dac  mov     [rsp+arg_0], rbx
0x140022db1  mov     [rsp+arg_8], rsi
0x140022db6  push    rdi
0x140022db7  sub     rsp, 40h
0x140022dbb  mov     rax, [rcx]
0x140022dbe  mov     rsi, r8
0x140022dc1  mov     rdi, rdx
0x140022dc4  mov     r9, [rax+8]
0x140022dc8  mov     [rdx], r9
0x140022dcb  mov     rbx, r9
0x140022dce  mov     qword ptr [rdx+8], 0
0x140022dd6  mov     rax, [rcx]
0x140022dd9  mov     [rdx+10h], rax
0x140022ddd  cmp     byte ptr [r9+19h], 0
0x140022de2  jnz     short loc_140022E5D
0x140022de4  lea     rdx, [rbx+20h]
0x140022de8  mov     [rdi], rbx
0x140022deb  lea     rcx, [rsp+48h+lpString1]
0x140022df0  call    ??$?0$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@?$_CharSpan@$$CB_W@tlx@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; tlx::_CharSpan<wchar_t const>::_CharSpan<wchar_t const>(std::wstring const &)
0x140022df5  mov     r9, [rsi+8]; cchCount2
0x140022df9  mov     rdx, qword ptr [rsp+48h+cchCount1]; cchCount1
0x140022dfe  mov     rax, r9
0x140022e01  or      rax, rdx
0x140022e04  cmp     rax, 7FFFFFFFh
0x140022e0a  jbe     short loc_140022E0E
0x140022e0c  int     2Ch; Windows NT - assertion failure
0x140022e0e  cmp     qword ptr [rsi], 0
0x140022e12  mov     r8d, 2
0x140022e18  mov     rax, [rsp+48h+lpString1]
0x140022e1d  mov     ecx, 2
0x140022e22  cmovnz  r8, [rsi]; lpString2
0x140022e26  test    rax, rax
0x140022e29  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x140022e31  cmovnz  rcx, rax; lpString1
0x140022e35  call    cs:__imp_CompareStringOrdinal
0x140022e3b  cmp     eax, 1
0x140022e3e  jnz     short loc_140022E48
0x140022e40  add     rbx, 10h
0x140022e44  xor     eax, eax
0x140022e46  jmp     short loc_140022E51
0x140022e48  mov     [rdi+10h], rbx
0x140022e4c  mov     eax, 1
0x140022e51  mov     [rdi+8], eax
0x140022e54  mov     rbx, [rbx]
0x140022e57  cmp     byte ptr [rbx+19h], 0
0x140022e5b  jz      short loc_140022DE4
0x140022e5d  mov     rbx, [rsp+48h+arg_0]
0x140022e62  mov     rax, rdi
0x140022e65  mov     rsi, [rsp+48h+arg_8]
0x140022e6a  add     rsp, 40h
0x140022e6e  pop     rdi
0x140022e6f  retn
```
