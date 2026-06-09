# std::_Traits_compare<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)

- ea: `0x180008000`
- end: `0x180008047`
- name: `??$_Traits_compare@U?$char_traits@_W@std@@@std@@YAHQEB_W_K01@Z`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000db5c`
- `0x18001c338`

## callees

- `0x180008000`
- `0x18000db50`

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
0x180008000  mov     [rsp+arg_0], rbx
0x180008005  push    rdi
0x180008006  sub     rsp, 20h
0x18000800a  mov     rax, r8
0x18000800d  cmp     r9, rdx
0x180008010  mov     r8, r9
0x180008013  mov     rdi, rdx
0x180008016  cmovnb  r8, rdx; N
0x18000801a  mov     rbx, r9
0x18000801d  mov     rdx, rax; S2
0x180008020  call    ?compare@?$_WChar_traits@_W@std@@SAHQEB_W0_K@Z; std::_WChar_traits<wchar_t>::compare(wchar_t const * const,wchar_t const * const,unsigned __int64)
0x180008025  test    eax, eax
0x180008027  jnz     short loc_18000803B
0x180008029  cmp     rdi, rbx
0x18000802c  jnb     short loc_180008033
0x18000802e  or      eax, 0FFFFFFFFh
0x180008031  jmp     short loc_18000803B
0x180008033  xor     eax, eax
0x180008035  cmp     rdi, rbx
0x180008038  setnbe  al
0x18000803b  mov     rbx, [rsp+28h+arg_0]
0x180008040  add     rsp, 20h
0x180008044  pop     rdi
0x180008045  retn
```
