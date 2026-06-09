# _dynamic_initializer_for__Brain::_filenameDefaultAppManifest__

- ea: `0x180002300`
- end: `0x18000232d`
- name: `_dynamic_initializer_for__Brain::_filenameDefaultAppManifest__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180029518`
- `0x180042ba4`

## string_xrefs

- `0x18000230a`: `app.manifest`

## pseudocode

```c
int dynamic_initializer_for__Brain::_filenameDefaultAppManifest__()
{
  std::wstring::_Construct<1,wchar_t const *>(&Brain::_filenameDefaultAppManifest, L"app.manifest");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Brain::_filenameDefaultAppManifest__);
}

```

## disassembly

```asm
0x180002300  sub     rsp, 28h
0x180002304  mov     r8d, 0Ch
0x18000230a  lea     rdx, aAppManifest; "app.manifest"
0x180002311  lea     rcx, ?_filenameDefaultAppManifest@Brain@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Brain::_filenameDefaultAppManifest
0x180002318  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000231d  lea     rcx, _dynamic_atexit_destructor_for__Brain___filenameDefaultAppManifest__
0x180002324  add     rsp, 28h
0x180002328  jmp     atexit
```
