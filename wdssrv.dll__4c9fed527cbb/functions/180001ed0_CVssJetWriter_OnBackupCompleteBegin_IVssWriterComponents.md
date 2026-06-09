# CVssJetWriter::OnBackupCompleteBegin(IVssWriterComponents *)

- ea: `0x180001ed0`
- end: `0x180001ed6`
- name: `?OnBackupCompleteBegin@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@@Z_0`
- size: `6`
- prototype: `bool(CVssJetWriter *__hidden this, struct IVssWriterComponents *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `VSSAPI!?OnBackupCompleteBegin@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@@Z` at `0x180001ed0`

## pseudocode

```c
// attributes: thunk
bool __fastcall CVssJetWriter::OnBackupCompleteBegin(CVssJetWriter *this, struct IVssWriterComponents *a2)
{
  return __imp_?OnBackupCompleteBegin@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@@Z(this, a2);
}

```

## disassembly

```asm
0x180001ed0  jmp     cs:__imp_?OnBackupCompleteBegin@CVssJetWriter@@UEAA_NPEAVIVssWriterComponents@@@Z
```
