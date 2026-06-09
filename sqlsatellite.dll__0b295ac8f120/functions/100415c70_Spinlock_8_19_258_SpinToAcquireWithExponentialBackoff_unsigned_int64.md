# Spinlock<8,19,258>::SpinToAcquireWithExponentialBackoff(unsigned __int64)

- ea: `0x100415c70`
- end: `0x100415f19`
- name: `?SpinToAcquireWithExponentialBackoff@?$Spinlock@$07$0BD@$0BAC@@@AEAAX_K@Z`
- size: `681`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100412320`
- `0x100413220`
- `0x1004700c0`
- `0x100470280`
- `0x100471430`
- `0x100471880`
- `0x100472d40`
- `0x100472f00`
- `0x100474660`
- `0x100475fd0`

## callees

- `0x100415c70`

## import_xrefs

- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x100415d36`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x100415df0`
- `sqldk!?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x100415df9`
- `sqldk!?sm_SpinIncrement@SOS_PublicGlobals@@2_KA` at `0x100415e0d`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x100415da9`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x100415da9`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x100415dbd`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x100415dbd`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x100415ed3`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x100415ed3`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100415d2b`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100415d2b`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100415d16`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100415d16`
- `sqldk!SystemThread_TlsIndex` at `0x100415ca7`
- `sqldk!SystemThread_TlsOffset` at `0x100415cb1`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100415cef`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100415e1e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100415e1e`

## pseudocode

```c
_BOOL8 __fastcall Spinlock<8,19,258>::SpinToAcquireWithExponentialBackoff(
        volatile signed __int64 *a1,
        signed __int64 a2)
{
  __int64 v4; // r10
  __int64 v5; // rcx
  __int64 v6; // rcx
  PerProcessGlobals *ClientProcessGlobals; // rax
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

  v23 = 3;
  v22[0] = 8;
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
    ClientProcessGlobals = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
    SpinlockStats = PerProcessGlobals::GetSpinlockStats(ClientProcessGlobals, *(_WORD *)(v25 + 160));
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
      *(_QWORD *)(*((_QWORD *)SpinlockStats + 3) + 448LL) += v18;
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
0x100415c70  mov     [rsp+arg_0], rbx
0x100415c75  mov     [rsp+arg_8], rbp
0x100415c7a  push    rsi
0x100415c7b  push    rdi
0x100415c7c  push    r12
0x100415c7e  push    r14
0x100415c80  push    r15
0x100415c82  sub     rsp, 50h
0x100415c86  mov     eax, 8
0x100415c8b  mov     [rsp+78h+var_54], 3
0x100415c93  mov     [rsp+78h+var_58], ax
0x100415c98  mov     r12, rdx
0x100415c9b  mov     r9, gs:58h
0x100415ca4  mov     r14, rcx
0x100415ca7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100415cae  mov     r8d, [rax]
0x100415cb1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100415cb8  mov     r10d, [rax]
0x100415cbb  add     r10, [r9+r8*8]
0x100415cbf  jz      short loc_100415CE4
0x100415cc1  cmp     [r10+110h], r10
0x100415cc8  jnz     short loc_100415CE4
0x100415cca  mov     rcx, [r10+100h]
0x100415cd1  mov     [rsp+78h+var_50], rcx
0x100415cd6  test    rcx, rcx
0x100415cd9  jz      short loc_100415CED
0x100415cdb  mov     rcx, [rcx+3E0h]
0x100415ce2  jmp     short loc_100415CEF
0x100415ce4  mov     [rsp+78h+var_50], 0
0x100415ced  xor     ecx, ecx
0x100415cef  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100415cf6  mov     [rsp+78h+var_48], rcx
0x100415cfb  mov     [rsp+78h+var_40], 0
0x100415d04  mov     [rsp+78h+var_38], 0
0x100415d0c  test    byte ptr [rax], 1
0x100415d0f  jz      short loc_100415D36
0x100415d11  test    rcx, rcx
0x100415d14  jz      short loc_100415D36
0x100415d16  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x100415d1c  mov     rcx, rax
0x100415d1f  mov     rax, [rsp+78h+var_48]
0x100415d24  movzx   edx, word ptr [rax+0A0h]
0x100415d2b  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x100415d31  mov     [rsp+78h+var_40], rax
0x100415d36  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x100415d3d  mov     r15d, 3Ch ; '<'
0x100415d43  mov     ecx, [rax]
0x100415d45  mov     rdx, [rsp+78h+var_40]
0x100415d4a  cmp     rcx, r15
0x100415d4d  mov     edi, ecx
0x100415d4f  cmova   edi, r15d
0x100415d53  test    rdx, rdx
0x100415d56  jz      loc_100415DF0
0x100415d5c  mov     ebx, [rsp+78h+var_54]
0x100415d60  xor     r8d, r8d
0x100415d63  movzx   esi, [rsp+78h+var_58]
0x100415d68  movzx   ecx, bx
0x100415d6b  sub     ecx, 1
0x100415d6e  jz      short loc_100415D91
0x100415d70  sub     ecx, 1
0x100415d73  jz      short loc_100415D8B
0x100415d75  sub     ecx, 1
0x100415d78  jz      short loc_100415D85
0x100415d7a  cmp     ecx, 1
0x100415d7d  jnz     short loc_100415D95
0x100415d7f  mov     r8, [rdx+20h]
0x100415d83  jmp     short loc_100415D95
0x100415d85  mov     r8, [rdx+18h]
0x100415d89  jmp     short loc_100415D95
0x100415d8b  mov     r8, [rdx+10h]
0x100415d8f  jmp     short loc_100415D95
0x100415d91  mov     r8, [rdx+8]
0x100415d95  imul    rcx, rsi, 38h ; '8'
0x100415d99  movzx   edx, si
0x100415d9c  inc     qword ptr [rcx+r8+8]
0x100415da1  mov     r8d, ebx
0x100415da4  mov     rcx, [rsp+78h+var_40]
0x100415da9  call    cs:__imp_?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetSpins(ushort,SPINLOCK_CATEGORY)
0x100415daf  mov     rcx, [rsp+78h+var_40]
0x100415db4  mov     r8d, ebx
0x100415db7  movzx   edx, si
0x100415dba  mov     rbp, rax
0x100415dbd  call    cs:__imp_?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::GetCollisions(ushort,SPINLOCK_CATEGORY)
0x100415dc3  mov     rcx, rax
0x100415dc6  test    rbp, rbp
0x100415dc9  jz      short loc_100415DF0
0x100415dcb  test    rax, rax
0x100415dce  jz      short loc_100415DF0
0x100415dd0  xor     edx, edx
0x100415dd2  mov     rax, rbp
0x100415dd5  div     rcx
0x100415dd8  mov     rcx, rdi
0x100415ddb  shr     rax, 1
0x100415dde  cmp     rax, rdi
0x100415de1  cmova   rcx, rax
0x100415de5  imul    rdi, 64h ; 'd'
0x100415de9  cmp     rcx, rdi
0x100415dec  cmovb   rdi, rcx
0x100415df0  mov     rax, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x100415df7  mov     ecx, [rax]
0x100415df9  mov     rax, cs:__imp_?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_StaggerEnabledForSpinToAcquire
0x100415e00  cmp     rcx, r15
0x100415e03  mov     ebp, ecx
0x100415e05  cmova   rbp, r15
0x100415e09  movzx   r15d, byte ptr [rax]
0x100415e0d  mov     rax, cs:__imp_?sm_SpinIncrement@SOS_PublicGlobals@@2_KA; unsigned __int64 SOS_PublicGlobals::sm_SpinIncrement
0x100415e14  mov     rsi, [rax]
0x100415e17  xor     ebx, ebx
0x100415e19  test    r15b, r15b
0x100415e1c  jz      short loc_100415E30
0x100415e1e  call    cs:__imp_rand
0x100415e24  xor     edx, edx
0x100415e26  cdqe
0x100415e28  div     rdi
0x100415e2b  inc     rdx
0x100415e2e  jmp     short loc_100415E33
0x100415e30  mov     rdx, rdi
0x100415e33  test    rdx, rdx
0x100415e36  jz      short loc_100415E4A
0x100415e38  nop     dword ptr [rax+rax+00000000h]
0x100415e40  pause
0x100415e42  add     rbx, rsi
0x100415e45  cmp     rbx, rdx
0x100415e48  jb      short loc_100415E40
0x100415e4a  mov     rax, [rsp+78h+var_40]
0x100415e4f  test    rax, rax
0x100415e52  jz      short loc_100415E5F
0x100415e54  mov     rax, [rax+18h]
0x100415e58  add     [rax+1C0h], rbx
0x100415e5f  mov     eax, [r14]
0x100415e62  test    eax, eax
0x100415e64  jnz     short loc_100415E7D
0x100415e66  xor     eax, eax
0x100415e68  lock cmpxchg [r14], r12
0x100415e6d  mov     eax, 0
0x100415e72  setz    al
0x100415e75  test    eax, eax
0x100415e77  jnz     loc_100415F00
0x100415e7d  inc     [rsp+78h+var_38]
0x100415e81  mov     rdx, [rsp+78h+var_40]
0x100415e86  test    rdx, rdx
0x100415e89  jz      short loc_100415ECB
0x100415e8b  movzx   ecx, word ptr [rsp+78h+var_54]
0x100415e90  xor     r8d, r8d
0x100415e93  sub     ecx, 1
0x100415e96  jz      short loc_100415EB9
0x100415e98  sub     ecx, 1
0x100415e9b  jz      short loc_100415EB3
0x100415e9d  sub     ecx, 1
0x100415ea0  jz      short loc_100415EAD
0x100415ea2  cmp     ecx, 1
0x100415ea5  jnz     short loc_100415EBD
0x100415ea7  mov     r8, [rdx+20h]
0x100415eab  jmp     short loc_100415EBD
0x100415ead  mov     r8, [rdx+18h]
0x100415eb1  jmp     short loc_100415EBD
0x100415eb3  mov     r8, [rdx+10h]
0x100415eb7  jmp     short loc_100415EBD
0x100415eb9  mov     r8, [rdx+8]
0x100415ebd  movzx   eax, [rsp+78h+var_58]
0x100415ec2  imul    rcx, rax, 38h ; '8'
0x100415ec6  inc     qword ptr [rcx+r8+18h]
0x100415ecb  lea     rdx, [rsp+78h+var_58]
0x100415ed0  mov     rcx, r14
0x100415ed3  call    cs:__imp_?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z; SpinlockBase::Backoff(SpinlockBase::SpinInfo &)
0x100415ed9  test    byte ptr [rsp+78h+var_38], 1Fh
0x100415ede  jnz     short loc_100415EE8
0x100415ee0  mov     rdi, rbp
0x100415ee3  jmp     loc_100415E17
0x100415ee8  lea     rax, [rdi+rdi]
0x100415eec  mov     ecx, 2625A0h
0x100415ef1  cmp     rax, rcx
0x100415ef4  mov     rdi, rax
0x100415ef7  cmova   rdi, rcx
0x100415efb  jmp     loc_100415E17
0x100415f00  lea     r11, [rsp+78h+var_28]
0x100415f05  mov     rbx, [r11+30h]
0x100415f09  mov     rbp, [r11+38h]
0x100415f0d  mov     rsp, r11
0x100415f10  pop     r15
0x100415f12  pop     r14
0x100415f14  pop     r12
0x100415f16  pop     rdi
0x100415f17  pop     rsi
0x100415f18  retn
```
