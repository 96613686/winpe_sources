# Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)

- ea: `0x10040a800`
- end: `0x10040aaa9`
- name: `?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAX_K@Z`
- size: `681`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100409de0`
- `0x10040a080`
- `0x10040a290`
- `0x100418d20`

## callees

- `0x10040a800`

## import_xrefs

- `sqldk!?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x10040a989`
- `sqldk!SystemThread_TlsOffset` at `0x10040a841`
- `sqldk!SystemThread_TlsIndex` at `0x10040a837`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040a8a6`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040a8a6`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040a8bb`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040a8bb`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10040a939`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10040a939`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10040a94d`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10040a94d`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10040aa63`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10040aa63`
- `sqldk!?sm_SpinIncrement@SOS_PublicGlobals@@2_KA` at `0x10040a99d`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040a87f`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x10040a8c6`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x10040a980`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040a9ae`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040a9ae`

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
  v22[0] = 25;
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
      *(_QWORD *)(*((_QWORD *)SpinlockStats + 1) + 1400LL) += v18;
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
0x10040a800  mov     [rsp+arg_0], rbx
0x10040a805  mov     [rsp+arg_8], rbp
0x10040a80a  push    rsi
0x10040a80b  push    rdi
0x10040a80c  push    r12
0x10040a80e  push    r14
0x10040a810  push    r15
0x10040a812  sub     rsp, 50h
0x10040a816  mov     eax, 19h
0x10040a81b  mov     [rsp+78h+var_54], 1
0x10040a823  mov     [rsp+78h+var_58], ax
0x10040a828  mov     r12, rdx
0x10040a82b  mov     r9, gs:58h
0x10040a834  mov     r14, rcx
0x10040a837  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040a83e  mov     r8d, [rax]
0x10040a841  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040a848  mov     r10d, [rax]
0x10040a84b  add     r10, [r9+r8*8]
0x10040a84f  jz      short loc_10040A874
0x10040a851  cmp     [r10+110h], r10
0x10040a858  jnz     short loc_10040A874
0x10040a85a  mov     rcx, [r10+100h]
0x10040a861  mov     [rsp+78h+var_50], rcx
0x10040a866  test    rcx, rcx
0x10040a869  jz      short loc_10040A87D
0x10040a86b  mov     rcx, [rcx+3E0h]
0x10040a872  jmp     short loc_10040A87F
0x10040a874  mov     [rsp+78h+var_50], 0
0x10040a87d  xor     ecx, ecx
0x10040a87f  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040a886  mov     [rsp+78h+var_48], rcx
0x10040a88b  mov     [rsp+78h+var_40], 0
0x10040a894  mov     [rsp+78h+var_38], 0
0x10040a89c  test    byte ptr [rax], 1
0x10040a89f  jz      short loc_10040A8C6
0x10040a8a1  test    rcx, rcx
0x10040a8a4  jz      short loc_10040A8C6
0x10040a8a6  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x10040a8ac  mov     rcx, rax
0x10040a8af  mov     rax, [rsp+78h+var_48]
0x10040a8b4  movzx   edx, word ptr [rax+0A0h]
0x10040a8bb  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x10040a8c1  mov     [rsp+78h+var_40], rax
0x10040a8c6  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x10040a8cd  mov     r15d, 3Ch ; '<'
0x10040a8d3  mov     ecx, [rax]
0x10040a8d5  mov     rdx, [rsp+78h+var_40]
0x10040a8da  cmp     rcx, r15
0x10040a8dd  mov     edi, ecx
0x10040a8df  cmova   edi, r15d
0x10040a8e3  test    rdx, rdx
0x10040a8e6  jz      loc_10040A980
0x10040a8ec  mov     ebx, [rsp+78h+var_54]
0x10040a8f0  xor     r8d, r8d
0x10040a8f3  movzx   esi, [rsp+78h+var_58]
0x10040a8f8  movzx   ecx, bx
0x10040a8fb  sub     ecx, 1
0x10040a8fe  jz      short loc_10040A921
0x10040a900  sub     ecx, 1
0x10040a903  jz      short loc_10040A91B
0x10040a905  sub     ecx, 1
0x10040a908  jz      short loc_10040A915
0x10040a90a  cmp     ecx, 1
0x10040a90d  jnz     short loc_10040A925
0x10040a90f  mov     r8, [rdx+20h]
0x10040a913  jmp     short loc_10040A925
0x10040a915  mov     r8, [rdx+18h]
0x10040a919  jmp     short loc_10040A925
0x10040a91b  mov     r8, [rdx+10h]
0x10040a91f  jmp     short loc_10040A925
0x10040a921  mov     r8, [rdx+8]
0x10040a925  imul    rcx, rsi, 38h ; '8'
0x10040a929  movzx   edx, si
0x10040a92c  inc     qword ptr [rcx+r8+8]
0x10040a931  mov     r8d, ebx
0x10040a934  mov     rcx, [rsp+78h+var_40]
0x10040a939  call    cs:__imp_?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetSpins(ushort,SPINLOCK_CATEGORY)
0x10040a93f  mov     rcx, [rsp+78h+var_40]
0x10040a944  mov     r8d, ebx
0x10040a947  movzx   edx, si
0x10040a94a  mov     rbp, rax
0x10040a94d  call    cs:__imp_?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetCollisions(ushort,SPINLOCK_CATEGORY)
0x10040a953  mov     rcx, rax
0x10040a956  test    rbp, rbp
0x10040a959  jz      short loc_10040A980
0x10040a95b  test    rax, rax
0x10040a95e  jz      short loc_10040A980
0x10040a960  xor     edx, edx
0x10040a962  mov     rax, rbp
0x10040a965  div     rcx
0x10040a968  mov     rcx, rdi
0x10040a96b  shr     rax, 1
0x10040a96e  cmp     rax, rdi
0x10040a971  cmova   rcx, rax
0x10040a975  imul    rdi, 64h ; 'd'
0x10040a979  cmp     rcx, rdi
0x10040a97c  cmovb   rdi, rcx
0x10040a980  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x10040a987  mov     ecx, [rax]
0x10040a989  mov     rax, cs:__imp_?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_StaggerEnabledForSpinToAcquire
0x10040a990  cmp     rcx, r15
0x10040a993  mov     ebp, ecx
0x10040a995  cmova   rbp, r15
0x10040a999  movzx   r15d, byte ptr [rax]
0x10040a99d  mov     rax, cs:__imp_?sm_SpinIncrement@SOS_PublicGlobals@@2_KA; unsigned __int64 SOS_PublicGlobals::sm_SpinIncrement
0x10040a9a4  mov     rsi, [rax]
0x10040a9a7  xor     ebx, ebx
0x10040a9a9  test    r15b, r15b
0x10040a9ac  jz      short loc_10040A9C0
0x10040a9ae  call    cs:__imp_rand
0x10040a9b4  xor     edx, edx
0x10040a9b6  cdqe
0x10040a9b8  div     rdi
0x10040a9bb  inc     rdx
0x10040a9be  jmp     short loc_10040A9C3
0x10040a9c0  mov     rdx, rdi
0x10040a9c3  test    rdx, rdx
0x10040a9c6  jz      short loc_10040A9DA
0x10040a9c8  nop     dword ptr [rax+rax]
0x10040a9cc  nop     dword ptr [rax+00h]
0x10040a9d0  pause
0x10040a9d2  add     rbx, rsi
0x10040a9d5  cmp     rbx, rdx
0x10040a9d8  jb      short loc_10040A9D0
0x10040a9da  mov     rax, [rsp+78h+var_40]
0x10040a9df  test    rax, rax
0x10040a9e2  jz      short loc_10040A9EF
0x10040a9e4  mov     rax, [rax+8]
0x10040a9e8  add     [rax+578h], rbx
0x10040a9ef  mov     eax, [r14]
0x10040a9f2  test    eax, eax
0x10040a9f4  jnz     short loc_10040AA0D
0x10040a9f6  xor     eax, eax
0x10040a9f8  lock cmpxchg [r14], r12
0x10040a9fd  mov     eax, 0
0x10040aa02  setz    al
0x10040aa05  test    eax, eax
0x10040aa07  jnz     loc_10040AA90
0x10040aa0d  inc     [rsp+78h+var_38]
0x10040aa11  mov     rdx, [rsp+78h+var_40]
0x10040aa16  test    rdx, rdx
0x10040aa19  jz      short loc_10040AA5B
0x10040aa1b  movzx   ecx, word ptr [rsp+78h+var_54]
0x10040aa20  xor     r8d, r8d
0x10040aa23  sub     ecx, 1
0x10040aa26  jz      short loc_10040AA49
0x10040aa28  sub     ecx, 1
0x10040aa2b  jz      short loc_10040AA43
0x10040aa2d  sub     ecx, 1
0x10040aa30  jz      short loc_10040AA3D
0x10040aa32  cmp     ecx, 1
0x10040aa35  jnz     short loc_10040AA4D
0x10040aa37  mov     r8, [rdx+20h]
0x10040aa3b  jmp     short loc_10040AA4D
0x10040aa3d  mov     r8, [rdx+18h]
0x10040aa41  jmp     short loc_10040AA4D
0x10040aa43  mov     r8, [rdx+10h]
0x10040aa47  jmp     short loc_10040AA4D
0x10040aa49  mov     r8, [rdx+8]
0x10040aa4d  movzx   eax, [rsp+78h+var_58]
0x10040aa52  imul    rcx, rax, 38h ; '8'
0x10040aa56  inc     qword ptr [rcx+r8+18h]
0x10040aa5b  lea     rdx, [rsp+78h+var_58]
0x10040aa60  mov     rcx, r14
0x10040aa63  call    cs:__imp_?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z; SpinlockBase::Backoff(SpinlockBase::SpinInfo &)
0x10040aa69  test    byte ptr [rsp+78h+var_38], 1Fh
0x10040aa6e  jnz     short loc_10040AA78
0x10040aa70  mov     rdi, rbp
0x10040aa73  jmp     loc_10040A9A7
0x10040aa78  lea     rax, [rdi+rdi]
0x10040aa7c  mov     ecx, 2625A0h
0x10040aa81  cmp     rax, rcx
0x10040aa84  mov     rdi, rax
0x10040aa87  cmova   rdi, rcx
0x10040aa8b  jmp     loc_10040A9A7
0x10040aa90  lea     r11, [rsp+78h+var_28]
0x10040aa95  mov     rbx, [r11+30h]
0x10040aa99  mov     rbp, [r11+38h]
0x10040aa9d  mov     rsp, r11
0x10040aaa0  pop     r15
0x10040aaa2  pop     r14
0x10040aaa4  pop     r12
0x10040aaa6  pop     rdi
0x10040aaa7  pop     rsi
0x10040aaa8  retn
```
