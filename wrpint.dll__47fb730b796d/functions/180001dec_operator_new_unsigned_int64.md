# operator new[](unsigned __int64)

- ea: `0x180001dec`
- end: `0x180001df1`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(size_t)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18001029c`
- `0x180010448`
- `0x180010750`
- `0x180010fe0`
- `0x180014054`

## callees

- `0x180001300`

## pseudocode

```c
// attributes: thunk
void *__fastcall operator new[](size_t a1)
{
  return operator new(a1);
}

```

## disassembly

```asm
0x180001dec  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
