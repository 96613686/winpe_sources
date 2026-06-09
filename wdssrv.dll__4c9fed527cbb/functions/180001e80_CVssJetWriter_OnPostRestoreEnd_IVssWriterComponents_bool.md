# CVssJetWriter::OnPostRestoreEnd(IVssWriterComponents *,bool)

- ea: `0x180001e80`
- end: `0x180001e86`
- name: `?OnPostRestoreEnd@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@_N@Z_0`
- size: `6`
- prototype: `bool(CVssJetWriter *__hidden this, struct IVssWriterComponents *, bool)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `VSSAPI!?OnPostRestoreEnd@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@_N@Z` at `0x180001e80`

## pseudocode

```c
// attributes: thunk
bool __fastcall CVssJetWriter::OnPostRestoreEnd(CVssJetWriter *this, struct IVssWriterComponents *a2, bool a3)
{
  return __imp_?OnPostRestoreEnd@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@_N@Z(this, a2, a3);
}

```

## disassembly

```asm
0x180001e80  jmp     cs:__imp_?OnPostRestoreEnd@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@_N@Z
```
