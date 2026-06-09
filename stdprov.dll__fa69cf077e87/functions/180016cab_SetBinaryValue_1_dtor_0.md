# _SetBinaryValue_::_1_::dtor$0

- ea: `0x180016cab`
- end: `0x180016cb9`
- name: `_SetBinaryValue_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180016cb2`

## pseudocode

```c
void __fastcall SetBinaryValue_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Registry::~Registry((Registry *)(a2 + 104));
}

```

## disassembly

```asm
0x180016cab  lea     rcx, [rdx+68h]
0x180016cb2  jmp     cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
```
