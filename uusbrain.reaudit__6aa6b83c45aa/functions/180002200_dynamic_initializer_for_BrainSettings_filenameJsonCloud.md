# _dynamic_initializer_for__BrainSettings::_filenameJsonCloud__

- ea: `0x180002200`
- end: `0x18000222d`
- name: `_dynamic_initializer_for__BrainSettings::_filenameJsonCloud__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180029518`
- `0x180042ba4`

## string_xrefs

- `0x18000220a`: `UusSettings.json`

## pseudocode

```c
int dynamic_initializer_for__BrainSettings::_filenameJsonCloud__()
{
  std::wstring::_Construct<1,wchar_t const *>(&BrainSettings::_filenameJsonCloud, L"UusSettings.json");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__BrainSettings::_filenameJsonCloud__);
}

```

## disassembly

```asm
0x180002200  sub     rsp, 28h
0x180002204  mov     r8d, 10h
0x18000220a  lea     rdx, aUussettingsJso; "UusSettings.json"
0x180002211  lea     rcx, ?_filenameJsonCloud@BrainSettings@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const BrainSettings::_filenameJsonCloud
0x180002218  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000221d  lea     rcx, _dynamic_atexit_destructor_for__BrainSettings___filenameJsonCloud__
0x180002224  add     rsp, 28h
0x180002228  jmp     atexit
```
