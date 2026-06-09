# terminate_0

- ea: `0x1800068ae`
- end: `0x1800068b4`
- name: `terminate_0`
- size: `6`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002e10`
- `0x180002ef8`
- `0x180002f64`
- `0x180003e48`
- `0x180004304`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!terminate` at `0x1800068ae`

## pseudocode

```c
// attributes: thunk
void __noreturn terminate_0()
{
  terminate();
}

```

## disassembly

```asm
0x1800068ae  jmp     cs:__imp_terminate
```
