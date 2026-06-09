# CVssJetWriter::OnFreezeEnd(bool)

- ea: `0x180001f30`
- end: `0x180001f36`
- name: `?OnFreezeEnd@CVssJetWriter@@UEAA_N_N@Z_0`
- size: `6`
- prototype: `bool(CVssJetWriter *__hidden this, bool)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VSSAPI!?OnFreezeEnd@CVssJetWriter@@UEAA_N_N@Z` at `0x180001f30`

## pseudocode

```c
// attributes: thunk
bool __fastcall CVssJetWriter::OnFreezeEnd(CVssJetWriter *this, bool a2)
{
  return __imp_?OnFreezeEnd@CVssJetWriter@@UEAA_N_N@Z(this, a2);
}

```

## disassembly

```asm
0x180001f30  jmp     cs:__imp_?OnFreezeEnd@CVssJetWriter@@UEAA_N_N@Z
```
