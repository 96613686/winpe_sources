# DirectUI::TouchHWNDElement::OnKeyFocusMoved(DirectUI::Element *,DirectUI::Element *)

- ea: `0x180003e80`
- end: `0x180003e86`
- name: `?OnKeyFocusMoved@TouchHWNDElement@DirectUI@@UEAAXPEAVElement@2@0@Z_0`
- size: `6`
- prototype: `void __fastcall(DirectUI::TouchHWNDElement *this, struct DirectUI::Element *, struct DirectUI::Element *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `DUI70!?OnKeyFocusMoved@TouchHWNDElement@DirectUI@@UEAAXPEAVElement@2@0@Z` at `0x180003e80`

## pseudocode

```c
// attributes: thunk
void __fastcall DirectUI::TouchHWNDElement::OnKeyFocusMoved(
        DirectUI::TouchHWNDElement *this,
        struct DirectUI::Element *a2,
        struct DirectUI::Element *a3)
{
  __imp_?OnKeyFocusMoved@TouchHWNDElement@DirectUI@@UEAAXPEAVElement@2@0@Z(this, a2, a3);
}

```

## disassembly

```asm
0x180003e80  jmp     cs:__imp_?OnKeyFocusMoved@TouchHWNDElement@DirectUI@@UEAAXPEAVElement@2@0@Z
```
