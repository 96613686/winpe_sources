# ComputeFlushPeriod

- ea: `0x1400229d0`
- end: `0x140022a58`
- name: `ComputeFlushPeriod`
- size: `136`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140022dd8`

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
0x1400229d0  mov     [rsp+arg_8], edx
0x1400229d4  sub     rsp, 38h
0x1400229d8  mov     rax, [rcx+158h]
0x1400229df  mov     r8d, 10h
0x1400229e5  shr     rcx, 4
0x1400229e9  mov     [rsp+38h+arg_0], rcx
0x1400229ee  lea     rcx, [rsp+38h+arg_8]
0x1400229f3  mov     [rsp+38h+arg_8], 0
0x1400229fb  mov     rdx, [rax+8]
0x1400229ff  movups  xmm0, xmmword ptr [rdx-10h]
0x140022a03  lea     rdx, [rsp+38h+var_18]
0x140022a08  movdqu  [rsp+38h+var_18], xmm0
0x140022a0e  call    RunningHash
0x140022a13  lea     rcx, [rsp+38h+arg_8]
0x140022a18  mov     r8d, 8
0x140022a1e  lea     rdx, [rsp+38h+arg_0]
0x140022a23  call    RunningHash
0x140022a28  lea     rcx, [rsp+38h+arg_8]
0x140022a2d  call    FinishHash
0x140022a32  mov     r8d, [rsp+38h+arg_8]
0x140022a37  mov     eax, 6FD91D85h
0x140022a3c  mul     r8d
0x140022a3f  shr     edx, 12h
0x140022a42  imul    ecx, edx, 927C0h
0x140022a48  sub     r8d, ecx
0x140022a4b  lea     eax, [r8+927C0h]
0x140022a52  add     rsp, 38h
0x140022a56  retn
```
