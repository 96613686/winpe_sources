# _o___std_exception_copy_0

- ea: `0x1400104ea`
- end: `0x1400104f0`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x14000bd18`
- `0x140017630`
- `0x1400196f0`
- `0x14001a3d0`
- `0x14001a430`
- `0x14001a480`
- `0x140045e34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1400104ea`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy_0()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x1400104ea  jmp     cs:__imp__o___std_exception_copy
```
