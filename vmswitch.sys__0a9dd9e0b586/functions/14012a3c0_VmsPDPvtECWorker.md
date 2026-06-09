# VmsPDPvtECWorker

- ea: `0x14012a3c0`
- end: `0x14012ae4a`
- name: `VmsPDPvtECWorker`
- size: `2698`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140027a64`
- `0x14003a450`
- `0x14003c378`
- `0x140046e5c`
- `0x140046f1c`
- `0x14008497c`
- `0x14009e3a8`
- `0x1400ecca8`
- `0x1400ecd9c`
- `0x1400ece00`
- `0x1400ecef4`
- `0x1401167a4`
- `0x1401288b0`
- `0x140128d94`
- `0x140129610`
- `0x14012a3c0`
- `0x1401a5c80`
- `0x1401a6290`
- `0x1401a68b0`
- `0x1401b95bc`
- `0x1401bbe80`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x14012acd2`
- `ntoskrnl!KeClearEvent` at `0x14012acd2`
- `ntoskrnl!PsTerminateSystemThread` at `0x14012ae29`
- `ntoskrnl!PsTerminateSystemThread` at `0x14012ae29`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14012a844`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14012a844`
- `ntoskrnl!KeWaitForSingleObject` at `0x14012ad97`
- `ntoskrnl!KeWaitForSingleObject` at `0x14012ad97`
- `NDIS!NdisReleaseRWLock` at `0x14012a55d`
- `NDIS!NdisReleaseRWLock` at `0x14012a55d`
- `NDIS!NdisAcquireRWLockWrite` at `0x14012a507`
- `NDIS!NdisAcquireRWLockWrite` at `0x14012a507`
- `vmbkmclr!VmbChannelPollRingBuffer` at `0x14012aa55`
- `vmbkmclr!VmbChannelPollRingBuffer` at `0x14012aa55`
- `vmbkmclr!VmbChannelSetPollingMode` at `0x14012aa13`
- `vmbkmclr!VmbChannelSetPollingMode` at `0x14012aa6e`
- `vmbkmclr!VmbChannelSetPollingMode` at `0x14012aa13`
- `vmbkmclr!VmbChannelSetPollingMode` at `0x14012aa6e`

## pseudocode

```c
void __fastcall VmsPDPvtECWorker(char *StartContext, int a2)
{
  char v2; // r12
  _QWORD *v3; // r15
  char v4; // r13
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r14
  char v9; // al
  __int64 v10; // r13
  unsigned int m; // r12d
  char *v12; // r15
  char *v13; // r14
  __int64 v14; // rdi
  __int64 v15; // r8
  int v16; // edx
  char *j; // rdi
  bool v18; // zf
  char *k; // rdi
  char *i; // rdi
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // edx
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r8
  unsigned int v29; // edi
  char *n; // rsi
  char *v31; // rdi
  __int64 v32; // rcx
  char *ii; // rdi
  __int64 v34; // r15
  int v35; // edx
  int v36; // eax
  char *jj; // rdi
  char *kk; // rdi
  char *mm; // rdi
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp-39h] BYREF
  int v41; // [rsp+44h] [rbp-35h]
  __int64 v42; // [rsp+48h] [rbp-31h] BYREF
  __int64 v43; // [rsp+50h] [rbp-29h] BYREF
  __int64 *v44; // [rsp+58h] [rbp-21h] BYREF
  __int64 *v45; // [rsp+60h] [rbp-19h] BYREF
  __int128 v46; // [rsp+68h] [rbp-11h] BYREF
  __int128 v47; // [rsp+78h] [rbp-1h]
  char v48; // [rsp+E0h] [rbp+67h]
  char v49; // [rsp+E8h] [rbp+6Fh]
  char v50; // [rsp+F0h] [rbp+77h] BYREF
  char v51; // [rsp+F8h] [rbp+7Fh]

  v2 = 0;
  v41 = 12;
  v50 = 0;
  v44 = &v43;
  v43 = 0;
  v3 = StartContext + 80;
  v42 = 0;
  v4 = 1;
  v45 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v48 = 1;
  v51 = 0;
  v46 = 0;
  v47 = 0;
  if ( *((_QWORD *)StartContext + 10) )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      a2,
      19,
      27,
      (__int64)WPP_ceb7cce27bd838a468dd456680e4ae98_Traceguids,
      (__int64)"ecBlock->EcHandle == NULL");
    if ( *v3 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  *((_QWORD *)StartContext + 107) = KeGetCurrentThread();
  while ( 1 )
  {
    (*(void (__fastcall **)(_QWORD, __int64 **, __int64, char *))(VmsPDPlatformDispatch + 24))(
      *((_QWORD *)StartContext + 8),
      &v44,
      0xFFFFFFFFLL,
      &v50);
    v8 = v43;
    if ( v43 )
    {
      while ( 1 )
      {
        v43 = *(_QWORD *)v8;
        v16 = *(_DWORD *)(v8 + 8);
        if ( v16 > 6 )
        {
          switch ( v16 )
          {
            case 7:
              break;
            case 8:
              VmsVmPDCreateQueue((__int64)StartContext, v8, v7);
              break;
            case 9:
              VmsVmPDFlushQueue(StartContext, v8);
              break;
            case 10:
              VmsVmPDDeleteQueue((__int64)StartContext, v8);
              break;
            default:
LABEL_69:
              LOBYTE(v16) = 2;
              WPP_RECORDER_SF_d(
                VmsIfrLog,
                v16,
                20,
                31,
                (__int64)WPP_ceb7cce27bd838a468dd456680e4ae98_Traceguids,
                *(_DWORD *)(v8 + 8));
              break;
          }
        }
        else
        {
          switch ( v16 )
          {
            case 6:
              break;
            case 1:
              v23 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(VmsPDPlatformDispatch + 96))(VmsPDClientHandle, v3);
              *(_DWORD *)(v8 + 16) = v23;
              if ( v23 < 0 )
              {
                LOBYTE(v24) = 2;
                WPP_RECORDER_SF_id(
                  VmsIfrLog,
                  v24,
                  20,
                  28,
                  (__int64)WPP_ceb7cce27bd838a468dd456680e4ae98_Traceguids,
                  VmsPDClientHandle,
                  v23);
                v25 = 3;
              }
              else
              {
                ++*((_DWORD *)StartContext + 114);
                v25 = 2;
              }
              *((_DWORD *)StartContext + 111) = v25;
              break;
            case 2:
              if ( !*((_DWORD *)StartContext + 114) )
              {
                WPP_RECORDER_SF_s(
                  VmsIfrLog,
                  v16,
                  19,
                  29,
                  (__int64)WPP_ceb7cce27bd838a468dd456680e4ae98_Traceguids,
                  (__int64)"ecBlock->PauseCount > 0");
                if ( !*((_DWORD *)StartContext + 114) )
                  MicrosoftTelemetryAssertTriggeredNoArgsKM();
              }
              v21 = *((_DWORD *)StartContext + 114);
              if ( !v21 || (v22 = v21 - 1, (*((_DWORD *)StartContext + 114) = v22) == 0) )
                *((_DWORD *)StartContext + 111) = 1;
              break;
            case 3:
              if ( *((_DWORD *)StartContext + 111) != 2 )
              {
                for ( i = (char *)*((_QWORD *)StartContext + 11); i != StartContext + 88; i = *(char **)i )
                  VmsPDDrainQueue(i);
              }
              ++*((_DWORD *)StartContext + 114);
              *((_DWORD *)StartContext + 111) = 2;
              break;
            case 4:
              if ( *(_QWORD *)v8 )
              {
                WPP_RECORDER_SF_s(
                  VmsIfrLog,
                  v16,
                  19,
                  30,
                  (__int64)WPP_ceb7cce27bd838a468dd456680e4ae98_Traceguids,
                  (__int64)"cmd->ListEntry.Next == NULL");
                if ( *(_QWORD *)v8 )
                  MicrosoftTelemetryAssertTriggeredNoArgsKM();
              }
              *((_DWORD *)StartContext + 111) = 3;
              break;
            case 5:
              v4 = 1;
              for ( j = (char *)*((_QWORD *)StartContext + 13); j != StartContext + 104; j = *(char **)j )
              {
                if ( (unsigned __int8)VmsPDConfigureAwmOnQueue(j) )
                {
                  v18 = v4 == 0;
                  v4 = 1;
                  if ( !v18 )
                    continue;
                }
                v4 = 0;
              }
              for ( k = (char *)*((_QWORD *)StartContext + 11); k != StartContext + 88; k = *(char **)k )
              {
                if ( (unsigned __int8)VmsPDConfigureAwmOnQueue(k) )
                {
                  v18 = v4 == 0;
                  v4 = 1;
                  if ( !v18 )
                    continue;
                }
                v4 = 0;
              }
              v51 = 0;
              break;
            default:
              goto LABEL_69;
          }
        }
        v26 = *((_QWORD *)StartContext + 56);
        v27 = v26 + 9008;
        switch ( *(_DWORD *)(v8 + 8) )
        {
          case 2:
            if ( *(_DWORD *)(v26 + 9036) )
            {
LABEL_80:
              if ( !*(_BYTE *)(v26 + 9088) )
              {
                *(_BYTE *)(v26 + 9088) = 1;
                PktCapReference(v26 + 9008);
              }
            }
            break;
          case 4:
            goto LABEL_174;
          case 6:
            goto LABEL_80;
          case 7:
LABEL_174:
            if ( *(_BYTE *)(v26 + 9088) )
            {
              *(_BYTE *)(v26 + 9088) = 0;
              ExReleaseRundownProtection((PEX_RUNDOWN_REF)(v26 + 9016));
            }
            break;
        }
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(VmsPDPlatformDispatch + 32))(
          *((_QWORD *)StartContext + 8),
          1,
          v27);
        v8 = v43;
        if ( !v43 )
        {
          v9 = v50;
          v48 = v4;
          goto LABEL_84;
        }
      }
    }
    v9 = v50;
    v49 = 1;
    if ( v50 )
      break;
    v2 = 1;
LABEL_9:
    if ( *((_DWORD *)StartContext + 111) != 1 )
      goto LABEL_147;
    v10 = 0;
    for ( m = 0; (int)m < 7; ++m )
    {
      v12 = &StartContext[40 * m + 152];
      v13 = &StartContext[40 * m + 168];
      if ( *(_QWORD *)v12 || *(_QWORD *)v13 )
      {
        v49 = 0;
        v14 = 0;
        NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)&StartContext[40 * m + 144], &LockState, 0);
        if ( *(_QWORD *)&StartContext[40 * m + 152] )
        {
          v14 = *(_QWORD *)&StartContext[40 * m + 152];
          *(_QWORD *)&StartContext[40 * m + 152] = 0;
          *(_QWORD *)&StartContext[40 * m + 160] = v12;
        }
        if ( *(_QWORD *)v13 )
        {
          v10 = *(_QWORD *)v13;
          *(_QWORD *)v13 = 0;
          *(_QWORD *)&StartContext[40 * m + 176] = v13;
        }
        NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)&StartContext[40 * m + 144], &LockState);
        if ( v14 )
        {
          if ( m )
          {
            if ( m == 1 )
            {
              VmsExtMpProcessPDIngressInjection(*((_QWORD *)StartContext + 56), v14);
            }
            else if ( m == 2 )
            {
              VmsExtMpProcessPDEgressInjection(*((_QWORD *)StartContext + 56), v14);
            }
            else
            {
              switch ( m )
              {
                case 3u:
                  v28 = 4096;
                  break;
                case 4u:
                  v15 = 4096;
LABEL_91:
                  VmsExtMpProcessPDEgressTestInjection(*((_QWORD *)StartContext + 56), v14, v15);
                  goto LABEL_97;
                case 5u:
                  v28 = 0x2000;
                  break;
                case 6u:
                  v15 = 0x2000;
                  goto LABEL_91;
                default:
                  goto LABEL_97;
              }
              VmsExtMpProcessPDIngressTestInjection(*((_QWORD *)StartContext + 56), v14, v28);
            }
          }
          else
          {
            VmsExtPtRoutePDBuffers(*(_QWORD *)(*(_QWORD *)(v14 + 24) + 8LL), v6, v14, 0);
          }
        }
LABEL_97:
        if ( !v10 )
        {
LABEL_115:
          v10 = 0;
          continue;
        }
        if ( m )
        {
          switch ( m )
          {
            case 1u:
              v29 = 3;
              break;
            case 2u:
              v29 = 7;
              break;
            case 3u:
              v29 = 2;
              break;
            case 4u:
              v29 = 8;
              break;
            case 5u:
              v29 = 4;
              break;
            case 6u:
              v29 = 6;
              break;
            default:
              v29 = v41;
              goto LABEL_114;
          }
        }
        else
        {
          v29 = 0;
        }
        v41 = v29;
LABEL_114:
        VmsPDReturnPDBuffers(*((_QWORD *)StartContext + 56), v10, v29);
        goto LABEL_115;
      }
    }
    for ( n = (char *)*((_QWORD *)StartContext + 15); n != StartContext + 120; n = *(char **)n )
    {
      v31 = n - 56;
      if ( n[24] )
      {
        LOBYTE(v6) = 1;
        v49 = 0;
        VmbChannelSetPollingMode(*(_QWORD *)v31, v6);
        if ( BYTE1(WPP_GLOBAL_Control->Timer) > 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_I(
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            22,
            33,
            (__int64)WPP_ceb7cce27bd838a468dd456680e4ae98_Traceguids,
            (_BYTE)n - 56);
        if ( !(unsigned __int8)VmbChannelPollRingBuffer(*(_QWORD *)v31) )
        {
          v32 = *(_QWORD *)v31;
          v31[80] = 0;
          VmbChannelSetPollingMode(v32, 0);
        }
      }
    }
    v2 = v49;
    for ( ii = (char *)*((_QWORD *)StartContext + 13); ii != StartContext + 104; ii = *(char **)ii )
    {
      v34 = *((_QWORD *)ii + 14);
      v45 = &v42;
      v42 = 0;
      if ( ii[200] )
      {
        (*(void (__fastcall **)(_QWORD, char *, __int64 **, __int64))(*(_QWORD *)(*((_QWORD *)ii + 5) + 8LL) + 8LL))(
          *((_QWORD *)ii + 5),
          ii + 208,
          &v45,
          64);
        if ( !*((_QWORD *)ii + 26) )
          *((_QWORD *)ii + 27) = ii + 208;
      }
      else
      {
        if ( (unsigned int)(*((_DWORD *)StartContext + 144) - *((_DWORD *)StartContext + 154)) < *((_DWORD *)ii + 33)
          && (int)VmsPDAllocateBufferSet(StartContext + 576) < 0 )
        {
          LOBYTE(v35) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v35,
            12,
            34,
            (__int64)WPP_ceb7cce27bd838a468dd456680e4ae98_Traceguids);
        }
        *(_QWORD *)&v46 = *((_QWORD *)StartContext + 76);
        *((_QWORD *)&v46 + 1) = &v42;
        LODWORD(v47) = 64;
        (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)(*((_QWORD *)ii + 5) + 8LL) + 32LL))(
          *((_QWORD *)ii + 5),
          &v46);
        *((_QWORD *)StartContext + 76) = v46;
        v36 = DWORD2(v47);
        *((_DWORD *)StartContext + 154) += DWORD2(v47);
        *((_DWORD *)ii + 40) += v36;
      }
      if ( DWORD1(v47) )
      {
        *((_DWORD *)ii + 40) -= DWORD1(v47);
        v2 = 0;
        VmsExtPtRoutePDBuffers(*(_QWORD *)(v34 + 96), v6, v42, DWORD1(v47));
      }
    }
    for ( jj = (char *)*((_QWORD *)StartContext + 11); jj != StartContext + 88; jj = *(char **)jj )
    {
      if ( *((_DWORD *)jj + 40) )
      {
        v42 = 0;
        *((_QWORD *)&v46 + 1) = &v42;
        *(_QWORD *)&v46 = 0;
        LODWORD(v47) = -1;
        (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)(*((_QWORD *)jj + 5) + 8LL) + 32LL))(
          *((_QWORD *)jj + 5),
          &v46);
        if ( DWORD1(v47) )
        {
          *((_DWORD *)jj + 40) -= DWORD1(v47);
          v2 = 0;
          if ( BYTE1(WPP_GLOBAL_Control->Timer) > 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
            WPP_RECORDER_SF_I(
              WPP_GLOBAL_Control->DeviceExtension,
              0,
              22,
              35,
              (__int64)WPP_ceb7cce27bd838a468dd456680e4ae98_Traceguids,
              *((_QWORD *)jj + 5));
          VmsPDReturnPDBuffers(*(_QWORD *)(*((_QWORD *)jj + 15) + 1888LL), v42, 10);
        }
      }
    }
    v4 = v48;
    v3 = StartContext + 80;
LABEL_147:
    if ( v4 && *((_DWORD *)StartContext + 111) == 1 )
    {
      if ( v51 )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) > 4u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_I(
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            24,
            37,
            (__int64)WPP_ceb7cce27bd838a468dd456680e4ae98_Traceguids,
            (char)StartContext);
        KeWaitForSingleObject(StartContext + 16, Executive, 0, 0, 0);
        v51 = 0;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) > 4u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_I(
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            24,
            38,
            (__int64)WPP_ceb7cce27bd838a468dd456680e4ae98_Traceguids,
            (char)StartContext);
      }
      else if ( v2 )
      {
        v51 = 1;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) > 4u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_I(
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            24,
            36,
            (__int64)WPP_ceb7cce27bd838a468dd456680e4ae98_Traceguids,
            (char)StartContext);
        KeClearEvent((PRKEVENT)(StartContext + 16));
        (*(void (__fastcall **)(_QWORD))(VmsPDPlatformDispatch + 56))(*((_QWORD *)StartContext + 8));
        for ( kk = (char *)*((_QWORD *)StartContext + 13); kk != StartContext + 104; kk = *(char **)kk )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(*((_QWORD *)kk + 14) + 32LL) + 80LL))(*((_QWORD *)kk + 5));
        for ( mm = (char *)*((_QWORD *)StartContext + 11); mm != StartContext + 88; mm = *(char **)mm )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(*((_QWORD *)mm + 14) + 32LL) + 80LL))(*((_QWORD *)mm + 5));
      }
    }
    if ( *v3 )
    {
      LOBYTE(v6) = v2;
      (*(void (__fastcall **)(_QWORD, __int64))(VmsPDPlatformDispatch + 112))(*v3, v6);
    }
    v2 = 0;
  }
LABEL_84:
  if ( v9 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v6,
      19,
      32,
      (__int64)WPP_ceb7cce27bd838a468dd456680e4ae98_Traceguids,
      (__int64)"!cmdQFlushed");
    if ( v50 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( *((_DWORD *)StartContext + 111) != 3 )
  {
    v49 = 0;
    v44 = &v43;
    goto LABEL_9;
  }
  if ( *v3 )
  {
    (*(void (**)(void))(VmsPDPlatformDispatch + 104))();
    *v3 = 0;
  }
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x14012a3c0  push    rbp
0x14012a3c2  push    rbx
0x14012a3c3  push    rsi
0x14012a3c4  push    rdi
0x14012a3c5  push    r12
0x14012a3c7  push    r13
0x14012a3c9  push    r14
0x14012a3cb  push    r15
0x14012a3cd  lea     rbp, [rsp-1Fh]
0x14012a3d2  sub     rsp, 98h
0x14012a3d9  xor     r12d, r12d
0x14012a3dc  mov     [rbp+57h+var_8C], 0Ch
0x14012a3e3  lea     rax, [rbp+57h+var_80]
0x14012a3e7  mov     [rbp+57h+arg_10], r12b
0x14012a3eb  xorps   xmm0, xmm0
0x14012a3ee  mov     [rbp+57h+var_78], rax
0x14012a3f2  xor     eax, eax
0x14012a3f4  mov     [rbp+57h+var_80], r12
0x14012a3f8  lea     r15, [rcx+50h]
0x14012a3fc  mov     [rbp+57h+var_88], r12
0x14012a400  lea     rdi, WPP_ceb7cce27bd838a468dd456680e4ae98_Traceguids
0x14012a407  mov     r13b, 1
0x14012a40a  mov     rbx, rcx
0x14012a40d  mov     [rbp+57h+var_70], r12
0x14012a411  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x14012a415  mov     [rbp+57h+LockState.Flags], al
0x14012a418  mov     [rbp+57h+arg_0], r13b
0x14012a41c  mov     [rbp+57h+arg_18], r12b
0x14012a420  movups  [rbp+57h+var_68], xmm0
0x14012a424  movups  [rbp+57h+var_58], xmm0
0x14012a428  cmp     [r15], r12
0x14012a42b  jz      short loc_14012A45E
0x14012a42d  mov     rcx, cs:VmsIfrLog
0x14012a434  lea     rax, aEcblockEchandl_0; "ecBlock->EcHandle == NULL"
0x14012a43b  mov     [rsp+0D0h+var_A8], rax
0x14012a440  lea     r9d, [r12+1Bh]
0x14012a445  lea     r8d, [r12+13h]
0x14012a44a  mov     [rsp+0D0h+Timeout], rdi
0x14012a44f  call    WPP_RECORDER_SF_s
0x14012a454  cmp     [r15], r12
0x14012a457  jz      short loc_14012A45E
0x14012a459  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ecBlock->EcHandle == ((void *)0)")
0x14012a45e  mov     rax, gs:188h
0x14012a467  mov     [rbx+358h], rax
0x14012a46e  jmp     short loc_14012A473
0x14012a470  xor     r12d, r12d
0x14012a473  mov     rax, cs:VmsPDPlatformDispatch
0x14012a47a  lea     r9, [rbp+57h+arg_10]
0x14012a47e  mov     rcx, [rbx+40h]
0x14012a482  lea     rdx, [rbp+57h+var_78]
0x14012a486  or      r8d, 0FFFFFFFFh
0x14012a48a  mov     rax, [rax+18h]
0x14012a48e  call    _guard_dispatch_icall
0x14012a493  mov     r14, [rbp+57h+var_80]
0x14012a497  test    r14, r14
0x14012a49a  jnz     loc_14012A5BF
0x14012a4a0  mov     al, [rbp+57h+arg_10]
0x14012a4a3  mov     [rbp+57h+arg_8], 1
0x14012a4a7  test    al, al
0x14012a4a9  jnz     loc_14012A8AB
0x14012a4af  mov     r12b, [rbp+57h+arg_8]
0x14012a4b3  cmp     dword ptr [rbx+1BCh], 1
0x14012a4ba  jnz     loc_14012AC64
0x14012a4c0  xor     r13d, r13d
0x14012a4c3  mov     r12d, r13d
0x14012a4c6  mov     eax, r12d
0x14012a4c9  lea     r15, [rbx+98h]
0x14012a4d0  lea     r14, [rbx+0A8h]
0x14012a4d7  lea     rsi, [rax+rax*4]
0x14012a4db  lea     r15, [r15+rsi*8]
0x14012a4df  lea     r14, [r14+rsi*8]
0x14012a4e3  cmp     [r15], r13
0x14012a4e6  jnz     short loc_14012A4F1
0x14012a4e8  cmp     [r14], r13
0x14012a4eb  jz      loc_14012A9DC
0x14012a4f1  mov     rcx, [rbx+rsi*8+90h]; Lock
0x14012a4f9  lea     rdx, [rbp+57h+LockState]; LockState
0x14012a4fd  xor     r8d, r8d; Flags
0x14012a500  mov     [rbp+57h+arg_8], 0
0x14012a504  mov     rdi, r13
0x14012a507  call    cs:__imp_NdisAcquireRWLockWrite
0x14012a50e  nop     dword ptr [rax+rax+00h]
0x14012a513  mov     rax, [rbx+rsi*8+98h]
0x14012a51b  test    rax, rax
0x14012a51e  jz      short loc_14012A537
0x14012a520  mov     rdi, rax
0x14012a523  mov     qword ptr [rbx+rsi*8+98h], 0
0x14012a52f  mov     [rbx+rsi*8+0A0h], r15
0x14012a537  mov     rax, [r14]
0x14012a53a  test    rax, rax
0x14012a53d  jz      short loc_14012A551
0x14012a53f  mov     r13, rax
0x14012a542  mov     qword ptr [r14], 0
0x14012a549  mov     [rbx+rsi*8+0B0h], r14
0x14012a551  mov     rcx, [rbx+rsi*8+90h]; Lock
0x14012a559  lea     rdx, [rbp+57h+LockState]; LockState
0x14012a55d  call    cs:__imp_NdisReleaseRWLock
0x14012a564  nop     dword ptr [rax+rax+00h]
0x14012a569  test    rdi, rdi
0x14012a56c  jz      loc_14012A96A
0x14012a572  mov     ecx, r12d
0x14012a575  test    r12d, r12d
0x14012a578  jz      loc_14012A957
0x14012a57e  sub     ecx, 1
0x14012a581  jz      loc_14012A946
0x14012a587  sub     ecx, 1
0x14012a58a  jz      loc_14012A935
0x14012a590  sub     ecx, 1
0x14012a593  jz      loc_14012A91E
0x14012a599  sub     ecx, 1
0x14012a59c  jz      loc_14012A907
0x14012a5a2  sub     ecx, 1
0x14012a5a5  jz      loc_14012A8FF
0x14012a5ab  cmp     ecx, 1
0x14012a5ae  jnz     loc_14012A96A
0x14012a5b4  mov     r8d, 2000h
0x14012a5ba  jmp     loc_14012A90D
0x14012a5bf  mov     rax, [r14]
0x14012a5c2  mov     [rbp+57h+var_80], rax
0x14012a5c6  mov     edx, [r14+8]
0x14012a5ca  cmp     edx, 6
0x14012a5cd  jg      loc_14012A7AC
0x14012a5d3  jz      loc_14012A80A
0x14012a5d9  mov     ecx, edx
0x14012a5db  sub     ecx, 1
0x14012a5de  jz      loc_14012A743
0x14012a5e4  sub     ecx, 1
0x14012a5e7  jz      loc_14012A6DC
0x14012a5ed  sub     ecx, 1
0x14012a5f0  jz      loc_14012A6A5
0x14012a5f6  sub     ecx, 1
0x14012a5f9  jz      short loc_14012A660
0x14012a5fb  cmp     ecx, 1
0x14012a5fe  jnz     loc_14012A7C2
0x14012a604  lea     rsi, [rbx+68h]
0x14012a608  mov     r13b, cl
0x14012a60b  mov     rdi, [rsi]
0x14012a60e  jmp     short loc_14012A62A
0x14012a610  mov     rcx, rdi
0x14012a613  call    VmsPDConfigureAwmOnQueue
0x14012a618  test    al, al
0x14012a61a  jz      short loc_14012A624
0x14012a61c  test    r13b, r13b
0x14012a61f  mov     r13b, 1
0x14012a622  jnz     short loc_14012A627
0x14012a624  mov     r13b, r12b
0x14012a627  mov     rdi, [rdi]
0x14012a62a  cmp     rdi, rsi
0x14012a62d  jnz     short loc_14012A610
0x14012a62f  lea     rsi, [rbx+58h]
0x14012a633  mov     rdi, [rsi]
0x14012a636  jmp     short loc_14012A652
0x14012a638  mov     rcx, rdi
0x14012a63b  call    VmsPDConfigureAwmOnQueue
0x14012a640  test    al, al
0x14012a642  jz      short loc_14012A64C
0x14012a644  test    r13b, r13b
0x14012a647  mov     r13b, 1
0x14012a64a  jnz     short loc_14012A64F
0x14012a64c  mov     r13b, r12b
0x14012a64f  mov     rdi, [rdi]
0x14012a652  cmp     rdi, rsi
0x14012a655  jnz     short loc_14012A638
0x14012a657  mov     [rbp+57h+arg_18], r12b
0x14012a65b  jmp     loc_14012A80A
0x14012a660  cmp     [r14], r12
0x14012a663  jz      short loc_14012A696
0x14012a665  mov     rcx, cs:VmsIfrLog
0x14012a66c  lea     rax, aCmdListentryNe; "cmd->ListEntry.Next == NULL"
0x14012a673  mov     r9d, 1Eh
0x14012a679  mov     [rsp+0D0h+var_A8], rax
0x14012a67e  mov     [rsp+0D0h+Timeout], rdi
0x14012a683  lea     r8d, [r9-0Bh]
0x14012a687  call    WPP_RECORDER_SF_s
0x14012a68c  cmp     [r14], r12
0x14012a68f  jz      short loc_14012A696
0x14012a691  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "cmd->ListEntry.Next == ((void *)0)")
0x14012a696  mov     dword ptr [rbx+1BCh], 3
0x14012a6a0  jmp     loc_14012A80A
0x14012a6a5  cmp     dword ptr [rbx+1BCh], 2
0x14012a6ac  jz      short loc_14012A6C7
0x14012a6ae  lea     rsi, [rbx+58h]
0x14012a6b2  mov     rdi, [rsi]
0x14012a6b5  jmp     short loc_14012A6C2
0x14012a6b7  mov     rcx, rdi
0x14012a6ba  call    VmsPDDrainQueue
0x14012a6bf  mov     rdi, [rdi]
0x14012a6c2  cmp     rdi, rsi
0x14012a6c5  jnz     short loc_14012A6B7
0x14012a6c7  inc     dword ptr [rbx+1C8h]
0x14012a6cd  mov     dword ptr [rbx+1BCh], 2
0x14012a6d7  jmp     loc_14012A80A
0x14012a6dc  cmp     [rbx+1C8h], r12d
0x14012a6e3  ja      short loc_14012A71A
0x14012a6e5  mov     rcx, cs:VmsIfrLog
0x14012a6ec  lea     rax, aEcblockPauseco; "ecBlock->PauseCount > 0"
0x14012a6f3  mov     r9d, 1Dh
0x14012a6f9  mov     [rsp+0D0h+var_A8], rax
0x14012a6fe  mov     [rsp+0D0h+Timeout], rdi
0x14012a703  lea     r8d, [r9-0Ah]
0x14012a707  call    WPP_RECORDER_SF_s
0x14012a70c  cmp     [rbx+1C8h], r12d
0x14012a713  ja      short loc_14012A71A
0x14012a715  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ecBlock->PauseCount > 0")
0x14012a71a  mov     eax, [rbx+1C8h]
0x14012a720  test    eax, eax
0x14012a722  jz      short loc_14012A734
0x14012a724  dec     eax
0x14012a726  mov     [rbx+1C8h], eax
0x14012a72c  test    eax, eax
0x14012a72e  jnz     loc_14012A80A
0x14012a734  mov     dword ptr [rbx+1BCh], 1
0x14012a73e  jmp     loc_14012A80A
0x14012a743  mov     rax, cs:VmsPDPlatformDispatch
0x14012a74a  mov     rdx, r15
0x14012a74d  mov     rcx, cs:VmsPDClientHandle
0x14012a754  mov     rax, [rax+60h]
0x14012a758  call    _guard_dispatch_icall
0x14012a75d  mov     [r14+10h], eax
0x14012a761  test    eax, eax
0x14012a763  js      short loc_14012A772
0x14012a765  inc     dword ptr [rbx+1C8h]
0x14012a76b  mov     eax, 2
0x14012a770  jmp     short loc_14012A7A4
0x14012a772  mov     rcx, cs:VmsIfrLog
0x14012a779  mov     r9d, 1Ch
0x14012a77f  mov     [rsp+0D0h+var_A0], eax
0x14012a783  mov     dl, 2
0x14012a785  mov     rax, cs:VmsPDClientHandle
0x14012a78c  mov     [rsp+0D0h+var_A8], rax
0x14012a791  lea     r8d, [r9-8]
0x14012a795  mov     [rsp+0D0h+Timeout], rdi
0x14012a79a  call    WPP_RECORDER_SF_id
0x14012a79f  mov     eax, 3
0x14012a7a4  mov     [rbx+1BCh], eax
0x14012a7aa  jmp     short loc_14012A80A
0x14012a7ac  mov     ecx, edx
0x14012a7ae  sub     ecx, 7
0x14012a7b1  jz      short loc_14012A80A
0x14012a7b3  sub     ecx, 1
0x14012a7b6  jz      short loc_14012A7FF
0x14012a7b8  sub     ecx, 1
0x14012a7bb  jz      short loc_14012A7F2
0x14012a7bd  cmp     ecx, 1
0x14012a7c0  jz      short loc_14012A7E5
0x14012a7c2  mov     rcx, cs:VmsIfrLog
0x14012a7c9  mov     r9d, 1Fh
0x14012a7cf  mov     dword ptr [rsp+0D0h+var_A8], edx
0x14012a7d3  mov     dl, 2
0x14012a7d5  mov     [rsp+0D0h+Timeout], rdi
0x14012a7da  lea     r8d, [r9-0Bh]
0x14012a7de  call    WPP_RECORDER_SF_d
0x14012a7e3  jmp     short loc_14012A80A
0x14012a7e5  mov     rdx, r14
0x14012a7e8  mov     rcx, rbx
0x14012a7eb  call    VmsVmPDDeleteQueue
0x14012a7f0  jmp     short loc_14012A80A
0x14012a7f2  mov     rdx, r14
0x14012a7f5  mov     rcx, rbx
0x14012a7f8  call    VmsVmPDFlushQueue
0x14012a7fd  jmp     short loc_14012A80A
0x14012a7ff  mov     rdx, r14
0x14012a802  mov     rcx, rbx
0x14012a805  call    VmsVmPDCreateQueue
0x14012a80a  mov     rcx, [rbx+1C0h]
0x14012a811  mov     edx, [r14+8]
0x14012a815  lea     r8, [rcx+2330h]
0x14012a81c  sub     edx, 2
0x14012a81f  jz      short loc_14012A852
0x14012a821  sub     edx, 2
0x14012a824  jz      short loc_14012A830
0x14012a826  sub     edx, 2
0x14012a829  jz      short loc_14012A858
0x14012a82b  cmp     edx, 1
0x14012a82e  jnz     short loc_14012A870
0x14012a830  cmp     [rcx+2380h], r12b
0x14012a837  jz      short loc_14012A870
0x14012a839  mov     [rcx+2380h], r12b
0x14012a840  lea     rcx, [r8+8]; RunRef
0x14012a844  call    cs:__imp_ExReleaseRundownProtection
0x14012a84b  nop     dword ptr [rax+rax+00h]
0x14012a850  jmp     short loc_14012A870
0x14012a852  cmp     [r8+1Ch], r12d
0x14012a856  jz      short loc_14012A870
0x14012a858  cmp     [rcx+2380h], r12b
0x14012a85f  jnz     short loc_14012A870
0x14012a861  mov     byte ptr [rcx+2380h], 1
0x14012a868  mov     rcx, r8
0x14012a86b  call    PktCapReference
0x14012a870  mov     rax, cs:VmsPDPlatformDispatch
0x14012a877  mov     edx, 1
0x14012a87c  mov     rcx, [rbx+40h]
0x14012a880  mov     rax, [rax+20h]
0x14012a884  call    _guard_dispatch_icall
0x14012a889  mov     r14, [rbp+57h+var_80]
0x14012a88d  lea     rdi, WPP_ceb7cce27bd838a468dd456680e4ae98_Traceguids
0x14012a894  test    r14, r14
0x14012a897  jnz     loc_14012A5BF
0x14012a89d  mov     al, [rbp+57h+arg_10]
0x14012a8a0  lea     rdi, WPP_ceb7cce27bd838a468dd456680e4ae98_Traceguids
  ... truncated ...
```
