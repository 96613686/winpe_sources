# CVssJetWriter::OnPrepareSnapshotBegin(void)

- ea: `0x180001f60`
- end: `0x180001f66`
- name: `?OnPrepareSnapshotBegin@CVssJetWriter@@UEAA_NXZ_0`
- size: `6`
- prototype: `bool(CVssJetWriter *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VSSAPI!?OnPrepareSnapshotBegin@CVssJetWriter@@UEAA_NXZ` at `0x180001f60`

## pseudocode

```c
// attributes: thunk
bool __fastcall CVssJetWriter::OnPrepareSnapshotBegin(CVssJetWriter *this)
{
  return __imp_?OnPrepareSnapshotBegin@CVssJetWriter@@UEAA_NXZ(this);
}

```

## disassembly

```asm
0x180001f60  jmp     cs:__imp_?OnPrepareSnapshotBegin@CVssJetWriter@@UEAA_NXZ
```
