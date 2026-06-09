# tlx::istring_less_ordinal::operator()<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,wchar_t,wchar_t,0>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x140023ffc`
- end: `0x14002406a`
- name: `??$?RV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V01@_W_W$0A@@istring_less_ordinal@tlx@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z`
- size: `110`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002421c`
- `0x14002787c`
- `0x140027900`

## callees

- `0x140022d2c`
- `0x140023ffc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140024059`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140024059`

## pseudocode

```c
bool __fastcall tlx::istring_less_ordinal::operator()<std::wstring,std::wstring,wchar_t,wchar_t,0>(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // r8
  const WCHAR *v3; // rcx
  const WCHAR *v4; // r8
  LPCWCH lpString2; // [rsp+30h] [rbp-28h] BYREF
  int cchCount2[2]; // [rsp+38h] [rbp-20h]
  LPCWCH lpString1; // [rsp+40h] [rbp-18h] BYREF
  int cchCount1[4]; // [rsp+48h] [rbp-10h]

  tlx::_CharSpan<wchar_t const>::_CharSpan<wchar_t const>(&lpString1, a2);
  tlx::_CharSpan<wchar_t const>::_CharSpan<wchar_t const>(&lpString2, v2);
  if ( (*(_QWORD *)cchCount1 | *(_QWORD *)cchCount2) > 0x7FFFFFFF )
    __int2c();
  v3 = (const WCHAR *)2;
  v4 = (const WCHAR *)2;
  if ( lpString2 )
    v4 = lpString2;
  if ( lpString1 )
    v3 = lpString1;
  return CompareStringOrdinal(v3, cchCount1[0], v4, cchCount2[0], 1) == 1;
}

```

## disassembly

```asm
0x140023ffc  sub     rsp, 58h
0x140024000  lea     rcx, [rsp+58h+lpString1]
0x140024005  call    ??$?0$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@?$_CharSpan@$$CB_W@tlx@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; tlx::_CharSpan<wchar_t const>::_CharSpan<wchar_t const>(std::wstring const &)
0x14002400a  mov     rdx, r8
0x14002400d  lea     rcx, [rsp+58h+lpString2]
0x140024012  call    ??$?0$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@?$_CharSpan@$$CB_W@tlx@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; tlx::_CharSpan<wchar_t const>::_CharSpan<wchar_t const>(std::wstring const &)
0x140024017  mov     r9, qword ptr [rsp+58h+cchCount2]; cchCount2
0x14002401c  mov     rdx, qword ptr [rsp+58h+cchCount1]; cchCount1
0x140024021  mov     rax, r9
0x140024024  or      rax, rdx
0x140024027  cmp     rax, 7FFFFFFFh
0x14002402d  jbe     short loc_140024031
0x14002402f  int     2Ch; Windows NT - assertion failure
0x140024031  mov     rax, [rsp+58h+lpString2]
0x140024036  mov     ecx, 2
0x14002403b  test    rax, rax
0x14002403e  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x140024046  mov     r8d, ecx
0x140024049  cmovnz  r8, rax; lpString2
0x14002404d  mov     rax, [rsp+58h+lpString1]
0x140024052  test    rax, rax
0x140024055  cmovnz  rcx, rax; lpString1
0x140024059  call    cs:__imp_CompareStringOrdinal
0x14002405f  cmp     eax, 1
0x140024062  setz    al
0x140024065  add     rsp, 58h
0x140024069  retn
```
