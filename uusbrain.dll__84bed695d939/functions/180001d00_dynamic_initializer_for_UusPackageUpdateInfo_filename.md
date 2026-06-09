# _dynamic_initializer_for__UusPackageUpdateInfo::_filename__

- ea: `0x180001d00`
- end: `0x180001d2d`
- name: `_dynamic_initializer_for__UusPackageUpdateInfo::_filename__`
- size: `45`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180029518`
- `0x180042ba4`

## string_xrefs

- `0x180001d0a`: `update.json`

## pseudocode

```c
int dynamic_initializer_for__UusPackageUpdateInfo::_filename__()
{
  std::wstring::_Construct<1,wchar_t const *>(&UusPackageUpdateInfo::_filename, L"update.json", 11);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__UusPackageUpdateInfo::_filename__);
}

```

## disassembly

```asm
0x180001d00  sub     rsp, 28h
0x180001d04  mov     r8d, 0Bh
0x180001d0a  lea     rdx, aUpdateJson; "update.json"
0x180001d11  lea     rcx, ?_filename@UusPackageUpdateInfo@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackageUpdateInfo::_filename
0x180001d18  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180001d1d  lea     rcx, _dynamic_atexit_destructor_for__UusPackageUpdateInfo___filename__
0x180001d24  add     rsp, 28h
0x180001d28  jmp     atexit
```
