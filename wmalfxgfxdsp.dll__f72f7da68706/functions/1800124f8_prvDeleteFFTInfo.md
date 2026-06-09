# prvDeleteFFTInfo

- ea: `0x1800124f8`
- end: `0x180012527`
- name: `prvDeleteFFTInfo`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000a0ec`
- `0x180085020`

## callees

- `0x1800124f8`
- `0x180012530`
- `0x180015104`

## pseudocode

```c
void __fastcall prvDeleteFFTInfo(void **Block)
{
  if ( Block )
  {
    prvDeleteFFTEntry(Block[1]);
    operator delete(Block);
  }
}

```

## disassembly

```asm
0x1800124f8  test    rcx, rcx
0x1800124fb  jz      short locret_180012526
0x1800124fd  push    rbx
0x1800124fe  sub     rsp, 20h
0x180012502  mov     edx, [rcx+4]
0x180012505  mov     rbx, rcx
0x180012508  sub     edx, [rcx]
0x18001250a  mov     r8d, [rcx+10h]
0x18001250e  inc     edx
0x180012510  mov     rcx, [rcx+8]; Block
0x180012514  call    prvDeleteFFTEntry
0x180012519  mov     rcx, rbx; Block
0x18001251c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012521  add     rsp, 20h
0x180012525  pop     rbx
0x180012526  retn
```
