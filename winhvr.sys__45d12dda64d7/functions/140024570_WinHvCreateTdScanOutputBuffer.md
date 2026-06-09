# WinHvCreateTdScanOutputBuffer

- ea: `0x140024570`
- end: `0x14002465f`
- name: `WinHvCreateTdScanOutputBuffer`
- size: `239`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140001ef0`
- `0x140004408`
- `0x140024570`
- `0x1400246f0`

## pseudocode

```c
__int64 __fastcall WinHvCreateTdScanOutputBuffer(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // r14d
  __int64 result; // rax
  __int64 v7; // rbx
  int v8; // r14d
  __int128 v9; // xmm0
  __int64 Src; // [rsp+40h] [rbp-28h] BYREF
  __int64 v11; // [rsp+48h] [rbp-20h] BYREF
  __int128 v12; // [rsp+50h] [rbp-18h] BYREF
  __int64 v13; // [rsp+A0h] [rbp+38h] BYREF

  Src = a1;
  v13 = 0;
  v11 = 0;
  v12 = 0;
  v5 = a2;
  WinHvpSetProximityDomain(&v11, a2);
  result = WinHvpAllocatingHypercall(a1, v5, 328, 0, &Src, 0x10u, &v13, 8u);
  if ( (int)result >= 0 )
  {
    v7 = v13;
    Src = a1;
    v11 = v13;
    v8 = WinHvpAllocatingHypercall(a1, v5, 329, 0, &Src, 0x10u, &v12, 0x10u);
    if ( v8 < 0 )
    {
      WinHvDeleteTdScanOutputBuffer(a1, v7);
      *(_QWORD *)a3 = -1;
    }
    else
    {
      v9 = v12;
      *(_QWORD *)a3 = v7;
      *(_OWORD *)(a3 + 8) = v9;
    }
    return (unsigned int)v8;
  }
  return result;
}

```

## disassembly

```asm
0x140024570  push    rbp
0x140024572  push    rbx
0x140024573  push    rsi
0x140024574  push    rdi
0x140024575  push    r14
0x140024577  push    r15
0x140024579  mov     rbp, rsp
0x14002457c  sub     rsp, 68h
0x140024580  mov     [rbp+var_28], rcx
0x140024584  mov     rsi, rcx
0x140024587  xorps   xmm0, xmm0
0x14002458a  mov     [rbp+arg_0], 0
0x140024592  lea     rcx, [rbp+var_20]
0x140024596  mov     [rbp+var_20], 0
0x14002459e  movups  [rbp+var_18], xmm0
0x1400245a2  mov     rdi, r8
0x1400245a5  mov     r14d, edx
0x1400245a8  call    WinHvpSetProximityDomain
0x1400245ad  mov     [rsp+68h+var_30], 8; size_t
0x1400245b6  lea     rax, [rbp+arg_0]
0x1400245ba  mov     [rsp+68h+var_38], rax; void *
0x1400245bf  mov     r15d, 10h
0x1400245c5  lea     rax, [rbp+var_28]
0x1400245c9  mov     [rsp+68h+Size], r15; Size
0x1400245ce  xor     r9d, r9d; int
0x1400245d1  mov     [rsp+68h+Src], rax; Src
0x1400245d6  mov     r8d, 148h; int
0x1400245dc  mov     edx, r14d; int
0x1400245df  mov     rcx, rsi; int
0x1400245e2  call    WinHvpAllocatingHypercall
0x1400245e7  test    eax, eax
0x1400245e9  js      short loc_140024651
0x1400245eb  mov     rbx, [rbp+arg_0]
0x1400245ef  lea     rax, [rbp+var_18]
0x1400245f3  mov     [rsp+68h+var_30], r15; size_t
0x1400245f8  xor     r9d, r9d; int
0x1400245fb  mov     [rsp+68h+var_38], rax; void *
0x140024600  mov     r8d, 149h; int
0x140024606  lea     rax, [rbp+var_28]
0x14002460a  mov     [rsp+68h+Size], r15; Size
0x14002460f  mov     edx, r14d; int
0x140024612  mov     [rsp+68h+Src], rax; Src
0x140024617  mov     rcx, rsi; int
0x14002461a  mov     [rbp+var_28], rsi
0x14002461e  mov     [rbp+var_20], rbx
0x140024622  call    WinHvpAllocatingHypercall
0x140024627  mov     r14d, eax
0x14002462a  test    eax, eax
0x14002462c  js      short loc_14002463C
0x14002462e  movups  xmm0, [rbp+var_18]
0x140024632  mov     [rdi], rbx
0x140024635  movdqu  xmmword ptr [rdi+8], xmm0
0x14002463a  jmp     short loc_14002464E
0x14002463c  mov     rdx, rbx
0x14002463f  mov     rcx, rsi
0x140024642  call    WinHvDeleteTdScanOutputBuffer
0x140024647  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x14002464e  mov     eax, r14d
0x140024651  add     rsp, 68h
0x140024655  pop     r15
0x140024657  pop     r14
0x140024659  pop     rdi
0x14002465a  pop     rsi
0x14002465b  pop     rbx
0x14002465c  pop     rbp
0x14002465d  retn
```
