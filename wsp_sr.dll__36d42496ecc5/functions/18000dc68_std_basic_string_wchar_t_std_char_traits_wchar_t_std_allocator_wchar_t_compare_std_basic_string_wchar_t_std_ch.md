# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::compare(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18000dc68`
- end: `0x18000dc8f`
- name: `?compare@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAHAEBV12@@Z`
- size: `39`
- prototype: `int __fastcall(const wchar_t *, const wchar_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008a04`
- `0x180011e78`
- `0x1800148d8`

## callees

- `0x180007ec8`
- `0x18000dc68`

## pseudocode

```c
int __fastcall std::wstring::compare(const wchar_t *a1, const wchar_t *a2)
{
  size_t v2; // r9
  size_t v3; // rax

  v2 = *((_QWORD *)a2 + 2);
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const wchar_t **)a2;
  v3 = *((_QWORD *)a1 + 2);
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const wchar_t **)a1;
  return std::_Traits_compare<std::char_traits<wchar_t>>(a1, v3, a2, v2);
}

```

## disassembly

```asm
0x18000dc68  cmp     qword ptr [rdx+18h], 7
0x18000dc6d  mov     r9, [rdx+10h]
0x18000dc71  jbe     short loc_18000DC76
0x18000dc73  mov     rdx, [rdx]
0x18000dc76  cmp     qword ptr [rcx+18h], 7
0x18000dc7b  mov     rax, [rcx+10h]
0x18000dc7f  jbe     short loc_18000DC84
0x18000dc81  mov     rcx, [rcx]
0x18000dc84  mov     r8, rdx
0x18000dc87  mov     rdx, rax
0x18000dc8a  jmp     ??$_Traits_compare@U?$char_traits@_W@std@@@std@@YAHQEB_W_K01@Z; std::_Traits_compare<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
```
