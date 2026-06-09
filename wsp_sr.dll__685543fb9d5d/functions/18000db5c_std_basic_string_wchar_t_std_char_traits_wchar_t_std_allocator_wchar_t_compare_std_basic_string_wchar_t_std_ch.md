# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::compare(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18000db5c`
- end: `0x18000db83`
- name: `?compare@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAHAEBV12@@Z`
- size: `39`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008b90`
- `0x180011d40`
- `0x18001478c`

## callees

- `0x180008000`
- `0x18000db5c`

## pseudocode

```c
__int64 __fastcall std::wstring::compare(_QWORD *a1, _QWORD *a2)
{
  __int64 v2; // r9
  __int64 v3; // rax

  v2 = a2[2];
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  v3 = a1[2];
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  return std::_Traits_compare<std::char_traits<wchar_t>>(a1, v3, a2, v2);
}

```

## disassembly

```asm
0x18000db5c  cmp     qword ptr [rdx+18h], 7
0x18000db61  mov     r9, [rdx+10h]
0x18000db65  jbe     short loc_18000DB6A
0x18000db67  mov     rdx, [rdx]
0x18000db6a  cmp     qword ptr [rcx+18h], 7
0x18000db6f  mov     rax, [rcx+10h]
0x18000db73  jbe     short loc_18000DB78
0x18000db75  mov     rcx, [rcx]
0x18000db78  mov     r8, rdx
0x18000db7b  mov     rdx, rax
0x18000db7e  jmp     ??$_Traits_compare@U?$char_traits@_W@std@@@std@@YAHQEB_W_K01@Z; std::_Traits_compare<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
```
