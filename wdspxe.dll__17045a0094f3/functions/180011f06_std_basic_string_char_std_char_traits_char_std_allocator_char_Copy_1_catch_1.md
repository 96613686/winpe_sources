# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180011f06`
- end: `0x180011f4a`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001fd4`
- `0x1800021a8`
- `0x180002308`
- `0x180011f06`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  size_t v5; // rcx

  v3 = *(_QWORD *)(a2 + 104);
  *(_QWORD *)(a2 + 104) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    v4 = operator new(v5);
    if ( !v4 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)(a2 + 120) = v4;
  return &loc_180002231;
}

```

## disassembly

```asm
0x180011f06  mov     [rsp+arg_8], rdx
0x180011f0b  push    rbp
0x180011f0c  sub     rsp, 20h
0x180011f10  mov     rbp, rdx
0x180011f13  mov     rcx, [rbp+68h]
0x180011f17  mov     [rbp+68h], rcx
0x180011f1b  xor     eax, eax
0x180011f1d  add     rcx, 1; Size
0x180011f21  jz      short loc_180011F38
0x180011f23  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180011f27  ja      short loc_180011F33
0x180011f29  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011f2e  test    rax, rax
0x180011f31  jnz     short loc_180011F38
0x180011f33  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180011f38  mov     [rbp+78h], rax
0x180011f3c  lea     rax, loc_180002231
0x180011f43  add     rsp, 20h
0x180011f47  pop     rbp
0x180011f48  retn
```
