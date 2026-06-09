# VmsExtFilterIngressFilterNetBufferLists

- ea: `0x14001acc8`
- end: `0x14001b261`
- name: `VmsExtFilterIngressFilterNetBufferLists`
- size: `1433`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001acb0`

## callees

- `0x140018330`
- `0x140018558`
- `0x140019560`
- `0x14001acc8`
- `0x14001b270`
- `0x140027a64`
- `0x14002c5d4`
- `0x14002fcbc`
- `0x14008497c`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001ae43`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001af2d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001ae43`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001af2d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001adfd`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001b17d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001adfd`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001b17d`
- `NDIS!NdisFSendNetBufferLists` at `0x14001af60`
- `NDIS!NdisFSendNetBufferLists` at `0x14001af60`
- `NDIS!NdisAcquireRWLockRead` at `0x14001ae1c`
- `NDIS!NdisAcquireRWLockRead` at `0x14001ae1c`
- `NDIS!NdisReleaseRWLock` at `0x14001ae6d`
- `NDIS!NdisReleaseRWLock` at `0x14001ae6d`

## string_xrefs

- `0x14001b03a`: `VmsNblHelperAppendNblsMoveLast`
- `0x14001b0b4`: `(curNblContext->Flags & (VMS_NBL_ROUTING_CONTEXT_FLAG_NEEDS_PT_EGRESS_COMPLETION | VMS_NBL_ROUTING_CONTEXT_FLAG_NEEDS_MP_INGRESS_COMPLETION | VMS_NBL_ROUTING_CONTEXT_FLAG_NEEDS_FILTER_INGRESS_COMPLETION | VMS_NBL_ROUTING_CONTEXT_FLAG_RESTORE_HANDLE_ON_INGRESS_COMPLETE | VMS_NBL_ROUTING_CONTEXT_FLAG_RESTORE_HANDLE_ON_EGRESS_COMPLETE)) == 0`

## pseudocode

```c
void __fastcall VmsExtFilterIngressFilterNetBufferLists(__int64 a1, __int64 *a2, NDIS_PORT_NUMBER a3, ULONG a4)
{
  __int64 *v4; // rdi
  __int64 *v6; // rbx
  __int64 **v7; // r12
  char v8; // r15
  unsigned int v9; // r13d
  __int64 *v10; // rsi
  __int64 v11; // rbx
  int v12; // edx
  UCHAR v13; // r8
  int v14; // esi
  unsigned __int8 v15; // di
  int v16; // edx
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // r13
  char v20; // r15
  __int64 v21; // rsi
  __int64 v22; // rax
  __int64 v23; // rdi
  __int64 v24; // rdi
  __int64 v25; // r12
  struct _NET_BUFFER_LIST *v26; // rdi
  unsigned int v27; // ebx
  PNET_BUFFER_LIST Alignment; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 *v35; // [rsp+30h] [rbp-28h] BYREF
  PNET_BUFFER_LIST NetBufferList; // [rsp+38h] [rbp-20h] BYREF
  __int64 v37[3]; // [rsp+40h] [rbp-18h] BYREF
  _UNKNOWN *retaddr; // [rsp+98h] [rbp+40h]
  char v39; // [rsp+A0h] [rbp+48h]
  struct _LOCK_STATE_EX LockState; // [rsp+A8h] [rbp+50h] BYREF
  NDIS_PORT_NUMBER PortNumber; // [rsp+B0h] [rbp+58h]
  ULONG SendFlags; // [rsp+B8h] [rbp+60h]

  SendFlags = a4;
  PortNumber = a3;
  v4 = a2;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NetBufferList = 0;
  v37[0] = 0;
  if ( (VmsDiagnosticFlags & 1) != 0 )
  {
    if ( a2 )
    {
      v29 = a2[36];
      if ( v29 )
      {
        v30 = *(_QWORD *)(v29 + 16);
        if ( v30 )
        {
          *(_QWORD *)(v30 + 176) = "VmsExtFilterIngressFilterNetBufferLists";
          *(_DWORD *)(v30 + 184) = 509;
          *(_QWORD *)(v30 + 168) = retaddr;
        }
      }
    }
  }
  v6 = 0;
  v7 = &v35;
  v35 = 0;
  v8 = a4 & 1;
  v9 = 0;
  v39 = a4 & 1;
  if ( a2 )
  {
    do
    {
      v10 = (__int64 *)*v4;
      if ( (VmsDiagnosticFlags & 1) != 0 )
      {
        if ( v10 )
        {
          v31 = v10[36];
          if ( v31 )
          {
            v32 = *(_QWORD *)(v31 + 16);
            if ( v32 )
            {
              *(_QWORD *)(v32 + 176) = "VmsExtFilterIngressFilterNetBufferLists";
              *(_DWORD *)(v32 + 184) = 526;
              *(_QWORD *)(v32 + 168) = retaddr;
            }
          }
        }
      }
      *v4 = 0;
      v11 = v4[36];
      if ( v11 )
        v11 = *(_QWORD *)(v11 + 16);
      if ( (*(_DWORD *)v11 & 0xD90) != 0 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          (unsigned int)WPP_2b5d34e9a7f63b44289e2806fb3c4af2_Traceguids,
          19,
          18,
          (__int64)WPP_2b5d34e9a7f63b44289e2806fb3c4af2_Traceguids,
          "(curNblContext->Flags & (VMS_NBL_ROUTING_CONTEXT_FLAG_NEEDS_PT_EGRESS_COMPLETION | VMS_NBL_ROUTING_CONTEXT_FLA"
          "G_NEEDS_MP_INGRESS_COMPLETION | VMS_NBL_ROUTING_CONTEXT_FLAG_NEEDS_FILTER_INGRESS_COMPLETION | VMS_NBL_ROUTING"
          "_CONTEXT_FLAG_RESTORE_HANDLE_ON_INGRESS_COMPLETE | VMS_NBL_ROUTING_CONTEXT_FLAG_RESTORE_HANDLE_ON_EGRESS_COMPLETE)) == 0");
        if ( (*(_DWORD *)v11 & 0xD90) != 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      *(_DWORD *)v11 |= 0x100u;
      if ( (*((_DWORD *)v4 + 75) & 0x100) != 0 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrLog,
          (unsigned int)WPP_2b5d34e9a7f63b44289e2806fb3c4af2_Traceguids,
          19,
          19,
          (__int64)WPP_2b5d34e9a7f63b44289e2806fb3c4af2_Traceguids,
          "fwdDetail->NativeForwardingRequired == 0");
        if ( (*((_DWORD *)v4 + 75) & 0x100) != 0 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      if ( VmsVerifierEnabled && *(_DWORD *)(v11 + 68) )
        VmsTrcVerifierFailure(40967, v4, a1, 0);
      if ( (*(_BYTE *)(a1 + 1232) & 8) != 0 )
        *((_DWORD *)v4 + 75) |= 0x100u;
      if ( (VmsDiagnosticFlags & 1) != 0 )
      {
        v33 = v4[36];
        if ( v33 )
        {
          v34 = *(_QWORD *)(v33 + 16);
          if ( v34 )
          {
            *(_DWORD *)(v34 + 184) = 2646;
            *(_QWORD *)(v34 + 176) = "VmsNblHelperAppendNblsMoveLast";
            *(_QWORD *)(v34 + 168) = retaddr;
          }
        }
      }
      *v7 = v4;
      do
      {
        v7 = (__int64 **)v4;
        v4 = (__int64 *)*v4;
      }
      while ( v4 );
      ++v9;
      v4 = v10;
    }
    while ( v10 );
    v6 = v35;
    v8 = v39;
  }
  if ( v8 )
  {
    if ( KeGetCurrentIrql() != 2 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v12,
        19,
        24,
        (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
        "KeGetCurrentIrql() == DISPATCH_LEVEL");
      if ( KeGetCurrentIrql() != 2 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v13 = 1;
  }
  else
  {
    v13 = 0;
  }
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState, v13);
  v14 = *(_DWORD *)(a1 + 8916);
  v15 = *(_BYTE *)(a1 + 1232) & 1;
  if ( !v15 && v14 != 1 )
    _InterlockedAdd64(
      (volatile signed __int64 *)(*(_QWORD *)(a1 + 6472) + ((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6) + 8),
      v9);
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
  if ( v15 || v14 == 1 )
  {
    VmsExtHelperReportAllPacketsDropped(a1, (_DWORD)v6, v17, 2 * (v15 ^ 1) - 536870883, -536862636);
    VmsExtIoPacketRouted(v6, 0);
  }
  else
  {
    v19 = SendFlags;
    if ( (SendFlags & 0x20) != 0 )
    {
      if ( VmsVerifierEnabled && !(unsigned __int8)VmsNblHelperVerifySingleSourcePort(v6) )
        VmsTrcVerifierFailure(40972, v6, v19, a1);
      v20 = 1;
    }
    else
    {
      v20 = VmsNblHelperVerifySingleSourcePort(v6);
    }
    if ( v6 )
    {
      do
      {
        if ( v20 )
        {
          v21 = 0;
        }
        else
        {
          v21 = *v6;
          *v6 = 0;
        }
        v22 = v6[36];
        if ( v22 )
          v23 = *(_QWORD *)(v22 + 16);
        else
          v23 = 0;
        v24 = *(_QWORD *)(v23 + 24);
        if ( !v24 )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            v16,
            19,
            20,
            (__int64)WPP_2b5d34e9a7f63b44289e2806fb3c4af2_Traceguids,
            "sourceNic != NULL");
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        v25 = *(_QWORD *)(v24 + 1984);
        if ( !v25 )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            v16,
            19,
            21,
            (__int64)WPP_2b5d34e9a7f63b44289e2806fb3c4af2_Traceguids,
            "sourcePort != NULL");
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        VmsExtFilterSourceProcessing(v24, v25, v6, v18, (__int64 *)&NetBufferList, v37);
        v26 = NetBufferList;
        if ( NetBufferList )
        {
          v27 = 0;
          Alignment = NetBufferList;
          do
          {
            Alignment = (PNET_BUFFER_LIST)Alignment->Link.Alignment;
            ++v27;
          }
          while ( Alignment );
          _InterlockedAdd64(
            (volatile signed __int64 *)(*(_QWORD *)(a1 + 6472)
                                      + ((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                      + 16),
            v27);
          NdisFSendNetBufferLists(*(NDIS_HANDLE *)(a1 + 4304), v26, PortNumber, v19);
        }
        if ( v37[0] )
          VmsNblHelperRefCountDecrementMany(v37[0], v20 == 0);
        v6 = (__int64 *)v21;
      }
      while ( v21 );
    }
  }
}

```

## disassembly

```asm
0x14001acc8  mov     [rsp-40h+SendFlags], r9d
0x14001accd  mov     [rsp-40h+PortNumber], r8d
0x14001acd2  push    rbp
0x14001acd3  push    rbx
0x14001acd4  push    rsi
0x14001acd5  push    rdi
0x14001acd6  push    r12
0x14001acd8  push    r13
0x14001acda  push    r14
0x14001acdc  push    r15
0x14001acde  mov     rbp, rsp
0x14001ace1  sub     rsp, 58h
0x14001ace5  xor     eax, eax
0x14001ace7  mov     rdi, rdx
0x14001acea  mov     word ptr [rbp+LockState.OldIrql], ax
0x14001acee  lea     rdx, aVmsextfilterin_0; "VmsExtFilterIngressFilterNetBufferLists"
0x14001acf5  mov     [rbp+LockState.Flags], al
0x14001acf8  mov     r14, rcx
0x14001acfb  mov     rcx, [rbp+40h]
0x14001acff  mov     [rbp+NetBufferList], rax
0x14001ad03  mov     [rbp+var_18], rax
0x14001ad07  mov     eax, cs:VmsDiagnosticFlags
0x14001ad0d  test    al, 1
0x14001ad0f  jnz     loc_14001AF97
0x14001ad15  xor     ebx, ebx
0x14001ad17  lea     r12, [rbp+var_28]
0x14001ad1b  mov     r15b, r9b
0x14001ad1e  mov     [rbp+var_28], rbx
0x14001ad22  and     r15b, 1
0x14001ad26  lea     rdx, WPP_2b5d34e9a7f63b44289e2806fb3c4af2_Traceguids
0x14001ad2d  xor     r13d, r13d
0x14001ad30  mov     [rbp+arg_0], r15b
0x14001ad34  test    rdi, rdi
0x14001ad37  jz      loc_14001ADF4
0x14001ad3d  lea     r15, aVmsextfilterin_0; "VmsExtFilterIngressFilterNetBufferLists"
0x14001ad44  mov     eax, cs:VmsDiagnosticFlags
0x14001ad4a  mov     rsi, [rdi]
0x14001ad4d  mov     rcx, [rbp+40h]
0x14001ad51  test    al, 1
0x14001ad53  jnz     loc_14001AFDA
0x14001ad59  mov     qword ptr [rdi], 0
0x14001ad60  mov     rbx, [rdi+120h]
0x14001ad67  test    rbx, rbx
0x14001ad6a  jz      loc_14001B0A8
0x14001ad70  mov     rbx, [rbx+10h]
0x14001ad74  test    dword ptr [rbx], 0D90h
0x14001ad7a  jnz     loc_14001B0AD
0x14001ad80  mov     ecx, 100h
0x14001ad85  or      [rbx], ecx
0x14001ad87  test    [rdi+12Ch], ecx
0x14001ad8d  jnz     loc_14001B0ED
0x14001ad93  cmp     cs:VmsVerifierEnabled, 0
0x14001ad9a  jnz     loc_14001B12D
0x14001ada0  test    byte ptr [r14+4D0h], 8
0x14001ada8  jz      short loc_14001ADB2
0x14001adaa  bts     dword ptr [rdi+12Ch], 8
0x14001adb2  mov     eax, cs:VmsDiagnosticFlags
0x14001adb8  mov     rcx, [rbp+40h]
0x14001adbc  test    al, 1
0x14001adbe  jnz     loc_14001B01D
0x14001adc4  mov     [r12], rdi
0x14001adc8  mov     rax, [rdi]
0x14001adcb  mov     r12, rdi
0x14001adce  mov     rdi, rax
0x14001add1  test    rax, rax
0x14001add4  jnz     short loc_14001ADC8
0x14001add6  inc     r13d
0x14001add9  lea     rdx, WPP_2b5d34e9a7f63b44289e2806fb3c4af2_Traceguids
0x14001ade0  mov     rdi, rsi
0x14001ade3  test    rsi, rsi
0x14001ade6  jnz     loc_14001AD44
0x14001adec  mov     rbx, [rbp+var_28]
0x14001adf0  mov     r15b, [rbp+arg_0]
0x14001adf4  test    r15b, r15b
0x14001adf7  jz      loc_14001B090
0x14001adfd  call    cs:__imp_KeGetCurrentIrql
0x14001ae04  nop     dword ptr [rax+rax+00h]
0x14001ae09  cmp     al, 2
0x14001ae0b  jnz     loc_14001B14F
0x14001ae11  mov     r8b, 1; Flags
0x14001ae14  mov     rcx, [r14+38h]; Lock
0x14001ae18  lea     rdx, [rbp+LockState]; LockState
0x14001ae1c  call    cs:__imp_NdisAcquireRWLockRead
0x14001ae23  nop     dword ptr [rax+rax+00h]
0x14001ae28  mov     dil, [r14+4D0h]
0x14001ae2f  mov     esi, [r14+22D4h]
0x14001ae36  and     dil, 1
0x14001ae3a  jnz     short loc_14001AE65
0x14001ae3c  cmp     esi, 1
0x14001ae3f  jz      short loc_14001AE65
0x14001ae41  xor     ecx, ecx; ProcNumber
0x14001ae43  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14001ae4a  nop     dword ptr [rax+rax+00h]
0x14001ae4f  mov     edx, eax
0x14001ae51  mov     rax, [r14+1948h]
0x14001ae58  shl     rdx, 6
0x14001ae5c  mov     ecx, r13d
0x14001ae5f  lock add [rax+rdx+8], rcx
0x14001ae65  mov     rcx, [r14+38h]; Lock
0x14001ae69  lea     rdx, [rbp+LockState]; LockState
0x14001ae6d  call    cs:__imp_NdisReleaseRWLock
0x14001ae74  nop     dword ptr [rax+rax+00h]
0x14001ae79  test    dil, dil
0x14001ae7c  jnz     loc_14001B05E
0x14001ae82  cmp     esi, 1
0x14001ae85  jz      loc_14001B05E
0x14001ae8b  mov     r13d, [rbp+SendFlags]
0x14001ae8f  test    r13b, 20h
0x14001ae93  jz      loc_14001B098
0x14001ae99  cmp     cs:VmsVerifierEnabled, dil
0x14001aea0  jnz     loc_14001B19B
0x14001aea6  mov     r15b, 1
0x14001aea9  test    rbx, rbx
0x14001aeac  jz      loc_14001AF85
0x14001aeb2  test    r15b, r15b
0x14001aeb5  jz      loc_14001B1C3
0x14001aebb  xor     esi, esi
0x14001aebd  mov     rax, [rbx+120h]
0x14001aec4  test    rax, rax
0x14001aec7  jz      loc_14001B1D2
0x14001aecd  mov     rdi, [rax+10h]
0x14001aed1  mov     rdi, [rdi+18h]
0x14001aed5  test    rdi, rdi
0x14001aed8  jz      loc_14001B1D9
0x14001aede  mov     r12, [rdi+7C0h]
0x14001aee5  test    r12, r12
0x14001aee8  jz      loc_14001B211
0x14001aeee  lea     rax, [rbp+var_18]
0x14001aef2  mov     r8, rbx
0x14001aef5  mov     [rsp+58h+var_30], rax
0x14001aefa  mov     rdx, r12
0x14001aefd  lea     rax, [rbp+NetBufferList]
0x14001af01  mov     rcx, rdi
0x14001af04  mov     [rsp+58h+var_38], rax
0x14001af09  call    VmsExtFilterSourceProcessing
0x14001af0e  mov     rdi, [rbp+NetBufferList]
0x14001af12  test    rdi, rdi
0x14001af15  jz      short loc_14001AF6C
0x14001af17  xor     ebx, ebx
0x14001af19  mov     rax, rdi
0x14001af1c  test    rdi, rdi
0x14001af1f  jz      short loc_14001AF2B
0x14001af21  mov     rax, [rax]
0x14001af24  inc     ebx
0x14001af26  test    rax, rax
0x14001af29  jnz     short loc_14001AF21
0x14001af2b  xor     ecx, ecx; ProcNumber
0x14001af2d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14001af34  nop     dword ptr [rax+rax+00h]
0x14001af39  mov     r8d, eax
0x14001af3c  mov     rax, [r14+1948h]
0x14001af43  shl     r8, 6
0x14001af47  mov     ecx, ebx
0x14001af49  lock add [rax+r8+10h], rcx
0x14001af4f  mov     r8d, [rbp+PortNumber]; PortNumber
0x14001af53  mov     r9d, r13d; SendFlags
0x14001af56  mov     rcx, [r14+10D0h]; NdisFilterHandle
0x14001af5d  mov     rdx, rdi; NetBufferList
0x14001af60  call    cs:__imp_NdisFSendNetBufferLists
0x14001af67  nop     dword ptr [rax+rax+00h]
0x14001af6c  mov     rcx, [rbp+var_18]
0x14001af70  test    rcx, rcx
0x14001af73  jnz     loc_14001B249
0x14001af79  mov     rbx, rsi
0x14001af7c  test    rsi, rsi
0x14001af7f  jnz     loc_14001AEB2
0x14001af85  add     rsp, 58h
0x14001af89  pop     r15
0x14001af8b  pop     r14
0x14001af8d  pop     r13
0x14001af8f  pop     r12
0x14001af91  pop     rdi
0x14001af92  pop     rsi
0x14001af93  pop     rbx
0x14001af94  pop     rbp
0x14001af95  retn
0x14001af97  test    rdi, rdi
0x14001af9a  jz      loc_14001AD15
0x14001afa0  mov     rax, [rdi+120h]
0x14001afa7  test    rax, rax
0x14001afaa  jz      loc_14001AD15
0x14001afb0  mov     rax, [rax+10h]
0x14001afb4  test    rax, rax
0x14001afb7  jz      loc_14001AD15
0x14001afbd  mov     [rax+0B0h], rdx
0x14001afc4  mov     dword ptr [rax+0B8h], 1FDh
0x14001afce  mov     [rax+0A8h], rcx
0x14001afd5  jmp     loc_14001AD15
0x14001afda  test    rsi, rsi
0x14001afdd  jz      loc_14001AD59
0x14001afe3  mov     rax, [rsi+120h]
0x14001afea  test    rax, rax
0x14001afed  jz      loc_14001AD59
0x14001aff3  mov     rax, [rax+10h]
0x14001aff7  test    rax, rax
0x14001affa  jz      loc_14001AD59
0x14001b000  mov     [rax+0B0h], r15
0x14001b007  mov     dword ptr [rax+0B8h], 20Eh
0x14001b011  mov     [rax+0A8h], rcx
0x14001b018  jmp     loc_14001AD59
0x14001b01d  mov     rax, [rdi+120h]
0x14001b024  test    rax, rax
0x14001b027  jz      loc_14001ADC4
0x14001b02d  mov     rax, [rax+10h]
0x14001b031  test    rax, rax
0x14001b034  jz      loc_14001ADC4
0x14001b03a  lea     rdx, aVmsnblhelperap; "VmsNblHelperAppendNblsMoveLast"
0x14001b041  mov     dword ptr [rax+0B8h], 0A56h
0x14001b04b  mov     [rax+0B0h], rdx
0x14001b052  mov     [rax+0A8h], rcx
0x14001b059  jmp     loc_14001ADC4
0x14001b05e  movzx   r9d, dil
0x14001b062  mov     rdx, rbx
0x14001b065  xor     r9d, 1
0x14001b069  mov     dword ptr [rsp+58h+var_38], 0E0002054h
0x14001b071  mov     rcx, r14
0x14001b074  lea     r9d, ds:0FFFFFFFFE000001Dh[r9*2]
0x14001b07c  call    VmsExtHelperReportAllPacketsDropped
0x14001b081  xor     edx, edx
0x14001b083  mov     rcx, rbx
0x14001b086  call    VmsExtIoPacketRouted
0x14001b08b  jmp     loc_14001AF85
0x14001b090  xor     r8d, r8d
0x14001b093  jmp     loc_14001AE14
0x14001b098  mov     rcx, rbx
0x14001b09b  call    VmsNblHelperVerifySingleSourcePort
0x14001b0a0  mov     r15b, al
0x14001b0a3  jmp     loc_14001AEA9
0x14001b0a8  jmp     loc_14001AD74
0x14001b0ad  mov     rcx, cs:VmsIfrLog
0x14001b0b4  lea     rax, aCurnblcontextF_2; "(curNblContext->Flags & (VMS_NBL_ROUTIN"...
0x14001b0bb  mov     r9d, 12h
0x14001b0c1  mov     [rsp+58h+var_30], rax
0x14001b0c6  mov     [rsp+58h+var_38], rdx
0x14001b0cb  lea     r8d, [r9+1]
0x14001b0cf  call    WPP_RECORDER_SF_s
0x14001b0d4  test    dword ptr [rbx], 0D90h
0x14001b0da  jz      short loc_14001B0E1
0x14001b0dc  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "(curNblContext->Flags & (0x00000010 | 0x00000080 | 0x00000100 | 0x00000800 | 0x00000400)) == 0")
0x14001b0e1  lea     rdx, WPP_2b5d34e9a7f63b44289e2806fb3c4af2_Traceguids
0x14001b0e8  jmp     loc_14001AD80
0x14001b0ed  mov     rcx, cs:VmsIfrLog
0x14001b0f4  lea     rax, aFwddetailNativ; "fwdDetail->NativeForwardingRequired == "...
0x14001b0fb  mov     r9d, 13h
0x14001b101  mov     [rsp+58h+var_30], rax
0x14001b106  mov     r8d, r9d
0x14001b109  mov     [rsp+58h+var_38], rdx
0x14001b10e  call    WPP_RECORDER_SF_s
0x14001b113  test    dword ptr [rdi+12Ch], 100h
0x14001b11d  jz      loc_14001AD93
0x14001b123  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "fwdDetail->NativeForwardingRequired == 0")
0x14001b128  jmp     loc_14001AD93
0x14001b12d  cmp     dword ptr [rbx+44h], 0
0x14001b131  jz      loc_14001ADA0
0x14001b137  xor     r9d, r9d
0x14001b13a  mov     r8, r14
0x14001b13d  mov     rdx, rdi
0x14001b140  mov     ecx, 0A007h
0x14001b145  call    VmsTrcVerifierFailure
0x14001b14a  jmp     loc_14001ADA0
0x14001b14f  mov     rcx, cs:VmsIfrLog
0x14001b156  lea     rax, aKegetcurrentir; "KeGetCurrentIrql() == DISPATCH_LEVEL"
0x14001b15d  mov     [rsp+58h+var_30], rax
0x14001b162  mov     r9d, 18h
0x14001b168  lea     rax, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x14001b16f  mov     [rsp+58h+var_38], rax
0x14001b174  lea     r8d, [r9-5]
0x14001b178  call    WPP_RECORDER_SF_s
0x14001b17d  call    cs:__imp_KeGetCurrentIrql
0x14001b184  nop     dword ptr [rax+rax+00h]
0x14001b189  cmp     al, 2
0x14001b18b  jz      loc_14001AE11
0x14001b191  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "KeGetCurrentIrql() == 2")
0x14001b196  jmp     loc_14001AE11
0x14001b19b  mov     rcx, rbx
0x14001b19e  call    VmsNblHelperVerifySingleSourcePort
0x14001b1a3  test    al, al
0x14001b1a5  jnz     loc_14001AEA6
0x14001b1ab  mov     r8, r13
0x14001b1ae  mov     r9, r14
0x14001b1b1  mov     rdx, rbx
0x14001b1b4  mov     ecx, 0A00Ch
0x14001b1b9  call    VmsTrcVerifierFailure
0x14001b1be  jmp     loc_14001AEA6
0x14001b1c3  mov     rsi, [rbx]
0x14001b1c6  mov     qword ptr [rbx], 0
0x14001b1cd  jmp     loc_14001AEBD
0x14001b1d2  xor     edi, edi
0x14001b1d4  jmp     loc_14001AED1
0x14001b1d9  mov     rcx, cs:VmsIfrLog
0x14001b1e0  lea     rax, aSourcenicNull; "sourceNic != NULL"
0x14001b1e7  mov     [rsp+58h+var_30], rax
0x14001b1ec  mov     r9d, 14h
0x14001b1f2  lea     rax, WPP_2b5d34e9a7f63b44289e2806fb3c4af2_Traceguids
0x14001b1f9  mov     [rsp+58h+var_38], rax
0x14001b1fe  lea     r8d, [r9-1]
0x14001b202  call    WPP_RECORDER_SF_s
0x14001b207  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "sourceNic != ((void *)0)")
0x14001b20c  jmp     loc_14001AEDE
0x14001b211  mov     rcx, cs:VmsIfrLog
  ... truncated ...
```
