# Spinlock<48,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)

- ea: `0x100409240`
- end: `0x1004094e9`
- name: `?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0DA@$00$0BAAAABAC@@@AEAAX_K@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100407490`

## callees

- `0x100409240`

## import_xrefs

- `sqldk!?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x1004093c9`
- `sqldk!SystemThread_TlsOffset` at `0x100409281`
- `sqldk!SystemThread_TlsIndex` at `0x100409277`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004092e6`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004092e6`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004092fb`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004092fb`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x100409379`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x100409379`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10040938d`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10040938d`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x1004094a3`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x1004094a3`
- `sqldk!?sm_SpinIncrement@SOS_PublicGlobals@@2_KA` at `0x1004093dd`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004092bf`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x100409306`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x1004093c0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004093ee`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004093ee`

## pseudocode

```c
_BOOL8 __fastcall Spinlock<48,1,268435714>::SpinToAcquireWithExponentialBackoff(
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
  v22[0] = 48;
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
      *(_QWORD *)(*((_QWORD *)SpinlockStats + 1) + 2688LL) += v18;
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
0x100409240  mov     [rsp+arg_0], rbx
0x100409245  mov     [rsp+arg_8], rbp
0x10040924a  push    rsi
0x10040924b  push    rdi
0x10040924c  push    r12
0x10040924e  push    r14
0x100409250  push    r15
0x100409252  sub     rsp, 50h
0x100409256  mov     eax, 30h ; '0'
0x10040925b  mov     [rsp+78h+var_54], 1
0x100409263  mov     [rsp+78h+var_58], ax
0x100409268  mov     r12, rdx
0x10040926b  mov     r9, gs:58h
0x100409274  mov     r14, rcx
0x100409277  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040927e  mov     r8d, [rax]
0x100409281  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100409288  mov     r10d, [rax]
0x10040928b  add     r10, [r9+r8*8]
0x10040928f  jz      short loc_1004092B4
0x100409291  cmp     [r10+110h], r10
0x100409298  jnz     short loc_1004092B4
0x10040929a  mov     rcx, [r10+100h]
0x1004092a1  mov     [rsp+78h+var_50], rcx
0x1004092a6  test    rcx, rcx
0x1004092a9  jz      short loc_1004092BD
0x1004092ab  mov     rcx, [rcx+3E0h]
0x1004092b2  jmp     short loc_1004092BF
0x1004092b4  mov     [rsp+78h+var_50], 0
0x1004092bd  xor     ecx, ecx
0x1004092bf  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004092c6  mov     [rsp+78h+var_48], rcx
0x1004092cb  mov     [rsp+78h+var_40], 0
0x1004092d4  mov     [rsp+78h+var_38], 0
0x1004092dc  test    byte ptr [rax], 1
0x1004092df  jz      short loc_100409306
0x1004092e1  test    rcx, rcx
0x1004092e4  jz      short loc_100409306
0x1004092e6  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x1004092ec  mov     rcx, rax
0x1004092ef  mov     rax, [rsp+78h+var_48]
0x1004092f4  movzx   edx, word ptr [rax+0A0h]
0x1004092fb  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x100409301  mov     [rsp+78h+var_40], rax
0x100409306  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x10040930d  mov     r15d, 3Ch ; '<'
0x100409313  mov     ecx, [rax]
0x100409315  mov     rdx, [rsp+78h+var_40]
0x10040931a  cmp     rcx, r15
0x10040931d  mov     edi, ecx
0x10040931f  cmova   edi, r15d
0x100409323  test    rdx, rdx
0x100409326  jz      loc_1004093C0
0x10040932c  mov     ebx, [rsp+78h+var_54]
0x100409330  xor     r8d, r8d
0x100409333  movzx   esi, [rsp+78h+var_58]
0x100409338  movzx   ecx, bx
0x10040933b  sub     ecx, 1
0x10040933e  jz      short loc_100409361
0x100409340  sub     ecx, 1
0x100409343  jz      short loc_10040935B
0x100409345  sub     ecx, 1
0x100409348  jz      short loc_100409355
0x10040934a  cmp     ecx, 1
0x10040934d  jnz     short loc_100409365
0x10040934f  mov     r8, [rdx+20h]
0x100409353  jmp     short loc_100409365
0x100409355  mov     r8, [rdx+18h]
0x100409359  jmp     short loc_100409365
0x10040935b  mov     r8, [rdx+10h]
0x10040935f  jmp     short loc_100409365
0x100409361  mov     r8, [rdx+8]
0x100409365  imul    rcx, rsi, 38h ; '8'
0x100409369  movzx   edx, si
0x10040936c  inc     qword ptr [rcx+r8+8]
0x100409371  mov     r8d, ebx
0x100409374  mov     rcx, [rsp+78h+var_40]
0x100409379  call    cs:__imp_?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetSpins(ushort,SPINLOCK_CATEGORY)
0x10040937f  mov     rcx, [rsp+78h+var_40]
0x100409384  mov     r8d, ebx
0x100409387  movzx   edx, si
0x10040938a  mov     rbp, rax
0x10040938d  call    cs:__imp_?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetCollisions(ushort,SPINLOCK_CATEGORY)
0x100409393  mov     rcx, rax
0x100409396  test    rbp, rbp
0x100409399  jz      short loc_1004093C0
0x10040939b  test    rax, rax
0x10040939e  jz      short loc_1004093C0
0x1004093a0  xor     edx, edx
0x1004093a2  mov     rax, rbp
0x1004093a5  div     rcx
0x1004093a8  mov     rcx, rdi
0x1004093ab  shr     rax, 1
0x1004093ae  cmp     rax, rdi
0x1004093b1  cmova   rcx, rax
0x1004093b5  imul    rdi, 64h ; 'd'
0x1004093b9  cmp     rcx, rdi
0x1004093bc  cmovb   rdi, rcx
0x1004093c0  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x1004093c7  mov     ecx, [rax]
0x1004093c9  mov     rax, cs:__imp_?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_StaggerEnabledForSpinToAcquire
0x1004093d0  cmp     rcx, r15
0x1004093d3  mov     ebp, ecx
0x1004093d5  cmova   rbp, r15
0x1004093d9  movzx   r15d, byte ptr [rax]
0x1004093dd  mov     rax, cs:__imp_?sm_SpinIncrement@SOS_PublicGlobals@@2_KA; unsigned __int64 SOS_PublicGlobals::sm_SpinIncrement
0x1004093e4  mov     rsi, [rax]
0x1004093e7  xor     ebx, ebx
0x1004093e9  test    r15b, r15b
0x1004093ec  jz      short loc_100409400
0x1004093ee  call    cs:__imp_rand
0x1004093f4  xor     edx, edx
0x1004093f6  cdqe
0x1004093f8  div     rdi
0x1004093fb  inc     rdx
0x1004093fe  jmp     short loc_100409403
0x100409400  mov     rdx, rdi
0x100409403  test    rdx, rdx
0x100409406  jz      short loc_10040941A
0x100409408  nop     dword ptr [rax+rax]
0x10040940c  nop     dword ptr [rax+00h]
0x100409410  pause
0x100409412  add     rbx, rsi
0x100409415  cmp     rbx, rdx
0x100409418  jb      short loc_100409410
0x10040941a  mov     rax, [rsp+78h+var_40]
0x10040941f  test    rax, rax
0x100409422  jz      short loc_10040942F
0x100409424  mov     rax, [rax+8]
0x100409428  add     [rax+0A80h], rbx
0x10040942f  mov     eax, [r14]
0x100409432  test    eax, eax
0x100409434  jnz     short loc_10040944D
0x100409436  xor     eax, eax
0x100409438  lock cmpxchg [r14], r12
0x10040943d  mov     eax, 0
0x100409442  setz    al
0x100409445  test    eax, eax
0x100409447  jnz     loc_1004094D0
0x10040944d  inc     [rsp+78h+var_38]
0x100409451  mov     rdx, [rsp+78h+var_40]
0x100409456  test    rdx, rdx
0x100409459  jz      short loc_10040949B
0x10040945b  movzx   ecx, word ptr [rsp+78h+var_54]
0x100409460  xor     r8d, r8d
0x100409463  sub     ecx, 1
0x100409466  jz      short loc_100409489
0x100409468  sub     ecx, 1
0x10040946b  jz      short loc_100409483
0x10040946d  sub     ecx, 1
0x100409470  jz      short loc_10040947D
0x100409472  cmp     ecx, 1
0x100409475  jnz     short loc_10040948D
0x100409477  mov     r8, [rdx+20h]
0x10040947b  jmp     short loc_10040948D
0x10040947d  mov     r8, [rdx+18h]
0x100409481  jmp     short loc_10040948D
0x100409483  mov     r8, [rdx+10h]
0x100409487  jmp     short loc_10040948D
0x100409489  mov     r8, [rdx+8]
0x10040948d  movzx   eax, [rsp+78h+var_58]
0x100409492  imul    rcx, rax, 38h ; '8'
0x100409496  inc     qword ptr [rcx+r8+18h]
0x10040949b  lea     rdx, [rsp+78h+var_58]
0x1004094a0  mov     rcx, r14
0x1004094a3  call    cs:__imp_?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z; SpinlockBase::Backoff(SpinlockBase::SpinInfo &)
0x1004094a9  test    byte ptr [rsp+78h+var_38], 1Fh
0x1004094ae  jnz     short loc_1004094B8
0x1004094b0  mov     rdi, rbp
0x1004094b3  jmp     loc_1004093E7
0x1004094b8  lea     rax, [rdi+rdi]
0x1004094bc  mov     ecx, 2625A0h
0x1004094c1  cmp     rax, rcx
0x1004094c4  mov     rdi, rax
0x1004094c7  cmova   rdi, rcx
0x1004094cb  jmp     loc_1004093E7
0x1004094d0  lea     r11, [rsp+78h+var_28]
0x1004094d5  mov     rbx, [r11+30h]
0x1004094d9  mov     rbp, [r11+38h]
0x1004094dd  mov     rsp, r11
0x1004094e0  pop     r15
0x1004094e2  pop     r14
0x1004094e4  pop     r12
0x1004094e6  pop     rdi
0x1004094e7  pop     rsi
0x1004094e8  retn
```
