# ComputeFlushPeriod

- ea: `0x140025d00`
- end: `0x140025d88`
- name: `ComputeFlushPeriod`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140026108`

## callees

- `0x140009bd8`
- `0x14000af98`

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
0x140025d00  mov     [rsp+arg_8], edx
0x140025d04  sub     rsp, 38h
0x140025d08  mov     rax, [rcx+158h]
0x140025d0f  mov     r8d, 10h
0x140025d15  shr     rcx, 4
0x140025d19  mov     [rsp+38h+arg_0], rcx
0x140025d1e  lea     rcx, [rsp+38h+arg_8]
0x140025d23  mov     [rsp+38h+arg_8], 0
0x140025d2b  mov     rdx, [rax+8]
0x140025d2f  movups  xmm0, xmmword ptr [rdx-10h]
0x140025d33  lea     rdx, [rsp+38h+var_18]
0x140025d38  movdqu  [rsp+38h+var_18], xmm0
0x140025d3e  call    RunningHash
0x140025d43  lea     rcx, [rsp+38h+arg_8]
0x140025d48  mov     r8d, 8
0x140025d4e  lea     rdx, [rsp+38h+arg_0]
0x140025d53  call    RunningHash
0x140025d58  lea     rcx, [rsp+38h+arg_8]
0x140025d5d  call    FinishHash
0x140025d62  mov     r8d, [rsp+38h+arg_8]
0x140025d67  mov     eax, 6FD91D85h
0x140025d6c  mul     r8d
0x140025d6f  shr     edx, 12h
0x140025d72  imul    ecx, edx, 927C0h
0x140025d78  sub     r8d, ecx
0x140025d7b  lea     eax, [r8+927C0h]
0x140025d82  add     rsp, 38h
0x140025d86  retn
```
