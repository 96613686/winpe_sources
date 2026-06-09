# WorkThreadManager::s_QueuePoolTask(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,Windows::Internal::IComPoolTask *)

- ea: `0x18000debc`
- end: `0x18000e2b3`
- name: `?s_QueuePoolTask@WorkThreadManager@@CAJW4TaskApartment@Internal@Windows@@W4TaskOptions@34@KPEAUIComPoolTask@34@@Z`
- size: `1015`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000d6bc`
- `0x18000dad0`

## callees

- `0x18000debc`
- `0x18000ed80`
- `0x18000f008`
- `0x18000f740`
- `0x18000f808`
- `0x18000f888`
- `0x180010274`
- `0x180019dd0`
- `0x180037590`
- `0x1800375b0`
- `0x1800377ac`
- `0x1800536ac`
- `0x180053bd8`
- `0x18006a800`
- `0x18006cf94`
- `0x18006cfc0`
- `0x18006d008`
- `0x18006d8cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000dff6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000dff6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000df09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e017`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000df09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e017`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000df74`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e044`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000df74`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000df7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000df7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e1ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e1ac`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000e24e`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000e24e`
- `combase!CoSetOutgoingCallState` at `0x18000e1c0`
- `combase!CoSetOutgoingCallState` at `0x18000e1c0`

## string_xrefs

- `0x18000e12c`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18000e16d`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18000e1de`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18000e216`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18000e265`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WorkThreadManager::s_QueuePoolTask(unsigned int a1, unsigned int a2, unsigned int a3, int a4)
{
  void *v8; // rbx
  int v9; // eax
  int v10; // edi
  DWORD LastError; // edi
  RTL_SRWLOCK *v12; // rdi
  DWORD v13; // esi
  _lambda_daf6045f3beb3c81c9b84f3d6c685eeb_ *v14; // rax
  DWORD v15; // eax
  unsigned int v16; // r8d
  const char *v17; // r9
  int v19; // eax
  unsigned int v20; // ebx
  int v21; // eax
  WorkThreadManager::TaskData *v22; // rax
  unsigned int v23; // edx
  HRESULT v24; // eax
  WorkThreadManager::TaskData *v25; // rax
  unsigned int v26; // edx
  int lpdwindex; // [rsp+20h] [rbp-59h]
  int lpdwindexa; // [rsp+20h] [rbp-59h]
  int lpdwindexb; // [rsp+20h] [rbp-59h]
  RTL_SRWLOCK *v30; // [rsp+48h] [rbp-31h] BYREF
  void *v31; // [rsp+50h] [rbp-29h] BYREF
  HANDLE pHandles[2]; // [rsp+58h] [rbp-21h] BYREF
  __int64 v33; // [rsp+68h] [rbp-11h] BYREF
  _QWORD v34[2]; // [rsp+70h] [rbp-9h] BYREF
  _BYTE v35[80]; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  DWORD dwindex; // [rsp+E8h] [rbp+6Fh] BYREF

  v8 = 0;
  v31 = 0;
  v34[1] = v34;
  v34[0] = v34;
  AcquireSRWLockExclusive(&WorkThreadManager::s_rwLock);
  v30 = &WorkThreadManager::s_rwLock;
  if ( (a2 & 0x60) != 0 )
  {
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v31,
      WorkThreadManager::s_hEventCache);
    WorkThreadManager::s_hEventCache = 0;
    v8 = v31;
    if ( !v31 )
    {
      v19 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
              &v31,
              0);
      v20 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x456,
          (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
          (const char *)(unsigned int)v19,
          lpdwindex);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v30);
        WorkThreadManager::TaskList::Clear((WorkThreadManager::TaskList *)v34);
        goto LABEL_19;
      }
      v8 = v31;
    }
  }
  dwindex = 0;
  lpdwindexa = a4;
  v9 = WorkThreadManager::s_QueuePoolTaskUnderLock(v8, a1, a2, a3);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45E,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)(unsigned int)v9,
      lpdwindexa);
LABEL_20:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v30);
    WorkThreadManager::TaskList::Clear((WorkThreadManager::TaskList *)v34);
    v20 = v10;
LABEL_19:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v31);
    return v20;
  }
  LastError = GetLastError();
  ReleaseSRWLockExclusive(&WorkThreadManager::s_rwLock);
  SetLastError(LastError);
  v12 = 0;
  v30 = 0;
  while ( (_QWORD *)v34[0] != v34 )
  {
    v22 = WorkThreadManager::TaskList::RawRemoveHead((WorkThreadManager::TaskList *)v34);
    if ( v22 )
      WorkThreadManager::TaskData::`scalar deleting destructor'(v22, v23);
  }
  v13 = dwindex;
  if ( !v8 )
    goto LABEL_12;
  v33 = 0;
  LOBYTE(dwindex) = 0;
  if ( v13 )
  {
    pHandles[0] = (HANDLE)__PAIR64__(v13, GetCurrentProcessId());
    v21 = CoSetOutgoingCallState(pHandles, &v33);
    if ( v21 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x47B,
        (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
        (const char *)(unsigned int)v21,
        lpdwindexa);
    else
      LOBYTE(dwindex) = 1;
  }
  v14 = _lambda_daf6045f3beb3c81c9b84f3d6c685eeb_::_lambda_daf6045f3beb3c81c9b84f3d6c685eeb_(
          (_lambda_daf6045f3beb3c81c9b84f3d6c685eeb_ *)pHandles,
          (const bool *)&dwindex,
          (const struct tagOutgoingCallData *)&v33);
  wil::scope_exit<_lambda_daf6045f3beb3c81c9b84f3d6c685eeb_>(v35, v14);
  if ( (a2 & 0x40) == 0 )
  {
    if ( (a2 & 0x20) != 0 )
    {
      v15 = WaitForSingleObjectEx(v8, 0xFFFFFFFF, 0);
      if ( v15 != 258 )
      {
        if ( v15 )
          wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v16, v17);
      }
    }
    goto LABEL_11;
  }
  dwindex = 0;
  pHandles[0] = v8;
  v24 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, pHandles, &dwindex);
  v10 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48A,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)(unsigned int)v24,
      lpdwindexb);
    wil::details::lambda_call<_lambda_daf6045f3beb3c81c9b84f3d6c685eeb_>::~lambda_call<_lambda_daf6045f3beb3c81c9b84f3d6c685eeb_>(v35);
    goto LABEL_20;
  }
LABEL_11:
  wil::details::lambda_call<_lambda_daf6045f3beb3c81c9b84f3d6c685eeb_>::~lambda_call<_lambda_daf6045f3beb3c81c9b84f3d6c685eeb_>(v35);
  AcquireSRWLockExclusive(&WorkThreadManager::s_rwLock);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
    &v30,
    &WorkThreadManager::s_rwLock);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &WorkThreadManager::s_hEventCache,
    v8);
  v12 = v30;
LABEL_12:
  if ( v12 )
    ReleaseSRWLockExclusive(v12);
  while ( (_QWORD *)v34[0] != v34 )
  {
    v25 = WorkThreadManager::TaskList::RawRemoveHead((WorkThreadManager::TaskList *)v34);
    if ( v25 )
      WorkThreadManager::TaskData::`scalar deleting destructor'(v25, v26);
  }
  return 0;
}

```

## disassembly

```asm
0x18000debc  push    rbp
0x18000debe  push    rbx
0x18000debf  push    rsi
0x18000dec0  push    rdi
0x18000dec1  push    r12
0x18000dec3  push    r13
0x18000dec5  push    r14
0x18000dec7  push    r15
0x18000dec9  lea     rbp, [rsp-1Fh]
0x18000dece  sub     rsp, 98h
0x18000ded5  mov     rdi, r9
0x18000ded8  mov     esi, r8d
0x18000dedb  mov     r14d, edx
0x18000dede  mov     r15d, ecx
0x18000dee1  xor     r12d, r12d
0x18000dee4  mov     ebx, r12d
0x18000dee7  mov     [rbp+57h+var_80], rbx
0x18000deeb  mov     [rbp+57h+var_90], r12
0x18000deef  lea     rax, [rbp+57h+var_60]
0x18000def3  mov     [rbp+57h+var_58], rax
0x18000def7  lea     rax, [rbp+57h+var_60]
0x18000defb  mov     [rbp+57h+var_60], rax
0x18000deff  lea     r13, ?s_rwLock@WorkThreadManager@@0Vsrwlock@wil@@A; wil::srwlock WorkThreadManager::s_rwLock
0x18000df06  mov     rcx, r13; SRWLock
0x18000df09  call    cs:__imp_AcquireSRWLockExclusive
0x18000df0f  mov     [rbp+57h+var_88], r13
0x18000df13  test    r14b, 60h
0x18000df17  jnz     loc_18000E094
0x18000df1d  mov     [rbp+57h+dwindex], r12d
0x18000df21  mov     rcx, [rbp+57h+var_90]
0x18000df25  test    rcx, rcx
0x18000df28  jnz     loc_18000E0DD
0x18000df2e  lea     rax, [rbp+57h+dwindex]
0x18000df32  mov     [rsp+0D0h+var_98], rax
0x18000df37  lea     rax, [rbp+57h+var_90]
0x18000df3b  mov     [rsp+0D0h+var_A0], rax
0x18000df40  lea     rax, [rbp+57h+var_60]
0x18000df44  mov     [rsp+0D0h+var_A8], rax
0x18000df49  mov     [rsp+0D0h+lpdwindex], rdi; int
0x18000df4e  mov     r9d, esi
0x18000df51  mov     r8d, r14d
0x18000df54  mov     edx, r15d
0x18000df57  mov     rcx, rbx
0x18000df5a  call    ?s_QueuePoolTaskUnderLock@WorkThreadManager@@CAJPEAXW4TaskApartment@Internal@Windows@@W4TaskOptions@34@KPEAUIComPoolTask@34@PEAVTaskList@1@PEAPEAVCThread@1@AEAK@Z; WorkThreadManager::s_QueuePoolTaskUnderLock(void *,Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,Windows::Internal::IComPoolTask *,WorkThreadManager::TaskList *,WorkThreadManager::CThread * *,ulong &)
0x18000df5f  mov     edi, eax
0x18000df61  test    eax, eax
0x18000df63  js      loc_18000E1D7
0x18000df69  call    cs:__imp_GetLastError
0x18000df6f  mov     edi, eax
0x18000df71  mov     rcx, r13; SRWLock
0x18000df74  call    cs:__imp_ReleaseSRWLockExclusive
0x18000df7a  mov     ecx, edi; dwErrCode
0x18000df7c  call    cs:__imp_SetLastError
0x18000df82  mov     rdi, r12
0x18000df85  mov     [rbp+57h+var_88], r12
0x18000df89  lea     rax, [rbp+57h+var_60]
0x18000df8d  cmp     [rbp+57h+var_60], rax
0x18000df91  jnz     loc_18000E1F4
0x18000df97  mov     rcx, [rbp+57h+var_90]; this
0x18000df9b  test    rcx, rcx
0x18000df9e  jnz     loc_18000E078
0x18000dfa4  mov     esi, [rbp+57h+dwindex]
0x18000dfa7  test    rbx, rbx
0x18000dfaa  jz      loc_18000E03C
0x18000dfb0  mov     [rbp+57h+var_68], r12
0x18000dfb4  mov     byte ptr [rbp+57h+dwindex], r12b
0x18000dfb8  test    esi, esi
0x18000dfba  jnz     loc_18000E1AC
0x18000dfc0  lea     r8, [rbp+57h+var_68]; struct tagOutgoingCallData *
0x18000dfc4  lea     rdx, [rbp+57h+dwindex]; bool *
0x18000dfc8  lea     rcx, [rbp+57h+pHandles]; this
0x18000dfcc  call    ??0_lambda_daf6045f3beb3c81c9b84f3d6c685eeb_@@QEAA@AEB_NAEBUtagOutgoingCallData@@@Z; _lambda_daf6045f3beb3c81c9b84f3d6c685eeb_::_lambda_daf6045f3beb3c81c9b84f3d6c685eeb_(bool const &,tagOutgoingCallData const &)
0x18000dfd1  mov     rdx, rax
0x18000dfd4  lea     rcx, [rbp+57h+var_50]
0x18000dfd8  call    ??$scope_exit@V_lambda_daf6045f3beb3c81c9b84f3d6c685eeb_@@@wil@@YA?A_P$$QEAV_lambda_daf6045f3beb3c81c9b84f3d6c685eeb_@@@Z
0x18000dfdd  test    r14b, 40h
0x18000dfe1  jnz     loc_18000E22C
0x18000dfe7  test    r14b, 20h
0x18000dfeb  jz      short loc_18000E00B
0x18000dfed  xor     r8d, r8d; bAlertable
0x18000dff0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000dff3  mov     rcx, rbx; hHandle
0x18000dff6  call    cs:__imp_WaitForSingleObjectEx
0x18000dffc  cmp     eax, 102h
0x18000e001  jz      short loc_18000E00B
0x18000e003  test    eax, eax
0x18000e005  jnz     loc_18000E284
0x18000e00b  lea     rcx, [rbp+57h+var_50]
0x18000e00f  call    ??1?$lambda_call@V_lambda_daf6045f3beb3c81c9b84f3d6c685eeb_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_daf6045f3beb3c81c9b84f3d6c685eeb_>::~lambda_call<_lambda_daf6045f3beb3c81c9b84f3d6c685eeb_>(void)
0x18000e014  mov     rcx, r13; SRWLock
0x18000e017  call    cs:__imp_AcquireSRWLockExclusive
0x18000e01d  mov     rdx, r13
0x18000e020  lea     rcx, [rbp+57h+var_88]
0x18000e024  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18000e029  mov     rdx, rbx
0x18000e02c  lea     rcx, ?s_hEventCache@WorkThreadManager@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@A
0x18000e033  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000e038  mov     rdi, [rbp+57h+var_88]
0x18000e03c  test    rdi, rdi
0x18000e03f  jz      short loc_18000E04B
0x18000e041  mov     rcx, rdi; SRWLock
0x18000e044  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e04a  nop
0x18000e04b  lea     rax, [rbp+57h+var_60]
0x18000e04f  cmp     [rbp+57h+var_60], rax
0x18000e053  jnz     loc_18000E293
0x18000e059  mov     rcx, [rbp+57h+var_90]
0x18000e05d  test    rcx, rcx
0x18000e060  jnz     short loc_18000E0D2
0x18000e062  xor     eax, eax
0x18000e064  add     rsp, 98h
0x18000e06b  pop     r15
0x18000e06d  pop     r14
0x18000e06f  pop     r13
0x18000e071  pop     r12
0x18000e073  pop     rdi
0x18000e074  pop     rsi
0x18000e075  pop     rbx
0x18000e076  pop     rbp
0x18000e077  retn
0x18000e078  call    ?WaitForThreadStart@CThread@WorkThreadManager@@QEAAJXZ; WorkThreadManager::CThread::WaitForThreadStart(void)
0x18000e07d  nop
0x18000e07e  mov     esi, eax
0x18000e080  test    eax, eax
0x18000e082  js      loc_18000E166
0x18000e088  mov     rax, [rbp+57h+var_90]
0x18000e08c  mov     esi, [rax+50h]
0x18000e08f  jmp     loc_18000DFA7
0x18000e094  mov     rdx, cs:?s_hEventCache@WorkThreadManager@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@A
0x18000e09b  lea     rcx, [rbp+57h+var_80]
0x18000e09f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000e0a4  mov     cs:?s_hEventCache@WorkThreadManager@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@A, r12
0x18000e0ab  mov     rbx, [rbp+57h+var_80]
0x18000e0af  test    rbx, rbx
0x18000e0b2  jnz     loc_18000DF1D
0x18000e0b8  xor     edx, edx
0x18000e0ba  lea     rcx, [rbp+57h+var_80]
0x18000e0be  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000e0c3  mov     ebx, eax
0x18000e0c5  test    eax, eax
0x18000e0c7  js      short loc_18000E125
0x18000e0c9  mov     rbx, [rbp+57h+var_80]
0x18000e0cd  jmp     loc_18000DF1D
0x18000e0d2  mov     [rbp+57h+var_90], r12
0x18000e0d6  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000e0db  jmp     short loc_18000E062
0x18000e0dd  mov     [rbp+57h+var_90], r12
0x18000e0e1  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000e0e6  jmp     loc_18000DF2E
0x18000e0eb  mov     ebx, edi
0x18000e0ed  lea     rcx, [rbp+57h+var_80]
0x18000e0f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e0f6  mov     eax, ebx
0x18000e0f8  jmp     loc_18000E064
0x18000e0fd  lea     rcx, [rbp+57h+var_88]
0x18000e101  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18000e106  nop
0x18000e107  lea     rcx, [rbp+57h+var_60]; this
0x18000e10b  call    ?Clear@TaskList@WorkThreadManager@@QEAAXXZ; WorkThreadManager::TaskList::Clear(void)
0x18000e110  nop
0x18000e111  mov     rcx, [rbp+57h+var_90]
0x18000e115  test    rcx, rcx
0x18000e118  jz      short loc_18000E0EB
0x18000e11a  mov     [rbp+57h+var_90], r12
0x18000e11e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000e123  jmp     short loc_18000E0EB
0x18000e125  mov     rcx, [rbp+5Fh]; this
0x18000e129  mov     r9d, eax; char *
0x18000e12c  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000e133  mov     edx, 456h; void *
0x18000e138  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e13d  nop
0x18000e13e  lea     rcx, [rbp+57h+var_88]
0x18000e142  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18000e147  nop
0x18000e148  lea     rcx, [rbp+57h+var_60]; this
0x18000e14c  call    ?Clear@TaskList@WorkThreadManager@@QEAAXXZ; WorkThreadManager::TaskList::Clear(void)
0x18000e151  nop
0x18000e152  mov     rcx, [rbp+57h+var_90]
0x18000e156  test    rcx, rcx
0x18000e159  jz      short loc_18000E0ED
0x18000e15b  mov     [rbp+57h+var_90], r12
0x18000e15f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000e164  jmp     short loc_18000E0ED
0x18000e166  mov     rcx, [rbp+5Fh]; this
0x18000e16a  mov     r9d, esi; char *
0x18000e16d  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000e174  mov     edx, 467h; void *
0x18000e179  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e17e  nop
0x18000e17f  lea     rcx, [rbp+57h+var_88]
0x18000e183  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18000e188  nop
0x18000e189  lea     rcx, [rbp+57h+var_60]; this
0x18000e18d  call    ?Clear@TaskList@WorkThreadManager@@QEAAXXZ; WorkThreadManager::TaskList::Clear(void)
0x18000e192  nop
0x18000e193  mov     rcx, [rbp+57h+var_90]
0x18000e197  test    rcx, rcx
0x18000e19a  jz      short loc_18000E1A5
0x18000e19c  mov     [rbp+57h+var_90], r12
0x18000e1a0  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000e1a5  mov     ebx, esi
0x18000e1a7  jmp     loc_18000E0ED
0x18000e1ac  call    cs:__imp_GetCurrentProcessId
0x18000e1b2  mov     dword ptr [rbp+57h+pHandles], eax
0x18000e1b5  mov     dword ptr [rbp+57h+pHandles+4], esi
0x18000e1b8  lea     rdx, [rbp+57h+var_68]
0x18000e1bc  lea     rcx, [rbp+57h+pHandles]
0x18000e1c0  call    cs:__imp_CoSetOutgoingCallState
0x18000e1c6  mov     rcx, [rbp+5Fh]; this
0x18000e1ca  test    eax, eax
0x18000e1cc  js      short loc_18000E213
0x18000e1ce  mov     byte ptr [rbp+57h+dwindex], 1
0x18000e1d2  jmp     loc_18000DFC0
0x18000e1d7  mov     rcx, [rbp+5Fh]; this
0x18000e1db  mov     r9d, edi; char *
0x18000e1de  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000e1e5  mov     edx, 45Eh; void *
0x18000e1ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e1ef  jmp     loc_18000E0FD
0x18000e1f4  lea     rcx, [rbp+57h+var_60]; this
0x18000e1f8  call    ?RawRemoveHead@TaskList@WorkThreadManager@@AEAAPEAUTaskData@2@XZ; WorkThreadManager::TaskList::RawRemoveHead(void)
0x18000e1fd  test    rax, rax
0x18000e200  jz      loc_18000DF89
0x18000e206  mov     rcx, rax; this
0x18000e209  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x18000e20e  jmp     loc_18000DF89
0x18000e213  mov     r9d, eax; char *
0x18000e216  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000e21d  mov     edx, 47Bh; void *
0x18000e222  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e227  jmp     loc_18000DFC0
0x18000e22c  mov     [rbp+57h+dwindex], r12d
0x18000e230  mov     [rbp+57h+pHandles], rbx
0x18000e234  lea     rax, [rbp+57h+dwindex]
0x18000e238  mov     [rsp+0D0h+lpdwindex], rax; int
0x18000e23d  lea     r9, [rbp+57h+pHandles]; pHandles
0x18000e241  mov     r8d, 1; cHandles
0x18000e247  or      edx, 0FFFFFFFFh; dwTimeout
0x18000e24a  lea     ecx, [r8+7]; dwFlags
0x18000e24e  call    cs:__imp_CoWaitForMultipleHandles
0x18000e254  mov     edi, eax
0x18000e256  test    eax, eax
0x18000e258  jns     loc_18000E00B
0x18000e25e  mov     rcx, [rbp+5Fh]; this
0x18000e262  mov     r9d, eax; char *
0x18000e265  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000e26c  mov     edx, 48Ah; void *
0x18000e271  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e276  lea     rcx, [rbp+57h+var_50]
0x18000e27a  call    ??1?$lambda_call@V_lambda_daf6045f3beb3c81c9b84f3d6c685eeb_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_daf6045f3beb3c81c9b84f3d6c685eeb_>::~lambda_call<_lambda_daf6045f3beb3c81c9b84f3d6c685eeb_>(void)
0x18000e27f  jmp     loc_18000E0FD
0x18000e284  mov     rcx, [rbp+5Fh]; this
0x18000e288  mov     edx, 0B0Fh; void *
0x18000e28d  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000e293  lea     rcx, [rbp+57h+var_60]; this
0x18000e297  call    ?RawRemoveHead@TaskList@WorkThreadManager@@AEAAPEAUTaskData@2@XZ; WorkThreadManager::TaskList::RawRemoveHead(void)
0x18000e29c  test    rax, rax
0x18000e29f  jz      loc_18000E04B
0x18000e2a5  mov     rcx, rax; this
0x18000e2a8  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x18000e2ad  jmp     loc_18000E04B
```
