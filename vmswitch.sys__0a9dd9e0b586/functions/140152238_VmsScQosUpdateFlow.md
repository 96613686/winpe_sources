# VmsScQosUpdateFlow

- ea: `0x140152238`
- end: `0x140152815`
- name: `VmsScQosUpdateFlow`
- size: `1501`
- prototype: ``
- caller_count: `5`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400dc670`
- `0x1400e7940`
- `0x1400e7ba0`
- `0x140124e6c`
- `0x140151a68`

## callees

- `0x140018330`
- `0x140027a64`
- `0x14003e9e4`
- `0x14006dec8`
- `0x1400749f4`
- `0x14008497c`
- `0x14008faa8`
- `0x140090bd0`
- `0x140152238`
- `0x140152aa0`
- `0x1401b6c0c`
- `0x1401b6e54`
- `0x1401b7284`
- `0x1401b72f4`
- `0x1401b734c`
- `0x1401b738c`
- `0x1401b74fc`
- `0x1401b7fd0`
- `0x1401bbcb0`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401524e5`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401524e5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140152497`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401524ce`
- `ntoskrnl!KeGetCurrentIrql` at `0x140152497`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401524ce`
- `NDIS!NdisReleaseRWLock` at `0x140152561`
- `NDIS!NdisReleaseRWLock` at `0x140152630`
- `NDIS!NdisReleaseRWLock` at `0x1401526f6`
- `NDIS!NdisReleaseRWLock` at `0x140152561`
- `NDIS!NdisReleaseRWLock` at `0x140152630`
- `NDIS!NdisReleaseRWLock` at `0x1401526f6`
- `NDIS!NdisAcquireRWLockWrite` at `0x140152523`
- `NDIS!NdisAcquireRWLockWrite` at `0x140152607`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401526d7`
- `NDIS!NdisAcquireRWLockWrite` at `0x140152523`
- `NDIS!NdisAcquireRWLockWrite` at `0x140152607`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401526d7`

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
0x140152238  mov     [rsp-8+arg_18], rbx
0x14015223d  push    rbp
0x14015223e  push    rsi
0x14015223f  push    rdi
0x140152240  push    r12
0x140152242  push    r13
0x140152244  push    r14
0x140152246  push    r15
0x140152248  lea     rbp, [rsp-10h]
0x14015224d  sub     rsp, 110h
0x140152254  mov     rax, cs:__security_cookie
0x14015225b  xor     rax, rsp
0x14015225e  mov     [rbp+40h+var_40], rax
0x140152262  xor     r12d, r12d
0x140152265  lea     r15, WPP_05c02c503ec134b208c2e41c140079b1_Traceguids
0x14015226c  xor     eax, eax
0x14015226e  mov     [rsp+140h+var_E8], r12
0x140152273  mov     [rbp+40h+var_88], eax
0x140152276  xorps   xmm0, xmm0
0x140152279  mov     [rsp+140h+var_F0], r12
0x14015227e  mov     ebx, r12d
0x140152281  mov     [rsp+140h+var_D8], r12
0x140152286  mov     r14, r8
0x140152289  mov     [rsp+140h+var_D0], r12
0x14015228e  lea     r13d, [rax+1]
0x140152292  mov     [rsp+140h+var_E0], r12
0x140152297  mov     rsi, rdx
0x14015229a  mov     word ptr [rsp+140h+LockState.OldIrql], ax
0x14015229f  mov     rdi, rcx
0x1401522a2  mov     [rsp+140h+LockState.Flags], al
0x1401522a6  mov     dword ptr [rsp+140h+var_F8], r12d
0x1401522ab  mov     [rbp+40h+var_68], r12
0x1401522af  mov     [rbp+40h+var_58], r12
0x1401522b3  mov     [rbp+40h+var_50], r12
0x1401522b7  mov     [rbp+40h+var_48], ebx
0x1401522ba  movups  [rbp+40h+var_B8], xmm0
0x1401522be  mov     dword ptr [rbp+40h+var_B8+8], r13d
0x1401522c2  movups  [rbp+40h+var_A8], xmm0
0x1401522c6  movups  [rbp+40h+var_98], xmm0
0x1401522ca  movups  [rsp+140h+var_C8], xmm0
0x1401522cf  test    rdx, rdx
0x1401522d2  jnz     short loc_1401522FE
0x1401522d4  mov     rcx, cs:VmsIfrPortLog
0x1401522db  lea     rax, aLineNull_0; "Line != NULL"
0x1401522e2  mov     [rsp+140h+var_118], rax
0x1401522e7  lea     r9d, [rdx+2Ch]
0x1401522eb  lea     r8d, [rdx+13h]
0x1401522ef  mov     [rsp+140h+var_120], r15
0x1401522f4  call    WPP_RECORDER_SF_s
0x1401522f9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Line != ((void *)0)")
0x1401522fe  mov     eax, [r14+1D0h]
0x140152305  test    eax, eax
0x140152307  jnz     short loc_140152353
0x140152309  mov     rax, [rdi+10h]
0x14015230d  mov     rcx, [rdi+20h]
0x140152311  shr     rax, 3
0x140152315  test    rcx, rcx
0x140152318  jz      short loc_140152324
0x14015231a  shr     rcx, 3
0x14015231e  mov     [rbp+40h+var_78], rcx
0x140152322  jmp     short loc_140152328
0x140152324  mov     [rbp+40h+var_78], rax
0x140152328  mov     rcx, [rdi+18h]
0x14015232c  test    rcx, rcx
0x14015232f  jz      short loc_14015233B
0x140152331  shr     rcx, 3
0x140152335  mov     [rbp+40h+var_70], rcx
0x140152339  jmp     short loc_14015233F
0x14015233b  mov     [rbp+40h+var_70], rax
0x14015233f  mov     [rbp+40h+var_80], rax
0x140152343  mov     [rbp+40h+var_60], 0FFFFFFFFh
0x14015234a  mov     [rbp+40h+var_5C], r13d
0x14015234e  jmp     loc_140152497
0x140152353  cmp     eax, r13d
0x140152356  jz      short loc_14015238D
0x140152358  mov     rcx, cs:VmsIfrPortLog
0x14015235f  lea     rax, aFlowFlowtypeVm; "Flow->FlowType == VmsFlowReservation"
0x140152366  mov     r9d, 2Dh ; '-'
0x14015236c  mov     [rsp+140h+var_118], rax
0x140152371  mov     [rsp+140h+var_120], r15
0x140152376  lea     r8d, [r9-1Ah]
0x14015237a  call    WPP_RECORDER_SF_s
0x14015237f  cmp     [r14+1D0h], r13d
0x140152386  jz      short loc_14015238D
0x140152388  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Flow->FlowType == VmsFlowReservation")
0x14015238d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140152391  mov     [rbp+40h+var_60], 0FFFFFFFFh
0x140152398  mov     [rbp+40h+var_78], rax
0x14015239c  mov     [rbp+40h+var_80], rax
0x1401523a0  mov     [rbp+40h+var_70], rax
0x1401523a4  mov     rax, [rdi+8]
0x1401523a8  mov     [rbp+40h+var_5C], 2
0x1401523af  cmp     [rdi], r12
0x1401523b2  jz      short loc_1401523FD
0x1401523b4  test    rax, rax
0x1401523b7  jz      short loc_1401523EB
0x1401523b9  mov     rcx, cs:VmsIfrPortLog
0x1401523c0  lea     rax, aBandwidthinfoB; "BandwidthInfo->BandwidthWeight == 0"
0x1401523c7  mov     r9d, 2Eh ; '.'
0x1401523cd  mov     [rsp+140h+var_118], rax
0x1401523d2  mov     [rsp+140h+var_120], r15
0x1401523d7  lea     r8d, [r9-1Bh]
0x1401523db  call    WPP_RECORDER_SF_s
0x1401523e0  cmp     [rdi+8], r12
0x1401523e4  jz      short loc_1401523EB
0x1401523e6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "BandwidthInfo->BandwidthWeight == 0")
0x1401523eb  mov     rcx, [rdi]
0x1401523ee  mov     rdx, rsi
0x1401523f1  call    VmsScQospConvertRateToWeight
0x1401523f6  mov     ebx, eax
0x1401523f8  mov     [rbp+40h+var_48], eax
0x1401523fb  jmp     short loc_140152438
0x1401523fd  test    rax, rax
0x140152400  jnz     short loc_140152432
0x140152402  mov     rcx, cs:VmsIfrPortLog
0x140152409  lea     r9d, [rax+2Fh]
0x14015240d  lea     rax, aBandwidthinfoB_0; "BandwidthInfo->BandwidthWeight != 0"
0x140152414  mov     [rsp+140h+var_118], rax
0x140152419  lea     r8d, [r9-1Ch]
0x14015241d  mov     [rsp+140h+var_120], r15
0x140152422  call    WPP_RECORDER_SF_s
0x140152427  cmp     [rdi+8], r12
0x14015242b  jnz     short loc_140152432
0x14015242d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "BandwidthInfo->BandwidthWeight != 0")
0x140152432  mov     ebx, [rdi+8]
0x140152435  mov     [rbp+40h+var_48], ebx
0x140152438  test    ebx, ebx
0x14015243a  jnz     short loc_140152466
0x14015243c  mov     rcx, cs:VmsIfrPortLog
0x140152443  lea     rax, aFlowspecWeight_0; "flowSpec.Weight > 0"
0x14015244a  mov     [rsp+140h+var_118], rax
0x14015244f  lea     r9d, [rbx+30h]
0x140152453  lea     r8d, [rbx+13h]
0x140152457  mov     [rsp+140h+var_120], r15
0x14015245c  call    WPP_RECORDER_SF_s
0x140152461  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "flowSpec.Weight > 0")
0x140152466  cmp     ebx, 64h ; 'd'
0x140152469  jbe     short loc_140152497
0x14015246b  mov     rcx, cs:VmsIfrPortLog
0x140152472  lea     rax, aFlowspecWeight; "flowSpec.Weight <= VMS_MAX_FLOW_WEIGHT"
0x140152479  mov     r9d, 31h ; '1'
0x14015247f  mov     [rsp+140h+var_118], rax
0x140152484  mov     [rsp+140h+var_120], r15
0x140152489  lea     r8d, [r9-1Eh]
0x14015248d  call    WPP_RECORDER_SF_s
0x140152492  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "flowSpec.Weight <= 100")
0x140152497  call    cs:__imp_KeGetCurrentIrql
0x14015249e  nop     dword ptr [rax+rax+00h]
0x1401524a3  cmp     al, 2
0x1401524a5  jz      short loc_1401524E3
0x1401524a7  mov     rcx, cs:VmsIfrPortLog
0x1401524ae  lea     rax, aKegetcurrentir; "KeGetCurrentIrql() == DISPATCH_LEVEL"
0x1401524b5  mov     r9d, 32h ; '2'
0x1401524bb  mov     [rsp+140h+var_118], rax
0x1401524c0  mov     [rsp+140h+var_120], r15
0x1401524c5  lea     r8d, [r9-1Fh]
0x1401524c9  call    WPP_RECORDER_SF_s
0x1401524ce  call    cs:__imp_KeGetCurrentIrql
0x1401524d5  nop     dword ptr [rax+rax+00h]
0x1401524da  cmp     al, 2
0x1401524dc  jz      short loc_1401524E3
0x1401524de  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "KeGetCurrentIrql() == 2")
0x1401524e3  xor     ecx, ecx; ProcNumber
0x1401524e5  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1401524ec  nop     dword ptr [rax+rax+00h]
0x1401524f1  mov     r8b, r13b
0x1401524f4  mov     dl, r13b
0x1401524f7  mov     ecx, eax
0x1401524f9  mov     r15d, eax
0x1401524fc  call    QosTimerGetCurrentTime
0x140152501  lea     r13, [r14+28h]
0x140152505  mov     rdx, rax
0x140152508  mov     rcx, r13
0x14015250b  lea     r8, [rbp+40h+var_A8]
0x14015250f  call    QosFlowNeedQueueFeedback
0x140152514  test    al, al
0x140152516  jz      short loc_14015257C
0x140152518  mov     rcx, [rsi]; Lock
0x14015251b  lea     rdx, [rsp+140h+LockState]; LockState
0x140152520  mov     r8b, 1; Flags
0x140152523  call    cs:__imp_NdisAcquireRWLockWrite
0x14015252a  nop     dword ptr [rax+rax+00h]
0x14015252f  lea     r12, [rsi+8]
0x140152533  mov     edx, r15d
0x140152536  mov     rcx, r12
0x140152539  call    QosLineNeedSignal
0x14015253e  test    al, al
0x140152540  jz      short loc_14015254D
0x140152542  mov     edx, r15d
0x140152545  mov     rcx, r12
0x140152548  call    QosLineSignalExternalEvent
0x14015254d  lea     r8, [rbp+40h+var_A8]
0x140152551  mov     rcx, r12
0x140152554  call    QosLineQueryQueueFeedback
0x140152559  mov     rcx, [rsi]; Lock
0x14015255c  lea     rdx, [rsp+140h+LockState]; LockState
0x140152561  call    cs:__imp_NdisReleaseRWLock
0x140152568  nop     dword ptr [rax+rax+00h]
0x14015256d  lea     rdx, [rbp+40h+var_A8]
0x140152571  mov     rcx, r13
0x140152574  call    QosTbcAdjustSendWindow
0x140152579  xor     r12d, r12d
0x14015257c  mov     [rbp+40h+var_44], 3
0x140152583  mov     r9d, r12d
0x140152586  cmp     ebx, 0FFFFFFFFh
0x140152589  jz      short loc_1401525C6
0x14015258b  mov     r8d, [r13+140h]
0x140152592  mov     ecx, ebx
0x140152594  sub     ecx, r8d
0x140152597  cmp     ecx, ebx
0x140152599  jnz     short loc_1401525A2
0x14015259b  mov     edx, 1
0x1401525a0  jmp     short loc_1401525B1
0x1401525a2  mov     edx, r12d
0x1401525a5  mov     eax, r8d
0x1401525a8  neg     eax
0x1401525aa  cmp     ecx, eax
0x1401525ac  setnz   dl
0x1401525af  dec     edx
0x1401525b1  test    ecx, ecx
0x1401525b3  jz      short loc_1401525C6
0x1401525b5  mov     dword ptr [rsp+140h+var_C8], r8d
0x1401525ba  mov     dword ptr [rsp+140h+var_C8+4], ebx
0x1401525be  mov     dword ptr [rbp+40h+var_C8+8], ecx
0x1401525c1  mov     dword ptr [rbp+40h+var_C8+0Ch], edx
0x1401525c4  jmp     short loc_1401525FC
0x1401525c6  lea     rax, [rsp+140h+var_F0]
0x1401525cb  mov     edx, r15d
0x1401525ce  mov     [rsp+140h+var_110], rax
0x1401525d3  lea     r8, [rbp+40h+var_80]
0x1401525d7  lea     rax, [rsp+140h+var_E8]
0x1401525dc  mov     rcx, r13
0x1401525df  mov     [rsp+140h+var_118], rax
0x1401525e4  lea     rax, [rsp+140h+var_F8]
0x1401525e9  mov     [rsp+140h+var_120], rax
0x1401525ee  call    QosFlowUpdateComplete
0x1401525f3  mov     ebx, eax
0x1401525f5  cmp     eax, 103h
0x1401525fa  jnz     short loc_14015266E
0x1401525fc  mov     rcx, [rsi]; Lock
0x1401525ff  lea     rdx, [rsp+140h+LockState]; LockState
0x140152604  mov     r8b, 1; Flags
0x140152607  call    cs:__imp_NdisAcquireRWLockWrite
0x14015260e  nop     dword ptr [rax+rax+00h]
0x140152613  lea     rcx, [rsi+8]
0x140152617  xor     r8d, r8d
0x14015261a  lea     r9, [rsp+140h+var_C8]
0x14015261f  xor     edx, edx
0x140152621  call    QosLineUpdate
0x140152626  mov     rcx, [rsi]; Lock
0x140152629  lea     rdx, [rsp+140h+LockState]; LockState
0x14015262e  mov     ebx, eax
0x140152630  call    cs:__imp_NdisReleaseRWLock
0x140152637  nop     dword ptr [rax+rax+00h]
0x14015263c  lea     rax, [rsp+140h+var_F0]
0x140152641  mov     r9d, ebx
0x140152644  mov     [rsp+140h+var_110], rax
0x140152649  lea     r8, [rbp+40h+var_80]
0x14015264d  lea     rax, [rsp+140h+var_E8]
0x140152652  mov     edx, r15d
0x140152655  mov     [rsp+140h+var_118], rax
0x14015265a  mov     rcx, r13
0x14015265d  lea     rax, [rsp+140h+var_F8]
0x140152662  mov     [rsp+140h+var_120], rax
0x140152667  call    QosFlowUpdateComplete
0x14015266c  mov     ebx, eax
0x14015266e  mov     r8, [rsp+140h+var_F0]
0x140152673  mov     rax, [r14+1D8h]
0x14015267a  mov     [rsp+140h+var_F8], rax
0x14015267f  test    r8, r8
0x140152682  jz      short loc_1401526AB
0x140152684  lea     r9, [rsp+140h+var_E0]
0x140152689  mov     dword ptr [rsp+140h+var_120], 0E0002025h
0x140152691  mov     rdx, rsi
0x140152694  mov     rcx, r14
0x140152697  call    VmsScQosDropNbls
0x14015269c  mov     rcx, [rsp+140h+var_E0]
0x1401526a1  mov     edx, 1
0x1401526a6  call    VmsNblHelperRefCountDecrementMany
0x1401526ab  mov     r13, [rsp+140h+var_E8]
0x1401526b0  test    r13, r13
0x1401526b3  jz      loc_1401527B5
0x1401526b9  lea     r12, [rsi+8]
0x1401526bd  mov     edx, r15d
0x1401526c0  mov     rcx, r12
0x1401526c3  call    QosLineNeedSignal
0x1401526c8  test    al, al
0x1401526ca  jz      short loc_140152702
0x1401526cc  mov     rcx, [rsi]; Lock
0x1401526cf  lea     rdx, [rsp+140h+LockState]; LockState
0x1401526d4  mov     r8b, 1; Flags
0x1401526d7  call    cs:__imp_NdisAcquireRWLockWrite
0x1401526de  nop     dword ptr [rax+rax+00h]
0x1401526e3  mov     edx, r15d
0x1401526e6  mov     rcx, r12
0x1401526e9  call    QosLineSignalExternalEvent
0x1401526ee  mov     rcx, [rsi]; Lock
0x1401526f1  lea     rdx, [rsp+140h+LockState]; LockState
0x1401526f6  call    cs:__imp_NdisReleaseRWLock
0x1401526fd  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
