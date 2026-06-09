# CVssJetWriter::OnAbortBegin(void)

- ea: `0x180001ef0`
- end: `0x180001ef6`
- name: `?OnAbortBegin@CVssJetWriter@@UEAAXXZ_0`
- size: `6`
- prototype: `void(CVssJetWriter *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `VSSAPI!?OnAbortBegin@CVssJetWriter@@UEAAXXZ` at `0x180001ef0`

## pseudocode

```c
// attributes: thunk
void __fastcall CVssJetWriter::OnAbortBegin(CVssJetWriter *this)
{
  __imp_?OnAbortBegin@CVssJetWriter@@UEAAXXZ(this);
}

```

## disassembly

```asm
0x180001ef0  jmp     cs:__imp_?OnAbortBegin@CVssJetWriter@@UEAAXXZ
```
