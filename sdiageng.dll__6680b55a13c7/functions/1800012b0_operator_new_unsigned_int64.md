# operator new[](unsigned __int64)

- ea: `0x1800012b0`
- end: `0x1800012b5`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(size_t)`
- caller_count: `33`
- callee_count: `1`
- tags: ``

## callers

- `0x180002338`
- `0x1800026a0`
- `0x1800040e8`
- `0x180004380`
- `0x18000533c`
- `0x18000571c`
- `0x180005d60`
- `0x180005ffc`
- `0x180007000`
- `0x180007184`
- `0x18000729c`
- `0x180007bc0`
- `0x18000c144`
- `0x18000c31c`
- `0x1800114dc`
- `0x180016228`
- `0x180019b88`
- `0x18001a0bc`
- `0x18001b4d4`
- `0x18001ee38`
- `0x18001fc10`
- `0x180021ec4`
- `0x180022174`
- `0x180023020`
- `0x180023260`
- `0x180023d78`
- `0x180023dc0`
- `0x180026958`
- `0x180026bf4`
- `0x18002708c`
- `0x1800278d4`
- `0x180027aa0`
- `0x180027b7c`

## callees

- `0x180001264`

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
0x1800012b0  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
