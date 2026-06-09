# DirectUI::ClassInfoBase::RemoveChild(void)

- ea: `0x180003d60`
- end: `0x180003d66`
- name: `?RemoveChild@ClassInfoBase@DirectUI@@UEAAXXZ_0`
- size: `6`
- prototype: `void __fastcall(DirectUI::ClassInfoBase *this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `DUI70!?RemoveChild@ClassInfoBase@DirectUI@@UEAAXXZ` at `0x180003d60`

## pseudocode

```c
// attributes: thunk
void __fastcall DirectUI::ClassInfoBase::RemoveChild(DirectUI::ClassInfoBase *this)
{
  __imp_?RemoveChild@ClassInfoBase@DirectUI@@UEAAXXZ(this);
}

```

## disassembly

```asm
0x180003d60  jmp     cs:__imp_?RemoveChild@ClassInfoBase@DirectUI@@UEAAXXZ
```
