# VmsPtNicMuxManageResources

- ea: `0x14013af44`
- end: `0x14013b536`
- name: `VmsPtNicMuxManageResources`
- size: `1522`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140121a80`

## callees

- `0x140027a64`
- `0x14008497c`
- `0x140088c50`
- `0x1400893c8`
- `0x140089a04`
- `0x14008c624`
- `0x14008cc04`
- `0x14008cd0c`
- `0x14012c0e0`
- `0x14012cbfc`
- `0x14012ff28`
- `0x140131b10`
- `0x140131bec`
- `0x140131eb8`
- `0x14013af44`
- `0x140142e64`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x14013b2c5`
- `ntoskrnl!KeResetEvent` at `0x14013b2c5`
- `ntoskrnl!KeReleaseMutex` at `0x14013b133`
- `ntoskrnl!KeReleaseMutex` at `0x14013b19c`
- `ntoskrnl!KeReleaseMutex` at `0x14013b33c`
- `ntoskrnl!KeReleaseMutex` at `0x14013b3ef`
- `ntoskrnl!KeReleaseMutex` at `0x14013b4f6`
- `ntoskrnl!KeReleaseMutex` at `0x14013b133`
- `ntoskrnl!KeReleaseMutex` at `0x14013b19c`
- `ntoskrnl!KeReleaseMutex` at `0x14013b33c`
- `ntoskrnl!KeReleaseMutex` at `0x14013b3ef`
- `ntoskrnl!KeReleaseMutex` at `0x14013b4f6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b113`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b157`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b173`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b302`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b374`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b3ab`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b46c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b113`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b157`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b173`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b302`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b374`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b3ab`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b46c`
- `NDIS!NdisAcquireRWLockRead` at `0x14013b0b4`
- `NDIS!NdisAcquireRWLockRead` at `0x14013b0b4`
- `NDIS!NdisReleaseRWLock` at `0x14013b0d9`
- `NDIS!NdisReleaseRWLock` at `0x14013b2a7`
- `NDIS!NdisReleaseRWLock` at `0x14013b0d9`
- `NDIS!NdisReleaseRWLock` at `0x14013b2a7`

## string_xrefs

- `0x14013af80`: `ProtocolNic != NULL`
- `0x14013b04c`: `ProtocolNic->ParentSwitch->NicTeamingContext->Team != NULL`
- `0x14013affd`: `ProtocolNic->ParentSwitch->NicTeamingContext != NULL`
- `0x14013afb9`: `ProtocolNic->ParentSwitch != NULL`

## pseudocode

```c
int __fastcall VmsPtNicMuxManageResources(__int64 a1, int a2)
{
  __int64 v3; // r15
  __int64 v4; // rsi
  __int128 *k; // rax
  int v6; // ebx
  __int64 i; // rax
  _QWORD *v8; // rcx
  _QWORD *j; // rax
  _QWORD *v10; // r8
  _QWORD *v11; // rax
  _QWORD *v12; // rdx
  __int64 v13; // r13
  __int64 v14; // r13
  _QWORD *v15; // rcx
  _QWORD *v16; // rax
  _QWORD *v17; // rbx
  _QWORD *v18; // r14
  __int128 *v19; // rbx
  __int128 *v20; // rsi
  int v21; // edx
  __int128 *v22; // rsi
  __int128 *v23; // rbx
  __int128 *v24; // rsi
  __int128 *v25; // rbx
  bool v26; // zf
  __int128 v28; // [rsp+30h] [rbp-10h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+80h] [rbp+40h] BYREF
  _QWORD *v30; // [rsp+88h] [rbp+48h]

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v28 = 0;
  if ( !a1 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      a2,
      19,
      65,
      (__int64)WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids,
      "ProtocolNic != NULL",
      v28);
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( !*(_QWORD *)(a1 + 1888) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      a2,
      19,
      66,
      (__int64)WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids,
      "ProtocolNic->ParentSwitch != NULL");
    if ( !*(_QWORD *)(a1 + 1888) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( !*(_QWORD *)(*(_QWORD *)(a1 + 1888) + 9000LL) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      a2,
      19,
      67,
      (__int64)WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids,
      "ProtocolNic->ParentSwitch->NicTeamingContext != NULL");
    if ( !*(_QWORD *)(*(_QWORD *)(a1 + 1888) + 9000LL) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 1888) + 9000LL) + 16LL) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      a2,
      19,
      68,
      (__int64)WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids,
      "ProtocolNic->ParentSwitch->NicTeamingContext->Team != NULL");
    if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 1888) + 9000LL) + 16LL) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v3 = *(_QWORD *)(a1 + 1888);
  v4 = *(_QWORD *)(*(_QWORD *)(v3 + 9000) + 16LL);
  *((_QWORD *)&v28 + 1) = &v28;
  *(_QWORD *)&v28 = &v28;
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v4 + 1584), &LockState, 0);
  if ( *(_WORD *)(v4 + 2308) )
  {
    for ( i = *(_QWORD *)(v4 + 2288); ; i = v18[2] )
    {
      v18 = (_QWORD *)(i - 16);
      if ( i == v4 + 2288 )
        break;
      if ( v18[110] )
      {
        v8 = v18 + 89;
        for ( j = (_QWORD *)v18[89]; ; j = (_QWORD *)v17[6] )
        {
          v17 = j - 6;
          if ( j == v8 )
            break;
          if ( *((_BYTE *)v17 + 100) )
          {
            v10 = v17 + 8;
            v11 = (_QWORD *)v17[8];
            v12 = v11 - 3;
            v30 = v11 - 3;
            if ( v11 != v17 + 8 )
            {
              do
              {
                v13 = v12[10];
                if ( v13 )
                {
                  v14 = *(_QWORD *)(v13 + 1256);
                  if ( *(_DWORD *)(v14 + 1880) == 1 && *(_DWORD *)(v14 + 1872) != 5 )
                  {
                    VmsOmNicIncrementControlCount(v14, 0, 53);
                    v15 = (_QWORD *)*((_QWORD *)&v28 + 1);
                    if ( **((__int128 ***)&v28 + 1) != &v28 )
                      __fastfail(3u);
                    *(_QWORD *)(v14 + 5624) = *((_QWORD *)&v28 + 1);
                    *(_QWORD *)(v14 + 5616) = &v28;
                    v10 = v17 + 8;
                    v12 = v30;
                    *v15 = v14 + 5616;
                    *((_QWORD *)&v28 + 1) = v14 + 5616;
                  }
                }
                v16 = (_QWORD *)v12[3];
                v12 = v16 - 3;
                v30 = v16 - 3;
              }
              while ( v16 != v10 );
              v8 = v18 + 89;
            }
            *((_BYTE *)v17 + 100) = 0;
          }
        }
      }
    }
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v4 + 1584), &LockState);
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 9148));
    KeResetEvent((PRKEVENT)(v3 + 9152));
    v19 = (__int128 *)v28;
    if ( (__int128 *)v28 != &v28 )
    {
      do
      {
        v20 = *(__int128 **)v19;
        KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
        if ( *((_DWORD *)v19 - 936) == 3 && *(_QWORD *)(*((_QWORD *)v19 - 288) + 792LL) )
          VmsIovRevokeVFIfAssigned(*((_QWORD *)v19 - 454), 2);
        KeReleaseMutex(&VmsOmIoctlMutex, 0);
        v19 = v20;
      }
      while ( v20 != &v28 );
    }
    if ( (int)VmsIovDecrementPendingVfRevokeCount(v3) > 0 )
      KeWaitForSingleObject((PVOID)(v3 + 9152), Executive, 0, 0, 0);
    v22 = (__int128 *)v28;
    if ( (__int128 *)v28 != &v28 )
    {
      do
      {
        v23 = *(__int128 **)v22;
        v24 = v22 - 351;
        KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
        if ( *(_DWORD *)(v3 + 8916) == 1 )
        {
          VmsPDRevokePDAccess(v24, a1, 0);
        }
        else
        {
          VmsVmqDoVmqOperation(v24, a1, 2);
          VmsIovDeleteMacFilters(v24, 0);
        }
        KeReleaseMutex(&VmsOmIoctlMutex, 0);
        v22 = v23;
      }
      while ( v23 != &v28 );
      v22 = (__int128 *)v28;
    }
    for ( k = &v28; v22 != &v28; k = &v28 )
    {
      v25 = v22 - 351;
      if ( v22 == (__int128 *)5616 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          v21,
          (_DWORD)v25 + 19,
          (_DWORD)v25 + 69,
          (__int64)WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids,
          "objNic != NULL");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      v22 = *(__int128 **)v22;
      KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
      v26 = *((_DWORD *)v25 + 470) == 1;
      *((_BYTE *)v25 + 5632) = 1;
      if ( v26 )
      {
        if ( *(_DWORD *)(v3 + 8916) == 1 )
        {
          VmsPDSetupPDAccess(v25, a1, 0);
        }
        else
        {
          VmsIovAllocateMacFilters(v25, a1);
          VmsVmqDoVmqOperation(v25, a1, 1);
          if ( *((_DWORD *)v25 + 468) == 3
            && *((_DWORD *)v25 + 470) == 1
            && (*(_BYTE *)(*((_QWORD *)v25 + 414) + 564LL) & 4) != 0 )
          {
            VmsIovReAssignVFIfPossible(*((_QWORD *)v25 + 248), 2);
          }
          VmsNdkSendPendingRdmaRequests(a1);
        }
      }
      KeReleaseMutex(&VmsOmIoctlMutex, 0);
      VmsOmNicDecrementControlCount(v25, 0, 53);
    }
  }
  else
  {
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v4 + 1584), &LockState);
    if ( *(_DWORD *)(v3 + 8916) == 1 )
    {
      LODWORD(k) = VmsPDSwitchDataPathModeUnsafe(v3, 0);
    }
    else
    {
      KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
      v6 = VmsIovRevokeVfsOnSwitch(v3, 9);
      KeReleaseMutex(&VmsOmIoctlMutex, 0);
      if ( v6 > 0 )
        KeWaitForSingleObject((PVOID)(v3 + 9152), Executive, 0, 0, 0);
      KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
      VmsVmqDoVmqOperation(a1, 0, 2);
      VmsIovDeleteMacFilters(a1, 0);
      LODWORD(k) = KeReleaseMutex(&VmsOmIoctlMutex, 0);
    }
  }
  return (int)k;
}

```

## disassembly

```asm
0x14013af44  mov     [rsp-38h+arg_10], rbx
0x14013af49  push    rbp
0x14013af4a  push    rsi
0x14013af4b  push    rdi
0x14013af4c  push    r12
0x14013af4e  push    r13
0x14013af50  push    r14
0x14013af52  push    r15
0x14013af54  mov     rbp, rsp
0x14013af57  sub     rsp, 40h
0x14013af5b  xor     eax, eax
0x14013af5d  lea     rsi, WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids
0x14013af64  xor     r13d, r13d
0x14013af67  mov     word ptr [rbp+LockState.OldIrql], ax
0x14013af6b  mov     [rbp+LockState.Flags], al
0x14013af6e  xorps   xmm0, xmm0
0x14013af71  mov     rdi, rcx
0x14013af74  lea     ebx, [rax+13h]
0x14013af77  movups  [rbp+var_10], xmm0
0x14013af7b  test    rcx, rcx
0x14013af7e  jnz     short loc_14013AFA9
0x14013af80  lea     rax, aProtocolnicNul_0; "ProtocolNic != NULL"
0x14013af87  mov     r8d, ebx
0x14013af8a  lea     r9d, [rcx+41h]
0x14013af8e  mov     [rsp+40h+var_18], rax
0x14013af93  mov     rcx, cs:VmsIfrLog
0x14013af9a  mov     [rsp+40h+Timeout], rsi
0x14013af9f  call    WPP_RECORDER_SF_s
0x14013afa4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ProtocolNic != ((void *)0)")
0x14013afa9  cmp     [rdi+760h], r13
0x14013afb0  jnz     short loc_14013AFE6
0x14013afb2  mov     rcx, cs:VmsIfrLog
0x14013afb9  lea     rax, aProtocolnicPar; "ProtocolNic->ParentSwitch != NULL"
0x14013afc0  mov     [rsp+40h+var_18], rax
0x14013afc5  mov     r9d, 42h ; 'B'
0x14013afcb  mov     r8d, ebx
0x14013afce  mov     [rsp+40h+Timeout], rsi
0x14013afd3  call    WPP_RECORDER_SF_s
0x14013afd8  cmp     [rdi+760h], r13
0x14013afdf  jnz     short loc_14013AFE6
0x14013afe1  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ProtocolNic->ParentSwitch != ((void *)0)")
0x14013afe6  mov     rax, [rdi+760h]
0x14013afed  cmp     [rax+2328h], r13
0x14013aff4  jnz     short loc_14013B031
0x14013aff6  mov     rcx, cs:VmsIfrLog
0x14013affd  lea     rax, aProtocolnicPar_1; "ProtocolNic->ParentSwitch->NicTeamingCo"...
0x14013b004  mov     [rsp+40h+var_18], rax
0x14013b009  mov     r9d, 43h ; 'C'
0x14013b00f  mov     r8d, ebx
0x14013b012  mov     [rsp+40h+Timeout], rsi
0x14013b017  call    WPP_RECORDER_SF_s
0x14013b01c  mov     rax, [rdi+760h]
0x14013b023  cmp     [rax+2328h], r13
0x14013b02a  jnz     short loc_14013B031
0x14013b02c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ProtocolNic->ParentSwitch->NicTeamingContext != ((void *)0)")
0x14013b031  mov     rax, [rdi+760h]
0x14013b038  mov     rcx, [rax+2328h]
0x14013b03f  cmp     [rcx+10h], r13
0x14013b043  jnz     short loc_14013B084
0x14013b045  mov     rcx, cs:VmsIfrLog
0x14013b04c  lea     rax, aProtocolnicPar_0; "ProtocolNic->ParentSwitch->NicTeamingCo"...
0x14013b053  mov     [rsp+40h+var_18], rax
0x14013b058  mov     r9d, 44h ; 'D'
0x14013b05e  mov     r8d, ebx
0x14013b061  mov     [rsp+40h+Timeout], rsi
0x14013b066  call    WPP_RECORDER_SF_s
0x14013b06b  mov     rax, [rdi+760h]
0x14013b072  mov     rcx, [rax+2328h]
0x14013b079  cmp     [rcx+10h], r13
0x14013b07d  jnz     short loc_14013B084
0x14013b07f  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ProtocolNic->ParentSwitch->NicTeamingContext->Team != ((void *)0)")
0x14013b084  mov     r15, [rdi+760h]
0x14013b08b  lea     rdx, [rbp+LockState]; LockState
0x14013b08f  xor     r8d, r8d; Flags
0x14013b092  mov     rax, [r15+2328h]
0x14013b099  mov     rsi, [rax+10h]
0x14013b09d  lea     rax, [rbp+var_10]
0x14013b0a1  mov     qword ptr [rbp+var_10+8], rax
0x14013b0a5  lea     rax, [rbp+var_10]
0x14013b0a9  mov     qword ptr [rbp+var_10], rax
0x14013b0ad  mov     rcx, [rsi+630h]; Lock
0x14013b0b4  call    cs:__imp_NdisAcquireRWLockRead
0x14013b0bb  nop     dword ptr [rax+rax+00h]
0x14013b0c0  cmp     [rsi+904h], r13w
0x14013b0c8  jnz     loc_14013B1AD
0x14013b0ce  mov     rcx, [rsi+630h]; Lock
0x14013b0d5  lea     rdx, [rbp+LockState]; LockState
0x14013b0d9  call    cs:__imp_NdisReleaseRWLock
0x14013b0e0  nop     dword ptr [rax+rax+00h]
0x14013b0e5  xor     edx, edx; WaitReason
0x14013b0e7  cmp     dword ptr [r15+22D4h], 1
0x14013b0ef  jnz     short loc_14013B0FE
0x14013b0f1  mov     rcx, r15
0x14013b0f4  call    VmsPDSwitchDataPathModeUnsafe
0x14013b0f9  jmp     loc_14013B51D
0x14013b0fe  lea     r14, VmsOmIoctlMutex
0x14013b105  mov     [rsp+40h+Timeout], r13; Timeout
0x14013b10a  mov     rcx, r14; Object
0x14013b10d  xor     r9d, r9d; Alertable
0x14013b110  xor     r8d, r8d; WaitMode
0x14013b113  call    cs:__imp_KeWaitForSingleObject
0x14013b11a  nop     dword ptr [rax+rax+00h]
0x14013b11f  mov     edx, 9
0x14013b124  mov     rcx, r15
0x14013b127  call    VmsIovRevokeVfsOnSwitch
0x14013b12c  xor     edx, edx; Wait
0x14013b12e  mov     rcx, r14; Mutex
0x14013b131  mov     ebx, eax
0x14013b133  call    cs:__imp_KeReleaseMutex
0x14013b13a  nop     dword ptr [rax+rax+00h]
0x14013b13f  test    ebx, ebx
0x14013b141  jle     short loc_14013B163
0x14013b143  lea     rcx, [r15+23C0h]; Object
0x14013b14a  mov     [rsp+40h+Timeout], r13; Timeout
0x14013b14f  xor     r9d, r9d; Alertable
0x14013b152  xor     r8d, r8d; WaitMode
0x14013b155  xor     edx, edx; WaitReason
0x14013b157  call    cs:__imp_KeWaitForSingleObject
0x14013b15e  nop     dword ptr [rax+rax+00h]
0x14013b163  xor     r9d, r9d; Alertable
0x14013b166  mov     [rsp+40h+Timeout], r13; Timeout
0x14013b16b  xor     r8d, r8d; WaitMode
0x14013b16e  xor     edx, edx; WaitReason
0x14013b170  mov     rcx, r14; Object
0x14013b173  call    cs:__imp_KeWaitForSingleObject
0x14013b17a  nop     dword ptr [rax+rax+00h]
0x14013b17f  xor     edx, edx
0x14013b181  mov     rcx, rdi
0x14013b184  lea     r8d, [rdx+2]
0x14013b188  call    VmsVmqDoVmqOperation
0x14013b18d  xor     edx, edx
0x14013b18f  mov     rcx, rdi
0x14013b192  call    VmsIovDeleteMacFilters
0x14013b197  xor     edx, edx; Wait
0x14013b199  mov     rcx, r14; Mutex
0x14013b19c  call    cs:__imp_KeReleaseMutex
0x14013b1a3  nop     dword ptr [rax+rax+00h]
0x14013b1a8  jmp     loc_14013B51D
0x14013b1ad  lea     r12, [rsi+8F0h]
0x14013b1b4  mov     rax, [r12]
0x14013b1b8  jmp     loc_14013B28F
0x14013b1bd  cmp     [r14+370h], r13
0x14013b1c4  jz      loc_14013B28B
0x14013b1ca  lea     rcx, [r14+2C8h]
0x14013b1d1  mov     rax, [rcx]
0x14013b1d4  jmp     loc_14013B27E
0x14013b1d9  cmp     [rbx+64h], r13b
0x14013b1dd  jz      loc_14013B27A
0x14013b1e3  lea     r8, [rbx+40h]
0x14013b1e7  mov     rax, [r8]
0x14013b1ea  lea     rdx, [rax-18h]
0x14013b1ee  mov     [rbp+arg_8], rdx
0x14013b1f2  cmp     rax, r8
0x14013b1f5  jz      short loc_14013B276
0x14013b1f7  mov     r13, [rdx+50h]
0x14013b1fb  test    r13, r13
0x14013b1fe  jz      short loc_14013B25B
0x14013b200  mov     r13, [r13+4E8h]
0x14013b207  cmp     dword ptr [r13+758h], 1
0x14013b20f  jnz     short loc_14013B25B
0x14013b211  cmp     dword ptr [r13+750h], 5
0x14013b219  jz      short loc_14013B25B
0x14013b21b  xor     edx, edx
0x14013b21d  mov     rcx, r13
0x14013b220  lea     r8d, [rdx+35h]
0x14013b224  call    VmsOmNicIncrementControlCount
0x14013b229  mov     rcx, qword ptr [rbp+var_10+8]
0x14013b22d  lea     rax, [rbp+var_10]
0x14013b231  cmp     [rcx], rax
0x14013b234  jnz     loc_14013B3D1
0x14013b23a  lea     rax, [r13+15F0h]
0x14013b241  lea     rdx, [rbp+var_10]
0x14013b245  mov     [rax+8], rcx
0x14013b249  mov     [rax], rdx
0x14013b24c  lea     r8, [rbx+40h]
0x14013b250  mov     rdx, [rbp+arg_8]
0x14013b254  mov     [rcx], rax
0x14013b257  mov     qword ptr [rbp+var_10+8], rax
0x14013b25b  mov     rax, [rdx+18h]
0x14013b25f  lea     rdx, [rax-18h]
0x14013b263  mov     [rbp+arg_8], rdx
0x14013b267  cmp     rax, r8
0x14013b26a  jnz     short loc_14013B1F7
0x14013b26c  lea     rcx, [r14+2C8h]
0x14013b273  xor     r13d, r13d
0x14013b276  mov     [rbx+64h], r13b
0x14013b27a  mov     rax, [rbx+30h]
0x14013b27e  lea     rbx, [rax-30h]
0x14013b282  cmp     rax, rcx
0x14013b285  jnz     loc_14013B1D9
0x14013b28b  mov     rax, [r14+10h]
0x14013b28f  lea     r14, [rax-10h]
0x14013b293  cmp     rax, r12
0x14013b296  jnz     loc_14013B1BD
0x14013b29c  mov     rcx, [rsi+630h]; Lock
0x14013b2a3  lea     rdx, [rbp+LockState]; LockState
0x14013b2a7  call    cs:__imp_NdisReleaseRWLock
0x14013b2ae  nop     dword ptr [rax+rax+00h]
0x14013b2b3  lock inc dword ptr [r15+23BCh]
0x14013b2bb  lea     r12, [r15+23C0h]
0x14013b2c2  mov     rcx, r12; Event
0x14013b2c5  call    cs:__imp_KeResetEvent
0x14013b2cc  nop     dword ptr [rax+rax+00h]
0x14013b2d1  mov     rbx, qword ptr [rbp+var_10]
0x14013b2d5  lea     rax, [rbp+var_10]
0x14013b2d9  lea     r14, VmsOmIoctlMutex
0x14013b2e0  mov     r13d, 2
0x14013b2e6  cmp     rbx, rax
0x14013b2e9  jz      short loc_14013B354
0x14013b2eb  mov     rsi, [rbx]
0x14013b2ee  xor     r9d, r9d; Alertable
0x14013b2f1  xor     r8d, r8d; WaitMode
0x14013b2f4  mov     [rsp+40h+Timeout], 0; Timeout
0x14013b2fd  xor     edx, edx; WaitReason
0x14013b2ff  mov     rcx, r14; Object
0x14013b302  call    cs:__imp_KeWaitForSingleObject
0x14013b309  nop     dword ptr [rax+rax+00h]
0x14013b30e  cmp     dword ptr [rbx-0EA0h], 3
0x14013b315  jnz     short loc_14013B337
0x14013b317  mov     rax, [rbx-900h]
0x14013b31e  cmp     qword ptr [rax+318h], 0
0x14013b326  jz      short loc_14013B337
0x14013b328  mov     rcx, [rbx-0E30h]
0x14013b32f  mov     edx, r13d
0x14013b332  call    VmsIovRevokeVFIfAssigned
0x14013b337  xor     edx, edx; Wait
0x14013b339  mov     rcx, r14; Mutex
0x14013b33c  call    cs:__imp_KeReleaseMutex
0x14013b343  nop     dword ptr [rax+rax+00h]
0x14013b348  lea     rax, [rbp+var_10]
0x14013b34c  mov     rbx, rsi
0x14013b34f  cmp     rsi, rax
0x14013b352  jnz     short loc_14013B2EB
0x14013b354  mov     rcx, r15
0x14013b357  call    VmsIovDecrementPendingVfRevokeCount
0x14013b35c  test    eax, eax
0x14013b35e  jle     short loc_14013B380
0x14013b360  xor     r9d, r9d; Alertable
0x14013b363  mov     [rsp+40h+Timeout], 0; Timeout
0x14013b36c  xor     r8d, r8d; WaitMode
0x14013b36f  xor     edx, edx; WaitReason
0x14013b371  mov     rcx, r12; Object
0x14013b374  call    cs:__imp_KeWaitForSingleObject
0x14013b37b  nop     dword ptr [rax+rax+00h]
0x14013b380  mov     rsi, qword ptr [rbp+var_10]
0x14013b384  lea     rax, [rbp+var_10]
0x14013b388  cmp     rsi, rax
0x14013b38b  jz      short loc_14013B40B
0x14013b38d  mov     rbx, [rsi]
0x14013b390  xor     r9d, r9d; Alertable
0x14013b393  xor     r8d, r8d; WaitMode
0x14013b396  mov     [rsp+40h+Timeout], 0; Timeout
0x14013b39f  xor     edx, edx; WaitReason
0x14013b3a1  mov     rcx, r14; Object
0x14013b3a4  add     rsi, 0FFFFFFFFFFFFEA10h
0x14013b3ab  call    cs:__imp_KeWaitForSingleObject
0x14013b3b2  nop     dword ptr [rax+rax+00h]
0x14013b3b7  cmp     dword ptr [r15+22D4h], 1
0x14013b3bf  mov     rdx, rdi
0x14013b3c2  mov     rcx, rsi
0x14013b3c5  jnz     short loc_14013B3D8
0x14013b3c7  xor     r8d, r8d
0x14013b3ca  call    VmsPDRevokePDAccess
0x14013b3cf  jmp     short loc_14013B3EA
0x14013b3d1  mov     ecx, 3
0x14013b3d6  int     29h; Win8: RtlFailFast(ecx)
0x14013b3d8  mov     r8d, r13d
0x14013b3db  call    VmsVmqDoVmqOperation
0x14013b3e0  xor     edx, edx
0x14013b3e2  mov     rcx, rsi
0x14013b3e5  call    VmsIovDeleteMacFilters
0x14013b3ea  xor     edx, edx; Wait
0x14013b3ec  mov     rcx, r14; Mutex
0x14013b3ef  call    cs:__imp_KeReleaseMutex
0x14013b3f6  nop     dword ptr [rax+rax+00h]
0x14013b3fb  lea     rax, [rbp+var_10]
0x14013b3ff  mov     rsi, rbx
0x14013b402  cmp     rbx, rax
0x14013b405  jnz     short loc_14013B38D
0x14013b407  mov     rsi, qword ptr [rbp+var_10]
0x14013b40b  lea     rax, [rbp+var_10]
0x14013b40f  cmp     rsi, rax
0x14013b412  jz      loc_14013B51D
0x14013b418  lea     r12, WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids
0x14013b41f  lea     rbx, [rsi-15F0h]
0x14013b426  test    rbx, rbx
0x14013b429  jnz     short loc_14013B455
0x14013b42b  mov     rcx, cs:VmsIfrLog
0x14013b432  lea     rax, aObjnicNull_1; "objNic != NULL"
0x14013b439  mov     [rsp+40h+var_18], rax
0x14013b43e  lea     r9d, [rbx+45h]
0x14013b442  lea     r8d, [rbx+13h]
0x14013b446  mov     [rsp+40h+Timeout], r12
0x14013b44b  call    WPP_RECORDER_SF_s
0x14013b450  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "objNic != ((void *)0)")
0x14013b455  mov     rsi, [rsi]
0x14013b458  xor     r9d, r9d; Alertable
0x14013b45b  xor     r8d, r8d; WaitMode
0x14013b45e  mov     [rsp+40h+Timeout], 0; Timeout
0x14013b467  xor     edx, edx; WaitReason
  ... truncated ...
```
