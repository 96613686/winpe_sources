# Spinlock<25,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)

- ea: `0x10040a5c0`
- end: `0x10040a7f0`
- name: `?SpinToAcquireOptimistic@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z`
- size: `560`
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

- `0x10040a5c0`

## import_xrefs

- `sqldk!SystemThread_TlsOffset` at `0x10040a621`
- `sqldk!SystemThread_TlsIndex` at `0x10040a617`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040a67e`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040a67e`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040a693`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040a693`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10040a7bf`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10040a7bf`
- `sqldk!?sm_SpinCounter@SOS_PublicGlobals@@2_JA` at `0x10040a6e6`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040a65b`
- `sqldk!?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x10040a5dc`

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
0x10040a5c0  mov     [rsp+arg_0], rbx
0x10040a5c5  mov     [rsp+arg_10], rbp
0x10040a5ca  mov     [rsp+arg_18], rsi
0x10040a5cf  push    rdi
0x10040a5d0  push    r12
0x10040a5d2  push    r13
0x10040a5d4  push    r14
0x10040a5d6  push    r15
0x10040a5d8  sub     rsp, 50h
0x10040a5dc  mov     rax, cs:__imp_?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_ShouldResetSpinsForSpinToAcquire
0x10040a5e3  mov     r14, rcx
0x10040a5e6  xor     r12d, r12d
0x10040a5e9  mov     r13d, 1
0x10040a5ef  mov     rbp, r8
0x10040a5f2  xor     dil, dil
0x10040a5f5  mov     rsi, rdx
0x10040a5f8  mov     ebx, r12d
0x10040a5fb  movzx   r15d, byte ptr [rax]
0x10040a5ff  mov     eax, 19h
0x10040a604  mov     [rsp+78h+var_58], ax
0x10040a609  mov     [rsp+78h+var_54], r13d
0x10040a60e  mov     r9, gs:58h
0x10040a617  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040a61e  mov     r8d, [rax]
0x10040a621  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040a628  mov     ecx, [rax]
0x10040a62a  add     rcx, [r9+r8*8]
0x10040a62e  jz      short loc_10040A653
0x10040a630  cmp     [rcx+110h], rcx
0x10040a637  jnz     short loc_10040A653
0x10040a639  mov     rdx, [rcx+100h]
0x10040a640  mov     [rsp+78h+var_50], rdx
0x10040a645  test    rdx, rdx
0x10040a648  jz      short loc_10040A658
0x10040a64a  mov     rdx, [rdx+3E0h]
0x10040a651  jmp     short loc_10040A65B
0x10040a653  mov     [rsp+78h+var_50], r12
0x10040a658  mov     rdx, r12
0x10040a65b  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040a662  mov     rcx, r12
0x10040a665  mov     [rsp+78h+var_48], rdx
0x10040a66a  mov     [rsp+78h+var_40], rcx
0x10040a66f  mov     [rsp+78h+var_38], r12d
0x10040a674  test    [rax], r13b
0x10040a677  jz      short loc_10040A6B6
0x10040a679  test    rdx, rdx
0x10040a67c  jz      short loc_10040A6B6
0x10040a67e  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x10040a684  mov     rcx, rax
0x10040a687  mov     rax, [rsp+78h+var_48]
0x10040a68c  movzx   edx, word ptr [rax+0A0h]
0x10040a693  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x10040a699  mov     [rsp+78h+var_40], rax
0x10040a69e  mov     rcx, rax
0x10040a6a1  test    rax, rax
0x10040a6a4  jz      short loc_10040A6B6
0x10040a6a6  mov     rax, [rax+8]
0x10040a6aa  inc     qword ptr [rax+580h]
0x10040a6b1  mov     rcx, [rsp+78h+var_40]
0x10040a6b6  test    rsi, rsi
0x10040a6b9  jz      short loc_10040A6E6
0x10040a6bb  mov     eax, [rsi+268h]
0x10040a6c1  test    al, 40h
0x10040a6c3  jnz     short loc_10040A6DF
0x10040a6c5  mov     edx, [rsi+320h]
0x10040a6cb  test    edx, 202000h
0x10040a6d1  jnz     short loc_10040A6DF
0x10040a6d3  bt      eax, 0Ah
0x10040a6d7  jb      short loc_10040A6DF
0x10040a6d9  bt      edx, 14h
0x10040a6dd  jnb     short loc_10040A6E6
0x10040a6df  mov     esi, 2710h
0x10040a6e4  jmp     short loc_10040A700
0x10040a6e6  mov     rax, cs:__imp_?sm_SpinCounter@SOS_PublicGlobals@@2_JA; __int64 SOS_PublicGlobals::sm_SpinCounter
0x10040a6ed  mov     esi, [rax]
0x10040a6ef  cmp     esi, r13d
0x10040a6f2  cmovb   esi, r13d
0x10040a6f6  nop     word ptr [rax+rax+00000000h]
0x10040a700  test    r15b, r15b
0x10040a703  mov     eax, r12d
0x10040a706  cmovz   eax, ebx
0x10040a709  mov     ebx, eax
0x10040a70b  cmp     eax, esi
0x10040a70d  jnb     short loc_10040A732
0x10040a70f  nop
0x10040a710  test    dil, dil
0x10040a713  jz      short loc_10040A71A
0x10040a715  xor     dil, dil
0x10040a718  jmp     short loc_10040A725
0x10040a71a  test    ebx, ebx
0x10040a71c  jz      short loc_10040A725
0x10040a71e  mov     eax, [r14]
0x10040a721  test    eax, eax
0x10040a723  jz      short loc_10040A72D
0x10040a725  pause
0x10040a727  inc     ebx
0x10040a729  cmp     ebx, esi
0x10040a72b  jb      short loc_10040A710
0x10040a72d  mov     rcx, [rsp+78h+var_40]
0x10040a732  test    rcx, rcx
0x10040a735  jz      short loc_10040A749
0x10040a737  mov     rcx, [rcx+8]
0x10040a73b  mov     eax, ebx
0x10040a73d  add     [rcx+578h], rax
0x10040a744  mov     rcx, [rsp+78h+var_40]
0x10040a749  cmp     ebx, esi
0x10040a74b  jnb     short loc_10040A76E
0x10040a74d  xor     eax, eax
0x10040a74f  lock cmpxchg [r14], rbp
0x10040a754  mov     eax, r12d
0x10040a757  setz    al
0x10040a75a  test    eax, eax
0x10040a75c  jnz     short loc_10040A7D2
0x10040a75e  mov     rcx, [rsp+78h+var_40]
0x10040a763  movzx   edi, r13b
0x10040a767  mov     [rsp+78h+var_38], r12d
0x10040a76c  jmp     short loc_10040A700
0x10040a76e  inc     [rsp+78h+var_38]
0x10040a772  test    rcx, rcx
0x10040a775  jz      short loc_10040A7B7
0x10040a777  movzx   edx, word ptr [rsp+78h+var_54]
0x10040a77c  mov     r8, r12
0x10040a77f  sub     edx, r13d
0x10040a782  jz      short loc_10040A7A5
0x10040a784  sub     edx, r13d
0x10040a787  jz      short loc_10040A79F
0x10040a789  sub     edx, r13d
0x10040a78c  jz      short loc_10040A799
0x10040a78e  cmp     edx, r13d
0x10040a791  jnz     short loc_10040A7A9
0x10040a793  mov     r8, [rcx+20h]
0x10040a797  jmp     short loc_10040A7A9
0x10040a799  mov     r8, [rcx+18h]
0x10040a79d  jmp     short loc_10040A7A9
0x10040a79f  mov     r8, [rcx+10h]
0x10040a7a3  jmp     short loc_10040A7A9
0x10040a7a5  mov     r8, [rcx+8]
0x10040a7a9  movzx   eax, [rsp+78h+var_58]
0x10040a7ae  imul    rcx, rax, 38h ; '8'
0x10040a7b2  inc     qword ptr [rcx+r8+18h]
0x10040a7b7  lea     rdx, [rsp+78h+var_58]
0x10040a7bc  mov     rcx, r14
0x10040a7bf  call    cs:__imp_?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z; SpinlockBase::Backoff(SpinlockBase::SpinInfo &)
0x10040a7c5  mov     rcx, [rsp+78h+var_40]
0x10040a7ca  mov     ebx, r12d
0x10040a7cd  jmp     loc_10040A700
0x10040a7d2  lea     r11, [rsp+78h+var_28]
0x10040a7d7  mov     rbx, [r11+30h]
0x10040a7db  mov     rbp, [r11+40h]
0x10040a7df  mov     rsi, [r11+48h]
0x10040a7e3  mov     rsp, r11
0x10040a7e6  pop     r15
0x10040a7e8  pop     r14
0x10040a7ea  pop     r13
0x10040a7ec  pop     r12
0x10040a7ee  pop     rdi
0x10040a7ef  retn
```
