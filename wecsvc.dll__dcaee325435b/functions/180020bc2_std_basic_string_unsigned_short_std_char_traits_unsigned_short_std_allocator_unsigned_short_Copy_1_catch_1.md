# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x180020bc2`
- end: `0x180020c15`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001238`
- `0x180003430`
- `0x180020bc2`

## pseudocode

```c
__int64 __fastcall std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  LPVOID v4; // rax
  unsigned __int64 v5; // rcx

  v3 = *(_QWORD *)(a2 + 88);
  *(_QWORD *)(a2 + 88) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    if ( v5 > 0x7FFFFFFFFFFFFFFFLL || (v4 = operator new(2 * v5)) == 0 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)(a2 + 104) = v4;
  return 0;
}

```

## disassembly

```asm
0x180020bc2  mov     [rsp+arg_8], rdx
0x180020bc7  push    rbp
0x180020bc8  sub     rsp, 20h
0x180020bcc  mov     rbp, rdx
0x180020bcf  mov     rcx, [rbp+58h]
0x180020bd3  mov     [rbp+58h], rcx
0x180020bd7  xor     eax, eax
0x180020bd9  add     rcx, 1
0x180020bdd  jz      short loc_180020C00
0x180020bdf  mov     rax, 7FFFFFFFFFFFFFFFh
0x180020be9  cmp     rcx, rax
0x180020bec  ja      short loc_180020BFB
0x180020bee  add     rcx, rcx; dwBytes
0x180020bf1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020bf6  test    rax, rax
0x180020bf9  jnz     short loc_180020C00
0x180020bfb  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180020c00  mov     [rbp+68h], rax
0x180020c04  mov     rax, 0
0x180020c0e  add     rsp, 20h
0x180020c12  pop     rbp
0x180020c13  retn
```
