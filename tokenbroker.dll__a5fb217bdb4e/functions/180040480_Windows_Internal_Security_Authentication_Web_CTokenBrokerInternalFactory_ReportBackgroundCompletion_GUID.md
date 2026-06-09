# Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::ReportBackgroundCompletion(_GUID)

- ea: `0x180040480`
- end: `0x180040788`
- name: `?ReportBackgroundCompletion@CTokenBrokerInternalFactory@Web@Authentication@Security@Internal@Windows@@UEAAJU_GUID@@@Z`
- size: `776`
- prototype: `int(Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000bd40`
- `0x18001e700`
- `0x18002071c`
- `0x180020c60`
- `0x180021750`
- `0x180023090`
- `0x1800231c0`
- `0x180040480`
- `0x180040790`
- `0x1800407e8`
- `0x180040880`
- `0x180040964`
- `0x18007f93c`
- `0x18008e690`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004055c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004055c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180040547`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180040547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004069f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004069f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040716`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040590`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800406ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040590`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800406ea`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180040529`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180040529`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040664`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040664`

## string_xrefs

- `0x1800405f7`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x180040645`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800406c7`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x18004073e`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800404e5`: `Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::ReportBackgroundCompletion`
- `0x1800404ab`: `TokenBrokerInternalReportBackgroundCompletion`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::ReportBackgroundCompletion(
        unsigned __int64 this,
        struct _GUID *a2)
{
  __int64 v4; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  HRESULT v7; // eax
  unsigned int v8; // ebx
  HANDLE EventW; // rbx
  LPOLESTR v10; // rcx
  LPOLESTR v12; // rcx
  signed int v13; // eax
  unsigned int v14; // edi
  signed int LastError; // eax
  unsigned int v16; // edi
  int v17; // [rsp+20h] [rbp-1A8h]
  LPOLESTR lpsz; // [rsp+30h] [rbp-198h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-190h] BYREF
  char v20; // [rsp+40h] [rbp-188h]
  _BYTE v21[24]; // [rsp+48h] [rbp-180h] BYREF
  _QWORD v22[42]; // [rsp+60h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v22,
    "TokenBrokerInternalReportBackgroundCompletion");
  v22[0] = &TbLogProvider::TokenBrokerInternalReportBackgroundCompletion::`vftable';
  TbLogProvider::TokenBrokerInternalReportBackgroundCompletion::StartActivity((TbLogProvider::TokenBrokerInternalReportBackgroundCompletion *)v22);
  Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(
    v4,
    (__int64)v21,
    (struct IUnknown *)(this & -(__int64)(this != 40)),
    "Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::ReportBackgroundCompletion",
    0);
  TokenHandle = 0;
  v20 = 0;
  v5 = Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::Suspend(&TokenHandle);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x138,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v5,
      v17);
    Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&TokenHandle);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v21);
    v22[0] = &TbLogProvider::TokenBrokerInternalReportBackgroundCompletion::`vftable';
    wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v22);
    wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v22);
    return v6;
  }
  else
  {
    lpsz = 0;
    v7 = StringFromCLSID(a2, &lpsz);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13D,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
        (const char *)(unsigned int)v7,
        v17);
      v12 = lpsz;
      lpsz = 0;
      CoTaskMemFree(v12);
      Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&TokenHandle);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v21);
      v22[0] = &TbLogProvider::TokenBrokerInternalReportBackgroundCompletion::`vftable';
      wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v22);
      wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v22);
      return v8;
    }
    else
    {
      EventW = CreateEventW(0, 1, 0, lpsz);
      if ( EventW )
        goto LABEL_12;
      LastError = GetLastError();
      v16 = LastError;
      if ( LastError > 0 )
        v16 = (unsigned __int16)LastError | 0x80070000;
      if ( (v16 & 0x80000000) == 0 )
      {
LABEL_12:
        if ( SetEvent(EventW) )
          goto LABEL_5;
        v13 = GetLastError();
        v14 = v13;
        if ( v13 > 0 )
          v14 = (unsigned __int16)v13 | 0x80070000;
        if ( (v14 & 0x80000000) == 0 )
        {
LABEL_5:
          wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v22);
          v10 = lpsz;
          lpsz = 0;
          CoTaskMemFree(v10);
          if ( EventW )
            CloseHandle(EventW);
          Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&TokenHandle);
          Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v21);
          v22[0] = &TbLogProvider::TokenBrokerInternalReportBackgroundCompletion::`vftable';
          wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v22);
          wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v22);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x13F,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
            (const char *)v14,
            v17);
          CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpsz);
          if ( EventW )
            CloseHandle(EventW);
          Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&TokenHandle);
          Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v21);
          TbLogProvider::TokenBrokerInternalReportBackgroundCompletion::~TokenBrokerInternalReportBackgroundCompletion((TbLogProvider::TokenBrokerInternalReportBackgroundCompletion *)v22);
          return v14;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13E,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
          (const char *)v16,
          v17);
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpsz);
        Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&TokenHandle);
        Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v21);
        TbLogProvider::TokenBrokerInternalReportBackgroundCompletion::~TokenBrokerInternalReportBackgroundCompletion((TbLogProvider::TokenBrokerInternalReportBackgroundCompletion *)v22);
        return v16;
      }
    }
  }
}

```

## disassembly

```asm
0x180040480  mov     [rsp+arg_10], rbx
0x180040485  mov     [rsp+arg_18], rdi
0x18004048a  push    r14
0x18004048c  sub     rsp, 1C0h
0x180040493  mov     rax, cs:__security_cookie
0x18004049a  xor     rax, rsp
0x18004049d  mov     [rsp+1C8h+var_18], rax
0x1800404a5  mov     rdi, rdx
0x1800404a8  mov     rbx, rcx
0x1800404ab  lea     rdx, aTokenbrokerint_6; "TokenBrokerInternalReportBackgroundComp"...
0x1800404b2  lea     rcx, [rsp+1C8h+var_168]
0x1800404b7  call    ??0?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800404bc  lea     r14, ??_7TokenBrokerInternalReportBackgroundCompletion@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalReportBackgroundCompletion::`vftable'
0x1800404c3  mov     [rsp+1C8h+var_168], r14
0x1800404c8  lea     rcx, [rsp+1C8h+var_168]; this
0x1800404cd  call    ?StartActivity@TokenBrokerInternalReportBackgroundCompletion@TbLogProvider@@QEAAXXZ; TbLogProvider::TokenBrokerInternalReportBackgroundCompletion::StartActivity(void)
0x1800404d2  nop
0x1800404d3  lea     rax, [rbx-28h]
0x1800404d7  neg     rax
0x1800404da  sbb     r8, r8
0x1800404dd  and     r8, rbx
0x1800404e0  mov     byte ptr [rsp+1C8h+var_1A8], 0; int
0x1800404e5  lea     r9, aWindowsInterna_18; "Windows::Internal::Security::Authentica"...
0x1800404ec  lea     rdx, [rsp+1C8h+var_180]
0x1800404f1  call    ?ProfileCaller@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@QEAA?AVCWamProfilerThreadScope@23456@PEAUIUnknown@@PEBD_N@Z; Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(IUnknown *,char const *,bool)
0x1800404f6  mov     [rsp+1C8h+TokenHandle], 0
0x1800404ff  mov     [rsp+1C8h+var_188], 0
0x180040504  lea     rcx, [rsp+1C8h+TokenHandle]; TokenHandle
0x180040509  call    ?Suspend@SuspendImpersonationScope@Web@Authentication@Security@Internal@Windows@@QEAAJXZ; Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::Suspend(void)
0x18004050e  mov     ebx, eax
0x180040510  test    eax, eax
0x180040512  js      loc_1800405EC
0x180040518  mov     [rsp+1C8h+lpsz], 0
0x180040521  lea     rdx, [rsp+1C8h+lpsz]; lplpsz
0x180040526  mov     rcx, rdi; rclsid
0x180040529  call    cs:__imp_StringFromCLSID
0x18004052f  mov     ebx, eax
0x180040531  test    eax, eax
0x180040533  js      loc_18004063A
0x180040539  mov     r9, [rsp+1C8h+lpsz]; lpName
0x18004053e  xor     r8d, r8d; bInitialState
0x180040541  lea     edx, [r8+1]; bManualReset
0x180040545  xor     ecx, ecx; lpEventAttributes
0x180040547  call    cs:__imp_CreateEventW
0x18004054d  mov     rbx, rax
0x180040550  test    rax, rax
0x180040553  jz      loc_180040716
0x180040559  mov     rcx, rbx; hEvent
0x18004055c  call    cs:__imp_SetEvent
0x180040562  test    eax, eax
0x180040564  jz      loc_18004069F
0x18004056a  lea     rcx, [rsp+1C8h+var_168]
0x18004056f  call    ?Stop@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180040574  mov     rcx, [rsp+1C8h+lpsz]; pv
0x180040579  mov     [rsp+1C8h+lpsz], 0
0x180040582  call    cs:__imp_CoTaskMemFree
0x180040588  test    rbx, rbx
0x18004058b  jz      short loc_180040596
0x18004058d  mov     rcx, rbx; hObject
0x180040590  call    cs:__imp_CloseHandle
0x180040596  lea     rcx, [rsp+1C8h+TokenHandle]; this
0x18004059b  call    ??1SuspendImpersonationScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope(void)
0x1800405a0  lea     rcx, [rsp+1C8h+var_180]; this
0x1800405a5  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800405aa  nop
0x1800405ab  mov     [rsp+1C8h+var_168], r14
0x1800405b0  lea     rcx, [rsp+1C8h+var_168]
0x1800405b5  call    ?Destroy@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800405ba  lea     rcx, [rsp+1C8h+var_168]
0x1800405bf  call    ??1?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800405c4  xor     eax, eax
0x1800405c6  mov     rcx, [rsp+1C8h+var_18]
0x1800405ce  xor     rcx, rsp; StackCookie
0x1800405d1  call    __security_check_cookie
0x1800405d6  lea     r11, [rsp+1C8h+var_8]
0x1800405de  mov     rbx, [r11+20h]
0x1800405e2  mov     rdi, [r11+28h]
0x1800405e6  mov     rsp, r11
0x1800405e9  pop     r14
0x1800405eb  retn
0x1800405ec  mov     rcx, [rsp+1C8h]; this
0x1800405f4  mov     r9d, ebx; char *
0x1800405f7  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800405fe  mov     edx, 138h; void *
0x180040603  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040608  lea     rcx, [rsp+1C8h+TokenHandle]; this
0x18004060d  call    ??1SuspendImpersonationScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope(void)
0x180040612  lea     rcx, [rsp+1C8h+var_180]; this
0x180040617  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18004061c  nop
0x18004061d  mov     [rsp+1C8h+var_168], r14
0x180040622  lea     rcx, [rsp+1C8h+var_168]
0x180040627  call    ?Destroy@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18004062c  lea     rcx, [rsp+1C8h+var_168]
0x180040631  call    ??1?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180040636  mov     eax, ebx
0x180040638  jmp     short loc_1800405C6
0x18004063a  mov     rcx, [rsp+1C8h]; this
0x180040642  mov     r9d, ebx; char *
0x180040645  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18004064c  mov     edx, 13Dh; void *
0x180040651  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040656  mov     rcx, [rsp+1C8h+lpsz]; pv
0x18004065b  mov     [rsp+1C8h+lpsz], 0
0x180040664  call    cs:__imp_CoTaskMemFree
0x18004066a  lea     rcx, [rsp+1C8h+TokenHandle]; this
0x18004066f  call    ??1SuspendImpersonationScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope(void)
0x180040674  lea     rcx, [rsp+1C8h+var_180]; this
0x180040679  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18004067e  nop
0x18004067f  mov     [rsp+1C8h+var_168], r14
0x180040684  lea     rcx, [rsp+1C8h+var_168]
0x180040689  call    ?Destroy@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18004068e  lea     rcx, [rsp+1C8h+var_168]
0x180040693  call    ??1?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180040698  mov     eax, ebx
0x18004069a  jmp     loc_1800405C6
0x18004069f  call    cs:__imp_GetLastError
0x1800406a5  mov     edi, eax
0x1800406a7  test    eax, eax
0x1800406a9  jle     short loc_1800406B4
0x1800406ab  movzx   edi, ax
0x1800406ae  or      edi, 80070000h
0x1800406b4  test    edi, edi
0x1800406b6  jns     loc_18004056A
0x1800406bc  mov     rcx, [rsp+1C8h]; this
0x1800406c4  mov     r9d, edi; char *
0x1800406c7  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800406ce  mov     edx, 13Fh; void *
0x1800406d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800406d8  lea     rcx, [rsp+1C8h+lpsz]
0x1800406dd  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800406e2  test    rbx, rbx
0x1800406e5  jz      short loc_1800406F0
0x1800406e7  mov     rcx, rbx; hObject
0x1800406ea  call    cs:__imp_CloseHandle
0x1800406f0  lea     rcx, [rsp+1C8h+TokenHandle]; this
0x1800406f5  call    ??1SuspendImpersonationScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope(void)
0x1800406fa  lea     rcx, [rsp+1C8h+var_180]; this
0x1800406ff  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x180040704  nop
0x180040705  lea     rcx, [rsp+1C8h+var_168]; this
0x18004070a  call    ??1TokenBrokerInternalReportBackgroundCompletion@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalReportBackgroundCompletion::~TokenBrokerInternalReportBackgroundCompletion(void)
0x18004070f  mov     eax, edi
0x180040711  jmp     loc_1800405C6
0x180040716  call    cs:__imp_GetLastError
0x18004071c  mov     edi, eax
0x18004071e  test    eax, eax
0x180040720  jle     short loc_18004072B
0x180040722  movzx   edi, ax
0x180040725  or      edi, 80070000h
0x18004072b  test    edi, edi
0x18004072d  jns     loc_180040559
0x180040733  mov     rcx, [rsp+1C8h]; this
0x18004073b  mov     r9d, edi; char *
0x18004073e  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180040745  mov     edx, 13Eh; void *
0x18004074a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004074f  lea     rcx, [rsp+1C8h+lpsz]
0x180040754  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180040759  lea     rcx, [rsp+1C8h+TokenHandle]; this
0x18004075e  call    ??1SuspendImpersonationScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope(void)
0x180040763  lea     rcx, [rsp+1C8h+var_180]; this
0x180040768  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18004076d  nop
0x18004076e  lea     rcx, [rsp+1C8h+var_168]; this
0x180040773  call    ??1TokenBrokerInternalReportBackgroundCompletion@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalReportBackgroundCompletion::~TokenBrokerInternalReportBackgroundCompletion(void)
0x180040778  mov     eax, edi
0x18004077a  jmp     loc_1800405C6
0x18004077f  mov     eax, dword ptr [rsp+1C8h+lpsz]
0x180040783  jmp     loc_1800405C6
```
