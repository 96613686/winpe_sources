# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180010326`
- end: `0x18001036a`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001ae8`
- `0x180001cc8`
- `0x180001e28`
- `0x180010326`

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
  return &loc_180001D51;
}

```

## disassembly

```asm
0x180010326  mov     [rsp+arg_8], rdx
0x18001032b  push    rbp
0x18001032c  sub     rsp, 20h
0x180010330  mov     rbp, rdx
0x180010333  mov     rcx, [rbp+68h]
0x180010337  mov     [rbp+68h], rcx
0x18001033b  xor     eax, eax
0x18001033d  add     rcx, 1; Size
0x180010341  jz      short loc_180010358
0x180010343  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180010347  ja      short loc_180010353
0x180010349  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001034e  test    rax, rax
0x180010351  jnz     short loc_180010358
0x180010353  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180010358  mov     [rbp+78h], rax
0x18001035c  lea     rax, loc_180001D51
0x180010363  add     rsp, 20h
0x180010367  pop     rbp
0x180010368  retn
```
