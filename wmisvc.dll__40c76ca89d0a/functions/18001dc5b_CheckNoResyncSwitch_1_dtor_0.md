# _CheckNoResyncSwitch_::_1_::dtor$0

- ea: `0x18001dc5b`
- end: `0x18001dc69`
- name: `_CheckNoResyncSwitch_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18001dc62`

## pseudocode

```c
void __fastcall CheckNoResyncSwitch_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Registry::~Registry((Registry *)(a2 + 56));
}

```

## disassembly

```asm
0x18001dc5b  lea     rcx, [rdx+38h]
0x18001dc62  jmp     cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
```
