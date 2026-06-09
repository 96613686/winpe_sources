# Spinlock<26,1,268435713>::SpinToAcquireWithExponentialBackoff(unsigned __int64)

- ea: `0x10045f450`
- end: `0x10045f6ba`
- name: `?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BK@$00$0BAAAABAB@@@AEAAX_K@Z`
- size: `618`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10045e890`
- `0x10045eb60`
- `0x10045ef60`

## callees

- `0x10045f3e0`
- `0x10045f450`

## import_xrefs

- `sqldk!?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x10045f5a0`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x10045f516`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x10045f597`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10045f4cf`
- `sqldk!?sm_SpinIncrement@SOS_PublicGlobals@@2_KA` at `0x10045f5b4`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10045f4f6`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10045f4f6`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10045f50b`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10045f50b`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10045f551`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10045f551`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10045f565`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10045f565`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10045f674`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10045f674`
- `sqldk!SystemThread_TlsIndex` at `0x10045f487`
- `sqldk!SystemThread_TlsOffset` at `0x10045f491`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10045f5c7`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10045f5c7`

## pseudocode

```c
_BOOL8 __fastcall Spinlock<26,1,268435713>::SpinToAcquireWithExponentialBackoff(
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
  v18[0] = 26;
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
      *(_QWORD *)(*((_QWORD *)SpinlockStats + 1) + 1456LL) += v14;
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
0x10045f450  mov     [rsp+arg_0], rbx
0x10045f455  mov     [rsp+arg_8], rbp
0x10045f45a  push    rsi
0x10045f45b  push    rdi
0x10045f45c  push    r12
0x10045f45e  push    r14
0x10045f460  push    r15
0x10045f462  sub     rsp, 50h
0x10045f466  mov     eax, 1Ah
0x10045f46b  mov     [rsp+78h+var_54], 1
0x10045f473  mov     [rsp+78h+var_58], ax
0x10045f478  mov     r12, rdx
0x10045f47b  mov     r9, gs:58h
0x10045f484  mov     r14, rcx
0x10045f487  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10045f48e  mov     r8d, [rax]
0x10045f491  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10045f498  mov     r10d, [rax]
0x10045f49b  add     r10, [r9+r8*8]
0x10045f49f  jz      short loc_10045F4C4
0x10045f4a1  cmp     [r10+110h], r10
0x10045f4a8  jnz     short loc_10045F4C4
0x10045f4aa  mov     rcx, [r10+100h]
0x10045f4b1  mov     [rsp+78h+var_50], rcx
0x10045f4b6  test    rcx, rcx
0x10045f4b9  jz      short loc_10045F4CD
0x10045f4bb  mov     rcx, [rcx+3E0h]
0x10045f4c2  jmp     short loc_10045F4CF
0x10045f4c4  mov     [rsp+78h+var_50], 0
0x10045f4cd  xor     ecx, ecx
0x10045f4cf  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10045f4d6  mov     [rsp+78h+var_48], rcx
0x10045f4db  mov     [rsp+78h+var_40], 0
0x10045f4e4  mov     [rsp+78h+var_38], 0
0x10045f4ec  test    byte ptr [rax], 1
0x10045f4ef  jz      short loc_10045F516
0x10045f4f1  test    rcx, rcx
0x10045f4f4  jz      short loc_10045F516
0x10045f4f6  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x10045f4fc  mov     rcx, rax
0x10045f4ff  mov     rax, [rsp+78h+var_48]
0x10045f504  movzx   edx, word ptr [rax+0A0h]
0x10045f50b  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x10045f511  mov     [rsp+78h+var_40], rax
0x10045f516  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x10045f51d  mov     r15d, 3Ch ; '<'
0x10045f523  mov     ecx, [rax]
0x10045f525  cmp     rcx, r15
0x10045f528  mov     esi, ecx
0x10045f52a  mov     rcx, [rsp+78h+var_40]
0x10045f52f  cmova   esi, r15d
0x10045f533  test    rcx, rcx
0x10045f536  jz      short loc_10045F597
0x10045f538  movzx   edi, [rsp+78h+var_58]
0x10045f53d  mov     ebx, [rsp+78h+var_54]
0x10045f541  movzx   edx, di
0x10045f544  mov     r8d, ebx
0x10045f547  call    ?IncrementCollisions@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::IncrementCollisions(ushort,SPINLOCK_CATEGORY)
0x10045f54c  mov     rcx, [rsp+78h+var_40]
0x10045f551  call    cs:__imp_?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetSpins(ushort,SPINLOCK_CATEGORY)
0x10045f557  mov     rcx, [rsp+78h+var_40]
0x10045f55c  mov     r8d, ebx
0x10045f55f  movzx   edx, di
0x10045f562  mov     rbp, rax
0x10045f565  call    cs:__imp_?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetCollisions(ushort,SPINLOCK_CATEGORY)
0x10045f56b  mov     rcx, rax
0x10045f56e  test    rbp, rbp
0x10045f571  jz      short loc_10045F597
0x10045f573  test    rax, rax
0x10045f576  jz      short loc_10045F597
0x10045f578  xor     edx, edx
0x10045f57a  mov     rax, rbp
0x10045f57d  div     rcx
0x10045f580  mov     ecx, esi
0x10045f582  shr     rax, 1
0x10045f585  cmp     rax, rsi
0x10045f588  cmova   rcx, rax
0x10045f58c  imul    rsi, 64h ; 'd'
0x10045f590  cmp     rcx, rsi
0x10045f593  cmovb   rsi, rcx
0x10045f597  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x10045f59e  mov     ecx, [rax]
0x10045f5a0  mov     rax, cs:__imp_?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_StaggerEnabledForSpinToAcquire
0x10045f5a7  cmp     rcx, r15
0x10045f5aa  mov     ebp, ecx
0x10045f5ac  cmova   rbp, r15
0x10045f5b0  movzx   r15d, byte ptr [rax]
0x10045f5b4  mov     rax, cs:__imp_?sm_SpinIncrement@SOS_PublicGlobals@@2_KA; unsigned __int64 SOS_PublicGlobals::sm_SpinIncrement
0x10045f5bb  mov     rdi, [rax]
0x10045f5be  xchg    ax, ax
0x10045f5c0  xor     ebx, ebx
0x10045f5c2  test    r15b, r15b
0x10045f5c5  jz      short loc_10045F5D9
0x10045f5c7  call    cs:__imp_rand
0x10045f5cd  xor     edx, edx
0x10045f5cf  cdqe
0x10045f5d1  div     rsi
0x10045f5d4  inc     rdx
0x10045f5d7  jmp     short loc_10045F5DC
0x10045f5d9  mov     rdx, rsi
0x10045f5dc  test    rdx, rdx
0x10045f5df  jz      short loc_10045F5EB
0x10045f5e1  pause
0x10045f5e3  add     rbx, rdi
0x10045f5e6  cmp     rbx, rdx
0x10045f5e9  jb      short loc_10045F5E1
0x10045f5eb  mov     rax, [rsp+78h+var_40]
0x10045f5f0  test    rax, rax
0x10045f5f3  jz      short loc_10045F600
0x10045f5f5  mov     rax, [rax+8]
0x10045f5f9  add     [rax+5B0h], rbx
0x10045f600  mov     eax, [r14]
0x10045f603  test    eax, eax
0x10045f605  jnz     short loc_10045F61E
0x10045f607  xor     eax, eax
0x10045f609  lock cmpxchg [r14], r12
0x10045f60e  mov     eax, 0
0x10045f613  setz    al
0x10045f616  test    eax, eax
0x10045f618  jnz     loc_10045F6A1
0x10045f61e  inc     [rsp+78h+var_38]
0x10045f622  mov     rdx, [rsp+78h+var_40]
0x10045f627  test    rdx, rdx
0x10045f62a  jz      short loc_10045F66C
0x10045f62c  movzx   ecx, word ptr [rsp+78h+var_54]
0x10045f631  xor     r8d, r8d
0x10045f634  sub     ecx, 1
0x10045f637  jz      short loc_10045F65A
0x10045f639  sub     ecx, 1
0x10045f63c  jz      short loc_10045F654
0x10045f63e  sub     ecx, 1
0x10045f641  jz      short loc_10045F64E
0x10045f643  cmp     ecx, 1
0x10045f646  jnz     short loc_10045F65E
0x10045f648  mov     r8, [rdx+20h]
0x10045f64c  jmp     short loc_10045F65E
0x10045f64e  mov     r8, [rdx+18h]
0x10045f652  jmp     short loc_10045F65E
0x10045f654  mov     r8, [rdx+10h]
0x10045f658  jmp     short loc_10045F65E
0x10045f65a  mov     r8, [rdx+8]
0x10045f65e  movzx   eax, [rsp+78h+var_58]
0x10045f663  imul    rcx, rax, 38h ; '8'
0x10045f667  inc     qword ptr [rcx+r8+18h]
0x10045f66c  lea     rdx, [rsp+78h+var_58]
0x10045f671  mov     rcx, r14
0x10045f674  call    cs:__imp_?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z; SpinlockBase::Backoff(SpinlockBase::SpinInfo &)
0x10045f67a  test    byte ptr [rsp+78h+var_38], 1Fh
0x10045f67f  jnz     short loc_10045F689
0x10045f681  mov     rsi, rbp
0x10045f684  jmp     loc_10045F5C0
0x10045f689  lea     rax, [rsi+rsi]
0x10045f68d  mov     ecx, 2625A0h
0x10045f692  cmp     rax, rcx
0x10045f695  mov     rsi, rax
0x10045f698  cmova   rsi, rcx
0x10045f69c  jmp     loc_10045F5C0
0x10045f6a1  lea     r11, [rsp+78h+var_28]
0x10045f6a6  mov     rbx, [r11+30h]
0x10045f6aa  mov     rbp, [r11+38h]
0x10045f6ae  mov     rsp, r11
0x10045f6b1  pop     r15
0x10045f6b3  pop     r14
0x10045f6b5  pop     r12
0x10045f6b7  pop     rdi
0x10045f6b8  pop     rsi
0x10045f6b9  retn
```
