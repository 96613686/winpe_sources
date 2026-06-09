# tlx::istring_less_ordinal::operator()<std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,wchar_t,wchar_t,0>(std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const &)

- ea: `0x18002c258`
- end: `0x18002c2a9`
- name: `??$?RV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V01@_W_W$0A@@istring_less_ordinal@tlx@@QEBA_NAEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002d8c8`

## callees

- `0x18002c258`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c298`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c298`

## pseudocode

```c
bool __fastcall tlx::istring_less_ordinal::operator()<std::wstring_view,std::wstring_view,wchar_t,wchar_t,0>(
        __int64 a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 v3; // r9
  __int64 v4; // r11
  __int64 v5; // rdx
  __int64 v6; // r10
  __int64 v7; // rcx
  __int64 v8; // r8

  v3 = a3[1];
  v4 = *a2;
  v5 = a2[1];
  v6 = *a3;
  if ( (v5 | (unsigned __int64)v3) > 0x7FFFFFFF )
    __int2c();
  v7 = 2;
  v8 = 2;
  if ( v6 )
    v8 = v6;
  if ( v4 )
    v7 = v4;
  return CompareStringOrdinal((LPCWCH)v7, v5, (LPCWCH)v8, v3, 1) == 1;
}

```

## disassembly

```asm
0x18002c258  sub     rsp, 38h
0x18002c25c  mov     r9, [r8+8]; cchCount2
0x18002c260  mov     r11, [rdx]
0x18002c263  mov     rax, r9
0x18002c266  mov     rdx, [rdx+8]; cchCount1
0x18002c26a  mov     r10, [r8]
0x18002c26d  or      rax, rdx
0x18002c270  cmp     rax, 7FFFFFFFh
0x18002c276  jbe     short loc_18002C27A
0x18002c278  int     2Ch; Windows NT - assertion failure
0x18002c27a  test    r10, r10
0x18002c27d  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18002c285  mov     ecx, 2
0x18002c28a  mov     r8d, ecx
0x18002c28d  cmovnz  r8, r10; lpString2
0x18002c291  test    r11, r11
0x18002c294  cmovnz  rcx, r11; lpString1
0x18002c298  call    cs:__imp_CompareStringOrdinal
0x18002c29e  cmp     eax, 1
0x18002c2a1  setz    al
0x18002c2a4  add     rsp, 38h
0x18002c2a8  retn
```
