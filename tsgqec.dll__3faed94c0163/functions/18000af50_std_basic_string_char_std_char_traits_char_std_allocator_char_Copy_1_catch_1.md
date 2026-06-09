# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000af50`
- end: `0x18000af94`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001344`
- `0x180001518`
- `0x180001678`
- `0x18000af50`

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
  return &loc_1800015A1;
}

```

## disassembly

```asm
0x18000af50  mov     [rsp+arg_8], rdx
0x18000af55  push    rbp
0x18000af56  sub     rsp, 20h
0x18000af5a  mov     rbp, rdx
0x18000af5d  mov     rcx, [rbp+68h]
0x18000af61  mov     [rbp+68h], rcx
0x18000af65  xor     eax, eax
0x18000af67  add     rcx, 1; Size
0x18000af6b  jz      short loc_18000AF82
0x18000af6d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000af71  ja      short loc_18000AF7D
0x18000af73  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000af78  test    rax, rax
0x18000af7b  jnz     short loc_18000AF82
0x18000af7d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000af82  mov     [rbp+78h], rax
0x18000af86  lea     rax, loc_1800015A1
0x18000af8d  add     rsp, 20h
0x18000af91  pop     rbp
0x18000af92  retn
```
