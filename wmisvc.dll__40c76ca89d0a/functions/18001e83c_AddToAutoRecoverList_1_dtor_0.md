# _AddToAutoRecoverList_::_1_::dtor$0

- ea: `0x18001e83c`
- end: `0x18001e84a`
- name: `_AddToAutoRecoverList_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18001e843`

## pseudocode

```c
void __fastcall AddToAutoRecoverList_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Registry::~Registry((Registry *)(a2 + 88));
}

```

## disassembly

```asm
0x18001e83c  lea     rcx, [rdx+58h]
0x18001e843  jmp     cs:__imp_??1Registry@@QEAA@XZ; Registry::~Registry(void)
```
