# CVssJetWriter::OnAbortEnd(void)

- ea: `0x180001ee0`
- end: `0x180001ee6`
- name: `?OnAbortEnd@CVssJetWriter@@UEAAXXZ_0`
- size: `6`
- prototype: `void(CVssJetWriter *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VSSAPI!?OnAbortEnd@CVssJetWriter@@UEAAXXZ` at `0x180001ee0`

## pseudocode

```c
// attributes: thunk
void __fastcall CVssJetWriter::OnAbortEnd(CVssJetWriter *this)
{
  __imp_?OnAbortEnd@CVssJetWriter@@UEAAXXZ(this);
}

```

## disassembly

```asm
0x180001ee0  jmp     cs:__imp_?OnAbortEnd@CVssJetWriter@@UEAAXXZ
```
