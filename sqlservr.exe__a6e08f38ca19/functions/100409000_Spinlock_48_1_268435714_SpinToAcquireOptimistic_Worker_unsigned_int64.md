# Spinlock<48,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)

- ea: `0x100409000`
- end: `0x100409230`
- name: `?SpinToAcquireOptimistic@?$Spinlock@$0DA@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100407490`

## callees

- `0x100409000`

## import_xrefs

- `sqldk!SystemThread_TlsOffset` at `0x100409061`
- `sqldk!SystemThread_TlsIndex` at `0x100409057`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004090be`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004090be`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004090d3`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004090d3`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x1004091ff`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x1004091ff`
- `sqldk!?sm_SpinCounter@SOS_PublicGlobals@@2_JA` at `0x100409126`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040909b`
- `sqldk!?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x10040901c`

## pseudocode

```c
_BOOL8 __fastcall Spinlock<48,1,268435714>::SpinToAcquireOptimistic(SpinlockBase *a1, __int64 a2, signed __int64 a3)
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
  v20[0] = 48;
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
        ++*(_QWORD *)(*((_QWORD *)SpinlockStats + 1) + 2696LL);
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
        *(_QWORD *)(*((_QWORD *)v11 + 1) + 2688LL) += v7;
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
0x100409000  mov     [rsp+arg_0], rbx
0x100409005  mov     [rsp+arg_10], rbp
0x10040900a  mov     [rsp+arg_18], rsi
0x10040900f  push    rdi
0x100409010  push    r12
0x100409012  push    r13
0x100409014  push    r14
0x100409016  push    r15
0x100409018  sub     rsp, 50h
0x10040901c  mov     rax, cs:__imp_?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_ShouldResetSpinsForSpinToAcquire
0x100409023  mov     r14, rcx
0x100409026  xor     r12d, r12d
0x100409029  mov     r13d, 1
0x10040902f  mov     rbp, r8
0x100409032  xor     dil, dil
0x100409035  mov     rsi, rdx
0x100409038  mov     ebx, r12d
0x10040903b  movzx   r15d, byte ptr [rax]
0x10040903f  mov     eax, 30h ; '0'
0x100409044  mov     [rsp+78h+var_58], ax
0x100409049  mov     [rsp+78h+var_54], r13d
0x10040904e  mov     r9, gs:58h
0x100409057  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040905e  mov     r8d, [rax]
0x100409061  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100409068  mov     ecx, [rax]
0x10040906a  add     rcx, [r9+r8*8]
0x10040906e  jz      short loc_100409093
0x100409070  cmp     [rcx+110h], rcx
0x100409077  jnz     short loc_100409093
0x100409079  mov     rdx, [rcx+100h]
0x100409080  mov     [rsp+78h+var_50], rdx
0x100409085  test    rdx, rdx
0x100409088  jz      short loc_100409098
0x10040908a  mov     rdx, [rdx+3E0h]
0x100409091  jmp     short loc_10040909B
0x100409093  mov     [rsp+78h+var_50], r12
0x100409098  mov     rdx, r12
0x10040909b  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004090a2  mov     rcx, r12
0x1004090a5  mov     [rsp+78h+var_48], rdx
0x1004090aa  mov     [rsp+78h+var_40], rcx
0x1004090af  mov     [rsp+78h+var_38], r12d
0x1004090b4  test    [rax], r13b
0x1004090b7  jz      short loc_1004090F6
0x1004090b9  test    rdx, rdx
0x1004090bc  jz      short loc_1004090F6
0x1004090be  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x1004090c4  mov     rcx, rax
0x1004090c7  mov     rax, [rsp+78h+var_48]
0x1004090cc  movzx   edx, word ptr [rax+0A0h]
0x1004090d3  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x1004090d9  mov     [rsp+78h+var_40], rax
0x1004090de  mov     rcx, rax
0x1004090e1  test    rax, rax
0x1004090e4  jz      short loc_1004090F6
0x1004090e6  mov     rax, [rax+8]
0x1004090ea  inc     qword ptr [rax+0A88h]
0x1004090f1  mov     rcx, [rsp+78h+var_40]
0x1004090f6  test    rsi, rsi
0x1004090f9  jz      short loc_100409126
0x1004090fb  mov     eax, [rsi+268h]
0x100409101  test    al, 40h
0x100409103  jnz     short loc_10040911F
0x100409105  mov     edx, [rsi+320h]
0x10040910b  test    edx, 202000h
0x100409111  jnz     short loc_10040911F
0x100409113  bt      eax, 0Ah
0x100409117  jb      short loc_10040911F
0x100409119  bt      edx, 14h
0x10040911d  jnb     short loc_100409126
0x10040911f  mov     esi, 2710h
0x100409124  jmp     short loc_100409140
0x100409126  mov     rax, cs:__imp_?sm_SpinCounter@SOS_PublicGlobals@@2_JA; __int64 SOS_PublicGlobals::sm_SpinCounter
0x10040912d  mov     esi, [rax]
0x10040912f  cmp     esi, r13d
0x100409132  cmovb   esi, r13d
0x100409136  nop     word ptr [rax+rax+00000000h]
0x100409140  test    r15b, r15b
0x100409143  mov     eax, r12d
0x100409146  cmovz   eax, ebx
0x100409149  mov     ebx, eax
0x10040914b  cmp     eax, esi
0x10040914d  jnb     short loc_100409172
0x10040914f  nop
0x100409150  test    dil, dil
0x100409153  jz      short loc_10040915A
0x100409155  xor     dil, dil
0x100409158  jmp     short loc_100409165
0x10040915a  test    ebx, ebx
0x10040915c  jz      short loc_100409165
0x10040915e  mov     eax, [r14]
0x100409161  test    eax, eax
0x100409163  jz      short loc_10040916D
0x100409165  pause
0x100409167  inc     ebx
0x100409169  cmp     ebx, esi
0x10040916b  jb      short loc_100409150
0x10040916d  mov     rcx, [rsp+78h+var_40]
0x100409172  test    rcx, rcx
0x100409175  jz      short loc_100409189
0x100409177  mov     rcx, [rcx+8]
0x10040917b  mov     eax, ebx
0x10040917d  add     [rcx+0A80h], rax
0x100409184  mov     rcx, [rsp+78h+var_40]
0x100409189  cmp     ebx, esi
0x10040918b  jnb     short loc_1004091AE
0x10040918d  xor     eax, eax
0x10040918f  lock cmpxchg [r14], rbp
0x100409194  mov     eax, r12d
0x100409197  setz    al
0x10040919a  test    eax, eax
0x10040919c  jnz     short loc_100409212
0x10040919e  mov     rcx, [rsp+78h+var_40]
0x1004091a3  movzx   edi, r13b
0x1004091a7  mov     [rsp+78h+var_38], r12d
0x1004091ac  jmp     short loc_100409140
0x1004091ae  inc     [rsp+78h+var_38]
0x1004091b2  test    rcx, rcx
0x1004091b5  jz      short loc_1004091F7
0x1004091b7  movzx   edx, word ptr [rsp+78h+var_54]
0x1004091bc  mov     r8, r12
0x1004091bf  sub     edx, r13d
0x1004091c2  jz      short loc_1004091E5
0x1004091c4  sub     edx, r13d
0x1004091c7  jz      short loc_1004091DF
0x1004091c9  sub     edx, r13d
0x1004091cc  jz      short loc_1004091D9
0x1004091ce  cmp     edx, r13d
0x1004091d1  jnz     short loc_1004091E9
0x1004091d3  mov     r8, [rcx+20h]
0x1004091d7  jmp     short loc_1004091E9
0x1004091d9  mov     r8, [rcx+18h]
0x1004091dd  jmp     short loc_1004091E9
0x1004091df  mov     r8, [rcx+10h]
0x1004091e3  jmp     short loc_1004091E9
0x1004091e5  mov     r8, [rcx+8]
0x1004091e9  movzx   eax, [rsp+78h+var_58]
0x1004091ee  imul    rcx, rax, 38h ; '8'
0x1004091f2  inc     qword ptr [rcx+r8+18h]
0x1004091f7  lea     rdx, [rsp+78h+var_58]
0x1004091fc  mov     rcx, r14
0x1004091ff  call    cs:__imp_?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z; SpinlockBase::Backoff(SpinlockBase::SpinInfo &)
0x100409205  mov     rcx, [rsp+78h+var_40]
0x10040920a  mov     ebx, r12d
0x10040920d  jmp     loc_100409140
0x100409212  lea     r11, [rsp+78h+var_28]
0x100409217  mov     rbx, [r11+30h]
0x10040921b  mov     rbp, [r11+40h]
0x10040921f  mov     rsi, [r11+48h]
0x100409223  mov     rsp, r11
0x100409226  pop     r15
0x100409228  pop     r14
0x10040922a  pop     r13
0x10040922c  pop     r12
0x10040922e  pop     rdi
0x10040922f  retn
```
