# CVssJetWriter::OnPostRestoreBegin(IVssWriterComponents *)

- ea: `0x180001e90`
- end: `0x180001e96`
- name: `?OnPostRestoreBegin@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@@Z_0`
- size: `6`
- prototype: `bool(CVssJetWriter *__hidden this, struct IVssWriterComponents *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `VSSAPI!?OnPostRestoreBegin@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@@Z` at `0x180001e90`

## pseudocode

```c
// attributes: thunk
bool __fastcall CVssJetWriter::OnPostRestoreBegin(CVssJetWriter *this, struct IVssWriterComponents *a2)
{
  return __imp_?OnPostRestoreBegin@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@@Z(this, a2);
}

```

## disassembly

```asm
0x180001e90  jmp     cs:__imp_?OnPostRestoreBegin@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@@Z
```
