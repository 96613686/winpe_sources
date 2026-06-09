# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180003c20`
- end: `0x180003c64`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001064`
- `0x180001238`
- `0x180001398`
- `0x180003c20`

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
  return &loc_1800012C1;
}

```

## disassembly

```asm
0x180003c20  mov     [rsp+arg_8], rdx
0x180003c25  push    rbp
0x180003c26  sub     rsp, 20h
0x180003c2a  mov     rbp, rdx
0x180003c2d  mov     rcx, [rbp+68h]
0x180003c31  mov     [rbp+68h], rcx
0x180003c35  xor     eax, eax
0x180003c37  add     rcx, 1; Size
0x180003c3b  jz      short loc_180003C52
0x180003c3d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180003c41  ja      short loc_180003C4D
0x180003c43  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003c48  test    rax, rax
0x180003c4b  jnz     short loc_180003C52
0x180003c4d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180003c52  mov     [rbp+78h], rax
0x180003c56  lea     rax, loc_1800012C1
0x180003c5d  add     rsp, 20h
0x180003c61  pop     rbp
0x180003c62  retn
```
