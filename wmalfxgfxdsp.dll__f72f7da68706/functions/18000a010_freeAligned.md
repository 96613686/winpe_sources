# freeAligned

- ea: `0x18000a010`
- end: `0x18000a02a`
- name: `freeAligned`
- size: `26`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180009664`
- `0x18000969c`
- `0x180009758`
- `0x180009b08`
- `0x180009c8c`
- `0x180009ccc`
- `0x180009f44`
- `0x18000c550`

## callees

- `0x18000a010`
- `0x180015104`

## pseudocode

```c
void __fastcall freeAligned(__int64 a1)
{
  if ( a1 )
    operator delete((void *)(a1 - *(unsigned __int8 *)(a1 - 1)));
}

```

## disassembly

```asm
0x18000a010  sub     rsp, 28h
0x18000a014  test    rcx, rcx
0x18000a017  jz      short loc_18000A025
0x18000a019  movzx   eax, byte ptr [rcx-1]
0x18000a01d  sub     rcx, rax; Block
0x18000a020  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a025  add     rsp, 28h
0x18000a029  retn
```
