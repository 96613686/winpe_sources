# std::vector<ulong,std::allocator<ulong>>::_Umove<ulong *>(ulong *,ulong *,ulong *)

- ea: `0x18001402c`
- end: `0x180014055`
- name: `??$_Umove@PEAK@?$vector@KV?$allocator@K@std@@@std@@IEAAPEAKPEAK00@Z`
- size: `41`
- prototype: `char *__fastcall(__int64, const void *, __int64, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180018e28`
- `0x18001926c`

## callees

- `0x180001982`

## pseudocode

```c
char *__fastcall std::vector<unsigned long>::_Umove<unsigned long *>(__int64 a1, const void *a2, __int64 a3, void *a4)
{
  return (char *)memmove_0(a4, a2, 4 * ((a3 - (__int64)a2) >> 2)) + 4 * ((a3 - (__int64)a2) >> 2);
}

```

## disassembly

```asm
0x18001402c  push    rbx
0x18001402e  sub     rsp, 20h
0x180014032  sub     r8, rdx
0x180014035  mov     rcx, r9; void *
0x180014038  sar     r8, 2
0x18001403c  lea     rbx, ds:0[r8*4]
0x180014044  mov     r8, rbx; Size
0x180014047  call    memmove_0
0x18001404c  add     rax, rbx
0x18001404f  add     rsp, 20h
0x180014053  pop     rbx
0x180014054  retn
```
