# Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)

- ea: `0x100408560`
- end: `0x100408809`
- name: `?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z`
- size: `681`
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

- `0x100408560`

## import_xrefs

- `sqldk!?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x1004086e9`
- `sqldk!SystemThread_TlsOffset` at `0x1004085a1`
- `sqldk!SystemThread_TlsIndex` at `0x100408597`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100408606`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100408606`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040861b`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040861b`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x100408699`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x100408699`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x1004086ad`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x1004086ad`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x1004087c3`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x1004087c3`
- `sqldk!?sm_SpinIncrement@SOS_PublicGlobals@@2_KA` at `0x1004086fd`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004085df`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x100408626`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x1004086e0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040870e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040870e`

## pseudocode

```c
_BOOL8 __fastcall Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(
        volatile signed __int64 *a1,
        signed __int64 a2)
{
  __int64 v4; // r10
  __int64 v5; // rcx
  __int64 v6; // rcx
  PerProcessGlobals *SOSProcessGlobals; // rax
  unsigned __int64 v8; // rdi
  unsigned int v9; // ebx
  __int64 v10; // r8
  unsigned __int16 v11; // si
  __int64 v12; // rdx
  unsigned __int64 Spins; // rbp
  unsigned __int64 Collisions; // rax
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rax
  __int64 v17; // rbp
  unsigned __int64 v18; // rbx
  unsigned __int64 v19; // rdx
  _BOOL8 result; // rax
  __int64 v21; // r8
  unsigned __int16 v22[2]; // [rsp+20h] [rbp-58h] BYREF
  int v23; // [rsp+24h] [rbp-54h]
  __int64 v24; // [rsp+28h] [rbp-50h]
  __int64 v25; // [rsp+30h] [rbp-48h]
  struct SpinlockStat *SpinlockStats; // [rsp+38h] [rbp-40h]
  int v27; // [rsp+40h] [rbp-38h]

  v23 = 1;
  v22[0] = 11;
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  if ( !v4 || *(_QWORD *)(v4 + 272) != v4 )
  {
    v24 = 0;
    goto LABEL_6;
  }
  v5 = *(_QWORD *)(v4 + 256);
  v24 = v5;
  if ( !v5 )
  {
LABEL_6:
    v6 = 0;
    goto LABEL_7;
  }
  v6 = *(_QWORD *)(v5 + 992);
LABEL_7:
  v25 = v6;
  SpinlockStats = 0;
  v27 = 0;
  if ( (SOS_PublicGlobals::sm_osStats & 1) != 0 && v6 )
  {
    SOSProcessGlobals = (PerProcessGlobals *)SOS_OS::GetSOSProcessGlobals();
    SpinlockStats = PerProcessGlobals::GetSpinlockStats(SOSProcessGlobals, *(_WORD *)(v25 + 160));
  }
  v8 = SOS_PublicGlobals::sm_cpuCount;
  if ( SOS_PublicGlobals::sm_cpuCount > 0x3CuLL )
    v8 = 60;
  if ( SpinlockStats )
  {
    v9 = v23;
    v10 = 0;
    v11 = v22[0];
    switch ( (unsigned __int16)v23 )
    {
      case 1u:
        v10 = *((_QWORD *)SpinlockStats + 1);
        break;
      case 2u:
        v10 = *((_QWORD *)SpinlockStats + 2);
        break;
      case 3u:
        v10 = *((_QWORD *)SpinlockStats + 3);
        break;
      case 4u:
        v10 = *((_QWORD *)SpinlockStats + 4);
        break;
    }
    v12 = v22[0];
    ++*(_QWORD *)(56LL * v22[0] + v10 + 8);
    Spins = SpinlockStat::GetSpins(SpinlockStats, v12, v9);
    Collisions = SpinlockStat::GetCollisions(SpinlockStats, v11, v9);
    if ( Spins && Collisions )
    {
      v15 = v8;
      v16 = (Spins / Collisions) >> 1;
      if ( v16 > v8 )
        v15 = v16;
      v8 *= 100LL;
      if ( v15 < v8 )
        v8 = v15;
    }
  }
  v17 = SOS_PublicGlobals::sm_cpuCount;
  if ( SOS_PublicGlobals::sm_cpuCount > 0x3CuLL )
    v17 = 60;
  while ( 1 )
  {
    v18 = 0;
    if ( SOS_PublicGlobals::sm_StaggerEnabledForSpinToAcquire )
      v19 = rand() % v8 + 1;
    else
      v19 = v8;
    if ( v19 )
    {
      do
      {
        _mm_pause();
        v18 += SOS_PublicGlobals::sm_SpinIncrement;
      }
      while ( v18 < v19 );
    }
    if ( SpinlockStats )
      *(_QWORD *)(*((_QWORD *)SpinlockStats + 1) + 616LL) += v18;
    if ( !*(_DWORD *)a1 )
    {
      result = _InterlockedCompareExchange64(a1, a2, 0) == 0;
      if ( result )
        break;
    }
    ++v27;
    if ( SpinlockStats )
    {
      v21 = 0;
      switch ( (unsigned __int16)v23 )
      {
        case 1u:
          v21 = *((_QWORD *)SpinlockStats + 1);
          break;
        case 2u:
          v21 = *((_QWORD *)SpinlockStats + 2);
          break;
        case 3u:
          v21 = *((_QWORD *)SpinlockStats + 3);
          break;
        case 4u:
          v21 = *((_QWORD *)SpinlockStats + 4);
          break;
      }
      ++*(_QWORD *)(56LL * v22[0] + v21 + 24);
    }
    SpinlockBase::Backoff((SpinlockBase *)a1, (struct SpinlockBase::SpinInfo *)v22);
    if ( (v27 & 0x1F) != 0 )
    {
      v8 *= 2LL;
      if ( v8 > 0x2625A0 )
        v8 = 2500000;
    }
    else
    {
      v8 = v17;
    }
  }
  return result;
}

```

## disassembly

```asm
0x100408560  mov     [rsp+arg_0], rbx
0x100408565  mov     [rsp+arg_8], rbp
0x10040856a  push    rsi
0x10040856b  push    rdi
0x10040856c  push    r12
0x10040856e  push    r14
0x100408570  push    r15
0x100408572  sub     rsp, 50h
0x100408576  mov     eax, 0Bh
0x10040857b  mov     [rsp+78h+var_54], 1
0x100408583  mov     [rsp+78h+var_58], ax
0x100408588  mov     r12, rdx
0x10040858b  mov     r9, gs:58h
0x100408594  mov     r14, rcx
0x100408597  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040859e  mov     r8d, [rax]
0x1004085a1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004085a8  mov     r10d, [rax]
0x1004085ab  add     r10, [r9+r8*8]
0x1004085af  jz      short loc_1004085D4
0x1004085b1  cmp     [r10+110h], r10
0x1004085b8  jnz     short loc_1004085D4
0x1004085ba  mov     rcx, [r10+100h]
0x1004085c1  mov     [rsp+78h+var_50], rcx
0x1004085c6  test    rcx, rcx
0x1004085c9  jz      short loc_1004085DD
0x1004085cb  mov     rcx, [rcx+3E0h]
0x1004085d2  jmp     short loc_1004085DF
0x1004085d4  mov     [rsp+78h+var_50], 0
0x1004085dd  xor     ecx, ecx
0x1004085df  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004085e6  mov     [rsp+78h+var_48], rcx
0x1004085eb  mov     [rsp+78h+var_40], 0
0x1004085f4  mov     [rsp+78h+var_38], 0
0x1004085fc  test    byte ptr [rax], 1
0x1004085ff  jz      short loc_100408626
0x100408601  test    rcx, rcx
0x100408604  jz      short loc_100408626
0x100408606  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x10040860c  mov     rcx, rax
0x10040860f  mov     rax, [rsp+78h+var_48]
0x100408614  movzx   edx, word ptr [rax+0A0h]
0x10040861b  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x100408621  mov     [rsp+78h+var_40], rax
0x100408626  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x10040862d  mov     r15d, 3Ch ; '<'
0x100408633  mov     ecx, [rax]
0x100408635  mov     rdx, [rsp+78h+var_40]
0x10040863a  cmp     rcx, r15
0x10040863d  mov     edi, ecx
0x10040863f  cmova   edi, r15d
0x100408643  test    rdx, rdx
0x100408646  jz      loc_1004086E0
0x10040864c  mov     ebx, [rsp+78h+var_54]
0x100408650  xor     r8d, r8d
0x100408653  movzx   esi, [rsp+78h+var_58]
0x100408658  movzx   ecx, bx
0x10040865b  sub     ecx, 1
0x10040865e  jz      short loc_100408681
0x100408660  sub     ecx, 1
0x100408663  jz      short loc_10040867B
0x100408665  sub     ecx, 1
0x100408668  jz      short loc_100408675
0x10040866a  cmp     ecx, 1
0x10040866d  jnz     short loc_100408685
0x10040866f  mov     r8, [rdx+20h]
0x100408673  jmp     short loc_100408685
0x100408675  mov     r8, [rdx+18h]
0x100408679  jmp     short loc_100408685
0x10040867b  mov     r8, [rdx+10h]
0x10040867f  jmp     short loc_100408685
0x100408681  mov     r8, [rdx+8]
0x100408685  imul    rcx, rsi, 38h ; '8'
0x100408689  movzx   edx, si
0x10040868c  inc     qword ptr [rcx+r8+8]
0x100408691  mov     r8d, ebx
0x100408694  mov     rcx, [rsp+78h+var_40]
0x100408699  call    cs:__imp_?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetSpins(ushort,SPINLOCK_CATEGORY)
0x10040869f  mov     rcx, [rsp+78h+var_40]
0x1004086a4  mov     r8d, ebx
0x1004086a7  movzx   edx, si
0x1004086aa  mov     rbp, rax
0x1004086ad  call    cs:__imp_?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetCollisions(ushort,SPINLOCK_CATEGORY)
0x1004086b3  mov     rcx, rax
0x1004086b6  test    rbp, rbp
0x1004086b9  jz      short loc_1004086E0
0x1004086bb  test    rax, rax
0x1004086be  jz      short loc_1004086E0
0x1004086c0  xor     edx, edx
0x1004086c2  mov     rax, rbp
0x1004086c5  div     rcx
0x1004086c8  mov     rcx, rdi
0x1004086cb  shr     rax, 1
0x1004086ce  cmp     rax, rdi
0x1004086d1  cmova   rcx, rax
0x1004086d5  imul    rdi, 64h ; 'd'
0x1004086d9  cmp     rcx, rdi
0x1004086dc  cmovb   rdi, rcx
0x1004086e0  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x1004086e7  mov     ecx, [rax]
0x1004086e9  mov     rax, cs:__imp_?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_StaggerEnabledForSpinToAcquire
0x1004086f0  cmp     rcx, r15
0x1004086f3  mov     ebp, ecx
0x1004086f5  cmova   rbp, r15
0x1004086f9  movzx   r15d, byte ptr [rax]
0x1004086fd  mov     rax, cs:__imp_?sm_SpinIncrement@SOS_PublicGlobals@@2_KA; unsigned __int64 SOS_PublicGlobals::sm_SpinIncrement
0x100408704  mov     rsi, [rax]
0x100408707  xor     ebx, ebx
0x100408709  test    r15b, r15b
0x10040870c  jz      short loc_100408720
0x10040870e  call    cs:__imp_rand
0x100408714  xor     edx, edx
0x100408716  cdqe
0x100408718  div     rdi
0x10040871b  inc     rdx
0x10040871e  jmp     short loc_100408723
0x100408720  mov     rdx, rdi
0x100408723  test    rdx, rdx
0x100408726  jz      short loc_10040873A
0x100408728  nop     dword ptr [rax+rax]
0x10040872c  nop     dword ptr [rax+00h]
0x100408730  pause
0x100408732  add     rbx, rsi
0x100408735  cmp     rbx, rdx
0x100408738  jb      short loc_100408730
0x10040873a  mov     rax, [rsp+78h+var_40]
0x10040873f  test    rax, rax
0x100408742  jz      short loc_10040874F
0x100408744  mov     rax, [rax+8]
0x100408748  add     [rax+268h], rbx
0x10040874f  mov     eax, [r14]
0x100408752  test    eax, eax
0x100408754  jnz     short loc_10040876D
0x100408756  xor     eax, eax
0x100408758  lock cmpxchg [r14], r12
0x10040875d  mov     eax, 0
0x100408762  setz    al
0x100408765  test    eax, eax
0x100408767  jnz     loc_1004087F0
0x10040876d  inc     [rsp+78h+var_38]
0x100408771  mov     rdx, [rsp+78h+var_40]
0x100408776  test    rdx, rdx
0x100408779  jz      short loc_1004087BB
0x10040877b  movzx   ecx, word ptr [rsp+78h+var_54]
0x100408780  xor     r8d, r8d
0x100408783  sub     ecx, 1
0x100408786  jz      short loc_1004087A9
0x100408788  sub     ecx, 1
0x10040878b  jz      short loc_1004087A3
0x10040878d  sub     ecx, 1
0x100408790  jz      short loc_10040879D
0x100408792  cmp     ecx, 1
0x100408795  jnz     short loc_1004087AD
0x100408797  mov     r8, [rdx+20h]
0x10040879b  jmp     short loc_1004087AD
0x10040879d  mov     r8, [rdx+18h]
0x1004087a1  jmp     short loc_1004087AD
0x1004087a3  mov     r8, [rdx+10h]
0x1004087a7  jmp     short loc_1004087AD
0x1004087a9  mov     r8, [rdx+8]
0x1004087ad  movzx   eax, [rsp+78h+var_58]
0x1004087b2  imul    rcx, rax, 38h ; '8'
0x1004087b6  inc     qword ptr [rcx+r8+18h]
0x1004087bb  lea     rdx, [rsp+78h+var_58]
0x1004087c0  mov     rcx, r14
0x1004087c3  call    cs:__imp_?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z; SpinlockBase::Backoff(SpinlockBase::SpinInfo &)
0x1004087c9  test    byte ptr [rsp+78h+var_38], 1Fh
0x1004087ce  jnz     short loc_1004087D8
0x1004087d0  mov     rdi, rbp
0x1004087d3  jmp     loc_100408707
0x1004087d8  lea     rax, [rdi+rdi]
0x1004087dc  mov     ecx, 2625A0h
0x1004087e1  cmp     rax, rcx
0x1004087e4  mov     rdi, rax
0x1004087e7  cmova   rdi, rcx
0x1004087eb  jmp     loc_100408707
0x1004087f0  lea     r11, [rsp+78h+var_28]
0x1004087f5  mov     rbx, [r11+30h]
0x1004087f9  mov     rbp, [r11+38h]
0x1004087fd  mov     rsp, r11
0x100408800  pop     r15
0x100408802  pop     r14
0x100408804  pop     r12
0x100408806  pop     rdi
0x100408807  pop     rsi
0x100408808  retn
```
