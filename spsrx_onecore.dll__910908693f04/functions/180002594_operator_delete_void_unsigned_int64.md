# operator delete(void *,unsigned __int64)

- ea: `0x180002594`
- end: `0x180002599`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `23`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800015f0`
- `0x1800037b0`
- `0x1800037f0`
- `0x180004d50`
- `0x180005940`
- `0x18000597c`
- `0x1800059d0`
- `0x180005a20`
- `0x1800063a0`
- `0x1800094e0`
- `0x180009520`
- `0x180009560`
- `0x18000959c`
- `0x1800095f8`
- `0x180009630`
- `0x180009670`
- `0x1800096c0`
- `0x180009700`
- `0x18000973c`
- `0x18000d588`
- `0x18000dd00`
- `0x18000e7c4`
- `0x18000e838`

## callees

- `0x180001c30`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  ??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x180002594  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
