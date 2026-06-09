# _std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0

- ea: `0x1800168e6`
- end: `0x18001690c`
- name: `_std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007ee8`
- `0x1800168e6`

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
0x1800168e6  push    rbp
0x1800168e8  sub     rsp, 20h
0x1800168ec  mov     rbp, rdx
0x1800168ef  mov     eax, [rbp+30h]
0x1800168f2  and     eax, 1
0x1800168f5  test    eax, eax
0x1800168f7  jz      short loc_180016906
0x1800168f9  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x1800168fd  mov     rcx, [rbp+70h]
0x180016901  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180016906  add     rsp, 20h
0x18001690a  pop     rbp
0x18001690b  retn
```
