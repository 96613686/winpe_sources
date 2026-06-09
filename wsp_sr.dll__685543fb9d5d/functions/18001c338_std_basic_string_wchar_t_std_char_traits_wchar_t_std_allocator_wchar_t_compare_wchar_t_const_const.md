# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::compare(wchar_t const * const)

- ea: `0x18001c338`
- end: `0x18001c36a`
- name: `?compare@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAHQEB_W@Z`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a934`

## callees

- `0x180006794`
- `0x180008000`
- `0x18001c338`

## pseudocode

```c
int __fastcall std::wstring::compare(__int64 a1, __int64 a2)
{
  size_t v2; // rax
  const wchar_t *v3; // rdx
  const wchar_t *v4; // r10
  size_t v5; // rcx

  v2 = std::_WChar_traits<wchar_t>::length(a2);
  v5 = *((_QWORD *)v4 + 2);
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(const wchar_t **)v4;
  return std::_Traits_compare<std::char_traits<wchar_t>>(v4, v5, v3, v2);
}

```

## disassembly

```asm
0x18001c338  sub     rsp, 28h
0x18001c33c  mov     r10, rcx
0x18001c33f  mov     rcx, rdx
0x18001c342  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x18001c347  cmp     qword ptr [r10+18h], 7
0x18001c34c  mov     rcx, [r10+10h]
0x18001c350  jbe     short loc_18001C355
0x18001c352  mov     r10, [r10]
0x18001c355  mov     r8, rdx
0x18001c358  mov     r9, rax
0x18001c35b  mov     rdx, rcx
0x18001c35e  mov     rcx, r10
0x18001c361  add     rsp, 28h
0x18001c365  jmp     ??$_Traits_compare@U?$char_traits@_W@std@@@std@@YAHQEB_W_K01@Z; std::_Traits_compare<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
```
