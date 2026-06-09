# VmsVmNicPvtVersion6HandleRxPdBatch

- ea: `0x1401a4d80`
- end: `0x1401a5546`
- name: `VmsVmNicPvtVersion6HandleRxPdBatch`
- size: `1990`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x14001484c`
- `0x140014988`
- `0x140017a7c`
- `0x140027a64`
- `0x14002bcc8`
- `0x14002e0f0`
- `0x1400313cc`
- `0x14003a450`
- `0x14008497c`
- `0x140116288`
- `0x140116410`
- `0x1401a49ec`
- `0x1401a4b08`
- `0x1401a4d80`
- `0x1401bbe10`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401a5012`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401a54c9`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401a5012`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401a54c9`
- `NDIS!NdisReleaseRWLock` at `0x1401a5065`
- `NDIS!NdisReleaseRWLock` at `0x1401a5065`
- `vmbkmclr!VmbChannelPacketComplete` at `0x1401a551e`
- `vmbkmclr!VmbChannelPacketComplete` at `0x1401a551e`
- `vmbkmclr!VmbChannelPacketFail` at `0x1401a4e25`
- `vmbkmclr!VmbChannelPacketFail` at `0x1401a4e25`
- `vmbkmclr!VmbChannelGetPointer` at `0x1401a4eac`
- `vmbkmclr!VmbChannelGetPointer` at `0x1401a4eac`

## string_xrefs

- `0x1401a4dc4`: `!"Security bug 9234257 must be fixed when this codepath is active"`
- `0x1401a546b`: `completedPDBuffer == NULL`

## pseudocode

```c
__int64 __fastcall VmsVmNicPvtVersion6HandleRxPdBatch(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  int v8; // edx
  int v10; // edx
  __int64 v11; // rsi
  __int64 v12; // r15
  __int64 v13; // rdi
  __int64 v14; // r14
  char v15; // r12
  __int64 NicHeaderAtIndex; // rbx
  __int64 v17; // rax
  int v18; // edx
  __int64 v19; // rax
  unsigned int v20; // ebx
  unsigned int v21; // ecx
  int v22; // edx
  _QWORD *v23; // rcx
  unsigned int v24; // r14d
  unsigned int v25; // esi
  _QWORD *v26; // rbx
  _QWORD *v27; // r12
  char v28; // al
  int v29; // r8d
  int v30; // r9d
  __int64 v31; // rcx
  __int64 *v32; // r12
  int v33; // eax
  __int64 v34; // rbx
  _QWORD *v35; // rsi
  __int64 v36; // rcx
  int v37; // edx
  __int64 v38; // rbx
  unsigned int v39; // [rsp+40h] [rbp-31h] BYREF
  unsigned int v40; // [rsp+44h] [rbp-2Dh] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+48h] [rbp-29h] BYREF
  int v42; // [rsp+4Ch] [rbp-25h]
  _QWORD *v43; // [rsp+50h] [rbp-21h]
  __int64 v44; // [rsp+58h] [rbp-19h] BYREF
  __int64 *v45; // [rsp+60h] [rbp-11h]
  __int64 v46; // [rsp+68h] [rbp-9h] BYREF
  __int64 v47; // [rsp+70h] [rbp-1h]
  __int64 Pointer; // [rsp+78h] [rbp+7h]
  __int64 *v49; // [rsp+80h] [rbp+Fh] BYREF
  __int64 v50; // [rsp+88h] [rbp+17h]
  unsigned __int16 v52; // [rsp+E0h] [rbp+6Fh]
  char v53; // [rsp+E8h] [rbp+77h]

  v44 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  WPP_RECORDER_SF_s(
    VmsIfrLog,
    a2,
    19,
    140,
    (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
    "!\"Security bug 9234257 must be fixed when this codepath is active\"");
  MicrosoftTelemetryAssertTriggeredNoArgsKM();
  if ( a4 >= 8 )
  {
    if ( *(_DWORD *)a3 != 136 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v8,
        19,
        142,
        (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
        "Message->Header.MessageType == NvspMessage6TypePdPostBatch");
      if ( *(_DWORD *)a3 != 136 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    if ( (*(_BYTE *)(a3 + 6) & 2) == 0 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v8,
        19,
        143,
        (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
        "Message->IsReceive");
      if ( (*(_BYTE *)(a3 + 6) & 2) == 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    Pointer = VmbChannelGetPointer(a1);
    v11 = Pointer;
    if ( !Pointer )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v10,
        19,
        144,
        (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
        "channelInfo != NULL");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v12 = *(_QWORD *)(Pointer + 8);
    if ( !v12 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v10,
        19,
        145,
        (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
        "vmNicExt != NULL");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v13 = *(_QWORD *)(v12 + 680);
    if ( !v13 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrLog,
        v10,
        19,
        146,
        (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
        "objNic != NULL");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    if ( *(_DWORD *)(v13 + 68) == 1 && *(_DWORD *)(v13 + 1880) == 1 )
    {
      v14 = *(_QWORD *)(v13 + 4112);
      v53 = 0;
      if ( !v14 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrNicLog,
          v10,
          19,
          147,
          (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
          "ecBlock != NULL");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      v15 = *(_BYTE *)(v12 + 866);
      if ( !*(_QWORD *)(v13 + 1984) )
      {
        WPP_RECORDER_SF_s(
          VmsIfrNicLog,
          v10,
          19,
          148,
          (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
          "objPort != NULL");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      NicHeaderAtIndex = VmsPtGetNicHeaderAtIndex(v13, 0);
      if ( NicHeaderAtIndex )
        _InterlockedIncrement64((volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                                          + *(_QWORD *)(NicHeaderAtIndex + 24)
                                                          + 8));
      VmsOmObjectLockShared(v13, &LockState, 0);
      v17 = *(_QWORD *)(v13 + 1888);
      v50 = v17;
      if ( v17 )
      {
        VmsOmpObjectReference(v17, 0);
        v53 = 1;
      }
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v13 + 56), &LockState);
      v44 = 0;
      v45 = &v44;
      v19 = *(_QWORD *)(v11 + 88);
      v42 = 0;
      v20 = *(unsigned __int16 *)(a3 + 4);
      v40 = v20;
      v52 = *(_WORD *)(v19 + 192);
      v21 = *(unsigned __int16 *)(v19 + 194);
      if ( v20 > v21 )
      {
        LOBYTE(v18) = 2;
        WPP_RECORDER_SF_ld(VmsIfrLog, v18, 20, 149, (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids, v20, v21);
        v20 = *(unsigned __int16 *)(*(_QWORD *)(v11 + 88) + 194LL);
        v40 = v20;
      }
      v39 = v20;
      v23 = (_QWORD *)VmsPDPopPDBuffers(v14 + (v15 != 0 ? 576LL : 464LL), &v39);
      v43 = v23;
      if ( v39 != v20 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrNicLog,
          v22,
          19,
          150,
          (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
          "numberOfBuffers == requestedNumberOfBuffers");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
        v23 = v43;
      }
      if ( v20 )
      {
        v24 = v40;
        v25 = 0;
        do
        {
          v26 = v23;
          v27 = v23;
          v43 = (_QWORD *)*v23;
          v47 = a3 + 8LL * v25 + 8;
          if ( !v23 )
          {
            WPP_RECORDER_SF_s(
              VmsIfrNicLog,
              v22,
              19,
              151,
              (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
              "hostPdBuffer != NULL");
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
          }
          if ( *((_WORD *)v26 + 28) )
          {
            WPP_RECORDER_SF_s(
              VmsIfrNicLog,
              v22,
              19,
              152,
              (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
              "hostPdBuffer->Flags == 0");
            if ( *((_WORD *)v26 + 28) )
              MicrosoftTelemetryAssertTriggeredNoArgsKM();
          }
          if ( (*(_DWORD *)v26[3] & 0x400) != 0 )
          {
            WPP_RECORDER_SF_s(
              VmsIfrNicLog,
              v22,
              19,
              153,
              (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
              "VMS_VMPD_IS_BUFFER_BOUND_TO_VM(hostPdBuffer) == FALSE");
            if ( (*(_DWORD *)v26[3] & 0x400) != 0 )
              MicrosoftTelemetryAssertTriggeredNoArgsKM();
          }
          *v27 = 0;
          if ( *(_BYTE *)(v12 + 866) )
          {
            v28 = VmsVmNicPvtShadowByHostPDBuffer(v12, v52, v26, v47);
          }
          else
          {
            LOWORD(v39) = 0;
            v40 = 0;
            if ( (unsigned __int8)VmsVmNicPvtValidateAndCaptureGuestPDBuffer(
                                    v12,
                                    v47,
                                    (_DWORD)v26,
                                    (unsigned int)&v39,
                                    (__int64)&v40) )
            {
              *((_DWORD *)v26 + 15) = 0;
              *v27 = 0;
              v31 = v26[3];
              *(_DWORD *)v31 |= 0xC00u;
              *(_WORD *)(v31 + 76) = v52;
              *(_WORD *)(v31 + 78) = v39;
              *(_DWORD *)(v31 + 72) = v40;
              v28 = 1;
              *(_QWORD *)(v31 + 80) = v12;
            }
            else
            {
              v28 = 0;
            }
          }
          if ( v28 )
          {
            v32 = v45;
            if ( *v45 )
            {
              WPP_RECORDER_SF_s(
                VmsIfrNicLog,
                v22,
                19,
                155,
                (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
                "*pdBufferListTail == NULL");
              if ( *v32 )
                MicrosoftTelemetryAssertTriggeredNoArgsKM();
            }
            ++v42;
            *v32 = (__int64)v26;
            v45 = v26;
          }
          else
          {
            if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
              WPP_RECORDER_SF_d(
                WPP_GLOBAL_Control->DeviceExtension,
                0,
                22,
                154,
                (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
                1);
            LOBYTE(v29) = 1;
            VmsPktReportDroppedPacket(v13, v22, v29, v30, -1073741823);
            VmsPDPushPDBuffers(v26);
          }
          v23 = v43;
          ++v25;
        }
        while ( v25 < v24 );
        v11 = Pointer;
      }
      v33 = v42;
      *(_DWORD *)(v11 + 100) += v42;
      v34 = *(_QWORD *)(v11 + 88);
      v46 = 0;
      v49 = &v46;
      if ( !v33 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrNicLog,
          v22,
          19,
          156,
          (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
          "totalBufferCount != 0");
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      if ( **(_QWORD **)(v34 + 216) )
      {
        WPP_RECORDER_SF_s(
          VmsIfrNicLog,
          v22,
          19,
          157,
          (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
          "*vmsPDQueue->VmPdInfo.RxPostTail == NULL");
        if ( **(_QWORD **)(v34 + 216) )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      v35 = (_QWORD *)(v34 + 208);
      **(_QWORD **)(v34 + 216) = v44;
      v36 = *(_QWORD *)(v34 + 40);
      *(_QWORD *)(v34 + 216) = v45;
      (*(void (__fastcall **)(__int64, __int64, __int64 **, _QWORD))(*(_QWORD *)(v36 + 8) + 8LL))(
        v36,
        v34 + 208,
        &v49,
        0);
      if ( v46 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrNicLog,
          v37,
          19,
          158,
          (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
          "completedPDBuffer == NULL");
        if ( v46 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      if ( !*v35 )
        *(_QWORD *)(v34 + 216) = v35;
      if ( v53 )
        VmsOmpObjectDereference(v50, 0);
      v38 = VmsPtGetNicHeaderAtIndex(v13, 0);
      if ( v38 )
        _InterlockedDecrement64((volatile signed __int64 *)(((unsigned __int64)KeGetCurrentProcessorNumberEx(0) << 6)
                                                          + *(_QWORD *)(v38 + 24)
                                                          + 8));
    }
    else
    {
      WPP_RECORDER_SF_s(
        VmsIfrNicLog,
        v10,
        19,
        159,
        (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
        "nicIsDisconnected == FALSE");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    return VmbChannelPacketComplete(a2, 0, 0);
  }
  else
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v8,
      19,
      141,
      (__int64)WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids,
      "!\"BufSize too small.\"");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    return VmbChannelPacketFail(a2);
  }
}

```

## disassembly

```asm
0x1401a4d80  mov     [rsp-8+arg_0], rbx
0x1401a4d85  mov     [rsp-8+arg_8], rdx
0x1401a4d8a  push    rbp
0x1401a4d8b  push    rsi
0x1401a4d8c  push    rdi
0x1401a4d8d  push    r12
0x1401a4d8f  push    r13
0x1401a4d91  push    r14
0x1401a4d93  push    r15
0x1401a4d95  lea     rbp, [rsp-1Fh]
0x1401a4d9a  sub     rsp, 90h
0x1401a4da1  xor     r12d, r12d
0x1401a4da4  mov     ebx, r9d
0x1401a4da7  xor     eax, eax
0x1401a4da9  mov     [rbp+4Fh+var_68], r12
0x1401a4dad  mov     word ptr [rbp+4Fh+LockState.OldIrql], ax
0x1401a4db1  mov     r13, r8
0x1401a4db4  mov     [rbp+4Fh+LockState.Flags], al
0x1401a4db7  mov     rsi, rdx
0x1401a4dba  mov     rdi, rcx
0x1401a4dbd  mov     rcx, cs:VmsIfrLog
0x1401a4dc4  lea     rax, aSecurityBug923; "!\"Security bug 9234257 must be fixed w"...
0x1401a4dcb  mov     [rsp+0C0h+var_98], rax
0x1401a4dd0  lea     r15d, [r12+13h]
0x1401a4dd5  lea     r14, WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids
0x1401a4ddc  mov     r8d, r15d
0x1401a4ddf  mov     r9d, 8Ch
0x1401a4de5  mov     [rsp+0C0h+var_A0], r14
0x1401a4dea  call    WPP_RECORDER_SF_s
0x1401a4def  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "!"Security bug 9234257 must be fixed when this codepath is active"")
0x1401a4df4  cmp     ebx, 8
0x1401a4df7  jnb     short loc_1401A4E36
0x1401a4df9  mov     rcx, cs:VmsIfrLog
0x1401a4e00  lea     rax, aBufsizeTooSmal; "!\"BufSize too small.\""
0x1401a4e07  mov     [rsp+0C0h+var_98], rax
0x1401a4e0c  lea     r9d, [r15+7Ah]
0x1401a4e10  mov     r8d, r15d
0x1401a4e13  mov     [rsp+0C0h+var_A0], r14
0x1401a4e18  call    WPP_RECORDER_SF_s
0x1401a4e1d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "!"BufSize too small."")
0x1401a4e22  mov     rcx, rsi
0x1401a4e25  call    cs:__imp_VmbChannelPacketFail
0x1401a4e2c  nop     dword ptr [rax+rax+00h]
0x1401a4e31  jmp     loc_1401A552A
0x1401a4e36  mov     ebx, 88h
0x1401a4e3b  cmp     [r13+0], ebx
0x1401a4e3f  jz      short loc_1401A4E70
0x1401a4e41  mov     rcx, cs:VmsIfrLog
0x1401a4e48  lea     rax, aMessageHeaderM; "Message->Header.MessageType == NvspMess"...
0x1401a4e4f  mov     [rsp+0C0h+var_98], rax
0x1401a4e54  lea     r9d, [rbx+6]
0x1401a4e58  mov     r8d, r15d
0x1401a4e5b  mov     [rsp+0C0h+var_A0], r14
0x1401a4e60  call    WPP_RECORDER_SF_s
0x1401a4e65  cmp     [r13+0], ebx
0x1401a4e69  jz      short loc_1401A4E70
0x1401a4e6b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Message->Header.MessageType == NvspMessage6TypePdPostBatch")
0x1401a4e70  test    byte ptr [r13+6], 2
0x1401a4e75  jnz     short loc_1401A4EA9
0x1401a4e77  mov     rcx, cs:VmsIfrLog
0x1401a4e7e  lea     rax, aMessageIsrecei; "Message->IsReceive"
0x1401a4e85  mov     [rsp+0C0h+var_98], rax
0x1401a4e8a  mov     r9d, 8Fh
0x1401a4e90  mov     r8d, r15d
0x1401a4e93  mov     [rsp+0C0h+var_A0], r14
0x1401a4e98  call    WPP_RECORDER_SF_s
0x1401a4e9d  test    byte ptr [r13+6], 2
0x1401a4ea2  jnz     short loc_1401A4EA9
0x1401a4ea4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Message->IsReceive")
0x1401a4ea9  mov     rcx, rdi
0x1401a4eac  call    cs:__imp_VmbChannelGetPointer
0x1401a4eb3  nop     dword ptr [rax+rax+00h]
0x1401a4eb8  mov     [rbp+4Fh+var_48], rax
0x1401a4ebc  mov     rsi, rax
0x1401a4ebf  test    rax, rax
0x1401a4ec2  jnz     short loc_1401A4EEF
0x1401a4ec4  mov     rcx, cs:VmsIfrLog
0x1401a4ecb  lea     rax, aChannelinfoNul; "channelInfo != NULL"
0x1401a4ed2  mov     [rsp+0C0h+var_98], rax
0x1401a4ed7  mov     r9d, 90h
0x1401a4edd  mov     r8d, r15d
0x1401a4ee0  mov     [rsp+0C0h+var_A0], r14
0x1401a4ee5  call    WPP_RECORDER_SF_s
0x1401a4eea  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "channelInfo != ((void *)0)")
0x1401a4eef  mov     r15, [rsi+8]
0x1401a4ef3  test    r15, r15
0x1401a4ef6  jnz     short loc_1401A4F24
0x1401a4ef8  mov     rcx, cs:VmsIfrLog
0x1401a4eff  lea     rax, aVmnicextNull_0; "vmNicExt != NULL"
0x1401a4f06  mov     [rsp+0C0h+var_98], rax
0x1401a4f0b  lea     r8d, [r15+13h]
0x1401a4f0f  mov     r9d, 91h
0x1401a4f15  mov     [rsp+0C0h+var_A0], r14
0x1401a4f1a  call    WPP_RECORDER_SF_s
0x1401a4f1f  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "vmNicExt != ((void *)0)")
0x1401a4f24  mov     rdi, [r15+2A8h]
0x1401a4f2b  test    rdi, rdi
0x1401a4f2e  jnz     short loc_1401A4F5C
0x1401a4f30  mov     rcx, cs:VmsIfrLog
0x1401a4f37  lea     rax, aObjnicNull_1; "objNic != NULL"
0x1401a4f3e  mov     [rsp+0C0h+var_98], rax
0x1401a4f43  lea     r8d, [rdi+13h]
0x1401a4f47  mov     r9d, 92h
0x1401a4f4d  mov     [rsp+0C0h+var_A0], r14
0x1401a4f52  call    WPP_RECORDER_SF_s
0x1401a4f57  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "objNic != ((void *)0)")
0x1401a4f5c  cmp     dword ptr [rdi+44h], 1
0x1401a4f60  jnz     loc_1401A54E7
0x1401a4f66  cmp     dword ptr [rdi+758h], 1
0x1401a4f6d  jnz     loc_1401A54E7
0x1401a4f73  mov     r14, [rdi+1010h]
0x1401a4f7a  mov     [rbp+4Fh+arg_18], r12b
0x1401a4f7e  test    r14, r14
0x1401a4f81  jnz     short loc_1401A4FB8
0x1401a4f83  mov     rcx, cs:VmsIfrNicLog
0x1401a4f8a  lea     rax, aEcblockNull; "ecBlock != NULL"
0x1401a4f91  mov     [rsp+0C0h+var_98], rax
0x1401a4f96  lea     rbx, WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids
0x1401a4f9d  mov     r9d, 93h
0x1401a4fa3  mov     [rsp+0C0h+var_A0], rbx
0x1401a4fa8  lea     r8d, [r14+13h]
0x1401a4fac  call    WPP_RECORDER_SF_s
0x1401a4fb1  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ecBlock != ((void *)0)")
0x1401a4fb6  jmp     short loc_1401A4FBF
0x1401a4fb8  lea     rbx, WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids
0x1401a4fbf  cmp     qword ptr [rdi+7C0h], 0
0x1401a4fc7  mov     r12b, [r15+362h]
0x1401a4fce  jnz     short loc_1401A4FFE
0x1401a4fd0  mov     rcx, cs:VmsIfrNicLog
0x1401a4fd7  lea     rax, aObjportNull; "objPort != NULL"
0x1401a4fde  mov     [rsp+0C0h+var_98], rax
0x1401a4fe3  mov     r9d, 94h
0x1401a4fe9  mov     r8d, 13h
0x1401a4fef  mov     [rsp+0C0h+var_A0], rbx
0x1401a4ff4  call    WPP_RECORDER_SF_s
0x1401a4ff9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "objPort != ((void *)0)")
0x1401a4ffe  xor     edx, edx
0x1401a5000  mov     rcx, rdi
0x1401a5003  call    VmsPtGetNicHeaderAtIndex
0x1401a5008  mov     rbx, rax
0x1401a500b  test    rax, rax
0x1401a500e  jz      short loc_1401A502E
0x1401a5010  xor     ecx, ecx; ProcNumber
0x1401a5012  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1401a5019  nop     dword ptr [rax+rax+00h]
0x1401a501e  mov     ecx, eax
0x1401a5020  mov     rax, [rbx+18h]
0x1401a5024  shl     rcx, 6
0x1401a5028  lock inc qword ptr [rcx+rax+8]
0x1401a502e  xor     r8d, r8d
0x1401a5031  lea     rdx, [rbp+4Fh+LockState]
0x1401a5035  mov     rcx, rdi
0x1401a5038  call    VmsOmObjectLockShared
0x1401a503d  mov     rax, [rdi+760h]
0x1401a5044  xor     ebx, ebx
0x1401a5046  mov     [rbp+4Fh+var_38], rax
0x1401a504a  test    rax, rax
0x1401a504d  jz      short loc_1401A505D
0x1401a504f  xor     edx, edx
0x1401a5051  mov     rcx, rax
0x1401a5054  call    VmsOmpObjectReference
0x1401a5059  mov     [rbp+4Fh+arg_18], 1
0x1401a505d  mov     rcx, [rdi+38h]; Lock
0x1401a5061  lea     rdx, [rbp+4Fh+LockState]; LockState
0x1401a5065  call    cs:__imp_NdisReleaseRWLock
0x1401a506c  nop     dword ptr [rax+rax+00h]
0x1401a5071  mov     [rbp+4Fh+var_68], rbx
0x1401a5075  lea     rax, [rbp+4Fh+var_68]
0x1401a5079  mov     [rbp+4Fh+var_60], rax
0x1401a507d  mov     rax, [rsi+58h]
0x1401a5081  mov     [rbp+4Fh+var_74], ebx
0x1401a5084  movzx   ebx, word ptr [r13+4]
0x1401a5089  mov     [rbp+4Fh+var_7C], ebx
0x1401a508c  movzx   ecx, word ptr [rax+0C0h]
0x1401a5093  mov     [rbp+4Fh+arg_10], cx
0x1401a5097  movzx   ecx, word ptr [rax+0C2h]
0x1401a509e  cmp     ebx, ecx
0x1401a50a0  jbe     short loc_1401A50DE
0x1401a50a2  mov     [rsp+0C0h+var_90], ecx
0x1401a50a6  lea     rax, WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids
0x1401a50ad  mov     rcx, cs:VmsIfrLog
0x1401a50b4  mov     r9d, 95h
0x1401a50ba  mov     dword ptr [rsp+0C0h+var_98], ebx
0x1401a50be  mov     r8d, 14h
0x1401a50c4  mov     dl, 2
0x1401a50c6  mov     [rsp+0C0h+var_A0], rax
0x1401a50cb  call    WPP_RECORDER_SF_ld
0x1401a50d0  mov     rax, [rsi+58h]
0x1401a50d4  movzx   ebx, word ptr [rax+0C2h]
0x1401a50db  mov     [rbp+4Fh+var_7C], ebx
0x1401a50de  neg     r12b
0x1401a50e1  mov     [rbp+4Fh+var_80], ebx
0x1401a50e4  lea     rdx, [rbp+4Fh+var_80]
0x1401a50e8  sbb     rcx, rcx
0x1401a50eb  and     ecx, 70h
0x1401a50ee  add     rcx, 1D0h
0x1401a50f5  add     rcx, r14
0x1401a50f8  call    VmsPDPopPDBuffers
0x1401a50fd  mov     rcx, rax
0x1401a5100  mov     [rbp+4Fh+var_70], rax
0x1401a5104  cmp     [rbp+4Fh+var_80], ebx
0x1401a5107  jz      short loc_1401A5142
0x1401a5109  mov     rcx, cs:VmsIfrNicLog
0x1401a5110  lea     rax, aNumberofbuffer; "numberOfBuffers == requestedNumberOfBuf"...
0x1401a5117  mov     [rsp+0C0h+var_98], rax
0x1401a511c  mov     r9d, 96h
0x1401a5122  lea     rax, WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids
0x1401a5129  mov     r8d, 13h
0x1401a512f  mov     [rsp+0C0h+var_A0], rax
0x1401a5134  call    WPP_RECORDER_SF_s
0x1401a5139  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "numberOfBuffers == requestedNumberOfBuffers")
0x1401a513e  mov     rcx, [rbp+4Fh+var_70]
0x1401a5142  xor     r12d, r12d
0x1401a5145  test    ebx, ebx
0x1401a5147  jz      loc_1401A5385
0x1401a514d  mov     r14d, [rbp+4Fh+var_7C]
0x1401a5151  mov     esi, r12d
0x1401a5154  mov     rbx, rcx
0x1401a5157  mov     eax, esi
0x1401a5159  mov     r12, rcx
0x1401a515c  mov     rcx, [rcx]
0x1401a515f  mov     [rbp+4Fh+var_70], rcx
0x1401a5163  lea     rax, ds:8[rax*8]
0x1401a516b  add     rax, r13
0x1401a516e  mov     [rbp+4Fh+var_50], rax
0x1401a5172  xor     eax, eax
0x1401a5174  test    rbx, rbx
0x1401a5177  jnz     short loc_1401A51AE
0x1401a5179  mov     rcx, cs:VmsIfrNicLog
0x1401a5180  lea     rax, aHostpdbufferNu; "hostPdBuffer != NULL"
0x1401a5187  mov     [rsp+0C0h+var_98], rax
0x1401a518c  lea     r8d, [rbx+13h]
0x1401a5190  lea     rax, WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids
0x1401a5197  mov     r9d, 97h
0x1401a519d  mov     [rsp+0C0h+var_A0], rax
0x1401a51a2  call    WPP_RECORDER_SF_s
0x1401a51a7  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "hostPdBuffer != ((void *)0)")
0x1401a51ac  xor     eax, eax
0x1401a51ae  cmp     [rbx+38h], ax
0x1401a51b2  jz      short loc_1401A51F1
0x1401a51b4  mov     rcx, cs:VmsIfrNicLog
0x1401a51bb  lea     rax, aHostpdbufferFl; "hostPdBuffer->Flags == 0"
0x1401a51c2  mov     [rsp+0C0h+var_98], rax
0x1401a51c7  mov     r9d, 98h
0x1401a51cd  lea     rax, WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids
0x1401a51d4  mov     r8d, 13h
0x1401a51da  mov     [rsp+0C0h+var_A0], rax
0x1401a51df  call    WPP_RECORDER_SF_s
0x1401a51e4  xor     eax, eax
0x1401a51e6  cmp     [rbx+38h], ax
0x1401a51ea  jz      short loc_1401A51F1
0x1401a51ec  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "hostPdBuffer->Flags == 0")
0x1401a51f1  mov     rax, [rbx+18h]
0x1401a51f5  test    dword ptr [rax], 400h
0x1401a51fb  jz      short loc_1401A523E
0x1401a51fd  mov     rcx, cs:VmsIfrNicLog
0x1401a5204  lea     rax, aVmsVmpdIsBuffe_0; "VMS_VMPD_IS_BUFFER_BOUND_TO_VM(hostPdBu"...
0x1401a520b  mov     [rsp+0C0h+var_98], rax
0x1401a5210  mov     r9d, 99h
0x1401a5216  lea     rax, WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids
0x1401a521d  mov     r8d, 13h
0x1401a5223  mov     [rsp+0C0h+var_A0], rax
0x1401a5228  call    WPP_RECORDER_SF_s
0x1401a522d  mov     rax, [rbx+18h]
0x1401a5231  test    dword ptr [rax], 400h
0x1401a5237  jz      short loc_1401A523E
0x1401a5239  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "((((PVMS_PD_CONTEXT)((hostPdBuffer)->PDClientContext))->Flags & 0x00000400) == 0x00000400) == 0")
0x1401a523e  xor     ecx, ecx
0x1401a5240  mov     r8, rbx
0x1401a5243  mov     [r12], rcx
0x1401a5247  cmp     [r15+362h], cl
0x1401a524e  jz      short loc_1401A5262
0x1401a5250  mov     r9, [rbp+4Fh+var_50]
0x1401a5254  mov     rcx, r15
0x1401a5257  movzx   edx, [rbp+4Fh+arg_10]
0x1401a525b  call    VmsVmNicPvtShadowByHostPDBuffer
0x1401a5260  jmp     short loc_1401A52B9
0x1401a5262  mov     rdx, [rbp+4Fh+var_50]
0x1401a5266  lea     rax, [rbp+4Fh+var_7C]
0x1401a526a  mov     word ptr [rbp+4Fh+var_80], cx
0x1401a526e  lea     r9, [rbp+4Fh+var_80]
0x1401a5272  mov     [rbp+4Fh+var_7C], ecx
0x1401a5275  mov     rcx, r15
0x1401a5278  mov     [rsp+0C0h+var_A0], rax
0x1401a527d  call    VmsVmNicPvtValidateAndCaptureGuestPDBuffer
0x1401a5282  xor     ecx, ecx
0x1401a5284  test    al, al
0x1401a5286  jnz     short loc_1401A528C
0x1401a5288  mov     al, cl
0x1401a528a  jmp     short loc_1401A52B9
0x1401a528c  movzx   eax, [rbp+4Fh+arg_10]
0x1401a5290  mov     [rbx+3Ch], ecx
0x1401a5293  mov     [r12], rcx
0x1401a5297  mov     rcx, [rbx+18h]
0x1401a529b  or      dword ptr [rcx], 0C00h
0x1401a52a1  mov     [rcx+4Ch], ax
0x1401a52a5  movzx   eax, word ptr [rbp+4Fh+var_80]
0x1401a52a9  mov     [rcx+4Eh], ax
0x1401a52ad  mov     eax, [rbp+4Fh+var_7C]
0x1401a52b0  mov     [rcx+48h], eax
  ... truncated ...
```
