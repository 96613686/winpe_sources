# DirectUI::TouchHWNDElement::RemoveTooltip(DirectUI::Element *)

- ea: `0x180003ed0`
- end: `0x180003ed6`
- name: `?RemoveTooltip@TouchHWNDElement@DirectUI@@UEAAXPEAVElement@2@@Z_0`
- size: `6`
- prototype: `void __fastcall(DirectUI::TouchHWNDElement *this, struct DirectUI::Element *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `DUI70!?RemoveTooltip@TouchHWNDElement@DirectUI@@UEAAXPEAVElement@2@@Z` at `0x180003ed0`

## pseudocode

```c
// attributes: thunk
void __fastcall DirectUI::TouchHWNDElement::RemoveTooltip(
        DirectUI::TouchHWNDElement *this,
        struct DirectUI::Element *a2)
{
  __imp_?RemoveTooltip@TouchHWNDElement@DirectUI@@UEAAXPEAVElement@2@@Z(this, a2);
}

```

## disassembly

```asm
0x180003ed0  jmp     cs:__imp_?RemoveTooltip@TouchHWNDElement@DirectUI@@UEAAXPEAVElement@2@@Z
```
