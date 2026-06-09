# _std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0

- ea: `0x14000ad88`
- end: `0x14000adae`
- name: `_std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000877c`
- `0x14000ad88`

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
0x14000ad88  push    rbp
0x14000ad8a  sub     rsp, 20h
0x14000ad8e  mov     rbp, rdx
0x14000ad91  mov     eax, [rbp+30h]
0x14000ad94  and     eax, 1
0x14000ad97  test    eax, eax
0x14000ad99  jz      short loc_14000ADA8
0x14000ad9b  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x14000ad9f  mov     rcx, [rbp+70h]
0x14000ada3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000ada8  add     rsp, 20h
0x14000adac  pop     rbp
0x14000adad  retn
```
