# VmsVmNicPvtVersion6HandleRxPdBatch

- ea: `0x1401a4df0`
- end: `0x1401a55b6`
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
- `0x1401162f8`
- `0x140116480`
- `0x1401a4a5c`
- `0x1401a4b78`
- `0x1401a4df0`
- `0x1401bbe80`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401a5082`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401a5539`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401a5082`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401a5539`
- `NDIS!NdisReleaseRWLock` at `0x1401a50d5`
- `NDIS!NdisReleaseRWLock` at `0x1401a50d5`
- `vmbkmclr!VmbChannelPacketComplete` at `0x1401a558e`
- `vmbkmclr!VmbChannelPacketComplete` at `0x1401a558e`
- `vmbkmclr!VmbChannelPacketFail` at `0x1401a4e95`
- `vmbkmclr!VmbChannelPacketFail` at `0x1401a4e95`
- `vmbkmclr!VmbChannelGetPointer` at `0x1401a4f1c`
- `vmbkmclr!VmbChannelGetPointer` at `0x1401a4f1c`

## string_xrefs

- `0x1401a54db`: `completedPDBuffer == NULL`
- `0x1401a4e34`: `!"Security bug 9234257 must be fixed when this codepath is active"`

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
0x1401a4df0  mov     [rsp-8+arg_0], rbx
0x1401a4df5  mov     [rsp-8+arg_8], rdx
0x1401a4dfa  push    rbp
0x1401a4dfb  push    rsi
0x1401a4dfc  push    rdi
0x1401a4dfd  push    r12
0x1401a4dff  push    r13
0x1401a4e01  push    r14
0x1401a4e03  push    r15
0x1401a4e05  lea     rbp, [rsp-1Fh]
0x1401a4e0a  sub     rsp, 90h
0x1401a4e11  xor     r12d, r12d
0x1401a4e14  mov     ebx, r9d
0x1401a4e17  xor     eax, eax
0x1401a4e19  mov     [rbp+4Fh+var_68], r12
0x1401a4e1d  mov     word ptr [rbp+4Fh+LockState.OldIrql], ax
0x1401a4e21  mov     r13, r8
0x1401a4e24  mov     [rbp+4Fh+LockState.Flags], al
0x1401a4e27  mov     rsi, rdx
0x1401a4e2a  mov     rdi, rcx
0x1401a4e2d  mov     rcx, cs:VmsIfrLog
0x1401a4e34  lea     rax, aSecurityBug923; "!\"Security bug 9234257 must be fixed w"...
0x1401a4e3b  mov     [rsp+0C0h+var_98], rax
0x1401a4e40  lea     r15d, [r12+13h]
0x1401a4e45  lea     r14, WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids
0x1401a4e4c  mov     r8d, r15d
0x1401a4e4f  mov     r9d, 8Ch
0x1401a4e55  mov     [rsp+0C0h+var_A0], r14
0x1401a4e5a  call    WPP_RECORDER_SF_s
0x1401a4e5f  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "!"Security bug 9234257 must be fixed when this codepath is active"")
0x1401a4e64  cmp     ebx, 8
0x1401a4e67  jnb     short loc_1401A4EA6
0x1401a4e69  mov     rcx, cs:VmsIfrLog
0x1401a4e70  lea     rax, aBufsizeTooSmal; "!\"BufSize too small.\""
0x1401a4e77  mov     [rsp+0C0h+var_98], rax
0x1401a4e7c  lea     r9d, [r15+7Ah]
0x1401a4e80  mov     r8d, r15d
0x1401a4e83  mov     [rsp+0C0h+var_A0], r14
0x1401a4e88  call    WPP_RECORDER_SF_s
0x1401a4e8d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "!"BufSize too small."")
0x1401a4e92  mov     rcx, rsi
0x1401a4e95  call    cs:__imp_VmbChannelPacketFail
0x1401a4e9c  nop     dword ptr [rax+rax+00h]
0x1401a4ea1  jmp     loc_1401A559A
0x1401a4ea6  mov     ebx, 88h
0x1401a4eab  cmp     [r13+0], ebx
0x1401a4eaf  jz      short loc_1401A4EE0
0x1401a4eb1  mov     rcx, cs:VmsIfrLog
0x1401a4eb8  lea     rax, aMessageHeaderM; "Message->Header.MessageType == NvspMess"...
0x1401a4ebf  mov     [rsp+0C0h+var_98], rax
0x1401a4ec4  lea     r9d, [rbx+6]
0x1401a4ec8  mov     r8d, r15d
0x1401a4ecb  mov     [rsp+0C0h+var_A0], r14
0x1401a4ed0  call    WPP_RECORDER_SF_s
0x1401a4ed5  cmp     [r13+0], ebx
0x1401a4ed9  jz      short loc_1401A4EE0
0x1401a4edb  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Message->Header.MessageType == NvspMessage6TypePdPostBatch")
0x1401a4ee0  test    byte ptr [r13+6], 2
0x1401a4ee5  jnz     short loc_1401A4F19
0x1401a4ee7  mov     rcx, cs:VmsIfrLog
0x1401a4eee  lea     rax, aMessageIsrecei; "Message->IsReceive"
0x1401a4ef5  mov     [rsp+0C0h+var_98], rax
0x1401a4efa  mov     r9d, 8Fh
0x1401a4f00  mov     r8d, r15d
0x1401a4f03  mov     [rsp+0C0h+var_A0], r14
0x1401a4f08  call    WPP_RECORDER_SF_s
0x1401a4f0d  test    byte ptr [r13+6], 2
0x1401a4f12  jnz     short loc_1401A4F19
0x1401a4f14  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Message->IsReceive")
0x1401a4f19  mov     rcx, rdi
0x1401a4f1c  call    cs:__imp_VmbChannelGetPointer
0x1401a4f23  nop     dword ptr [rax+rax+00h]
0x1401a4f28  mov     [rbp+4Fh+var_48], rax
0x1401a4f2c  mov     rsi, rax
0x1401a4f2f  test    rax, rax
0x1401a4f32  jnz     short loc_1401A4F5F
0x1401a4f34  mov     rcx, cs:VmsIfrLog
0x1401a4f3b  lea     rax, aChannelinfoNul; "channelInfo != NULL"
0x1401a4f42  mov     [rsp+0C0h+var_98], rax
0x1401a4f47  mov     r9d, 90h
0x1401a4f4d  mov     r8d, r15d
0x1401a4f50  mov     [rsp+0C0h+var_A0], r14
0x1401a4f55  call    WPP_RECORDER_SF_s
0x1401a4f5a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "channelInfo != ((void *)0)")
0x1401a4f5f  mov     r15, [rsi+8]
0x1401a4f63  test    r15, r15
0x1401a4f66  jnz     short loc_1401A4F94
0x1401a4f68  mov     rcx, cs:VmsIfrLog
0x1401a4f6f  lea     rax, aVmnicextNull_0; "vmNicExt != NULL"
0x1401a4f76  mov     [rsp+0C0h+var_98], rax
0x1401a4f7b  lea     r8d, [r15+13h]
0x1401a4f7f  mov     r9d, 91h
0x1401a4f85  mov     [rsp+0C0h+var_A0], r14
0x1401a4f8a  call    WPP_RECORDER_SF_s
0x1401a4f8f  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "vmNicExt != ((void *)0)")
0x1401a4f94  mov     rdi, [r15+2A8h]
0x1401a4f9b  test    rdi, rdi
0x1401a4f9e  jnz     short loc_1401A4FCC
0x1401a4fa0  mov     rcx, cs:VmsIfrLog
0x1401a4fa7  lea     rax, aObjnicNull_1; "objNic != NULL"
0x1401a4fae  mov     [rsp+0C0h+var_98], rax
0x1401a4fb3  lea     r8d, [rdi+13h]
0x1401a4fb7  mov     r9d, 92h
0x1401a4fbd  mov     [rsp+0C0h+var_A0], r14
0x1401a4fc2  call    WPP_RECORDER_SF_s
0x1401a4fc7  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "objNic != ((void *)0)")
0x1401a4fcc  cmp     dword ptr [rdi+44h], 1
0x1401a4fd0  jnz     loc_1401A5557
0x1401a4fd6  cmp     dword ptr [rdi+758h], 1
0x1401a4fdd  jnz     loc_1401A5557
0x1401a4fe3  mov     r14, [rdi+1010h]
0x1401a4fea  mov     [rbp+4Fh+arg_18], r12b
0x1401a4fee  test    r14, r14
0x1401a4ff1  jnz     short loc_1401A5028
0x1401a4ff3  mov     rcx, cs:VmsIfrNicLog
0x1401a4ffa  lea     rax, aEcblockNull; "ecBlock != NULL"
0x1401a5001  mov     [rsp+0C0h+var_98], rax
0x1401a5006  lea     rbx, WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids
0x1401a500d  mov     r9d, 93h
0x1401a5013  mov     [rsp+0C0h+var_A0], rbx
0x1401a5018  lea     r8d, [r14+13h]
0x1401a501c  call    WPP_RECORDER_SF_s
0x1401a5021  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ecBlock != ((void *)0)")
0x1401a5026  jmp     short loc_1401A502F
0x1401a5028  lea     rbx, WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids
0x1401a502f  cmp     qword ptr [rdi+7C0h], 0
0x1401a5037  mov     r12b, [r15+362h]
0x1401a503e  jnz     short loc_1401A506E
0x1401a5040  mov     rcx, cs:VmsIfrNicLog
0x1401a5047  lea     rax, aObjportNull; "objPort != NULL"
0x1401a504e  mov     [rsp+0C0h+var_98], rax
0x1401a5053  mov     r9d, 94h
0x1401a5059  mov     r8d, 13h
0x1401a505f  mov     [rsp+0C0h+var_A0], rbx
0x1401a5064  call    WPP_RECORDER_SF_s
0x1401a5069  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "objPort != ((void *)0)")
0x1401a506e  xor     edx, edx
0x1401a5070  mov     rcx, rdi
0x1401a5073  call    VmsPtGetNicHeaderAtIndex
0x1401a5078  mov     rbx, rax
0x1401a507b  test    rax, rax
0x1401a507e  jz      short loc_1401A509E
0x1401a5080  xor     ecx, ecx; ProcNumber
0x1401a5082  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1401a5089  nop     dword ptr [rax+rax+00h]
0x1401a508e  mov     ecx, eax
0x1401a5090  mov     rax, [rbx+18h]
0x1401a5094  shl     rcx, 6
0x1401a5098  lock inc qword ptr [rcx+rax+8]
0x1401a509e  xor     r8d, r8d
0x1401a50a1  lea     rdx, [rbp+4Fh+LockState]
0x1401a50a5  mov     rcx, rdi
0x1401a50a8  call    VmsOmObjectLockShared
0x1401a50ad  mov     rax, [rdi+760h]
0x1401a50b4  xor     ebx, ebx
0x1401a50b6  mov     [rbp+4Fh+var_38], rax
0x1401a50ba  test    rax, rax
0x1401a50bd  jz      short loc_1401A50CD
0x1401a50bf  xor     edx, edx
0x1401a50c1  mov     rcx, rax
0x1401a50c4  call    VmsOmpObjectReference
0x1401a50c9  mov     [rbp+4Fh+arg_18], 1
0x1401a50cd  mov     rcx, [rdi+38h]; Lock
0x1401a50d1  lea     rdx, [rbp+4Fh+LockState]; LockState
0x1401a50d5  call    cs:__imp_NdisReleaseRWLock
0x1401a50dc  nop     dword ptr [rax+rax+00h]
0x1401a50e1  mov     [rbp+4Fh+var_68], rbx
0x1401a50e5  lea     rax, [rbp+4Fh+var_68]
0x1401a50e9  mov     [rbp+4Fh+var_60], rax
0x1401a50ed  mov     rax, [rsi+58h]
0x1401a50f1  mov     [rbp+4Fh+var_74], ebx
0x1401a50f4  movzx   ebx, word ptr [r13+4]
0x1401a50f9  mov     [rbp+4Fh+var_7C], ebx
0x1401a50fc  movzx   ecx, word ptr [rax+0C0h]
0x1401a5103  mov     [rbp+4Fh+arg_10], cx
0x1401a5107  movzx   ecx, word ptr [rax+0C2h]
0x1401a510e  cmp     ebx, ecx
0x1401a5110  jbe     short loc_1401A514E
0x1401a5112  mov     [rsp+0C0h+var_90], ecx
0x1401a5116  lea     rax, WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids
0x1401a511d  mov     rcx, cs:VmsIfrLog
0x1401a5124  mov     r9d, 95h
0x1401a512a  mov     dword ptr [rsp+0C0h+var_98], ebx
0x1401a512e  mov     r8d, 14h
0x1401a5134  mov     dl, 2
0x1401a5136  mov     [rsp+0C0h+var_A0], rax
0x1401a513b  call    WPP_RECORDER_SF_ld
0x1401a5140  mov     rax, [rsi+58h]
0x1401a5144  movzx   ebx, word ptr [rax+0C2h]
0x1401a514b  mov     [rbp+4Fh+var_7C], ebx
0x1401a514e  neg     r12b
0x1401a5151  mov     [rbp+4Fh+var_80], ebx
0x1401a5154  lea     rdx, [rbp+4Fh+var_80]
0x1401a5158  sbb     rcx, rcx
0x1401a515b  and     ecx, 70h
0x1401a515e  add     rcx, 1D0h
0x1401a5165  add     rcx, r14
0x1401a5168  call    VmsPDPopPDBuffers
0x1401a516d  mov     rcx, rax
0x1401a5170  mov     [rbp+4Fh+var_70], rax
0x1401a5174  cmp     [rbp+4Fh+var_80], ebx
0x1401a5177  jz      short loc_1401A51B2
0x1401a5179  mov     rcx, cs:VmsIfrNicLog
0x1401a5180  lea     rax, aNumberofbuffer; "numberOfBuffers == requestedNumberOfBuf"...
0x1401a5187  mov     [rsp+0C0h+var_98], rax
0x1401a518c  mov     r9d, 96h
0x1401a5192  lea     rax, WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids
0x1401a5199  mov     r8d, 13h
0x1401a519f  mov     [rsp+0C0h+var_A0], rax
0x1401a51a4  call    WPP_RECORDER_SF_s
0x1401a51a9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "numberOfBuffers == requestedNumberOfBuffers")
0x1401a51ae  mov     rcx, [rbp+4Fh+var_70]
0x1401a51b2  xor     r12d, r12d
0x1401a51b5  test    ebx, ebx
0x1401a51b7  jz      loc_1401A53F5
0x1401a51bd  mov     r14d, [rbp+4Fh+var_7C]
0x1401a51c1  mov     esi, r12d
0x1401a51c4  mov     rbx, rcx
0x1401a51c7  mov     eax, esi
0x1401a51c9  mov     r12, rcx
0x1401a51cc  mov     rcx, [rcx]
0x1401a51cf  mov     [rbp+4Fh+var_70], rcx
0x1401a51d3  lea     rax, ds:8[rax*8]
0x1401a51db  add     rax, r13
0x1401a51de  mov     [rbp+4Fh+var_50], rax
0x1401a51e2  xor     eax, eax
0x1401a51e4  test    rbx, rbx
0x1401a51e7  jnz     short loc_1401A521E
0x1401a51e9  mov     rcx, cs:VmsIfrNicLog
0x1401a51f0  lea     rax, aHostpdbufferNu; "hostPdBuffer != NULL"
0x1401a51f7  mov     [rsp+0C0h+var_98], rax
0x1401a51fc  lea     r8d, [rbx+13h]
0x1401a5200  lea     rax, WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids
0x1401a5207  mov     r9d, 97h
0x1401a520d  mov     [rsp+0C0h+var_A0], rax
0x1401a5212  call    WPP_RECORDER_SF_s
0x1401a5217  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "hostPdBuffer != ((void *)0)")
0x1401a521c  xor     eax, eax
0x1401a521e  cmp     [rbx+38h], ax
0x1401a5222  jz      short loc_1401A5261
0x1401a5224  mov     rcx, cs:VmsIfrNicLog
0x1401a522b  lea     rax, aHostpdbufferFl; "hostPdBuffer->Flags == 0"
0x1401a5232  mov     [rsp+0C0h+var_98], rax
0x1401a5237  mov     r9d, 98h
0x1401a523d  lea     rax, WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids
0x1401a5244  mov     r8d, 13h
0x1401a524a  mov     [rsp+0C0h+var_A0], rax
0x1401a524f  call    WPP_RECORDER_SF_s
0x1401a5254  xor     eax, eax
0x1401a5256  cmp     [rbx+38h], ax
0x1401a525a  jz      short loc_1401A5261
0x1401a525c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "hostPdBuffer->Flags == 0")
0x1401a5261  mov     rax, [rbx+18h]
0x1401a5265  test    dword ptr [rax], 400h
0x1401a526b  jz      short loc_1401A52AE
0x1401a526d  mov     rcx, cs:VmsIfrNicLog
0x1401a5274  lea     rax, aVmsVmpdIsBuffe_0; "VMS_VMPD_IS_BUFFER_BOUND_TO_VM(hostPdBu"...
0x1401a527b  mov     [rsp+0C0h+var_98], rax
0x1401a5280  mov     r9d, 99h
0x1401a5286  lea     rax, WPP_7e0688d80965326dc40524fca8c77d9d_Traceguids
0x1401a528d  mov     r8d, 13h
0x1401a5293  mov     [rsp+0C0h+var_A0], rax
0x1401a5298  call    WPP_RECORDER_SF_s
0x1401a529d  mov     rax, [rbx+18h]
0x1401a52a1  test    dword ptr [rax], 400h
0x1401a52a7  jz      short loc_1401A52AE
0x1401a52a9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "((((PVMS_PD_CONTEXT)((hostPdBuffer)->PDClientContext))->Flags & 0x00000400) == 0x00000400) == 0")
0x1401a52ae  xor     ecx, ecx
0x1401a52b0  mov     r8, rbx
0x1401a52b3  mov     [r12], rcx
0x1401a52b7  cmp     [r15+362h], cl
0x1401a52be  jz      short loc_1401A52D2
0x1401a52c0  mov     r9, [rbp+4Fh+var_50]
0x1401a52c4  mov     rcx, r15
0x1401a52c7  movzx   edx, [rbp+4Fh+arg_10]
0x1401a52cb  call    VmsVmNicPvtShadowByHostPDBuffer
0x1401a52d0  jmp     short loc_1401A5329
0x1401a52d2  mov     rdx, [rbp+4Fh+var_50]
0x1401a52d6  lea     rax, [rbp+4Fh+var_7C]
0x1401a52da  mov     word ptr [rbp+4Fh+var_80], cx
0x1401a52de  lea     r9, [rbp+4Fh+var_80]
0x1401a52e2  mov     [rbp+4Fh+var_7C], ecx
0x1401a52e5  mov     rcx, r15
0x1401a52e8  mov     [rsp+0C0h+var_A0], rax
0x1401a52ed  call    VmsVmNicPvtValidateAndCaptureGuestPDBuffer
0x1401a52f2  xor     ecx, ecx
0x1401a52f4  test    al, al
0x1401a52f6  jnz     short loc_1401A52FC
0x1401a52f8  mov     al, cl
0x1401a52fa  jmp     short loc_1401A5329
0x1401a52fc  movzx   eax, [rbp+4Fh+arg_10]
0x1401a5300  mov     [rbx+3Ch], ecx
0x1401a5303  mov     [r12], rcx
0x1401a5307  mov     rcx, [rbx+18h]
0x1401a530b  or      dword ptr [rcx], 0C00h
0x1401a5311  mov     [rcx+4Ch], ax
0x1401a5315  movzx   eax, word ptr [rbp+4Fh+var_80]
0x1401a5319  mov     [rcx+4Eh], ax
0x1401a531d  mov     eax, [rbp+4Fh+var_7C]
0x1401a5320  mov     [rcx+48h], eax
  ... truncated ...
```
