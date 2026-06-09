# _std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0

- ea: `0x180016b32`
- end: `0x180016b58`
- name: `_std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008664`
- `0x180016b32`

## pseudocode

```c
__int64 __fastcall std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 48) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    return std::string::~string(*(_QWORD *)(a2 + 112));
  }
  return result;
}

```

## disassembly

```asm
0x180016b32  push    rbp
0x180016b34  sub     rsp, 20h
0x180016b38  mov     rbp, rdx
0x180016b3b  mov     eax, [rbp+30h]
0x180016b3e  and     eax, 1
0x180016b41  test    eax, eax
0x180016b43  jz      short loc_180016B52
0x180016b45  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x180016b49  mov     rcx, [rbp+70h]
0x180016b4d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180016b52  add     rsp, 20h
0x180016b56  pop     rbp
0x180016b57  retn
```
