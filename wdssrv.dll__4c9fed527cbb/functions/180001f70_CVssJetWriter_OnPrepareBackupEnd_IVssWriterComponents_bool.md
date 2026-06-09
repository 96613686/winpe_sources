# CVssJetWriter::OnPrepareBackupEnd(IVssWriterComponents *,bool)

- ea: `0x180001f70`
- end: `0x180001f76`
- name: `?OnPrepareBackupEnd@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@_N@Z_0`
- size: `6`
- prototype: `bool(CVssJetWriter *__hidden this, struct IVssWriterComponents *, bool)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `VSSAPI!?OnPrepareBackupEnd@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@_N@Z` at `0x180001f70`

## pseudocode

```c
// attributes: thunk
bool __fastcall CVssJetWriter::OnPrepareBackupEnd(CVssJetWriter *this, struct IVssWriterComponents *a2, bool a3)
{
  return __imp_?OnPrepareBackupEnd@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@_N@Z(this, a2, a3);
}

```

## disassembly

```asm
0x180001f70  jmp     cs:__imp_?OnPrepareBackupEnd@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@_N@Z
```
