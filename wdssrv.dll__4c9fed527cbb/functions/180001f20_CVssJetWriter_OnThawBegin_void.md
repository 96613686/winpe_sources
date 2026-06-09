# CVssJetWriter::OnThawBegin(void)

- ea: `0x180001f20`
- end: `0x180001f26`
- name: `?OnThawBegin@CVssJetWriter@@UEAA_NXZ_0`
- size: `6`
- prototype: `bool(CVssJetWriter *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VSSAPI!?OnThawBegin@CVssJetWriter@@UEAA_NXZ` at `0x180001f20`

## pseudocode

```c
// attributes: thunk
bool __fastcall CVssJetWriter::OnThawBegin(CVssJetWriter *this)
{
  return __imp_?OnThawBegin@CVssJetWriter@@UEAA_NXZ(this);
}

```

## disassembly

```asm
0x180001f20  jmp     cs:__imp_?OnThawBegin@CVssJetWriter@@UEAA_NXZ
```
