# Registry::~Registry(void)

- ea: `0x18000c93d`
- end: `0x18000c943`
- name: `??1Registry@@QEAA@XZ_0`
- size: `6`
- prototype: `void __fastcall(Registry *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `wbemcomn!??1Registry@@QEAA@XZ` at `0x18000c93d`

## pseudocode

```c
// attributes: thunk
void __fastcall Registry::~Registry(Registry *this)
{
  __imp_??1Registry@@QEAA@XZ(this);
}

```

## disassembly

```asm
0x18000c93d  jmp     cs:__imp_??1Registry@@QEAA@XZ
```
