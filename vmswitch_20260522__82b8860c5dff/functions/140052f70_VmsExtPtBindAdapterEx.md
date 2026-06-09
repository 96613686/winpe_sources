# VmsExtPtBindAdapterEx

- ea: `0x140052f70`
- end: `0x140053432`
- name: `VmsExtPtBindAdapterEx`
- size: `1218`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14001484c`
- `0x140027a64`
- `0x14002e45c`
- `0x14003a450`
- `0x14004f5d8`
- `0x140052460`
- `0x140052f70`
- `0x140053438`
- `0x1400535dc`
- `0x1400538c4`
- `0x14006b084`
- `0x14006b990`
- `0x14006ea20`
- `0x14008497c`
- `0x140089714`
- `0x1400f044c`
- `0x1401043ec`
- `0x14015cf30`
- `0x1401bbc40`

## import_xrefs

- `NDIS!NdisWaitEvent` at `0x1400530a7`
- `NDIS!NdisWaitEvent` at `0x1400530a7`
- `NDIS!NdisOpenAdapterEx` at `0x14005308c`
- `NDIS!NdisOpenAdapterEx` at `0x14005308c`
- `NDIS!NdisResetEvent` at `0x140053033`
- `NDIS!NdisResetEvent` at `0x140053033`
- `NDIS!NdisReleaseRWLock` at `0x14005313c`
- `NDIS!NdisReleaseRWLock` at `0x1400531b4`
- `NDIS!NdisReleaseRWLock` at `0x1400532fd`
- `NDIS!NdisReleaseRWLock` at `0x1400533b9`
- `NDIS!NdisReleaseRWLock` at `0x14005313c`
- `NDIS!NdisReleaseRWLock` at `0x1400531b4`
- `NDIS!NdisReleaseRWLock` at `0x1400532fd`
- `NDIS!NdisReleaseRWLock` at `0x1400533b9`
- `NDIS!NdisAcquireRWLockWrite` at `0x140053113`
- `NDIS!NdisAcquireRWLockWrite` at `0x140053176`
- `NDIS!NdisAcquireRWLockWrite` at `0x140053245`
- `NDIS!NdisAcquireRWLockWrite` at `0x140053113`
- `NDIS!NdisAcquireRWLockWrite` at `0x140053176`
- `NDIS!NdisAcquireRWLockWrite` at `0x140053245`

## pseudocode

```c
__int64 __fastcall VmsExtPtBindAdapterEx(char a1, void *a2, __int64 a3)
{
  __int64 v6; // rcx
  __int64 SwitchByExtMiniportAdapterInfo; // rax
  int v8; // edx
  __int64 v9; // rbx
  int v10; // edx
  struct _NDIS_EVENT *v11; // rsi
  NDIS_STATUS v12; // eax
  int v13; // edx
  int v14; // r8d
  struct _NDIS_RW_LOCK_EX *v15; // rcx
  char v16; // si
  int v17; // edx
  struct _NDIS_RW_LOCK_EX *v18; // rcx
  struct _NDIS_RW_LOCK_EX *v19; // rcx
  __int64 v20; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp-59h] BYREF
  unsigned int v23; // [rsp+54h] [rbp-55h]
  int v24; // [rsp+58h] [rbp-51h] BYREF
  int v25; // [rsp+5Ch] [rbp-4Dh] BYREF
  PVOID NdisBindingHandle; // [rsp+60h] [rbp-49h] BYREF
  _NDIS_OPEN_PARAMETERS OpenParameters; // [rsp+68h] [rbp-41h] BYREF
  __int128 v28; // [rsp+A0h] [rbp-9h] BYREF
  _BYTE v29[24]; // [rsp+B0h] [rbp+7h] BYREF

  v23 = -1073741823;
  v25 = 0;
  NdisBindingHandle = 0;
  v6 = *(_QWORD *)(a3 + 16);
  memset(v29, 0, 22);
  *(_WORD *)&LockState.OldIrql = 0;
  memset(&OpenParameters, 0, 52);
  LockState.Flags = 0;
  v24 = 0;
  v28 = 0;
  SwitchByExtMiniportAdapterInfo = VmsOmpFindSwitchByExtMiniportAdapterInfo(v6, 0, 0);
  v9 = SwitchByExtMiniportAdapterInfo;
  if ( SwitchByExtMiniportAdapterInfo )
  {
    v11 = (struct _NDIS_EVENT *)(SwitchByExtMiniportAdapterInfo + 5144);
    NdisResetEvent((PNDIS_EVENT)(SwitchByExtMiniportAdapterInfo + 5144));
    OpenParameters.AdapterName = *(PNDIS_STRING *)(a3 + 16);
    *(_QWORD *)&OpenParameters.Header.Type = 3670407;
    OpenParameters.MediumArray = (PNDIS_MEDIUM)&dword_1401FA18C;
    OpenParameters.SelectedMediumIndex = (PUINT)&v25;
    *(_QWORD *)&OpenParameters.MediumArraySize = 1;
    *(_QWORD *)&OpenParameters.FrameTypeArraySize = 0;
    OpenParameters.FrameTypeArray = 0;
    v12 = NdisOpenAdapterEx(VmsVswitchProtocolHandle, (NDIS_HANDLE)v9, &OpenParameters, a2, &NdisBindingHandle);
    v23 = v12;
    if ( v12 == 259 )
    {
      NdisWaitEvent(v11, 0);
      v12 = *(_DWORD *)(v9 + 5168);
      v23 = v12;
    }
    if ( v12 )
    {
      WPP_RECORDER_SF_qqqqd(
        VmsIfrLog,
        v13,
        v14,
        11,
        (__int64)WPP_c69d984230f533cb421e05600cf3b8f5_Traceguids,
        (char)VmsVswitchProtocolHandle,
        v9,
        (char)&OpenParameters,
        (char)a2,
        v12);
    }
    else
    {
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v9 + 56), &LockState, 0);
      v15 = *(struct _NDIS_RW_LOCK_EX **)(v9 + 56);
      *(_QWORD *)(v9 + 4288) = NdisBindingHandle;
      *(_DWORD *)(v9 + 4272) = 1;
      NdisReleaseRWLock(v15, &LockState);
      v23 = VmsExtMpNotifySwitchActivation(v9);
      if ( v23 || *(_DWORD *)(v9 + 4272) != 2 )
      {
        v23 = -1073741823;
        VmsEtwTraceSwitchFailure(&VM_SWITCH_EXT_ACTIVATE_FAILED, 0, v9 + 72, v9 + 616);
      }
      else
      {
        v16 = 0;
        NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v9 + 56), &LockState, 0);
        if ( (unsigned __int8)VmsPtCheckIsEmbeddedTeamingEnabled(0, v9)
          && !*(_BYTE *)(v9 + 8992)
          && !*(_QWORD *)(v9 + 9000) )
        {
          *(_BYTE *)(v9 + 8992) = 1;
          v16 = 1;
        }
        NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v9 + 56), &LockState);
        if ( v16 )
        {
          v28 = 0;
          memset(v29, 0, sizeof(v29));
          *((_QWORD *)&v28 + 1) = *(_QWORD *)(v9 + 8968);
          v29[20] = 1;
          VmsTmTeamInitialize(v9, &v28, 0);
          *(_BYTE *)(v9 + 8992) = 0;
        }
        v24 = 65551;
        VmsEptPvtProcessPrivateOid(NdisBindingHandle, (__int64)&v24, 4, 0, 0);
        NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v9 + 56), &LockState, 0);
        if ( !*(_DWORD *)(a3 + 160) )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            v17,
            19,
            12,
            (__int64)WPP_c69d984230f533cb421e05600cf3b8f5_Traceguids,
            (__int64)"BindParams->BoundIfIndex != 0");
          if ( !*(_DWORD *)(a3 + 160) )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        if ( !*(_DWORD *)(a3 + 176) )
        {
          WPP_RECORDER_SF_s(
            VmsIfrLog,
            v17,
            19,
            13,
            (__int64)WPP_c69d984230f533cb421e05600cf3b8f5_Traceguids,
            (__int64)"BindParams->LowestIfIndex != 0");
          if ( !*(_DWORD *)(a3 + 176) )
            MicrosoftTelemetryAssertTriggeredNoArgsKM();
        }
        v18 = *(struct _NDIS_RW_LOCK_EX **)(v9 + 56);
        *(_DWORD *)(v9 + 5136) = *(_DWORD *)(a3 + 160);
        *(_DWORD *)(v9 + 5140) = *(_DWORD *)(a3 + 176);
        NdisReleaseRWLock(v18, &LockState);
        VmsOmSwitchRefreshFilterList(v9);
        if ( (_QWORD)xmmword_1401FB3E0 )
          VmsPktMonRegisterExtNic(v9);
      }
    }
  }
  else
  {
    v23 = -1073741823;
    LOBYTE(v8) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v8, 20, 10, (__int64)WPP_c69d984230f533cb421e05600cf3b8f5_Traceguids, 1);
  }
  if ( v23 )
  {
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_qqqd(
      VmsIfrLog,
      v10,
      20,
      14,
      (__int64)WPP_c69d984230f533cb421e05600cf3b8f5_Traceguids,
      a1,
      (char)a2,
      a3,
      v23);
    if ( v9 )
    {
      VmsOmObjectLockExclusive(v9, &LockState, 0);
      v19 = *(struct _NDIS_RW_LOCK_EX **)(v9 + 56);
      *(_DWORD *)(v9 + 4272) = 4;
      NdisReleaseRWLock(v19, &LockState);
      VmsExtMpDequeueAllStatusNotifications(v9);
      VmsOmpObjectDereference(v9, 0);
    }
  }
  else
  {
    if ( v9 )
      v20 = *(_QWORD *)(v9 + 9096);
    else
      LODWORD(v20) = VmsIfrLog;
    WPP_RECORDER_SF_qZ(
      v20,
      v10,
      1,
      15,
      (__int64)WPP_c69d984230f533cb421e05600cf3b8f5_Traceguids,
      v9,
      *(_QWORD *)(a3 + 16));
  }
  return v23;
}

```

## disassembly

```asm
0x140052f70  push    rbp
0x140052f72  push    rbx
0x140052f73  push    rsi
0x140052f74  push    rdi
0x140052f75  push    r12
0x140052f77  push    r14
0x140052f79  push    r15
0x140052f7b  lea     rbp, [rsp-27h]
0x140052f80  sub     rsp, 0D0h
0x140052f87  mov     rax, cs:__security_cookie
0x140052f8e  xor     rax, rsp
0x140052f91  mov     [rbp+57h+var_38], rax
0x140052f95  xorps   xmm0, xmm0
0x140052f98  mov     [rbp+57h+var_AC], 0C0000001h
0x140052f9f  xor     eax, eax
0x140052fa1  mov     rdi, r8
0x140052fa4  xor     r12d, r12d
0x140052fa7  mov     [rbp+57h+OpenParameters.FrameTypeArraySize], eax
0x140052faa  mov     r14, rdx
0x140052fad  mov     [rbp+57h+var_A4], r12d
0x140052fb1  mov     r15, rcx
0x140052fb4  mov     [rbp+57h+var_A0], r12
0x140052fb8  mov     rcx, [rdi+10h]
0x140052fbc  xor     r8d, r8d
0x140052fbf  movups  [rbp+57h+var_50], xmm0
0x140052fc3  xor     edx, edx
0x140052fc5  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x140052fc9  movups  xmmword ptr [rbp+57h+OpenParameters.Header.Type], xmm0
0x140052fcd  mov     [rbp+57h+LockState.Flags], al
0x140052fd0  movups  xmmword ptr [rbp+57h+OpenParameters.MediumArray], xmm0
0x140052fd4  mov     [rbp+57h+var_A8], r12d
0x140052fd8  movups  xmmword ptr [rbp+57h+OpenParameters.SelectedMediumIndex], xmm0
0x140052fdc  mov     qword ptr [rbp+57h+var_50+0Eh], rax
0x140052fe0  movups  [rbp+57h+var_60], xmm0
0x140052fe4  call    VmsOmpFindSwitchByExtMiniportAdapterInfo
0x140052fe9  lea     rsi, WPP_c69d984230f533cb421e05600cf3b8f5_Traceguids
0x140052ff0  mov     rbx, rax
0x140052ff3  test    rax, rax
0x140052ff6  jnz     short loc_140053029
0x140052ff8  mov     [rbp+57h+var_AC], 0C0000001h
0x140052fff  mov     rcx, cs:VmsIfrLog
0x140053006  lea     r9d, [r12+0Ah]
0x14005300b  mov     dword ptr [rsp+100h+var_D8], 0C0000001h
0x140053013  lea     r8d, [r12+14h]
0x140053018  mov     dl, 2
0x14005301a  mov     [rsp+100h+NdisBindingHandle], rsi
0x14005301f  call    WPP_RECORDER_SF_d
0x140053024  jmp     loc_14005335C
0x140053029  lea     rsi, [rax+1418h]
0x140053030  mov     rcx, rsi; Event
0x140053033  call    cs:__imp_NdisResetEvent
0x14005303a  nop     dword ptr [rax+rax+00h]
0x14005303f  mov     rax, [rdi+10h]
0x140053043  lea     r8, [rbp+57h+OpenParameters]; OpenParameters
0x140053047  mov     rcx, cs:VmsVswitchProtocolHandle; NdisProtocolHandle
0x14005304e  mov     r9, r14; BindContext
0x140053051  mov     [rbp+57h+OpenParameters.AdapterName], rax
0x140053055  mov     rdx, rbx; ProtocolBindingContext
0x140053058  lea     rax, dword_1401FA18C
0x14005305f  mov     qword ptr [rbp+57h+OpenParameters.Header.Type], 380187h
0x140053067  mov     [rbp+57h+OpenParameters.MediumArray], rax
0x14005306b  lea     rax, [rbp+57h+var_A4]
0x14005306f  mov     [rbp+57h+OpenParameters.SelectedMediumIndex], rax
0x140053073  lea     rax, [rbp+57h+var_A0]
0x140053077  mov     [rsp+100h+NdisBindingHandle], rax; NdisBindingHandle
0x14005307c  mov     qword ptr [rbp+57h+OpenParameters.MediumArraySize], 1
0x140053084  mov     qword ptr [rbp+57h+OpenParameters.FrameTypeArraySize], r12
0x140053088  mov     [rbp+57h+OpenParameters.FrameTypeArray], r12
0x14005308c  call    cs:__imp_NdisOpenAdapterEx
0x140053093  nop     dword ptr [rax+rax+00h]
0x140053098  mov     [rbp+57h+var_AC], eax
0x14005309b  cmp     eax, 103h
0x1400530a0  jnz     short loc_1400530BC
0x1400530a2  xor     edx, edx; MsToWait
0x1400530a4  mov     rcx, rsi; Event
0x1400530a7  call    cs:__imp_NdisWaitEvent
0x1400530ae  nop     dword ptr [rax+rax+00h]
0x1400530b3  mov     eax, [rbx+1430h]
0x1400530b9  mov     [rbp+57h+var_AC], eax
0x1400530bc  mov     ecx, eax
0x1400530be  test    eax, eax
0x1400530c0  jz      short loc_140053108
0x1400530c2  mov     rcx, cs:VmsIfrLog
0x1400530c9  lea     rsi, WPP_c69d984230f533cb421e05600cf3b8f5_Traceguids
0x1400530d0  mov     [rsp+100h+var_B8], eax
0x1400530d4  mov     r9d, 0Bh
0x1400530da  mov     [rsp+100h+var_C0], r14
0x1400530df  lea     rax, [rbp+57h+OpenParameters]
0x1400530e3  mov     [rsp+100h+var_C8], rax
0x1400530e8  mov     rax, cs:VmsVswitchProtocolHandle
0x1400530ef  mov     [rsp+100h+var_D0], rbx
0x1400530f4  mov     [rsp+100h+var_D8], rax
0x1400530f9  mov     [rsp+100h+NdisBindingHandle], rsi
0x1400530fe  call    WPP_RECORDER_SF_qqqqd
0x140053103  jmp     loc_14005335C
0x140053108  mov     rcx, [rbx+38h]; Lock
0x14005310c  lea     rdx, [rbp+57h+LockState]; LockState
0x140053110  xor     r8d, r8d; Flags
0x140053113  call    cs:__imp_NdisAcquireRWLockWrite
0x14005311a  nop     dword ptr [rax+rax+00h]
0x14005311f  mov     rax, [rbp+57h+var_A0]
0x140053123  lea     rdx, [rbp+57h+LockState]; LockState
0x140053127  mov     rcx, [rbx+38h]; Lock
0x14005312b  mov     [rbx+10C0h], rax
0x140053132  mov     dword ptr [rbx+10B0h], 1
0x14005313c  call    cs:__imp_NdisReleaseRWLock
0x140053143  nop     dword ptr [rax+rax+00h]
0x140053148  mov     rcx, rbx
0x14005314b  call    VmsExtMpNotifySwitchActivation
0x140053150  mov     [rbp+57h+var_AC], eax
0x140053153  test    eax, eax
0x140053155  jnz     loc_140053324
0x14005315b  cmp     dword ptr [rbx+10B0h], 2
0x140053162  jnz     loc_140053324
0x140053168  mov     rcx, [rbx+38h]; Lock
0x14005316c  lea     rdx, [rbp+57h+LockState]; LockState
0x140053170  xor     r8d, r8d; Flags
0x140053173  mov     sil, r12b
0x140053176  call    cs:__imp_NdisAcquireRWLockWrite
0x14005317d  nop     dword ptr [rax+rax+00h]
0x140053182  mov     rdx, rbx
0x140053185  xor     ecx, ecx
0x140053187  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x14005318c  test    al, al
0x14005318e  jz      short loc_1400531AC
0x140053190  cmp     [rbx+2320h], r12b
0x140053197  jnz     short loc_1400531AC
0x140053199  cmp     [rbx+2328h], r12
0x1400531a0  jnz     short loc_1400531AC
0x1400531a2  mov     byte ptr [rbx+2320h], 1
0x1400531a9  mov     sil, 1
0x1400531ac  mov     rcx, [rbx+38h]; Lock
0x1400531b0  lea     rdx, [rbp+57h+LockState]; LockState
0x1400531b4  call    cs:__imp_NdisReleaseRWLock
0x1400531bb  nop     dword ptr [rax+rax+00h]
0x1400531c0  test    sil, sil
0x1400531c3  jz      short loc_140053202
0x1400531c5  xor     eax, eax
0x1400531c7  lea     rdx, [rbp+57h+var_60]
0x1400531cb  mov     [rbp+57h+var_40], rax
0x1400531cf  xorps   xmm0, xmm0
0x1400531d2  movups  [rbp+57h+var_60], xmm0
0x1400531d6  xor     r8d, r8d
0x1400531d9  mov     rcx, rbx
0x1400531dc  movups  [rbp+57h+var_50], xmm0
0x1400531e0  mov     eax, [rbx+2308h]
0x1400531e6  mov     dword ptr [rbp+57h+var_60+8], eax
0x1400531e9  mov     eax, [rbx+230Ch]
0x1400531ef  mov     dword ptr [rbp+57h+var_60+0Ch], eax
0x1400531f2  mov     byte ptr [rbp+57h+var_40+4], 1
0x1400531f6  call    VmsTmTeamInitialize
0x1400531fb  mov     [rbx+2320h], r12b
0x140053202  mov     rcx, [rbp+57h+var_A0]
0x140053206  lea     rax, [rbp+57h+var_A8]
0x14005320a  mov     dword ptr [rsp+100h+var_C8], r12d
0x14005320f  xor     r9d, r9d
0x140053212  mov     [rsp+100h+var_D0], r12
0x140053217  mov     r8d, 1010Eh
0x14005321d  mov     dword ptr [rsp+100h+var_D8], 4
0x140053225  mov     [rbp+57h+var_A8], 1000Fh
0x14005322c  lea     edx, [r9+1]
0x140053230  mov     [rsp+100h+NdisBindingHandle], rax
0x140053235  call    VmsEptPvtProcessPrivateOid
0x14005323a  mov     rcx, [rbx+38h]; Lock
0x14005323e  lea     rdx, [rbp+57h+LockState]; LockState
0x140053242  xor     r8d, r8d; Flags
0x140053245  call    cs:__imp_NdisAcquireRWLockWrite
0x14005324c  nop     dword ptr [rax+rax+00h]
0x140053251  cmp     [rdi+0A0h], r12d
0x140053258  jnz     short loc_140053298
0x14005325a  mov     rcx, cs:VmsIfrLog
0x140053261  lea     rax, aBindparamsBoun; "BindParams->BoundIfIndex != 0"
0x140053268  mov     r9d, 0Ch
0x14005326e  mov     [rsp+100h+var_D8], rax
0x140053273  lea     rsi, WPP_c69d984230f533cb421e05600cf3b8f5_Traceguids
0x14005327a  mov     [rsp+100h+NdisBindingHandle], rsi
0x14005327f  lea     r8d, [r9+7]
0x140053283  call    WPP_RECORDER_SF_s
0x140053288  cmp     [rdi+0A0h], r12d
0x14005328f  jnz     short loc_14005329F
0x140053291  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "BindParams->BoundIfIndex != 0")
0x140053296  jmp     short loc_14005329F
0x140053298  lea     rsi, WPP_c69d984230f533cb421e05600cf3b8f5_Traceguids
0x14005329f  cmp     [rdi+0B0h], r12d
0x1400532a6  jnz     short loc_1400532DD
0x1400532a8  mov     rcx, cs:VmsIfrLog
0x1400532af  lea     rax, aBindparamsLowe; "BindParams->LowestIfIndex != 0"
0x1400532b6  mov     r9d, 0Dh
0x1400532bc  mov     [rsp+100h+var_D8], rax
0x1400532c1  mov     [rsp+100h+NdisBindingHandle], rsi
0x1400532c6  lea     r8d, [r9+6]
0x1400532ca  call    WPP_RECORDER_SF_s
0x1400532cf  cmp     [rdi+0B0h], r12d
0x1400532d6  jnz     short loc_1400532DD
0x1400532d8  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "BindParams->LowestIfIndex != 0")
0x1400532dd  mov     eax, [rdi+0A0h]
0x1400532e3  lea     rdx, [rbp+57h+LockState]; LockState
0x1400532e7  mov     rcx, [rbx+38h]; Lock
0x1400532eb  mov     [rbx+1410h], eax
0x1400532f1  mov     eax, [rdi+0B0h]
0x1400532f7  mov     [rbx+1414h], eax
0x1400532fd  call    cs:__imp_NdisReleaseRWLock
0x140053304  nop     dword ptr [rax+rax+00h]
0x140053309  mov     rcx, rbx
0x14005330c  call    VmsOmSwitchRefreshFilterList
0x140053311  cmp     qword ptr cs:xmmword_1401FB3E0, r12
0x140053318  jz      short loc_14005335C
0x14005331a  mov     rcx, rbx
0x14005331d  call    VmsPktMonRegisterExtNic
0x140053322  jmp     short loc_14005335C
0x140053324  lea     rax, [rbx+268h]
0x14005332b  mov     [rbp+57h+var_AC], 0C0000001h
0x140053332  mov     [rsp+100h+var_D0], rax; __int64
0x140053337  lea     rcx, [rbx+48h]
0x14005333b  mov     [rsp+100h+var_D8], rcx; __int64
0x140053340  lea     r9, [rbp+57h+var_AC]
0x140053344  lea     rcx, VM_SWITCH_EXT_ACTIVATE_FAILED; EventDescriptor
0x14005334b  mov     dword ptr [rsp+100h+NdisBindingHandle], r12d; char
0x140053350  call    VmsEtwTraceSwitchFailure
0x140053355  lea     rsi, WPP_c69d984230f533cb421e05600cf3b8f5_Traceguids
0x14005335c  mov     eax, [rbp+57h+var_AC]
0x14005335f  test    eax, eax
0x140053361  jz      short loc_1400533D9
0x140053363  mov     rcx, cs:VmsIfrLog
0x14005336a  mov     r9d, 0Eh
0x140053370  mov     dword ptr [rsp+100h+var_C0], eax
0x140053374  mov     dl, 2
0x140053376  mov     [rsp+100h+var_C8], rdi
0x14005337b  mov     [rsp+100h+var_D0], r14
0x140053380  lea     r8d, [r9+6]
0x140053384  mov     [rsp+100h+var_D8], r15
0x140053389  mov     [rsp+100h+NdisBindingHandle], rsi
0x14005338e  call    WPP_RECORDER_SF_qqqd
0x140053393  test    rbx, rbx
0x140053396  jz      short loc_140053410
0x140053398  xor     r8d, r8d
0x14005339b  lea     rdx, [rbp+57h+LockState]
0x14005339f  mov     rcx, rbx
0x1400533a2  call    VmsOmObjectLockExclusive
0x1400533a7  mov     rcx, [rbx+38h]; Lock
0x1400533ab  lea     rdx, [rbp+57h+LockState]; LockState
0x1400533af  mov     dword ptr [rbx+10B0h], 4
0x1400533b9  call    cs:__imp_NdisReleaseRWLock
0x1400533c0  nop     dword ptr [rax+rax+00h]
0x1400533c5  mov     rcx, rbx
0x1400533c8  call    VmsExtMpDequeueAllStatusNotifications
0x1400533cd  xor     edx, edx
0x1400533cf  mov     rcx, rbx
0x1400533d2  call    VmsOmpObjectDereference
0x1400533d7  jmp     short loc_140053410
0x1400533d9  test    rbx, rbx
0x1400533dc  jz      short loc_1400533E7
0x1400533de  mov     rcx, [rbx+2388h]
0x1400533e5  jmp     short loc_1400533EE
0x1400533e7  mov     rcx, cs:VmsIfrLog
0x1400533ee  mov     rax, [rdi+10h]
0x1400533f2  mov     r9d, 0Fh
0x1400533f8  mov     [rsp+100h+var_D0], rax
0x1400533fd  mov     [rsp+100h+var_D8], rbx
0x140053402  mov     [rsp+100h+NdisBindingHandle], rsi
0x140053407  lea     r8d, [r9-0Eh]
0x14005340b  call    WPP_RECORDER_SF_qZ
0x140053410  mov     eax, [rbp+57h+var_AC]
0x140053413  mov     rcx, [rbp+57h+var_38]
0x140053417  xor     rcx, rsp; StackCookie
0x14005341a  call    __security_check_cookie
0x14005341f  add     rsp, 0D0h
0x140053426  pop     r15
0x140053428  pop     r14
0x14005342a  pop     r12
0x14005342c  pop     rdi
0x14005342d  pop     rsi
0x14005342e  pop     rbx
0x14005342f  pop     rbp
0x140053430  retn
```
