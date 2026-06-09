# _dynamic_initializer_for__UusExclusion::_subdirOneSettingsRoot__

- ea: `0x180001bc0`
- end: `0x180001bed`
- name: `_dynamic_initializer_for__UusExclusion::_subdirOneSettingsRoot__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180029518`
- `0x180042ba4`

## string_xrefs

- `0x180001bca`: `%ProgramData%\Microsoft\Windows\OneSettings`

## pseudocode

```c
int dynamic_initializer_for__UusExclusion::_subdirOneSettingsRoot__()
{
  std::wstring::_Construct<1,wchar_t const *>(
    &UusExclusion::_subdirOneSettingsRoot,
    L"%ProgramData%\\Microsoft\\Windows\\OneSettings",
    0x2Bu);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__UusExclusion::_subdirOneSettingsRoot__);
}

```

## disassembly

```asm
0x180001bc0  sub     rsp, 28h
0x180001bc4  mov     r8d, 2Bh ; '+'
0x180001bca  lea     rdx, aProgramdataMic_0; "%ProgramData%\\Microsoft\\Windows\\OneS"...
0x180001bd1  lea     rcx, ?_subdirOneSettingsRoot@UusExclusion@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusExclusion::_subdirOneSettingsRoot
0x180001bd8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180001bdd  lea     rcx, _dynamic_atexit_destructor_for__UusExclusion___subdirOneSettingsRoot__
0x180001be4  add     rsp, 28h
0x180001be8  jmp     atexit
```
