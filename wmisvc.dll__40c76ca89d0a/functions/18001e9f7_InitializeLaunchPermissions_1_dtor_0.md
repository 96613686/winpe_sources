# _InitializeLaunchPermissions_::_1_::dtor$0

- ea: `0x18001e9f7`
- end: `0x18001ea05`
- name: `_InitializeLaunchPermissions_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18001e9fe`

## pseudocode

```c
void __fastcall InitializeLaunchPermissions_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Registry::~Registry((Registry *)(a2 + 152));
}

```

## disassembly

```asm
0x18001e9f7  lea     rcx, [rdx+98h]
0x18001e9fe  jmp     cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
```
