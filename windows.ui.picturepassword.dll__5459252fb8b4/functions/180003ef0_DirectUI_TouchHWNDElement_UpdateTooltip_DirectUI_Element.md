# DirectUI::TouchHWNDElement::UpdateTooltip(DirectUI::Element *)

- ea: `0x180003ef0`
- end: `0x180003ef6`
- name: `?UpdateTooltip@TouchHWNDElement@DirectUI@@UEAAXPEAVElement@2@@Z_0`
- size: `6`
- prototype: `void(DirectUI::TouchHWNDElement *__hidden this, struct DirectUI::Element *)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `DUI70!?UpdateTooltip@TouchHWNDElement@DirectUI@@UEAAXPEAVElement@2@@Z` at `0x180003ef0`

## pseudocode

```c
// attributes: thunk
void __fastcall DirectUI::TouchHWNDElement::UpdateTooltip(
        DirectUI::TouchHWNDElement *this,
        struct DirectUI::Element *a2)
{
  __imp_?UpdateTooltip@TouchHWNDElement@DirectUI@@UEAAXPEAVElement@2@@Z(this, a2);
}

```

## disassembly

```asm
0x180003ef0  jmp     cs:__imp_?UpdateTooltip@TouchHWNDElement@DirectUI@@UEAAXPEAVElement@2@@Z
```
