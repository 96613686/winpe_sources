# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x1800132f3`
- end: `0x180013337`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800019e4`
- `0x180001cc8`
- `0x180001e28`
- `0x1800132f3`

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
0x1800132f3  mov     [rsp+arg_8], rdx
0x1800132f8  push    rbp
0x1800132f9  sub     rsp, 20h
0x1800132fd  mov     rbp, rdx
0x180013300  mov     rcx, [rbp+68h]
0x180013304  mov     [rbp+68h], rcx
0x180013308  xor     eax, eax
0x18001330a  add     rcx, 1; Size
0x18001330e  jz      short loc_180013325
0x180013310  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180013314  ja      short loc_180013320
0x180013316  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001331b  test    rax, rax
0x18001331e  jnz     short loc_180013325
0x180013320  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180013325  mov     [rbp+78h], rax
0x180013329  lea     rax, loc_180001D51
0x180013330  add     rsp, 20h
0x180013334  pop     rbp
0x180013335  retn
```
