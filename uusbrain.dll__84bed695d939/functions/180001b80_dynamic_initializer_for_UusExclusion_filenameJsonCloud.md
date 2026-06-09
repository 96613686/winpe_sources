# _dynamic_initializer_for__UusExclusion::_filenameJsonCloud__

- ea: `0x180001b80`
- end: `0x180001bad`
- name: `_dynamic_initializer_for__UusExclusion::_filenameJsonCloud__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180029518`
- `0x180042ba4`

## string_xrefs

- `0x180001b8a`: `UusSettings.json`

## pseudocode

```c
int dynamic_initializer_for__UusExclusion::_filenameJsonCloud__()
{
  std::wstring::_Construct<1,wchar_t const *>(&UusExclusion::_filenameJsonCloud, L"UusSettings.json", 0x10u);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__UusExclusion::_filenameJsonCloud__);
}

```

## disassembly

```asm
0x180001b80  sub     rsp, 28h
0x180001b84  mov     r8d, 10h
0x180001b8a  lea     rdx, aUussettingsJso; "UusSettings.json"
0x180001b91  lea     rcx, ?_filenameJsonCloud@UusExclusion@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusExclusion::_filenameJsonCloud
0x180001b98  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180001b9d  lea     rcx, _dynamic_atexit_destructor_for__UusExclusion___filenameJsonCloud__
0x180001ba4  add     rsp, 28h
0x180001ba8  jmp     atexit
```
