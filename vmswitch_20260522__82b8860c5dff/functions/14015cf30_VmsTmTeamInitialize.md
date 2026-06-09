# VmsTmTeamInitialize

- ea: `0x14015cf30`
- end: `0x14015d661`
- name: `VmsTmTeamInitialize`
- size: `1841`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140052f70`
- `0x14015da40`

## callees

- `0x14002e0f0`
- `0x14003e9e4`
- `0x140052460`
- `0x140139b5c`
- `0x14015b440`
- `0x14015c64c`
- `0x14015c7cc`
- `0x14015cc28`
- `0x14015cf30`
- `0x14015e294`
- `0x14015e4d4`
- `0x1401621b4`
- `0x140162f50`
- `0x140164cd0`
- `0x140166f94`
- `0x1401887f0`
- `0x14018ad8c`
- `0x1401bbc40`
- `0x1401bbfc0`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x14015d12c`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x14015d12c`
- `ntoskrnl!KeInitializeEvent` at `0x14015d108`
- `ntoskrnl!KeInitializeEvent` at `0x14015d120`
- `ntoskrnl!KeInitializeEvent` at `0x14015d2ee`
- `ntoskrnl!KeInitializeEvent` at `0x14015d108`
- `ntoskrnl!KeInitializeEvent` at `0x14015d120`
- `ntoskrnl!KeInitializeEvent` at `0x14015d2ee`
- `ntoskrnl!ExAllocatePool3` at `0x14015d057`
- `ntoskrnl!ExAllocatePool3` at `0x14015d15f`
- `ntoskrnl!ExAllocatePool3` at `0x14015d057`
- `ntoskrnl!ExAllocatePool3` at `0x14015d15f`
- `ntoskrnl!KeReleaseMutex` at `0x14015d3c2`
- `ntoskrnl!KeReleaseMutex` at `0x14015d3c2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14015d33c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14015d33c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015d62b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015d62b`
- `NDIS!NdisInitializeEvent` at `0x14015d298`
- `NDIS!NdisInitializeEvent` at `0x14015d298`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14015d1f6`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14015d1f6`
- `NDIS!NdisAcquireRWLockRead` at `0x14015d4f9`
- `NDIS!NdisAcquireRWLockRead` at `0x14015d4f9`
- `NDIS!NdisReleaseRWLock` at `0x14015d3b1`
- `NDIS!NdisReleaseRWLock` at `0x14015d52b`
- `NDIS!NdisReleaseRWLock` at `0x14015d3b1`
- `NDIS!NdisReleaseRWLock` at `0x14015d52b`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015d356`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015d356`

## pseudocode

```c
__int64 __fastcall VmsTmTeamInitialize(_QWORD *a1, _WORD *a2, char *a3)
{
  unsigned int VmsNicArray; // eax
  _DWORD *v7; // r12
  unsigned int v8; // ebx
  unsigned int i; // r8d
  char *v10; // rax
  char *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rsi
  int v14; // edx
  __int64 v15; // rcx
  bool v16; // al
  __int64 v17; // r9
  __int64 v18; // r15
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 RecommendedSharedDataAlignment; // rdi
  __int64 v22; // rax
  void *v23; // rcx
  NDIS_HANDLE NetBufferListPool; // rax
  unsigned int v25; // edi
  __int64 v26; // r15
  int v27; // r9d
  _WORD *v28; // rcx
  struct _NDIS_RW_LOCK_EX *v29; // rcx
  char v30; // r8
  const char *v31; // rdx
  unsigned int v32; // edi
  char *v33; // rdx
  const EVENT_DESCRIPTOR *v34; // rcx
  __int64 v35; // r8
  int v36; // edx
  __int64 v37; // rcx
  int Timeout; // [rsp+20h] [rbp-59h]
  int v40; // [rsp+48h] [rbp-31h]
  int Team; // [rsp+50h] [rbp-29h] BYREF
  struct _LOCK_STATE_EX v42; // [rsp+54h] [rbp-25h] BYREF
  PVOID P; // [rsp+58h] [rbp-21h] BYREF
  _WORD *v44; // [rsp+60h] [rbp-19h]
  __int128 v45; // [rsp+68h] [rbp-11h] BYREF
  _BYTE Parameters[20]; // [rsp+78h] [rbp-1h] BYREF

  v44 = a2;
  *(_WORD *)&v42.OldIrql = 0;
  v42.Flags = 0;
  *(_DWORD *)Parameters = 1048960;
  P = 0;
  *(_DWORD *)&Parameters[4] = 256;
  strcpy(&Parameters[8], "NicT|");
  *(_WORD *)&Parameters[14] = 0;
  *(_DWORD *)&Parameters[16] = 0;
  v45 = 0;
  VmsNicArray = VmsTmGetVmsNicArray(a1, &P);
  v7 = P;
  v8 = VmsNicArray;
  Team = VmsNicArray;
  if ( VmsNicArray )
    goto LABEL_15;
  if ( !a3 )
  {
    for ( i = 0; i < *((_DWORD *)P + 3); ++i )
    {
      v10 = (char *)P + *((_DWORD *)P + 4) * i;
      v11 = &v10[*((unsigned __int16 *)P + 4)];
      if ( !*((_DWORD *)v11 + 262) && *((_DWORD *)v11 + 263) == 2 && *((_WORD *)v11 + 522) )
      {
        a3 = &v10[*((unsigned __int16 *)P + 4)];
        memmove(a2, v11 + 2174, 6u);
        a2[8] = 1;
        if ( !a3 )
          goto LABEL_15;
        goto LABEL_10;
      }
    }
    goto LABEL_15;
  }
LABEL_10:
  DWORD2(v45) = 16;
  *(_QWORD *)&v45 = v45 & 0xFFFFFFFFFFFFFF00uLL | 1;
  v12 = ExAllocatePool3(64, 320, 1415801166, &v45, 1);
  v13 = v12;
  if ( !v12 )
  {
    v14 = -1073741670;
    v8 = -1073741670;
    Team = -1073741670;
    if ( a1 )
      v15 = a1[1137];
    else
      LODWORD(v15) = VmsIfrLog;
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_ld(v15, v14, 20, 15, (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids, 64, 154);
    goto LABEL_15;
  }
  *(_QWORD *)(v12 + 296) = a1;
  *(_QWORD *)(v12 + 304) = a1[537];
  *(_DWORD *)(v12 + 256) = 0;
  *(_WORD *)(v12 + 206) = 1;
  KeInitializeEvent((PRKEVENT)(v12 + 208), NotificationEvent, 0);
  KeInitializeEvent((PRKEVENT)(v13 + 232), NotificationEvent, 1u);
  RecommendedSharedDataAlignment = KeGetRecommendedSharedDataAlignment();
  v22 = ExAllocatePool3(
          64,
          RecommendedSharedDataAlignment + 320LL * LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) - 1,
          1415801166,
          &v45,
          1);
  *(_QWORD *)(v13 + 272) = v22;
  if ( !v22 )
  {
    v8 = -1073741670;
    Team = -1073741670;
    WPP_RECORDER_SF_ld(
      a1[1137],
      -1073741822,
      20,
      16,
      (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
      RecommendedSharedDataAlignment + (LOBYTE(WPP_MAIN_CB.Queue.Wcb.DeviceObject) << 6) - 1,
      154);
LABEL_15:
    v16 = 0;
    v17 = 0;
    v18 = 0;
    goto LABEL_16;
  }
  v23 = (void *)(~(RecommendedSharedDataAlignment - 1) & (RecommendedSharedDataAlignment - 1 + v22));
  *(_QWORD *)(v13 + 64) = v23;
  memset(v23, 0, 320LL * LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject));
  NetBufferListPool = NdisAllocateNetBufferListPool(
                        *(NDIS_HANDLE *)(v13 + 304),
                        (PNET_BUFFER_LIST_POOL_PARAMETERS)Parameters);
  v25 = 0;
  *(_QWORD *)(v13 + 264) = NetBufferListPool;
  if ( !NetBufferListPool )
  {
    v8 = -1073741670;
    Team = -1073741670;
    WPP_RECORDER_SF_qqd(
      a1[1137],
      -1073741822,
      20,
      17,
      (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
      *(_QWORD *)(v13 + 304),
      (char)Parameters,
      154);
    goto LABEL_15;
  }
  *(_DWORD *)(v13 + 256) = 1;
  Team = VmsTmCreateTeam(v13, (__int64)a2);
  v8 = Team;
  if ( Team )
    goto LABEL_15;
  v26 = *(_QWORD *)(v13 + 16);
  *(_BYTE *)(v13 + 204) |= 1u;
  *(_WORD *)(v13 + 202) &= 0xF000u;
  NdisInitializeEvent((PNDIS_EVENT)(v26 + 3840));
  a1[1125] = v13;
  if ( (*(_BYTE *)(v13 + 204) & 1) != 0
    && (unsigned int)(*(_DWORD *)(v26 + 1516) - 1) <= 1
    && *(_DWORD *)(v26 + 1520) == 1
    && (BYTE4(WPP_MAIN_CB.Queue.Wcb.DeviceObject) & 0x10) == 0 )
  {
    KeInitializeEvent((PRKEVENT)(v26 + 1488), NotificationEvent, 0);
    memset((void *)(v26 + 592), 0, 0x380u);
    vmqClearCapabilities(v26 + 592);
    *(_QWORD *)(v26 + 584) = v13;
    KeWaitForSingleObject((PVOID)(v26 + 1528), Executive, 0, 0, 0);
    NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v26 + 1584), &v42, 0);
    v28 = v44;
    *(_BYTE *)(v26 + 1460) = *((_BYTE *)v44 + 36);
    *(_BYTE *)(v26 + 1461) = *((_BYTE *)v28 + 37);
    *(_BYTE *)(v26 + 1462) = *((_BYTE *)v28 + 38);
    vmqClearCapabilities(v26 + 1028);
    vmqIndicateCapsChange(v26 + 584);
    *(_BYTE *)(v13 + 204) |= 2u;
    v29 = *(struct _NDIS_RW_LOCK_EX **)(v26 + 1584);
    *(_QWORD *)(v26 + 144) = v13;
    NdisReleaseRWLock(v29, &v42);
    KeReleaseMutex((PRKMUTEX)(v26 + 1528), 0);
    v25 = 0;
  }
  if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    v30 = *(_BYTE *)(v13 + 204);
    v31 = "sum";
    if ( (v30 & 2) == 0 )
      v31 = "min";
    WPP_RECORDER_SF_qqdls(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v31,
      v30 & 1,
      v27,
      Timeout,
      v13,
      v26,
      *(_WORD *)(v13 + 202),
      v30 & 1,
      (__int64)v31);
  }
  Team = VmsTmInitTeamWithPnP((PVOID)v26);
  v8 = Team;
  if ( !Team )
  {
    while ( v25 < v7[3] )
    {
      Team = VmsTmAddVmsPort(v13, (char *)v7 + v7[4] * v25 + *((unsigned __int16 *)v7 + 4), 0);
      v8 = Team;
      if ( Team )
        goto LABEL_49;
      ++v25;
    }
    v32 = 0;
    Team = VmsTmAddNicToTeam(v13, a3);
    v8 = Team;
    if ( !Team )
    {
      while ( v32 < v7[3] )
      {
        v33 = (char *)v7 + v7[4] * v32 + *((unsigned __int16 *)v7 + 4);
        if ( !*((_DWORD *)v33 + 262) && *((_DWORD *)v33 + 263) == 2 )
        {
          if ( *((_WORD *)v33 + 522) )
          {
            if ( v33 != a3 )
            {
              Team = VmsTmAddNicToTeam(v13, v33);
              v8 = Team;
              if ( Team )
                goto LABEL_49;
            }
          }
        }
        ++v32;
      }
      NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v26 + 1584), &v42, 0);
      if ( (*(_BYTE *)(v13 + 204) & 2) != 0 )
        lbfoCalculateVmqCaps(v26);
      *(_DWORD *)(v13 + 256) = 3;
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v26 + 1584), &v42);
      if ( a1[533] )
        VmsPtNicMuxCalculateProtocolNicLinkState();
    }
  }
LABEL_49:
  if ( !v26 )
    goto LABEL_15;
  v17 = v26 + 1516;
  v16 = (*(_BYTE *)(v13 + 204) & 2) != 0;
  v18 = v26 + 1520;
LABEL_16:
  if ( a1 )
  {
    v19 = (__int64)(a1 + 77);
    v20 = (__int64)(a1 + 9);
  }
  else
  {
    v19 = 0;
    v20 = 0;
  }
  LOBYTE(v40) = v16;
  v34 = (const EVENT_DESCRIPTOR *)VM_EMBEDDED_TEAMING_TEAM_INITIALIZATION_SUCCEEDED;
  if ( v8 )
    v34 = &VM_EMBEDDED_TEAMING_TEAM_INITIALIZATION_FAILED;
  VmsEtwTraceEmbeddedTeaming(v34, (__int64)&Team, v20, v19, v18, v17, v40);
  LOBYTE(v35) = 1;
  VmsTraceLoggingTraceEmbeddedTeamingTeamOperation(v8, a1, v35);
  if ( v8 )
  {
    VmsTmTeamDetach(a1);
    if ( a1 )
      v37 = a1[1137];
    else
      LODWORD(v37) = VmsIfrLog;
    LOBYTE(v36) = 2;
    WPP_RECORDER_SF_qqqd(
      v37,
      v36,
      20,
      19,
      (__int64)WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids,
      (char)a1,
      (char)v44,
      (char)a3,
      v8);
  }
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  return v8;
}

```

## disassembly

```asm
0x14015cf30  mov     [rsp-8+arg_18], rbx
0x14015cf35  push    rbp
0x14015cf36  push    rsi
0x14015cf37  push    rdi
0x14015cf38  push    r12
0x14015cf3a  push    r13
0x14015cf3c  push    r14
0x14015cf3e  push    r15
0x14015cf40  lea     rbp, [rsp-27h]
0x14015cf45  sub     rsp, 0A0h
0x14015cf4c  mov     rax, cs:__security_cookie
0x14015cf53  xor     rax, rsp
0x14015cf56  mov     [rbp+57h+var_40], rax
0x14015cf5a  xor     eax, eax
0x14015cf5c  mov     [rbp+57h+var_70], rdx
0x14015cf60  mov     r15, rdx
0x14015cf63  mov     word ptr [rbp+57h+var_80+4], ax
0x14015cf67  xorps   xmm0, xmm0
0x14015cf6a  mov     byte ptr [rbp+57h+var_80+6], al
0x14015cf6d  xor     edi, edi
0x14015cf6f  mov     dword ptr [rbp+57h+Parameters], 100180h
0x14015cf76  lea     rdx, [rbp+57h+P]
0x14015cf7a  mov     [rbp+57h+P], rdi
0x14015cf7e  lea     esi, [rax+1]
0x14015cf81  mov     dword ptr [rbp+57h+Parameters+4], 100h
0x14015cf88  mov     r13, r8
0x14015cf8b  mov     dword ptr [rbp+57h+Parameters+8], 5463694Eh
0x14015cf92  mov     r14, rcx
0x14015cf95  mov     qword ptr [rbp+57h+Parameters+0Ch], 7Ch ; '|'
0x14015cf9d  movups  [rbp+57h+var_68], xmm0
0x14015cfa1  call    VmsTmGetVmsNicArray
0x14015cfa6  mov     r12, [rbp+57h+P]
0x14015cfaa  mov     ebx, eax
0x14015cfac  mov     dword ptr [rbp+57h+var_80], eax
0x14015cfaf  test    eax, eax
0x14015cfb1  jnz     loc_14015D0B8
0x14015cfb7  test    r13, r13
0x14015cfba  jnz     short loc_14015D027
0x14015cfbc  mov     r9d, [r12+0Ch]
0x14015cfc1  mov     r8d, edi
0x14015cfc4  cmp     r8d, r9d
0x14015cfc7  jnb     loc_14015D0B8
0x14015cfcd  movzx   edx, word ptr [r12+8]
0x14015cfd3  mov     eax, r8d
0x14015cfd6  imul    eax, [r12+10h]
0x14015cfdc  add     rax, r12
0x14015cfdf  add     rdx, rax
0x14015cfe2  cmp     [rdx+418h], edi
0x14015cfe8  jnz     short loc_14015CFFC
0x14015cfea  cmp     dword ptr [rdx+41Ch], 2
0x14015cff1  jnz     short loc_14015CFFC
0x14015cff3  cmp     [rdx+414h], di
0x14015cffa  jnz     short loc_14015D001
0x14015cffc  add     r8d, esi
0x14015cfff  jmp     short loc_14015CFC4
0x14015d001  mov     r13, rdx
0x14015d004  mov     r8d, 6; Size
0x14015d00a  add     rdx, 87Eh; Src
0x14015d011  mov     rcx, r15; void *
0x14015d014  call    memmove
0x14015d019  mov     [r15+10h], si
0x14015d01e  test    r13, r13
0x14015d021  jz      loc_14015D0B8
0x14015d027  mov     rax, qword ptr [rbp+57h+var_68]
0x14015d02b  lea     r9, [rbp+57h+var_68]
0x14015d02f  and     rax, 0FFFFFFFFFFFFFF01h
0x14015d035  mov     dword ptr [rbp+57h+var_68+8], 10h
0x14015d03c  or      rax, rsi
0x14015d03f  mov     dword ptr [rsp+0D0h+Timeout], esi
0x14015d043  mov     edx, 140h
0x14015d048  mov     qword ptr [rbp+57h+var_68], rax
0x14015d04c  mov     ecx, 40h ; '@'
0x14015d051  mov     r8d, 5463694Eh
0x14015d057  call    cs:__imp_ExAllocatePool3
0x14015d05e  nop     dword ptr [rax+rax+00h]
0x14015d063  mov     rsi, rax
0x14015d066  test    rax, rax
0x14015d069  jnz     short loc_14015D0D5
0x14015d06b  mov     edx, 0C000009Ah
0x14015d070  mov     ebx, edx
0x14015d072  mov     dword ptr [rbp+57h+var_80], edx
0x14015d075  test    r14, r14
0x14015d078  jz      short loc_14015D083
0x14015d07a  mov     rcx, [r14+2388h]
0x14015d081  jmp     short loc_14015D08A
0x14015d083  mov     rcx, cs:VmsIfrLog
0x14015d08a  mov     dword ptr [rsp+0D0h+var_A0], edx
0x14015d08e  lea     rax, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015d095  mov     r9d, 0Fh
0x14015d09b  mov     dword ptr [rsp+0D0h+var_A8], 140h
0x14015d0a3  mov     dl, 2
0x14015d0a5  mov     [rsp+0D0h+Timeout], rax
0x14015d0aa  lea     r8d, [r9+5]
0x14015d0ae  call    WPP_RECORDER_SF_ld
0x14015d0b3  mov     esi, 1
0x14015d0b8  mov     al, dil
0x14015d0bb  mov     r9, rdi
0x14015d0be  mov     r15, rdi
0x14015d0c1  test    r14, r14
0x14015d0c4  jnz     loc_14015D57A
0x14015d0ca  mov     rdx, rdi
0x14015d0cd  mov     r8, rdi
0x14015d0d0  jmp     loc_14015D585
0x14015d0d5  mov     [rax+128h], r14
0x14015d0dc  lea     rcx, [rsi+0D0h]; Event
0x14015d0e3  mov     rax, [r14+10C8h]
0x14015d0ea  mov     ebx, 1
0x14015d0ef  xor     r8d, r8d; State
0x14015d0f2  mov     [rsi+130h], rax
0x14015d0f9  xor     edx, edx; Type
0x14015d0fb  mov     [rsi+100h], edi
0x14015d101  mov     [rsi+0CEh], bx
0x14015d108  call    cs:__imp_KeInitializeEvent
0x14015d10f  nop     dword ptr [rax+rax+00h]
0x14015d114  lea     rcx, [rsi+0E8h]; Event
0x14015d11b  mov     r8b, bl; State
0x14015d11e  xor     edx, edx; Type
0x14015d120  call    cs:__imp_KeInitializeEvent
0x14015d127  nop     dword ptr [rax+rax+00h]
0x14015d12c  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x14015d133  nop     dword ptr [rax+rax+00h]
0x14015d138  lea     r9, [rbp+57h+var_68]
0x14015d13c  mov     dword ptr [rsp+0D0h+Timeout], ebx
0x14015d140  mov     edi, eax
0x14015d142  lea     ecx, [rbx+3Fh]
0x14015d145  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+30h
0x14015d14b  mov     r8d, 5463694Eh
0x14015d151  lea     rdx, [rax+rax*4]
0x14015d155  shl     rdx, 6
0x14015d159  dec     rdx
0x14015d15c  add     rdx, rdi
0x14015d15f  call    cs:__imp_ExAllocatePool3
0x14015d166  nop     dword ptr [rax+rax+00h]
0x14015d16b  mov     [rsi+110h], rax
0x14015d172  mov     rcx, rax
0x14015d175  test    rax, rax
0x14015d178  jnz     short loc_14015D1C5
0x14015d17a  mov     edx, 0C000009Ah
0x14015d17f  mov     ebx, edx
0x14015d181  mov     dword ptr [rbp+57h+var_80], edx
0x14015d184  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+30h
0x14015d18a  lea     r9d, [rcx+10h]
0x14015d18e  mov     dword ptr [rsp+0D0h+var_A0], edx
0x14015d192  lea     r8d, [rcx+14h]
0x14015d196  mov     rcx, [r14+2388h]
0x14015d19d  mov     dl, 2
0x14015d19f  lea     eax, [rax+rax*4]
0x14015d1a2  shl     eax, 6
0x14015d1a5  dec     eax
0x14015d1a7  add     eax, edi
0x14015d1a9  mov     dword ptr [rsp+0D0h+var_A8], eax
0x14015d1ad  lea     rax, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015d1b4  mov     [rsp+0D0h+Timeout], rax
0x14015d1b9  call    WPP_RECORDER_SF_ld
0x14015d1be  xor     edi, edi
0x14015d1c0  jmp     loc_14015D0B3
0x14015d1c5  lea     rax, [rdi-1]
0x14015d1c9  xor     edx, edx; Val
0x14015d1cb  add     rcx, rax
0x14015d1ce  not     rax
0x14015d1d1  and     rcx, rax; void *
0x14015d1d4  mov     [rsi+40h], rcx
0x14015d1d8  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+30h
0x14015d1de  lea     r8, [rax+rax*4]
0x14015d1e2  shl     r8, 6; Size
0x14015d1e6  call    memset
0x14015d1eb  mov     rcx, [rsi+130h]; NdisHandle
0x14015d1f2  lea     rdx, [rbp+57h+Parameters]; Parameters
0x14015d1f6  call    cs:__imp_NdisAllocateNetBufferListPool
0x14015d1fd  nop     dword ptr [rax+rax+00h]
0x14015d202  xor     edi, edi
0x14015d204  mov     [rsi+108h], rax
0x14015d20b  test    rax, rax
0x14015d20e  jnz     short loc_14015D25A
0x14015d210  mov     edx, 0C000009Ah
0x14015d215  mov     ebx, edx
0x14015d217  mov     dword ptr [rbp+57h+var_80], edx
0x14015d21a  mov     rcx, [r14+2388h]
0x14015d221  lea     r9d, [rax+11h]
0x14015d225  mov     dword ptr [rsp+0D0h+var_98], edx
0x14015d229  lea     rax, [rbp+57h+Parameters]
0x14015d22d  mov     [rsp+0D0h+var_A0], rax
0x14015d232  lea     r8d, [rdi+14h]
0x14015d236  mov     rax, [rsi+130h]
0x14015d23d  mov     dl, 2
0x14015d23f  mov     [rsp+0D0h+var_A8], rax
0x14015d244  lea     rax, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015d24b  mov     [rsp+0D0h+Timeout], rax
0x14015d250  call    WPP_RECORDER_SF_qqd
0x14015d255  jmp     loc_14015D0B3
0x14015d25a  mov     rdx, r15
0x14015d25d  mov     [rsi+100h], ebx
0x14015d263  mov     rcx, rsi
0x14015d266  call    VmsTmCreateTeam
0x14015d26b  mov     dword ptr [rbp+57h+var_80], eax
0x14015d26e  mov     ebx, eax
0x14015d270  test    eax, eax
0x14015d272  jnz     loc_14015D0B3
0x14015d278  mov     r15, [rsi+10h]
0x14015d27c  lea     ebx, [rax+1]
0x14015d27f  or      [rsi+0CCh], bl
0x14015d285  mov     eax, 0F000h
0x14015d28a  and     [rsi+0CAh], ax
0x14015d291  lea     rcx, [r15+0F00h]; Event
0x14015d298  call    cs:__imp_NdisInitializeEvent
0x14015d29f  nop     dword ptr [rax+rax+00h]
0x14015d2a4  mov     [r14+2328h], rsi
0x14015d2ab  test    [rsi+0CCh], bl
0x14015d2b1  jz      loc_14015D3D3
0x14015d2b7  mov     eax, [r15+5ECh]
0x14015d2be  sub     eax, ebx
0x14015d2c0  cmp     eax, ebx
0x14015d2c2  ja      loc_14015D3D3
0x14015d2c8  cmp     [r15+5F0h], ebx
0x14015d2cf  jnz     loc_14015D3D3
0x14015d2d5  test    byte ptr cs:WPP_MAIN_CB.Queue+34h, 10h
0x14015d2dc  jnz     loc_14015D3D3
0x14015d2e2  lea     rcx, [r15+5D0h]; Event
0x14015d2e9  xor     r8d, r8d; State
0x14015d2ec  xor     edx, edx; Type
0x14015d2ee  call    cs:__imp_KeInitializeEvent
0x14015d2f5  nop     dword ptr [rax+rax+00h]
0x14015d2fa  lea     rcx, [r15+250h]; void *
0x14015d301  xor     edx, edx; Val
0x14015d303  mov     r8d, 380h; Size
0x14015d309  lea     rbx, [r15+248h]
0x14015d310  call    memset
0x14015d315  lea     rcx, [rbx+8]
0x14015d319  call    vmqClearCapabilities
0x14015d31e  lea     rdi, [r15+5F8h]
0x14015d325  mov     [rbx], rsi
0x14015d328  mov     rcx, rdi; Object
0x14015d32b  mov     [rsp+0D0h+Timeout], 0; Timeout
0x14015d334  xor     r9d, r9d; Alertable
0x14015d337  xor     r8d, r8d; WaitMode
0x14015d33a  xor     edx, edx; WaitReason
0x14015d33c  call    cs:__imp_KeWaitForSingleObject
0x14015d343  nop     dword ptr [rax+rax+00h]
0x14015d348  mov     rcx, [r15+630h]; Lock
0x14015d34f  lea     rdx, [rbp+57h+var_80+4]; LockState
0x14015d353  xor     r8d, r8d; Flags
0x14015d356  call    cs:__imp_NdisAcquireRWLockWrite
0x14015d35d  nop     dword ptr [rax+rax+00h]
0x14015d362  mov     rcx, [rbp+57h+var_70]
0x14015d366  mov     al, [rcx+24h]
0x14015d369  mov     [r15+5B4h], al
0x14015d370  mov     al, [rcx+25h]
0x14015d373  mov     [r15+5B5h], al
0x14015d37a  mov     al, [rcx+26h]
0x14015d37d  lea     rcx, [r15+404h]
0x14015d384  mov     [r15+5B6h], al
0x14015d38b  call    vmqClearCapabilities
0x14015d390  mov     rcx, rbx
0x14015d393  call    vmqIndicateCapsChange
0x14015d398  or      byte ptr [rsi+0CCh], 2
0x14015d39f  lea     rdx, [rbp+57h+var_80+4]; LockState
0x14015d3a3  mov     rcx, [r15+630h]; Lock
0x14015d3aa  mov     [r15+90h], rsi
0x14015d3b1  call    cs:__imp_NdisReleaseRWLock
0x14015d3b8  nop     dword ptr [rax+rax+00h]
0x14015d3bd  xor     edx, edx; Wait
0x14015d3bf  mov     rcx, rdi; Mutex
0x14015d3c2  call    cs:__imp_KeReleaseMutex
0x14015d3c9  nop     dword ptr [rax+rax+00h]
0x14015d3ce  xor     edi, edi
0x14015d3d0  lea     ebx, [rdi+1]
0x14015d3d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14015d3da  mov     al, [rcx+29h]
0x14015d3dd  sub     al, bl
0x14015d3df  cmp     al, 2
0x14015d3e1  ja      short loc_14015D3E9
0x14015d3e3  cmp     [rcx+48h], di
0x14015d3e7  jz      short loc_14015D437
0x14015d3e9  movzx   r8d, byte ptr [rsi+0CCh]
0x14015d3f1  lea     rax, aMin; "min"
0x14015d3f8  mov     rcx, [rcx+40h]
0x14015d3fc  lea     rdx, aSum; "sum"
0x14015d403  test    r8b, 2
0x14015d407  cmovz   rdx, rax
0x14015d40b  movzx   eax, word ptr [rsi+0CAh]
0x14015d412  mov     qword ptr [rsp+0D0h+var_88], rdx
0x14015d417  and     r8d, ebx
0x14015d41a  mov     dword ptr [rsp+0D0h+var_90], r8d
0x14015d41f  and     eax, 0FFFh
0x14015d424  mov     dword ptr [rsp+0D0h+var_98], eax
0x14015d428  mov     [rsp+0D0h+var_A0], r15
0x14015d42d  mov     [rsp+0D0h+var_A8], rsi
0x14015d432  call    WPP_RECORDER_SF_qqdls
0x14015d437  mov     rcx, r15; FunctionContext
0x14015d43a  call    VmsTmInitTeamWithPnP
0x14015d43f  mov     dword ptr [rbp+57h+var_80], eax
0x14015d442  mov     ebx, eax
0x14015d444  test    eax, eax
0x14015d446  jnz     loc_14015D54E
0x14015d44c  mov     rcx, rsi
0x14015d44f  cmp     edi, [r12+0Ch]
0x14015d454  jnb     short loc_14015D483
0x14015d456  movzx   edx, word ptr [r12+8]
0x14015d45c  mov     eax, edi
0x14015d45e  imul    eax, [r12+10h]
  ... truncated ...
```
