# Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)

- ea: `0x100403760`
- end: `0x100403a09`
- name: `?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAX_K@Z`
- size: `681`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100403270`
- `0x10040bbb0`
- `0x10040bf30`
- `0x10041d070`
- `0x100421ca0`
- `0x100421e80`
- `0x1004740e0`
- `0x100475c00`
- `0x100476ab0`
- `0x100477010`
- `0x1004771f0`
- `0x1004773d0`
- `0x1004775a0`

## callees

- `0x100403760`

## import_xrefs

- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x100403826`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x1004038e0`
- `sqldk!?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x1004038e9`
- `sqldk!?sm_SpinIncrement@SOS_PublicGlobals@@2_KA` at `0x1004038fd`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x100403899`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x100403899`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x1004038ad`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x1004038ad`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x1004039c3`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x1004039c3`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040381b`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040381b`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100403806`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100403806`
- `sqldk!SystemThread_TlsIndex` at `0x100403797`
- `sqldk!SystemThread_TlsOffset` at `0x1004037a1`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004037df`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040390e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040390e`

## pseudocode

```c
_BOOL8 __fastcall Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(
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
  v22[0] = 19;
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
      *(_QWORD *)(*((_QWORD *)SpinlockStats + 1) + 1064LL) += v18;
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
0x100403760  mov     [rsp+arg_0], rbx
0x100403765  mov     [rsp+arg_8], rbp
0x10040376a  push    rsi
0x10040376b  push    rdi
0x10040376c  push    r12
0x10040376e  push    r14
0x100403770  push    r15
0x100403772  sub     rsp, 50h
0x100403776  mov     eax, 13h
0x10040377b  mov     [rsp+78h+var_54], 1
0x100403783  mov     [rsp+78h+var_58], ax
0x100403788  mov     r12, rdx
0x10040378b  mov     r9, gs:58h
0x100403794  mov     r14, rcx
0x100403797  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040379e  mov     r8d, [rax]
0x1004037a1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004037a8  mov     r10d, [rax]
0x1004037ab  add     r10, [r9+r8*8]
0x1004037af  jz      short loc_1004037D4
0x1004037b1  cmp     [r10+110h], r10
0x1004037b8  jnz     short loc_1004037D4
0x1004037ba  mov     rcx, [r10+100h]
0x1004037c1  mov     [rsp+78h+var_50], rcx
0x1004037c6  test    rcx, rcx
0x1004037c9  jz      short loc_1004037DD
0x1004037cb  mov     rcx, [rcx+3E0h]
0x1004037d2  jmp     short loc_1004037DF
0x1004037d4  mov     [rsp+78h+var_50], 0
0x1004037dd  xor     ecx, ecx
0x1004037df  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004037e6  mov     [rsp+78h+var_48], rcx
0x1004037eb  mov     [rsp+78h+var_40], 0
0x1004037f4  mov     [rsp+78h+var_38], 0
0x1004037fc  test    byte ptr [rax], 1
0x1004037ff  jz      short loc_100403826
0x100403801  test    rcx, rcx
0x100403804  jz      short loc_100403826
0x100403806  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x10040380c  mov     rcx, rax
0x10040380f  mov     rax, [rsp+78h+var_48]
0x100403814  movzx   edx, word ptr [rax+0A0h]
0x10040381b  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x100403821  mov     [rsp+78h+var_40], rax
0x100403826  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x10040382d  mov     r15d, 3Ch ; '<'
0x100403833  mov     ecx, [rax]
0x100403835  mov     rdx, [rsp+78h+var_40]
0x10040383a  cmp     rcx, r15
0x10040383d  mov     edi, ecx
0x10040383f  cmova   edi, r15d
0x100403843  test    rdx, rdx
0x100403846  jz      loc_1004038E0
0x10040384c  mov     ebx, [rsp+78h+var_54]
0x100403850  xor     r8d, r8d
0x100403853  movzx   esi, [rsp+78h+var_58]
0x100403858  movzx   ecx, bx
0x10040385b  sub     ecx, 1
0x10040385e  jz      short loc_100403881
0x100403860  sub     ecx, 1
0x100403863  jz      short loc_10040387B
0x100403865  sub     ecx, 1
0x100403868  jz      short loc_100403875
0x10040386a  cmp     ecx, 1
0x10040386d  jnz     short loc_100403885
0x10040386f  mov     r8, [rdx+20h]
0x100403873  jmp     short loc_100403885
0x100403875  mov     r8, [rdx+18h]
0x100403879  jmp     short loc_100403885
0x10040387b  mov     r8, [rdx+10h]
0x10040387f  jmp     short loc_100403885
0x100403881  mov     r8, [rdx+8]
0x100403885  imul    rcx, rsi, 38h ; '8'
0x100403889  movzx   edx, si
0x10040388c  inc     qword ptr [rcx+r8+8]
0x100403891  mov     r8d, ebx
0x100403894  mov     rcx, [rsp+78h+var_40]
0x100403899  call    cs:__imp_?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetSpins(ushort,SPINLOCK_CATEGORY)
0x10040389f  mov     rcx, [rsp+78h+var_40]
0x1004038a4  mov     r8d, ebx
0x1004038a7  movzx   edx, si
0x1004038aa  mov     rbp, rax
0x1004038ad  call    cs:__imp_?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetCollisions(ushort,SPINLOCK_CATEGORY)
0x1004038b3  mov     rcx, rax
0x1004038b6  test    rbp, rbp
0x1004038b9  jz      short loc_1004038E0
0x1004038bb  test    rax, rax
0x1004038be  jz      short loc_1004038E0
0x1004038c0  xor     edx, edx
0x1004038c2  mov     rax, rbp
0x1004038c5  div     rcx
0x1004038c8  mov     rcx, rdi
0x1004038cb  shr     rax, 1
0x1004038ce  cmp     rax, rdi
0x1004038d1  cmova   rcx, rax
0x1004038d5  imul    rdi, 64h ; 'd'
0x1004038d9  cmp     rcx, rdi
0x1004038dc  cmovb   rdi, rcx
0x1004038e0  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x1004038e7  mov     ecx, [rax]
0x1004038e9  mov     rax, cs:__imp_?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_StaggerEnabledForSpinToAcquire
0x1004038f0  cmp     rcx, r15
0x1004038f3  mov     ebp, ecx
0x1004038f5  cmova   rbp, r15
0x1004038f9  movzx   r15d, byte ptr [rax]
0x1004038fd  mov     rax, cs:__imp_?sm_SpinIncrement@SOS_PublicGlobals@@2_KA; unsigned __int64 SOS_PublicGlobals::sm_SpinIncrement
0x100403904  mov     rsi, [rax]
0x100403907  xor     ebx, ebx
0x100403909  test    r15b, r15b
0x10040390c  jz      short loc_100403920
0x10040390e  call    cs:__imp_rand
0x100403914  xor     edx, edx
0x100403916  cdqe
0x100403918  div     rdi
0x10040391b  inc     rdx
0x10040391e  jmp     short loc_100403923
0x100403920  mov     rdx, rdi
0x100403923  test    rdx, rdx
0x100403926  jz      short loc_10040393A
0x100403928  nop     dword ptr [rax+rax+00000000h]
0x100403930  pause
0x100403932  add     rbx, rsi
0x100403935  cmp     rbx, rdx
0x100403938  jb      short loc_100403930
0x10040393a  mov     rax, [rsp+78h+var_40]
0x10040393f  test    rax, rax
0x100403942  jz      short loc_10040394F
0x100403944  mov     rax, [rax+8]
0x100403948  add     [rax+428h], rbx
0x10040394f  mov     eax, [r14]
0x100403952  test    eax, eax
0x100403954  jnz     short loc_10040396D
0x100403956  xor     eax, eax
0x100403958  lock cmpxchg [r14], r12
0x10040395d  mov     eax, 0
0x100403962  setz    al
0x100403965  test    eax, eax
0x100403967  jnz     loc_1004039F0
0x10040396d  inc     [rsp+78h+var_38]
0x100403971  mov     rdx, [rsp+78h+var_40]
0x100403976  test    rdx, rdx
0x100403979  jz      short loc_1004039BB
0x10040397b  movzx   ecx, word ptr [rsp+78h+var_54]
0x100403980  xor     r8d, r8d
0x100403983  sub     ecx, 1
0x100403986  jz      short loc_1004039A9
0x100403988  sub     ecx, 1
0x10040398b  jz      short loc_1004039A3
0x10040398d  sub     ecx, 1
0x100403990  jz      short loc_10040399D
0x100403992  cmp     ecx, 1
0x100403995  jnz     short loc_1004039AD
0x100403997  mov     r8, [rdx+20h]
0x10040399b  jmp     short loc_1004039AD
0x10040399d  mov     r8, [rdx+18h]
0x1004039a1  jmp     short loc_1004039AD
0x1004039a3  mov     r8, [rdx+10h]
0x1004039a7  jmp     short loc_1004039AD
0x1004039a9  mov     r8, [rdx+8]
0x1004039ad  movzx   eax, [rsp+78h+var_58]
0x1004039b2  imul    rcx, rax, 38h ; '8'
0x1004039b6  inc     qword ptr [rcx+r8+18h]
0x1004039bb  lea     rdx, [rsp+78h+var_58]
0x1004039c0  mov     rcx, r14
0x1004039c3  call    cs:__imp_?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z; SpinlockBase::Backoff(SpinlockBase::SpinInfo &)
0x1004039c9  test    byte ptr [rsp+78h+var_38], 1Fh
0x1004039ce  jnz     short loc_1004039D8
0x1004039d0  mov     rdi, rbp
0x1004039d3  jmp     loc_100403907
0x1004039d8  lea     rax, [rdi+rdi]
0x1004039dc  mov     ecx, 2625A0h
0x1004039e1  cmp     rax, rcx
0x1004039e4  mov     rdi, rax
0x1004039e7  cmova   rdi, rcx
0x1004039eb  jmp     loc_100403907
0x1004039f0  lea     r11, [rsp+78h+var_28]
0x1004039f5  mov     rbx, [r11+30h]
0x1004039f9  mov     rbp, [r11+38h]
0x1004039fd  mov     rsp, r11
0x100403a00  pop     r15
0x100403a02  pop     r14
0x100403a04  pop     r12
0x100403a06  pop     rdi
0x100403a07  pop     rsi
0x100403a08  retn
```
