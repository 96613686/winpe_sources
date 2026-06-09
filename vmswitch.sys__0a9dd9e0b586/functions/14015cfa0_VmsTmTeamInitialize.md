# VmsTmTeamInitialize

- ea: `0x14015cfa0`
- end: `0x14015d6d1`
- name: `VmsTmTeamInitialize`
- size: `1841`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140052f70`
- `0x14015dab0`

## callees

- `0x14002e0f0`
- `0x14003e9e4`
- `0x140052460`
- `0x140139bcc`
- `0x14015b4b0`
- `0x14015c6bc`
- `0x14015c83c`
- `0x14015cc98`
- `0x14015cfa0`
- `0x14015e304`
- `0x14015e544`
- `0x140162224`
- `0x140162fc0`
- `0x140164d40`
- `0x140167004`
- `0x140188860`
- `0x14018adfc`
- `0x1401bbcb0`
- `0x1401bc040`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x14015d19c`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x14015d19c`
- `ntoskrnl!KeInitializeEvent` at `0x14015d178`
- `ntoskrnl!KeInitializeEvent` at `0x14015d190`
- `ntoskrnl!KeInitializeEvent` at `0x14015d35e`
- `ntoskrnl!KeInitializeEvent` at `0x14015d178`
- `ntoskrnl!KeInitializeEvent` at `0x14015d190`
- `ntoskrnl!KeInitializeEvent` at `0x14015d35e`
- `ntoskrnl!ExAllocatePool3` at `0x14015d0c7`
- `ntoskrnl!ExAllocatePool3` at `0x14015d1cf`
- `ntoskrnl!ExAllocatePool3` at `0x14015d0c7`
- `ntoskrnl!ExAllocatePool3` at `0x14015d1cf`
- `ntoskrnl!KeReleaseMutex` at `0x14015d432`
- `ntoskrnl!KeReleaseMutex` at `0x14015d432`
- `ntoskrnl!KeWaitForSingleObject` at `0x14015d3ac`
- `ntoskrnl!KeWaitForSingleObject` at `0x14015d3ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015d69b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015d69b`
- `NDIS!NdisInitializeEvent` at `0x14015d308`
- `NDIS!NdisInitializeEvent` at `0x14015d308`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14015d266`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14015d266`
- `NDIS!NdisAcquireRWLockRead` at `0x14015d569`
- `NDIS!NdisAcquireRWLockRead` at `0x14015d569`
- `NDIS!NdisReleaseRWLock` at `0x14015d421`
- `NDIS!NdisReleaseRWLock` at `0x14015d59b`
- `NDIS!NdisReleaseRWLock` at `0x14015d421`
- `NDIS!NdisReleaseRWLock` at `0x14015d59b`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015d3c6`
- `NDIS!NdisAcquireRWLockWrite` at `0x14015d3c6`

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
0x14015cfa0  mov     [rsp-8+arg_18], rbx
0x14015cfa5  push    rbp
0x14015cfa6  push    rsi
0x14015cfa7  push    rdi
0x14015cfa8  push    r12
0x14015cfaa  push    r13
0x14015cfac  push    r14
0x14015cfae  push    r15
0x14015cfb0  lea     rbp, [rsp-27h]
0x14015cfb5  sub     rsp, 0A0h
0x14015cfbc  mov     rax, cs:__security_cookie
0x14015cfc3  xor     rax, rsp
0x14015cfc6  mov     [rbp+57h+var_40], rax
0x14015cfca  xor     eax, eax
0x14015cfcc  mov     [rbp+57h+var_70], rdx
0x14015cfd0  mov     r15, rdx
0x14015cfd3  mov     word ptr [rbp+57h+var_80+4], ax
0x14015cfd7  xorps   xmm0, xmm0
0x14015cfda  mov     byte ptr [rbp+57h+var_80+6], al
0x14015cfdd  xor     edi, edi
0x14015cfdf  mov     dword ptr [rbp+57h+Parameters], 100180h
0x14015cfe6  lea     rdx, [rbp+57h+P]
0x14015cfea  mov     [rbp+57h+P], rdi
0x14015cfee  lea     esi, [rax+1]
0x14015cff1  mov     dword ptr [rbp+57h+Parameters+4], 100h
0x14015cff8  mov     r13, r8
0x14015cffb  mov     dword ptr [rbp+57h+Parameters+8], 5463694Eh
0x14015d002  mov     r14, rcx
0x14015d005  mov     qword ptr [rbp+57h+Parameters+0Ch], 7Ch ; '|'
0x14015d00d  movups  [rbp+57h+var_68], xmm0
0x14015d011  call    VmsTmGetVmsNicArray
0x14015d016  mov     r12, [rbp+57h+P]
0x14015d01a  mov     ebx, eax
0x14015d01c  mov     dword ptr [rbp+57h+var_80], eax
0x14015d01f  test    eax, eax
0x14015d021  jnz     loc_14015D128
0x14015d027  test    r13, r13
0x14015d02a  jnz     short loc_14015D097
0x14015d02c  mov     r9d, [r12+0Ch]
0x14015d031  mov     r8d, edi
0x14015d034  cmp     r8d, r9d
0x14015d037  jnb     loc_14015D128
0x14015d03d  movzx   edx, word ptr [r12+8]
0x14015d043  mov     eax, r8d
0x14015d046  imul    eax, [r12+10h]
0x14015d04c  add     rax, r12
0x14015d04f  add     rdx, rax
0x14015d052  cmp     [rdx+418h], edi
0x14015d058  jnz     short loc_14015D06C
0x14015d05a  cmp     dword ptr [rdx+41Ch], 2
0x14015d061  jnz     short loc_14015D06C
0x14015d063  cmp     [rdx+414h], di
0x14015d06a  jnz     short loc_14015D071
0x14015d06c  add     r8d, esi
0x14015d06f  jmp     short loc_14015D034
0x14015d071  mov     r13, rdx
0x14015d074  mov     r8d, 6; Size
0x14015d07a  add     rdx, 87Eh; Src
0x14015d081  mov     rcx, r15; void *
0x14015d084  call    memmove
0x14015d089  mov     [r15+10h], si
0x14015d08e  test    r13, r13
0x14015d091  jz      loc_14015D128
0x14015d097  mov     rax, qword ptr [rbp+57h+var_68]
0x14015d09b  lea     r9, [rbp+57h+var_68]
0x14015d09f  and     rax, 0FFFFFFFFFFFFFF01h
0x14015d0a5  mov     dword ptr [rbp+57h+var_68+8], 10h
0x14015d0ac  or      rax, rsi
0x14015d0af  mov     dword ptr [rsp+0D0h+Timeout], esi
0x14015d0b3  mov     edx, 140h
0x14015d0b8  mov     qword ptr [rbp+57h+var_68], rax
0x14015d0bc  mov     ecx, 40h ; '@'
0x14015d0c1  mov     r8d, 5463694Eh
0x14015d0c7  call    cs:__imp_ExAllocatePool3
0x14015d0ce  nop     dword ptr [rax+rax+00h]
0x14015d0d3  mov     rsi, rax
0x14015d0d6  test    rax, rax
0x14015d0d9  jnz     short loc_14015D145
0x14015d0db  mov     edx, 0C000009Ah
0x14015d0e0  mov     ebx, edx
0x14015d0e2  mov     dword ptr [rbp+57h+var_80], edx
0x14015d0e5  test    r14, r14
0x14015d0e8  jz      short loc_14015D0F3
0x14015d0ea  mov     rcx, [r14+2388h]
0x14015d0f1  jmp     short loc_14015D0FA
0x14015d0f3  mov     rcx, cs:VmsIfrLog
0x14015d0fa  mov     dword ptr [rsp+0D0h+var_A0], edx
0x14015d0fe  lea     rax, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015d105  mov     r9d, 0Fh
0x14015d10b  mov     dword ptr [rsp+0D0h+var_A8], 140h
0x14015d113  mov     dl, 2
0x14015d115  mov     [rsp+0D0h+Timeout], rax
0x14015d11a  lea     r8d, [r9+5]
0x14015d11e  call    WPP_RECORDER_SF_ld
0x14015d123  mov     esi, 1
0x14015d128  mov     al, dil
0x14015d12b  mov     r9, rdi
0x14015d12e  mov     r15, rdi
0x14015d131  test    r14, r14
0x14015d134  jnz     loc_14015D5EA
0x14015d13a  mov     rdx, rdi
0x14015d13d  mov     r8, rdi
0x14015d140  jmp     loc_14015D5F5
0x14015d145  mov     [rax+128h], r14
0x14015d14c  lea     rcx, [rsi+0D0h]; Event
0x14015d153  mov     rax, [r14+10C8h]
0x14015d15a  mov     ebx, 1
0x14015d15f  xor     r8d, r8d; State
0x14015d162  mov     [rsi+130h], rax
0x14015d169  xor     edx, edx; Type
0x14015d16b  mov     [rsi+100h], edi
0x14015d171  mov     [rsi+0CEh], bx
0x14015d178  call    cs:__imp_KeInitializeEvent
0x14015d17f  nop     dword ptr [rax+rax+00h]
0x14015d184  lea     rcx, [rsi+0E8h]; Event
0x14015d18b  mov     r8b, bl; State
0x14015d18e  xor     edx, edx; Type
0x14015d190  call    cs:__imp_KeInitializeEvent
0x14015d197  nop     dword ptr [rax+rax+00h]
0x14015d19c  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x14015d1a3  nop     dword ptr [rax+rax+00h]
0x14015d1a8  lea     r9, [rbp+57h+var_68]
0x14015d1ac  mov     dword ptr [rsp+0D0h+Timeout], ebx
0x14015d1b0  mov     edi, eax
0x14015d1b2  lea     ecx, [rbx+3Fh]
0x14015d1b5  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+30h
0x14015d1bb  mov     r8d, 5463694Eh
0x14015d1c1  lea     rdx, [rax+rax*4]
0x14015d1c5  shl     rdx, 6
0x14015d1c9  dec     rdx
0x14015d1cc  add     rdx, rdi
0x14015d1cf  call    cs:__imp_ExAllocatePool3
0x14015d1d6  nop     dword ptr [rax+rax+00h]
0x14015d1db  mov     [rsi+110h], rax
0x14015d1e2  mov     rcx, rax
0x14015d1e5  test    rax, rax
0x14015d1e8  jnz     short loc_14015D235
0x14015d1ea  mov     edx, 0C000009Ah
0x14015d1ef  mov     ebx, edx
0x14015d1f1  mov     dword ptr [rbp+57h+var_80], edx
0x14015d1f4  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+30h
0x14015d1fa  lea     r9d, [rcx+10h]
0x14015d1fe  mov     dword ptr [rsp+0D0h+var_A0], edx
0x14015d202  lea     r8d, [rcx+14h]
0x14015d206  mov     rcx, [r14+2388h]
0x14015d20d  mov     dl, 2
0x14015d20f  lea     eax, [rax+rax*4]
0x14015d212  shl     eax, 6
0x14015d215  dec     eax
0x14015d217  add     eax, edi
0x14015d219  mov     dword ptr [rsp+0D0h+var_A8], eax
0x14015d21d  lea     rax, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015d224  mov     [rsp+0D0h+Timeout], rax
0x14015d229  call    WPP_RECORDER_SF_ld
0x14015d22e  xor     edi, edi
0x14015d230  jmp     loc_14015D123
0x14015d235  lea     rax, [rdi-1]
0x14015d239  xor     edx, edx; Val
0x14015d23b  add     rcx, rax
0x14015d23e  not     rax
0x14015d241  and     rcx, rax; void *
0x14015d244  mov     [rsi+40h], rcx
0x14015d248  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+30h
0x14015d24e  lea     r8, [rax+rax*4]
0x14015d252  shl     r8, 6; Size
0x14015d256  call    memset
0x14015d25b  mov     rcx, [rsi+130h]; NdisHandle
0x14015d262  lea     rdx, [rbp+57h+Parameters]; Parameters
0x14015d266  call    cs:__imp_NdisAllocateNetBufferListPool
0x14015d26d  nop     dword ptr [rax+rax+00h]
0x14015d272  xor     edi, edi
0x14015d274  mov     [rsi+108h], rax
0x14015d27b  test    rax, rax
0x14015d27e  jnz     short loc_14015D2CA
0x14015d280  mov     edx, 0C000009Ah
0x14015d285  mov     ebx, edx
0x14015d287  mov     dword ptr [rbp+57h+var_80], edx
0x14015d28a  mov     rcx, [r14+2388h]
0x14015d291  lea     r9d, [rax+11h]
0x14015d295  mov     dword ptr [rsp+0D0h+var_98], edx
0x14015d299  lea     rax, [rbp+57h+Parameters]
0x14015d29d  mov     [rsp+0D0h+var_A0], rax
0x14015d2a2  lea     r8d, [rdi+14h]
0x14015d2a6  mov     rax, [rsi+130h]
0x14015d2ad  mov     dl, 2
0x14015d2af  mov     [rsp+0D0h+var_A8], rax
0x14015d2b4  lea     rax, WPP_8d18035697e5374b15dcad7d63bbb9e2_Traceguids
0x14015d2bb  mov     [rsp+0D0h+Timeout], rax
0x14015d2c0  call    WPP_RECORDER_SF_qqd
0x14015d2c5  jmp     loc_14015D123
0x14015d2ca  mov     rdx, r15
0x14015d2cd  mov     [rsi+100h], ebx
0x14015d2d3  mov     rcx, rsi
0x14015d2d6  call    VmsTmCreateTeam
0x14015d2db  mov     dword ptr [rbp+57h+var_80], eax
0x14015d2de  mov     ebx, eax
0x14015d2e0  test    eax, eax
0x14015d2e2  jnz     loc_14015D123
0x14015d2e8  mov     r15, [rsi+10h]
0x14015d2ec  lea     ebx, [rax+1]
0x14015d2ef  or      [rsi+0CCh], bl
0x14015d2f5  mov     eax, 0F000h
0x14015d2fa  and     [rsi+0CAh], ax
0x14015d301  lea     rcx, [r15+0F00h]; Event
0x14015d308  call    cs:__imp_NdisInitializeEvent
0x14015d30f  nop     dword ptr [rax+rax+00h]
0x14015d314  mov     [r14+2328h], rsi
0x14015d31b  test    [rsi+0CCh], bl
0x14015d321  jz      loc_14015D443
0x14015d327  mov     eax, [r15+5ECh]
0x14015d32e  sub     eax, ebx
0x14015d330  cmp     eax, ebx
0x14015d332  ja      loc_14015D443
0x14015d338  cmp     [r15+5F0h], ebx
0x14015d33f  jnz     loc_14015D443
0x14015d345  test    byte ptr cs:WPP_MAIN_CB.Queue+34h, 10h
0x14015d34c  jnz     loc_14015D443
0x14015d352  lea     rcx, [r15+5D0h]; Event
0x14015d359  xor     r8d, r8d; State
0x14015d35c  xor     edx, edx; Type
0x14015d35e  call    cs:__imp_KeInitializeEvent
0x14015d365  nop     dword ptr [rax+rax+00h]
0x14015d36a  lea     rcx, [r15+250h]; void *
0x14015d371  xor     edx, edx; Val
0x14015d373  mov     r8d, 380h; Size
0x14015d379  lea     rbx, [r15+248h]
0x14015d380  call    memset
0x14015d385  lea     rcx, [rbx+8]
0x14015d389  call    vmqClearCapabilities
0x14015d38e  lea     rdi, [r15+5F8h]
0x14015d395  mov     [rbx], rsi
0x14015d398  mov     rcx, rdi; Object
0x14015d39b  mov     [rsp+0D0h+Timeout], 0; Timeout
0x14015d3a4  xor     r9d, r9d; Alertable
0x14015d3a7  xor     r8d, r8d; WaitMode
0x14015d3aa  xor     edx, edx; WaitReason
0x14015d3ac  call    cs:__imp_KeWaitForSingleObject
0x14015d3b3  nop     dword ptr [rax+rax+00h]
0x14015d3b8  mov     rcx, [r15+630h]; Lock
0x14015d3bf  lea     rdx, [rbp+57h+var_80+4]; LockState
0x14015d3c3  xor     r8d, r8d; Flags
0x14015d3c6  call    cs:__imp_NdisAcquireRWLockWrite
0x14015d3cd  nop     dword ptr [rax+rax+00h]
0x14015d3d2  mov     rcx, [rbp+57h+var_70]
0x14015d3d6  mov     al, [rcx+24h]
0x14015d3d9  mov     [r15+5B4h], al
0x14015d3e0  mov     al, [rcx+25h]
0x14015d3e3  mov     [r15+5B5h], al
0x14015d3ea  mov     al, [rcx+26h]
0x14015d3ed  lea     rcx, [r15+404h]
0x14015d3f4  mov     [r15+5B6h], al
0x14015d3fb  call    vmqClearCapabilities
0x14015d400  mov     rcx, rbx
0x14015d403  call    vmqIndicateCapsChange
0x14015d408  or      byte ptr [rsi+0CCh], 2
0x14015d40f  lea     rdx, [rbp+57h+var_80+4]; LockState
0x14015d413  mov     rcx, [r15+630h]; Lock
0x14015d41a  mov     [r15+90h], rsi
0x14015d421  call    cs:__imp_NdisReleaseRWLock
0x14015d428  nop     dword ptr [rax+rax+00h]
0x14015d42d  xor     edx, edx; Wait
0x14015d42f  mov     rcx, rdi; Mutex
0x14015d432  call    cs:__imp_KeReleaseMutex
0x14015d439  nop     dword ptr [rax+rax+00h]
0x14015d43e  xor     edi, edi
0x14015d440  lea     ebx, [rdi+1]
0x14015d443  mov     rcx, cs:WPP_GLOBAL_Control
0x14015d44a  mov     al, [rcx+29h]
0x14015d44d  sub     al, bl
0x14015d44f  cmp     al, 2
0x14015d451  ja      short loc_14015D459
0x14015d453  cmp     [rcx+48h], di
0x14015d457  jz      short loc_14015D4A7
0x14015d459  movzx   r8d, byte ptr [rsi+0CCh]
0x14015d461  lea     rax, aMin; "min"
0x14015d468  mov     rcx, [rcx+40h]
0x14015d46c  lea     rdx, aSum; "sum"
0x14015d473  test    r8b, 2
0x14015d477  cmovz   rdx, rax
0x14015d47b  movzx   eax, word ptr [rsi+0CAh]
0x14015d482  mov     qword ptr [rsp+0D0h+var_88], rdx
0x14015d487  and     r8d, ebx
0x14015d48a  mov     dword ptr [rsp+0D0h+var_90], r8d
0x14015d48f  and     eax, 0FFFh
0x14015d494  mov     dword ptr [rsp+0D0h+var_98], eax
0x14015d498  mov     [rsp+0D0h+var_A0], r15
0x14015d49d  mov     [rsp+0D0h+var_A8], rsi
0x14015d4a2  call    WPP_RECORDER_SF_qqdls
0x14015d4a7  mov     rcx, r15; FunctionContext
0x14015d4aa  call    VmsTmInitTeamWithPnP
0x14015d4af  mov     dword ptr [rbp+57h+var_80], eax
0x14015d4b2  mov     ebx, eax
0x14015d4b4  test    eax, eax
0x14015d4b6  jnz     loc_14015D5BE
0x14015d4bc  mov     rcx, rsi
0x14015d4bf  cmp     edi, [r12+0Ch]
0x14015d4c4  jnb     short loc_14015D4F3
0x14015d4c6  movzx   edx, word ptr [r12+8]
0x14015d4cc  mov     eax, edi
0x14015d4ce  imul    eax, [r12+10h]
  ... truncated ...
```
