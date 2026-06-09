# Spinlock<19,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)

- ea: `0x100408b50`
- end: `0x100408df9`
- name: `?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAX_K@Z`
- size: `681`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100408160`
- `0x100409760`
- `0x10040abb0`
- `0x10040ad90`
- `0x10040af70`
- `0x10041e640`

## callees

- `0x100408b50`

## import_xrefs

- `sqldk!?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x100408cd9`
- `sqldk!SystemThread_TlsOffset` at `0x100408b91`
- `sqldk!SystemThread_TlsIndex` at `0x100408b87`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100408bf6`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100408bf6`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100408c0b`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100408c0b`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x100408c89`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x100408c89`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x100408c9d`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x100408c9d`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x100408db3`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x100408db3`
- `sqldk!?sm_SpinIncrement@SOS_PublicGlobals@@2_KA` at `0x100408ced`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100408bcf`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x100408c16`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x100408cd0`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100408cfe`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100408cfe`

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
0x100408b50  mov     [rsp+arg_0], rbx
0x100408b55  mov     [rsp+arg_8], rbp
0x100408b5a  push    rsi
0x100408b5b  push    rdi
0x100408b5c  push    r12
0x100408b5e  push    r14
0x100408b60  push    r15
0x100408b62  sub     rsp, 50h
0x100408b66  mov     eax, 13h
0x100408b6b  mov     [rsp+78h+var_54], 1
0x100408b73  mov     [rsp+78h+var_58], ax
0x100408b78  mov     r12, rdx
0x100408b7b  mov     r9, gs:58h
0x100408b84  mov     r14, rcx
0x100408b87  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100408b8e  mov     r8d, [rax]
0x100408b91  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100408b98  mov     r10d, [rax]
0x100408b9b  add     r10, [r9+r8*8]
0x100408b9f  jz      short loc_100408BC4
0x100408ba1  cmp     [r10+110h], r10
0x100408ba8  jnz     short loc_100408BC4
0x100408baa  mov     rcx, [r10+100h]
0x100408bb1  mov     [rsp+78h+var_50], rcx
0x100408bb6  test    rcx, rcx
0x100408bb9  jz      short loc_100408BCD
0x100408bbb  mov     rcx, [rcx+3E0h]
0x100408bc2  jmp     short loc_100408BCF
0x100408bc4  mov     [rsp+78h+var_50], 0
0x100408bcd  xor     ecx, ecx
0x100408bcf  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100408bd6  mov     [rsp+78h+var_48], rcx
0x100408bdb  mov     [rsp+78h+var_40], 0
0x100408be4  mov     [rsp+78h+var_38], 0
0x100408bec  test    byte ptr [rax], 1
0x100408bef  jz      short loc_100408C16
0x100408bf1  test    rcx, rcx
0x100408bf4  jz      short loc_100408C16
0x100408bf6  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x100408bfc  mov     rcx, rax
0x100408bff  mov     rax, [rsp+78h+var_48]
0x100408c04  movzx   edx, word ptr [rax+0A0h]
0x100408c0b  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x100408c11  mov     [rsp+78h+var_40], rax
0x100408c16  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x100408c1d  mov     r15d, 3Ch ; '<'
0x100408c23  mov     ecx, [rax]
0x100408c25  mov     rdx, [rsp+78h+var_40]
0x100408c2a  cmp     rcx, r15
0x100408c2d  mov     edi, ecx
0x100408c2f  cmova   edi, r15d
0x100408c33  test    rdx, rdx
0x100408c36  jz      loc_100408CD0
0x100408c3c  mov     ebx, [rsp+78h+var_54]
0x100408c40  xor     r8d, r8d
0x100408c43  movzx   esi, [rsp+78h+var_58]
0x100408c48  movzx   ecx, bx
0x100408c4b  sub     ecx, 1
0x100408c4e  jz      short loc_100408C71
0x100408c50  sub     ecx, 1
0x100408c53  jz      short loc_100408C6B
0x100408c55  sub     ecx, 1
0x100408c58  jz      short loc_100408C65
0x100408c5a  cmp     ecx, 1
0x100408c5d  jnz     short loc_100408C75
0x100408c5f  mov     r8, [rdx+20h]
0x100408c63  jmp     short loc_100408C75
0x100408c65  mov     r8, [rdx+18h]
0x100408c69  jmp     short loc_100408C75
0x100408c6b  mov     r8, [rdx+10h]
0x100408c6f  jmp     short loc_100408C75
0x100408c71  mov     r8, [rdx+8]
0x100408c75  imul    rcx, rsi, 38h ; '8'
0x100408c79  movzx   edx, si
0x100408c7c  inc     qword ptr [rcx+r8+8]
0x100408c81  mov     r8d, ebx
0x100408c84  mov     rcx, [rsp+78h+var_40]
0x100408c89  call    cs:__imp_?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetSpins(ushort,SPINLOCK_CATEGORY)
0x100408c8f  mov     rcx, [rsp+78h+var_40]
0x100408c94  mov     r8d, ebx
0x100408c97  movzx   edx, si
0x100408c9a  mov     rbp, rax
0x100408c9d  call    cs:__imp_?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetCollisions(ushort,SPINLOCK_CATEGORY)
0x100408ca3  mov     rcx, rax
0x100408ca6  test    rbp, rbp
0x100408ca9  jz      short loc_100408CD0
0x100408cab  test    rax, rax
0x100408cae  jz      short loc_100408CD0
0x100408cb0  xor     edx, edx
0x100408cb2  mov     rax, rbp
0x100408cb5  div     rcx
0x100408cb8  mov     rcx, rdi
0x100408cbb  shr     rax, 1
0x100408cbe  cmp     rax, rdi
0x100408cc1  cmova   rcx, rax
0x100408cc5  imul    rdi, 64h ; 'd'
0x100408cc9  cmp     rcx, rdi
0x100408ccc  cmovb   rdi, rcx
0x100408cd0  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x100408cd7  mov     ecx, [rax]
0x100408cd9  mov     rax, cs:__imp_?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_StaggerEnabledForSpinToAcquire
0x100408ce0  cmp     rcx, r15
0x100408ce3  mov     ebp, ecx
0x100408ce5  cmova   rbp, r15
0x100408ce9  movzx   r15d, byte ptr [rax]
0x100408ced  mov     rax, cs:__imp_?sm_SpinIncrement@SOS_PublicGlobals@@2_KA; unsigned __int64 SOS_PublicGlobals::sm_SpinIncrement
0x100408cf4  mov     rsi, [rax]
0x100408cf7  xor     ebx, ebx
0x100408cf9  test    r15b, r15b
0x100408cfc  jz      short loc_100408D10
0x100408cfe  call    cs:__imp_rand
0x100408d04  xor     edx, edx
0x100408d06  cdqe
0x100408d08  div     rdi
0x100408d0b  inc     rdx
0x100408d0e  jmp     short loc_100408D13
0x100408d10  mov     rdx, rdi
0x100408d13  test    rdx, rdx
0x100408d16  jz      short loc_100408D2A
0x100408d18  nop     dword ptr [rax+rax]
0x100408d1c  nop     dword ptr [rax+00h]
0x100408d20  pause
0x100408d22  add     rbx, rsi
0x100408d25  cmp     rbx, rdx
0x100408d28  jb      short loc_100408D20
0x100408d2a  mov     rax, [rsp+78h+var_40]
0x100408d2f  test    rax, rax
0x100408d32  jz      short loc_100408D3F
0x100408d34  mov     rax, [rax+8]
0x100408d38  add     [rax+428h], rbx
0x100408d3f  mov     eax, [r14]
0x100408d42  test    eax, eax
0x100408d44  jnz     short loc_100408D5D
0x100408d46  xor     eax, eax
0x100408d48  lock cmpxchg [r14], r12
0x100408d4d  mov     eax, 0
0x100408d52  setz    al
0x100408d55  test    eax, eax
0x100408d57  jnz     loc_100408DE0
0x100408d5d  inc     [rsp+78h+var_38]
0x100408d61  mov     rdx, [rsp+78h+var_40]
0x100408d66  test    rdx, rdx
0x100408d69  jz      short loc_100408DAB
0x100408d6b  movzx   ecx, word ptr [rsp+78h+var_54]
0x100408d70  xor     r8d, r8d
0x100408d73  sub     ecx, 1
0x100408d76  jz      short loc_100408D99
0x100408d78  sub     ecx, 1
0x100408d7b  jz      short loc_100408D93
0x100408d7d  sub     ecx, 1
0x100408d80  jz      short loc_100408D8D
0x100408d82  cmp     ecx, 1
0x100408d85  jnz     short loc_100408D9D
0x100408d87  mov     r8, [rdx+20h]
0x100408d8b  jmp     short loc_100408D9D
0x100408d8d  mov     r8, [rdx+18h]
0x100408d91  jmp     short loc_100408D9D
0x100408d93  mov     r8, [rdx+10h]
0x100408d97  jmp     short loc_100408D9D
0x100408d99  mov     r8, [rdx+8]
0x100408d9d  movzx   eax, [rsp+78h+var_58]
0x100408da2  imul    rcx, rax, 38h ; '8'
0x100408da6  inc     qword ptr [rcx+r8+18h]
0x100408dab  lea     rdx, [rsp+78h+var_58]
0x100408db0  mov     rcx, r14
0x100408db3  call    cs:__imp_?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z; SpinlockBase::Backoff(SpinlockBase::SpinInfo &)
0x100408db9  test    byte ptr [rsp+78h+var_38], 1Fh
0x100408dbe  jnz     short loc_100408DC8
0x100408dc0  mov     rdi, rbp
0x100408dc3  jmp     loc_100408CF7
0x100408dc8  lea     rax, [rdi+rdi]
0x100408dcc  mov     ecx, 2625A0h
0x100408dd1  cmp     rax, rcx
0x100408dd4  mov     rdi, rax
0x100408dd7  cmova   rdi, rcx
0x100408ddb  jmp     loc_100408CF7
0x100408de0  lea     r11, [rsp+78h+var_28]
0x100408de5  mov     rbx, [r11+30h]
0x100408de9  mov     rbp, [r11+38h]
0x100408ded  mov     rsp, r11
0x100408df0  pop     r15
0x100408df2  pop     r14
0x100408df4  pop     r12
0x100408df6  pop     rdi
0x100408df7  pop     rsi
0x100408df8  retn
```
