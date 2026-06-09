# FrameProvider::AddRef(void)

- ea: `0x180017250`
- end: `0x180017257`
- name: `?AddRef@FrameProvider@@UEAAKXZ`
- size: `7`
- prototype: `unsigned int __fastcall(FrameProvider *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180017260`
- `0x180017270`
- `0x180017280`
- `0x180017290`
- `0x1800172a0`

## import_xrefs

- `DUI70!?AddRef@XProvider@DirectUI@@UEAAKXZ` at `0x180017250`

## pseudocode

```c
// attributes: thunk
unsigned int __fastcall FrameProvider::AddRef(FrameProvider *this)
{
  return DirectUI::XProvider::AddRef(this);
}

```

## disassembly

```asm
0x180017250  jmp     cs:__imp_?AddRef@XProvider@DirectUI@@UEAAKXZ; DirectUI::XProvider::AddRef(void)
```
