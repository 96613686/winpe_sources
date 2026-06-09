# DirectUI::Element::OnMouseFocusMoved(DirectUI::Element *,DirectUI::Element *)

- ea: `0x180003cf0`
- end: `0x180003cf6`
- name: `?OnMouseFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z_0`
- size: `6`
- prototype: `void __fastcall(DirectUI::Element *this, struct DirectUI::Element *, struct DirectUI::Element *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `DUI70!?OnMouseFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z` at `0x180003cf0`

## pseudocode

```c
// attributes: thunk
void __fastcall DirectUI::Element::OnMouseFocusMoved(
        DirectUI::Element *this,
        struct DirectUI::Element *a2,
        struct DirectUI::Element *a3)
{
  __imp_?OnMouseFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z(this, a2, a3);
}

```

## disassembly

```asm
0x180003cf0  jmp     cs:__imp_?OnMouseFocusMoved@Element@DirectUI@@UEAAXPEAV12@0@Z
```
