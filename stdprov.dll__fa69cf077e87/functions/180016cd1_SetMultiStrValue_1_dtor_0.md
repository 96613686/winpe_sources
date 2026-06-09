# _SetMultiStrValue_::_1_::dtor$0

- ea: `0x180016cd1`
- end: `0x180016cdf`
- name: `_SetMultiStrValue_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180016cd8`

## pseudocode

```c
void __fastcall SetMultiStrValue_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Registry::~Registry((Registry *)(a2 + 112));
}

```

## disassembly

```asm
0x180016cd1  lea     rcx, [rdx+70h]
0x180016cd8  jmp     cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
```
