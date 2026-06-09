# operator delete(void *,unsigned __int64)

- ea: `0x1400023c4`
- end: `0x1400023c9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `23`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140003990`
- `0x1400039d0`
- `0x1400073a0`
- `0x140007498`
- `0x1400075ec`
- `0x1400076f0`
- `0x14000780c`
- `0x140007980`
- `0x140007ab8`
- `0x140007bf8`
- `0x140007ea8`
- `0x14000875c`
- `0x1400087c4`
- `0x140008f50`
- `0x140008f90`
- `0x140008fd0`
- `0x140009040`
- `0x1400090a0`
- `0x140009100`
- `0x140009130`
- `0x140009180`
- `0x140009dcc`
- `0x14000b022`

## callees

- `0x140002a50`

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
0x1400023c4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
