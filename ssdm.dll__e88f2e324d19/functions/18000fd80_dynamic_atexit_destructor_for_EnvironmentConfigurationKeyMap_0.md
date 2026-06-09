# _dynamic_atexit_destructor_for__EnvironmentConfigurationKeyMap___0

- ea: `0x18000fd80`
- end: `0x18000fd9c`
- name: `_dynamic_atexit_destructor_for__EnvironmentConfigurationKeyMap___0`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002da0`

## pseudocode

```c
void dynamic_atexit_destructor_for__EnvironmentConfigurationKeyMap___0()
{
  `eh vector destructor iterator'(qword_18001FBA0, 0x20u, 8u, std::wstring::~wstring);
}

```

## disassembly

```asm
0x18000fd80  mov     edx, 20h ; ' '; unsigned __int64
0x18000fd85  lea     r9, ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; void (*)(void *)
0x18000fd8c  lea     rcx, qword_18001FBA0; void *
0x18000fd93  lea     r8d, [rdx-18h]; unsigned __int64
0x18000fd97  jmp     ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
```
