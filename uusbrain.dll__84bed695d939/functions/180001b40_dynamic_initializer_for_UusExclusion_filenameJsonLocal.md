# _dynamic_initializer_for__UusExclusion::_filenameJsonLocal__

- ea: `0x180001b40`
- end: `0x180001b6d`
- name: `_dynamic_initializer_for__UusExclusion::_filenameJsonLocal__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180029518`
- `0x180042ba4`

## string_xrefs

- `0x180001b4a`: `uus-exclusion.json`

## pseudocode

```c
int dynamic_initializer_for__UusExclusion::_filenameJsonLocal__()
{
  std::wstring::_Construct<1,wchar_t const *>(&UusExclusion::_filenameJsonLocal, L"uus-exclusion.json", 0x12u);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__UusExclusion::_filenameJsonLocal__);
}

```

## disassembly

```asm
0x180001b40  sub     rsp, 28h
0x180001b44  mov     r8d, 12h
0x180001b4a  lea     rdx, aUusExclusionJs; "uus-exclusion.json"
0x180001b51  lea     rcx, ?_filenameJsonLocal@UusExclusion@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusExclusion::_filenameJsonLocal
0x180001b58  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180001b5d  lea     rcx, _dynamic_atexit_destructor_for__UusExclusion___filenameJsonLocal__
0x180001b64  add     rsp, 28h
0x180001b68  jmp     atexit
```
