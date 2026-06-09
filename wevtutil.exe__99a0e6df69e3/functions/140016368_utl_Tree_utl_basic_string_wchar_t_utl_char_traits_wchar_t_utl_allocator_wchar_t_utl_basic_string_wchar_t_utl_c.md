# utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_KeyIsLessEqual<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)

- ea: `0x140016368`
- end: `0x1400163c6`
- name: `??$_KeyIsLessEqual@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@Uistring_less_ordinal@tlx@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@$0A@@utl@@AEBA_NAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@1@0@Z`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002b7e0`

## callees

- `0x140016368`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400163b5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400163b5`

## pseudocode

```c
bool __fastcall utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_KeyIsLessEqual<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(
        __int64 a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 v3; // r11
  __int64 v4; // r9
  __int64 v5; // r10
  __int64 v6; // rcx
  __int64 v7; // r8

  v3 = *a3;
  v4 = (a2[1] - *a2) >> 1;
  v5 = (a3[1] - *a3) >> 1;
  if ( (v5 | (unsigned __int64)v4) > 0x7FFFFFFF )
    __int2c();
  v6 = 2;
  v7 = 2;
  if ( *a2 )
    v7 = *a2;
  if ( v3 )
    v6 = v3;
  return CompareStringOrdinal((LPCWCH)v6, v5, (LPCWCH)v7, v4, 1) != 1;
}

```

## disassembly

```asm
0x140016368  sub     rsp, 38h
0x14001636c  mov     r9, [rdx+8]
0x140016370  sub     r9, [rdx]
0x140016373  mov     r11, [r8]
0x140016376  mov     r10, [r8+8]
0x14001637a  sar     r9, 1; cchCount2
0x14001637d  sub     r10, r11
0x140016380  sar     r10, 1
0x140016383  mov     rax, r9
0x140016386  or      rax, r10
0x140016389  cmp     rax, 7FFFFFFFh
0x14001638f  jbe     short loc_140016393
0x140016391  int     2Ch; Windows NT - assertion failure
0x140016393  cmp     qword ptr [rdx], 0
0x140016397  mov     ecx, 2
0x14001639c  mov     r8d, ecx
0x14001639f  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1400163a7  cmovnz  r8, [rdx]; lpString2
0x1400163ab  test    r11, r11
0x1400163ae  mov     edx, r10d; cchCount1
0x1400163b1  cmovnz  rcx, r11; lpString1
0x1400163b5  call    cs:__imp_CompareStringOrdinal
0x1400163bb  cmp     eax, 1
0x1400163be  setnz   al
0x1400163c1  add     rsp, 38h
0x1400163c5  retn
```
