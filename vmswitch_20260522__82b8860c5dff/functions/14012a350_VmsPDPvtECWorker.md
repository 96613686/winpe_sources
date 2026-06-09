# VmsPDPvtECWorker

- ea: `0x14012a350`
- end: `0x14012adda`
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
- `0x1400ecc38`
- `0x1400ecd2c`
- `0x1400ecd90`
- `0x1400ece84`
- `0x140116734`
- `0x140128840`
- `0x140128d24`
- `0x1401295a0`
- `0x14012a350`
- `0x1401a5c10`
- `0x1401a6220`
- `0x1401a6840`
- `0x1401b954c`
- `0x1401bbe10`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x14012ac62`
- `ntoskrnl!KeClearEvent` at `0x14012ac62`
- `ntoskrnl!PsTerminateSystemThread` at `0x14012adb9`
- `ntoskrnl!PsTerminateSystemThread` at `0x14012adb9`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14012a7d4`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14012a7d4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14012ad27`
- `ntoskrnl!KeWaitForSingleObject` at `0x14012ad27`
- `NDIS!NdisReleaseRWLock` at `0x14012a4ed`
- `NDIS!NdisReleaseRWLock` at `0x14012a4ed`
- `NDIS!NdisAcquireRWLockWrite` at `0x14012a497`
- `NDIS!NdisAcquireRWLockWrite` at `0x14012a497`
- `vmbkmclr!VmbChannelPollRingBuffer` at `0x14012a9e5`
- `vmbkmclr!VmbChannelPollRingBuffer` at `0x14012a9e5`
- `vmbkmclr!VmbChannelSetPollingMode` at `0x14012a9a3`
- `vmbkmclr!VmbChannelSetPollingMode` at `0x14012a9fe`
- `vmbkmclr!VmbChannelSetPollingMode` at `0x14012a9a3`
- `vmbkmclr!VmbChannelSetPollingMode` at `0x14012a9fe`

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
0x14012a350  push    rbp
0x14012a352  push    rbx
0x14012a353  push    rsi
0x14012a354  push    rdi
0x14012a355  push    r12
0x14012a357  push    r13
0x14012a359  push    r14
0x14012a35b  push    r15
0x14012a35d  lea     rbp, [rsp-1Fh]
0x14012a362  sub     rsp, 98h
0x14012a369  xor     r12d, r12d
0x14012a36c  mov     [rbp+57h+var_8C], 0Ch
0x14012a373  lea     rax, [rbp+57h+var_80]
0x14012a377  mov     [rbp+57h+arg_10], r12b
0x14012a37b  xorps   xmm0, xmm0
0x14012a37e  mov     [rbp+57h+var_78], rax
0x14012a382  xor     eax, eax
0x14012a384  mov     [rbp+57h+var_80], r12
0x14012a388  lea     r15, [rcx+50h]
0x14012a38c  mov     [rbp+57h+var_88], r12
0x14012a390  lea     rdi, WPP_ceb7cce27bd838a468dd456680e4ae98_Traceguids
0x14012a397  mov     r13b, 1
0x14012a39a  mov     rbx, rcx
0x14012a39d  mov     [rbp+57h+var_70], r12
0x14012a3a1  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x14012a3a5  mov     [rbp+57h+LockState.Flags], al
0x14012a3a8  mov     [rbp+57h+arg_0], r13b
0x14012a3ac  mov     [rbp+57h+arg_18], r12b
0x14012a3b0  movups  [rbp+57h+var_68], xmm0
0x14012a3b4  movups  [rbp+57h+var_58], xmm0
0x14012a3b8  cmp     [r15], r12
0x14012a3bb  jz      short loc_14012A3EE
0x14012a3bd  mov     rcx, cs:VmsIfrLog
0x14012a3c4  lea     rax, aEcblockEchandl_0; "ecBlock->EcHandle == NULL"
0x14012a3cb  mov     [rsp+0D0h+var_A8], rax
0x14012a3d0  lea     r9d, [r12+1Bh]
0x14012a3d5  lea     r8d, [r12+13h]
0x14012a3da  mov     [rsp+0D0h+Timeout], rdi
0x14012a3df  call    WPP_RECORDER_SF_s
0x14012a3e4  cmp     [r15], r12
0x14012a3e7  jz      short loc_14012A3EE
0x14012a3e9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ecBlock->EcHandle == ((void *)0)")
0x14012a3ee  mov     rax, gs:188h
0x14012a3f7  mov     [rbx+358h], rax
0x14012a3fe  jmp     short loc_14012A403
0x14012a400  xor     r12d, r12d
0x14012a403  mov     rax, cs:VmsPDPlatformDispatch
0x14012a40a  lea     r9, [rbp+57h+arg_10]
0x14012a40e  mov     rcx, [rbx+40h]
0x14012a412  lea     rdx, [rbp+57h+var_78]
0x14012a416  or      r8d, 0FFFFFFFFh
0x14012a41a  mov     rax, [rax+18h]
0x14012a41e  call    _guard_dispatch_icall
0x14012a423  mov     r14, [rbp+57h+var_80]
0x14012a427  test    r14, r14
0x14012a42a  jnz     loc_14012A54F
0x14012a430  mov     al, [rbp+57h+arg_10]
0x14012a433  mov     [rbp+57h+arg_8], 1
0x14012a437  test    al, al
0x14012a439  jnz     loc_14012A83B
0x14012a43f  mov     r12b, [rbp+57h+arg_8]
0x14012a443  cmp     dword ptr [rbx+1BCh], 1
0x14012a44a  jnz     loc_14012ABF4
0x14012a450  xor     r13d, r13d
0x14012a453  mov     r12d, r13d
0x14012a456  mov     eax, r12d
0x14012a459  lea     r15, [rbx+98h]
0x14012a460  lea     r14, [rbx+0A8h]
0x14012a467  lea     rsi, [rax+rax*4]
0x14012a46b  lea     r15, [r15+rsi*8]
0x14012a46f  lea     r14, [r14+rsi*8]
0x14012a473  cmp     [r15], r13
0x14012a476  jnz     short loc_14012A481
0x14012a478  cmp     [r14], r13
0x14012a47b  jz      loc_14012A96C
0x14012a481  mov     rcx, [rbx+rsi*8+90h]; Lock
0x14012a489  lea     rdx, [rbp+57h+LockState]; LockState
0x14012a48d  xor     r8d, r8d; Flags
0x14012a490  mov     [rbp+57h+arg_8], 0
0x14012a494  mov     rdi, r13
0x14012a497  call    cs:__imp_NdisAcquireRWLockWrite
0x14012a49e  nop     dword ptr [rax+rax+00h]
0x14012a4a3  mov     rax, [rbx+rsi*8+98h]
0x14012a4ab  test    rax, rax
0x14012a4ae  jz      short loc_14012A4C7
0x14012a4b0  mov     rdi, rax
0x14012a4b3  mov     qword ptr [rbx+rsi*8+98h], 0
0x14012a4bf  mov     [rbx+rsi*8+0A0h], r15
0x14012a4c7  mov     rax, [r14]
0x14012a4ca  test    rax, rax
0x14012a4cd  jz      short loc_14012A4E1
0x14012a4cf  mov     r13, rax
0x14012a4d2  mov     qword ptr [r14], 0
0x14012a4d9  mov     [rbx+rsi*8+0B0h], r14
0x14012a4e1  mov     rcx, [rbx+rsi*8+90h]; Lock
0x14012a4e9  lea     rdx, [rbp+57h+LockState]; LockState
0x14012a4ed  call    cs:__imp_NdisReleaseRWLock
0x14012a4f4  nop     dword ptr [rax+rax+00h]
0x14012a4f9  test    rdi, rdi
0x14012a4fc  jz      loc_14012A8FA
0x14012a502  mov     ecx, r12d
0x14012a505  test    r12d, r12d
0x14012a508  jz      loc_14012A8E7
0x14012a50e  sub     ecx, 1
0x14012a511  jz      loc_14012A8D6
0x14012a517  sub     ecx, 1
0x14012a51a  jz      loc_14012A8C5
0x14012a520  sub     ecx, 1
0x14012a523  jz      loc_14012A8AE
0x14012a529  sub     ecx, 1
0x14012a52c  jz      loc_14012A897
0x14012a532  sub     ecx, 1
0x14012a535  jz      loc_14012A88F
0x14012a53b  cmp     ecx, 1
0x14012a53e  jnz     loc_14012A8FA
0x14012a544  mov     r8d, 2000h
0x14012a54a  jmp     loc_14012A89D
0x14012a54f  mov     rax, [r14]
0x14012a552  mov     [rbp+57h+var_80], rax
0x14012a556  mov     edx, [r14+8]
0x14012a55a  cmp     edx, 6
0x14012a55d  jg      loc_14012A73C
0x14012a563  jz      loc_14012A79A
0x14012a569  mov     ecx, edx
0x14012a56b  sub     ecx, 1
0x14012a56e  jz      loc_14012A6D3
0x14012a574  sub     ecx, 1
0x14012a577  jz      loc_14012A66C
0x14012a57d  sub     ecx, 1
0x14012a580  jz      loc_14012A635
0x14012a586  sub     ecx, 1
0x14012a589  jz      short loc_14012A5F0
0x14012a58b  cmp     ecx, 1
0x14012a58e  jnz     loc_14012A752
0x14012a594  lea     rsi, [rbx+68h]
0x14012a598  mov     r13b, cl
0x14012a59b  mov     rdi, [rsi]
0x14012a59e  jmp     short loc_14012A5BA
0x14012a5a0  mov     rcx, rdi
0x14012a5a3  call    VmsPDConfigureAwmOnQueue
0x14012a5a8  test    al, al
0x14012a5aa  jz      short loc_14012A5B4
0x14012a5ac  test    r13b, r13b
0x14012a5af  mov     r13b, 1
0x14012a5b2  jnz     short loc_14012A5B7
0x14012a5b4  mov     r13b, r12b
0x14012a5b7  mov     rdi, [rdi]
0x14012a5ba  cmp     rdi, rsi
0x14012a5bd  jnz     short loc_14012A5A0
0x14012a5bf  lea     rsi, [rbx+58h]
0x14012a5c3  mov     rdi, [rsi]
0x14012a5c6  jmp     short loc_14012A5E2
0x14012a5c8  mov     rcx, rdi
0x14012a5cb  call    VmsPDConfigureAwmOnQueue
0x14012a5d0  test    al, al
0x14012a5d2  jz      short loc_14012A5DC
0x14012a5d4  test    r13b, r13b
0x14012a5d7  mov     r13b, 1
0x14012a5da  jnz     short loc_14012A5DF
0x14012a5dc  mov     r13b, r12b
0x14012a5df  mov     rdi, [rdi]
0x14012a5e2  cmp     rdi, rsi
0x14012a5e5  jnz     short loc_14012A5C8
0x14012a5e7  mov     [rbp+57h+arg_18], r12b
0x14012a5eb  jmp     loc_14012A79A
0x14012a5f0  cmp     [r14], r12
0x14012a5f3  jz      short loc_14012A626
0x14012a5f5  mov     rcx, cs:VmsIfrLog
0x14012a5fc  lea     rax, aCmdListentryNe; "cmd->ListEntry.Next == NULL"
0x14012a603  mov     r9d, 1Eh
0x14012a609  mov     [rsp+0D0h+var_A8], rax
0x14012a60e  mov     [rsp+0D0h+Timeout], rdi
0x14012a613  lea     r8d, [r9-0Bh]
0x14012a617  call    WPP_RECORDER_SF_s
0x14012a61c  cmp     [r14], r12
0x14012a61f  jz      short loc_14012A626
0x14012a621  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "cmd->ListEntry.Next == ((void *)0)")
0x14012a626  mov     dword ptr [rbx+1BCh], 3
0x14012a630  jmp     loc_14012A79A
0x14012a635  cmp     dword ptr [rbx+1BCh], 2
0x14012a63c  jz      short loc_14012A657
0x14012a63e  lea     rsi, [rbx+58h]
0x14012a642  mov     rdi, [rsi]
0x14012a645  jmp     short loc_14012A652
0x14012a647  mov     rcx, rdi
0x14012a64a  call    VmsPDDrainQueue
0x14012a64f  mov     rdi, [rdi]
0x14012a652  cmp     rdi, rsi
0x14012a655  jnz     short loc_14012A647
0x14012a657  inc     dword ptr [rbx+1C8h]
0x14012a65d  mov     dword ptr [rbx+1BCh], 2
0x14012a667  jmp     loc_14012A79A
0x14012a66c  cmp     [rbx+1C8h], r12d
0x14012a673  ja      short loc_14012A6AA
0x14012a675  mov     rcx, cs:VmsIfrLog
0x14012a67c  lea     rax, aEcblockPauseco; "ecBlock->PauseCount > 0"
0x14012a683  mov     r9d, 1Dh
0x14012a689  mov     [rsp+0D0h+var_A8], rax
0x14012a68e  mov     [rsp+0D0h+Timeout], rdi
0x14012a693  lea     r8d, [r9-0Ah]
0x14012a697  call    WPP_RECORDER_SF_s
0x14012a69c  cmp     [rbx+1C8h], r12d
0x14012a6a3  ja      short loc_14012A6AA
0x14012a6a5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "ecBlock->PauseCount > 0")
0x14012a6aa  mov     eax, [rbx+1C8h]
0x14012a6b0  test    eax, eax
0x14012a6b2  jz      short loc_14012A6C4
0x14012a6b4  dec     eax
0x14012a6b6  mov     [rbx+1C8h], eax
0x14012a6bc  test    eax, eax
0x14012a6be  jnz     loc_14012A79A
0x14012a6c4  mov     dword ptr [rbx+1BCh], 1
0x14012a6ce  jmp     loc_14012A79A
0x14012a6d3  mov     rax, cs:VmsPDPlatformDispatch
0x14012a6da  mov     rdx, r15
0x14012a6dd  mov     rcx, cs:VmsPDClientHandle
0x14012a6e4  mov     rax, [rax+60h]
0x14012a6e8  call    _guard_dispatch_icall
0x14012a6ed  mov     [r14+10h], eax
0x14012a6f1  test    eax, eax
0x14012a6f3  js      short loc_14012A702
0x14012a6f5  inc     dword ptr [rbx+1C8h]
0x14012a6fb  mov     eax, 2
0x14012a700  jmp     short loc_14012A734
0x14012a702  mov     rcx, cs:VmsIfrLog
0x14012a709  mov     r9d, 1Ch
0x14012a70f  mov     [rsp+0D0h+var_A0], eax
0x14012a713  mov     dl, 2
0x14012a715  mov     rax, cs:VmsPDClientHandle
0x14012a71c  mov     [rsp+0D0h+var_A8], rax
0x14012a721  lea     r8d, [r9-8]
0x14012a725  mov     [rsp+0D0h+Timeout], rdi
0x14012a72a  call    WPP_RECORDER_SF_id
0x14012a72f  mov     eax, 3
0x14012a734  mov     [rbx+1BCh], eax
0x14012a73a  jmp     short loc_14012A79A
0x14012a73c  mov     ecx, edx
0x14012a73e  sub     ecx, 7
0x14012a741  jz      short loc_14012A79A
0x14012a743  sub     ecx, 1
0x14012a746  jz      short loc_14012A78F
0x14012a748  sub     ecx, 1
0x14012a74b  jz      short loc_14012A782
0x14012a74d  cmp     ecx, 1
0x14012a750  jz      short loc_14012A775
0x14012a752  mov     rcx, cs:VmsIfrLog
0x14012a759  mov     r9d, 1Fh
0x14012a75f  mov     dword ptr [rsp+0D0h+var_A8], edx
0x14012a763  mov     dl, 2
0x14012a765  mov     [rsp+0D0h+Timeout], rdi
0x14012a76a  lea     r8d, [r9-0Bh]
0x14012a76e  call    WPP_RECORDER_SF_d
0x14012a773  jmp     short loc_14012A79A
0x14012a775  mov     rdx, r14
0x14012a778  mov     rcx, rbx
0x14012a77b  call    VmsVmPDDeleteQueue
0x14012a780  jmp     short loc_14012A79A
0x14012a782  mov     rdx, r14
0x14012a785  mov     rcx, rbx
0x14012a788  call    VmsVmPDFlushQueue
0x14012a78d  jmp     short loc_14012A79A
0x14012a78f  mov     rdx, r14
0x14012a792  mov     rcx, rbx
0x14012a795  call    VmsVmPDCreateQueue
0x14012a79a  mov     rcx, [rbx+1C0h]
0x14012a7a1  mov     edx, [r14+8]
0x14012a7a5  lea     r8, [rcx+2330h]
0x14012a7ac  sub     edx, 2
0x14012a7af  jz      short loc_14012A7E2
0x14012a7b1  sub     edx, 2
0x14012a7b4  jz      short loc_14012A7C0
0x14012a7b6  sub     edx, 2
0x14012a7b9  jz      short loc_14012A7E8
0x14012a7bb  cmp     edx, 1
0x14012a7be  jnz     short loc_14012A800
0x14012a7c0  cmp     [rcx+2380h], r12b
0x14012a7c7  jz      short loc_14012A800
0x14012a7c9  mov     [rcx+2380h], r12b
0x14012a7d0  lea     rcx, [r8+8]; RunRef
0x14012a7d4  call    cs:__imp_ExReleaseRundownProtection
0x14012a7db  nop     dword ptr [rax+rax+00h]
0x14012a7e0  jmp     short loc_14012A800
0x14012a7e2  cmp     [r8+1Ch], r12d
0x14012a7e6  jz      short loc_14012A800
0x14012a7e8  cmp     [rcx+2380h], r12b
0x14012a7ef  jnz     short loc_14012A800
0x14012a7f1  mov     byte ptr [rcx+2380h], 1
0x14012a7f8  mov     rcx, r8
0x14012a7fb  call    PktCapReference
0x14012a800  mov     rax, cs:VmsPDPlatformDispatch
0x14012a807  mov     edx, 1
0x14012a80c  mov     rcx, [rbx+40h]
0x14012a810  mov     rax, [rax+20h]
0x14012a814  call    _guard_dispatch_icall
0x14012a819  mov     r14, [rbp+57h+var_80]
0x14012a81d  lea     rdi, WPP_ceb7cce27bd838a468dd456680e4ae98_Traceguids
0x14012a824  test    r14, r14
0x14012a827  jnz     loc_14012A54F
0x14012a82d  mov     al, [rbp+57h+arg_10]
0x14012a830  lea     rdi, WPP_ceb7cce27bd838a468dd456680e4ae98_Traceguids
  ... truncated ...
```
