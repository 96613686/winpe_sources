# _std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0

- ea: `0x180016228`
- end: `0x18001624e`
- name: `_std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007b40`
- `0x180016228`

## pseudocode

```c
void __fastcall std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 48) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    std::string::~string(*(_QWORD *)(a2 + 112));
  }
}

```

## disassembly

```asm
0x180016228  push    rbp
0x18001622a  sub     rsp, 20h
0x18001622e  mov     rbp, rdx
0x180016231  mov     eax, [rbp+30h]
0x180016234  and     eax, 1
0x180016237  test    eax, eax
0x180016239  jz      short loc_180016248
0x18001623b  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x18001623f  mov     rcx, [rbp+70h]
0x180016243  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180016248  add     rsp, 20h
0x18001624c  pop     rbp
0x18001624d  retn
```
