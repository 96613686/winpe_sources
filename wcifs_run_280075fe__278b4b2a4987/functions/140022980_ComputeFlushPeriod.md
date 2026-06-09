# ComputeFlushPeriod

- ea: `0x140022980`
- end: `0x140022a08`
- name: `ComputeFlushPeriod`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140022d88`

## callees

- `0x14000756c`
- `0x140007a50`

## pseudocode

```c
__int64 __fastcall ComputeFlushPeriod(unsigned __int64 a1, unsigned int a2)
{
  __int64 v2; // rax
  __int128 v4; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int64 v5; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = a2;
  v2 = *(_QWORD *)(a1 + 344);
  v5 = a1 >> 4;
  v6 = 0;
  v4 = *(_OWORD *)(*(_QWORD *)(v2 + 8) - 16LL);
  RunningHash(&v6, &v4, 16);
  RunningHash(&v6, &v5, 8);
  FinishHash(&v6);
  return v6 % 0x927C0 + 600000;
}

```

## disassembly

```asm
0x140022980  mov     [rsp+arg_8], edx
0x140022984  sub     rsp, 38h
0x140022988  mov     rax, [rcx+158h]
0x14002298f  mov     r8d, 10h
0x140022995  shr     rcx, 4
0x140022999  mov     [rsp+38h+arg_0], rcx
0x14002299e  lea     rcx, [rsp+38h+arg_8]
0x1400229a3  mov     [rsp+38h+arg_8], 0
0x1400229ab  mov     rdx, [rax+8]
0x1400229af  movups  xmm0, xmmword ptr [rdx-10h]
0x1400229b3  lea     rdx, [rsp+38h+var_18]
0x1400229b8  movdqu  [rsp+38h+var_18], xmm0
0x1400229be  call    RunningHash
0x1400229c3  lea     rcx, [rsp+38h+arg_8]
0x1400229c8  mov     r8d, 8
0x1400229ce  lea     rdx, [rsp+38h+arg_0]
0x1400229d3  call    RunningHash
0x1400229d8  lea     rcx, [rsp+38h+arg_8]
0x1400229dd  call    FinishHash
0x1400229e2  mov     r8d, [rsp+38h+arg_8]
0x1400229e7  mov     eax, 6FD91D85h
0x1400229ec  mul     r8d
0x1400229ef  shr     edx, 12h
0x1400229f2  imul    ecx, edx, 927C0h
0x1400229f8  sub     r8d, ecx
0x1400229fb  lea     eax, [r8+927C0h]
0x140022a02  add     rsp, 38h
0x140022a06  retn
```
