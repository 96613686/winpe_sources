# CVssJetWriter::OnThawEnd(bool)

- ea: `0x180001f10`
- end: `0x180001f16`
- name: `?OnThawEnd@CVssJetWriter@@UEAA_N_N@Z_0`
- size: `6`
- prototype: `bool(CVssJetWriter *__hidden this, bool)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VSSAPI!?OnThawEnd@CVssJetWriter@@UEAA_N_N@Z` at `0x180001f10`

## pseudocode

```c
// attributes: thunk
bool __fastcall CVssJetWriter::OnThawEnd(CVssJetWriter *this, bool a2)
{
  return __imp_?OnThawEnd@CVssJetWriter@@UEAA_N_N@Z(this, a2);
}

```

## disassembly

```asm
0x180001f10  jmp     cs:__imp_?OnThawEnd@CVssJetWriter@@UEAA_N_N@Z
```
