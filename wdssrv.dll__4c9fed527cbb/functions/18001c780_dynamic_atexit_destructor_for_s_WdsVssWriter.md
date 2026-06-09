# _dynamic_atexit_destructor_for__s_WdsVssWriter__

- ea: `0x18001c780`
- end: `0x18001c78e`
- name: `_dynamic_atexit_destructor_for__s_WdsVssWriter__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `VSSAPI!??1CVssJetWriter@@UEAA@XZ` at `0x18001c787`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_WdsVssWriter__()
{
  CVssJetWriter::~CVssJetWriter((CVssJetWriter *)&off_180028160);
}

```

## disassembly

```asm
0x18001c780  lea     rcx, off_180028160
0x18001c787  jmp     cs:__imp_??1CVssJetWriter@@UEAA@XZ; CVssJetWriter::~CVssJetWriter(void)
```
