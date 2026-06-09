# CInputHostLayout::_SendWindowNotifications(HWND__ *,IHM_DISPLAY_MODE)

- ea: `0x180081fb8`
- end: `0x1800826e1`
- name: `?_SendWindowNotifications@CInputHostLayout@@AEAAJPEAUHWND__@@W4IHM_DISPLAY_MODE@@@Z`
- size: `1833`
- prototype: `int __high(HWND, enum IHM_DISPLAY_MODE)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180081f90`

## callees

- `0x18000b7e8`
- `0x18003c1d0`
- `0x18004e1f4`
- `0x180081fb8`
- `0x1800826e8`
- `0x18008275c`
- `0x1800827a8`
- `0x180083be0`
- `0x18013d330`
- `0x180254f98`
- `0x180254fe0`
- `0x180255028`
- `0x1802550c4`
- `0x1802552f0`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180081ff9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180082613`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180081ff9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180082613`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008208d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082642`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008208d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082642`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800820af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800820af`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800825d9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800825d9`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800825c4`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800825c4`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180082104`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180082137`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x18008216a`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180082104`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180082137`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x18008216a`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180082190`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18008219a`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x1800821a4`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18008252d`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180082190`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18008219a`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x1800821a4`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18008252d`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x1800821ff`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18008220d`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18008221b`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x1800821ff`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18008220d`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18008221b`

## pseudocode

```c
__int64 __fastcall CInputHostLayout::_SendWindowNotifications(RTL_SRWLOCK *a1, RTL_SRWLOCK *a2, unsigned int a3)
{
  __int64 v6; // rbx
  RTL_SRWLOCK *v7; // r12
  char *i; // rsi
  __int64 v9; // rsi
  int v10; // r15d
  RTL_SRWLOCK *v11; // rsi
  DWORD v12; // r15d
  CGITRegistrationList *v13; // rsi
  int v14; // r14d
  DWORD v15; // esi
  unsigned int left; // r12d
  __int64 v17; // rcx
  struct IObjectArray *v18; // rcx
  unsigned __int64 v19; // rdx
  int v20; // ecx
  __int64 v21; // rcx
  InputHostManagerTelemetry *v22; // rcx
  unsigned __int64 v23; // rdx
  int v24; // ecx
  __int64 v25; // rcx
  InputHostManagerTelemetry *v26; // rcx
  unsigned __int64 v27; // rdx
  int v28; // ecx
  __int64 v29; // rcx
  InputHostManagerTelemetry *v30; // rcx
  unsigned __int64 v31; // rdx
  int v32; // ecx
  __int64 v33; // rcx
  InputHostManagerTelemetry *v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  DWORD DueTime; // [rsp+40h] [rbp-C0h] BYREF
  int v40; // [rsp+44h] [rbp-BCh]
  __int64 v41; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  int v44; // [rsp+60h] [rbp-A0h]
  int v45; // [rsp+64h] [rbp-9Ch]
  int v46; // [rsp+68h] [rbp-98h]
  struct IObjectArray *v47; // [rsp+70h] [rbp-90h] BYREF
  DWORD Parameter; // [rsp+78h] [rbp-88h] BYREF
  char v49; // [rsp+7Ch] [rbp-84h]
  int v50; // [rsp+80h] [rbp-80h]
  HANDLE Timer; // [rsp+88h] [rbp-78h]
  PSRWLOCK SRWLock; // [rsp+90h] [rbp-70h] BYREF
  CGITRegistrationList *v53; // [rsp+98h] [rbp-68h]
  RTL_SRWLOCK *v54; // [rsp+A0h] [rbp-60h]
  struct tagRECT v55; // [rsp+A8h] [rbp-58h] BYREF
  int v56; // [rsp+B8h] [rbp-48h] BYREF
  struct tagRECT rc; // [rsp+BCh] [rbp-44h] BYREF
  RECT rcSrc; // [rsp+CCh] [rbp-34h] BYREF
  RECT v59; // [rsp+DCh] [rbp-24h] BYREF
  LONG v60; // [rsp+ECh] [rbp-14h]
  struct tagRECT v61; // [rsp+F0h] [rbp-10h] BYREF
  struct tagRECT v62; // [rsp+100h] [rbp+0h] BYREF
  struct tagRECT rcDst; // [rsp+110h] [rbp+10h] BYREF

  SRWLock = a1 + 32;
  AcquireSRWLockExclusive(a1 + 32);
  v6 = 0;
  v7 = a1 + 33;
  v54 = a1 + 33;
  for ( i = 0; ; ++i )
  {
    if ( i >= a1[34].Ptr )
    {
      v10 = -2147319765;
      goto LABEL_11;
    }
    if ( a2 == (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v7->Ptr + (_QWORD)i) + 24LL))(*((_QWORD *)v7->Ptr + (_QWORD)i)) )
      break;
  }
  if ( i >= a1[34].Ptr )
  {
    v10 = -2147316575;
  }
  else
  {
    _mm_lfence();
    v9 = *((_QWORD *)v7->Ptr + (_QWORD)i);
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
      v6 = v9;
    }
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 32LL))(v6);
  }
LABEL_11:
  v11 = a1 + 32;
  v40 = v10;
  ReleaseSRWLockExclusive(a1 + 32);
  if ( v10 >= 0 )
  {
    DueTime = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 64LL))(v6);
    Parameter = GetCurrentThreadId();
    v49 = 0;
    v50 = -2147467259;
    Timer = 0;
    CBaseRPCTimeout::Arm(&Parameter, DueTime);
    v43 = 0;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v43);
    v42 = 0;
    v44 = CoreQueryWindowService(a2, &SID_SystemUIInputHostHandler, &GUID_c91fa253_e03a_45c3_8123_15e348a62f8d, &v43);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v42);
    v41 = 0;
    v45 = CoreQueryWindowService(a2, &SID_InputPaneEventHandler, &GUID_87482e5d_0157_459a_bd7c_cb18085be80f, &v42);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v41);
    v46 = CoreQueryWindowService(
            a2,
            &SID_ApplicationFrameInputPaneEventHandler,
            &GUID_fb45dabf_22c2_43b2_b887_af34b3a857f1,
            &v41);
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&Parameter);
    v56 = 0;
    v60 = 2;
    SetRectEmpty(&rc);
    SetRectEmpty(&rcSrc);
    SetRectEmpty(&v59);
    if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 48LL))(v6, &v56) >= 0 )
    {
      v12 = DueTime;
      v13 = (CGITRegistrationList *)&a1[26];
      v53 = (CGITRegistrationList *)&a1[26];
      do
      {
        v14 = v56;
        v55.left = v60;
        rcDst = 0;
        v62 = 0;
        v61 = 0;
        if ( v56 == 1 )
        {
          CopyRect(&rcDst, &rc);
          CopyRect(&v62, &rcSrc);
          CopyRect(&v61, &v59);
        }
        v47 = 0;
        if ( (int)CGITRegistrationList::GetCallbackArray(v13, &v47) >= 0 )
        {
          DueTime = 0;
          if ( ((int (__fastcall *)(struct IObjectArray *, DWORD *))v47->lpVtbl->GetCount)(v47, &DueTime) >= 0 )
          {
            v15 = 0;
            if ( DueTime )
            {
              left = v55.left;
              do
              {
                *(_QWORD *)&v55.left = 0;
                if ( ((int (__fastcall *)(struct IObjectArray *, _QWORD, GUID *, struct tagRECT *))v47->lpVtbl->GetAt)(
                       v47,
                       v15,
                       &GUID_4fb9f2b9_bdd6_47b9_9ebe_703eacdc1c8e,
                       &v55) >= 0 )
                {
                  if ( v14 == 1 )
                  {
                    (*(void (__fastcall **)(_QWORD, RTL_SRWLOCK *, struct tagRECT *, _QWORD, struct tagRECT *, struct tagRECT *))(**(_QWORD **)&v55.left + 24LL))(
                      *(_QWORD *)&v55.left,
                      a2,
                      &rcDst,
                      left,
                      &v62,
                      &v61);
                  }
                  else if ( v14 == 2 )
                  {
                    (*(void (__fastcall **)(_QWORD, RTL_SRWLOCK *, _QWORD))(**(_QWORD **)&v55.left + 32LL))(
                      *(_QWORD *)&v55.left,
                      a2,
                      left);
                  }
                }
                v17 = *(_QWORD *)&v55.left;
                if ( *(_QWORD *)&v55.left )
                {
                  *(_QWORD *)&v55.left = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
                }
                ++v15;
              }
              while ( v15 < DueTime );
            }
            v13 = v53;
          }
        }
        v18 = v47;
        if ( v47 )
        {
          v47 = 0;
          ((void (__fastcall *)(struct IObjectArray *))v18->lpVtbl->Release)(v18);
        }
        if ( v56 == 1 )
        {
          CBaseRPCTimeout::Arm(&Parameter, v12);
          if ( v44 < 0 )
          {
            if ( v45 >= 0 )
            {
              if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
                McTemplateU0dpdddd_EventWriteTransfer(
                  v28,
                  (unsigned int)ImmersiveShell_InputHost_AppNotification_Start,
                  1,
                  (_DWORD)a2,
                  rc.left,
                  rc.top,
                  rc.right,
                  rc.bottom);
              if ( InputHostManagerTelemetry::IsEnabled(v28, v27) )
              {
                wil::details::static_lazy<InputHostManagerTelemetry>::get(
                  v29,
                  _lambda_d53bed665c4d83ca2776d67ec0cbd1ab_::_lambda_invoker_cdecl_);
                InputHostManagerTelemetry::InputPaneAppNotification_Showing_Start_(v30, (HWND)a2, &rc);
              }
              if ( v46 < 0 )
              {
                v55 = 0;
                SetRectEmpty(&v55);
                (*(void (__fastcall **)(__int64, struct tagRECT *, struct tagRECT *, struct tagRECT *, struct tagRECT *, unsigned int))(*(_QWORD *)v42 + 24LL))(
                  v42,
                  &rc,
                  &v55,
                  &v55,
                  &v55,
                  a3);
              }
              else
              {
                (*(void (__fastcall **)(__int64, RTL_SRWLOCK *, struct tagRECT *, _QWORD))(*(_QWORD *)v41 + 32LL))(
                  v41,
                  a2,
                  &rc,
                  a3);
              }
              if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
                McTemplateU0dpdddd_EventWriteTransfer(
                  v32,
                  (unsigned int)ImmersiveShell_InputHost_AppNotification_Stop,
                  1,
                  (_DWORD)a2,
                  rc.left,
                  rc.top,
                  rc.right,
                  rc.bottom);
              if ( InputHostManagerTelemetry::IsEnabled(v32, v31) )
              {
                wil::details::static_lazy<InputHostManagerTelemetry>::get(
                  v33,
                  _lambda_d53bed665c4d83ca2776d67ec0cbd1ab_::_lambda_invoker_cdecl_);
                InputHostManagerTelemetry::InputPaneAppNotification_Showing_Stop_(v34, (HWND)a2);
              }
            }
          }
          else
          {
            (*(void (__fastcall **)(__int64, struct tagRECT *, _QWORD))(*(_QWORD *)v43 + 24LL))(v43, &rc, a3);
          }
          if ( v50 >= 0 )
          {
            v50 = -2147467259;
            CoDisableCallCancellation(0);
            if ( Timer )
            {
              DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
              Timer = 0;
            }
          }
        }
        else if ( v56 == 2 )
        {
          CBaseRPCTimeout::Arm(&Parameter, v12);
          if ( v44 < 0 )
          {
            if ( v45 >= 0 )
            {
              if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
                McTemplateU0dpdddd_EventWriteTransfer(
                  v20,
                  (unsigned int)ImmersiveShell_InputHost_AppNotification_Start,
                  2,
                  (_DWORD)a2,
                  0,
                  0,
                  0,
                  0);
              if ( InputHostManagerTelemetry::IsEnabled(v20, v19) )
              {
                wil::details::static_lazy<InputHostManagerTelemetry>::get(
                  v21,
                  _lambda_d53bed665c4d83ca2776d67ec0cbd1ab_::_lambda_invoker_cdecl_);
                InputHostManagerTelemetry::InputPaneAppNotification_Hiding_Start_(v22, (HWND)a2);
              }
              if ( v46 < 0 )
                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v42 + 32LL))(v42, a3);
              else
                (*(void (__fastcall **)(__int64, RTL_SRWLOCK *, _QWORD))(*(_QWORD *)v41 + 40LL))(v41, a2, a3);
              if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
                McTemplateU0dpdddd_EventWriteTransfer(
                  v24,
                  (unsigned int)ImmersiveShell_InputHost_AppNotification_Stop,
                  2,
                  (_DWORD)a2,
                  0,
                  0,
                  0,
                  0);
              if ( InputHostManagerTelemetry::IsEnabled(v24, v23) )
              {
                wil::details::static_lazy<InputHostManagerTelemetry>::get(
                  v25,
                  _lambda_d53bed665c4d83ca2776d67ec0cbd1ab_::_lambda_invoker_cdecl_);
                InputHostManagerTelemetry::InputPaneAppNotification_Hiding_Stop_(v26, (HWND)a2);
              }
            }
          }
          else
          {
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v43 + 32LL))(v43, a3);
          }
          CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&Parameter);
        }
      }
      while ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 48LL))(v6, &v56) >= 0 );
      v10 = v40;
      v7 = v54;
      v11 = SRWLock;
    }
    AcquireSRWLockExclusive(v11);
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v6 + 56LL))(v6) )
    {
      SRWLock = a2;
      v10 = CTSimpleArray<Microsoft::WRL::ComPtr<IPerWindowNotificationQueue>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IPerWindowNotificationQueue>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IPerWindowNotificationQueue>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IPerWindowNotificationQueue>>>::RemoveEx<CPerWindowNotificationQueueFinder>(
              v7,
              &SRWLock);
    }
    ReleaseSRWLockExclusive(v11);
    v35 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v36 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    v37 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&Parameter);
  }
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180081fb8  mov     [rsp-8+arg_18], rbx
0x180081fbd  push    rbp
0x180081fbe  push    rsi
0x180081fbf  push    rdi
0x180081fc0  push    r12
0x180081fc2  push    r13
0x180081fc4  push    r14
0x180081fc6  push    r15
0x180081fc8  lea     rbp, [rsp-30h]
0x180081fcd  sub     rsp, 130h
0x180081fd4  mov     rax, cs:__security_cookie
0x180081fdb  xor     rax, rsp
0x180081fde  mov     [rbp+60h+var_40], rax
0x180081fe2  lea     rax, [rcx+100h]
0x180081fe9  mov     r14, rcx
0x180081fec  mov     rcx, rax; SRWLock
0x180081fef  mov     [rbp+60h+SRWLock], rax
0x180081ff3  mov     r13d, r8d
0x180081ff6  mov     rdi, rdx
0x180081ff9  call    cs:__imp_AcquireSRWLockExclusive
0x180081fff  xor     ebx, ebx
0x180082001  lea     r12, [r14+108h]
0x180082008  mov     [rbp+60h+var_C0], r12
0x18008200c  xor     esi, esi
0x18008200e  cmp     rsi, [r12+8]
0x180082013  jnb     short loc_180082078
0x180082015  mov     rax, [r12]
0x180082019  mov     rcx, [rax+rsi*8]
0x18008201d  mov     rax, [rcx]
0x180082020  mov     rax, [rax+18h]
0x180082024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082029  cmp     rdi, rax
0x18008202c  jz      short loc_180082033
0x18008202e  inc     rsi
0x180082031  jmp     short loc_18008200E
0x180082033  cmp     rsi, [r12+8]
0x180082038  jnb     short loc_180082070
0x18008203a  lfence
0x18008203d  mov     rax, [r12]
0x180082041  mov     rsi, [rax+rsi*8]
0x180082045  test    rsi, rsi
0x180082048  jz      short loc_18008205C
0x18008204a  mov     rax, [rsi]
0x18008204d  mov     rcx, rsi
0x180082050  mov     rax, [rax+8]
0x180082054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082059  mov     rbx, rsi
0x18008205c  mov     rax, [rbx]
0x18008205f  mov     rcx, rbx
0x180082062  mov     rax, [rax+20h]
0x180082066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008206b  mov     r15d, eax
0x18008206e  jmp     short loc_18008207E
0x180082070  mov     r15d, 80028CA1h
0x180082076  jmp     short loc_18008207E
0x180082078  mov     r15d, 8002802Bh
0x18008207e  lea     rsi, [r14+100h]
0x180082085  mov     [rsp+160h+var_11C], r15d
0x18008208a  mov     rcx, rsi; SRWLock
0x18008208d  call    cs:__imp_ReleaseSRWLockExclusive
0x180082093  test    r15d, r15d
0x180082096  js      loc_1800826A3
0x18008209c  mov     rax, [rbx]
0x18008209f  mov     rcx, rbx
0x1800820a2  mov     rax, [rax+40h]
0x1800820a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800820ab  mov     [rsp+160h+DueTime], eax
0x1800820af  call    cs:__imp_GetCurrentThreadId
0x1800820b5  mov     edx, [rsp+160h+DueTime]; DueTime
0x1800820b9  lea     rcx, [rsp+160h+Parameter]; Parameter
0x1800820be  mov     [rsp+160h+Parameter], eax
0x1800820c2  mov     [rsp+160h+var_E4], 0
0x1800820c7  mov     [rbp+60h+var_E0], 80004005h
0x1800820ce  mov     [rbp+60h+Timer], 0
0x1800820d6  call    ?Arm@CBaseRPCTimeout@@QEAAXK@Z; CBaseRPCTimeout::Arm(ulong)
0x1800820db  lea     rcx, [rsp+160h+var_108]
0x1800820e0  mov     [rsp+160h+var_108], 0
0x1800820e9  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800820ee  lea     r9, [rsp+160h+var_108]
0x1800820f3  mov     rcx, rdi
0x1800820f6  lea     r8, _GUID_c91fa253_e03a_45c3_8123_15e348a62f8d
0x1800820fd  lea     rdx, SID_SystemUIInputHostHandler
0x180082104  call    cs:__imp_CoreQueryWindowService
0x18008210a  lea     rcx, [rsp+160h+var_110]
0x18008210f  mov     [rsp+160h+var_110], 0
0x180082118  mov     [rsp+160h+var_100], eax
0x18008211c  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180082121  lea     r9, [rsp+160h+var_110]
0x180082126  mov     rcx, rdi
0x180082129  lea     r8, _GUID_87482e5d_0157_459a_bd7c_cb18085be80f
0x180082130  lea     rdx, SID_InputPaneEventHandler
0x180082137  call    cs:__imp_CoreQueryWindowService
0x18008213d  lea     rcx, [rsp+160h+var_118]
0x180082142  mov     [rsp+160h+var_118], 0
0x18008214b  mov     [rsp+160h+var_FC], eax
0x18008214f  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180082154  lea     r9, [rsp+160h+var_118]
0x180082159  mov     rcx, rdi
0x18008215c  lea     r8, _GUID_fb45dabf_22c2_43b2_b887_af34b3a857f1
0x180082163  lea     rdx, SID_ApplicationFrameInputPaneEventHandler
0x18008216a  call    cs:__imp_CoreQueryWindowService
0x180082170  lea     rcx, [rsp+160h+Parameter]; this
0x180082175  mov     [rsp+160h+var_F8], eax
0x180082179  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x18008217e  lea     rcx, [rbp+60h+rc]; lprc
0x180082182  mov     [rbp+60h+var_A8], 0
0x180082189  mov     [rbp+60h+var_74], 2
0x180082190  call    cs:__imp_SetRectEmpty
0x180082196  lea     rcx, [rbp+60h+rcSrc]; lprc
0x18008219a  call    cs:__imp_SetRectEmpty
0x1800821a0  lea     rcx, [rbp+60h+var_84]; lprc
0x1800821a4  call    cs:__imp_SetRectEmpty
0x1800821aa  mov     rcx, [rbx]
0x1800821ad  lea     rdx, [rbp+60h+var_A8]
0x1800821b1  mov     rax, [rcx+30h]
0x1800821b5  mov     rcx, rbx
0x1800821b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800821bd  test    eax, eax
0x1800821bf  js      loc_18008260D
0x1800821c5  mov     r15d, [rsp+160h+DueTime]
0x1800821ca  lea     rsi, [r14+0D0h]
0x1800821d1  mov     [rbp+60h+var_C8], rsi
0x1800821d5  mov     r14d, [rbp+60h+var_A8]
0x1800821d9  xorps   xmm0, xmm0
0x1800821dc  mov     eax, [rbp+60h+var_74]
0x1800821df  xorps   xmm1, xmm1
0x1800821e2  mov     [rbp+60h+var_B8.left], eax
0x1800821e5  movups  xmmword ptr [rbp+60h+rcDst.left], xmm0
0x1800821e9  movups  xmmword ptr [rbp+60h+var_60.left], xmm1
0x1800821ed  movups  xmmword ptr [rbp+60h+var_70.left], xmm0
0x1800821f1  cmp     r14d, 1
0x1800821f5  jnz     short loc_180082221
0x1800821f7  lea     rdx, [rbp+60h+rc]; lprcSrc
0x1800821fb  lea     rcx, [rbp+60h+rcDst]; lprcDst
0x1800821ff  call    cs:__imp_CopyRect
0x180082205  lea     rdx, [rbp+60h+rcSrc]; lprcSrc
0x180082209  lea     rcx, [rbp+60h+var_60]; lprcDst
0x18008220d  call    cs:__imp_CopyRect
0x180082213  lea     rdx, [rbp+60h+var_84]; lprcSrc
0x180082217  lea     rcx, [rbp+60h+var_70]; lprcDst
0x18008221b  call    cs:__imp_CopyRect
0x180082221  xor     r12d, r12d
0x180082224  lea     rdx, [rsp+160h+var_F0]; struct IObjectArray **
0x180082229  mov     rcx, rsi; this
0x18008222c  mov     [rsp+160h+var_F0], r12
0x180082231  call    ?GetCallbackArray@CGITRegistrationList@@QEAAJPEAPEAUIObjectArray@@@Z; CGITRegistrationList::GetCallbackArray(IObjectArray * *)
0x180082236  test    eax, eax
0x180082238  js      loc_18008231B
0x18008223e  mov     rcx, [rsp+160h+var_F0]
0x180082243  lea     rdx, [rsp+160h+DueTime]
0x180082248  mov     [rsp+160h+DueTime], r12d
0x18008224d  mov     rax, [rcx]
0x180082250  mov     rax, [rax+18h]
0x180082254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082259  test    eax, eax
0x18008225b  js      loc_18008231B
0x180082261  mov     esi, r12d
0x180082264  cmp     [rsp+160h+DueTime], r12d
0x180082269  jbe     loc_180082317
0x18008226f  mov     r12d, [rbp+60h+var_B8.left]
0x180082273  mov     rcx, [rsp+160h+var_F0]
0x180082278  lea     r9, [rbp+60h+var_B8]
0x18008227c  mov     qword ptr [rbp+60h+var_B8.left], 0
0x180082284  lea     r8, _GUID_4fb9f2b9_bdd6_47b9_9ebe_703eacdc1c8e
0x18008228b  mov     edx, esi
0x18008228d  mov     rax, [rcx]
0x180082290  mov     rax, [rax+20h]
0x180082294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082299  test    eax, eax
0x18008229b  js      short loc_1800822EE
0x18008229d  mov     ecx, r14d
0x1800822a0  sub     ecx, 1
0x1800822a3  jz      short loc_1800822C2
0x1800822a5  cmp     ecx, 1
0x1800822a8  jnz     short loc_1800822EE
0x1800822aa  mov     rcx, qword ptr [rbp+60h+var_B8.left]
0x1800822ae  mov     r8d, r12d
0x1800822b1  mov     rdx, rdi
0x1800822b4  mov     rax, [rcx]
0x1800822b7  mov     rax, [rax+20h]
0x1800822bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800822c0  jmp     short loc_1800822EE
0x1800822c2  mov     rcx, qword ptr [rbp+60h+var_B8.left]
0x1800822c6  lea     rdx, [rbp+60h+var_70]
0x1800822ca  mov     [rsp+160h+var_138], rdx
0x1800822cf  lea     r8, [rbp+60h+rcDst]
0x1800822d3  lea     rdx, [rbp+60h+var_60]
0x1800822d7  mov     r9d, r12d
0x1800822da  mov     [rsp+160h+var_140], rdx
0x1800822df  mov     rdx, rdi
0x1800822e2  mov     rax, [rcx]
0x1800822e5  mov     rax, [rax+18h]
0x1800822e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800822ee  mov     rcx, qword ptr [rbp+60h+var_B8.left]
0x1800822f2  test    rcx, rcx
0x1800822f5  jz      short loc_18008230B
0x1800822f7  mov     qword ptr [rbp+60h+var_B8.left], 0
0x1800822ff  mov     rax, [rcx]
0x180082302  mov     rax, [rax+10h]
0x180082306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008230b  inc     esi
0x18008230d  cmp     esi, [rsp+160h+DueTime]
0x180082311  jb      loc_180082273
0x180082317  mov     rsi, [rbp+60h+var_C8]
0x18008231b  mov     rcx, [rsp+160h+var_F0]
0x180082320  xor     r14d, r14d
0x180082323  test    rcx, rcx
0x180082326  jz      short loc_180082339
0x180082328  mov     [rsp+160h+var_F0], r14
0x18008232d  mov     rax, [rcx]
0x180082330  mov     rax, [rax+10h]
0x180082334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082339  mov     ecx, [rbp+60h+var_A8]
0x18008233c  sub     ecx, 1
0x18008233f  jz      loc_180082467
0x180082345  cmp     ecx, 1
0x180082348  jnz     loc_1800825E3
0x18008234e  mov     edx, r15d; DueTime
0x180082351  lea     rcx, [rsp+160h+Parameter]; Parameter
0x180082356  call    ?Arm@CBaseRPCTimeout@@QEAAXK@Z; CBaseRPCTimeout::Arm(ulong)
0x18008235b  cmp     [rsp+160h+var_100], r14d
0x180082360  jl      short loc_18008237B
0x180082362  mov     rcx, [rsp+160h+var_108]
0x180082367  mov     edx, r13d
0x18008236a  mov     rax, [rcx]
0x18008236d  mov     rax, [rax+20h]
0x180082371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082376  jmp     loc_180082458
0x18008237b  cmp     [rsp+160h+var_FC], r14d
0x180082380  jl      loc_180082458
0x180082386  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x18008238d  jz      short loc_1800823B8
0x18008238f  mov     [rsp+160h+var_128], r14d
0x180082394  lea     rdx, ImmersiveShell_InputHost_AppNotification_Start
0x18008239b  mov     [rsp+160h+var_130], r14d
0x1800823a0  mov     r9, rdi
0x1800823a3  mov     dword ptr [rsp+160h+var_138], r14d
0x1800823a8  mov     r8d, 2
0x1800823ae  mov     dword ptr [rsp+160h+var_140], r14d
0x1800823b3  call    McTemplateU0dpdddd_EventWriteTransfer
0x1800823b8  call    ?IsEnabled@InputHostManagerTelemetry@@SA_NE_K@Z; InputHostManagerTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800823bd  test    al, al
0x1800823bf  jz      short loc_1800823D5
0x1800823c1  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d53bed665c4d83ca2776d67ec0cbd1ab_@@CA@XZ; _lambda_d53bed665c4d83ca2776d67ec0cbd1ab_::_lambda_invoker_cdecl_(void)
0x1800823c8  call    ?get@?$static_lazy@VInputHostManagerTelemetry@@@details@wil@@QEAAPEAVInputHostManagerTelemetry@@P6AXXZ@Z; wil::details::static_lazy<InputHostManagerTelemetry>::get(void (*)(void))
0x1800823cd  mov     rdx, rdi; HWND
0x1800823d0  call    ?InputPaneAppNotification_Hiding_Start_@InputHostManagerTelemetry@@QEBAXPEAUHWND__@@@Z; InputHostManagerTelemetry::InputPaneAppNotification_Hiding_Start_(HWND__ *)
0x1800823d5  cmp     [rsp+160h+var_F8], r14d
0x1800823da  jl      short loc_1800823F5
0x1800823dc  mov     rcx, [rsp+160h+var_118]
0x1800823e1  mov     r8d, r13d
0x1800823e4  mov     rdx, rdi
0x1800823e7  mov     rax, [rcx]
0x1800823ea  mov     rax, [rax+28h]
0x1800823ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800823f3  jmp     short loc_180082409
0x1800823f5  mov     rcx, [rsp+160h+var_110]
0x1800823fa  mov     edx, r13d
0x1800823fd  mov     rax, [rcx]
0x180082400  mov     rax, [rax+20h]
0x180082404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082409  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x180082410  jz      short loc_18008243B
0x180082412  mov     [rsp+160h+var_128], r14d
0x180082417  lea     rdx, ImmersiveShell_InputHost_AppNotification_Stop
0x18008241e  mov     [rsp+160h+var_130], r14d
0x180082423  mov     r9, rdi
0x180082426  mov     dword ptr [rsp+160h+var_138], r14d
0x18008242b  mov     r8d, 2
0x180082431  mov     dword ptr [rsp+160h+var_140], r14d
0x180082436  call    McTemplateU0dpdddd_EventWriteTransfer
0x18008243b  call    ?IsEnabled@InputHostManagerTelemetry@@SA_NE_K@Z; InputHostManagerTelemetry::IsEnabled(uchar,unsigned __int64)
0x180082440  test    al, al
0x180082442  jz      short loc_180082458
0x180082444  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d53bed665c4d83ca2776d67ec0cbd1ab_@@CA@XZ; _lambda_d53bed665c4d83ca2776d67ec0cbd1ab_::_lambda_invoker_cdecl_(void)
0x18008244b  call    ?get@?$static_lazy@VInputHostManagerTelemetry@@@details@wil@@QEAAPEAVInputHostManagerTelemetry@@P6AXXZ@Z; wil::details::static_lazy<InputHostManagerTelemetry>::get(void (*)(void))
0x180082450  mov     rdx, rdi; HWND
0x180082453  call    ?InputPaneAppNotification_Hiding_Stop_@InputHostManagerTelemetry@@QEBAXPEAUHWND__@@@Z; InputHostManagerTelemetry::InputPaneAppNotification_Hiding_Stop_(HWND__ *)
0x180082458  lea     rcx, [rsp+160h+Parameter]; this
0x18008245d  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x180082462  jmp     loc_1800825E3
0x180082467  mov     edx, r15d; DueTime
0x18008246a  lea     rcx, [rsp+160h+Parameter]; Parameter
0x18008246f  call    ?Arm@CBaseRPCTimeout@@QEAAXK@Z; CBaseRPCTimeout::Arm(ulong)
0x180082474  cmp     [rsp+160h+var_100], r14d
0x180082479  jl      short loc_180082498
0x18008247b  mov     rcx, [rsp+160h+var_108]
0x180082480  lea     rdx, [rbp+60h+rc]
0x180082484  mov     r8d, r13d
0x180082487  mov     rax, [rcx]
0x18008248a  mov     rax, [rax+18h]
0x18008248e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082493  jmp     loc_1800825B5
0x180082498  cmp     [rsp+160h+var_FC], r14d
0x18008249d  jl      loc_1800825B5
0x1800824a3  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x1800824aa  jz      short loc_1800824DD
0x1800824ac  mov     eax, [rbp+60h+rc.bottom]
0x1800824af  lea     rdx, ImmersiveShell_InputHost_AppNotification_Start
0x1800824b6  mov     [rsp+160h+var_128], eax
  ... truncated ...
```
