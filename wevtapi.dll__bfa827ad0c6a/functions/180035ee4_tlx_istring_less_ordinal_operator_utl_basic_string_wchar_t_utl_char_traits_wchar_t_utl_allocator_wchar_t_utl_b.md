# tlx::istring_less_ordinal::operator()<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wchar_t,wchar_t,0>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)

- ea: `0x180035ee4`
- end: `0x180035f41`
- name: `??$?RV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V01@_W_W$0A@@istring_less_ordinal@tlx@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@0@Z`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180038bd4`
- `0x180038d0c`

## callees

- `0x180035ee4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180035f30`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180035f30`

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
0x180035ee4  sub     rsp, 38h
0x180035ee8  mov     r11, [rdx]
0x180035eeb  mov     rdx, [rdx+8]
0x180035eef  mov     r10, [r8]
0x180035ef2  sub     rdx, r11
0x180035ef5  mov     r9, [r8+8]
0x180035ef9  sub     r9, r10
0x180035efc  sar     rdx, 1; cchCount1
0x180035eff  sar     r9, 1; cchCount2
0x180035f02  mov     rax, r9
0x180035f05  or      rax, rdx
0x180035f08  cmp     rax, 7FFFFFFFh
0x180035f0e  jbe     short loc_180035F12
0x180035f10  int     2Ch; Windows NT - assertion failure
0x180035f12  test    r10, r10
0x180035f15  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180035f1d  mov     ecx, 2
0x180035f22  mov     r8d, ecx
0x180035f25  cmovnz  r8, r10; lpString2
0x180035f29  test    r11, r11
0x180035f2c  cmovnz  rcx, r11; lpString1
0x180035f30  call    cs:__imp_CompareStringOrdinal
0x180035f36  cmp     eax, 1
0x180035f39  setz    al
0x180035f3c  add     rsp, 38h
0x180035f40  retn
```
