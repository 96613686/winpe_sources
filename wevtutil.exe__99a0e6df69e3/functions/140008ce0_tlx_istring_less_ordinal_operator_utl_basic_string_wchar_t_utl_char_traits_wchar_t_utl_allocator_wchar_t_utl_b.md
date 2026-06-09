# tlx::istring_less_ordinal::operator()<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wchar_t,wchar_t,0>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)

- ea: `0x140008ce0`
- end: `0x140008d3d`
- name: `??$?RV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V01@_W_W$0A@@istring_less_ordinal@tlx@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0@Z`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002b6b0`
- `0x14002b7e0`

## callees

- `0x140008ce0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140008d2c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140008d2c`

## pseudocode

```c
bool __fastcall tlx::istring_less_ordinal::operator()<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wchar_t,wchar_t,0>(
        __int64 a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 v3; // r11
  __int64 v4; // r10
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // rcx
  __int64 v8; // r8

  v3 = *a2;
  v4 = *a3;
  v5 = (a2[1] - *a2) >> 1;
  v6 = (a3[1] - *a3) >> 1;
  if ( (v5 | (unsigned __int64)v6) > 0x7FFFFFFF )
    __int2c();
  v7 = 2;
  v8 = 2;
  if ( v4 )
    v8 = v4;
  if ( v3 )
    v7 = v3;
  return CompareStringOrdinal((LPCWCH)v7, v5, (LPCWCH)v8, v6, 1) == 1;
}

```

## disassembly

```asm
0x140008ce0  sub     rsp, 38h
0x140008ce4  mov     r11, [rdx]
0x140008ce7  mov     rdx, [rdx+8]
0x140008ceb  mov     r10, [r8]
0x140008cee  sub     rdx, r11
0x140008cf1  mov     r9, [r8+8]
0x140008cf5  sub     r9, r10
0x140008cf8  sar     rdx, 1; cchCount1
0x140008cfb  sar     r9, 1; cchCount2
0x140008cfe  mov     rax, r9
0x140008d01  or      rax, rdx
0x140008d04  cmp     rax, 7FFFFFFFh
0x140008d0a  jbe     short loc_140008D0E
0x140008d0c  int     2Ch; Windows NT - assertion failure
0x140008d0e  test    r10, r10
0x140008d11  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x140008d19  mov     ecx, 2
0x140008d1e  mov     r8d, ecx
0x140008d21  cmovnz  r8, r10; lpString2
0x140008d25  test    r11, r11
0x140008d28  cmovnz  rcx, r11; lpString1
0x140008d2c  call    cs:__imp_CompareStringOrdinal
0x140008d32  cmp     eax, 1
0x140008d35  setz    al
0x140008d38  add     rsp, 38h
0x140008d3c  retn
```
