# DirectUI::HWNDElement::GetAccessibleImpl(IAccessible * *)

- ea: `0x180003ac0`
- end: `0x180003ac6`
- name: `?GetAccessibleImpl@HWNDElement@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z_0`
- size: `6`
- prototype: `int __fastcall(DirectUI::HWNDElement *this, struct IAccessible **)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `DUI70!?GetAccessibleImpl@HWNDElement@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z` at `0x180003ac0`

## pseudocode

```c
// attributes: thunk
int __fastcall DirectUI::HWNDElement::GetAccessibleImpl(DirectUI::HWNDElement *this, struct IAccessible **a2)
{
  return __imp_?GetAccessibleImpl@HWNDElement@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z(this, a2);
}

```

## disassembly

```asm
0x180003ac0  jmp     cs:__imp_?GetAccessibleImpl@HWNDElement@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z
```
