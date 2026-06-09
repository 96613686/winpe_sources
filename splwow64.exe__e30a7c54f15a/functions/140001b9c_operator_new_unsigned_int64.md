# operator new[](unsigned __int64)

- ea: `0x140001b9c`
- end: `0x140001ba1`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x140002174`
- `0x1400069b8`
- `0x140006c10`
- `0x140007548`
- `0x1400077fc`
- `0x14000c670`
- `0x14000d264`
- `0x14000d420`
- `0x14000d6c0`
- `0x14000e89c`
- `0x14000ec28`
- `0x14000f1e4`
- `0x140012d4c`

## callees

- `0x140001b50`

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
0x140001b9c  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
