# DirectUI::Element::UpdateTooltip(DirectUI::Element *)

- ea: `0x180002b80`
- end: `0x180002b86`
- name: `?UpdateTooltip@Element@DirectUI@@MEAAXPEAV12@@Z_0`
- size: `6`
- prototype: `void(DirectUI::Element *__hidden this, struct DirectUI::Element *)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `DUI70!?UpdateTooltip@Element@DirectUI@@MEAAXPEAV12@@Z` at `0x180002b80`

## pseudocode

```c
// attributes: thunk
void __fastcall DirectUI::Element::UpdateTooltip(DirectUI::Element *this, struct DirectUI::Element *a2)
{
  __imp_?UpdateTooltip@Element@DirectUI@@MEAAXPEAV12@@Z(this, a2);
}

```

## disassembly

```asm
0x180002b80  jmp     cs:__imp_?UpdateTooltip@Element@DirectUI@@MEAAXPEAV12@@Z
```
