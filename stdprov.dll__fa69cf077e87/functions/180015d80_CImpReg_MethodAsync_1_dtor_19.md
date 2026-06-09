# _CImpReg::MethodAsync_::_1_::dtor$19

- ea: `0x180015d80`
- end: `0x180015d8e`
- name: `_CImpReg::MethodAsync_::_1_::dtor$19`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `wbemcomn!??1Registry@@QEAA@XZ` at `0x180015d87`

## pseudocode

```c
void __fastcall CImpReg::MethodAsync_::_1_::dtor_19(__int64 a1, __int64 a2)
{
  Registry::~Registry((Registry *)(a2 + 304));
}

```

## disassembly

```asm
0x180015d80  lea     rcx, [rdx+130h]
0x180015d87  jmp     cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
```
