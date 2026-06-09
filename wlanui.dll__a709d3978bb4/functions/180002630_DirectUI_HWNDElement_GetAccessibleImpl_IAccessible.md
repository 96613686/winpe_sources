# DirectUI::HWNDElement::GetAccessibleImpl(IAccessible * *)

- ea: `0x180002630`
- end: `0x180002636`
- name: `?GetAccessibleImpl@HWNDElement@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z_0`
- size: `6`
- prototype: `int(DirectUI::HWNDElement *__hidden this, struct IAccessible **)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `DUI70!?GetAccessibleImpl@HWNDElement@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z` at `0x180002630`

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
0x180002630  jmp     cs:__imp_?GetAccessibleImpl@HWNDElement@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z
```
