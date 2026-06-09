# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x1400078f6`
- end: `0x14000793a`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140001174`
- `0x140001318`
- `0x140006d2c`
- `0x1400078f6`

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
  return &loc_140006DB5;
}

```

## disassembly

```asm
0x1400078f6  mov     [rsp+arg_8], rdx
0x1400078fb  push    rbp
0x1400078fc  sub     rsp, 20h
0x140007900  mov     rbp, rdx
0x140007903  mov     rcx, [rbp+68h]
0x140007907  mov     [rbp+68h], rcx
0x14000790b  xor     eax, eax
0x14000790d  add     rcx, 1; Size
0x140007911  jz      short loc_140007928
0x140007913  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140007917  ja      short loc_140007923
0x140007919  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000791e  test    rax, rax
0x140007921  jnz     short loc_140007928
0x140007923  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140007928  mov     [rbp+78h], rax
0x14000792c  lea     rax, loc_140006DB5
0x140007933  add     rsp, 20h
0x140007937  pop     rbp
0x140007938  retn
```
