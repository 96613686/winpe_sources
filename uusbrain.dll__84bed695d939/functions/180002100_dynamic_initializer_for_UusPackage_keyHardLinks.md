# _dynamic_initializer_for__UusPackage::_keyHardLinks__

- ea: `0x180002100`
- end: `0x18000212d`
- name: `_dynamic_initializer_for__UusPackage::_keyHardLinks__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180029518`
- `0x180042ba4`

## string_xrefs

- `0x18000210a`: `hardLinks`

## pseudocode

```c
int dynamic_initializer_for__UusPackage::_keyHardLinks__()
{
  std::wstring::_Construct<1,wchar_t const *>(UusPackage::_keyHardLinks, L"hardLinks", 9u);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__UusPackage::_keyHardLinks__);
}

```

## disassembly

```asm
0x180002100  sub     rsp, 28h
0x180002104  mov     r8d, 9
0x18000210a  lea     rdx, aHardlinks; "hardLinks"
0x180002111  lea     rcx, ?_keyHardLinks@UusPackage@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackage::_keyHardLinks
0x180002118  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000211d  lea     rcx, _dynamic_atexit_destructor_for__UusPackage___keyHardLinks__
0x180002124  add     rsp, 28h
0x180002128  jmp     atexit
```
