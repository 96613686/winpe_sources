# Concurrency::details::_Schedule_chore(Concurrency::details::_Threadpool_chore *)

- ea: `0x180019029`
- end: `0x18001902f`
- name: `?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z`
- size: `6`
- prototype: `int __fastcall(Concurrency::details *this, struct Concurrency::details::_Threadpool_chore *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000fc9c`

## import_xrefs

- `msvcp_win!?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z` at `0x180019029`

## pseudocode

```c
// attributes: thunk
int __fastcall Concurrency::details::_Schedule_chore(
        Concurrency::details *this,
        struct Concurrency::details::_Threadpool_chore *a2)
{
  return __imp_?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z(this, a2);
}

```

## disassembly

```asm
0x180019029  jmp     cs:__imp_?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z
```
