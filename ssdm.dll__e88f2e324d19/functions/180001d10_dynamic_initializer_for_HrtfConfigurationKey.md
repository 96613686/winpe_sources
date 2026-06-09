# _dynamic_initializer_for__HrtfConfigurationKey__

- ea: `0x180001d10`
- end: `0x180001d37`
- name: `_dynamic_initializer_for__HrtfConfigurationKey__`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000274c`
- `0x18000424c`

## pseudocode

```c
int dynamic_initializer_for__HrtfConfigurationKey__()
{
  std::wstring::wstring(&qword_18001FB60, L"Hrtf");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__HrtfConfigurationKey__);
}

```

## disassembly

```asm
0x180001d10  sub     rsp, 28h
0x180001d14  lea     rdx, aHrtf; "Hrtf"
0x180001d1b  lea     rcx, qword_18001FB60; void *
0x180001d22  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180001d27  lea     rcx, _dynamic_atexit_destructor_for__HrtfConfigurationKey__
0x180001d2e  add     rsp, 28h
0x180001d32  jmp     atexit
```
