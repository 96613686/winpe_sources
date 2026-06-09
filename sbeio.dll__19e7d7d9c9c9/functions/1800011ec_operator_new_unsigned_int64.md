# operator new[](unsigned __int64)

- ea: `0x1800011ec`
- end: `0x1800011f1`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `91`
- callee_count: `1`
- tags: ``

## callers

- `0x1800024c4`
- `0x1800039f0`
- `0x180005df0`
- `0x180009820`
- `0x18000a860`
- `0x18000c2a0`
- `0x18000c9f8`
- `0x18000cd9c`
- `0x18000dbb0`
- `0x18000dfe0`
- `0x18000f390`
- `0x180010060`
- `0x180010c14`
- `0x1800118f8`
- `0x180012e38`
- `0x1800162dc`
- `0x18001640c`
- `0x180017588`
- `0x1800177dc`
- `0x180017a20`
- `0x180017b68`
- `0x180017cf4`
- `0x180017dc0`
- `0x180017ec4`
- `0x180018480`
- `0x180018700`
- `0x1800188d0`
- `0x180018b30`
- `0x180018c80`
- `0x180018da0`
- `0x180018f60`
- `0x180019080`
- `0x1800191b0`
- `0x1800198f0`
- `0x180019f40`
- `0x18001a350`
- `0x18001ad08`
- `0x18001eb10`
- `0x1800209d0`
- `0x180020d20`
- `0x180020e70`
- `0x180020f70`
- `0x180021130`
- `0x180021350`
- `0x180021570`
- `0x1800218c0`
- `0x180021b30`
- `0x180021c20`
- `0x180021da0`
- `0x180021e90`

## callees

- `0x1800011a0`

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
0x1800011ec  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
