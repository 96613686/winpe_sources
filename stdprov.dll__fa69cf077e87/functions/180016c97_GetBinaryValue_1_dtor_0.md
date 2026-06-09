# _GetBinaryValue_::_1_::dtor$0

- ea: `0x180016c97`
- end: `0x180016ca5`
- name: `_GetBinaryValue_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180016c9e`

## pseudocode

```c
void __fastcall GetBinaryValue_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Registry::~Registry((Registry *)(a2 + 80));
}

```

## disassembly

```asm
0x180016c97  lea     rcx, [rdx+50h]
0x180016c9e  jmp     cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
```
