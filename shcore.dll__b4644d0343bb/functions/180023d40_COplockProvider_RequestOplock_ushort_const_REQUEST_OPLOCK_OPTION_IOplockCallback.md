# COplockProvider::RequestOplock(ushort const *,REQUEST_OPLOCK_OPTION,IOplockCallback *)

- ea: `0x180023d40`
- end: `0x180024168`
- name: `?RequestOplock@COplockProvider@@UEAAJPEBGW4REQUEST_OPLOCK_OPTION@@PEAUIOplockCallback@@@Z`
- size: `1064`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18001261c`
- `0x180023414`
- `0x180023d40`
- `0x180024170`
- `0x180024224`
- `0x180024254`
- `0x180024304`
- `0x1800243b0`
- `0x18002440c`
- `0x1800254d8`
- `0x1800255d4`
- `0x18002570c`
- `0x18002572c`
- `0x18002578c`
- `0x1800259e8`
- `0x180026cb4`
- `0x180035720`
- `0x18003f05c`
- `0x180042be4`
- `0x180047a2c`
- `0x18004fd80`
- `0x180053bd8`
- `0x180054410`
- `0x180082f78`
- `0x1800831bc`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ebb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ebb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023f18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023f18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002405e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024119`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002405e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024119`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180023e1e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180023e1e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180024009`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180024009`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180023e81`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180023e81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800240fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800240fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall COplockProvider::RequestOplock(char *a1, const unsigned __int16 *a2, int a3, void *a4)
{
  char *v8; // r15
  int v9; // ebx
  __int64 v10; // rcx
  wil::TraceLoggingProvider *v11; // rax
  unsigned __int8 v12; // dl
  unsigned __int64 v13; // r8
  __int64 v14; // rcx
  SHCoreOplockTelemetry *v15; // rcx
  signed __int32 v16; // eax
  int DriveNumberW; // eax
  int v18; // eax
  char *File2; // rbx
  struct _TP_TIMER *v20; // r12
  COplockProvider *v21; // rcx
  signed int v22; // edi
  unsigned int v23; // edx
  const char *v24; // r9
  DWORD LastError; // edi
  __int64 v26; // rdi
  LPWSTR ExtensionW; // rax
  int v28; // eax
  __int64 v29; // rdi
  int v31; // [rsp+20h] [rbp-99h]
  char v32; // [rsp+30h] [rbp-89h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-81h] BYREF
  signed __int32 v34; // [rsp+40h] [rbp-79h] BYREF
  char *v35; // [rsp+48h] [rbp-71h] BYREF
  _QWORD v36[3]; // [rsp+50h] [rbp-69h] BYREF
  char v37; // [rsp+68h] [rbp-51h]
  struct _GUID v38; // [rsp+70h] [rbp-49h] BYREF
  _OWORD v39[2]; // [rsp+80h] [rbp-39h] BYREF
  char v40[8]; // [rsp+A0h] [rbp-19h] BYREF
  char v41[48]; // [rsp+A8h] [rbp-11h] BYREF
  LPVOID v42; // [rsp+D8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v8 = a1 + 264;
  tip2::tip_test<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>::start_and_watch_errors(
    a1 + 264,
    v40);
  v38 = *(struct _GUID *)((char *)v42 + 152);
  v9 = *((_DWORD *)a1 + 62);
  v11 = (wil::TraceLoggingProvider *)wil::details::static_lazy<SHCoreOplockTelemetry>::get(
                                       v10,
                                       _lambda_ec6e2907394b4434fdfb8b987aa4b821_::_lambda_invoker_cdecl_);
  if ( wil::TraceLoggingProvider::IsEnabled_(v11, v12, v13) )
  {
    wil::details::static_lazy<SHCoreOplockTelemetry>::get(
      v14,
      _lambda_ec6e2907394b4434fdfb8b987aa4b821_::_lambda_invoker_cdecl_);
    SHCoreOplockTelemetry::RequestOplockStart_(v15, a1, v9, a4, a2);
  }
  v16 = _InterlockedCompareExchange((volatile signed __int32 *)a1 + 62, 1, 0);
  v34 = v16;
  if ( v16 )
  {
    LODWORD(pv) = v16;
    v35 = a1;
    SHCoreOplockTelemetry::RequestOplockInvalidStartState<COplockProvider *,int>(&v35, &pv);
    v26 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>::ensure_data(v8);
    pv = (LPVOID)v26;
    if ( v26 )
      _InterlockedAdd((volatile signed __int32 *)(v26 + 280), 1u);
    tip2::details::shared_data<1,0,0>::begin_update(v26 + 8);
    *(_DWORD *)(v26 + 272) = 5;
    tip2::details::shared_data<1,0,0>::end_update(v26 + 8);
    wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>,wil::err_returncode_policy>::reset(&pv);
    if ( pv )
      tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>::Release(pv);
    tip2::tip_test<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>::complete(v8);
    v22 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x258,
      (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\oplock.cpp",
      (const char *)0x8007139FLL,
      v31);
    goto LABEL_26;
  }
  v32 = 0;
  v36[0] = &v32;
  v36[1] = a1;
  v36[2] = &v34;
  v37 = 1;
  if ( (*(int (__fastcall **)(char *, const unsigned __int16 *))(*(_QWORD *)a1 + 24LL))(a1, a2) < 0
    || (DriveNumberW = PathGetDriveNumberW(a2), (unsigned int)(DriveType(DriveNumberW) - 2) > 1) )
  {
    v32 = 1;
    v22 = 1;
    goto LABEL_48;
  }
  memset(v39, 0, sizeof(v39));
  LODWORD(v39[0]) = 32;
  v18 = 1076101120;
  if ( a3 != 1 )
    v18 = 1074003968;
  DWORD2(v39[0]) = v18;
  *((_QWORD *)a1 + 37) = a2;
  COplockProvider::StartCreateFileCallbackTimer(a1);
  File2 = (char *)CreateFile2(a2, 0x80000000LL, 1, 3, v39);
  v35 = File2;
  v20 = (struct _TP_TIMER *)*((_QWORD *)a1 + 35);
  if ( v20 )
  {
    LastError = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v20);
    SetLastError(LastError);
  }
  *((_QWORD *)a1 + 35) = 0;
  *((_QWORD *)a1 + 37) = 0;
  if ( ((unsigned __int64)(File2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_28;
  v22 = GetLastError();
  if ( v22 <= 0 )
    v23 = v22;
  else
    v23 = (unsigned __int16)v22 | 0x80070000;
  if ( COplockProvider::ShouldSuppressCreateFileError(v21, v23, &v38) )
  {
    v32 = 1;
    if ( v22 )
    {
      if ( v22 > 0 )
        v22 = (unsigned __int16)v22 | 0x80070000;
      goto LABEL_46;
    }
  }
  if ( ((unsigned __int64)(File2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
LABEL_28:
    ExtensionW = PathFindExtensionW(a2);
    if ( *ExtensionW )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &pv,
        ExtensionW);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        a1 + 240,
        &pv);
      if ( pv )
        CoTaskMemFree(pv);
    }
    v28 = COplockProvider::RequestOplockOnHandleInternal(
            (COplockProvider *)a1,
            File2,
            (struct IOplockCallback *)a4,
            &v38);
    if ( !v28 )
      goto LABEL_32;
    if ( v28 == 1 )
    {
      v32 = 1;
      v22 = 1;
    }
    else
    {
      if ( v28 >= 0 )
      {
LABEL_32:
        CloseHandle(File2);
        v29 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>::ensure_data(v8);
        pv = (LPVOID)v29;
        if ( v29 )
          _InterlockedIncrement((volatile signed __int32 *)(v29 + 280));
        tip2::details::shared_data<1,0,0>::begin_update(v29 + 8);
        *(_DWORD *)(v29 + 272) = 3;
        tip2::details::shared_data<1,0,0>::end_update(v29 + 8);
        wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>,wil::err_returncode_policy>::reset(&pv);
        if ( pv )
          tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>::Release(pv);
        tip2::tip_test<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>::complete(v8);
        if ( v42 )
          tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>::Release(v42);
        v22 = 0;
        goto LABEL_39;
      }
      v22 = v28;
    }
LABEL_46:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
LABEL_48:
    v37 = 0;
    lambda_26cd70ff2e96c6105ba1d23aa9312e48_::operator()(v36);
    tip2::test_watcher<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>::~test_watcher<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>(v40);
    return (unsigned int)v22;
  }
  v22 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x291,
          (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\oplock.cpp",
          v24);
  if ( (unsigned __int64)(File2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(File2);
  v37 = 0;
  lambda_26cd70ff2e96c6105ba1d23aa9312e48_::operator()(v36);
LABEL_26:
  if ( v42 )
    tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>::Release(v42);
LABEL_39:
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v41);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180023d40  mov     [rsp-8+arg_10], rbx
0x180023d45  push    rbp
0x180023d46  push    rsi
0x180023d47  push    rdi
0x180023d48  push    r12
0x180023d4a  push    r13
0x180023d4c  push    r14
0x180023d4e  push    r15
0x180023d50  lea     rbp, [rsp-27h]
0x180023d55  sub     rsp, 0E0h
0x180023d5c  mov     r13, r9
0x180023d5f  mov     edi, r8d
0x180023d62  mov     r14, rdx
0x180023d65  mov     rsi, rcx
0x180023d68  lea     r15, [rcx+108h]
0x180023d6f  lea     rdx, [rbp+57h+var_70]
0x180023d73  mov     rcx, r15
0x180023d76  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>::start_and_watch_errors(void)
0x180023d7b  nop
0x180023d7c  mov     rax, [rbp+57h+var_38]
0x180023d80  movups  xmm0, xmmword ptr [rax+98h]
0x180023d87  movdqu  xmmword ptr [rbp+57h+var_A0.Data1], xmm0
0x180023d8c  mov     ebx, [rsi+0F8h]
0x180023d92  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_ec6e2907394b4434fdfb8b987aa4b821_@@CA@XZ; _lambda_ec6e2907394b4434fdfb8b987aa4b821_::_lambda_invoker_cdecl_(void)
0x180023d99  call    ?get@?$static_lazy@VSHCoreOplockTelemetry@@@details@wil@@QEAAPEAVSHCoreOplockTelemetry@@P6AXXZ@Z; wil::details::static_lazy<SHCoreOplockTelemetry>::get(void (*)(void))
0x180023d9e  mov     rcx, rax; this
0x180023da1  call    ?IsEnabled_@TraceLoggingProvider@wil@@IEBA_NE_K@Z; wil::TraceLoggingProvider::IsEnabled_(uchar,unsigned __int64)
0x180023da6  xor     r12d, r12d
0x180023da9  test    al, al
0x180023dab  jz      short loc_180023DCC
0x180023dad  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_ec6e2907394b4434fdfb8b987aa4b821_@@CA@XZ; _lambda_ec6e2907394b4434fdfb8b987aa4b821_::_lambda_invoker_cdecl_(void)
0x180023db4  call    ?get@?$static_lazy@VSHCoreOplockTelemetry@@@details@wil@@QEAAPEAVSHCoreOplockTelemetry@@P6AXXZ@Z; wil::details::static_lazy<SHCoreOplockTelemetry>::get(void (*)(void))
0x180023db9  mov     qword ptr [rsp+110h+var_F0], r14; int
0x180023dbe  mov     r9, r13; void *
0x180023dc1  mov     r8d, ebx; int
0x180023dc4  mov     rdx, rsi; void *
0x180023dc7  call    ?RequestOplockStart_@SHCoreOplockTelemetry@@QEAAXPEAXH0PEBG@Z; SHCoreOplockTelemetry::RequestOplockStart_(void *,int,void *,ushort const *)
0x180023dcc  mov     ebx, 1
0x180023dd1  xor     eax, eax
0x180023dd3  lock cmpxchg [rsi+0F8h], ebx
0x180023ddb  mov     [rbp+57h+var_D0], eax
0x180023dde  jnz     loc_180023F23
0x180023de4  mov     [rsp+110h+var_E0], r12b
0x180023de9  lea     rax, [rsp+110h+var_E0]
0x180023dee  mov     [rbp+57h+var_C0], rax
0x180023df2  mov     [rbp+57h+var_B8], rsi
0x180023df6  lea     rax, [rbp+57h+var_D0]
0x180023dfa  mov     [rbp+57h+var_B0], rax
0x180023dfe  mov     [rbp+57h+var_A8], bl
0x180023e01  mov     rax, [rsi]
0x180023e04  mov     rdx, r14
0x180023e07  mov     rcx, rsi
0x180023e0a  mov     rax, [rax+18h]
0x180023e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e13  test    eax, eax
0x180023e15  js      loc_180024146
0x180023e1b  mov     rcx, r14; pszPath
0x180023e1e  call    cs:__imp_PathGetDriveNumberW
0x180023e24  mov     ecx, eax; iDrive
0x180023e26  call    DriveType
0x180023e2b  add     eax, 0FFFFFFFEh
0x180023e2e  cmp     eax, ebx
0x180023e30  ja      loc_180024146
0x180023e36  xorps   xmm0, xmm0
0x180023e39  movups  [rbp+57h+var_90], xmm0
0x180023e3d  movups  [rbp+57h+var_80], xmm0
0x180023e41  mov     dword ptr [rbp+57h+var_90], 20h ; ' '
0x180023e48  mov     eax, 40240000h
0x180023e4d  mov     ecx, 40040000h
0x180023e52  cmp     edi, ebx
0x180023e54  cmovnz  eax, ecx
0x180023e57  mov     dword ptr [rbp+57h+var_90+8], eax
0x180023e5a  mov     [rsi+128h], r14
0x180023e61  mov     rcx, rsi; pv
0x180023e64  call    ?StartCreateFileCallbackTimer@COplockProvider@@AEAAXXZ; COplockProvider::StartCreateFileCallbackTimer(void)
0x180023e69  lea     rax, [rbp+57h+var_90]
0x180023e6d  mov     qword ptr [rsp+110h+var_F0], rax
0x180023e72  lea     r9d, [rbx+2]
0x180023e76  mov     r8d, ebx
0x180023e79  mov     edx, 80000000h
0x180023e7e  mov     rcx, r14
0x180023e81  call    cs:__imp_CreateFile2
0x180023e87  mov     rbx, rax
0x180023e8a  mov     [rbp+57h+var_C8], rax
0x180023e8e  mov     r12, [rsi+118h]
0x180023e95  test    r12, r12
0x180023e98  jnz     short loc_180023F06
0x180023e9a  xor     r12d, r12d
0x180023e9d  mov     [rsi+118h], r12
0x180023ea4  mov     [rsi+128h], r12
0x180023eab  lea     rax, [rbx+1]
0x180023eaf  test    rax, 0FFFFFFFFFFFFFFFEh
0x180023eb5  jnz     loc_180024006
0x180023ebb  call    cs:__imp_GetLastError
0x180023ec1  mov     edi, eax
0x180023ec3  test    eax, eax
0x180023ec5  jle     loc_18002410F
0x180023ecb  movzx   edx, di
0x180023ece  or      edx, 80070000h; int
0x180023ed4  lea     r8, [rbp+57h+var_A0]; struct _GUID *
0x180023ed8  call    ?ShouldSuppressCreateFileError@COplockProvider@@AEAA_NJAEBU_GUID@@@Z; COplockProvider::ShouldSuppressCreateFileError(long,_GUID const &)
0x180023edd  test    al, al
0x180023edf  jz      loc_180023FB0
0x180023ee5  mov     [rsp+110h+var_E0], 1
0x180023eea  test    edi, edi
0x180023eec  jz      loc_180023FB0
0x180023ef2  jle     loc_18002413B
0x180023ef8  movzx   edi, di
0x180023efb  or      edi, 80070000h
0x180023f01  jmp     loc_18002413B
0x180023f06  call    cs:__imp_GetLastError
0x180023f0c  mov     edi, eax
0x180023f0e  mov     rcx, r12; pti
0x180023f11  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180023f16  mov     ecx, edi; dwErrCode
0x180023f18  call    cs:__imp_SetLastError
0x180023f1e  jmp     loc_180023E9A
0x180023f23  mov     dword ptr [rsp+110h+pv], eax
0x180023f27  mov     [rbp+57h+var_C8], rsi
0x180023f2b  lea     rdx, [rsp+110h+pv]
0x180023f30  lea     rcx, [rbp+57h+var_C8]
0x180023f34  call    ??$RequestOplockInvalidStartState@PEAVCOplockProvider@@H@SHCoreOplockTelemetry@@SAX$$QEAPEAVCOplockProvider@@$$QEAH@Z; SHCoreOplockTelemetry::RequestOplockInvalidStartState<COplockProvider *,int>(COplockProvider * &&,int &&)
0x180023f39  mov     rcx, r15
0x180023f3c  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>::ensure_data(void)
0x180023f41  mov     rdi, [rax]
0x180023f44  mov     [rsp+110h+pv], rdi
0x180023f49  test    rdi, rdi
0x180023f4c  jz      short loc_180023F55
0x180023f4e  lock add [rdi+118h], ebx
0x180023f55  lea     rcx, [rdi+8]
0x180023f59  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180023f5e  mov     dword ptr [rdi+110h], 5
0x180023f68  lea     rcx, [rdi+8]
0x180023f6c  call    ?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::end_update(void)
0x180023f71  lea     rcx, [rsp+110h+pv]
0x180023f76  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>,wil::err_returncode_policy>::reset(void)
0x180023f7b  mov     rcx, [rsp+110h+pv]; pv
0x180023f80  test    rcx, rcx
0x180023f83  jnz     loc_180024105
0x180023f89  mov     rcx, r15
0x180023f8c  call    ?complete@?$tip_test@V?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>::complete(void)
0x180023f91  mov     rcx, [rbp+5Fh]; this
0x180023f95  mov     edi, 8007139Fh
0x180023f9a  mov     r9d, edi; char *
0x180023f9d  lea     r8, aOnecoreShellSh_5; "onecore\\shell\\shcore\\libs\\stream\\o"...
0x180023fa4  mov     edx, 258h; void *
0x180023fa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023fae  jmp     short loc_180023FEF
0x180023fb0  lea     rax, [rbx+1]
0x180023fb4  test    rax, 0FFFFFFFFFFFFFFFEh
0x180023fba  jnz     short loc_180024006
0x180023fbc  mov     rcx, [rbp+5Fh]; this
0x180023fc0  lea     r8, aOnecoreShellSh_5; "onecore\\shell\\shcore\\libs\\stream\\o"...
0x180023fc7  mov     edx, 291h; void *
0x180023fcc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023fd1  mov     edi, eax
0x180023fd3  lea     rcx, [rbx-1]
0x180023fd7  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180023fdb  jbe     loc_180024116
0x180023fe1  mov     [rbp+57h+var_A8], r12b
0x180023fe5  lea     rcx, [rbp+57h+var_C0]
0x180023fe9  call    _lambda_26cd70ff2e96c6105ba1d23aa9312e48___operator__
0x180023fee  nop
0x180023fef  mov     rcx, [rbp+57h+var_38]; pv
0x180023ff3  test    rcx, rcx
0x180023ff6  jz      loc_1800240C5
0x180023ffc  call    ?Release@?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>::Release(void)
0x180024001  jmp     loc_1800240C5
0x180024006  mov     rcx, r14; pszPath
0x180024009  call    cs:__imp_PathFindExtensionW
0x18002400f  cmp     [rax], r12w
0x180024013  jz      short loc_180024041
0x180024015  mov     rdx, rax
0x180024018  lea     rcx, [rsp+110h+pv]
0x18002401d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180024022  lea     rcx, [rsi+0F0h]
0x180024029  lea     rdx, [rsp+110h+pv]
0x18002402e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180024033  mov     rcx, [rsp+110h+pv]; pv
0x180024038  test    rcx, rcx
0x18002403b  jnz     loc_1800240FA
0x180024041  lea     r9, [rbp+57h+var_A0]; struct _GUID *
0x180024045  mov     r8, r13; struct IOplockCallback *
0x180024048  mov     rdx, rbx; hSourceHandle
0x18002404b  mov     rcx, rsi; this
0x18002404e  call    ?RequestOplockOnHandleInternal@COplockProvider@@AEAAJPEAXPEAUIOplockCallback@@AEBU_GUID@@@Z; COplockProvider::RequestOplockOnHandleInternal(void *,IOplockCallback *,_GUID const &)
0x180024053  test    eax, eax
0x180024055  jnz     loc_180024124
0x18002405b  mov     rcx, rbx; hObject
0x18002405e  call    cs:__imp_CloseHandle
0x180024064  mov     rcx, r15
0x180024067  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>::ensure_data(void)
0x18002406c  mov     rdi, [rax]
0x18002406f  mov     [rsp+110h+pv], rdi
0x180024074  test    rdi, rdi
0x180024077  jz      short loc_180024080
0x180024079  lock inc dword ptr [rdi+118h]
0x180024080  lea     rcx, [rdi+8]
0x180024084  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180024089  mov     dword ptr [rdi+110h], 3
0x180024093  lea     rcx, [rdi+8]
0x180024097  call    ?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::end_update(void)
0x18002409c  lea     rcx, [rsp+110h+pv]
0x1800240a1  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>,wil::err_returncode_policy>::reset(void)
0x1800240a6  mov     rcx, [rsp+110h+pv]; pv
0x1800240ab  test    rcx, rcx
0x1800240ae  jnz     short loc_1800240EB
0x1800240b0  mov     rcx, r15
0x1800240b3  call    ?complete@?$tip_test@V?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>::complete(void)
0x1800240b8  nop
0x1800240b9  mov     rcx, [rbp+57h+var_38]; pv
0x1800240bd  test    rcx, rcx
0x1800240c0  jnz     short loc_1800240F3
0x1800240c2  mov     edi, r12d
0x1800240c5  lea     rcx, [rbp+57h+var_68]; this
0x1800240c9  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800240ce  mov     eax, edi
0x1800240d0  mov     rbx, [rsp+110h+arg_10]
0x1800240d8  add     rsp, 0E0h
0x1800240df  pop     r15
0x1800240e1  pop     r14
0x1800240e3  pop     r13
0x1800240e5  pop     r12
0x1800240e7  pop     rdi
0x1800240e8  pop     rsi
0x1800240e9  pop     rbp
0x1800240ea  retn
0x1800240eb  call    ?Release@?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>::Release(void)
0x1800240f0  nop
0x1800240f1  jmp     short loc_1800240B0
0x1800240f3  call    ?Release@?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>::Release(void)
0x1800240f8  jmp     short loc_1800240C2
0x1800240fa  call    cs:__imp_CoTaskMemFree
0x180024100  jmp     loc_180024041
0x180024105  call    ?Release@?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>::Release(void)
0x18002410a  jmp     loc_180023F89
0x18002410f  mov     edx, edi
0x180024111  jmp     loc_180023ED4
0x180024116  mov     rcx, rbx; hObject
0x180024119  call    cs:__imp_CloseHandle
0x18002411f  jmp     loc_180023FE1
0x180024124  cmp     eax, 1
0x180024127  jnz     short loc_180024131
0x180024129  mov     [rsp+110h+var_E0], al
0x18002412d  mov     edi, eax
0x18002412f  jmp     short loc_18002413B
0x180024131  test    eax, eax
0x180024133  jns     loc_18002405B
0x180024139  mov     edi, eax
0x18002413b  lea     rcx, [rbp+57h+var_C8]
0x18002413f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180024144  jmp     short loc_18002414C
0x180024146  mov     [rsp+110h+var_E0], bl
0x18002414a  mov     edi, ebx
0x18002414c  mov     [rbp+57h+var_A8], r12b
0x180024150  lea     rcx, [rbp+57h+var_C0]
0x180024154  call    _lambda_26cd70ff2e96c6105ba1d23aa9312e48___operator__
0x180024159  nop
0x18002415a  lea     rcx, [rbp+57h+var_70]
0x18002415e  call    ??1?$test_watcher@V?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>::~test_watcher<tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>>(void)
0x180024163  jmp     loc_1800240CE
```
