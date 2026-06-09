# FederatedDownloadJob::BeginDownloadInternal(IUpdateSession2 *,IUpdateCollection *,ulong,tagDownloadPriority,tagNetworkCostPolicy,UpdateIdToHardReserveIdMap const &,void * const,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,tagAttributeTargeting)

- ea: `0x180012e54`
- end: `0x1800132bd`
- name: `?BeginDownloadInternal@FederatedDownloadJob@@AEAAJPEAUIUpdateSession2@@PEAUIUpdateCollection@@KW4tagDownloadPriority@@W4tagNetworkCostPolicy@@AEBVUpdateIdToHardReserveIdMap@@QEAXPEB_W666UtagAttributeTargeting@@@Z`
- size: `1129`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180012d30`

## callees

- `0x180006ac4`
- `0x180007d34`
- `0x18000ed90`
- `0x180012ad0`
- `0x180012e54`
- `0x1800132c4`
- `0x180013794`
- `0x180016e70`
- `0x180016e9c`
- `0x18006d780`
- `0x180081a38`
- `0x180082b28`
- `0x180090bc8`
- `0x1800940b4`
- `0x180096b10`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800130ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800130ce`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800130e2`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800130e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800131dc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001320b`
- `OLEAUT32!__imp_SysFreeString` at `0x180013239`
- `OLEAUT32!__imp_SysFreeString` at `0x1800131dc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001320b`
- `OLEAUT32!__imp_SysFreeString` at `0x180013239`

## string_xrefs

- `0x180012ee2`: `C:\__w\1\s\src\Client\comapi\FederatedDownloadJob.cpp`
- `0x180012f5e`: `C:\__w\1\s\src\Client\comapi\FederatedDownloadJob.cpp`
- `0x1800130f4`: `C:\__w\1\s\src\Client\comapi\FederatedDownloadJob.cpp`

## pseudocode

```c
__int64 __fastcall FederatedDownloadJob::BeginDownloadInternal(
        __int64 a1,
        __int64 a2,
        struct IUpdateCollection *a3,
        int a4,
        int a5,
        int a6,
        UpdateIdToHardReserveIdMap *a7,
        HANDLE ExistingTokenHandle,
        __int64 a9,
        const WCHAR *lpString1,
        __int64 a11,
        __int64 a12,
        wchar_t **a13)
{
  __int64 v16; // rdx
  int started; // ebx
  struct IUpdateCollection v19; // rax
  const wchar_t *v20; // rdx
  bool v21; // zf
  const wchar_t *v22; // rax
  __int64 v23; // rcx
  void *v24; // rcx
  const char *v25; // r9
  void *v26; // rcx
  void *v27; // rcx
  void *v28; // rcx
  wchar_t *v29; // rcx
  wchar_t *v30; // rcx
  wchar_t *v31; // rcx
  int v32; // [rsp+20h] [rbp-88h]
  unsigned int v34; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  if ( !a2 )
  {
    v16 = 113;
LABEL_3:
    started = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\FederatedDownloadJob.cpp",
      (const char *)(unsigned int)started,
      v32);
    return (unsigned int)started;
  }
  if ( !a3 )
  {
    v16 = 114;
    goto LABEL_3;
  }
  v19.lpVtbl = a3->lpVtbl;
  v34 = 0;
  started = ((__int64 (__fastcall *)(struct IUpdateCollection *, unsigned int *))v19.lpVtbl->get_Count)(a3, &v34);
  if ( started < 0 )
  {
    v16 = 118;
    goto LABEL_4;
  }
  if ( !v34 )
  {
    started = -2145124316;
    v16 = 119;
    goto LABEL_4;
  }
  if ( (unsigned int)AreTestKeysAllowed(1) && TestRegUtil::IsClientBlocked(lpString1, v20) )
  {
    started = -2145124351;
    wil::details::in1diag3::Return_HrSuppressTelemetry(
      retaddr,
      (void *)0x7C,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\FederatedDownloadJob.cpp",
      (const char *)0x80240001LL,
      v32);
    return (unsigned int)started;
  }
  WUTrace(
    0,
    0,
    0x10000,
    4,
    0,
    L"* START *   Federated Download ClientId = %ws (cV = %hs)",
    lpString1,
    *(_QWORD *)(a1 + 408));
  if ( a11 )
  {
    v21 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl'::`2'::impl) == 0;
    v22 = L"Downloader SessionData = %ws";
    if ( v21 )
      v22 = L"SessionData = %ws";
    WUTrace(0, 0, 0x10000, 4, 0, v22, a11);
  }
  if ( a12 )
    WUTrace(0, 0, 0x10000, 4, 0, L"IntentPFaNs = %ws");
  started = FederatedDownloadJob::CopyUpdatesAndMapByServiceId((FederatedDownloadJob *)a1, a3);
  if ( started < 0 )
  {
    v16 = 149;
    goto LABEL_4;
  }
  started = UpdateIdToHardReserveIdMap::CopyTo(a7, (struct UpdateIdToHardReserveIdMap *)(a1 + 952));
  if ( started < 0 )
  {
    v16 = 152;
    goto LABEL_4;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  v23 = *(_QWORD *)(a1 + 672);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  *(_QWORD *)(a1 + 672) = a2;
  *(_DWORD *)(a1 + 684) = a5;
  *(_DWORD *)(a1 + 680) = a4;
  *(_DWORD *)(a1 + 688) = a6;
  if ( !ExistingTokenHandle )
    goto LABEL_32;
  v24 = *(void **)(a1 + 696);
  if ( v24 )
  {
    CloseHandle(v24);
    *(_QWORD *)(a1 + 696) = 0;
  }
  if ( !DuplicateToken(ExistingTokenHandle, SecurityIdentification, (PHANDLE)(a1 + 696)) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xA7,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\FederatedDownloadJob.cpp",
             v25);
LABEL_32:
  *(_BYTE *)(a1 + 464) = (a4 & 0x940) != 0;
  v26 = *(void **)(a1 + 704);
  if ( v26 )
  {
    SusFree(v26);
    *(_QWORD *)(a1 + 704) = 0;
  }
  started = DuplicateOptionalString<wchar_t const *,wchar_t *>(a9, a1 + 704);
  if ( started < 0 )
  {
    v16 = 178;
    goto LABEL_4;
  }
  started = DuplicateOptionalString<wchar_t const *,wchar_t *>(lpString1, a1 + 456);
  if ( started < 0 )
  {
    v16 = 179;
    goto LABEL_4;
  }
  v27 = *(void **)(a1 + 712);
  if ( v27 )
  {
    SusFree(v27);
    *(_QWORD *)(a1 + 712) = 0;
  }
  started = DuplicateOptionalString<wchar_t const *,wchar_t *>(a11, a1 + 712);
  if ( started < 0 )
  {
    v16 = 180;
    goto LABEL_4;
  }
  v28 = *(void **)(a1 + 720);
  if ( v28 )
  {
    SusFree(v28);
    *(_QWORD *)(a1 + 720) = 0;
  }
  started = DuplicateOptionalString<wchar_t const *,wchar_t *>(a12, a1 + 720);
  if ( started < 0 )
  {
    v16 = 181;
    goto LABEL_4;
  }
  SysFreeString(*(BSTR *)(a1 + 728));
  v29 = a13[1];
  *(_QWORD *)(a1 + 728) = 0;
  started = SusCopyBSTR(v29, (wchar_t **)(a1 + 728));
  if ( started < 0 )
  {
    v16 = 183;
    goto LABEL_4;
  }
  SysFreeString(*(BSTR *)(a1 + 736));
  v30 = *a13;
  *(_QWORD *)(a1 + 736) = 0;
  started = SusCopyBSTR(v30, (wchar_t **)(a1 + 736));
  if ( started < 0 )
  {
    v16 = 184;
    goto LABEL_4;
  }
  SysFreeString(*(BSTR *)(a1 + 744));
  v31 = a13[2];
  *(_QWORD *)(a1 + 744) = 0;
  started = SusCopyBSTR(v31, (wchar_t **)(a1 + 744));
  if ( started < 0 )
  {
    v16 = 185;
    goto LABEL_4;
  }
  started = CDownloadResult::Initialize(*(CDownloadResult **)(a1 + 448), v34);
  if ( started < 0 )
  {
    v16 = 187;
    goto LABEL_4;
  }
  started = FederatedDownloadJob::StartFederationWorker((FederatedDownloadJob *)a1);
  if ( started < 0 )
  {
    v16 = 193;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x180012e54  mov     [rsp+arg_18], rbx
0x180012e59  push    rbp
0x180012e5a  push    rsi
0x180012e5b  push    rdi
0x180012e5c  push    r12
0x180012e5e  push    r13
0x180012e60  push    r14
0x180012e62  push    r15
0x180012e64  sub     rsp, 70h
0x180012e68  mov     rax, cs:__security_cookie
0x180012e6f  xor     rax, rsp
0x180012e72  mov     [rsp+0A8h+var_40], rax
0x180012e77  mov     rax, [rsp+0A8h+arg_30]
0x180012e7f  mov     rdi, rcx
0x180012e82  mov     rcx, [rsp+0A8h+arg_58]
0x180012e8a  mov     rsi, r8
0x180012e8d  mov     r15, [rsp+0A8h+arg_60]
0x180012e95  mov     r14, rdx
0x180012e98  mov     r13, [rsp+0A8h+ExistingTokenHandle]
0x180012ea0  mov     r12, [rsp+0A8h+lpString1]
0x180012ea8  mov     rbp, [rsp+0A8h+arg_50]
0x180012eb0  mov     [rsp+0A8h+var_58], rax
0x180012eb5  mov     rax, [rsp+0A8h+arg_40]
0x180012ebd  mov     [rsp+0A8h+var_50], rax
0x180012ec2  mov     [rsp+0A8h+var_68], r9d
0x180012ec7  mov     [rsp+0A8h+var_60], rcx
0x180012ecc  test    rdx, rdx
0x180012ecf  jnz     short loc_180012EF8
0x180012ed1  lea     edx, [r14+71h]; void *
0x180012ed5  mov     ebx, 80004003h
0x180012eda  mov     rcx, [rsp+0A8h]; this
0x180012ee2  lea     r8, aCW1SSrcClientC_38; "C:\\__w\\1\\s\\src\\Client\\comapi\\Fed"...
0x180012ee9  mov     r9d, ebx; char *
0x180012eec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ef1  mov     eax, ebx
0x180012ef3  jmp     loc_180013298
0x180012ef8  test    rsi, rsi
0x180012efb  jnz     short loc_180012F02
0x180012efd  lea     edx, [rsi+72h]
0x180012f00  jmp     short loc_180012ED5
0x180012f02  mov     rax, [r8]
0x180012f05  lea     rdx, [rsp+0A8h+var_48]
0x180012f0a  mov     rcx, rsi
0x180012f0d  mov     [rsp+0A8h+var_48], 0
0x180012f15  mov     rax, [rax+50h]
0x180012f19  call    _guard_dispatch_icall
0x180012f1e  mov     ebx, eax
0x180012f20  test    eax, eax
0x180012f22  jns     short loc_180012F2B
0x180012f24  mov     edx, 76h ; 'v'
0x180012f29  jmp     short loc_180012EDA
0x180012f2b  xor     ebx, ebx
0x180012f2d  cmp     [rsp+0A8h+var_48], ebx
0x180012f31  jnz     short loc_180012F3F
0x180012f33  mov     ebx, 80240024h
0x180012f38  mov     edx, 77h ; 'w'
0x180012f3d  jmp     short loc_180012EDA
0x180012f3f  mov     cl, 1; bool
0x180012f41  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x180012f46  test    eax, eax
0x180012f48  jz      short loc_180012F7C
0x180012f4a  mov     rcx, r12; lpString1
0x180012f4d  call    ?IsClientBlocked@TestRegUtil@@YA_NPEB_W@Z; TestRegUtil::IsClientBlocked(wchar_t const *)
0x180012f52  test    al, al
0x180012f54  jz      short loc_180012F7C
0x180012f56  mov     rcx, [rsp+0A8h]; this
0x180012f5e  lea     r8, aCW1SSrcClientC_38; "C:\\__w\\1\\s\\src\\Client\\comapi\\Fed"...
0x180012f65  mov     ebx, 80240001h
0x180012f6a  mov     edx, 7Ch ; '|'; void *
0x180012f6f  mov     r9d, ebx; char *
0x180012f72  call    ?Return_HrSuppressTelemetry@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_HrSuppressTelemetry(void *,uint,char const *,long)
0x180012f77  jmp     loc_180012EF1
0x180012f7c  mov     rax, [rdi+198h]
0x180012f83  xor     edx, edx
0x180012f85  mov     [rsp+0A8h+var_70], rax
0x180012f8a  xor     ecx, ecx
0x180012f8c  lea     rax, aStartFederated; "* START *   Federated Download ClientId"...
0x180012f93  mov     [rsp+0A8h+var_78], r12
0x180012f98  mov     [rsp+0A8h+var_80], rax
0x180012f9d  mov     r8d, 10000h
0x180012fa3  lea     r9d, [rdx+4]
0x180012fa7  mov     [rsp+0A8h+var_88], rbx
0x180012fac  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180012fb1  test    rbp, rbp
0x180012fb4  jz      short loc_180012FF6
0x180012fb6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl(void)'::`2'::impl
0x180012fbd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(void)
0x180012fc2  xor     edx, edx
0x180012fc4  mov     [rsp+0A8h+var_78], rbp
0x180012fc9  xor     ecx, ecx
0x180012fcb  mov     r8d, 10000h
0x180012fd1  test    al, al
0x180012fd3  lea     rax, aDownloaderSess; "Downloader SessionData = %ws"
0x180012fda  lea     r9d, [rdx+4]
0x180012fde  jnz     short loc_180012FE7
0x180012fe0  lea     rax, aSessiondataWs; "SessionData = %ws"
0x180012fe7  mov     [rsp+0A8h+var_80], rax
0x180012fec  mov     [rsp+0A8h+var_88], rbx
0x180012ff1  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180012ff6  mov     rax, [rsp+0A8h+var_60]
0x180012ffb  test    rax, rax
0x180012ffe  jz      short loc_180013029
0x180013000  mov     [rsp+0A8h+var_78], rax
0x180013005  xor     edx, edx
0x180013007  lea     rax, aIntentpfansWs; "IntentPFaNs = %ws"
0x18001300e  xor     ecx, ecx
0x180013010  mov     [rsp+0A8h+var_80], rax
0x180013015  mov     r8d, 10000h
0x18001301b  mov     [rsp+0A8h+var_88], rbx
0x180013020  lea     r9d, [rdx+4]
0x180013024  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180013029  mov     rdx, rsi; struct IUpdateCollection *
0x18001302c  mov     rcx, rdi; this
0x18001302f  call    ?CopyUpdatesAndMapByServiceId@FederatedDownloadJob@@AEAAJPEAUIUpdateCollection@@@Z; FederatedDownloadJob::CopyUpdatesAndMapByServiceId(IUpdateCollection *)
0x180013034  mov     ebx, eax
0x180013036  test    eax, eax
0x180013038  jns     short loc_180013044
0x18001303a  mov     edx, 95h
0x18001303f  jmp     loc_180012EDA
0x180013044  mov     rcx, [rsp+0A8h+var_58]; this
0x180013049  lea     rdx, [rdi+3B8h]; struct UpdateIdToHardReserveIdMap *
0x180013050  call    ?CopyTo@UpdateIdToHardReserveIdMap@@QEBAJPEAV1@@Z; UpdateIdToHardReserveIdMap::CopyTo(UpdateIdToHardReserveIdMap *)
0x180013055  mov     ebx, eax
0x180013057  test    eax, eax
0x180013059  jns     short loc_180013065
0x18001305b  mov     edx, 98h
0x180013060  jmp     loc_180012EDA
0x180013065  mov     rax, [r14]
0x180013068  mov     rcx, r14
0x18001306b  mov     rax, [rax+8]
0x18001306f  call    _guard_dispatch_icall
0x180013074  mov     rcx, [rdi+2A0h]
0x18001307b  test    rcx, rcx
0x18001307e  jz      short loc_18001308C
0x180013080  mov     rax, [rcx]
0x180013083  mov     rax, [rax+10h]
0x180013087  call    _guard_dispatch_icall
0x18001308c  mov     eax, [rsp+0A8h+arg_20]
0x180013093  mov     esi, [rsp+0A8h+var_68]
0x180013097  mov     [rdi+2A0h], r14
0x18001309e  xor     r14d, r14d
0x1800130a1  mov     [rdi+2ACh], eax
0x1800130a7  mov     eax, [rsp+0A8h+arg_28]
0x1800130ae  mov     [rdi+2A8h], esi
0x1800130b4  mov     [rdi+2B0h], eax
0x1800130ba  test    r13, r13
0x1800130bd  jz      short loc_18001310A
0x1800130bf  lea     rbx, [rdi+2B8h]
0x1800130c6  mov     rcx, [rbx]; hObject
0x1800130c9  test    rcx, rcx
0x1800130cc  jz      short loc_1800130D7
0x1800130ce  call    cs:__imp_CloseHandle
0x1800130d4  mov     [rbx], r14
0x1800130d7  mov     r8, rbx; DuplicateTokenHandle
0x1800130da  mov     edx, 1; ImpersonationLevel
0x1800130df  mov     rcx, r13; ExistingTokenHandle
0x1800130e2  call    cs:__imp_DuplicateToken
0x1800130e8  test    eax, eax
0x1800130ea  jnz     short loc_18001310A
0x1800130ec  mov     rcx, [rsp+0A8h]; this
0x1800130f4  lea     r8, aCW1SSrcClientC_38; "C:\\__w\\1\\s\\src\\Client\\comapi\\Fed"...
0x1800130fb  mov     edx, 0A7h; void *
0x180013100  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013105  jmp     loc_180013298
0x18001310a  test    esi, 940h
0x180013110  lea     rbx, [rdi+2C0h]
0x180013117  setnz   al
0x18001311a  mov     [rdi+1D0h], al
0x180013120  mov     rcx, [rbx]; lpMem
0x180013123  test    rcx, rcx
0x180013126  jz      short loc_180013130
0x180013128  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18001312d  mov     [rbx], r14
0x180013130  mov     rcx, [rsp+0A8h+var_50]
0x180013135  mov     rdx, rbx
0x180013138  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x18001313d  mov     ebx, eax
0x18001313f  test    eax, eax
0x180013141  jns     short loc_18001314D
0x180013143  mov     edx, 0B2h
0x180013148  jmp     loc_180012EDA
0x18001314d  lea     rdx, [rdi+1C8h]
0x180013154  mov     rcx, r12
0x180013157  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x18001315c  mov     ebx, eax
0x18001315e  test    eax, eax
0x180013160  jns     short loc_18001316C
0x180013162  mov     edx, 0B3h
0x180013167  jmp     loc_180012EDA
0x18001316c  lea     rbx, [rdi+2C8h]
0x180013173  mov     rcx, [rbx]; lpMem
0x180013176  test    rcx, rcx
0x180013179  jz      short loc_180013183
0x18001317b  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180013180  mov     [rbx], r14
0x180013183  mov     rdx, rbx
0x180013186  mov     rcx, rbp
0x180013189  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x18001318e  mov     ebx, eax
0x180013190  test    eax, eax
0x180013192  jns     short loc_18001319E
0x180013194  mov     edx, 0B4h
0x180013199  jmp     loc_180012EDA
0x18001319e  lea     rbx, [rdi+2D0h]
0x1800131a5  mov     rcx, [rbx]; lpMem
0x1800131a8  test    rcx, rcx
0x1800131ab  jz      short loc_1800131B5
0x1800131ad  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800131b2  mov     [rbx], r14
0x1800131b5  mov     rcx, [rsp+0A8h+var_60]
0x1800131ba  mov     rdx, rbx
0x1800131bd  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x1800131c2  mov     ebx, eax
0x1800131c4  test    eax, eax
0x1800131c6  jns     short loc_1800131D2
0x1800131c8  mov     edx, 0B5h
0x1800131cd  jmp     loc_180012EDA
0x1800131d2  lea     rbx, [rdi+2D8h]
0x1800131d9  mov     rcx, [rbx]; bstrString
0x1800131dc  call    cs:__imp_SysFreeString
0x1800131e2  mov     rcx, [r15+8]; strIn
0x1800131e6  mov     rdx, rbx; wchar_t **
0x1800131e9  mov     [rbx], r14
0x1800131ec  call    ?SusCopyBSTR@@YAJPEA_WPEAPEA_W@Z; SusCopyBSTR(wchar_t *,wchar_t * *)
0x1800131f1  mov     ebx, eax
0x1800131f3  test    eax, eax
0x1800131f5  jns     short loc_180013201
0x1800131f7  mov     edx, 0B7h
0x1800131fc  jmp     loc_180012EDA
0x180013201  lea     rbx, [rdi+2E0h]
0x180013208  mov     rcx, [rbx]; bstrString
0x18001320b  call    cs:__imp_SysFreeString
0x180013211  mov     rcx, [r15]; strIn
0x180013214  mov     rdx, rbx; wchar_t **
0x180013217  mov     [rbx], r14
0x18001321a  call    ?SusCopyBSTR@@YAJPEA_WPEAPEA_W@Z; SusCopyBSTR(wchar_t *,wchar_t * *)
0x18001321f  mov     ebx, eax
0x180013221  test    eax, eax
0x180013223  jns     short loc_18001322F
0x180013225  mov     edx, 0B8h
0x18001322a  jmp     loc_180012EDA
0x18001322f  lea     rbx, [rdi+2E8h]
0x180013236  mov     rcx, [rbx]; bstrString
0x180013239  call    cs:__imp_SysFreeString
0x18001323f  mov     rcx, [r15+10h]; strIn
0x180013243  mov     rdx, rbx; wchar_t **
0x180013246  mov     [rbx], r14
0x180013249  call    ?SusCopyBSTR@@YAJPEA_WPEAPEA_W@Z; SusCopyBSTR(wchar_t *,wchar_t * *)
0x18001324e  mov     ebx, eax
0x180013250  test    eax, eax
0x180013252  jns     short loc_18001325E
0x180013254  mov     edx, 0B9h
0x180013259  jmp     loc_180012EDA
0x18001325e  mov     edx, [rsp+0A8h+var_48]; unsigned int
0x180013262  mov     rcx, [rdi+1C0h]; this
0x180013269  call    ?Initialize@CDownloadResult@@QEAAJK@Z; CDownloadResult::Initialize(ulong)
0x18001326e  mov     ebx, eax
0x180013270  test    eax, eax
0x180013272  jns     short loc_18001327E
0x180013274  mov     edx, 0BBh
0x180013279  jmp     loc_180012EDA
0x18001327e  mov     rcx, rdi; this
0x180013281  call    ?StartFederationWorker@FederatedDownloadJob@@AEAAJXZ; FederatedDownloadJob::StartFederationWorker(void)
0x180013286  mov     ebx, eax
0x180013288  test    eax, eax
0x18001328a  jns     short loc_180013296
0x18001328c  mov     edx, 0C1h
0x180013291  jmp     loc_180012EDA
0x180013296  xor     eax, eax
0x180013298  mov     rcx, [rsp+0A8h+var_40]
0x18001329d  xor     rcx, rsp; StackCookie
0x1800132a0  call    __security_check_cookie
0x1800132a5  mov     rbx, [rsp+0A8h+arg_18]
0x1800132ad  add     rsp, 70h
0x1800132b1  pop     r15
0x1800132b3  pop     r14
0x1800132b5  pop     r13
0x1800132b7  pop     r12
0x1800132b9  pop     rdi
0x1800132ba  pop     rsi
0x1800132bb  pop     rbp
0x1800132bc  retn
```
