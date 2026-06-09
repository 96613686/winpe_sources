# CVssJetWriter::OnPreRestoreBegin(IVssWriterComponents *)

- ea: `0x180001eb0`
- end: `0x180001eb6`
- name: `?OnPreRestoreBegin@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@@Z_0`
- size: `6`
- prototype: `bool(CVssJetWriter *__hidden this, struct IVssWriterComponents *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `VSSAPI!?OnPreRestoreBegin@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@@Z` at `0x180001eb0`

## pseudocode

```c
// attributes: thunk
bool __fastcall CVssJetWriter::OnPreRestoreBegin(CVssJetWriter *this, struct IVssWriterComponents *a2)
{
  return __imp_?OnPreRestoreBegin@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@@Z(this, a2);
}

```

## disassembly

```asm
0x180001eb0  jmp     cs:__imp_?OnPreRestoreBegin@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@@Z
```
