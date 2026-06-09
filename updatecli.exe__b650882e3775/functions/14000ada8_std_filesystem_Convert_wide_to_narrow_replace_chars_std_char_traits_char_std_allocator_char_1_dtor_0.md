# _std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0

- ea: `0x14000ada8`
- end: `0x14000adce`
- name: `_std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000875c`
- `0x14000ada8`

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
0x14000ada8  push    rbp
0x14000adaa  sub     rsp, 20h
0x14000adae  mov     rbp, rdx
0x14000adb1  mov     eax, [rbp+30h]
0x14000adb4  and     eax, 1
0x14000adb7  test    eax, eax
0x14000adb9  jz      short loc_14000ADC8
0x14000adbb  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x14000adbf  mov     rcx, [rbp+70h]
0x14000adc3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000adc8  add     rsp, 20h
0x14000adcc  pop     rbp
0x14000adcd  retn
```
