# DirectUI::Element::Remove(DirectUI::Element * *,uint)

- ea: `0x180003ca0`
- end: `0x180003ca6`
- name: `?Remove@Element@DirectUI@@UEAAJPEAPEAV12@I@Z_0`
- size: `6`
- prototype: `int __fastcall(DirectUI::Element *this, struct DirectUI::Element **, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `DUI70!?Remove@Element@DirectUI@@UEAAJPEAPEAV12@I@Z` at `0x180003ca0`

## pseudocode

```c
// attributes: thunk
int __fastcall DirectUI::Element::Remove(DirectUI::Element *this, struct DirectUI::Element **a2, unsigned int a3)
{
  return __imp_?Remove@Element@DirectUI@@UEAAJPEAPEAV12@I@Z(this, a2, a3);
}

```

## disassembly

```asm
0x180003ca0  jmp     cs:__imp_?Remove@Element@DirectUI@@UEAAJPEAPEAV12@I@Z
```
