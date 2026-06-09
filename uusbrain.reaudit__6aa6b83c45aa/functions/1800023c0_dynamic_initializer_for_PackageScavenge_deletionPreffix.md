# _dynamic_initializer_for__PackageScavenge::_deletionPreffix__

- ea: `0x1800023c0`
- end: `0x1800023ed`
- name: `_dynamic_initializer_for__PackageScavenge::_deletionPreffix__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180029518`
- `0x180042ba4`

## string_xrefs

- `0x1800023ca`: `DELETE_`

## pseudocode

```c
int dynamic_initializer_for__PackageScavenge::_deletionPreffix__()
{
  std::wstring::_Construct<1,wchar_t const *>(&PackageScavenge::_deletionPreffix, L"DELETE_", 7);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__PackageScavenge::_deletionPreffix__);
}

```

## disassembly

```asm
0x1800023c0  sub     rsp, 28h
0x1800023c4  mov     r8d, 7
0x1800023ca  lea     rdx, aDelete; "DELETE_"
0x1800023d1  lea     rcx, ?_deletionPreffix@PackageScavenge@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const PackageScavenge::_deletionPreffix
0x1800023d8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800023dd  lea     rcx, _dynamic_atexit_destructor_for__PackageScavenge___deletionPreffix__
0x1800023e4  add     rsp, 28h
0x1800023e8  jmp     atexit
```
