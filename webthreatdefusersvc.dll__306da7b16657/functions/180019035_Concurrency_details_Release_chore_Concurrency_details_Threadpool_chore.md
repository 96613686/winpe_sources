# Concurrency::details::_Release_chore(Concurrency::details::_Threadpool_chore *)

- ea: `0x180019035`
- end: `0x18001903b`
- name: `?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z`
- size: `6`
- prototype: `void __fastcall(Concurrency::details *this, struct Concurrency::details::_Threadpool_chore *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800076f0`
- `0x180008a78`
- `0x18000d0e0`

## import_xrefs

- `msvcp_win!?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z` at `0x180019035`

## pseudocode

```c
// attributes: thunk
void __fastcall Concurrency::details::_Release_chore(
        Concurrency::details *this,
        struct Concurrency::details::_Threadpool_chore *a2)
{
  __imp_?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z(this, a2);
}

```

## disassembly

```asm
0x180019035  jmp     cs:__imp_?_Release_chore@details@Concurrency@@YAXPEAU_Threadpool_chore@12@@Z
```
