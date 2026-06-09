# __dynamic_initializer_for__EnvironmentConfigurationKeyMap___::_1_::dtor$2

- ea: `0x18000f02b`
- end: `0x18000f037`
- name: `__dynamic_initializer_for__EnvironmentConfigurationKeyMap___::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004660`

## pseudocode

```c
void _dynamic_initializer_for__EnvironmentConfigurationKeyMap___::_1_::dtor_2()
{
  std::wstring::~wstring(qword_18001FAA0);
}

```

## disassembly

```asm
0x18000f02b  lea     rcx, qword_18001FAA0; void *
0x18000f032  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
