# __ExceptionPtrCreate(void *)

- ea: `0x180018f53`
- end: `0x180018f59`
- name: `?__ExceptionPtrCreate@@YAXPEAX@Z`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180006528`
- `0x18000f6bc`
- `0x18002aaa7`
- `0x18002ae4a`
- `0x18002b024`
- `0x18002b183`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180018f53`

## pseudocode

```c
// attributes: thunk
void __fastcall __ExceptionPtrCreate(void *a1)
{
  __imp_?__ExceptionPtrCreate@@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x180018f53  jmp     cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z
```
