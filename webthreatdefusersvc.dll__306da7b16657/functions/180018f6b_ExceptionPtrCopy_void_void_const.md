# __ExceptionPtrCopy(void *,void const *)

- ea: `0x180018f6b`
- end: `0x180018f71`
- name: `?__ExceptionPtrCopy@@YAXPEAXPEBX@Z`
- size: `6`
- prototype: `void __fastcall(void *, const void *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180006978`
- `0x180006c10`
- `0x18000f168`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180018f6b`

## pseudocode

```c
// attributes: thunk
void __fastcall __ExceptionPtrCopy(void *a1, const void *a2)
{
  __imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z(a1, a2);
}

```

## disassembly

```asm
0x180018f6b  jmp     cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z
```
