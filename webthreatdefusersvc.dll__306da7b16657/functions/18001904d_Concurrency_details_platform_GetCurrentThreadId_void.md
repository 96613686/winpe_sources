# Concurrency::details::platform::GetCurrentThreadId(void)

- ea: `0x18001904d`
- end: `0x180019053`
- name: `?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ`
- size: `6`
- prototype: `int __fastcall(Concurrency::details::platform *this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d7f8`
- `0x18000e73c`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x18001904d`

## pseudocode

```c
// attributes: thunk
int __fastcall Concurrency::details::platform::GetCurrentThreadId(Concurrency::details::platform *this)
{
  return __imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ(this);
}

```

## disassembly

```asm
0x18001904d  jmp     cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ
```
