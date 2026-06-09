# utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_FindImpl<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> const &)

- ea: `0x14001e02c`
- end: `0x14001e0ba`
- name: `??$_FindImpl@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@Uistring_less_ordinal@tlx@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@$0A@@utl@@AEBAPEAU?$_TreeNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@1@AEBV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001d828`

## callees

- `0x14001e02c`
- `0x140029ef8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14001e09a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14001e09a`

## pseudocode

```c
__int64 __fastcall utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_FindImpl<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rax
  __int64 v6; // r10
  __int64 v7; // rdx
  __int64 v8; // r9
  __int64 v9; // rcx
  __int64 v10; // r8

  if ( *(_QWORD *)(a1 + 16) == a1 )
    return a1;
  v5 = utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_LowerBoundNonEmpty<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>();
  v4 = v5;
  if ( v5 != a1 )
  {
    v6 = *(_QWORD *)(v5 + 24);
    v7 = a2[1];
    v8 = (*(_QWORD *)(v5 + 32) - v6) >> 1;
    if ( (v7 | (unsigned __int64)v8) > 0x7FFFFFFF )
      __int2c();
    v9 = 2;
    v10 = 2;
    if ( v6 )
      v10 = *(_QWORD *)(v5 + 24);
    if ( *a2 )
      v9 = *a2;
    if ( CompareStringOrdinal((LPCWCH)v9, v7, (LPCWCH)v10, v8, 1) == 1 )
      return a1;
  }
  return v4;
}

```

## disassembly

```asm
0x14001e02c  mov     [rsp+arg_0], rbx
0x14001e031  mov     [rsp+arg_8], rsi
0x14001e036  push    rdi
0x14001e037  sub     rsp, 30h
0x14001e03b  mov     rsi, rdx
0x14001e03e  mov     rbx, rcx
0x14001e041  cmp     [rcx+10h], rcx
0x14001e045  jnz     short loc_14001E04C
0x14001e047  mov     rdi, rcx
0x14001e04a  jmp     short loc_14001E0A7
0x14001e04c  call    ??$_LowerBoundNonEmpty@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@Uistring_less_ordinal@tlx@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@$0A@@utl@@AEBAPEAU?$_TreeNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@1@AEBV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_LowerBoundNonEmpty<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x14001e051  mov     rdi, rax
0x14001e054  cmp     rax, rbx
0x14001e057  jz      short loc_14001E0A7
0x14001e059  mov     r10, [rax+18h]
0x14001e05d  mov     r9, [rax+20h]
0x14001e061  mov     rdx, [rsi+8]; cchCount1
0x14001e065  sub     r9, r10
0x14001e068  sar     r9, 1; cchCount2
0x14001e06b  mov     rax, r9
0x14001e06e  or      rax, rdx
0x14001e071  cmp     rax, 7FFFFFFFh
0x14001e077  jbe     short loc_14001E07B
0x14001e079  int     2Ch; Windows NT - assertion failure
0x14001e07b  test    r10, r10
0x14001e07e  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x14001e086  mov     ecx, 2
0x14001e08b  mov     r8d, ecx
0x14001e08e  cmovnz  r8, r10; lpString2
0x14001e092  cmp     qword ptr [rsi], 0
0x14001e096  cmovnz  rcx, [rsi]; lpString1
0x14001e09a  call    cs:__imp_CompareStringOrdinal
0x14001e0a0  cmp     eax, 1
0x14001e0a3  cmovz   rdi, rbx
0x14001e0a7  mov     rbx, [rsp+38h+arg_0]
0x14001e0ac  mov     rax, rdi
0x14001e0af  mov     rsi, [rsp+38h+arg_8]
0x14001e0b4  add     rsp, 30h
0x14001e0b8  pop     rdi
0x14001e0b9  retn
```
