# DirectUI::ClassInfoBase::RemoveChild(void)

- ea: `0x180002c50`
- end: `0x180002c56`
- name: `?RemoveChild@ClassInfoBase@DirectUI@@UEAAXXZ_0`
- size: `6`
- prototype: `void(DirectUI::ClassInfoBase *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `DUI70!?RemoveChild@ClassInfoBase@DirectUI@@UEAAXXZ` at `0x180002c50`

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
0x180002c50  jmp     cs:__imp_?RemoveChild@ClassInfoBase@DirectUI@@UEAAXXZ
```
