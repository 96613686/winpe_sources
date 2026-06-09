# _SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration_::_1_::dtor$4

- ea: `0x18000f0cf`
- end: `0x18000f0db`
- name: `_SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180004660`

## pseudocode

```c
void __fastcall SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration_::_1_::dtor_4(
        __int64 a1,
        __int64 a2)
{
  std::wstring::~wstring((void *)(a2 + 128));
}

```

## disassembly

```asm
0x18000f0cf  lea     rcx, [rdx+80h]; void *
0x18000f0d6  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
