# BalanceUpdateStatsForStartingJob

- ea: `0x140002bf0`
- end: `0x140002f7f`
- name: `BalanceUpdateStatsForStartingJob`
- size: `911`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140003de0`

## callees

- `0x140002bf0`
- `0x140002f90`
- `0x1400031a0`
- `0x140004610`
- `0x1400056e0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140002cdf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002e0b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002cdf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002e0b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002c7b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002dd4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002c7b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002dd4`

## pseudocode

```c
bool __fastcall BalanceUpdateStatsForStartingJob(__int64 a1)
{
  volatile signed __int32 *v1; // rax
  __int64 v2; // rbx
  unsigned __int64 v3; // r12
  __int64 v4; // rdi
  __int64 *v5; // rdx
  unsigned __int64 v6; // r14
  __int64 v7; // rsi
  __int64 v8; // rax
  char v9; // dl
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  __int64 v12; // rbp
  bool v14; // cf
  __int64 v15; // rax
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // r8
  unsigned __int64 v19; // r9
  unsigned __int64 v20; // rtt
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rax
  __int64 v23; // rcx

  v1 = *(volatile signed __int32 **)(a1 + 40);
  v2 = a1;
  v3 = *(_QWORD *)(a1 + 160);
  v4 = *(_QWORD *)v1;
  *(_BYTE *)(a1 + 128) = 1;
  _InterlockedIncrement(v1 + 50);
  _InterlockedIncrement((volatile signed __int32 *)(v4 + 4136));
  v5 = *(__int64 **)(a1 + 40);
  v6 = *(_QWORD *)(a1 + 144);
  v7 = *v5;
  if ( v6 )
  {
    v6 = (v6 + 511) >> 9;
    v8 = a1;
    _InterlockedExchange64(
      v5 + 32,
      (*(_QWORD *)(a1 + 136) >> 9) - _InterlockedExchange64(v5 + 31, v6 + (*(_QWORD *)(a1 + 136) >> 9)));
    a1 = 127;
    v9 = 1;
  }
  else
  {
    v9 = 0;
    v8 = 127;
  }
  *(_BYTE *)(v8 + a1) = v9;
  *(_BYTE *)(v7 + 1096) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v7 + 1088));
  v10 = *(_QWORD *)(v7 + 1224);
  if ( v10 )
    v11 = *(_QWORD *)(v7 + 1120) + *(_QWORD *)(v7 + 1144) * *(_QWORD *)(v7 + 1248) / v10;
  else
    v11 = *(_QWORD *)(v7 + 1120);
  if ( *(_BYTE *)(v2 + 127) )
    v11 += *(_QWORD *)(v7 + 1128);
  v12 = *(_QWORD *)(v7 + 1136) * v6 + v11;
  KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 1088), *(_BYTE *)(v7 + 1096));
  if ( v12 > 0 )
  {
    if ( (unsigned __int64)v12 > 0xEE6B2800 )
      v12 = 4000000000LL;
  }
  else
  {
    v12 = 1;
  }
  *(_QWORD *)(v2 + 152) = v12;
  if ( v3 >= qword_14000D2C0 + *(_QWORD *)(v4 + 3016)
    && !_interlockedbittestandset((volatile signed __int32 *)(v4 + 2936), 0) )
  {
    BalanceCollectThroughputSample(v4, v3, v4 + 3016);
    if ( v3 - *(_QWORD *)(v4 + 2944) >= qword_14000D320 )
    {
      v14 = *(_DWORD *)(v4 + 2932) < 0x14u;
      *(_QWORD *)(v4 + 2944) = v3;
      if ( !v14 && *(_DWORD *)(v4 + 4008) >= 0x14u )
      {
        v15 = *(_QWORD *)(v4 + 2976);
        if ( v15 )
          BalanceComputeThroughputFunction(
            v4 + 3016,
            v15 * (unsigned __int64)(unsigned int)dword_14000D2E4 / 0x64,
            *(_QWORD *)(v4 + 2960));
      }
      *(_BYTE *)(v4 + 1096) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 1088));
      if ( (unsigned __int8)SqospAreExternalDeviceCostEstimatesValid(v4) )
      {
        v16 = *(_QWORD *)(v4 + 960);
      }
      else if ( *(_QWORD *)(v4 + 4032) && *(_DWORD *)(v4 + 920) )
      {
        v23 = *(_QWORD *)(v4 + 1112);
        if ( !v23 )
          v23 = *(_QWORD *)(v4 + 960);
        v16 = (unsigned __int64)(v23 + *(_QWORD *)(v4 + 4032)) >> 1;
        *(_QWORD *)(v4 + 1112) = v16;
      }
      else
      {
        v16 = qword_14000D2D0;
        *(_QWORD *)(v4 + 1112) = qword_14000D2D0;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 1088), *(_BYTE *)(v4 + 1096));
      v17 = qword_14000D2D8;
      if ( v16 >= qword_14000D2D8 )
      {
        v17 = v16;
        if ( v16 > qword_14000D2D0 )
          v17 = qword_14000D2D0;
      }
      v18 = v17 >> 1;
      v19 = *(_QWORD *)(v4 + 4064) - *(_QWORD *)(v4 + 2992);
      *(_QWORD *)(v4 + 2992) = *(_QWORD *)(v4 + 4064);
      if ( v19 )
      {
        v20 = *(_QWORD *)(v4 + 4152) - *(_QWORD *)(v4 + 2984);
        *(_QWORD *)(v4 + 2984) = *(_QWORD *)(v4 + 4152);
        v21 = (qword_14000D298 * (v20 / v19)) >> 16;
      }
      else
      {
        v21 = 0;
      }
      v22 = 100 * v21;
      if ( v22 <= v18 )
        _interlockedbittestandreset((volatile signed __int32 *)(v4 + 2936), 1u);
      else
        _interlockedbittestandset((volatile signed __int32 *)(v4 + 2936), 1u);
      if ( *(_DWORD *)(v4 + 924) )
      {
        *(_QWORD *)(v4 + 3000) = v18;
        *(_QWORD *)(v4 + 3008) = v22;
      }
    }
    _interlockedbittestandreset((volatile signed __int32 *)(v4 + 2936), 0);
  }
  if ( *(_DWORD *)(v4 + 1152) == 3 && _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 1152), 4, 3) == 3 )
    BalanceUpdateCostEstimatesInternal(v4, v3);
  return (*(_DWORD *)(v4 + 2936) & 2) != 0;
}

```

## disassembly

```asm
0x140002bf0  push    rbx
0x140002bf2  push    rbp
0x140002bf3  push    rsi
0x140002bf4  push    rdi
0x140002bf5  push    r12
0x140002bf7  push    r14
0x140002bf9  push    r15
0x140002bfb  sub     rsp, 20h
0x140002bff  mov     rax, [rcx+28h]
0x140002c03  mov     rbx, rcx
0x140002c06  mov     r12, [rcx+0A0h]
0x140002c0d  mov     rdi, [rax]
0x140002c10  mov     byte ptr [rcx+80h], 1
0x140002c17  lock inc dword ptr [rax+0C8h]
0x140002c1e  lock inc dword ptr [rdi+1028h]
0x140002c25  mov     rdx, [rcx+28h]
0x140002c29  mov     r14, [rcx+90h]
0x140002c30  mov     rsi, [rdx]
0x140002c33  test    r14, r14
0x140002c36  jz      loc_140002EA9
0x140002c3c  mov     rcx, [rcx+88h]
0x140002c43  add     r14, 1FFh
0x140002c4a  shr     rcx, 9
0x140002c4e  shr     r14, 9
0x140002c52  lea     rax, [r14+rcx]
0x140002c56  xchg    rax, [rdx+0F8h]
0x140002c5d  sub     rcx, rax
0x140002c60  mov     rax, rbx
0x140002c63  xchg    rcx, [rdx+100h]
0x140002c6a  mov     ecx, 7Fh
0x140002c6f  mov     dl, 1
0x140002c71  mov     [rax+rcx], dl
0x140002c74  lea     rcx, [rsi+440h]; SpinLock
0x140002c7b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002c82  nop     dword ptr [rax+rax+00h]
0x140002c87  mov     [rsi+448h], al
0x140002c8d  mov     rcx, [rsi+4C8h]
0x140002c94  mov     r8, [rsi+460h]
0x140002c9b  test    rcx, rcx
0x140002c9e  jz      loc_140002EB5
0x140002ca4  mov     rax, [rsi+4E0h]
0x140002cab  xor     edx, edx
0x140002cad  imul    rax, [rsi+478h]
0x140002cb5  div     rcx
0x140002cb8  add     rax, r8
0x140002cbb  cmp     byte ptr [rbx+7Fh], 0
0x140002cbf  jnz     loc_140002EBD
0x140002cc5  imul    r14, [rsi+470h]
0x140002ccd  movzx   edx, byte ptr [rsi+448h]; NewIrql
0x140002cd4  lea     rcx, [rsi+440h]; SpinLock
0x140002cdb  lea     rbp, [r14+rax]
0x140002cdf  call    cs:__imp_KeReleaseSpinLock
0x140002ce6  nop     dword ptr [rax+rax+00h]
0x140002ceb  test    rbp, rbp
0x140002cee  jg      loc_140002EC9
0x140002cf4  mov     ebp, 1
0x140002cf9  mov     [rbx+98h], rbp
0x140002d00  mov     rcx, [rdi+0BC8h]
0x140002d07  add     rcx, cs:qword_14000D2C0
0x140002d0e  cmp     r12, rcx
0x140002d11  jnb     short loc_140002D3C
0x140002d13  mov     eax, [rdi+480h]
0x140002d19  cmp     eax, 3
0x140002d1c  jz      loc_140002F57
0x140002d22  mov     eax, [rdi+0B78h]
0x140002d28  shr     eax, 1
0x140002d2a  and     al, 1
0x140002d2c  add     rsp, 20h
0x140002d30  pop     r15
0x140002d32  pop     r14
0x140002d34  pop     r12
0x140002d36  pop     rdi
0x140002d37  pop     rsi
0x140002d38  pop     rbp
0x140002d39  pop     rbx
0x140002d3a  retn
0x140002d3c  lock bts dword ptr [rdi+0B78h], 0
0x140002d45  jb      short loc_140002D13
0x140002d47  lea     r8, [rdi+0BC8h]
0x140002d4e  mov     rdx, r12
0x140002d51  mov     rcx, rdi
0x140002d54  call    BalanceCollectThroughputSample
0x140002d59  mov     rax, r12
0x140002d5c  sub     rax, [rdi+0B80h]
0x140002d63  cmp     rax, cs:qword_14000D320
0x140002d6a  jb      loc_140002E8C
0x140002d70  cmp     dword ptr [rdi+0B74h], 14h
0x140002d77  mov     [rdi+0B80h], r12
0x140002d7e  jb      short loc_140002DCD
0x140002d80  cmp     dword ptr [rdi+0FA8h], 14h
0x140002d87  jb      short loc_140002DCD
0x140002d89  mov     rax, [rdi+0BA0h]
0x140002d90  test    rax, rax
0x140002d93  jz      short loc_140002DCD
0x140002d95  mov     r9d, cs:dword_14000D2E4
0x140002d9c  lea     rcx, [rdi+0BC8h]
0x140002da3  mov     r8, [rdi+0B90h]
0x140002daa  imul    r9, rax
0x140002dae  mov     rax, 47AE147AE147AE15h
0x140002db8  mul     r9
0x140002dbb  sub     r9, rdx
0x140002dbe  shr     r9, 1
0x140002dc1  add     rdx, r9
0x140002dc4  shr     rdx, 6
0x140002dc8  call    BalanceComputeThroughputFunction
0x140002dcd  lea     rcx, [rdi+440h]; SpinLock
0x140002dd4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002ddb  nop     dword ptr [rax+rax+00h]
0x140002de0  mov     rcx, rdi
0x140002de3  mov     [rdi+448h], al
0x140002de9  call    SqospAreExternalDeviceCostEstimatesValid
0x140002dee  test    al, al
0x140002df0  jz      loc_140002EDA
0x140002df6  mov     rbx, [rdi+3C0h]
0x140002dfd  movzx   edx, byte ptr [rdi+448h]; NewIrql
0x140002e04  lea     rcx, [rdi+440h]; SpinLock
0x140002e0b  call    cs:__imp_KeReleaseSpinLock
0x140002e12  nop     dword ptr [rax+rax+00h]
0x140002e17  mov     r8, cs:qword_14000D2D8
0x140002e1e  cmp     rbx, r8
0x140002e21  jnb     loc_140002F2D
0x140002e27  mov     rax, [rdi+0FE0h]
0x140002e2e  mov     r9, rax
0x140002e31  shr     r8, 1
0x140002e34  sub     r9, [rdi+0BB0h]
0x140002e3b  mov     [rdi+0BB0h], rax
0x140002e42  jz      short loc_140002E9A
0x140002e44  mov     rcx, [rdi+1038h]
0x140002e4b  xor     edx, edx
0x140002e4d  mov     rax, rcx
0x140002e50  sub     rax, [rdi+0BA8h]
0x140002e57  div     r9
0x140002e5a  mov     [rdi+0BA8h], rcx
0x140002e61  imul    rax, cs:qword_14000D298
0x140002e69  shr     rax, 10h
0x140002e6d  imul    rax, 64h ; 'd'
0x140002e71  cmp     rax, r8
0x140002e74  jbe     short loc_140002E9E
0x140002e76  lock bts dword ptr [rdi+0B78h], 1
0x140002e7f  cmp     dword ptr [rdi+39Ch], 0
0x140002e86  jnz     loc_140002F44
0x140002e8c  lock btr dword ptr [rdi+0B78h], 0
0x140002e95  jmp     loc_140002D13
0x140002e9a  xor     eax, eax
0x140002e9c  jmp     short loc_140002E6D
0x140002e9e  lock btr dword ptr [rdi+0B78h], 1
0x140002ea7  jmp     short loc_140002E7F
0x140002ea9  xor     dl, dl
0x140002eab  mov     eax, 7Fh
0x140002eb0  jmp     loc_140002C71
0x140002eb5  mov     rax, r8
0x140002eb8  jmp     loc_140002CBB
0x140002ebd  add     rax, [rsi+468h]
0x140002ec4  jmp     loc_140002CC5
0x140002ec9  mov     eax, 0EE6B2800h
0x140002ece  cmp     rbp, rax
0x140002ed1  cmova   rbp, rax
0x140002ed5  jmp     loc_140002CF9
0x140002eda  cmp     qword ptr [rdi+0FC0h], 0
0x140002ee2  jz      short loc_140002F1A
0x140002ee4  mov     eax, [rdi+398h]
0x140002eea  test    eax, eax
0x140002eec  jz      short loc_140002F1A
0x140002eee  mov     rcx, [rdi+458h]
0x140002ef5  test    rcx, rcx
0x140002ef8  jnz     short loc_140002F01
0x140002efa  mov     rcx, [rdi+3C0h]
0x140002f01  mov     rbx, [rdi+0FC0h]
0x140002f08  add     rbx, rcx
0x140002f0b  shr     rbx, 1
0x140002f0e  mov     [rdi+458h], rbx
0x140002f15  jmp     loc_140002DFD
0x140002f1a  mov     rbx, cs:qword_14000D2D0
0x140002f21  mov     [rdi+458h], rbx
0x140002f28  jmp     loc_140002DFD
0x140002f2d  cmp     rbx, cs:qword_14000D2D0
0x140002f34  mov     r8, rbx
0x140002f37  cmova   r8, cs:qword_14000D2D0
0x140002f3f  jmp     loc_140002E27
0x140002f44  mov     [rdi+0BB8h], r8
0x140002f4b  mov     [rdi+0BC0h], rax
0x140002f52  jmp     loc_140002E8C
0x140002f57  mov     ecx, 4
0x140002f5c  mov     eax, 3
0x140002f61  lock cmpxchg [rdi+480h], ecx
0x140002f69  jnz     loc_140002D22
0x140002f6f  mov     rdx, r12
0x140002f72  mov     rcx, rdi
0x140002f75  call    BalanceUpdateCostEstimatesInternal
0x140002f7a  jmp     loc_140002D22
```
