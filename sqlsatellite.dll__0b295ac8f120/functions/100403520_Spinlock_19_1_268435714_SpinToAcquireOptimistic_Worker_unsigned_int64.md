# Spinlock<19,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)

- ea: `0x100403520`
- end: `0x100403750`
- name: `?SpinToAcquireOptimistic@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z`
- size: `560`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100403270`
- `0x10040bbb0`
- `0x10040bf30`
- `0x10041d070`
- `0x100421ca0`
- `0x100421e80`
- `0x1004740e0`
- `0x100475c00`
- `0x100476ab0`
- `0x100477010`
- `0x1004771f0`
- `0x1004773d0`
- `0x1004775a0`

## callees

- `0x100403520`

## import_xrefs

- `sqldk!?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x10040353c`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10040371f`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10040371f`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004035f3`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004035f3`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004035de`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004035de`
- `sqldk!SystemThread_TlsIndex` at `0x100403577`
- `sqldk!SystemThread_TlsOffset` at `0x100403581`
- `sqldk!?sm_SpinCounter@SOS_PublicGlobals@@2_JA` at `0x100403646`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004035bb`

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
0x100403520  mov     [rsp+arg_0], rbx
0x100403525  mov     [rsp+arg_10], rbp
0x10040352a  mov     [rsp+arg_18], rsi
0x10040352f  push    rdi
0x100403530  push    r12
0x100403532  push    r13
0x100403534  push    r14
0x100403536  push    r15
0x100403538  sub     rsp, 50h
0x10040353c  mov     rax, cs:__imp_?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA; bool SOS_PublicGlobals::sm_ShouldResetSpinsForSpinToAcquire
0x100403543  mov     r14, rcx
0x100403546  xor     r12d, r12d
0x100403549  mov     r13d, 1
0x10040354f  mov     rbp, r8
0x100403552  xor     dil, dil
0x100403555  mov     rsi, rdx
0x100403558  mov     ebx, r12d
0x10040355b  movzx   r15d, byte ptr [rax]
0x10040355f  mov     eax, 13h
0x100403564  mov     [rsp+78h+var_58], ax
0x100403569  mov     [rsp+78h+var_54], r13d
0x10040356e  mov     r9, gs:58h
0x100403577  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040357e  mov     r8d, [rax]
0x100403581  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100403588  mov     ecx, [rax]
0x10040358a  add     rcx, [r9+r8*8]
0x10040358e  jz      short loc_1004035B3
0x100403590  cmp     [rcx+110h], rcx
0x100403597  jnz     short loc_1004035B3
0x100403599  mov     rdx, [rcx+100h]
0x1004035a0  mov     [rsp+78h+var_50], rdx
0x1004035a5  test    rdx, rdx
0x1004035a8  jz      short loc_1004035B8
0x1004035aa  mov     rdx, [rdx+3E0h]
0x1004035b1  jmp     short loc_1004035BB
0x1004035b3  mov     [rsp+78h+var_50], r12
0x1004035b8  mov     rdx, r12
0x1004035bb  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004035c2  mov     rcx, r12
0x1004035c5  mov     [rsp+78h+var_48], rdx
0x1004035ca  mov     [rsp+78h+var_40], rcx
0x1004035cf  mov     [rsp+78h+var_38], r12d
0x1004035d4  test    [rax], r13b
0x1004035d7  jz      short loc_100403616
0x1004035d9  test    rdx, rdx
0x1004035dc  jz      short loc_100403616
0x1004035de  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x1004035e4  mov     rcx, rax
0x1004035e7  mov     rax, [rsp+78h+var_48]
0x1004035ec  movzx   edx, word ptr [rax+0A0h]
0x1004035f3  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x1004035f9  mov     [rsp+78h+var_40], rax
0x1004035fe  mov     rcx, rax
0x100403601  test    rax, rax
0x100403604  jz      short loc_100403616
0x100403606  mov     rax, [rax+8]
0x10040360a  inc     qword ptr [rax+430h]
0x100403611  mov     rcx, [rsp+78h+var_40]
0x100403616  test    rsi, rsi
0x100403619  jz      short loc_100403646
0x10040361b  mov     eax, [rsi+268h]
0x100403621  test    al, 40h
0x100403623  jnz     short loc_10040363F
0x100403625  mov     edx, [rsi+320h]
0x10040362b  test    edx, 202000h
0x100403631  jnz     short loc_10040363F
0x100403633  bt      eax, 0Ah
0x100403637  jb      short loc_10040363F
0x100403639  bt      edx, 14h
0x10040363d  jnb     short loc_100403646
0x10040363f  mov     esi, 2710h
0x100403644  jmp     short loc_100403660
0x100403646  mov     rax, cs:__imp_?sm_SpinCounter@SOS_PublicGlobals@@2_JA; __int64 SOS_PublicGlobals::sm_SpinCounter
0x10040364d  mov     esi, [rax]
0x10040364f  cmp     esi, r13d
0x100403652  cmovb   esi, r13d
0x100403656  nop     word ptr [rax+rax+00000000h]
0x100403660  test    r15b, r15b
0x100403663  mov     eax, r12d
0x100403666  cmovz   eax, ebx
0x100403669  mov     ebx, eax
0x10040366b  cmp     eax, esi
0x10040366d  jnb     short loc_100403692
0x10040366f  nop
0x100403670  test    dil, dil
0x100403673  jz      short loc_10040367A
0x100403675  xor     dil, dil
0x100403678  jmp     short loc_100403685
0x10040367a  test    ebx, ebx
0x10040367c  jz      short loc_100403685
0x10040367e  mov     eax, [r14]
0x100403681  test    eax, eax
0x100403683  jz      short loc_10040368D
0x100403685  pause
0x100403687  inc     ebx
0x100403689  cmp     ebx, esi
0x10040368b  jb      short loc_100403670
0x10040368d  mov     rcx, [rsp+78h+var_40]
0x100403692  test    rcx, rcx
0x100403695  jz      short loc_1004036A9
0x100403697  mov     rcx, [rcx+8]
0x10040369b  mov     eax, ebx
0x10040369d  add     [rcx+428h], rax
0x1004036a4  mov     rcx, [rsp+78h+var_40]
0x1004036a9  cmp     ebx, esi
0x1004036ab  jnb     short loc_1004036CE
0x1004036ad  xor     eax, eax
0x1004036af  lock cmpxchg [r14], rbp
0x1004036b4  mov     eax, r12d
0x1004036b7  setz    al
0x1004036ba  test    eax, eax
0x1004036bc  jnz     short loc_100403732
0x1004036be  mov     rcx, [rsp+78h+var_40]
0x1004036c3  movzx   edi, r13b
0x1004036c7  mov     [rsp+78h+var_38], r12d
0x1004036cc  jmp     short loc_100403660
0x1004036ce  inc     [rsp+78h+var_38]
0x1004036d2  test    rcx, rcx
0x1004036d5  jz      short loc_100403717
0x1004036d7  movzx   edx, word ptr [rsp+78h+var_54]
0x1004036dc  mov     r8, r12
0x1004036df  sub     edx, r13d
0x1004036e2  jz      short loc_100403705
0x1004036e4  sub     edx, r13d
0x1004036e7  jz      short loc_1004036FF
0x1004036e9  sub     edx, r13d
0x1004036ec  jz      short loc_1004036F9
0x1004036ee  cmp     edx, r13d
0x1004036f1  jnz     short loc_100403709
0x1004036f3  mov     r8, [rcx+20h]
0x1004036f7  jmp     short loc_100403709
0x1004036f9  mov     r8, [rcx+18h]
0x1004036fd  jmp     short loc_100403709
0x1004036ff  mov     r8, [rcx+10h]
0x100403703  jmp     short loc_100403709
0x100403705  mov     r8, [rcx+8]
0x100403709  movzx   eax, [rsp+78h+var_58]
0x10040370e  imul    rcx, rax, 38h ; '8'
0x100403712  inc     qword ptr [rcx+r8+18h]
0x100403717  lea     rdx, [rsp+78h+var_58]
0x10040371c  mov     rcx, r14
0x10040371f  call    cs:__imp_?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z; SpinlockBase::Backoff(SpinlockBase::SpinInfo &)
0x100403725  mov     rcx, [rsp+78h+var_40]
0x10040372a  mov     ebx, r12d
0x10040372d  jmp     loc_100403660
0x100403732  lea     r11, [rsp+78h+var_28]
0x100403737  mov     rbx, [r11+30h]
0x10040373b  mov     rbp, [r11+40h]
0x10040373f  mov     rsi, [r11+48h]
0x100403743  mov     rsp, r11
0x100403746  pop     r15
0x100403748  pop     r14
0x10040374a  pop     r13
0x10040374c  pop     r12
0x10040374e  pop     rdi
0x10040374f  retn
```
