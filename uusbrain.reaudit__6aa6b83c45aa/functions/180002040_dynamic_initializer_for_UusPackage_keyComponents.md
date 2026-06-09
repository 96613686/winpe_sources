# _dynamic_initializer_for__UusPackage::_keyComponents__

- ea: `0x180002040`
- end: `0x18000206d`
- name: `_dynamic_initializer_for__UusPackage::_keyComponents__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180029518`
- `0x180042ba4`

## string_xrefs

- `0x18000204a`: `components`

## pseudocode

```c
int dynamic_initializer_for__UusPackage::_keyComponents__()
{
  std::wstring::_Construct<1,wchar_t const *>(UusPackage::_keyComponents, L"components");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__UusPackage::_keyComponents__);
}

```

## disassembly

```asm
0x180002040  sub     rsp, 28h
0x180002044  mov     r8d, 0Ah
0x18000204a  lea     rdx, aComponents; "components"
0x180002051  lea     rcx, ?_keyComponents@UusPackage@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackage::_keyComponents
0x180002058  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000205d  lea     rcx, _dynamic_atexit_destructor_for__UusPackage___keyComponents__
0x180002064  add     rsp, 28h
0x180002068  jmp     atexit
```
