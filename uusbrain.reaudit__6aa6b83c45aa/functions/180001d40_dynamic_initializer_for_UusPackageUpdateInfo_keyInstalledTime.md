# _dynamic_initializer_for__UusPackageUpdateInfo::_keyInstalledTime__

- ea: `0x180001d40`
- end: `0x180001d6d`
- name: `_dynamic_initializer_for__UusPackageUpdateInfo::_keyInstalledTime__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180029518`
- `0x180042ba4`

## string_xrefs

- `0x180001d4a`: `InstalledTime`

## pseudocode

```c
int dynamic_initializer_for__UusPackageUpdateInfo::_keyInstalledTime__()
{
  std::wstring::_Construct<1,wchar_t const *>(UusPackageUpdateInfo::_keyInstalledTime, L"InstalledTime");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__UusPackageUpdateInfo::_keyInstalledTime__);
}

```

## disassembly

```asm
0x180001d40  sub     rsp, 28h
0x180001d44  mov     r8d, 0Dh
0x180001d4a  lea     rdx, aInstalledtime; "InstalledTime"
0x180001d51  lea     rcx, ?_keyInstalledTime@UusPackageUpdateInfo@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackageUpdateInfo::_keyInstalledTime
0x180001d58  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180001d5d  lea     rcx, _dynamic_atexit_destructor_for__UusPackageUpdateInfo___keyInstalledTime__
0x180001d64  add     rsp, 28h
0x180001d68  jmp     atexit
```
