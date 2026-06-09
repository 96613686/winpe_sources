# _SetStringValue_::_1_::dtor$0

- ea: `0x180016cf7`
- end: `0x180016d05`
- name: `_SetStringValue_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180016cfe`

## pseudocode

```c
void __fastcall SetStringValue_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Registry::~Registry((Registry *)(a2 + 88));
}

```

## disassembly

```asm
0x180016cf7  lea     rcx, [rdx+58h]
0x180016cfe  jmp     cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
```
