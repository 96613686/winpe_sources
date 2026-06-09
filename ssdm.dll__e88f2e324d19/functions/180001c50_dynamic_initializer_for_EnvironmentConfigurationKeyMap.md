# _dynamic_initializer_for__EnvironmentConfigurationKeyMap__

- ea: `0x180001c50`
- end: `0x180001d04`
- name: `_dynamic_initializer_for__EnvironmentConfigurationKeyMap__`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000274c`
- `0x18000424c`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
int dynamic_initializer_for__EnvironmentConfigurationKeyMap__()
{
  std::wstring::wstring(qword_18001FA60, L"ReverbSmall");
  std::wstring::wstring(qword_18001FA80, L"ReverbMedium");
  std::wstring::wstring(qword_18001FAA0, L"ReverbLarge");
  std::wstring::wstring(qword_18001FAC0, L"ReverbOutdoor");
  std::wstring::wstring(qword_18001FAE0, L"ReverbAverage");
  std::wstring::wstring(qword_18001FB00, L"ReverbDynamicShort");
  std::wstring::wstring(qword_18001FB20, L"ReverbDynamicMedium");
  std::wstring::wstring(qword_18001FB40, L"ReverbDynamicLong");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__EnvironmentConfigurationKeyMap__);
}

```

## disassembly

```asm
0x180001c50  sub     rsp, 28h
0x180001c54  lea     rdx, aReverbsmall; "ReverbSmall"
0x180001c5b  lea     rcx, qword_18001FA60; void *
0x180001c62  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180001c67  nop
0x180001c68  lea     rdx, aReverbmedium; "ReverbMedium"
0x180001c6f  lea     rcx, qword_18001FA80; void *
0x180001c76  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180001c7b  nop
0x180001c7c  lea     rdx, aReverblarge; "ReverbLarge"
0x180001c83  lea     rcx, qword_18001FAA0; void *
0x180001c8a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180001c8f  nop
0x180001c90  lea     rdx, aReverboutdoor; "ReverbOutdoor"
0x180001c97  lea     rcx, qword_18001FAC0; void *
0x180001c9e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180001ca3  nop
0x180001ca4  lea     rdx, aReverbaverage; "ReverbAverage"
0x180001cab  lea     rcx, qword_18001FAE0; void *
0x180001cb2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180001cb7  nop
0x180001cb8  lea     rdx, aReverbdynamics; "ReverbDynamicShort"
0x180001cbf  lea     rcx, qword_18001FB00; void *
0x180001cc6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180001ccb  nop
0x180001ccc  lea     rdx, aReverbdynamicm; "ReverbDynamicMedium"
0x180001cd3  lea     rcx, qword_18001FB20; void *
0x180001cda  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180001cdf  nop
0x180001ce0  lea     rdx, aReverbdynamicl; "ReverbDynamicLong"
0x180001ce7  lea     rcx, qword_18001FB40; void *
0x180001cee  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180001cf3  nop
0x180001cf4  lea     rcx, _dynamic_atexit_destructor_for__EnvironmentConfigurationKeyMap__
0x180001cfb  add     rsp, 28h
0x180001cff  jmp     atexit
```
