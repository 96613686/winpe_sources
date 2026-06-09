# CVssJetWriter::OnIdentify(IVssCreateWriterMetadata *)

- ea: `0x180001f90`
- end: `0x180001f96`
- name: `?OnIdentify@CVssJetWriter@@UEAA_NPEAVIVssCreateWriterMetadata@@@Z_0`
- size: `6`
- prototype: `bool(CVssJetWriter *__hidden this, struct IVssCreateWriterMetadata *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VSSAPI!?OnIdentify@CVssJetWriter@@UEAA_NPEAVIVssCreateWriterMetadata@@@Z` at `0x180001f90`

## pseudocode

```c
// attributes: thunk
bool __fastcall CVssJetWriter::OnIdentify(CVssJetWriter *this, struct IVssCreateWriterMetadata *a2)
{
  return __imp_?OnIdentify@CVssJetWriter@@UEAA_NPEAVIVssCreateWriterMetadata@@@Z(this, a2);
}

```

## disassembly

```asm
0x180001f90  jmp     cs:__imp_?OnIdentify@CVssJetWriter@@UEAA_NPEAVIVssCreateWriterMetadata@@@Z
```
