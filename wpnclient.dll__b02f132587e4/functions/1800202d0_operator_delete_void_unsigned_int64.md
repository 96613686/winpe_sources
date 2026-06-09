# operator delete(void *,unsigned __int64)

- ea: `0x1800202d0`
- end: `0x1800202d5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `44`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800020d0`
- `0x18000dd90`
- `0x18000de50`
- `0x18000dee0`
- `0x18000dfa0`
- `0x18000e090`
- `0x18000e130`
- `0x18000e200`
- `0x18000e340`
- `0x18000e3b0`
- `0x18000fdf0`
- `0x18000feb0`
- `0x1800125c0`
- `0x180014810`
- `0x1800155d0`
- `0x180015720`
- `0x1800158e0`
- `0x1800160e0`
- `0x1800171e0`
- `0x180017210`
- `0x180017240`
- `0x1800176f0`
- `0x180017730`
- `0x1800180cc`
- `0x180021960`
- `0x1800219a0`
- `0x180023770`
- `0x1800237b0`
- `0x180023800`
- `0x180023840`
- `0x180024d40`
- `0x180024d80`
- `0x1800252f0`
- `0x180026080`
- `0x1800260b0`
- `0x180026ed0`
- `0x180027cd0`
- `0x180027d10`
- `0x180027d50`
- `0x180027d90`
- `0x180027dd0`
- `0x180029a70`
- `0x180029ab0`
- `0x180031b79`

## callees

- `0x180020374`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x1800202d0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
