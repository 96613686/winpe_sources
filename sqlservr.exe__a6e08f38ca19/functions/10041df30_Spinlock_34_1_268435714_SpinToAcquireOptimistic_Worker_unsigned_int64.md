# Spinlock<34,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)

- ea: `0x10041df30`
- end: `0x10041e160`
- name: `?SpinToAcquireOptimistic@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z`
- size: `560`
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

- `0x10041df30`

## import_xrefs

- `sqldk!SystemThread_TlsOffset` at `0x10041df91`
- `sqldk!SystemThread_TlsIndex` at `0x10041df87`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10041dfee`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10041dfee`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10041e003`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10041e003`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10041e12f`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10041e12f`
- `sqldk!?sm_SpinCounter@SOS_PublicGlobals@@2_JA` at `0x10041e056`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10041dfcb`
- `sqldk!?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x10041df4c`

## pseudocode

```c
_BOOL8 __fastcall Spinlock<34,1,268435714>::SpinToAcquireOptimistic(SpinlockBase *a1, __int64 a2, signed __int64 a3)
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
  v20[0] = 34;
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
        ++*(_QWORD *)(*((_QWORD *)SpinlockStats + 1) + 1912LL);
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
        *(_QWORD *)(*((_QWORD *)v11 + 1) + 1904LL) += v7;
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
0x10041df30  mov     [rsp+arg_0], rbx
0x10041df35  mov     [rsp+arg_10], rbp
0x10041df3a  mov     [rsp+arg_18], rsi
0x10041df3f  push    rdi
0x10041df40  push    r12
0x10041df42  push    r13
0x10041df44  push    r14
0x10041df46  push    r15
0x10041df48  sub     rsp, 50h
0x10041df4c  mov     rax, cs:__imp_?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_ShouldResetSpinsForSpinToAcquire
0x10041df53  mov     r14, rcx
0x10041df56  xor     r12d, r12d
0x10041df59  mov     r13d, 1
0x10041df5f  mov     rbp, r8
0x10041df62  xor     dil, dil
0x10041df65  mov     rsi, rdx
0x10041df68  mov     ebx, r12d
0x10041df6b  movzx   r15d, byte ptr [rax]
0x10041df6f  mov     eax, 22h ; '"'
0x10041df74  mov     [rsp+78h+var_58], ax
0x10041df79  mov     [rsp+78h+var_54], r13d
0x10041df7e  mov     r9, gs:58h
0x10041df87  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041df8e  mov     r8d, [rax]
0x10041df91  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041df98  mov     ecx, [rax]
0x10041df9a  add     rcx, [r9+r8*8]
0x10041df9e  jz      short loc_10041DFC3
0x10041dfa0  cmp     [rcx+110h], rcx
0x10041dfa7  jnz     short loc_10041DFC3
0x10041dfa9  mov     rdx, [rcx+100h]
0x10041dfb0  mov     [rsp+78h+var_50], rdx
0x10041dfb5  test    rdx, rdx
0x10041dfb8  jz      short loc_10041DFC8
0x10041dfba  mov     rdx, [rdx+3E0h]
0x10041dfc1  jmp     short loc_10041DFCB
0x10041dfc3  mov     [rsp+78h+var_50], r12
0x10041dfc8  mov     rdx, r12
0x10041dfcb  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10041dfd2  mov     rcx, r12
0x10041dfd5  mov     [rsp+78h+var_48], rdx
0x10041dfda  mov     [rsp+78h+var_40], rcx
0x10041dfdf  mov     [rsp+78h+var_38], r12d
0x10041dfe4  test    [rax], r13b
0x10041dfe7  jz      short loc_10041E026
0x10041dfe9  test    rdx, rdx
0x10041dfec  jz      short loc_10041E026
0x10041dfee  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x10041dff4  mov     rcx, rax
0x10041dff7  mov     rax, [rsp+78h+var_48]
0x10041dffc  movzx   edx, word ptr [rax+0A0h]
0x10041e003  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x10041e009  mov     [rsp+78h+var_40], rax
0x10041e00e  mov     rcx, rax
0x10041e011  test    rax, rax
0x10041e014  jz      short loc_10041E026
0x10041e016  mov     rax, [rax+8]
0x10041e01a  inc     qword ptr [rax+778h]
0x10041e021  mov     rcx, [rsp+78h+var_40]
0x10041e026  test    rsi, rsi
0x10041e029  jz      short loc_10041E056
0x10041e02b  mov     eax, [rsi+268h]
0x10041e031  test    al, 40h
0x10041e033  jnz     short loc_10041E04F
0x10041e035  mov     edx, [rsi+320h]
0x10041e03b  test    edx, 202000h
0x10041e041  jnz     short loc_10041E04F
0x10041e043  bt      eax, 0Ah
0x10041e047  jb      short loc_10041E04F
0x10041e049  bt      edx, 14h
0x10041e04d  jnb     short loc_10041E056
0x10041e04f  mov     esi, 2710h
0x10041e054  jmp     short loc_10041E070
0x10041e056  mov     rax, cs:__imp_?sm_SpinCounter@SOS_PublicGlobals@@2_JA; __int64 SOS_PublicGlobals::sm_SpinCounter
0x10041e05d  mov     esi, [rax]
0x10041e05f  cmp     esi, r13d
0x10041e062  cmovb   esi, r13d
0x10041e066  nop     word ptr [rax+rax+00000000h]
0x10041e070  test    r15b, r15b
0x10041e073  mov     eax, r12d
0x10041e076  cmovz   eax, ebx
0x10041e079  mov     ebx, eax
0x10041e07b  cmp     eax, esi
0x10041e07d  jnb     short loc_10041E0A2
0x10041e07f  nop
0x10041e080  test    dil, dil
0x10041e083  jz      short loc_10041E08A
0x10041e085  xor     dil, dil
0x10041e088  jmp     short loc_10041E095
0x10041e08a  test    ebx, ebx
0x10041e08c  jz      short loc_10041E095
0x10041e08e  mov     eax, [r14]
0x10041e091  test    eax, eax
0x10041e093  jz      short loc_10041E09D
0x10041e095  pause
0x10041e097  inc     ebx
0x10041e099  cmp     ebx, esi
0x10041e09b  jb      short loc_10041E080
0x10041e09d  mov     rcx, [rsp+78h+var_40]
0x10041e0a2  test    rcx, rcx
0x10041e0a5  jz      short loc_10041E0B9
0x10041e0a7  mov     rcx, [rcx+8]
0x10041e0ab  mov     eax, ebx
0x10041e0ad  add     [rcx+770h], rax
0x10041e0b4  mov     rcx, [rsp+78h+var_40]
0x10041e0b9  cmp     ebx, esi
0x10041e0bb  jnb     short loc_10041E0DE
0x10041e0bd  xor     eax, eax
0x10041e0bf  lock cmpxchg [r14], rbp
0x10041e0c4  mov     eax, r12d
0x10041e0c7  setz    al
0x10041e0ca  test    eax, eax
0x10041e0cc  jnz     short loc_10041E142
0x10041e0ce  mov     rcx, [rsp+78h+var_40]
0x10041e0d3  movzx   edi, r13b
0x10041e0d7  mov     [rsp+78h+var_38], r12d
0x10041e0dc  jmp     short loc_10041E070
0x10041e0de  inc     [rsp+78h+var_38]
0x10041e0e2  test    rcx, rcx
0x10041e0e5  jz      short loc_10041E127
0x10041e0e7  movzx   edx, word ptr [rsp+78h+var_54]
0x10041e0ec  mov     r8, r12
0x10041e0ef  sub     edx, r13d
0x10041e0f2  jz      short loc_10041E115
0x10041e0f4  sub     edx, r13d
0x10041e0f7  jz      short loc_10041E10F
0x10041e0f9  sub     edx, r13d
0x10041e0fc  jz      short loc_10041E109
0x10041e0fe  cmp     edx, r13d
0x10041e101  jnz     short loc_10041E119
0x10041e103  mov     r8, [rcx+20h]
0x10041e107  jmp     short loc_10041E119
0x10041e109  mov     r8, [rcx+18h]
0x10041e10d  jmp     short loc_10041E119
0x10041e10f  mov     r8, [rcx+10h]
0x10041e113  jmp     short loc_10041E119
0x10041e115  mov     r8, [rcx+8]
0x10041e119  movzx   eax, [rsp+78h+var_58]
0x10041e11e  imul    rcx, rax, 38h ; '8'
0x10041e122  inc     qword ptr [rcx+r8+18h]
0x10041e127  lea     rdx, [rsp+78h+var_58]
0x10041e12c  mov     rcx, r14
0x10041e12f  call    cs:__imp_?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z; SpinlockBase::Backoff(SpinlockBase::SpinInfo &)
0x10041e135  mov     rcx, [rsp+78h+var_40]
0x10041e13a  mov     ebx, r12d
0x10041e13d  jmp     loc_10041E070
0x10041e142  lea     r11, [rsp+78h+var_28]
0x10041e147  mov     rbx, [r11+30h]
0x10041e14b  mov     rbp, [r11+40h]
0x10041e14f  mov     rsi, [r11+48h]
0x10041e153  mov     rsp, r11
0x10041e156  pop     r15
0x10041e158  pop     r14
0x10041e15a  pop     r13
0x10041e15c  pop     r12
0x10041e15e  pop     rdi
0x10041e15f  retn
```
