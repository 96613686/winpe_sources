# CVssJetWriter::OnFreezeBegin(void)

- ea: `0x180001f40`
- end: `0x180001f46`
- name: `?OnFreezeBegin@CVssJetWriter@@UEAA_NXZ_0`
- size: `6`
- prototype: `bool(CVssJetWriter *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VSSAPI!?OnFreezeBegin@CVssJetWriter@@UEAA_NXZ` at `0x180001f40`

## pseudocode

```c
// attributes: thunk
bool __fastcall CVssJetWriter::OnFreezeBegin(CVssJetWriter *this)
{
  return __imp_?OnFreezeBegin@CVssJetWriter@@UEAA_NXZ(this);
}

```

## disassembly

```asm
0x180001f40  jmp     cs:__imp_?OnFreezeBegin@CVssJetWriter@@UEAA_NXZ
```
