# _std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0

- ea: `0x18000e5f0`
- end: `0x18000e616`
- name: `_std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008aa0`
- `0x18000e5f0`

## pseudocode

```c
void __fastcall std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 48) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    std::string::~string(*(char ***)(a2 + 112));
  }
}

```

## disassembly

```asm
0x18000e5f0  push    rbp
0x18000e5f2  sub     rsp, 20h
0x18000e5f6  mov     rbp, rdx
0x18000e5f9  mov     eax, [rbp+30h]
0x18000e5fc  and     eax, 1
0x18000e5ff  test    eax, eax
0x18000e601  jz      short loc_18000E610
0x18000e603  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x18000e607  mov     rcx, [rbp+70h]
0x18000e60b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000e610  add     rsp, 20h
0x18000e614  pop     rbp
0x18000e615  retn
```
