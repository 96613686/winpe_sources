# _CImpReg::MethodAsync_::_1_::dtor$9

- ea: `0x180015c80`
- end: `0x180015c8e`
- name: `_CImpReg::MethodAsync_::_1_::dtor$9`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180015c87`

## pseudocode

```c
void __fastcall CImpReg::MethodAsync_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  Registry::~Registry((Registry *)(a2 + 120));
}

```

## disassembly

```asm
0x180015c80  lea     rcx, [rdx+78h]
0x180015c87  jmp     cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
```
