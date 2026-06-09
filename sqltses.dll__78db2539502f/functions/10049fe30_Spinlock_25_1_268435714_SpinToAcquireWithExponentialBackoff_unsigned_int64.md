# Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)

- ea: `0x10049fe30`
- end: `0x1004a009a`
- name: `?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAX_K@Z`
- size: `618`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10049f510`
- `0x10049f780`
- `0x10049f9a0`
- `0x100836c60`
- `0x100837f80`

## callees

- `0x10045f3e0`
- `0x10049fe30`

## import_xrefs

- `sqldk!?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x10049ff80`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x10049fef6`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x10049ff77`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10049feaf`
- `sqldk!?sm_SpinIncrement@SOS_PublicGlobals@@2_KA` at `0x10049ff94`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10049fed6`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10049fed6`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10049feeb`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10049feeb`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10049ff31`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10049ff31`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10049ff45`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10049ff45`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x1004a0054`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x1004a0054`
- `sqldk!SystemThread_TlsIndex` at `0x10049fe67`
- `sqldk!SystemThread_TlsOffset` at `0x10049fe71`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10049ffa7`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10049ffa7`

## pseudocode

```c
_BOOL8 __fastcall Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(
        volatile signed __int64 *a1,
        signed __int64 a2)
{
  __int64 v4; // r10
  __int64 v5; // rcx
  __int64 v6; // rcx
  PerProcessGlobals *SOSProcessGlobals; // rax
  unsigned __int64 v8; // rsi
  unsigned __int64 Spins; // rbp
  unsigned __int64 Collisions; // rax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rax
  __int64 v13; // rbp
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rdx
  _BOOL8 result; // rax
  __int64 v17; // r8
  unsigned __int16 v18[2]; // [rsp+20h] [rbp-58h] BYREF
  unsigned int v19; // [rsp+24h] [rbp-54h]
  __int64 v20; // [rsp+28h] [rbp-50h]
  __int64 v21; // [rsp+30h] [rbp-48h]
  struct SpinlockStat *SpinlockStats; // [rsp+38h] [rbp-40h]
  int v23; // [rsp+40h] [rbp-38h]

  v19 = 1;
  v18[0] = 25;
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  if ( !v4 || *(_QWORD *)(v4 + 272) != v4 )
  {
    v20 = 0;
    goto LABEL_6;
  }
  v5 = *(_QWORD *)(v4 + 256);
  v20 = v5;
  if ( !v5 )
  {
LABEL_6:
    v6 = 0;
    goto LABEL_7;
  }
  v6 = *(_QWORD *)(v5 + 992);
LABEL_7:
  v21 = v6;
  SpinlockStats = 0;
  v23 = 0;
  if ( (SOS_PublicGlobals::sm_osStats & 1) != 0 && v6 )
  {
    SOSProcessGlobals = (PerProcessGlobals *)SOS_OS::GetSOSProcessGlobals();
    SpinlockStats = PerProcessGlobals::GetSpinlockStats(SOSProcessGlobals, *(_WORD *)(v21 + 160));
  }
  v8 = SOS_PublicGlobals::sm_cpuCount;
  if ( SOS_PublicGlobals::sm_cpuCount > 0x3CuLL )
    v8 = 60;
  if ( SpinlockStats )
  {
    SpinlockStat::IncrementCollisions(SpinlockStats, v18[0], v19);
    Spins = SpinlockStat::GetSpins(SpinlockStats);
    Collisions = SpinlockStat::GetCollisions(SpinlockStats, v18[0], v19);
    if ( Spins )
    {
      if ( Collisions )
      {
        v11 = (unsigned int)v8;
        v12 = (Spins / Collisions) >> 1;
        if ( v12 > v8 )
          v11 = v12;
        v8 *= 100LL;
        if ( v11 < v8 )
          v8 = v11;
      }
    }
  }
  v13 = SOS_PublicGlobals::sm_cpuCount;
  if ( SOS_PublicGlobals::sm_cpuCount > 0x3CuLL )
    v13 = 60;
  while ( 1 )
  {
    v14 = 0;
    if ( SOS_PublicGlobals::sm_StaggerEnabledForSpinToAcquire )
      v15 = rand() % v8 + 1;
    else
      v15 = v8;
    if ( v15 )
    {
      do
      {
        _mm_pause();
        v14 += SOS_PublicGlobals::sm_SpinIncrement;
      }
      while ( v14 < v15 );
    }
    if ( SpinlockStats )
      *(_QWORD *)(*((_QWORD *)SpinlockStats + 1) + 1400LL) += v14;
    if ( !*(_DWORD *)a1 )
    {
      result = _InterlockedCompareExchange64(a1, a2, 0) == 0;
      if ( result )
        break;
    }
    ++v23;
    if ( SpinlockStats )
    {
      v17 = 0;
      switch ( (unsigned __int16)v19 )
      {
        case 1u:
          v17 = *((_QWORD *)SpinlockStats + 1);
          break;
        case 2u:
          v17 = *((_QWORD *)SpinlockStats + 2);
          break;
        case 3u:
          v17 = *((_QWORD *)SpinlockStats + 3);
          break;
        case 4u:
          v17 = *((_QWORD *)SpinlockStats + 4);
          break;
      }
      ++*(_QWORD *)(56LL * v18[0] + v17 + 24);
    }
    SpinlockBase::Backoff((SpinlockBase *)a1, (struct SpinlockBase::SpinInfo *)v18);
    if ( (v23 & 0x1F) != 0 )
    {
      v8 *= 2LL;
      if ( v8 > 0x2625A0 )
        v8 = 2500000;
    }
    else
    {
      v8 = v13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10049fe30  mov     [rsp+arg_0], rbx
0x10049fe35  mov     [rsp+arg_8], rbp
0x10049fe3a  push    rsi
0x10049fe3b  push    rdi
0x10049fe3c  push    r12
0x10049fe3e  push    r14
0x10049fe40  push    r15
0x10049fe42  sub     rsp, 50h
0x10049fe46  mov     eax, 19h
0x10049fe4b  mov     [rsp+78h+var_54], 1
0x10049fe53  mov     [rsp+78h+var_58], ax
0x10049fe58  mov     r12, rdx
0x10049fe5b  mov     r9, gs:58h
0x10049fe64  mov     r14, rcx
0x10049fe67  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10049fe6e  mov     r8d, [rax]
0x10049fe71  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10049fe78  mov     r10d, [rax]
0x10049fe7b  add     r10, [r9+r8*8]
0x10049fe7f  jz      short loc_10049FEA4
0x10049fe81  cmp     [r10+110h], r10
0x10049fe88  jnz     short loc_10049FEA4
0x10049fe8a  mov     rcx, [r10+100h]
0x10049fe91  mov     [rsp+78h+var_50], rcx
0x10049fe96  test    rcx, rcx
0x10049fe99  jz      short loc_10049FEAD
0x10049fe9b  mov     rcx, [rcx+3E0h]
0x10049fea2  jmp     short loc_10049FEAF
0x10049fea4  mov     [rsp+78h+var_50], 0
0x10049fead  xor     ecx, ecx
0x10049feaf  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10049feb6  mov     [rsp+78h+var_48], rcx
0x10049febb  mov     [rsp+78h+var_40], 0
0x10049fec4  mov     [rsp+78h+var_38], 0
0x10049fecc  test    byte ptr [rax], 1
0x10049fecf  jz      short loc_10049FEF6
0x10049fed1  test    rcx, rcx
0x10049fed4  jz      short loc_10049FEF6
0x10049fed6  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x10049fedc  mov     rcx, rax
0x10049fedf  mov     rax, [rsp+78h+var_48]
0x10049fee4  movzx   edx, word ptr [rax+0A0h]
0x10049feeb  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x10049fef1  mov     [rsp+78h+var_40], rax
0x10049fef6  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x10049fefd  mov     r15d, 3Ch ; '<'
0x10049ff03  mov     ecx, [rax]
0x10049ff05  cmp     rcx, r15
0x10049ff08  mov     esi, ecx
0x10049ff0a  mov     rcx, [rsp+78h+var_40]
0x10049ff0f  cmova   esi, r15d
0x10049ff13  test    rcx, rcx
0x10049ff16  jz      short loc_10049FF77
0x10049ff18  movzx   edi, [rsp+78h+var_58]
0x10049ff1d  mov     ebx, [rsp+78h+var_54]
0x10049ff21  movzx   edx, di
0x10049ff24  mov     r8d, ebx
0x10049ff27  call    ?IncrementCollisions@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::IncrementCollisions(ushort,SPINLOCK_CATEGORY)
0x10049ff2c  mov     rcx, [rsp+78h+var_40]
0x10049ff31  call    cs:__imp_?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetSpins(ushort,SPINLOCK_CATEGORY)
0x10049ff37  mov     rcx, [rsp+78h+var_40]
0x10049ff3c  mov     r8d, ebx
0x10049ff3f  movzx   edx, di
0x10049ff42  mov     rbp, rax
0x10049ff45  call    cs:__imp_?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetCollisions(ushort,SPINLOCK_CATEGORY)
0x10049ff4b  mov     rcx, rax
0x10049ff4e  test    rbp, rbp
0x10049ff51  jz      short loc_10049FF77
0x10049ff53  test    rax, rax
0x10049ff56  jz      short loc_10049FF77
0x10049ff58  xor     edx, edx
0x10049ff5a  mov     rax, rbp
0x10049ff5d  div     rcx
0x10049ff60  mov     ecx, esi
0x10049ff62  shr     rax, 1
0x10049ff65  cmp     rax, rsi
0x10049ff68  cmova   rcx, rax
0x10049ff6c  imul    rsi, 64h ; 'd'
0x10049ff70  cmp     rcx, rsi
0x10049ff73  cmovb   rsi, rcx
0x10049ff77  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x10049ff7e  mov     ecx, [rax]
0x10049ff80  mov     rax, cs:__imp_?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_StaggerEnabledForSpinToAcquire
0x10049ff87  cmp     rcx, r15
0x10049ff8a  mov     ebp, ecx
0x10049ff8c  cmova   rbp, r15
0x10049ff90  movzx   r15d, byte ptr [rax]
0x10049ff94  mov     rax, cs:__imp_?sm_SpinIncrement@SOS_PublicGlobals@@2_KA; unsigned __int64 SOS_PublicGlobals::sm_SpinIncrement
0x10049ff9b  mov     rdi, [rax]
0x10049ff9e  xchg    ax, ax
0x10049ffa0  xor     ebx, ebx
0x10049ffa2  test    r15b, r15b
0x10049ffa5  jz      short loc_10049FFB9
0x10049ffa7  call    cs:__imp_rand
0x10049ffad  xor     edx, edx
0x10049ffaf  cdqe
0x10049ffb1  div     rsi
0x10049ffb4  inc     rdx
0x10049ffb7  jmp     short loc_10049FFBC
0x10049ffb9  mov     rdx, rsi
0x10049ffbc  test    rdx, rdx
0x10049ffbf  jz      short loc_10049FFCB
0x10049ffc1  pause
0x10049ffc3  add     rbx, rdi
0x10049ffc6  cmp     rbx, rdx
0x10049ffc9  jb      short loc_10049FFC1
0x10049ffcb  mov     rax, [rsp+78h+var_40]
0x10049ffd0  test    rax, rax
0x10049ffd3  jz      short loc_10049FFE0
0x10049ffd5  mov     rax, [rax+8]
0x10049ffd9  add     [rax+578h], rbx
0x10049ffe0  mov     eax, [r14]
0x10049ffe3  test    eax, eax
0x10049ffe5  jnz     short loc_10049FFFE
0x10049ffe7  xor     eax, eax
0x10049ffe9  lock cmpxchg [r14], r12
0x10049ffee  mov     eax, 0
0x10049fff3  setz    al
0x10049fff6  test    eax, eax
0x10049fff8  jnz     loc_1004A0081
0x10049fffe  inc     [rsp+78h+var_38]
0x1004a0002  mov     rdx, [rsp+78h+var_40]
0x1004a0007  test    rdx, rdx
0x1004a000a  jz      short loc_1004A004C
0x1004a000c  movzx   ecx, word ptr [rsp+78h+var_54]
0x1004a0011  xor     r8d, r8d
0x1004a0014  sub     ecx, 1
0x1004a0017  jz      short loc_1004A003A
0x1004a0019  sub     ecx, 1
0x1004a001c  jz      short loc_1004A0034
0x1004a001e  sub     ecx, 1
0x1004a0021  jz      short loc_1004A002E
0x1004a0023  cmp     ecx, 1
0x1004a0026  jnz     short loc_1004A003E
0x1004a0028  mov     r8, [rdx+20h]
0x1004a002c  jmp     short loc_1004A003E
0x1004a002e  mov     r8, [rdx+18h]
0x1004a0032  jmp     short loc_1004A003E
0x1004a0034  mov     r8, [rdx+10h]
0x1004a0038  jmp     short loc_1004A003E
0x1004a003a  mov     r8, [rdx+8]
0x1004a003e  movzx   eax, [rsp+78h+var_58]
0x1004a0043  imul    rcx, rax, 38h ; '8'
0x1004a0047  inc     qword ptr [rcx+r8+18h]
0x1004a004c  lea     rdx, [rsp+78h+var_58]
0x1004a0051  mov     rcx, r14
0x1004a0054  call    cs:__imp_?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z; SpinlockBase::Backoff(SpinlockBase::SpinInfo &)
0x1004a005a  test    byte ptr [rsp+78h+var_38], 1Fh
0x1004a005f  jnz     short loc_1004A0069
0x1004a0061  mov     rsi, rbp
0x1004a0064  jmp     loc_10049FFA0
0x1004a0069  lea     rax, [rsi+rsi]
0x1004a006d  mov     ecx, 2625A0h
0x1004a0072  cmp     rax, rcx
0x1004a0075  mov     rsi, rax
0x1004a0078  cmova   rsi, rcx
0x1004a007c  jmp     loc_10049FFA0
0x1004a0081  lea     r11, [rsp+78h+var_28]
0x1004a0086  mov     rbx, [r11+30h]
0x1004a008a  mov     rbp, [r11+38h]
0x1004a008e  mov     rsp, r11
0x1004a0091  pop     r15
0x1004a0093  pop     r14
0x1004a0095  pop     r12
0x1004a0097  pop     rdi
0x1004a0098  pop     rsi
0x1004a0099  retn
```
