# VmsIovDeleteVPort

- ea: `0x140094d5c`
- end: `0x1400953e2`
- name: `VmsIovDeleteVPort`
- size: `1670`
- prototype: ``
- caller_count: `4`
- callee_count: `22`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14012c0e0`
- `0x14012edb0`
- `0x14012fff8`
- `0x140134704`

## callees

- `0x14001484c`
- `0x140027a64`
- `0x14002e0f0`
- `0x1400313cc`
- `0x140035438`
- `0x14003a450`
- `0x14003e9e4`
- `0x14004f5d8`
- `0x14006b084`
- `0x14008497c`
- `0x140089a04`
- `0x14008a800`
- `0x140094d5c`
- `0x1400953e8`
- `0x140117640`
- `0x1401177b0`
- `0x14011ee94`
- `0x14013b53c`
- `0x1401430bc`
- `0x14015c020`
- `0x14015dce8`
- `0x1401bbcb0`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140094e39`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140094e39`
- `ntoskrnl!ExRundownCompleted` at `0x140094e48`
- `ntoskrnl!ExRundownCompleted` at `0x140094e48`
- `NDIS!NdisMSleep` at `0x1400951a1`
- `NDIS!NdisMSleep` at `0x1400951a1`
- `NDIS!NdisReleaseRWLock` at `0x140095127`
- `NDIS!NdisReleaseRWLock` at `0x1400952a9`
- `NDIS!NdisReleaseRWLock` at `0x140095127`
- `NDIS!NdisReleaseRWLock` at `0x1400952a9`

## string_xrefs

- `0x140094e9a`: `IsListEmpty(&ObjNic->NicNDKInfo.NDKAdapterList)`
- `0x1400950f4`: `vmq->ProtocolNic == ProtocolNic`
- `0x140094dc0`: `ObjNic != NULL && ProtocolNic != NULL`

## pseudocode

```c
__int64 __fastcall VmsIovDeleteVPort(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  unsigned int v4; // ebx
  _QWORD *v5; // rbx
  int v6; // edx
  int v7; // r8d
  __int64 v8; // r14
  int v9; // edx
  char v10; // r12
  __int64 VmqExt; // rax
  int v12; // edx
  __int64 v13; // rbx
  char v14; // r15
  unsigned int v15; // ebx
  int v16; // edx
  int v17; // edx
  struct _NDIS_RW_LOCK_EX *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rdx
  _WORD v25[2]; // [rsp+60h] [rbp-9h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+64h] [rbp-5h] BYREF
  __int64 v27; // [rsp+68h] [rbp-1h] BYREF
  __int64 v28; // [rsp+70h] [rbp+7h] BYREF
  int v29; // [rsp+78h] [rbp+Fh]

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v2 = a2;
  v25[0] = 0;
  v28 = 0;
  v29 = 0;
  if ( !a1 || !a2 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrNicLog,
      a2,
      19,
      117,
      (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
      "ObjNic != NULL && ProtocolNic != NULL");
    if ( !a1 || !v2 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
      if ( !a1 || !v2 )
      {
        v4 = -1073741811;
        LOBYTE(a2) = 2;
        WPP_RECORDER_SF_qqd(
          VmsIfrNicLog,
          a2,
          20,
          118,
          (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
          a1,
          v2,
          13);
        goto LABEL_64;
      }
    }
  }
  v4 = 0;
  if ( *(_BYTE *)(a1 + 4072) )
  {
    if ( *(_DWORD *)(a1 + 1872) == 1 )
    {
      if ( *(_DWORD *)(a1 + 4764) == 3 )
        VmsNdkSendPnPEvent(a1, 14);
      ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(a1 + 4872));
      ExRundownCompleted((PEX_RUNDOWN_REF)(a1 + 4872));
    }
    *(_DWORD *)(a1 + 4764) = 0;
    v5 = (_QWORD *)(a1 + 4824);
    *(_DWORD *)(a1 + 4860) = 0;
    *(_OWORD *)(a1 + 4768) = 0;
    *(_OWORD *)(a1 + 4784) = 0;
    *(_OWORD *)(a1 + 4800) = 0;
    *(_QWORD *)(a1 + 4816) = 0;
    if ( (_QWORD *)*v5 != v5 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        a2,
        19,
        119,
        (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
        "IsListEmpty(&ObjNic->NicNDKInfo.NDKAdapterList)");
      if ( (_QWORD *)*v5 != v5 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    if ( *(_BYTE *)(a1 + 4072) == 1 && (_QWORD *)*v5 != v5 )
    {
      v4 = -1073741811;
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(VmsIfrNicLog, a2, 20, 120, (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids, 13);
LABEL_64:
      WPP_RECORDER_SF_qqLd(
        VmsIfrNicLog,
        v6,
        v7,
        132,
        (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
        a1,
        v2,
        0,
        v4);
      return v4;
    }
    v8 = *(_QWORD *)(v2 + 3312);
    if ( !v8 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrNicLog,
        a2,
        19,
        121,
        (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
        "ptNicExt != NULL");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
      v4 = -1073741811;
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_d(VmsIfrNicLog, v9, 20, 122, (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids, 13);
      goto LABEL_64;
    }
    if ( !*(_BYTE *)(v8 + 305) && !*(_BYTE *)(v8 + 1513) )
    {
      v4 = -1073741811;
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(VmsIfrNicLog, a2, 20, 123, (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids, 13);
      goto LABEL_64;
    }
    v10 = 0;
    VmsOmObjectLockShared(a1, &LockState, 0);
    VmqExt = VmsMpCommonGetVmqExt(a1);
    if ( VmqExt )
    {
      v13 = *(_QWORD *)(VmqExt + 16);
      if ( v13 )
      {
        if ( *(_DWORD *)(v13 + 196) )
        {
          WPP_RECORDER_SF_s(
            VmsIfrNicLog,
            v12,
            19,
            124,
            (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
            "vmq->NumFilters == 0");
          if ( *(_DWORD *)(v13 + 196) )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        if ( *(_DWORD *)(v13 + 56) )
        {
          WPP_RECORDER_SF_s(
            VmsIfrNicLog,
            v12,
            19,
            125,
            (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
            "vmq->QueueId == NDIS_DEFAULT_RECEIVE_QUEUE_ID");
          if ( *(_DWORD *)(v13 + 56) )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        if ( !*(_DWORD *)(v13 + 60) )
        {
          WPP_RECORDER_SF_s(
            VmsIfrNicLog,
            v12,
            19,
            126,
            (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
            "vmq->VPortId != NDIS_DEFAULT_VPORT_ID");
          if ( !*(_DWORD *)(v13 + 60) )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        if ( (*(_DWORD *)(v13 + 52) & 2) == 0 )
        {
          WPP_RECORDER_SF_s(
            VmsIfrNicLog,
            v12,
            19,
            127,
            (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
            "vmq->Flags & VMS_VMQ_QUEUE_BLOCK_FLAGS_QUEUE_ALLOCATED");
          if ( (*(_DWORD *)(v13 + 52) & 2) == 0 )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        if ( *(_QWORD *)(v13 + 40) != a1 )
        {
          WPP_RECORDER_SF_s(
            VmsIfrNicLog,
            v12,
            19,
            128,
            (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
            "vmq->Nic == ObjNic");
          if ( *(_QWORD *)(v13 + 40) != a1 )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        if ( *(_QWORD *)(v13 + 32) != v2 )
        {
          WPP_RECORDER_SF_s(
            VmsIfrNicLog,
            v12,
            19,
            129,
            (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
            "vmq->ProtocolNic == ProtocolNic");
          if ( *(_QWORD *)(v13 + 32) != v2 )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
      }
    }
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
    v29 = *(_DWORD *)(a1 + 4188);
    v28 = 786816;
    v14 = VmsPtCheckIsEmbeddedTeamingEnabled(v2, 0);
    v27 = *(_QWORD *)(v8 + 3392);
    if ( v14 )
    {
      v15 = 0;
      while ( (unsigned int)VmsTmGetMappedNicIndexByObjNic(a1, 3, v25)
           || (unsigned int)VmsPtNicMuxReferenceMemberAdapterByIndex(v2, v25[0], 22, &v27) )
      {
        NdisMSleep(0x2710u);
        if ( v15 >= 0x3E8 )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            v16,
            19,
            130,
            (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
            "retryCount < 1000");
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        ++v15;
      }
      v10 = 1;
    }
    v4 = VmsPtNicProcessPublicOid(a1, v2, 1, 66116, v25[0], *(_DWORD *)(a1 + 4188), 1, 0, (__int64)&v28, 12, 0);
    LOBYTE(v17) = 4;
    WPP_RECORDER_SF_ld(
      VmsVrssIfrLog,
      v17,
      3,
      131,
      (__int64)WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids,
      *(_DWORD *)(a1 + 4188),
      v4);
    if ( v4 )
    {
      if ( v14 )
        VmsTmUpdateStubAllocationMaskByObjNic(a1, 3);
      v4 = VmsCriticalOidFailureHandler(0x10244u);
    }
    else
    {
      if ( v14 )
        VmsTmUpdateStubAllocationMaskByObjNic(a1, 3);
      VmsOmObjectLockExclusive(a1, &LockState, 0);
      v18 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 56);
      *(_BYTE *)(a1 + 4072) = 0;
      *(_DWORD *)(a1 + 4188) = 0;
      NdisReleaseRWLock(v18, &LockState);
      v19 = *(unsigned int *)(a1 + 4720);
      v20 = v27;
      *(_DWORD *)(a1 + 4180) = 0;
      *(_QWORD *)(a1 + 4168) = 0;
      *(_BYTE *)(a1 + 4179) = 0;
      v21 = VmsPtCalculateChangeInNumQueuePairs(v20, v19);
      VmsPtAdjustNumQueuePairsInUse(v27, (unsigned int)-v21);
      LOBYTE(v22) = 3;
      VmsOmpObjectDereference(a1, v22);
      LOBYTE(v23) = 4;
      VmsOmpObjectDereference(v2, v23);
      if ( v14 )
        VmsOmNicDecrementControlCount(*(_QWORD *)v8, v25[0], 20);
    }
    if ( v10 )
      VmsOmNicDecrementControlCount(v2, v25[0], 22);
    if ( v4 )
      goto LABEL_64;
  }
  return v4;
}

```

## disassembly

```asm
0x140094d5c  mov     [rsp-8+arg_10], rbx
0x140094d61  push    rbp
0x140094d62  push    rsi
0x140094d63  push    rdi
0x140094d64  push    r12
0x140094d66  push    r13
0x140094d68  push    r14
0x140094d6a  push    r15
0x140094d6c  lea     rbp, [rsp-27h]
0x140094d71  sub     rsp, 90h
0x140094d78  mov     rax, cs:__security_cookie
0x140094d7f  xor     rax, rsp
0x140094d82  mov     [rbp+57h+var_40], rax
0x140094d86  xor     eax, eax
0x140094d88  lea     r15, WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids
0x140094d8f  xor     r13d, r13d
0x140094d92  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x140094d96  mov     [rbp+57h+LockState.Flags], al
0x140094d99  mov     rsi, rdx
0x140094d9c  mov     [rbp+57h+var_60], r13w
0x140094da1  mov     rdi, rcx
0x140094da4  mov     [rbp+57h+var_50], rax
0x140094da8  lea     r12d, [rax+13h]
0x140094dac  mov     [rbp+57h+var_48], eax
0x140094daf  test    rcx, rcx
0x140094db2  jz      short loc_140094DB9
0x140094db4  test    rdx, rdx
0x140094db7  jnz     short loc_140094E00
0x140094db9  mov     rcx, cs:VmsIfrNicLog
0x140094dc0  lea     rax, aObjnicNullProt; "ObjNic != NULL && ProtocolNic != NULL"
0x140094dc7  mov     [rsp+0C0h+var_98], rax
0x140094dcc  mov     r9d, 75h ; 'u'
0x140094dd2  mov     r8d, r12d
0x140094dd5  mov     [rsp+0C0h+var_A0], r15
0x140094dda  call    WPP_RECORDER_SF_s
0x140094ddf  test    rdi, rdi
0x140094de2  jz      short loc_140094DE9
0x140094de4  test    rsi, rsi
0x140094de7  jnz     short loc_140094E00
0x140094de9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ObjNic != ((void *)0) && ProtocolNic != ((void *)0)")
0x140094dee  test    rdi, rdi
0x140094df1  jz      loc_14009535C
0x140094df7  test    rsi, rsi
0x140094dfa  jz      loc_14009535C
0x140094e00  mov     ebx, r13d
0x140094e03  cmp     [rdi+0FE8h], r13b
0x140094e0a  jz      loc_1400953B8
0x140094e10  cmp     dword ptr [rdi+750h], 1
0x140094e17  jnz     short loc_140094E54
0x140094e19  cmp     dword ptr [rdi+129Ch], 3
0x140094e20  jnz     short loc_140094E2F
0x140094e22  mov     edx, 0Eh
0x140094e27  mov     rcx, rdi
0x140094e2a  call    VmsNdkSendPnPEvent
0x140094e2f  lea     rbx, [rdi+1308h]
0x140094e36  mov     rcx, rbx; RunRef
0x140094e39  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140094e40  nop     dword ptr [rax+rax+00h]
0x140094e45  mov     rcx, rbx; RunRef
0x140094e48  call    cs:__imp_ExRundownCompleted
0x140094e4f  nop     dword ptr [rax+rax+00h]
0x140094e54  mov     [rdi+129Ch], r13d
0x140094e5b  lea     rbx, [rdi+12D8h]
0x140094e62  mov     [rdi+12FCh], r13d
0x140094e69  xorps   xmm0, xmm0
0x140094e6c  movups  xmmword ptr [rdi+12A0h], xmm0
0x140094e73  xor     eax, eax
0x140094e75  movups  xmmword ptr [rdi+12B0h], xmm0
0x140094e7c  movups  xmmword ptr [rdi+12C0h], xmm0
0x140094e83  mov     [rdi+12D0h], rax
0x140094e8a  cmp     [rbx], rbx
0x140094e8d  jz      short loc_140094EBD
0x140094e8f  mov     rcx, cs:VmsIfrLog
0x140094e96  lea     r9d, [rax+77h]
0x140094e9a  lea     rax, aIslistemptyObj_1; "IsListEmpty(&ObjNic->NicNDKInfo.NDKAdap"...
0x140094ea1  mov     r8d, r12d
0x140094ea4  mov     [rsp+0C0h+var_98], rax
0x140094ea9  mov     [rsp+0C0h+var_A0], r15
0x140094eae  call    WPP_RECORDER_SF_s
0x140094eb3  cmp     [rbx], rbx
0x140094eb6  jz      short loc_140094EBD
0x140094eb8  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "IsListEmpty(&ObjNic->NicNDKInfo.NDKAdapterList)")
0x140094ebd  cmp     byte ptr [rdi+0FE8h], 1
0x140094ec4  jnz     short loc_140094EF8
0x140094ec6  cmp     [rbx], rbx
0x140094ec9  jz      short loc_140094EF8
0x140094ecb  mov     eax, 0C000000Dh
0x140094ed0  mov     ebx, eax
0x140094ed2  mov     rcx, cs:VmsIfrNicLog
0x140094ed9  mov     r9d, 78h ; 'x'
0x140094edf  mov     dword ptr [rsp+0C0h+var_98], eax
0x140094ee3  mov     dl, 2
0x140094ee5  mov     [rsp+0C0h+var_A0], r15
0x140094eea  lea     r8d, [r9-64h]
0x140094eee  call    WPP_RECORDER_SF_d
0x140094ef3  jmp     loc_14009538E
0x140094ef8  mov     r14, [rsi+0CF0h]
0x140094eff  test    r14, r14
0x140094f02  jnz     short loc_140094F58
0x140094f04  mov     rcx, cs:VmsIfrNicLog
0x140094f0b  lea     rax, aPtnicextNull_0; "ptNicExt != NULL"
0x140094f12  mov     [rsp+0C0h+var_98], rax
0x140094f17  lea     r9d, [r14+79h]
0x140094f1b  mov     r8d, r12d
0x140094f1e  mov     [rsp+0C0h+var_A0], r15
0x140094f23  call    WPP_RECORDER_SF_s
0x140094f28  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ptNicExt != ((void *)0)")
0x140094f2d  mov     eax, 0C000000Dh
0x140094f32  mov     ebx, eax
0x140094f34  mov     rcx, cs:VmsIfrNicLog
0x140094f3b  lea     r9d, [r14+7Ah]
0x140094f3f  mov     dword ptr [rsp+0C0h+var_98], eax
0x140094f43  lea     r8d, [r14+14h]
0x140094f47  mov     dl, 2
0x140094f49  mov     [rsp+0C0h+var_A0], r15
0x140094f4e  call    WPP_RECORDER_SF_d
0x140094f53  jmp     loc_14009538E
0x140094f58  cmp     [r14+131h], r13b
0x140094f5f  jnz     short loc_140094F97
0x140094f61  cmp     [r14+5E9h], r13b
0x140094f68  jnz     short loc_140094F97
0x140094f6a  mov     eax, 0C000000Dh
0x140094f6f  mov     ebx, eax
0x140094f71  mov     rcx, cs:VmsIfrNicLog
0x140094f78  mov     r9d, 7Bh ; '{'
0x140094f7e  mov     dword ptr [rsp+0C0h+var_98], eax
0x140094f82  mov     dl, 2
0x140094f84  mov     [rsp+0C0h+var_A0], r15
0x140094f89  lea     r8d, [r9-67h]
0x140094f8d  call    WPP_RECORDER_SF_d
0x140094f92  jmp     loc_14009538E
0x140094f97  xor     r8d, r8d
0x140094f9a  lea     rdx, [rbp+57h+LockState]
0x140094f9e  mov     rcx, rdi
0x140094fa1  mov     r12b, r13b
0x140094fa4  call    VmsOmObjectLockShared
0x140094fa9  mov     rcx, rdi
0x140094fac  call    VmsMpCommonGetVmqExt
0x140094fb1  test    rax, rax
0x140094fb4  jz      loc_14009511F
0x140094fba  mov     rbx, [rax+10h]
0x140094fbe  test    rbx, rbx
0x140094fc1  jz      loc_14009511F
0x140094fc7  cmp     [rbx+0C4h], r13d
0x140094fce  jz      short loc_140095005
0x140094fd0  mov     rcx, cs:VmsIfrNicLog
0x140094fd7  lea     rax, aVmqNumfilters0; "vmq->NumFilters == 0"
0x140094fde  mov     r9d, 7Ch ; '|'
0x140094fe4  mov     [rsp+0C0h+var_98], rax
0x140094fe9  mov     [rsp+0C0h+var_A0], r15
0x140094fee  lea     r8d, [r9-69h]
0x140094ff2  call    WPP_RECORDER_SF_s
0x140094ff7  cmp     [rbx+0C4h], r13d
0x140094ffe  jz      short loc_140095005
0x140095000  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "vmq->NumFilters == 0")
0x140095005  cmp     [rbx+38h], r13d
0x140095009  jz      short loc_14009503D
0x14009500b  mov     rcx, cs:VmsIfrNicLog
0x140095012  lea     rax, aVmqQueueidNdis; "vmq->QueueId == NDIS_DEFAULT_RECEIVE_QU"...
0x140095019  mov     r9d, 7Dh ; '}'
0x14009501f  mov     [rsp+0C0h+var_98], rax
0x140095024  mov     [rsp+0C0h+var_A0], r15
0x140095029  lea     r8d, [r9-6Ah]
0x14009502d  call    WPP_RECORDER_SF_s
0x140095032  cmp     [rbx+38h], r13d
0x140095036  jz      short loc_14009503D
0x140095038  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "vmq->QueueId == 0")
0x14009503d  cmp     [rbx+3Ch], r13d
0x140095041  jnz     short loc_140095075
0x140095043  mov     rcx, cs:VmsIfrNicLog
0x14009504a  lea     rax, aVmqVportidNdis_0; "vmq->VPortId != NDIS_DEFAULT_VPORT_ID"
0x140095051  mov     r9d, 7Eh ; '~'
0x140095057  mov     [rsp+0C0h+var_98], rax
0x14009505c  mov     [rsp+0C0h+var_A0], r15
0x140095061  lea     r8d, [r9-6Bh]
0x140095065  call    WPP_RECORDER_SF_s
0x14009506a  cmp     [rbx+3Ch], r13d
0x14009506e  jnz     short loc_140095075
0x140095070  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "vmq->VPortId != 0")
0x140095075  mov     eax, [rbx+34h]
0x140095078  test    al, 2
0x14009507a  jnz     short loc_1400950AF
0x14009507c  mov     rcx, cs:VmsIfrNicLog
0x140095083  lea     rax, aVmqFlagsVmsVmq_0; "vmq->Flags & VMS_VMQ_QUEUE_BLOCK_FLAGS_"...
0x14009508a  mov     r9d, 7Fh
0x140095090  mov     [rsp+0C0h+var_98], rax
0x140095095  mov     [rsp+0C0h+var_A0], r15
0x14009509a  lea     r8d, [r9-6Ch]
0x14009509e  call    WPP_RECORDER_SF_s
0x1400950a3  mov     eax, [rbx+34h]
0x1400950a6  test    al, 2
0x1400950a8  jnz     short loc_1400950AF
0x1400950aa  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "vmq->Flags & 0x00000002")
0x1400950af  cmp     [rbx+28h], rdi
0x1400950b3  jz      short loc_1400950E7
0x1400950b5  mov     rcx, cs:VmsIfrNicLog
0x1400950bc  lea     rax, aVmqNicObjnic; "vmq->Nic == ObjNic"
0x1400950c3  mov     r9d, 80h
0x1400950c9  mov     [rsp+0C0h+var_98], rax
0x1400950ce  mov     [rsp+0C0h+var_A0], r15
0x1400950d3  lea     r8d, [r9-6Dh]
0x1400950d7  call    WPP_RECORDER_SF_s
0x1400950dc  cmp     [rbx+28h], rdi
0x1400950e0  jz      short loc_1400950E7
0x1400950e2  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "vmq->Nic == ObjNic")
0x1400950e7  cmp     [rbx+20h], rsi
0x1400950eb  jz      short loc_14009511F
0x1400950ed  mov     rcx, cs:VmsIfrNicLog
0x1400950f4  lea     rax, aVmqProtocolnic; "vmq->ProtocolNic == ProtocolNic"
0x1400950fb  mov     r9d, 81h
0x140095101  mov     [rsp+0C0h+var_98], rax
0x140095106  mov     [rsp+0C0h+var_A0], r15
0x14009510b  lea     r8d, [r9-6Eh]
0x14009510f  call    WPP_RECORDER_SF_s
0x140095114  cmp     [rbx+20h], rsi
0x140095118  jz      short loc_14009511F
0x14009511a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "vmq->ProtocolNic == ProtocolNic")
0x14009511f  mov     rcx, [rdi+38h]; Lock
0x140095123  lea     rdx, [rbp+57h+LockState]; LockState
0x140095127  call    cs:__imp_NdisReleaseRWLock
0x14009512e  nop     dword ptr [rax+rax+00h]
0x140095133  mov     eax, [rdi+105Ch]
0x140095139  xor     edx, edx
0x14009513b  mov     rcx, rsi
0x14009513e  mov     [rbp+57h+var_48], eax
0x140095141  mov     [rbp+57h+var_50], 0C0180h
0x140095149  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x14009514e  mov     r15b, al
0x140095151  mov     rax, [r14+0D40h]
0x140095158  mov     [rbp+57h+var_58], rax
0x14009515c  test    r15b, r15b
0x14009515f  jz      loc_1400951E8
0x140095165  mov     ebx, r13d
0x140095168  lea     r12, WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids
0x14009516f  lea     r8, [rbp+57h+var_60]
0x140095173  mov     edx, 3
0x140095178  mov     rcx, rdi
0x14009517b  call    VmsTmGetMappedNicIndexByObjNic
0x140095180  test    eax, eax
0x140095182  jnz     short loc_14009519C
0x140095184  movzx   edx, [rbp+57h+var_60]
0x140095188  lea     r9, [rbp+57h+var_58]
0x14009518c  lea     r8d, [rax+16h]
0x140095190  mov     rcx, rsi
0x140095193  call    VmsPtNicMuxReferenceMemberAdapterByIndex
0x140095198  test    eax, eax
0x14009519a  jz      short loc_1400951E5
0x14009519c  mov     ecx, 2710h; MicrosecondsToSleep
0x1400951a1  call    cs:__imp_NdisMSleep
0x1400951a8  nop     dword ptr [rax+rax+00h]
0x1400951ad  cmp     ebx, 3E8h
0x1400951b3  jb      short loc_1400951E1
0x1400951b5  mov     rcx, cs:VmsIfrLog
0x1400951bc  lea     rax, aRetrycount1000; "retryCount < 1000"
0x1400951c3  mov     r9d, 82h
0x1400951c9  mov     [rsp+0C0h+var_98], rax
0x1400951ce  mov     [rsp+0C0h+var_A0], r12
0x1400951d3  lea     r8d, [r9-6Fh]
0x1400951d7  call    WPP_RECORDER_SF_s
0x1400951dc  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "retryCount < 1000")
0x1400951e1  inc     ebx
0x1400951e3  jmp     short loc_14009516F
0x1400951e5  mov     r12b, 1
0x1400951e8  movzx   ecx, [rbp+57h+var_60]
0x1400951ec  lea     rax, [rbp+57h+var_50]
0x1400951f0  mov     [rsp+0C0h+var_70], r13d
0x1400951f5  mov     r9d, 10244h
0x1400951fb  mov     [rsp+0C0h+var_78], 0Ch
0x140095203  mov     r8d, 1
0x140095209  mov     [rsp+0C0h+var_80], rax
0x14009520e  mov     rdx, rsi
0x140095211  mov     eax, [rdi+105Ch]
0x140095217  mov     [rsp+0C0h+var_88], r13d
0x14009521c  mov     dword ptr [rsp+0C0h+var_90], 1
0x140095224  mov     dword ptr [rsp+0C0h+var_98], eax
0x140095228  mov     dword ptr [rsp+0C0h+var_A0], ecx
0x14009522c  mov     rcx, rdi
0x14009522f  call    VmsPtNicProcessPublicOid
0x140095234  mov     ebx, eax
0x140095236  mov     ecx, [rdi+105Ch]
0x14009523c  mov     r9d, 83h
0x140095242  mov     dword ptr [rsp+0C0h+var_90], eax
0x140095246  mov     dl, 4
0x140095248  mov     dword ptr [rsp+0C0h+var_98], ecx
0x14009524c  lea     rax, WPP_a4992ba016473c310ce3fedced6e9e69_Traceguids
0x140095253  mov     rcx, cs:VmsVrssIfrLog
0x14009525a  lea     r8d, [r9-80h]
0x14009525e  mov     [rsp+0C0h+var_A0], rax
0x140095263  call    WPP_RECORDER_SF_ld
0x140095268  test    ebx, ebx
0x14009526a  jnz     loc_140095313
0x140095270  test    r15b, r15b
0x140095273  jz      short loc_140095284
0x140095275  lea     edx, [rbx+3]
0x140095278  mov     rcx, rdi
0x14009527b  lea     r8d, [rbx+1]
0x14009527f  call    VmsTmUpdateStubAllocationMaskByObjNic
0x140095284  xor     r8d, r8d
0x140095287  lea     rdx, [rbp+57h+LockState]
0x14009528b  mov     rcx, rdi
  ... truncated ...
```
