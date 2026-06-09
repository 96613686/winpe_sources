# _InitHotMofStuff_::_1_::dtor$0

- ea: `0x18001df74`
- end: `0x18001df82`
- name: `_InitHotMofStuff_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18001df7b`

## pseudocode

```c
void __fastcall InitHotMofStuff_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Registry::~Registry((Registry *)(a2 + 32));
}

```

## disassembly

```asm
0x18001df74  lea     rcx, [rdx+20h]
0x18001df7b  jmp     cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
```
