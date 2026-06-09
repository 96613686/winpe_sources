# __dynamic_initializer_for__EnvironmentConfigurationKeyMap___::_1_::dtor$1_0

- ea: `0x18000f37f`
- end: `0x18000f38b`
- name: `__dynamic_initializer_for__EnvironmentConfigurationKeyMap___::_1_::dtor$1_0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004660`

## pseudocode

```c
void _dynamic_initializer_for__EnvironmentConfigurationKeyMap___::_1_::dtor_1_0()
{
  std::wstring::~wstring(qword_18001FBC0);
}

```

## disassembly

```asm
0x18000f37f  lea     rcx, qword_18001FBC0; void *
0x18000f386  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
