# CVssJetWriter::OnPrepareSnapshotEnd(bool)

- ea: `0x180001f50`
- end: `0x180001f56`
- name: `?OnPrepareSnapshotEnd@CVssJetWriter@@UEAA_N_N@Z_0`
- size: `6`
- prototype: `bool(CVssJetWriter *__hidden this, bool)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VSSAPI!?OnPrepareSnapshotEnd@CVssJetWriter@@UEAA_N_N@Z` at `0x180001f50`

## pseudocode

```c
// attributes: thunk
bool __fastcall CVssJetWriter::OnPrepareSnapshotEnd(CVssJetWriter *this, bool a2)
{
  return __imp_?OnPrepareSnapshotEnd@CVssJetWriter@@UEAA_N_N@Z(this, a2);
}

```

## disassembly

```asm
0x180001f50  jmp     cs:__imp_?OnPrepareSnapshotEnd@CVssJetWriter@@UEAA_N_N@Z
```
