# std::_Traits_compare<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)

- ea: `0x180007ec8`
- end: `0x180007f0e`
- name: `??$_Traits_compare@U?$char_traits@_W@std@@@std@@YAHQEB_W_K01@Z`
- size: `70`
- prototype: `int __fastcall(const wchar_t *, size_t, const wchar_t *, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dc68`
- `0x18001c248`

## callees

- `0x180007ec8`
- `0x18000dc5c`

## pseudocode

```c
int __fastcall std::_Traits_compare<std::char_traits<wchar_t>>(
        const wchar_t *a1,
        size_t a2,
        const wchar_t *a3,
        size_t a4)
{
  size_t v5; // r8
  int result; // eax

  v5 = a4;
  if ( a4 >= a2 )
    v5 = a2;
  result = std::_WChar_traits<wchar_t>::compare(a1, a3, v5);
  if ( !result )
  {
    if ( a2 >= a4 )
      return a2 > a4;
    else
      return -1;
  }
  return result;
}

```

## disassembly

```asm
0x180007ec8  mov     [rsp+arg_0], rbx
0x180007ecd  push    rdi
0x180007ece  sub     rsp, 20h
0x180007ed2  mov     rax, r8
0x180007ed5  cmp     r9, rdx
0x180007ed8  mov     r8, r9
0x180007edb  mov     rdi, rdx
0x180007ede  cmovnb  r8, rdx; N
0x180007ee2  mov     rbx, r9
0x180007ee5  mov     rdx, rax; S2
0x180007ee8  call    ?compare@?$_WChar_traits@_W@std@@SAHQEB_W0_K@Z; std::_WChar_traits<wchar_t>::compare(wchar_t const * const,wchar_t const * const,unsigned __int64)
0x180007eed  test    eax, eax
0x180007eef  jnz     short loc_180007F03
0x180007ef1  cmp     rdi, rbx
0x180007ef4  jnb     short loc_180007EFB
0x180007ef6  or      eax, 0FFFFFFFFh
0x180007ef9  jmp     short loc_180007F03
0x180007efb  xor     eax, eax
0x180007efd  cmp     rdi, rbx
0x180007f00  setnbe  al
0x180007f03  mov     rbx, [rsp+28h+arg_0]
0x180007f08  add     rsp, 20h
0x180007f0c  pop     rdi
0x180007f0d  retn
```
