# Spinlock<25,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)

- ea: `0x10049fbf0`
- end: `0x10049fe20`
- name: `?SpinToAcquireOptimistic@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z`
- size: `560`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10049f510`
- `0x10049f780`
- `0x10049f9a0`
- `0x100836c60`
- `0x100837f80`

## callees

- `0x10049fbf0`

## import_xrefs

- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10049fc8b`
- `sqldk!?sm_SpinCounter@SOS_PublicGlobals@@2_JA` at `0x10049fd16`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10049fcae`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10049fcae`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10049fcc3`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10049fcc3`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10049fdef`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10049fdef`
- `sqldk!?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x10049fc0c`
- `sqldk!SystemThread_TlsIndex` at `0x10049fc47`
- `sqldk!SystemThread_TlsOffset` at `0x10049fc51`

## pseudocode

```c
_BOOL8 __fastcall Spinlock<25,1,268435714>::SpinToAcquireOptimistic(SpinlockBase *a1, __int64 a2, signed __int64 a3)
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
  v20[0] = 25;
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
        ++*(_QWORD *)(*((_QWORD *)SpinlockStats + 1) + 1408LL);
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
        *(_QWORD *)(*((_QWORD *)v11 + 1) + 1400LL) += v7;
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
0x10049fbf0  mov     [rsp+arg_0], rbx
0x10049fbf5  mov     [rsp+arg_10], rbp
0x10049fbfa  mov     [rsp+arg_18], rsi
0x10049fbff  push    rdi
0x10049fc00  push    r12
0x10049fc02  push    r13
0x10049fc04  push    r14
0x10049fc06  push    r15
0x10049fc08  sub     rsp, 50h
0x10049fc0c  mov     rax, cs:__imp_?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_ShouldResetSpinsForSpinToAcquire
0x10049fc13  mov     r14, rcx
0x10049fc16  xor     r12d, r12d
0x10049fc19  mov     r13d, 1
0x10049fc1f  mov     rbp, r8
0x10049fc22  xor     dil, dil
0x10049fc25  mov     rsi, rdx
0x10049fc28  mov     ebx, r12d
0x10049fc2b  movzx   r15d, byte ptr [rax]
0x10049fc2f  mov     eax, 19h
0x10049fc34  mov     [rsp+78h+var_58], ax
0x10049fc39  mov     [rsp+78h+var_54], r13d
0x10049fc3e  mov     r9, gs:58h
0x10049fc47  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10049fc4e  mov     r8d, [rax]
0x10049fc51  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10049fc58  mov     ecx, [rax]
0x10049fc5a  add     rcx, [r9+r8*8]
0x10049fc5e  jz      short loc_10049FC83
0x10049fc60  cmp     [rcx+110h], rcx
0x10049fc67  jnz     short loc_10049FC83
0x10049fc69  mov     rdx, [rcx+100h]
0x10049fc70  mov     [rsp+78h+var_50], rdx
0x10049fc75  test    rdx, rdx
0x10049fc78  jz      short loc_10049FC88
0x10049fc7a  mov     rdx, [rdx+3E0h]
0x10049fc81  jmp     short loc_10049FC8B
0x10049fc83  mov     [rsp+78h+var_50], r12
0x10049fc88  mov     rdx, r12
0x10049fc8b  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10049fc92  mov     rcx, r12
0x10049fc95  mov     [rsp+78h+var_48], rdx
0x10049fc9a  mov     [rsp+78h+var_40], rcx
0x10049fc9f  mov     [rsp+78h+var_38], r12d
0x10049fca4  test    [rax], r13b
0x10049fca7  jz      short loc_10049FCE6
0x10049fca9  test    rdx, rdx
0x10049fcac  jz      short loc_10049FCE6
0x10049fcae  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x10049fcb4  mov     rcx, rax
0x10049fcb7  mov     rax, [rsp+78h+var_48]
0x10049fcbc  movzx   edx, word ptr [rax+0A0h]
0x10049fcc3  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x10049fcc9  mov     [rsp+78h+var_40], rax
0x10049fcce  mov     rcx, rax
0x10049fcd1  test    rax, rax
0x10049fcd4  jz      short loc_10049FCE6
0x10049fcd6  mov     rax, [rax+8]
0x10049fcda  inc     qword ptr [rax+580h]
0x10049fce1  mov     rcx, [rsp+78h+var_40]
0x10049fce6  test    rsi, rsi
0x10049fce9  jz      short loc_10049FD16
0x10049fceb  mov     eax, [rsi+268h]
0x10049fcf1  test    al, 40h
0x10049fcf3  jnz     short loc_10049FD0F
0x10049fcf5  mov     edx, [rsi+320h]
0x10049fcfb  test    edx, 202000h
0x10049fd01  jnz     short loc_10049FD0F
0x10049fd03  bt      eax, 0Ah
0x10049fd07  jb      short loc_10049FD0F
0x10049fd09  bt      edx, 14h
0x10049fd0d  jnb     short loc_10049FD16
0x10049fd0f  mov     esi, 2710h
0x10049fd14  jmp     short loc_10049FD30
0x10049fd16  mov     rax, cs:__imp_?sm_SpinCounter@SOS_PublicGlobals@@2_JA; __int64 SOS_PublicGlobals::sm_SpinCounter
0x10049fd1d  mov     esi, [rax]
0x10049fd1f  cmp     esi, r13d
0x10049fd22  cmovb   esi, r13d
0x10049fd26  nop     word ptr [rax+rax+00000000h]
0x10049fd30  test    r15b, r15b
0x10049fd33  mov     eax, r12d
0x10049fd36  cmovz   eax, ebx
0x10049fd39  mov     ebx, eax
0x10049fd3b  cmp     eax, esi
0x10049fd3d  jnb     short loc_10049FD62
0x10049fd3f  nop
0x10049fd40  test    dil, dil
0x10049fd43  jz      short loc_10049FD4A
0x10049fd45  xor     dil, dil
0x10049fd48  jmp     short loc_10049FD55
0x10049fd4a  test    ebx, ebx
0x10049fd4c  jz      short loc_10049FD55
0x10049fd4e  mov     eax, [r14]
0x10049fd51  test    eax, eax
0x10049fd53  jz      short loc_10049FD5D
0x10049fd55  pause
0x10049fd57  inc     ebx
0x10049fd59  cmp     ebx, esi
0x10049fd5b  jb      short loc_10049FD40
0x10049fd5d  mov     rcx, [rsp+78h+var_40]
0x10049fd62  test    rcx, rcx
0x10049fd65  jz      short loc_10049FD79
0x10049fd67  mov     rcx, [rcx+8]
0x10049fd6b  mov     eax, ebx
0x10049fd6d  add     [rcx+578h], rax
0x10049fd74  mov     rcx, [rsp+78h+var_40]
0x10049fd79  cmp     ebx, esi
0x10049fd7b  jnb     short loc_10049FD9E
0x10049fd7d  xor     eax, eax
0x10049fd7f  lock cmpxchg [r14], rbp
0x10049fd84  mov     eax, r12d
0x10049fd87  setz    al
0x10049fd8a  test    eax, eax
0x10049fd8c  jnz     short loc_10049FE02
0x10049fd8e  mov     rcx, [rsp+78h+var_40]
0x10049fd93  movzx   edi, r13b
0x10049fd97  mov     [rsp+78h+var_38], r12d
0x10049fd9c  jmp     short loc_10049FD30
0x10049fd9e  inc     [rsp+78h+var_38]
0x10049fda2  test    rcx, rcx
0x10049fda5  jz      short loc_10049FDE7
0x10049fda7  movzx   edx, word ptr [rsp+78h+var_54]
0x10049fdac  mov     r8, r12
0x10049fdaf  sub     edx, r13d
0x10049fdb2  jz      short loc_10049FDD5
0x10049fdb4  sub     edx, r13d
0x10049fdb7  jz      short loc_10049FDCF
0x10049fdb9  sub     edx, r13d
0x10049fdbc  jz      short loc_10049FDC9
0x10049fdbe  cmp     edx, r13d
0x10049fdc1  jnz     short loc_10049FDD9
0x10049fdc3  mov     r8, [rcx+20h]
0x10049fdc7  jmp     short loc_10049FDD9
0x10049fdc9  mov     r8, [rcx+18h]
0x10049fdcd  jmp     short loc_10049FDD9
0x10049fdcf  mov     r8, [rcx+10h]
0x10049fdd3  jmp     short loc_10049FDD9
0x10049fdd5  mov     r8, [rcx+8]
0x10049fdd9  movzx   eax, [rsp+78h+var_58]
0x10049fdde  imul    rcx, rax, 38h ; '8'
0x10049fde2  inc     qword ptr [rcx+r8+18h]
0x10049fde7  lea     rdx, [rsp+78h+var_58]
0x10049fdec  mov     rcx, r14
0x10049fdef  call    cs:__imp_?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z; SpinlockBase::Backoff(SpinlockBase::SpinInfo &)
0x10049fdf5  mov     rcx, [rsp+78h+var_40]
0x10049fdfa  mov     ebx, r12d
0x10049fdfd  jmp     loc_10049FD30
0x10049fe02  lea     r11, [rsp+78h+var_28]
0x10049fe07  mov     rbx, [r11+30h]
0x10049fe0b  mov     rbp, [r11+40h]
0x10049fe0f  mov     rsi, [r11+48h]
0x10049fe13  mov     rsp, r11
0x10049fe16  pop     r15
0x10049fe18  pop     r14
0x10049fe1a  pop     r13
0x10049fe1c  pop     r12
0x10049fe1e  pop     rdi
0x10049fe1f  retn
```
