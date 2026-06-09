# __dynamic_initializer_for__EnvironmentConfigurationKeyMap___::_1_::dtor$3_0

- ea: `0x18000f3a3`
- end: `0x18000f3af`
- name: `__dynamic_initializer_for__EnvironmentConfigurationKeyMap___::_1_::dtor$3_0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004660`

## pseudocode

```c
void _dynamic_initializer_for__EnvironmentConfigurationKeyMap___::_1_::dtor_3_0()
{
  std::wstring::~wstring(qword_18001FC00);
}

```

## disassembly

```asm
0x18000f3a3  lea     rcx, qword_18001FC00; void *
0x18000f3aa  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
