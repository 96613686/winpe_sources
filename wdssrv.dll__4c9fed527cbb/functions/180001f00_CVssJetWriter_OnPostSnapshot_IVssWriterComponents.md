# CVssJetWriter::OnPostSnapshot(IVssWriterComponents *)

- ea: `0x180001f00`
- end: `0x180001f06`
- name: `?OnPostSnapshot@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@@Z_0`
- size: `6`
- prototype: `bool(CVssJetWriter *__hidden this, struct IVssWriterComponents *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `VSSAPI!?OnPostSnapshot@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@@Z` at `0x180001f00`

## pseudocode

```c
// attributes: thunk
bool __fastcall CVssJetWriter::OnPostSnapshot(CVssJetWriter *this, struct IVssWriterComponents *a2)
{
  return __imp_?OnPostSnapshot@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@@Z(this, a2);
}

```

## disassembly

```asm
0x180001f00  jmp     cs:__imp_?OnPostSnapshot@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@@Z
```
