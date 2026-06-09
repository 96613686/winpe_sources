# VmsScQosUpdateFlow

- ea: `0x1401521c8`
- end: `0x1401527a5`
- name: `VmsScQosUpdateFlow`
- size: `1501`
- prototype: ``
- caller_count: `5`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400dc600`
- `0x1400e78d0`
- `0x1400e7b30`
- `0x140124dfc`
- `0x1401519f8`

## callees

- `0x140018330`
- `0x140027a64`
- `0x14003e9e4`
- `0x14006dec8`
- `0x1400749f4`
- `0x14008497c`
- `0x14008faa8`
- `0x140090bd0`
- `0x1401521c8`
- `0x140152a30`
- `0x1401b6b9c`
- `0x1401b6de4`
- `0x1401b7214`
- `0x1401b7284`
- `0x1401b72dc`
- `0x1401b731c`
- `0x1401b748c`
- `0x1401b7f60`
- `0x1401bbc40`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140152475`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140152475`
- `ntoskrnl!KeGetCurrentIrql` at `0x140152427`
- `ntoskrnl!KeGetCurrentIrql` at `0x14015245e`
- `ntoskrnl!KeGetCurrentIrql` at `0x140152427`
- `ntoskrnl!KeGetCurrentIrql` at `0x14015245e`
- `NDIS!NdisReleaseRWLock` at `0x1401524f1`
- `NDIS!NdisReleaseRWLock` at `0x1401525c0`
- `NDIS!NdisReleaseRWLock` at `0x140152686`
- `NDIS!NdisReleaseRWLock` at `0x1401524f1`
- `NDIS!NdisReleaseRWLock` at `0x1401525c0`
- `NDIS!NdisReleaseRWLock` at `0x140152686`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401524b3`
- `NDIS!NdisAcquireRWLockWrite` at `0x140152597`
- `NDIS!NdisAcquireRWLockWrite` at `0x140152667`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401524b3`
- `NDIS!NdisAcquireRWLockWrite` at `0x140152597`
- `NDIS!NdisAcquireRWLockWrite` at `0x140152667`

## pseudocode

```c
__int64 __fastcall VmsScQosUpdateFlow(_QWORD *a1, PNDIS_RW_LOCK_EX *a2, __int64 a3)
{
  unsigned int v3; // ebx
  int v7; // eax
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  unsigned __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // edx
  ULONG CurrentProcessorNumber; // eax
  __int64 v14; // r8
  __int64 v15; // rdx
  ULONG v16; // r15d
  __int64 CurrentTime; // rax
  __int64 v18; // rdx
  int v19; // r8d
  int v20; // ecx
  int v21; // edx
  int v22; // edx
  int updated; // ebx
  int v24; // ebx
  int v25; // r13d
  int v26; // edx
  int v27; // r9d
  int v28; // edx
  __int64 v29; // r9
  _QWORD *v30; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v38; // [rsp+70h] [rbp-90h] BYREF
  __int128 v39; // [rsp+78h] [rbp-88h] BYREF
  __int128 v40; // [rsp+88h] [rbp-78h]
  _OWORD v41[2]; // [rsp+98h] [rbp-68h] BYREF
  int v42; // [rsp+B8h] [rbp-48h]
  __int64 v43; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v44; // [rsp+C8h] [rbp-38h]
  __int64 v45; // [rsp+D0h] [rbp-30h]
  __int64 v46; // [rsp+D8h] [rbp-28h]
  int v47; // [rsp+E0h] [rbp-20h]
  int v48; // [rsp+E4h] [rbp-1Ch]
  __int64 v49; // [rsp+E8h] [rbp-18h]
  __int64 v50; // [rsp+F0h] [rbp-10h]
  unsigned int v51; // [rsp+F8h] [rbp-8h]
  int v52; // [rsp+FCh] [rbp-4h]

  v35 = 0;
  v42 = 0;
  v34 = 0;
  v3 = 0;
  v37 = 0;
  v38 = 0;
  v36 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  LODWORD(v33) = 0;
  v46 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v40 = 0;
  DWORD2(v40) = 1;
  memset(v41, 0, sizeof(v41));
  v39 = 0;
  if ( !a2 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrPortLog,
      0,
      19,
      44,
      (__int64)WPP_05c02c503ec134b208c2e41c140079b1_Traceguids,
      (__int64)"Line != NULL");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  v7 = *(_DWORD *)(a3 + 464);
  if ( v7 )
  {
    if ( v7 != 1 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrPortLog,
        (_DWORD)a2,
        19,
        45,
        (__int64)WPP_05c02c503ec134b208c2e41c140079b1_Traceguids,
        (__int64)"Flow->FlowType == VmsFlowReservation");
      if ( *(_DWORD *)(a3 + 464) != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    v47 = -1;
    v44 = -1;
    v43 = -1;
    v45 = -1;
    v11 = a1[1];
    v48 = 2;
    if ( *a1 )
    {
      if ( v11 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrPortLog,
          (_DWORD)a2,
          19,
          46,
          (__int64)WPP_05c02c503ec134b208c2e41c140079b1_Traceguids,
          (__int64)"BandwidthInfo->BandwidthWeight == 0");
        if ( a1[1] )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      v3 = VmsScQospConvertRateToWeight(*a1, a2);
      v51 = v3;
    }
    else
    {
      if ( !v11 )
      {
        WPP_RECORDER_SF_s(
          VmsIfrPortLog,
          (_DWORD)a2,
          19,
          47,
          (__int64)WPP_05c02c503ec134b208c2e41c140079b1_Traceguids,
          (__int64)"BandwidthInfo->BandwidthWeight != 0");
        if ( !a1[1] )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
      }
      v3 = *((_DWORD *)a1 + 2);
      v51 = v3;
    }
    if ( !v3 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrPortLog,
        (_DWORD)a2,
        19,
        48,
        (__int64)WPP_05c02c503ec134b208c2e41c140079b1_Traceguids,
        (__int64)"flowSpec.Weight > 0");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    if ( v3 > 0x64 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrPortLog,
        (_DWORD)a2,
        19,
        49,
        (__int64)WPP_05c02c503ec134b208c2e41c140079b1_Traceguids,
        (__int64)"flowSpec.Weight <= VMS_MAX_FLOW_WEIGHT");
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
  }
  else
  {
    v8 = a1[4];
    v9 = a1[2] >> 3;
    if ( v8 )
      v44 = v8 >> 3;
    else
      v44 = a1[2] >> 3;
    v10 = a1[3];
    if ( v10 )
      v45 = v10 >> 3;
    else
      v45 = v9;
    v43 = v9;
    v47 = -1;
    v48 = 1;
  }
  if ( KeGetCurrentIrql() != 2 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrPortLog,
      v12,
      19,
      50,
      (__int64)WPP_05c02c503ec134b208c2e41c140079b1_Traceguids,
      (__int64)"KeGetCurrentIrql() == DISPATCH_LEVEL");
    if ( KeGetCurrentIrql() != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  LOBYTE(v14) = 1;
  LOBYTE(v15) = 1;
  v16 = CurrentProcessorNumber;
  CurrentTime = QosTimerGetCurrentTime(CurrentProcessorNumber, v15, v14);
  if ( (unsigned __int8)QosFlowNeedQueueFeedback(a3 + 40, CurrentTime, v41) )
  {
    NdisAcquireRWLockWrite(*a2, &LockState, 1u);
    if ( (unsigned __int8)QosLineNeedSignal(a2 + 1, v16) )
      QosLineSignalExternalEvent(a2 + 1, v16);
    QosLineQueryQueueFeedback(a2 + 1, v18, v41);
    NdisReleaseRWLock(*a2, &LockState);
    QosTbcAdjustSendWindow(a3 + 40, v41);
  }
  v52 = 3;
  if ( v3 == -1
    || ((v19 = *(_DWORD *)(a3 + 360), v20 = v3 - v19, v3 - v19 != v3) ? (v21 = (v20 != -v19) - 1) : (v21 = 1), !v20) )
  {
    updated = QosFlowUpdateComplete(
                (int)a3 + 40,
                v16,
                (unsigned int)&v43,
                0,
                (__int64)&v33,
                (__int64)&v35,
                (__int64)&v34);
    if ( updated != 259 )
      goto LABEL_42;
  }
  else
  {
    LODWORD(v39) = *(_DWORD *)(a3 + 360);
    DWORD1(v39) = v3;
    DWORD2(v39) = v3 - v19;
    HIDWORD(v39) = v21;
  }
  NdisAcquireRWLockWrite(*a2, &LockState, 1u);
  v24 = QosLineUpdate(a2 + 1, 0, 0, &v39);
  NdisReleaseRWLock(*a2, &LockState);
  updated = QosFlowUpdateComplete(
              (int)a3 + 40,
              v16,
              (unsigned int)&v43,
              v24,
              (__int64)&v33,
              (__int64)&v35,
              (__int64)&v34);
LABEL_42:
  v33 = *(_QWORD *)(a3 + 472);
  if ( v34 )
  {
    VmsScQosDropNbls(a3, (_DWORD)a2, v34, (unsigned int)&v36, -536862683);
    VmsNblHelperRefCountDecrementMany(v36, 1);
  }
  v25 = v35;
  if ( v35 )
  {
    if ( (unsigned __int8)QosLineNeedSignal(a2 + 1, v16) )
    {
      NdisAcquireRWLockWrite(*a2, &LockState, 1u);
      QosLineSignalExternalEvent(a2 + 1, v16);
      NdisReleaseRWLock(*a2, &LockState);
    }
    QosLineSendNetBufferLists((_DWORD)a2 + 8, v26, v25, v27, (__int64)&v37, (__int64)&v34);
    if ( *(_DWORD *)(a3 + 464) )
    {
      WPP_RECORDER_SF_s(
        VmsIfrPortLog,
        v28,
        19,
        51,
        (__int64)WPP_05c02c503ec134b208c2e41c140079b1_Traceguids,
        (__int64)"Flow->FlowType == VmsFlowLimit");
      if ( *(_DWORD *)(a3 + 464) )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    VmsScQosCompleteNbls(a3, a2, v37, &v38);
    if ( v38 )
    {
      LODWORD(v29) = 0;
      v30 = v38;
      do
      {
        v30 = (_QWORD *)*v30;
        v29 = (unsigned int)(v29 + 1);
      }
      while ( v30 );
      VmsScQospSendProcessedNbls(*(unsigned int *)(a3 + 464), v33, v38, v29);
    }
  }
  if ( updated < 0 )
  {
    LOBYTE(v22) = 2;
    WPP_RECORDER_SF_qqd(
      VmsIfrPortLog,
      v22,
      20,
      52,
      (__int64)WPP_05c02c503ec134b208c2e41c140079b1_Traceguids,
      (char)a1,
      (char)a2,
      updated);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1401521c8  mov     [rsp-8+arg_18], rbx
0x1401521cd  push    rbp
0x1401521ce  push    rsi
0x1401521cf  push    rdi
0x1401521d0  push    r12
0x1401521d2  push    r13
0x1401521d4  push    r14
0x1401521d6  push    r15
0x1401521d8  lea     rbp, [rsp-10h]
0x1401521dd  sub     rsp, 110h
0x1401521e4  mov     rax, cs:__security_cookie
0x1401521eb  xor     rax, rsp
0x1401521ee  mov     [rbp+40h+var_40], rax
0x1401521f2  xor     r12d, r12d
0x1401521f5  lea     r15, WPP_05c02c503ec134b208c2e41c140079b1_Traceguids
0x1401521fc  xor     eax, eax
0x1401521fe  mov     [rsp+140h+var_E8], r12
0x140152203  mov     [rbp+40h+var_88], eax
0x140152206  xorps   xmm0, xmm0
0x140152209  mov     [rsp+140h+var_F0], r12
0x14015220e  mov     ebx, r12d
0x140152211  mov     [rsp+140h+var_D8], r12
0x140152216  mov     r14, r8
0x140152219  mov     [rsp+140h+var_D0], r12
0x14015221e  lea     r13d, [rax+1]
0x140152222  mov     [rsp+140h+var_E0], r12
0x140152227  mov     rsi, rdx
0x14015222a  mov     word ptr [rsp+140h+LockState.OldIrql], ax
0x14015222f  mov     rdi, rcx
0x140152232  mov     [rsp+140h+LockState.Flags], al
0x140152236  mov     dword ptr [rsp+140h+var_F8], r12d
0x14015223b  mov     [rbp+40h+var_68], r12
0x14015223f  mov     [rbp+40h+var_58], r12
0x140152243  mov     [rbp+40h+var_50], r12
0x140152247  mov     [rbp+40h+var_48], ebx
0x14015224a  movups  [rbp+40h+var_B8], xmm0
0x14015224e  mov     dword ptr [rbp+40h+var_B8+8], r13d
0x140152252  movups  [rbp+40h+var_A8], xmm0
0x140152256  movups  [rbp+40h+var_98], xmm0
0x14015225a  movups  [rsp+140h+var_C8], xmm0
0x14015225f  test    rdx, rdx
0x140152262  jnz     short loc_14015228E
0x140152264  mov     rcx, cs:VmsIfrPortLog
0x14015226b  lea     rax, aLineNull_0; "Line != NULL"
0x140152272  mov     [rsp+140h+var_118], rax
0x140152277  lea     r9d, [rdx+2Ch]
0x14015227b  lea     r8d, [rdx+13h]
0x14015227f  mov     [rsp+140h+var_120], r15
0x140152284  call    WPP_RECORDER_SF_s
0x140152289  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Line != ((void *)0)")
0x14015228e  mov     eax, [r14+1D0h]
0x140152295  test    eax, eax
0x140152297  jnz     short loc_1401522E3
0x140152299  mov     rax, [rdi+10h]
0x14015229d  mov     rcx, [rdi+20h]
0x1401522a1  shr     rax, 3
0x1401522a5  test    rcx, rcx
0x1401522a8  jz      short loc_1401522B4
0x1401522aa  shr     rcx, 3
0x1401522ae  mov     [rbp+40h+var_78], rcx
0x1401522b2  jmp     short loc_1401522B8
0x1401522b4  mov     [rbp+40h+var_78], rax
0x1401522b8  mov     rcx, [rdi+18h]
0x1401522bc  test    rcx, rcx
0x1401522bf  jz      short loc_1401522CB
0x1401522c1  shr     rcx, 3
0x1401522c5  mov     [rbp+40h+var_70], rcx
0x1401522c9  jmp     short loc_1401522CF
0x1401522cb  mov     [rbp+40h+var_70], rax
0x1401522cf  mov     [rbp+40h+var_80], rax
0x1401522d3  mov     [rbp+40h+var_60], 0FFFFFFFFh
0x1401522da  mov     [rbp+40h+var_5C], r13d
0x1401522de  jmp     loc_140152427
0x1401522e3  cmp     eax, r13d
0x1401522e6  jz      short loc_14015231D
0x1401522e8  mov     rcx, cs:VmsIfrPortLog
0x1401522ef  lea     rax, aFlowFlowtypeVm; "Flow->FlowType == VmsFlowReservation"
0x1401522f6  mov     r9d, 2Dh ; '-'
0x1401522fc  mov     [rsp+140h+var_118], rax
0x140152301  mov     [rsp+140h+var_120], r15
0x140152306  lea     r8d, [r9-1Ah]
0x14015230a  call    WPP_RECORDER_SF_s
0x14015230f  cmp     [r14+1D0h], r13d
0x140152316  jz      short loc_14015231D
0x140152318  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Flow->FlowType == VmsFlowReservation")
0x14015231d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140152321  mov     [rbp+40h+var_60], 0FFFFFFFFh
0x140152328  mov     [rbp+40h+var_78], rax
0x14015232c  mov     [rbp+40h+var_80], rax
0x140152330  mov     [rbp+40h+var_70], rax
0x140152334  mov     rax, [rdi+8]
0x140152338  mov     [rbp+40h+var_5C], 2
0x14015233f  cmp     [rdi], r12
0x140152342  jz      short loc_14015238D
0x140152344  test    rax, rax
0x140152347  jz      short loc_14015237B
0x140152349  mov     rcx, cs:VmsIfrPortLog
0x140152350  lea     rax, aBandwidthinfoB; "BandwidthInfo->BandwidthWeight == 0"
0x140152357  mov     r9d, 2Eh ; '.'
0x14015235d  mov     [rsp+140h+var_118], rax
0x140152362  mov     [rsp+140h+var_120], r15
0x140152367  lea     r8d, [r9-1Bh]
0x14015236b  call    WPP_RECORDER_SF_s
0x140152370  cmp     [rdi+8], r12
0x140152374  jz      short loc_14015237B
0x140152376  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "BandwidthInfo->BandwidthWeight == 0")
0x14015237b  mov     rcx, [rdi]
0x14015237e  mov     rdx, rsi
0x140152381  call    VmsScQospConvertRateToWeight
0x140152386  mov     ebx, eax
0x140152388  mov     [rbp+40h+var_48], eax
0x14015238b  jmp     short loc_1401523C8
0x14015238d  test    rax, rax
0x140152390  jnz     short loc_1401523C2
0x140152392  mov     rcx, cs:VmsIfrPortLog
0x140152399  lea     r9d, [rax+2Fh]
0x14015239d  lea     rax, aBandwidthinfoB_0; "BandwidthInfo->BandwidthWeight != 0"
0x1401523a4  mov     [rsp+140h+var_118], rax
0x1401523a9  lea     r8d, [r9-1Ch]
0x1401523ad  mov     [rsp+140h+var_120], r15
0x1401523b2  call    WPP_RECORDER_SF_s
0x1401523b7  cmp     [rdi+8], r12
0x1401523bb  jnz     short loc_1401523C2
0x1401523bd  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "BandwidthInfo->BandwidthWeight != 0")
0x1401523c2  mov     ebx, [rdi+8]
0x1401523c5  mov     [rbp+40h+var_48], ebx
0x1401523c8  test    ebx, ebx
0x1401523ca  jnz     short loc_1401523F6
0x1401523cc  mov     rcx, cs:VmsIfrPortLog
0x1401523d3  lea     rax, aFlowspecWeight_0; "flowSpec.Weight > 0"
0x1401523da  mov     [rsp+140h+var_118], rax
0x1401523df  lea     r9d, [rbx+30h]
0x1401523e3  lea     r8d, [rbx+13h]
0x1401523e7  mov     [rsp+140h+var_120], r15
0x1401523ec  call    WPP_RECORDER_SF_s
0x1401523f1  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "flowSpec.Weight > 0")
0x1401523f6  cmp     ebx, 64h ; 'd'
0x1401523f9  jbe     short loc_140152427
0x1401523fb  mov     rcx, cs:VmsIfrPortLog
0x140152402  lea     rax, aFlowspecWeight; "flowSpec.Weight <= VMS_MAX_FLOW_WEIGHT"
0x140152409  mov     r9d, 31h ; '1'
0x14015240f  mov     [rsp+140h+var_118], rax
0x140152414  mov     [rsp+140h+var_120], r15
0x140152419  lea     r8d, [r9-1Eh]
0x14015241d  call    WPP_RECORDER_SF_s
0x140152422  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "flowSpec.Weight <= 100")
0x140152427  call    cs:__imp_KeGetCurrentIrql
0x14015242e  nop     dword ptr [rax+rax+00h]
0x140152433  cmp     al, 2
0x140152435  jz      short loc_140152473
0x140152437  mov     rcx, cs:VmsIfrPortLog
0x14015243e  lea     rax, aKegetcurrentir; "KeGetCurrentIrql() == DISPATCH_LEVEL"
0x140152445  mov     r9d, 32h ; '2'
0x14015244b  mov     [rsp+140h+var_118], rax
0x140152450  mov     [rsp+140h+var_120], r15
0x140152455  lea     r8d, [r9-1Fh]
0x140152459  call    WPP_RECORDER_SF_s
0x14015245e  call    cs:__imp_KeGetCurrentIrql
0x140152465  nop     dword ptr [rax+rax+00h]
0x14015246a  cmp     al, 2
0x14015246c  jz      short loc_140152473
0x14015246e  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "KeGetCurrentIrql() == 2")
0x140152473  xor     ecx, ecx; ProcNumber
0x140152475  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14015247c  nop     dword ptr [rax+rax+00h]
0x140152481  mov     r8b, r13b
0x140152484  mov     dl, r13b
0x140152487  mov     ecx, eax
0x140152489  mov     r15d, eax
0x14015248c  call    QosTimerGetCurrentTime
0x140152491  lea     r13, [r14+28h]
0x140152495  mov     rdx, rax
0x140152498  mov     rcx, r13
0x14015249b  lea     r8, [rbp+40h+var_A8]
0x14015249f  call    QosFlowNeedQueueFeedback
0x1401524a4  test    al, al
0x1401524a6  jz      short loc_14015250C
0x1401524a8  mov     rcx, [rsi]; Lock
0x1401524ab  lea     rdx, [rsp+140h+LockState]; LockState
0x1401524b0  mov     r8b, 1; Flags
0x1401524b3  call    cs:__imp_NdisAcquireRWLockWrite
0x1401524ba  nop     dword ptr [rax+rax+00h]
0x1401524bf  lea     r12, [rsi+8]
0x1401524c3  mov     edx, r15d
0x1401524c6  mov     rcx, r12
0x1401524c9  call    QosLineNeedSignal
0x1401524ce  test    al, al
0x1401524d0  jz      short loc_1401524DD
0x1401524d2  mov     edx, r15d
0x1401524d5  mov     rcx, r12
0x1401524d8  call    QosLineSignalExternalEvent
0x1401524dd  lea     r8, [rbp+40h+var_A8]
0x1401524e1  mov     rcx, r12
0x1401524e4  call    QosLineQueryQueueFeedback
0x1401524e9  mov     rcx, [rsi]; Lock
0x1401524ec  lea     rdx, [rsp+140h+LockState]; LockState
0x1401524f1  call    cs:__imp_NdisReleaseRWLock
0x1401524f8  nop     dword ptr [rax+rax+00h]
0x1401524fd  lea     rdx, [rbp+40h+var_A8]
0x140152501  mov     rcx, r13
0x140152504  call    QosTbcAdjustSendWindow
0x140152509  xor     r12d, r12d
0x14015250c  mov     [rbp+40h+var_44], 3
0x140152513  mov     r9d, r12d
0x140152516  cmp     ebx, 0FFFFFFFFh
0x140152519  jz      short loc_140152556
0x14015251b  mov     r8d, [r13+140h]
0x140152522  mov     ecx, ebx
0x140152524  sub     ecx, r8d
0x140152527  cmp     ecx, ebx
0x140152529  jnz     short loc_140152532
0x14015252b  mov     edx, 1
0x140152530  jmp     short loc_140152541
0x140152532  mov     edx, r12d
0x140152535  mov     eax, r8d
0x140152538  neg     eax
0x14015253a  cmp     ecx, eax
0x14015253c  setnz   dl
0x14015253f  dec     edx
0x140152541  test    ecx, ecx
0x140152543  jz      short loc_140152556
0x140152545  mov     dword ptr [rsp+140h+var_C8], r8d
0x14015254a  mov     dword ptr [rsp+140h+var_C8+4], ebx
0x14015254e  mov     dword ptr [rbp+40h+var_C8+8], ecx
0x140152551  mov     dword ptr [rbp+40h+var_C8+0Ch], edx
0x140152554  jmp     short loc_14015258C
0x140152556  lea     rax, [rsp+140h+var_F0]
0x14015255b  mov     edx, r15d
0x14015255e  mov     [rsp+140h+var_110], rax
0x140152563  lea     r8, [rbp+40h+var_80]
0x140152567  lea     rax, [rsp+140h+var_E8]
0x14015256c  mov     rcx, r13
0x14015256f  mov     [rsp+140h+var_118], rax
0x140152574  lea     rax, [rsp+140h+var_F8]
0x140152579  mov     [rsp+140h+var_120], rax
0x14015257e  call    QosFlowUpdateComplete
0x140152583  mov     ebx, eax
0x140152585  cmp     eax, 103h
0x14015258a  jnz     short loc_1401525FE
0x14015258c  mov     rcx, [rsi]; Lock
0x14015258f  lea     rdx, [rsp+140h+LockState]; LockState
0x140152594  mov     r8b, 1; Flags
0x140152597  call    cs:__imp_NdisAcquireRWLockWrite
0x14015259e  nop     dword ptr [rax+rax+00h]
0x1401525a3  lea     rcx, [rsi+8]
0x1401525a7  xor     r8d, r8d
0x1401525aa  lea     r9, [rsp+140h+var_C8]
0x1401525af  xor     edx, edx
0x1401525b1  call    QosLineUpdate
0x1401525b6  mov     rcx, [rsi]; Lock
0x1401525b9  lea     rdx, [rsp+140h+LockState]; LockState
0x1401525be  mov     ebx, eax
0x1401525c0  call    cs:__imp_NdisReleaseRWLock
0x1401525c7  nop     dword ptr [rax+rax+00h]
0x1401525cc  lea     rax, [rsp+140h+var_F0]
0x1401525d1  mov     r9d, ebx
0x1401525d4  mov     [rsp+140h+var_110], rax
0x1401525d9  lea     r8, [rbp+40h+var_80]
0x1401525dd  lea     rax, [rsp+140h+var_E8]
0x1401525e2  mov     edx, r15d
0x1401525e5  mov     [rsp+140h+var_118], rax
0x1401525ea  mov     rcx, r13
0x1401525ed  lea     rax, [rsp+140h+var_F8]
0x1401525f2  mov     [rsp+140h+var_120], rax
0x1401525f7  call    QosFlowUpdateComplete
0x1401525fc  mov     ebx, eax
0x1401525fe  mov     r8, [rsp+140h+var_F0]
0x140152603  mov     rax, [r14+1D8h]
0x14015260a  mov     [rsp+140h+var_F8], rax
0x14015260f  test    r8, r8
0x140152612  jz      short loc_14015263B
0x140152614  lea     r9, [rsp+140h+var_E0]
0x140152619  mov     dword ptr [rsp+140h+var_120], 0E0002025h
0x140152621  mov     rdx, rsi
0x140152624  mov     rcx, r14
0x140152627  call    VmsScQosDropNbls
0x14015262c  mov     rcx, [rsp+140h+var_E0]
0x140152631  mov     edx, 1
0x140152636  call    VmsNblHelperRefCountDecrementMany
0x14015263b  mov     r13, [rsp+140h+var_E8]
0x140152640  test    r13, r13
0x140152643  jz      loc_140152745
0x140152649  lea     r12, [rsi+8]
0x14015264d  mov     edx, r15d
0x140152650  mov     rcx, r12
0x140152653  call    QosLineNeedSignal
0x140152658  test    al, al
0x14015265a  jz      short loc_140152692
0x14015265c  mov     rcx, [rsi]; Lock
0x14015265f  lea     rdx, [rsp+140h+LockState]; LockState
0x140152664  mov     r8b, 1; Flags
0x140152667  call    cs:__imp_NdisAcquireRWLockWrite
0x14015266e  nop     dword ptr [rax+rax+00h]
0x140152673  mov     edx, r15d
0x140152676  mov     rcx, r12
0x140152679  call    QosLineSignalExternalEvent
0x14015267e  mov     rcx, [rsi]; Lock
0x140152681  lea     rdx, [rsp+140h+LockState]; LockState
0x140152686  call    cs:__imp_NdisReleaseRWLock
0x14015268d  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
