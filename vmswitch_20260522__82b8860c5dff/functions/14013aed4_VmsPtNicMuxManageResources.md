# VmsPtNicMuxManageResources

- ea: `0x14013aed4`
- end: `0x14013b4c6`
- name: `VmsPtNicMuxManageResources`
- size: `1522`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140121a10`

## callees

- `0x140027a64`
- `0x14008497c`
- `0x140088c50`
- `0x1400893c8`
- `0x140089a04`
- `0x14008c624`
- `0x14008cc04`
- `0x14008cd0c`
- `0x14012c070`
- `0x14012cb8c`
- `0x14012feb8`
- `0x140131aa0`
- `0x140131b7c`
- `0x140131e48`
- `0x14013aed4`
- `0x140142df4`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x14013b255`
- `ntoskrnl!KeResetEvent` at `0x14013b255`
- `ntoskrnl!KeReleaseMutex` at `0x14013b0c3`
- `ntoskrnl!KeReleaseMutex` at `0x14013b12c`
- `ntoskrnl!KeReleaseMutex` at `0x14013b2cc`
- `ntoskrnl!KeReleaseMutex` at `0x14013b37f`
- `ntoskrnl!KeReleaseMutex` at `0x14013b486`
- `ntoskrnl!KeReleaseMutex` at `0x14013b0c3`
- `ntoskrnl!KeReleaseMutex` at `0x14013b12c`
- `ntoskrnl!KeReleaseMutex` at `0x14013b2cc`
- `ntoskrnl!KeReleaseMutex` at `0x14013b37f`
- `ntoskrnl!KeReleaseMutex` at `0x14013b486`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b0a3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b0e7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b103`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b292`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b304`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b33b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b3fc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b0a3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b0e7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b103`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b292`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b304`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b33b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14013b3fc`
- `NDIS!NdisAcquireRWLockRead` at `0x14013b044`
- `NDIS!NdisAcquireRWLockRead` at `0x14013b044`
- `NDIS!NdisReleaseRWLock` at `0x14013b069`
- `NDIS!NdisReleaseRWLock` at `0x14013b237`
- `NDIS!NdisReleaseRWLock` at `0x14013b069`
- `NDIS!NdisReleaseRWLock` at `0x14013b237`

## string_xrefs

- `0x14013af10`: `ProtocolNic != NULL`
- `0x14013af49`: `ProtocolNic->ParentSwitch != NULL`
- `0x14013afdc`: `ProtocolNic->ParentSwitch->NicTeamingContext->Team != NULL`
- `0x14013af8d`: `ProtocolNic->ParentSwitch->NicTeamingContext != NULL`

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
0x14013aed4  mov     [rsp-38h+arg_10], rbx
0x14013aed9  push    rbp
0x14013aeda  push    rsi
0x14013aedb  push    rdi
0x14013aedc  push    r12
0x14013aede  push    r13
0x14013aee0  push    r14
0x14013aee2  push    r15
0x14013aee4  mov     rbp, rsp
0x14013aee7  sub     rsp, 40h
0x14013aeeb  xor     eax, eax
0x14013aeed  lea     rsi, WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids
0x14013aef4  xor     r13d, r13d
0x14013aef7  mov     word ptr [rbp+LockState.OldIrql], ax
0x14013aefb  mov     [rbp+LockState.Flags], al
0x14013aefe  xorps   xmm0, xmm0
0x14013af01  mov     rdi, rcx
0x14013af04  lea     ebx, [rax+13h]
0x14013af07  movups  [rbp+var_10], xmm0
0x14013af0b  test    rcx, rcx
0x14013af0e  jnz     short loc_14013AF39
0x14013af10  lea     rax, aProtocolnicNul_0; "ProtocolNic != NULL"
0x14013af17  mov     r8d, ebx
0x14013af1a  lea     r9d, [rcx+41h]
0x14013af1e  mov     [rsp+40h+var_18], rax
0x14013af23  mov     rcx, cs:VmsIfrLog
0x14013af2a  mov     [rsp+40h+Timeout], rsi
0x14013af2f  call    WPP_RECORDER_SF_s
0x14013af34  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ProtocolNic != ((void *)0)")
0x14013af39  cmp     [rdi+760h], r13
0x14013af40  jnz     short loc_14013AF76
0x14013af42  mov     rcx, cs:VmsIfrLog
0x14013af49  lea     rax, aProtocolnicPar; "ProtocolNic->ParentSwitch != NULL"
0x14013af50  mov     [rsp+40h+var_18], rax
0x14013af55  mov     r9d, 42h ; 'B'
0x14013af5b  mov     r8d, ebx
0x14013af5e  mov     [rsp+40h+Timeout], rsi
0x14013af63  call    WPP_RECORDER_SF_s
0x14013af68  cmp     [rdi+760h], r13
0x14013af6f  jnz     short loc_14013AF76
0x14013af71  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ProtocolNic->ParentSwitch != ((void *)0)")
0x14013af76  mov     rax, [rdi+760h]
0x14013af7d  cmp     [rax+2328h], r13
0x14013af84  jnz     short loc_14013AFC1
0x14013af86  mov     rcx, cs:VmsIfrLog
0x14013af8d  lea     rax, aProtocolnicPar_1; "ProtocolNic->ParentSwitch->NicTeamingCo"...
0x14013af94  mov     [rsp+40h+var_18], rax
0x14013af99  mov     r9d, 43h ; 'C'
0x14013af9f  mov     r8d, ebx
0x14013afa2  mov     [rsp+40h+Timeout], rsi
0x14013afa7  call    WPP_RECORDER_SF_s
0x14013afac  mov     rax, [rdi+760h]
0x14013afb3  cmp     [rax+2328h], r13
0x14013afba  jnz     short loc_14013AFC1
0x14013afbc  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ProtocolNic->ParentSwitch->NicTeamingContext != ((void *)0)")
0x14013afc1  mov     rax, [rdi+760h]
0x14013afc8  mov     rcx, [rax+2328h]
0x14013afcf  cmp     [rcx+10h], r13
0x14013afd3  jnz     short loc_14013B014
0x14013afd5  mov     rcx, cs:VmsIfrLog
0x14013afdc  lea     rax, aProtocolnicPar_0; "ProtocolNic->ParentSwitch->NicTeamingCo"...
0x14013afe3  mov     [rsp+40h+var_18], rax
0x14013afe8  mov     r9d, 44h ; 'D'
0x14013afee  mov     r8d, ebx
0x14013aff1  mov     [rsp+40h+Timeout], rsi
0x14013aff6  call    WPP_RECORDER_SF_s
0x14013affb  mov     rax, [rdi+760h]
0x14013b002  mov     rcx, [rax+2328h]
0x14013b009  cmp     [rcx+10h], r13
0x14013b00d  jnz     short loc_14013B014
0x14013b00f  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ProtocolNic->ParentSwitch->NicTeamingContext->Team != ((void *)0)")
0x14013b014  mov     r15, [rdi+760h]
0x14013b01b  lea     rdx, [rbp+LockState]; LockState
0x14013b01f  xor     r8d, r8d; Flags
0x14013b022  mov     rax, [r15+2328h]
0x14013b029  mov     rsi, [rax+10h]
0x14013b02d  lea     rax, [rbp+var_10]
0x14013b031  mov     qword ptr [rbp+var_10+8], rax
0x14013b035  lea     rax, [rbp+var_10]
0x14013b039  mov     qword ptr [rbp+var_10], rax
0x14013b03d  mov     rcx, [rsi+630h]; Lock
0x14013b044  call    cs:__imp_NdisAcquireRWLockRead
0x14013b04b  nop     dword ptr [rax+rax+00h]
0x14013b050  cmp     [rsi+904h], r13w
0x14013b058  jnz     loc_14013B13D
0x14013b05e  mov     rcx, [rsi+630h]; Lock
0x14013b065  lea     rdx, [rbp+LockState]; LockState
0x14013b069  call    cs:__imp_NdisReleaseRWLock
0x14013b070  nop     dword ptr [rax+rax+00h]
0x14013b075  xor     edx, edx; WaitReason
0x14013b077  cmp     dword ptr [r15+22D4h], 1
0x14013b07f  jnz     short loc_14013B08E
0x14013b081  mov     rcx, r15
0x14013b084  call    VmsPDSwitchDataPathModeUnsafe
0x14013b089  jmp     loc_14013B4AD
0x14013b08e  lea     r14, VmsOmIoctlMutex
0x14013b095  mov     [rsp+40h+Timeout], r13; Timeout
0x14013b09a  mov     rcx, r14; Object
0x14013b09d  xor     r9d, r9d; Alertable
0x14013b0a0  xor     r8d, r8d; WaitMode
0x14013b0a3  call    cs:__imp_KeWaitForSingleObject
0x14013b0aa  nop     dword ptr [rax+rax+00h]
0x14013b0af  mov     edx, 9
0x14013b0b4  mov     rcx, r15
0x14013b0b7  call    VmsIovRevokeVfsOnSwitch
0x14013b0bc  xor     edx, edx; Wait
0x14013b0be  mov     rcx, r14; Mutex
0x14013b0c1  mov     ebx, eax
0x14013b0c3  call    cs:__imp_KeReleaseMutex
0x14013b0ca  nop     dword ptr [rax+rax+00h]
0x14013b0cf  test    ebx, ebx
0x14013b0d1  jle     short loc_14013B0F3
0x14013b0d3  lea     rcx, [r15+23C0h]; Object
0x14013b0da  mov     [rsp+40h+Timeout], r13; Timeout
0x14013b0df  xor     r9d, r9d; Alertable
0x14013b0e2  xor     r8d, r8d; WaitMode
0x14013b0e5  xor     edx, edx; WaitReason
0x14013b0e7  call    cs:__imp_KeWaitForSingleObject
0x14013b0ee  nop     dword ptr [rax+rax+00h]
0x14013b0f3  xor     r9d, r9d; Alertable
0x14013b0f6  mov     [rsp+40h+Timeout], r13; Timeout
0x14013b0fb  xor     r8d, r8d; WaitMode
0x14013b0fe  xor     edx, edx; WaitReason
0x14013b100  mov     rcx, r14; Object
0x14013b103  call    cs:__imp_KeWaitForSingleObject
0x14013b10a  nop     dword ptr [rax+rax+00h]
0x14013b10f  xor     edx, edx
0x14013b111  mov     rcx, rdi
0x14013b114  lea     r8d, [rdx+2]
0x14013b118  call    VmsVmqDoVmqOperation
0x14013b11d  xor     edx, edx
0x14013b11f  mov     rcx, rdi
0x14013b122  call    VmsIovDeleteMacFilters
0x14013b127  xor     edx, edx; Wait
0x14013b129  mov     rcx, r14; Mutex
0x14013b12c  call    cs:__imp_KeReleaseMutex
0x14013b133  nop     dword ptr [rax+rax+00h]
0x14013b138  jmp     loc_14013B4AD
0x14013b13d  lea     r12, [rsi+8F0h]
0x14013b144  mov     rax, [r12]
0x14013b148  jmp     loc_14013B21F
0x14013b14d  cmp     [r14+370h], r13
0x14013b154  jz      loc_14013B21B
0x14013b15a  lea     rcx, [r14+2C8h]
0x14013b161  mov     rax, [rcx]
0x14013b164  jmp     loc_14013B20E
0x14013b169  cmp     [rbx+64h], r13b
0x14013b16d  jz      loc_14013B20A
0x14013b173  lea     r8, [rbx+40h]
0x14013b177  mov     rax, [r8]
0x14013b17a  lea     rdx, [rax-18h]
0x14013b17e  mov     [rbp+arg_8], rdx
0x14013b182  cmp     rax, r8
0x14013b185  jz      short loc_14013B206
0x14013b187  mov     r13, [rdx+50h]
0x14013b18b  test    r13, r13
0x14013b18e  jz      short loc_14013B1EB
0x14013b190  mov     r13, [r13+4E8h]
0x14013b197  cmp     dword ptr [r13+758h], 1
0x14013b19f  jnz     short loc_14013B1EB
0x14013b1a1  cmp     dword ptr [r13+750h], 5
0x14013b1a9  jz      short loc_14013B1EB
0x14013b1ab  xor     edx, edx
0x14013b1ad  mov     rcx, r13
0x14013b1b0  lea     r8d, [rdx+35h]
0x14013b1b4  call    VmsOmNicIncrementControlCount
0x14013b1b9  mov     rcx, qword ptr [rbp+var_10+8]
0x14013b1bd  lea     rax, [rbp+var_10]
0x14013b1c1  cmp     [rcx], rax
0x14013b1c4  jnz     loc_14013B361
0x14013b1ca  lea     rax, [r13+15F0h]
0x14013b1d1  lea     rdx, [rbp+var_10]
0x14013b1d5  mov     [rax+8], rcx
0x14013b1d9  mov     [rax], rdx
0x14013b1dc  lea     r8, [rbx+40h]
0x14013b1e0  mov     rdx, [rbp+arg_8]
0x14013b1e4  mov     [rcx], rax
0x14013b1e7  mov     qword ptr [rbp+var_10+8], rax
0x14013b1eb  mov     rax, [rdx+18h]
0x14013b1ef  lea     rdx, [rax-18h]
0x14013b1f3  mov     [rbp+arg_8], rdx
0x14013b1f7  cmp     rax, r8
0x14013b1fa  jnz     short loc_14013B187
0x14013b1fc  lea     rcx, [r14+2C8h]
0x14013b203  xor     r13d, r13d
0x14013b206  mov     [rbx+64h], r13b
0x14013b20a  mov     rax, [rbx+30h]
0x14013b20e  lea     rbx, [rax-30h]
0x14013b212  cmp     rax, rcx
0x14013b215  jnz     loc_14013B169
0x14013b21b  mov     rax, [r14+10h]
0x14013b21f  lea     r14, [rax-10h]
0x14013b223  cmp     rax, r12
0x14013b226  jnz     loc_14013B14D
0x14013b22c  mov     rcx, [rsi+630h]; Lock
0x14013b233  lea     rdx, [rbp+LockState]; LockState
0x14013b237  call    cs:__imp_NdisReleaseRWLock
0x14013b23e  nop     dword ptr [rax+rax+00h]
0x14013b243  lock inc dword ptr [r15+23BCh]
0x14013b24b  lea     r12, [r15+23C0h]
0x14013b252  mov     rcx, r12; Event
0x14013b255  call    cs:__imp_KeResetEvent
0x14013b25c  nop     dword ptr [rax+rax+00h]
0x14013b261  mov     rbx, qword ptr [rbp+var_10]
0x14013b265  lea     rax, [rbp+var_10]
0x14013b269  lea     r14, VmsOmIoctlMutex
0x14013b270  mov     r13d, 2
0x14013b276  cmp     rbx, rax
0x14013b279  jz      short loc_14013B2E4
0x14013b27b  mov     rsi, [rbx]
0x14013b27e  xor     r9d, r9d; Alertable
0x14013b281  xor     r8d, r8d; WaitMode
0x14013b284  mov     [rsp+40h+Timeout], 0; Timeout
0x14013b28d  xor     edx, edx; WaitReason
0x14013b28f  mov     rcx, r14; Object
0x14013b292  call    cs:__imp_KeWaitForSingleObject
0x14013b299  nop     dword ptr [rax+rax+00h]
0x14013b29e  cmp     dword ptr [rbx-0EA0h], 3
0x14013b2a5  jnz     short loc_14013B2C7
0x14013b2a7  mov     rax, [rbx-900h]
0x14013b2ae  cmp     qword ptr [rax+318h], 0
0x14013b2b6  jz      short loc_14013B2C7
0x14013b2b8  mov     rcx, [rbx-0E30h]
0x14013b2bf  mov     edx, r13d
0x14013b2c2  call    VmsIovRevokeVFIfAssigned
0x14013b2c7  xor     edx, edx; Wait
0x14013b2c9  mov     rcx, r14; Mutex
0x14013b2cc  call    cs:__imp_KeReleaseMutex
0x14013b2d3  nop     dword ptr [rax+rax+00h]
0x14013b2d8  lea     rax, [rbp+var_10]
0x14013b2dc  mov     rbx, rsi
0x14013b2df  cmp     rsi, rax
0x14013b2e2  jnz     short loc_14013B27B
0x14013b2e4  mov     rcx, r15
0x14013b2e7  call    VmsIovDecrementPendingVfRevokeCount
0x14013b2ec  test    eax, eax
0x14013b2ee  jle     short loc_14013B310
0x14013b2f0  xor     r9d, r9d; Alertable
0x14013b2f3  mov     [rsp+40h+Timeout], 0; Timeout
0x14013b2fc  xor     r8d, r8d; WaitMode
0x14013b2ff  xor     edx, edx; WaitReason
0x14013b301  mov     rcx, r12; Object
0x14013b304  call    cs:__imp_KeWaitForSingleObject
0x14013b30b  nop     dword ptr [rax+rax+00h]
0x14013b310  mov     rsi, qword ptr [rbp+var_10]
0x14013b314  lea     rax, [rbp+var_10]
0x14013b318  cmp     rsi, rax
0x14013b31b  jz      short loc_14013B39B
0x14013b31d  mov     rbx, [rsi]
0x14013b320  xor     r9d, r9d; Alertable
0x14013b323  xor     r8d, r8d; WaitMode
0x14013b326  mov     [rsp+40h+Timeout], 0; Timeout
0x14013b32f  xor     edx, edx; WaitReason
0x14013b331  mov     rcx, r14; Object
0x14013b334  add     rsi, 0FFFFFFFFFFFFEA10h
0x14013b33b  call    cs:__imp_KeWaitForSingleObject
0x14013b342  nop     dword ptr [rax+rax+00h]
0x14013b347  cmp     dword ptr [r15+22D4h], 1
0x14013b34f  mov     rdx, rdi
0x14013b352  mov     rcx, rsi
0x14013b355  jnz     short loc_14013B368
0x14013b357  xor     r8d, r8d
0x14013b35a  call    VmsPDRevokePDAccess
0x14013b35f  jmp     short loc_14013B37A
0x14013b361  mov     ecx, 3
0x14013b366  int     29h; Win8: RtlFailFast(ecx)
0x14013b368  mov     r8d, r13d
0x14013b36b  call    VmsVmqDoVmqOperation
0x14013b370  xor     edx, edx
0x14013b372  mov     rcx, rsi
0x14013b375  call    VmsIovDeleteMacFilters
0x14013b37a  xor     edx, edx; Wait
0x14013b37c  mov     rcx, r14; Mutex
0x14013b37f  call    cs:__imp_KeReleaseMutex
0x14013b386  nop     dword ptr [rax+rax+00h]
0x14013b38b  lea     rax, [rbp+var_10]
0x14013b38f  mov     rsi, rbx
0x14013b392  cmp     rbx, rax
0x14013b395  jnz     short loc_14013B31D
0x14013b397  mov     rsi, qword ptr [rbp+var_10]
0x14013b39b  lea     rax, [rbp+var_10]
0x14013b39f  cmp     rsi, rax
0x14013b3a2  jz      loc_14013B4AD
0x14013b3a8  lea     r12, WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids
0x14013b3af  lea     rbx, [rsi-15F0h]
0x14013b3b6  test    rbx, rbx
0x14013b3b9  jnz     short loc_14013B3E5
0x14013b3bb  mov     rcx, cs:VmsIfrLog
0x14013b3c2  lea     rax, aObjnicNull_1; "objNic != NULL"
0x14013b3c9  mov     [rsp+40h+var_18], rax
0x14013b3ce  lea     r9d, [rbx+45h]
0x14013b3d2  lea     r8d, [rbx+13h]
0x14013b3d6  mov     [rsp+40h+Timeout], r12
0x14013b3db  call    WPP_RECORDER_SF_s
0x14013b3e0  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "objNic != ((void *)0)")
0x14013b3e5  mov     rsi, [rsi]
0x14013b3e8  xor     r9d, r9d; Alertable
0x14013b3eb  xor     r8d, r8d; WaitMode
0x14013b3ee  mov     [rsp+40h+Timeout], 0; Timeout
0x14013b3f7  xor     edx, edx; WaitReason
  ... truncated ...
```
