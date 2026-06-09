# DirectUI::HWNDElement::RemoveTooltip(DirectUI::Element *)

- ea: `0x180002660`
- end: `0x180002666`
- name: `?RemoveTooltip@HWNDElement@DirectUI@@UEAAXPEAVElement@2@@Z_0`
- size: `6`
- prototype: `void(DirectUI::HWNDElement *__hidden this, struct DirectUI::Element *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `DUI70!?RemoveTooltip@HWNDElement@DirectUI@@UEAAXPEAVElement@2@@Z` at `0x180002660`

## pseudocode

```c
// attributes: thunk
void __fastcall DirectUI::HWNDElement::RemoveTooltip(DirectUI::HWNDElement *this, struct DirectUI::Element *a2)
{
  __imp_?RemoveTooltip@HWNDElement@DirectUI@@UEAAXPEAVElement@2@@Z(this, a2);
}

```

## disassembly

```asm
0x180002660  jmp     cs:__imp_?RemoveTooltip@HWNDElement@DirectUI@@UEAAXPEAVElement@2@@Z
```
