# DirectUI::HWNDHost::GetAccessibleImpl(IAccessible * *)

- ea: `0x180002e30`
- end: `0x180002e36`
- name: `?GetAccessibleImpl@HWNDHost@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z_0`
- size: `6`
- prototype: `int(DirectUI::HWNDHost *__hidden this, struct IAccessible **)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `DUI70!?GetAccessibleImpl@HWNDHost@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z` at `0x180002e30`

## pseudocode

```c
// attributes: thunk
int __fastcall DirectUI::HWNDHost::GetAccessibleImpl(DirectUI::HWNDHost *this, struct IAccessible **a2)
{
  return __imp_?GetAccessibleImpl@HWNDHost@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z(this, a2);
}

```

## disassembly

```asm
0x180002e30  jmp     cs:__imp_?GetAccessibleImpl@HWNDHost@DirectUI@@UEAAJPEAPEAUIAccessible@@@Z
```
