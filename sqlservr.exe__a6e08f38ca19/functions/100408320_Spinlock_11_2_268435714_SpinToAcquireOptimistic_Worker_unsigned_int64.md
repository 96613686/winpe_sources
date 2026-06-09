# Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)

- ea: `0x100408320`
- end: `0x100408550`
- name: `?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z`
- size: `560`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100404ed0`
- `0x100405100`
- `0x100412470`
- `0x100416770`
- `0x10041d320`
- `0x10041d870`
- `0x10041f860`
- `0x100435700`
- `0x1004369a0`
- `0x10043f6a0`

## callees

- `0x100408320`

## import_xrefs

- `sqldk!SystemThread_TlsOffset` at `0x100408381`
- `sqldk!SystemThread_TlsIndex` at `0x100408377`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004083de`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004083de`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004083f3`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004083f3`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10040851f`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10040851f`
- `sqldk!?sm_SpinCounter@SOS_PublicGlobals@@2_JA` at `0x100408446`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004083bb`
- `sqldk!?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x10040833c`

## pseudocode

```c
_BOOL8 __fastcall Spinlock<11,2,268435714>::SpinToAcquireOptimistic(SpinlockBase *a1, __int64 a2, signed __int64 a3)
{
  char v5; // di
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdx
  struct SpinlockStat *v11; // rcx
  PerProcessGlobals *SOSProcessGlobals; // rax
  struct SpinlockStat *SpinlockStats; // rax
  int v14; // eax
  int v15; // edx
  unsigned int v16; // esi
  unsigned int v17; // eax
  _BOOL8 result; // rax
  __int64 v19; // r8
  unsigned __int16 v20[2]; // [rsp+20h] [rbp-58h] BYREF
  int v21; // [rsp+24h] [rbp-54h]
  __int64 v22; // [rsp+28h] [rbp-50h]
  __int64 v23; // [rsp+30h] [rbp-48h]
  struct SpinlockStat *v24; // [rsp+38h] [rbp-40h]
  int v25; // [rsp+40h] [rbp-38h]

  v5 = 0;
  v7 = 0;
  v20[0] = 11;
  v21 = 1;
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  if ( v8 && *(_QWORD *)(v8 + 272) == v8 )
  {
    v9 = *(_QWORD *)(v8 + 256);
    v22 = v9;
    if ( v9 )
    {
      v10 = *(_QWORD *)(v9 + 992);
      goto LABEL_7;
    }
  }
  else
  {
    v22 = 0;
  }
  v10 = 0;
LABEL_7:
  v11 = 0;
  v23 = v10;
  v24 = 0;
  v25 = 0;
  if ( (SOS_PublicGlobals::sm_osStats & 1) != 0 )
  {
    if ( v10 )
    {
      SOSProcessGlobals = (PerProcessGlobals *)SOS_OS::GetSOSProcessGlobals();
      SpinlockStats = PerProcessGlobals::GetSpinlockStats(SOSProcessGlobals, *(_WORD *)(v23 + 160));
      v24 = SpinlockStats;
      v11 = SpinlockStats;
      if ( SpinlockStats )
      {
        ++*(_QWORD *)(*((_QWORD *)SpinlockStats + 1) + 624LL);
        v11 = v24;
      }
    }
  }
  if ( a2
    && ((v14 = *(_DWORD *)(a2 + 616), (v14 & 0x40) != 0)
     || (v15 = *(_DWORD *)(a2 + 800), (v15 & 0x202000) != 0)
     || (v14 & 0x400) != 0
     || (v15 & 0x100000) != 0) )
  {
    v16 = 10000;
  }
  else
  {
    v16 = SOS_PublicGlobals::sm_SpinCounter;
    if ( !(_DWORD)SOS_PublicGlobals::sm_SpinCounter )
      v16 = 1;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      v17 = 0;
      if ( !SOS_PublicGlobals::sm_ShouldResetSpinsForSpinToAcquire )
        v17 = v7;
      v7 = v17;
      if ( v17 < v16 )
      {
        while ( 1 )
        {
          if ( v5 )
          {
            v5 = 0;
          }
          else if ( v7 && !*(_DWORD *)a1 )
          {
LABEL_27:
            v11 = v24;
            break;
          }
          _mm_pause();
          if ( ++v7 >= v16 )
            goto LABEL_27;
        }
      }
      if ( v11 )
      {
        *(_QWORD *)(*((_QWORD *)v11 + 1) + 616LL) += v7;
        v11 = v24;
      }
      if ( v7 < v16 )
        break;
      ++v25;
      if ( v11 )
      {
        v19 = 0;
        switch ( (unsigned __int16)v21 )
        {
          case 1u:
            v19 = *((_QWORD *)v11 + 1);
            break;
          case 2u:
            v19 = *((_QWORD *)v11 + 2);
            break;
          case 3u:
            v19 = *((_QWORD *)v11 + 3);
            break;
          case 4u:
            v19 = *((_QWORD *)v11 + 4);
            break;
        }
        ++*(_QWORD *)(56LL * v20[0] + v19 + 24);
      }
      SpinlockBase::Backoff(a1, (struct SpinlockBase::SpinInfo *)v20);
      v11 = v24;
      v7 = 0;
    }
    result = _InterlockedCompareExchange64((volatile signed __int64 *)a1, a3, 0) == 0;
    if ( result )
      return result;
    v11 = v24;
    v5 = 1;
    v25 = 0;
  }
}

```

## disassembly

```asm
0x100408320  mov     [rsp+arg_0], rbx
0x100408325  mov     [rsp+arg_10], rbp
0x10040832a  mov     [rsp+arg_18], rsi
0x10040832f  push    rdi
0x100408330  push    r12
0x100408332  push    r13
0x100408334  push    r14
0x100408336  push    r15
0x100408338  sub     rsp, 50h
0x10040833c  mov     rax, cs:__imp_?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_ShouldResetSpinsForSpinToAcquire
0x100408343  mov     r14, rcx
0x100408346  xor     r12d, r12d
0x100408349  mov     r13d, 1
0x10040834f  mov     rbp, r8
0x100408352  xor     dil, dil
0x100408355  mov     rsi, rdx
0x100408358  mov     ebx, r12d
0x10040835b  movzx   r15d, byte ptr [rax]
0x10040835f  mov     eax, 0Bh
0x100408364  mov     [rsp+78h+var_58], ax
0x100408369  mov     [rsp+78h+var_54], r13d
0x10040836e  mov     r9, gs:58h
0x100408377  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040837e  mov     r8d, [rax]
0x100408381  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100408388  mov     ecx, [rax]
0x10040838a  add     rcx, [r9+r8*8]
0x10040838e  jz      short loc_1004083B3
0x100408390  cmp     [rcx+110h], rcx
0x100408397  jnz     short loc_1004083B3
0x100408399  mov     rdx, [rcx+100h]
0x1004083a0  mov     [rsp+78h+var_50], rdx
0x1004083a5  test    rdx, rdx
0x1004083a8  jz      short loc_1004083B8
0x1004083aa  mov     rdx, [rdx+3E0h]
0x1004083b1  jmp     short loc_1004083BB
0x1004083b3  mov     [rsp+78h+var_50], r12
0x1004083b8  mov     rdx, r12
0x1004083bb  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004083c2  mov     rcx, r12
0x1004083c5  mov     [rsp+78h+var_48], rdx
0x1004083ca  mov     [rsp+78h+var_40], rcx
0x1004083cf  mov     [rsp+78h+var_38], r12d
0x1004083d4  test    [rax], r13b
0x1004083d7  jz      short loc_100408416
0x1004083d9  test    rdx, rdx
0x1004083dc  jz      short loc_100408416
0x1004083de  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x1004083e4  mov     rcx, rax
0x1004083e7  mov     rax, [rsp+78h+var_48]
0x1004083ec  movzx   edx, word ptr [rax+0A0h]
0x1004083f3  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x1004083f9  mov     [rsp+78h+var_40], rax
0x1004083fe  mov     rcx, rax
0x100408401  test    rax, rax
0x100408404  jz      short loc_100408416
0x100408406  mov     rax, [rax+8]
0x10040840a  inc     qword ptr [rax+270h]
0x100408411  mov     rcx, [rsp+78h+var_40]
0x100408416  test    rsi, rsi
0x100408419  jz      short loc_100408446
0x10040841b  mov     eax, [rsi+268h]
0x100408421  test    al, 40h
0x100408423  jnz     short loc_10040843F
0x100408425  mov     edx, [rsi+320h]
0x10040842b  test    edx, 202000h
0x100408431  jnz     short loc_10040843F
0x100408433  bt      eax, 0Ah
0x100408437  jb      short loc_10040843F
0x100408439  bt      edx, 14h
0x10040843d  jnb     short loc_100408446
0x10040843f  mov     esi, 2710h
0x100408444  jmp     short loc_100408460
0x100408446  mov     rax, cs:__imp_?sm_SpinCounter@SOS_PublicGlobals@@2_JA; __int64 SOS_PublicGlobals::sm_SpinCounter
0x10040844d  mov     esi, [rax]
0x10040844f  cmp     esi, r13d
0x100408452  cmovb   esi, r13d
0x100408456  nop     word ptr [rax+rax+00000000h]
0x100408460  test    r15b, r15b
0x100408463  mov     eax, r12d
0x100408466  cmovz   eax, ebx
0x100408469  mov     ebx, eax
0x10040846b  cmp     eax, esi
0x10040846d  jnb     short loc_100408492
0x10040846f  nop
0x100408470  test    dil, dil
0x100408473  jz      short loc_10040847A
0x100408475  xor     dil, dil
0x100408478  jmp     short loc_100408485
0x10040847a  test    ebx, ebx
0x10040847c  jz      short loc_100408485
0x10040847e  mov     eax, [r14]
0x100408481  test    eax, eax
0x100408483  jz      short loc_10040848D
0x100408485  pause
0x100408487  inc     ebx
0x100408489  cmp     ebx, esi
0x10040848b  jb      short loc_100408470
0x10040848d  mov     rcx, [rsp+78h+var_40]
0x100408492  test    rcx, rcx
0x100408495  jz      short loc_1004084A9
0x100408497  mov     rcx, [rcx+8]
0x10040849b  mov     eax, ebx
0x10040849d  add     [rcx+268h], rax
0x1004084a4  mov     rcx, [rsp+78h+var_40]
0x1004084a9  cmp     ebx, esi
0x1004084ab  jnb     short loc_1004084CE
0x1004084ad  xor     eax, eax
0x1004084af  lock cmpxchg [r14], rbp
0x1004084b4  mov     eax, r12d
0x1004084b7  setz    al
0x1004084ba  test    eax, eax
0x1004084bc  jnz     short loc_100408532
0x1004084be  mov     rcx, [rsp+78h+var_40]
0x1004084c3  movzx   edi, r13b
0x1004084c7  mov     [rsp+78h+var_38], r12d
0x1004084cc  jmp     short loc_100408460
0x1004084ce  inc     [rsp+78h+var_38]
0x1004084d2  test    rcx, rcx
0x1004084d5  jz      short loc_100408517
0x1004084d7  movzx   edx, word ptr [rsp+78h+var_54]
0x1004084dc  mov     r8, r12
0x1004084df  sub     edx, r13d
0x1004084e2  jz      short loc_100408505
0x1004084e4  sub     edx, r13d
0x1004084e7  jz      short loc_1004084FF
0x1004084e9  sub     edx, r13d
0x1004084ec  jz      short loc_1004084F9
0x1004084ee  cmp     edx, r13d
0x1004084f1  jnz     short loc_100408509
0x1004084f3  mov     r8, [rcx+20h]
0x1004084f7  jmp     short loc_100408509
0x1004084f9  mov     r8, [rcx+18h]
0x1004084fd  jmp     short loc_100408509
0x1004084ff  mov     r8, [rcx+10h]
0x100408503  jmp     short loc_100408509
0x100408505  mov     r8, [rcx+8]
0x100408509  movzx   eax, [rsp+78h+var_58]
0x10040850e  imul    rcx, rax, 38h ; '8'
0x100408512  inc     qword ptr [rcx+r8+18h]
0x100408517  lea     rdx, [rsp+78h+var_58]
0x10040851c  mov     rcx, r14
0x10040851f  call    cs:__imp_?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z; SpinlockBase::Backoff(SpinlockBase::SpinInfo &)
0x100408525  mov     rcx, [rsp+78h+var_40]
0x10040852a  mov     ebx, r12d
0x10040852d  jmp     loc_100408460
0x100408532  lea     r11, [rsp+78h+var_28]
0x100408537  mov     rbx, [r11+30h]
0x10040853b  mov     rbp, [r11+40h]
0x10040853f  mov     rsi, [r11+48h]
0x100408543  mov     rsp, r11
0x100408546  pop     r15
0x100408548  pop     r14
0x10040854a  pop     r13
0x10040854c  pop     r12
0x10040854e  pop     rdi
0x10040854f  retn
```
