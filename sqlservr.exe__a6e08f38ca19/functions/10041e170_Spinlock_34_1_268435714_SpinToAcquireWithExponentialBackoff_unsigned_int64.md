# Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)

- ea: `0x10041e170`
- end: `0x10041e419`
- name: `?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAX_K@Z`
- size: `681`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100412470`
- `0x100416770`
- `0x10041d870`
- `0x100435700`
- `0x1004369a0`
- `0x10043f6a0`

## callees

- `0x10041e170`

## import_xrefs

- `sqldk!?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x10041e2f9`
- `sqldk!SystemThread_TlsOffset` at `0x10041e1b1`
- `sqldk!SystemThread_TlsIndex` at `0x10041e1a7`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10041e216`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10041e216`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10041e22b`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10041e22b`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10041e2a9`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10041e2a9`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10041e2bd`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10041e2bd`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10041e3d3`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10041e3d3`
- `sqldk!?sm_SpinIncrement@SOS_PublicGlobals@@2_KA` at `0x10041e30d`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10041e1ef`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x10041e236`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x10041e2f0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041e31e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10041e31e`

## pseudocode

```c
_BOOL8 __fastcall Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(
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
  v22[0] = 34;
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
      *(_QWORD *)(*((_QWORD *)SpinlockStats + 1) + 1904LL) += v18;
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
0x10041e170  mov     [rsp+arg_0], rbx
0x10041e175  mov     [rsp+arg_8], rbp
0x10041e17a  push    rsi
0x10041e17b  push    rdi
0x10041e17c  push    r12
0x10041e17e  push    r14
0x10041e180  push    r15
0x10041e182  sub     rsp, 50h
0x10041e186  mov     eax, 22h ; '"'
0x10041e18b  mov     [rsp+78h+var_54], 1
0x10041e193  mov     [rsp+78h+var_58], ax
0x10041e198  mov     r12, rdx
0x10041e19b  mov     r9, gs:58h
0x10041e1a4  mov     r14, rcx
0x10041e1a7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041e1ae  mov     r8d, [rax]
0x10041e1b1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041e1b8  mov     r10d, [rax]
0x10041e1bb  add     r10, [r9+r8*8]
0x10041e1bf  jz      short loc_10041E1E4
0x10041e1c1  cmp     [r10+110h], r10
0x10041e1c8  jnz     short loc_10041E1E4
0x10041e1ca  mov     rcx, [r10+100h]
0x10041e1d1  mov     [rsp+78h+var_50], rcx
0x10041e1d6  test    rcx, rcx
0x10041e1d9  jz      short loc_10041E1ED
0x10041e1db  mov     rcx, [rcx+3E0h]
0x10041e1e2  jmp     short loc_10041E1EF
0x10041e1e4  mov     [rsp+78h+var_50], 0
0x10041e1ed  xor     ecx, ecx
0x10041e1ef  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10041e1f6  mov     [rsp+78h+var_48], rcx
0x10041e1fb  mov     [rsp+78h+var_40], 0
0x10041e204  mov     [rsp+78h+var_38], 0
0x10041e20c  test    byte ptr [rax], 1
0x10041e20f  jz      short loc_10041E236
0x10041e211  test    rcx, rcx
0x10041e214  jz      short loc_10041E236
0x10041e216  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x10041e21c  mov     rcx, rax
0x10041e21f  mov     rax, [rsp+78h+var_48]
0x10041e224  movzx   edx, word ptr [rax+0A0h]
0x10041e22b  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x10041e231  mov     [rsp+78h+var_40], rax
0x10041e236  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x10041e23d  mov     r15d, 3Ch ; '<'
0x10041e243  mov     ecx, [rax]
0x10041e245  mov     rdx, [rsp+78h+var_40]
0x10041e24a  cmp     rcx, r15
0x10041e24d  mov     edi, ecx
0x10041e24f  cmova   edi, r15d
0x10041e253  test    rdx, rdx
0x10041e256  jz      loc_10041E2F0
0x10041e25c  mov     ebx, [rsp+78h+var_54]
0x10041e260  xor     r8d, r8d
0x10041e263  movzx   esi, [rsp+78h+var_58]
0x10041e268  movzx   ecx, bx
0x10041e26b  sub     ecx, 1
0x10041e26e  jz      short loc_10041E291
0x10041e270  sub     ecx, 1
0x10041e273  jz      short loc_10041E28B
0x10041e275  sub     ecx, 1
0x10041e278  jz      short loc_10041E285
0x10041e27a  cmp     ecx, 1
0x10041e27d  jnz     short loc_10041E295
0x10041e27f  mov     r8, [rdx+20h]
0x10041e283  jmp     short loc_10041E295
0x10041e285  mov     r8, [rdx+18h]
0x10041e289  jmp     short loc_10041E295
0x10041e28b  mov     r8, [rdx+10h]
0x10041e28f  jmp     short loc_10041E295
0x10041e291  mov     r8, [rdx+8]
0x10041e295  imul    rcx, rsi, 38h ; '8'
0x10041e299  movzx   edx, si
0x10041e29c  inc     qword ptr [rcx+r8+8]
0x10041e2a1  mov     r8d, ebx
0x10041e2a4  mov     rcx, [rsp+78h+var_40]
0x10041e2a9  call    cs:__imp_?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetSpins(ushort,SPINLOCK_CATEGORY)
0x10041e2af  mov     rcx, [rsp+78h+var_40]
0x10041e2b4  mov     r8d, ebx
0x10041e2b7  movzx   edx, si
0x10041e2ba  mov     rbp, rax
0x10041e2bd  call    cs:__imp_?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetCollisions(ushort,SPINLOCK_CATEGORY)
0x10041e2c3  mov     rcx, rax
0x10041e2c6  test    rbp, rbp
0x10041e2c9  jz      short loc_10041E2F0
0x10041e2cb  test    rax, rax
0x10041e2ce  jz      short loc_10041E2F0
0x10041e2d0  xor     edx, edx
0x10041e2d2  mov     rax, rbp
0x10041e2d5  div     rcx
0x10041e2d8  mov     rcx, rdi
0x10041e2db  shr     rax, 1
0x10041e2de  cmp     rax, rdi
0x10041e2e1  cmova   rcx, rax
0x10041e2e5  imul    rdi, 64h ; 'd'
0x10041e2e9  cmp     rcx, rdi
0x10041e2ec  cmovb   rdi, rcx
0x10041e2f0  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x10041e2f7  mov     ecx, [rax]
0x10041e2f9  mov     rax, cs:__imp_?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_StaggerEnabledForSpinToAcquire
0x10041e300  cmp     rcx, r15
0x10041e303  mov     ebp, ecx
0x10041e305  cmova   rbp, r15
0x10041e309  movzx   r15d, byte ptr [rax]
0x10041e30d  mov     rax, cs:__imp_?sm_SpinIncrement@SOS_PublicGlobals@@2_KA; unsigned __int64 SOS_PublicGlobals::sm_SpinIncrement
0x10041e314  mov     rsi, [rax]
0x10041e317  xor     ebx, ebx
0x10041e319  test    r15b, r15b
0x10041e31c  jz      short loc_10041E330
0x10041e31e  call    cs:__imp_rand
0x10041e324  xor     edx, edx
0x10041e326  cdqe
0x10041e328  div     rdi
0x10041e32b  inc     rdx
0x10041e32e  jmp     short loc_10041E333
0x10041e330  mov     rdx, rdi
0x10041e333  test    rdx, rdx
0x10041e336  jz      short loc_10041E34A
0x10041e338  nop     dword ptr [rax+rax]
0x10041e33c  nop     dword ptr [rax+00h]
0x10041e340  pause
0x10041e342  add     rbx, rsi
0x10041e345  cmp     rbx, rdx
0x10041e348  jb      short loc_10041E340
0x10041e34a  mov     rax, [rsp+78h+var_40]
0x10041e34f  test    rax, rax
0x10041e352  jz      short loc_10041E35F
0x10041e354  mov     rax, [rax+8]
0x10041e358  add     [rax+770h], rbx
0x10041e35f  mov     eax, [r14]
0x10041e362  test    eax, eax
0x10041e364  jnz     short loc_10041E37D
0x10041e366  xor     eax, eax
0x10041e368  lock cmpxchg [r14], r12
0x10041e36d  mov     eax, 0
0x10041e372  setz    al
0x10041e375  test    eax, eax
0x10041e377  jnz     loc_10041E400
0x10041e37d  inc     [rsp+78h+var_38]
0x10041e381  mov     rdx, [rsp+78h+var_40]
0x10041e386  test    rdx, rdx
0x10041e389  jz      short loc_10041E3CB
0x10041e38b  movzx   ecx, word ptr [rsp+78h+var_54]
0x10041e390  xor     r8d, r8d
0x10041e393  sub     ecx, 1
0x10041e396  jz      short loc_10041E3B9
0x10041e398  sub     ecx, 1
0x10041e39b  jz      short loc_10041E3B3
0x10041e39d  sub     ecx, 1
0x10041e3a0  jz      short loc_10041E3AD
0x10041e3a2  cmp     ecx, 1
0x10041e3a5  jnz     short loc_10041E3BD
0x10041e3a7  mov     r8, [rdx+20h]
0x10041e3ab  jmp     short loc_10041E3BD
0x10041e3ad  mov     r8, [rdx+18h]
0x10041e3b1  jmp     short loc_10041E3BD
0x10041e3b3  mov     r8, [rdx+10h]
0x10041e3b7  jmp     short loc_10041E3BD
0x10041e3b9  mov     r8, [rdx+8]
0x10041e3bd  movzx   eax, [rsp+78h+var_58]
0x10041e3c2  imul    rcx, rax, 38h ; '8'
0x10041e3c6  inc     qword ptr [rcx+r8+18h]
0x10041e3cb  lea     rdx, [rsp+78h+var_58]
0x10041e3d0  mov     rcx, r14
0x10041e3d3  call    cs:__imp_?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z; SpinlockBase::Backoff(SpinlockBase::SpinInfo &)
0x10041e3d9  test    byte ptr [rsp+78h+var_38], 1Fh
0x10041e3de  jnz     short loc_10041E3E8
0x10041e3e0  mov     rdi, rbp
0x10041e3e3  jmp     loc_10041E317
0x10041e3e8  lea     rax, [rdi+rdi]
0x10041e3ec  mov     ecx, 2625A0h
0x10041e3f1  cmp     rax, rcx
0x10041e3f4  mov     rdi, rax
0x10041e3f7  cmova   rdi, rcx
0x10041e3fb  jmp     loc_10041E317
0x10041e400  lea     r11, [rsp+78h+var_28]
0x10041e405  mov     rbx, [r11+30h]
0x10041e409  mov     rbp, [r11+38h]
0x10041e40d  mov     rsp, r11
0x10041e410  pop     r15
0x10041e412  pop     r14
0x10041e414  pop     r12
0x10041e416  pop     rdi
0x10041e417  pop     rsi
0x10041e418  retn
```
