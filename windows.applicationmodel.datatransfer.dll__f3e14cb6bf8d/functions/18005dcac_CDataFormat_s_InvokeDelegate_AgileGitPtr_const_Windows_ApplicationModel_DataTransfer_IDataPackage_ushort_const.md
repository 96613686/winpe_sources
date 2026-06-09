# CDataFormat::s_InvokeDelegate(AgileGitPtr const &,Windows::ApplicationModel::DataTransfer::IDataPackage *,ushort const *,bool)

- ea: `0x18005dcac`
- end: `0x18005e289`
- name: `?s_InvokeDelegate@CDataFormat@@SAJAEBVAgileGitPtr@@PEAUIDataPackage@DataTransfer@ApplicationModel@Windows@@PEBG_N@Z`
- size: `1501`
- prototype: `static int(const struct AgileGitPtr *, struct Windows::ApplicationModel::DataTransfer::IDataPackage *, const unsigned __int16 *, bool)`
- caller_count: `4`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fdb8`
- `0x18000fec8`
- `0x18002d820`
- `0x180038eb8`

## callees

- `0x180002ad0`
- `0x18000346c`
- `0x1800045b8`
- `0x18000490c`
- `0x180005504`
- `0x180006914`
- `0x1800143c4`
- `0x1800178bc`
- `0x180049a94`
- `0x180049e14`
- `0x18004e118`
- `0x18004e4d0`
- `0x18005dcac`
- `0x18005fa50`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18005e1cd`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18005e1cd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005e18b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005e1b9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005e18b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005e1b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005df40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005df40`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18005e03a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18005e03a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18005df90`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18005df90`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18005e0e0`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18005e0e0`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18005e024`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18005e024`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18005df5a`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18005df5a`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CDataFormat::s_InvokeDelegate(
        const struct AgileGitPtr *a1,
        struct Windows::ApplicationModel::DataTransfer::IDataPackage *a2,
        const unsigned __int16 *a3,
        char a4)
{
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rbx
  _QWORD *v11; // rax
  CDataProviderRequest *v12; // rcx
  __int64 v13; // r8
  CDataProviderRequest *v14; // rsi
  int v15; // edi
  _QWORD *v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rcx
  HWND v19; // rcx
  unsigned int v20; // r9d
  unsigned int v21; // eax
  HRESULT v22; // eax
  __int64 v23; // rsi
  __int64 (__fastcall *v24)(__int64, _QWORD); // rdi
  _QWORD *v25; // rax
  int v26; // eax
  __int64 v27; // rcx
  unsigned int StringW; // eax
  __int64 v29; // rcx
  CDataProviderRequest *v30; // rcx
  __int64 *DueTime; // [rsp+20h] [rbp-E0h]
  DWORD Period; // [rsp+28h] [rbp-D8h]
  DWORD dwindex[2]; // [rsp+40h] [rbp-C0h] BYREF
  CDataProviderRequest *v35; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE pHandles; // [rsp+50h] [rbp-B0h] BYREF
  CDataProviderRequest *v37; // [rsp+58h] [rbp-A8h]
  DWORD Parameter; // [rsp+60h] [rbp-A0h] BYREF
  char v39; // [rsp+64h] [rbp-9Ch]
  HRESULT v40; // [rsp+68h] [rbp-98h]
  void *phNewTimer; // [rsp+70h] [rbp-90h] BYREF
  void **v42; // [rsp+80h] [rbp-80h] BYREF
  int v43; // [rsp+88h] [rbp-78h] BYREF
  char v44; // [rsp+8Ch] [rbp-74h]
  int v45; // [rsp+B0h] [rbp-50h] BYREF
  const char *v46; // [rsp+B8h] [rbp-48h]
  __int64 v47; // [rsp+C0h] [rbp-40h]
  char v48; // [rsp+C8h] [rbp-38h]
  int v49; // [rsp+D0h] [rbp-30h]
  char v50[152]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v51; // [rsp+170h] [rbp+70h]
  int v52; // [rsp+180h] [rbp+80h]
  __int64 v53; // [rsp+188h] [rbp+88h]
  int *v54; // [rsp+190h] [rbp+90h]
  __int64 v55; // [rsp+198h] [rbp+98h]
  __int64 v56; // [rsp+1A0h] [rbp+A0h]
  void ***v57; // [rsp+1A8h] [rbp+A8h]
  __int64 v58; // [rsp+1B0h] [rbp+B0h]
  int v59; // [rsp+1B8h] [rbp+B8h]
  int *v60; // [rsp+1C0h] [rbp+C0h]
  char v61; // [rsp+1C8h] [rbp+C8h]
  const unsigned __int16 *v62; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v63; // [rsp+1E0h] [rbp+E0h] BYREF

  v62 = a3;
  v43 = 0;
  v44 = 0;
  v48 = 0;
  v45 = 0;
  v46 = "DelayedRenderActivity";
  v47 = 0;
  v49 = 0;
  v51 = 0;
  memset_0(v50, 0, sizeof(v50));
  v52 = 1;
  v53 = 0;
  v54 = &v43;
  v55 = 0;
  v56 = 0;
  v57 = &v42;
  v58 = 0;
  v59 = 0;
  v60 = &v45;
  v61 = 0;
  v42 = &DataPackageTracing::DelayedRenderActivity::`vftable';
  DataPackageTracing::DelayedRenderActivity::StartActivity((DataPackageTracing::DelayedRenderActivity *)&v42);
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    DueTime = &v63;
    McGenEventWrite_EventWriteTransfer(v8, DataPackage_InvokeDataProviderHandler_Start, v9, 1);
  }
  v10 = *(_QWORD *)a1;
  v63 = v10;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  v37 = 0;
  v11 = operator new(0x80u, (const struct std::nothrow_t *)std::nothrow);
  v14 = (CDataProviderRequest *)v11;
  pHandles = v11;
  if ( !v11 )
  {
    v15 = -2147024882;
    goto LABEL_50;
  }
  v16 = v11 + 3;
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v11 + 3));
  *((_QWORD *)v14 + 8) = 1;
  *(_QWORD *)v14 = &Microsoft::WRL::RuntimeClass<Windows::ApplicationModel::DataTransfer::IDataProviderRequest,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::DataTransfer::IDataProviderDeferral>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::ApplicationModel::DataTransfer::IDataProviderRequest'};
  *((_QWORD *)v14 + 1) = &Microsoft::WRL::RuntimeClass<Windows::ApplicationModel::DataTransfer::IDataProviderRequest,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::DataTransfer::IDataProviderDeferral>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::DataTransfer::IDataProviderDeferral>,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)v14 + 2) = &Microsoft::WRL::RuntimeClass<Windows::ApplicationModel::DataTransfer::IDataProviderRequest,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::DataTransfer::IDataProviderDeferral>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::ApplicationModel::DataTransfer::IDataProviderDeferral>'};
  *v16 = &Microsoft::WRL::RuntimeClass<Windows::ApplicationModel::DataTransfer::IDataProviderRequest,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::DataTransfer::IDataProviderDeferral>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v14 = &CDataProviderRequest::`vftable'{for `Windows::ApplicationModel::DataTransfer::IDataProviderRequest'};
  *((_QWORD *)v14 + 1) = &CDataProviderRequest::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::DataTransfer::IDataProviderDeferral>,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)v14 + 2) = &CDataProviderRequest::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::ApplicationModel::DataTransfer::IDataProviderDeferral>'};
  *v16 = &CDataProviderRequest::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)v14 + 9) = 0;
  *((_QWORD *)v14 + 11) = 0;
  *((_QWORD *)v14 + 12) = 0;
  *((_QWORD *)v14 + 13) = 0;
  *((_QWORD *)v14 + 14) = 0;
  *((_QWORD *)v14 + 15) = 0;
  *((_QWORD *)v14 + 10) = 0;
  v35 = v14;
  pHandles = 0;
  v15 = CDataProviderRequest::RuntimeClassInitialize(v14, a2, a3, 0x57E40u);
  v17 = *(_QWORD *)v14;
  if ( v15 < 0 )
  {
    (*(void (__fastcall **)(CDataProviderRequest *))(v17 + 16))(v14);
    goto LABEL_50;
  }
  (*(void (__fastcall **)(CDataProviderRequest *))(v17 + 8))(v14);
  v37 = v14;
  (*(void (__fastcall **)(CDataProviderRequest *))(*(_QWORD *)v14 + 16LL))(v14);
  v35 = 0;
  if ( v10 )
    v15 = (*(__int64 (__fastcall **)(__int64, GUID *, CDataProviderRequest **))(*(_QWORD *)v10 + 24LL))(
            v10,
            &GUID_e7ecd720_f2f4_4a2d_920e_170a2f482a27,
            &v35);
  else
    v15 = -2147024809;
  if ( v15 >= 0 )
  {
    Parameter = GetCurrentThreadId();
    v39 = 0;
    v40 = -2147467259;
    phNewTimer = 0;
    v40 = CoEnableCallCancellation(0);
    if ( v40 >= 0 )
      CreateTimerQueueTimer(&phNewTimer, 0, CBaseRPCTimeout::s_Callback, &Parameter, 0x57E40u, 0x3E8u, 0);
    if ( a4 )
    {
      *(_QWORD *)dwindex = 0;
      if ( (**(int (__fastcall ***)(CDataProviderRequest *, GUID *, DWORD *))v35)(
             v35,
             &GUID_00000144_0000_0000_c000_000000000046,
             dwindex) >= 0 )
        (*(void (__fastcall **)(_QWORD, CDataProviderRequest *, __int64))(**(_QWORD **)dwindex + 24LL))(
          *(_QWORD *)dwindex,
          v35,
          5);
      v18 = *(_QWORD *)dwindex;
      if ( *(_QWORD *)dwindex )
      {
        *(_QWORD *)dwindex = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
    }
    v15 = (*(__int64 (__fastcall **)(CDataProviderRequest *, CDataProviderRequest *))(*(_QWORD *)v35 + 24LL))(v35, v37);
    if ( v40 >= 0 )
    {
      v40 = -2147467259;
      CoDisableCallCancellation(0);
      if ( phNewTimer )
        DeleteTimerQueueTimer(0, phNewTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    }
  }
  _InterlockedExchange((volatile __int32 *)v37 + 29, 1);
  if ( v15 >= 0 )
  {
    pHandles = (HANDLE)*((_QWORD *)v37 + 13);
    if ( !pHandles )
      goto LABEL_48;
    if ( (unsigned __int8)IsMsgWaitForMultipleObjectsExPresent() && (unsigned __int8)IsPeekMessageWPresent() )
    {
      *(_QWORD *)dwindex = pHandles;
      v21 = SHProcessMessagesUntilEventsEx(v19, (void **)dwindex, pHandles != 0, v20, (unsigned int)DueTime, Period);
      if ( v21 )
      {
        if ( v21 != 258 )
        {
          v15 = -2147467259;
          goto LABEL_48;
        }
        goto LABEL_31;
      }
      goto LABEL_36;
    }
    dwindex[0] = 0;
    v22 = CoWaitForMultipleHandles(8u, 0x57E40u, 1u, &pHandles, dwindex);
    v15 = v22;
    if ( v22 >= 0 )
    {
LABEL_36:
      *(_QWORD *)dwindex = 0;
      v15 = (**(__int64 (__fastcall ***)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, GUID *, DWORD *))a2)(
              a2,
              &GUID_cd1c0ba1_0ccb_4a33_9652_fe27a738c219,
              dwindex);
      if ( v15 >= 0 )
      {
        v23 = *(_QWORD *)dwindex;
        v24 = *(__int64 (__fastcall **)(__int64, _QWORD))(**(_QWORD **)dwindex + 48LL);
        v25 = (_QWORD *)Windows::Internal::StringReference::StringReference(&Parameter, &v62);
        v26 = v24(v23, *v25);
        v15 = -2147023728;
        if ( v26 )
          v15 = 0;
      }
      v27 = *(_QWORD *)dwindex;
      if ( *(_QWORD *)dwindex )
      {
        *(_QWORD *)dwindex = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
      goto LABEL_41;
    }
    if ( v22 == -2147417835 )
    {
LABEL_31:
      v15 = -2147417825;
LABEL_42:
      pHandles = 0;
      StringW = LoadStringW(&_ImageBase, 0xEu, (LPWSTR)&pHandles, 0);
      if ( !StringW )
        goto LABEL_48;
      v29 = 2147549471LL;
      goto LABEL_47;
    }
  }
LABEL_41:
  if ( v15 == -2147417825 )
    goto LABEL_42;
  if ( v15 == -2147023728 )
  {
    pHandles = 0;
    StringW = LoadStringW(&_ImageBase, 0xFu, (LPWSTR)&pHandles, 0);
    if ( StringW )
    {
      v29 = 2147943568LL;
LABEL_47:
      RoOriginateErrorW(v29, StringW, pHandles);
    }
  }
LABEL_48:
  v12 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(CDataProviderRequest *))(*(_QWORD *)v12 + 16LL))(v12);
  }
LABEL_50:
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v12, DataPackage_InvokeDataProviderHandler_Stop, v13, 1);
  wil::ActivityBase<DataPackageTracing,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    &v42,
    (unsigned int)v15);
  v30 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(CDataProviderRequest *))(*(_QWORD *)v30 + 16LL))(v30);
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  DataPackageTracing::DelayedRenderActivity::~DelayedRenderActivity((DataPackageTracing::DelayedRenderActivity *)&v42);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18005dcac  mov     [rsp-8+arg_0], rbx
0x18005dcb1  push    rbp
0x18005dcb2  push    rsi
0x18005dcb3  push    rdi
0x18005dcb4  push    r12
0x18005dcb6  push    r13
0x18005dcb8  push    r14
0x18005dcba  push    r15
0x18005dcbc  lea     rbp, [rsp-100h]
0x18005dcc4  sub     rsp, 200h
0x18005dccb  mov     rax, cs:__security_cookie
0x18005dcd2  xor     rax, rsp
0x18005dcd5  mov     [rbp+130h+var_40], rax
0x18005dcdc  mov     r15b, r9b
0x18005dcdf  mov     r14, r8
0x18005dce2  mov     r12, rdx
0x18005dce5  mov     rbx, rcx
0x18005dce8  mov     [rbp+130h+var_60], r8
0x18005dcef  xor     r13d, r13d
0x18005dcf2  mov     [rbp+130h+var_1A8], r13d
0x18005dcf6  mov     [rbp+130h+var_1A4], r13b
0x18005dcfa  mov     [rbp+130h+var_168], r13b
0x18005dcfe  mov     [rbp+130h+var_180], r13d
0x18005dd02  lea     rax, aDelayedrendera; "DelayedRenderActivity"
0x18005dd09  mov     [rbp+130h+var_178], rax
0x18005dd0d  mov     [rbp+130h+var_170], r13
0x18005dd11  mov     [rbp+130h+var_160], r13d
0x18005dd15  xorps   xmm0, xmm0
0x18005dd18  movdqa  [rbp+130h+var_C0], xmm0
0x18005dd1d  xor     edx, edx; Val
0x18005dd1f  mov     r8d, 98h; Size
0x18005dd25  lea     rcx, [rbp+130h+var_158]; void *
0x18005dd29  call    memset_0
0x18005dd2e  mov     [rbp+130h+var_B0], 1
0x18005dd38  xor     eax, eax
0x18005dd3a  mov     [rbp+130h+var_A8], rax
0x18005dd41  lea     rax, [rbp+130h+var_1A8]
0x18005dd45  mov     [rbp+130h+var_A0], rax
0x18005dd4c  mov     [rbp+130h+var_98], r13
0x18005dd53  mov     [rbp+130h+var_90], r13
0x18005dd5a  lea     rax, [rbp+130h+var_1B0]
0x18005dd5e  mov     [rbp+130h+var_88], rax
0x18005dd65  mov     [rbp+130h+var_80], r13
0x18005dd6c  mov     [rbp+130h+var_78], r13d
0x18005dd73  lea     rax, [rbp+130h+var_180]
0x18005dd77  mov     [rbp+130h+var_70], rax
0x18005dd7e  mov     [rbp+130h+var_68], r13b
0x18005dd85  lea     rax, ??_7DelayedRenderActivity@DataPackageTracing@@6B@; const DataPackageTracing::DelayedRenderActivity::`vftable'
0x18005dd8c  mov     [rbp+130h+var_1B0], rax
0x18005dd90  lea     rcx, [rbp+130h+var_1B0]; this
0x18005dd94  call    ?StartActivity@DelayedRenderActivity@DataPackageTracing@@QEAAXXZ; DataPackageTracing::DelayedRenderActivity::StartActivity(void)
0x18005dd99  nop
0x18005dd9a  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18005dda1  jz      short loc_18005DDBF
0x18005dda3  lea     rax, [rbp+130h+var_50]
0x18005ddaa  mov     qword ptr [rsp+230h+DueTime], rax
0x18005ddaf  lea     r9d, [r13+1]
0x18005ddb3  lea     rdx, DataPackage_InvokeDataProviderHandler_Start
0x18005ddba  call    McGenEventWrite_EventWriteTransfer
0x18005ddbf  mov     rbx, [rbx]
0x18005ddc2  mov     [rbp+130h+var_50], rbx
0x18005ddc9  test    rbx, rbx
0x18005ddcc  jz      short loc_18005DDDE
0x18005ddce  mov     rax, [rbx]
0x18005ddd1  mov     rcx, rbx
0x18005ddd4  mov     rax, [rax+8]
0x18005ddd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dddd  nop
0x18005ddde  mov     [rsp+230h+var_1D8], r13
0x18005dde3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005ddea  mov     ecx, 80h; unsigned __int64
0x18005ddef  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005ddf4  mov     rsi, rax
0x18005ddf7  mov     [rsp+230h+pHandles], rax
0x18005ddfc  test    rax, rax
0x18005ddff  jnz     short loc_18005DE0B
0x18005de01  mov     edi, 8007000Eh
0x18005de06  jmp     loc_18005E1F0
0x18005de0b  lea     rdi, [rax+18h]
0x18005de0f  mov     rcx, rdi; this
0x18005de12  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18005de17  mov     qword ptr [rsi+40h], 1
0x18005de1f  lea     rax, ??_7?$RuntimeClass@UIDataProviderRequest@DataTransfer@ApplicationModel@Windows@@U?$CloakedIid@UIDataProviderDeferral@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@VFtmBase@67@@WRL@Microsoft@@6BIDataProviderRequest@DataTransfer@ApplicationModel@Windows@@@; const Microsoft::WRL::RuntimeClass<Windows::ApplicationModel::DataTransfer::IDataProviderRequest,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::DataTransfer::IDataProviderDeferral>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::ApplicationModel::DataTransfer::IDataProviderRequest'}
0x18005de26  mov     [rsi], rax
0x18005de29  lea     rax, ??_7?$RuntimeClass@UIDataProviderRequest@DataTransfer@ApplicationModel@Windows@@U?$CloakedIid@UIDataProviderDeferral@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@VFtmBase@67@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UIDataProviderDeferral@DataTransfer@ApplicationModel@Windows@@@23@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::ApplicationModel::DataTransfer::IDataProviderRequest,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::DataTransfer::IDataProviderDeferral>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::DataTransfer::IDataProviderDeferral>,Microsoft::WRL::FtmBase>'}
0x18005de30  mov     [rsi+8], rax
0x18005de34  lea     rax, ??_7?$RuntimeClass@UIDataProviderRequest@DataTransfer@ApplicationModel@Windows@@U?$CloakedIid@UIDataProviderDeferral@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@VFtmBase@67@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIDataProviderDeferral@DataTransfer@ApplicationModel@Windows@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::ApplicationModel::DataTransfer::IDataProviderRequest,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::DataTransfer::IDataProviderDeferral>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::ApplicationModel::DataTransfer::IDataProviderDeferral>'}
0x18005de3b  mov     [rsi+10h], rax
0x18005de3f  lea     rax, ??_7?$RuntimeClass@UIDataProviderRequest@DataTransfer@ApplicationModel@Windows@@U?$CloakedIid@UIDataProviderDeferral@DataTransfer@ApplicationModel@Windows@@@WRL@Microsoft@@VFtmBase@67@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::ApplicationModel::DataTransfer::IDataProviderRequest,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::DataTransfer::IDataProviderDeferral>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18005de46  mov     [rdi], rax
0x18005de49  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18005de50  test    rcx, rcx
0x18005de53  jz      short loc_18005DE62
0x18005de55  mov     rax, [rcx]
0x18005de58  mov     rax, [rax+8]
0x18005de5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005de61  nop
0x18005de62  lea     rax, ??_7CDataProviderRequest@@6BIDataProviderRequest@DataTransfer@ApplicationModel@Windows@@@; const CDataProviderRequest::`vftable'{for `Windows::ApplicationModel::DataTransfer::IDataProviderRequest'}
0x18005de69  mov     [rsi], rax
0x18005de6c  lea     rax, ??_7CDataProviderRequest@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UIDataProviderDeferral@DataTransfer@ApplicationModel@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const CDataProviderRequest::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::ApplicationModel::DataTransfer::IDataProviderDeferral>,Microsoft::WRL::FtmBase>'}
0x18005de73  mov     [rsi+8], rax
0x18005de77  lea     rax, ??_7CDataProviderRequest@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIDataProviderDeferral@DataTransfer@ApplicationModel@Windows@@@Details@WRL@Microsoft@@@; const CDataProviderRequest::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::ApplicationModel::DataTransfer::IDataProviderDeferral>'}
0x18005de7e  mov     [rsi+10h], rax
0x18005de82  lea     rax, ??_7CDataProviderRequest@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CDataProviderRequest::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18005de89  mov     [rdi], rax
0x18005de8c  mov     [rsi+48h], r13
0x18005de90  mov     [rsi+58h], r13
0x18005de94  mov     [rsi+60h], r13
0x18005de98  mov     [rsi+68h], r13
0x18005de9c  mov     [rsi+70h], r13
0x18005dea0  mov     [rsi+78h], r13
0x18005dea4  xor     eax, eax
0x18005dea6  mov     [rsi+50h], rax
0x18005deaa  mov     [rsp+230h+var_1E8], rsi
0x18005deaf  mov     [rsp+230h+pHandles], r13
0x18005deb4  mov     r9d, 57E40h; unsigned int
0x18005deba  mov     r8, r14; unsigned __int16 *
0x18005debd  mov     rdx, r12; struct Windows::ApplicationModel::DataTransfer::IDataPackage *
0x18005dec0  mov     rcx, rsi; this
0x18005dec3  call    ?RuntimeClassInitialize@CDataProviderRequest@@QEAAJPEAUIDataPackage@DataTransfer@ApplicationModel@Windows@@PEBGK@Z; CDataProviderRequest::RuntimeClassInitialize(Windows::ApplicationModel::DataTransfer::IDataPackage *,ushort const *,ulong)
0x18005dec8  mov     edi, eax
0x18005deca  mov     rax, [rsi]
0x18005decd  test    edi, edi
0x18005decf  jns     short loc_18005DEE3
0x18005ded1  mov     rcx, rsi
0x18005ded4  mov     rax, [rax+10h]
0x18005ded8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dedd  nop
0x18005dede  jmp     loc_18005E1F0
0x18005dee3  mov     rcx, rsi
0x18005dee6  mov     rax, [rax+8]
0x18005deea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005deef  nop
0x18005def0  mov     [rsp+230h+var_1D8], rsi
0x18005def5  mov     rax, [rsi]
0x18005def8  mov     rcx, rsi
0x18005defb  mov     rax, [rax+10h]
0x18005deff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005df04  nop
0x18005df05  mov     [rsp+230h+var_1E8], r13
0x18005df0a  test    rbx, rbx
0x18005df0d  jz      short loc_18005DF2E
0x18005df0f  mov     rax, [rbx]
0x18005df12  lea     r8, [rsp+230h+var_1E8]
0x18005df17  lea     rdx, _GUID_e7ecd720_f2f4_4a2d_920e_170a2f482a27
0x18005df1e  mov     rcx, rbx
0x18005df21  mov     rax, [rax+18h]
0x18005df25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005df2a  mov     edi, eax
0x18005df2c  jmp     short loc_18005DF33
0x18005df2e  mov     edi, 80070057h
0x18005df33  mov     esi, 80004005h
0x18005df38  test    edi, edi
0x18005df3a  js      loc_18005E040
0x18005df40  call    cs:__imp_GetCurrentThreadId
0x18005df46  mov     [rsp+230h+Parameter], eax
0x18005df4a  mov     [rsp+230h+var_1CC], r13b
0x18005df4f  mov     [rsp+230h+var_1C8], esi
0x18005df53  mov     [rsp+230h+phNewTimer], r13
0x18005df58  xor     ecx, ecx; pReserved
0x18005df5a  call    cs:__imp_CoEnableCallCancellation
0x18005df60  mov     [rsp+230h+var_1C8], eax
0x18005df64  test    eax, eax
0x18005df66  js      short loc_18005DF97
0x18005df68  mov     [rsp+230h+Flags], r13d; Flags
0x18005df6d  mov     [rsp+230h+Period], 3E8h; unsigned int
0x18005df75  mov     [rsp+230h+DueTime], 57E40h; unsigned int
0x18005df7d  lea     r9, [rsp+230h+Parameter]; Parameter
0x18005df82  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x18005df89  xor     edx, edx; TimerQueue
0x18005df8b  lea     rcx, [rsp+230h+phNewTimer]; phNewTimer
0x18005df90  call    cs:__imp_CreateTimerQueueTimer
0x18005df96  nop
0x18005df97  test    r15b, r15b
0x18005df9a  jz      short loc_18005DFFF
0x18005df9c  mov     qword ptr [rsp+230h+dwindex], r13
0x18005dfa1  mov     rcx, [rsp+230h+var_1E8]
0x18005dfa6  mov     rax, [rcx]
0x18005dfa9  lea     r8, [rsp+230h+dwindex]
0x18005dfae  lea     rdx, _GUID_00000144_0000_0000_c000_000000000046
0x18005dfb5  mov     rax, [rax]
0x18005dfb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dfbd  nop
0x18005dfbe  test    eax, eax
0x18005dfc0  js      short loc_18005DFE3
0x18005dfc2  mov     rcx, qword ptr [rsp+230h+dwindex]
0x18005dfc7  mov     rax, [rcx]
0x18005dfca  mov     r9d, 1
0x18005dfd0  lea     r8d, [r9+4]
0x18005dfd4  mov     rdx, [rsp+230h+var_1E8]
0x18005dfd9  mov     rax, [rax+18h]
0x18005dfdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dfe2  nop
0x18005dfe3  mov     rcx, qword ptr [rsp+230h+dwindex]
0x18005dfe8  test    rcx, rcx
0x18005dfeb  jz      short loc_18005DFFF
0x18005dfed  mov     qword ptr [rsp+230h+dwindex], r13
0x18005dff2  mov     rax, [rcx]
0x18005dff5  mov     rax, [rax+10h]
0x18005dff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dffe  nop
0x18005dfff  mov     rcx, [rsp+230h+var_1E8]
0x18005e004  mov     rax, [rcx]
0x18005e007  mov     rdx, [rsp+230h+var_1D8]
0x18005e00c  mov     rax, [rax+18h]
0x18005e010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e015  mov     edi, eax
0x18005e017  cmp     [rsp+230h+var_1C8], r13d
0x18005e01c  jl      short loc_18005E040
0x18005e01e  mov     [rsp+230h+var_1C8], esi
0x18005e022  xor     ecx, ecx; pReserved
0x18005e024  call    cs:__imp_CoDisableCallCancellation
0x18005e02a  mov     rdx, [rsp+230h+phNewTimer]; Timer
0x18005e02f  test    rdx, rdx
0x18005e032  jz      short loc_18005E040
0x18005e034  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18005e038  xor     ecx, ecx; TimerQueue
0x18005e03a  call    cs:__imp_DeleteTimerQueueTimer
0x18005e040  mov     rcx, [rsp+230h+var_1D8]
0x18005e045  mov     eax, 1
0x18005e04a  xchg    eax, [rcx+74h]
0x18005e04d  mov     r14d, 80070490h
0x18005e053  test    edi, edi
0x18005e055  js      loc_18005E16B
0x18005e05b  mov     rax, [rsp+230h+var_1D8]
0x18005e060  mov     rcx, [rax+68h]
0x18005e064  mov     [rsp+230h+pHandles], rcx
0x18005e069  test    rcx, rcx
0x18005e06c  jz      loc_18005E1D4
0x18005e072  call    IsMsgWaitForMultipleObjectsExPresent
0x18005e077  test    al, al
0x18005e079  jz      short loc_18005E0BE
0x18005e07b  call    IsPeekMessageWPresent
0x18005e080  test    al, al
0x18005e082  jz      short loc_18005E0BE
0x18005e084  mov     rax, [rsp+230h+pHandles]
0x18005e089  mov     qword ptr [rsp+230h+dwindex], rax
0x18005e08e  mov     r8d, r13d
0x18005e091  test    rax, rax
0x18005e094  setnz   r8b; unsigned int
0x18005e098  lea     rdx, [rsp+230h+dwindex]; void **
0x18005e09d  call    ?SHProcessMessagesUntilEventsEx@@YAKPEAUHWND__@@PEAPEAXKKKK@Z; SHProcessMessagesUntilEventsEx(HWND__ *,void * *,ulong,ulong,ulong,ulong)
0x18005e0a2  test    eax, eax
0x18005e0a4  jz      short loc_18005E0F5
0x18005e0a6  cmp     eax, 102h
0x18005e0ab  jnz     short loc_18005E0B7
0x18005e0ad  mov     edi, 8001011Fh
0x18005e0b2  jmp     loc_18005E173
0x18005e0b7  mov     edi, esi
0x18005e0b9  jmp     loc_18005E1D4
0x18005e0be  mov     [rsp+230h+dwindex], r13d
0x18005e0c3  lea     rax, [rsp+230h+dwindex]
0x18005e0c8  mov     qword ptr [rsp+230h+DueTime], rax; lpdwindex
0x18005e0cd  lea     r9, [rsp+230h+pHandles]; pHandles
0x18005e0d2  mov     edx, 57E40h; dwTimeout
0x18005e0d7  mov     ecx, 8; dwFlags
0x18005e0dc  lea     r8d, [rcx-7]; cHandles
0x18005e0e0  call    cs:__imp_CoWaitForMultipleHandles
0x18005e0e6  mov     edi, eax
0x18005e0e8  test    eax, eax
0x18005e0ea  jns     short loc_18005E0F5
0x18005e0ec  cmp     eax, 80010115h
0x18005e0f1  jnz     short loc_18005E16B
0x18005e0f3  jmp     short loc_18005E0AD
0x18005e0f5  mov     qword ptr [rsp+230h+dwindex], r13
0x18005e0fa  mov     rax, [r12]
0x18005e0fe  lea     r8, [rsp+230h+dwindex]
0x18005e103  lea     rdx, _GUID_cd1c0ba1_0ccb_4a33_9652_fe27a738c219
0x18005e10a  mov     rcx, r12
0x18005e10d  mov     rax, [rax]
0x18005e110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e115  mov     edi, eax
0x18005e117  test    eax, eax
0x18005e119  js      short loc_18005E14F
0x18005e11b  mov     rsi, qword ptr [rsp+230h+dwindex]
0x18005e120  mov     rax, [rsi]
0x18005e123  mov     rdi, [rax+30h]
0x18005e127  lea     rdx, [rbp+130h+var_60]
0x18005e12e  lea     rcx, [rsp+230h+Parameter]
0x18005e133  call    ??$?0PEBG@StringReference@Internal@Windows@@QEAA@AEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::StringReference::StringReference(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x18005e138  mov     rdx, [rax]
0x18005e13b  mov     rcx, rsi
0x18005e13e  mov     rax, rdi
0x18005e141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e146  mov     edi, r14d
0x18005e149  test    eax, eax
0x18005e14b  cmovnz  edi, r13d
0x18005e14f  mov     rcx, qword ptr [rsp+230h+dwindex]
0x18005e154  test    rcx, rcx
0x18005e157  jz      short loc_18005E16B
0x18005e159  mov     qword ptr [rsp+230h+dwindex], r13
0x18005e15e  mov     rax, [rcx]
0x18005e161  mov     rax, [rax+10h]
0x18005e165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e16a  nop
0x18005e16b  cmp     edi, 8001011Fh
0x18005e171  jnz     short loc_18005E19C
0x18005e173  mov     [rsp+230h+pHandles], r13
0x18005e178  xor     r9d, r9d; cchBufferMax
0x18005e17b  lea     r8, [rsp+230h+pHandles]; lpBuffer
  ... truncated ...
```
