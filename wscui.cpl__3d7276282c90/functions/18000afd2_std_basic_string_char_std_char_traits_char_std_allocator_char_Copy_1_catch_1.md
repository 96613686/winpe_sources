# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000afd2`
- end: `0x18000b006`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008098`

## pseudocode

```c
__int64 __fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a2 + 88);
  *(_QWORD *)(a2 + 88) = v2;
  *(_QWORD *)(a2 + 104) = std::_Allocate<char>(v2 + 1, 0);
  return 0;
}

```

## disassembly

```asm
0x18000afd2  mov     [rsp+arg_8], rdx
0x18000afd7  push    rbp
0x18000afd8  sub     rsp, 20h
0x18000afdc  mov     rbp, rdx
0x18000afdf  mov     rcx, [rbp+58h]
0x18000afe3  mov     [rbp+58h], rcx
0x18000afe7  inc     rcx
0x18000afea  xor     edx, edx
0x18000afec  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x18000aff1  mov     [rbp+68h], rax
0x18000aff5  mov     rax, 0
0x18000afff  add     rsp, 20h
0x18000b003  pop     rbp
0x18000b004  retn
```
