# SHTaskPoolAllowThreadReuse

- ea: `0x180018d5e`
- end: `0x180018d64`
- name: `SHTaskPoolAllowThreadReuse`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18000cdfc`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180018d5e`

## pseudocode

```c
// attributes: thunk
__int64 SHTaskPoolAllowThreadReuse()
{
  return __imp_SHTaskPoolAllowThreadReuse();
}

```

## disassembly

```asm
0x180018d5e  jmp     cs:__imp_SHTaskPoolAllowThreadReuse
```
