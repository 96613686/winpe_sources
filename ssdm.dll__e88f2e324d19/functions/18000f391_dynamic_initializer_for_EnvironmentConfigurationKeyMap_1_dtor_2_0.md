# __dynamic_initializer_for__EnvironmentConfigurationKeyMap___::_1_::dtor$2_0

- ea: `0x18000f391`
- end: `0x18000f39d`
- name: `__dynamic_initializer_for__EnvironmentConfigurationKeyMap___::_1_::dtor$2_0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004660`

## pseudocode

```c
void _dynamic_initializer_for__EnvironmentConfigurationKeyMap___::_1_::dtor_2_0()
{
  std::wstring::~wstring(qword_18001FBE0);
}

```

## disassembly

```asm
0x18000f391  lea     rcx, qword_18001FBE0; void *
0x18000f398  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
