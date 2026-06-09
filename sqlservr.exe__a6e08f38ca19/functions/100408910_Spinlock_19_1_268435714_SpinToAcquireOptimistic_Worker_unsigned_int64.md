# Spinlock<19,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)

- ea: `0x100408910`
- end: `0x100408b40`
- name: `?SpinToAcquireOptimistic@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z`
- size: `560`
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

- `0x100408910`

## import_xrefs

- `sqldk!SystemThread_TlsOffset` at `0x100408971`
- `sqldk!SystemThread_TlsIndex` at `0x100408967`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004089ce`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004089ce`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004089e3`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004089e3`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x100408b0f`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x100408b0f`
- `sqldk!?sm_SpinCounter@SOS_PublicGlobals@@2_JA` at `0x100408a36`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004089ab`
- `sqldk!?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x10040892c`

## pseudocode

```c
_BOOL8 __fastcall Spinlock<19,1,268435714>::SpinToAcquireOptimistic(SpinlockBase *a1, __int64 a2, signed __int64 a3)
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
  v20[0] = 19;
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
        ++*(_QWORD *)(*((_QWORD *)SpinlockStats + 1) + 1072LL);
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
        *(_QWORD *)(*((_QWORD *)v11 + 1) + 1064LL) += v7;
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
0x100408910  mov     [rsp+arg_0], rbx
0x100408915  mov     [rsp+arg_10], rbp
0x10040891a  mov     [rsp+arg_18], rsi
0x10040891f  push    rdi
0x100408920  push    r12
0x100408922  push    r13
0x100408924  push    r14
0x100408926  push    r15
0x100408928  sub     rsp, 50h
0x10040892c  mov     rax, cs:__imp_?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_ShouldResetSpinsForSpinToAcquire
0x100408933  mov     r14, rcx
0x100408936  xor     r12d, r12d
0x100408939  mov     r13d, 1
0x10040893f  mov     rbp, r8
0x100408942  xor     dil, dil
0x100408945  mov     rsi, rdx
0x100408948  mov     ebx, r12d
0x10040894b  movzx   r15d, byte ptr [rax]
0x10040894f  mov     eax, 13h
0x100408954  mov     [rsp+78h+var_58], ax
0x100408959  mov     [rsp+78h+var_54], r13d
0x10040895e  mov     r9, gs:58h
0x100408967  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040896e  mov     r8d, [rax]
0x100408971  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100408978  mov     ecx, [rax]
0x10040897a  add     rcx, [r9+r8*8]
0x10040897e  jz      short loc_1004089A3
0x100408980  cmp     [rcx+110h], rcx
0x100408987  jnz     short loc_1004089A3
0x100408989  mov     rdx, [rcx+100h]
0x100408990  mov     [rsp+78h+var_50], rdx
0x100408995  test    rdx, rdx
0x100408998  jz      short loc_1004089A8
0x10040899a  mov     rdx, [rdx+3E0h]
0x1004089a1  jmp     short loc_1004089AB
0x1004089a3  mov     [rsp+78h+var_50], r12
0x1004089a8  mov     rdx, r12
0x1004089ab  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004089b2  mov     rcx, r12
0x1004089b5  mov     [rsp+78h+var_48], rdx
0x1004089ba  mov     [rsp+78h+var_40], rcx
0x1004089bf  mov     [rsp+78h+var_38], r12d
0x1004089c4  test    [rax], r13b
0x1004089c7  jz      short loc_100408A06
0x1004089c9  test    rdx, rdx
0x1004089cc  jz      short loc_100408A06
0x1004089ce  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x1004089d4  mov     rcx, rax
0x1004089d7  mov     rax, [rsp+78h+var_48]
0x1004089dc  movzx   edx, word ptr [rax+0A0h]
0x1004089e3  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x1004089e9  mov     [rsp+78h+var_40], rax
0x1004089ee  mov     rcx, rax
0x1004089f1  test    rax, rax
0x1004089f4  jz      short loc_100408A06
0x1004089f6  mov     rax, [rax+8]
0x1004089fa  inc     qword ptr [rax+430h]
0x100408a01  mov     rcx, [rsp+78h+var_40]
0x100408a06  test    rsi, rsi
0x100408a09  jz      short loc_100408A36
0x100408a0b  mov     eax, [rsi+268h]
0x100408a11  test    al, 40h
0x100408a13  jnz     short loc_100408A2F
0x100408a15  mov     edx, [rsi+320h]
0x100408a1b  test    edx, 202000h
0x100408a21  jnz     short loc_100408A2F
0x100408a23  bt      eax, 0Ah
0x100408a27  jb      short loc_100408A2F
0x100408a29  bt      edx, 14h
0x100408a2d  jnb     short loc_100408A36
0x100408a2f  mov     esi, 2710h
0x100408a34  jmp     short loc_100408A50
0x100408a36  mov     rax, cs:__imp_?sm_SpinCounter@SOS_PublicGlobals@@2_JA; __int64 SOS_PublicGlobals::sm_SpinCounter
0x100408a3d  mov     esi, [rax]
0x100408a3f  cmp     esi, r13d
0x100408a42  cmovb   esi, r13d
0x100408a46  nop     word ptr [rax+rax+00000000h]
0x100408a50  test    r15b, r15b
0x100408a53  mov     eax, r12d
0x100408a56  cmovz   eax, ebx
0x100408a59  mov     ebx, eax
0x100408a5b  cmp     eax, esi
0x100408a5d  jnb     short loc_100408A82
0x100408a5f  nop
0x100408a60  test    dil, dil
0x100408a63  jz      short loc_100408A6A
0x100408a65  xor     dil, dil
0x100408a68  jmp     short loc_100408A75
0x100408a6a  test    ebx, ebx
0x100408a6c  jz      short loc_100408A75
0x100408a6e  mov     eax, [r14]
0x100408a71  test    eax, eax
0x100408a73  jz      short loc_100408A7D
0x100408a75  pause
0x100408a77  inc     ebx
0x100408a79  cmp     ebx, esi
0x100408a7b  jb      short loc_100408A60
0x100408a7d  mov     rcx, [rsp+78h+var_40]
0x100408a82  test    rcx, rcx
0x100408a85  jz      short loc_100408A99
0x100408a87  mov     rcx, [rcx+8]
0x100408a8b  mov     eax, ebx
0x100408a8d  add     [rcx+428h], rax
0x100408a94  mov     rcx, [rsp+78h+var_40]
0x100408a99  cmp     ebx, esi
0x100408a9b  jnb     short loc_100408ABE
0x100408a9d  xor     eax, eax
0x100408a9f  lock cmpxchg [r14], rbp
0x100408aa4  mov     eax, r12d
0x100408aa7  setz    al
0x100408aaa  test    eax, eax
0x100408aac  jnz     short loc_100408B22
0x100408aae  mov     rcx, [rsp+78h+var_40]
0x100408ab3  movzx   edi, r13b
0x100408ab7  mov     [rsp+78h+var_38], r12d
0x100408abc  jmp     short loc_100408A50
0x100408abe  inc     [rsp+78h+var_38]
0x100408ac2  test    rcx, rcx
0x100408ac5  jz      short loc_100408B07
0x100408ac7  movzx   edx, word ptr [rsp+78h+var_54]
0x100408acc  mov     r8, r12
0x100408acf  sub     edx, r13d
0x100408ad2  jz      short loc_100408AF5
0x100408ad4  sub     edx, r13d
0x100408ad7  jz      short loc_100408AEF
0x100408ad9  sub     edx, r13d
0x100408adc  jz      short loc_100408AE9
0x100408ade  cmp     edx, r13d
0x100408ae1  jnz     short loc_100408AF9
0x100408ae3  mov     r8, [rcx+20h]
0x100408ae7  jmp     short loc_100408AF9
0x100408ae9  mov     r8, [rcx+18h]
0x100408aed  jmp     short loc_100408AF9
0x100408aef  mov     r8, [rcx+10h]
0x100408af3  jmp     short loc_100408AF9
0x100408af5  mov     r8, [rcx+8]
0x100408af9  movzx   eax, [rsp+78h+var_58]
0x100408afe  imul    rcx, rax, 38h ; '8'
0x100408b02  inc     qword ptr [rcx+r8+18h]
0x100408b07  lea     rdx, [rsp+78h+var_58]
0x100408b0c  mov     rcx, r14
0x100408b0f  call    cs:__imp_?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z; SpinlockBase::Backoff(SpinlockBase::SpinInfo &)
0x100408b15  mov     rcx, [rsp+78h+var_40]
0x100408b1a  mov     ebx, r12d
0x100408b1d  jmp     loc_100408A50
0x100408b22  lea     r11, [rsp+78h+var_28]
0x100408b27  mov     rbx, [r11+30h]
0x100408b2b  mov     rbp, [r11+40h]
0x100408b2f  mov     rsi, [r11+48h]
0x100408b33  mov     rsp, r11
0x100408b36  pop     r15
0x100408b38  pop     r14
0x100408b3a  pop     r13
0x100408b3c  pop     r12
0x100408b3e  pop     rdi
0x100408b3f  retn
```
