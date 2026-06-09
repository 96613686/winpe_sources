# ?SetAppAsDefault@?QIApplicationAssociationRegistration@@CApplicationAssociationRegistration@@UEAAJPEBG0W4ASSOCIATIONTYPE@@@Z

- ea: `0x1805c42c0`
- end: `0x1805c4702`
- name: `?SetAppAsDefault@?QIApplicationAssociationRegistration@@CApplicationAssociationRegistration@@UEAAJPEBG0W4ASSOCIATIONTYPE@@@Z`
- size: `1090`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800371a8`
- `0x1800432f0`
- `0x1800d13a0`
- `0x18012bd20`
- `0x180165250`
- `0x1802d2c54`
- `0x180302dcc`
- `0x18035f034`
- `0x1803790e4`
- `0x1803a4cb0`
- `0x1805c27a0`
- `0x1805c2a3c`
- `0x1805c2d4c`
- `0x1805c376c`
- `0x1805c42c0`
- `0x1805c48a0`
- `0x1805c4a50`
- `0x1805c4c28`
- `0x1805c673c`
- `0x1805e8890`
- `0x1805f968c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1805c4383`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1805c4547`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1805c456e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1805c4383`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1805c4547`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1805c456e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c447c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c4491`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c44cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c4502`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c45fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c460d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c461e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c462f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c4688`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c4699`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c46aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c46bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c447c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c4491`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c44cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c4502`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c45fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c460d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c461e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c462f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c4688`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c4699`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c46aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805c46bb`

## string_xrefs

- `0x1805c45d4`: `SetAppAsDefault Completed Successfully`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall _SetAppAsDefault__QIApplicationAssociationRegistration__CApplicationAssociationRegistration__UEAAJPEBG0W4ASSOCIATIONTYPE___Z(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        enum ASSOCIATIONTYPE a4)
{
  char HasCapability; // al
  CApplicationAssociationRegistration *v9; // rcx
  const char *v10; // r9
  int v12; // eax
  int PublisherFromCurrentProcess; // ebx
  enum ASSOCIATIONTYPE v14; // r8d
  unsigned __int16 **v15; // rdx
  int CurrentDefault; // eax
  unsigned __int16 **v17; // rcx
  unsigned __int16 **v18; // rdx
  unsigned __int16 **v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  const unsigned __int16 *v23; // rbx
  const unsigned __int16 *v24; // rdi
  const unsigned __int16 *v25; // rsi
  const unsigned __int16 *v26; // r14
  int bIgnoreCase; // [rsp+20h] [rbp-1B8h]
  int bIgnoreCasea; // [rsp+20h] [rbp-1B8h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-1B8h]
  _BYTE v30[8]; // [rsp+30h] [rbp-1A8h] BYREF
  LPCWCH lpString2; // [rsp+38h] [rbp-1A0h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-198h] BYREF
  LPCWCH v33; // [rsp+48h] [rbp-190h] BYREF
  unsigned __int16 *v34[2]; // [rsp+50h] [rbp-188h] BYREF
  _QWORD v35[42]; // [rsp+60h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  try
  {
    LODWORD(v34[0]) = 5;
    HasCapability = winrt::Windows::Internal::ApplicationDefaults::AppDefaultHelpers::HasCapability((const enum winrt::Windows::Internal::ApplicationDefaults::AppDefaultsCapability *)v34);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2E2,
                           (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\fileassoc.cpp",
                           v10);
  }
  if ( !HasCapability )
    return 2147500033LL;
  if ( (unsigned int)(a4 - 2) <= 1 )
  {
    v12 = CApplicationAssociationRegistration::_SetAppAsDefault(v9, a2, a3, a4);
    PublisherFromCurrentProcess = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E6,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\fileassoc.cpp",
        (const char *)(unsigned int)v12,
        bIgnoreCase);
      return (unsigned int)PublisherFromCurrentProcess;
    }
    return 0;
  }
  if ( IsBrowserExtension(a3) || CompareStringOrdinal(a3, -1, L".pdf", -1, 1) == 2 )
    return 0;
  wil::ActivityBase<DefaultAssocLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DefaultAssocLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v35);
  v35[0] = &DefaultAssocTelemetry::SetAppAsDefault::`vftable';
  DefaultAssocTelemetry::SetAppAsDefault::StartActivity((DefaultAssocTelemetry::SetAppAsDefault *)v35, a2, a3, 0);
  LogAppDefaultMessage<_lambda_21d8748d23f009167a853bcb59d64c85_>(
    v30,
    L"SetAppAsDefault-Info: Association=%ls, ProgId=%ls",
    a3,
    a2);
  v34[0] = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(v34);
  v14 = IsFileExtension(a3) == 0;
  CurrentDefault = CApplicationAssociationRegistration::QueryCurrentDefault(
                     (CApplicationAssociationRegistration *)(a1 - 8),
                     a3,
                     v14,
                     AL_EFFECTIVE,
                     v15);
  PublisherFromCurrentProcess = CurrentDefault;
  if ( CurrentDefault >= 0 )
  {
    LogAppDefaultMessage<_lambda_21d8748d23f009167a853bcb59d64c85_>(
      v30,
      L"SetAppAsDefault-Info: PrevProgId=%ls",
      v34[0]);
    pv = 0;
    v17 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
    PublisherFromCurrentProcess = GetPublisherFromCurrentProcess(v17);
    if ( PublisherFromCurrentProcess >= 0 )
    {
      lpString2 = 0;
      v18 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&lpString2);
      PublisherFromCurrentProcess = GetPublisherFromProgId(v34[0], v18);
      if ( PublisherFromCurrentProcess >= 0 )
      {
        v33 = 0;
        v19 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v33);
        PublisherFromCurrentProcess = GetPublisherFromProgId(a2, v19);
        if ( PublisherFromCurrentProcess >= 0 )
        {
          LogAppDefaultMessage<_lambda_21d8748d23f009167a853bcb59d64c85_>(
            v30,
            L"SetAppAsDefault-Info: CallingAppPublisher=%ls, DefaultAppPublisher=%ls, progIdToSetPublisher=%ls",
            pv,
            lpString2,
            v33);
          if ( CompareStringOrdinal((LPCWCH)pv, -1, lpString2, -1, 1) != 2
            || CompareStringOrdinal(lpString2, -1, v33, -1, 1) != 2 )
          {
            v23 = v33;
            v24 = lpString2;
            v25 = (const unsigned __int16 *)pv;
            v26 = v34[0];
            wil::ActivityBase<OpenWithLogging,1,70368744177664,5,2048,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(v35);
            DefaultAssocTelemetry::SetAppAsDefault::Stop(
              (DefaultAssocTelemetry::SetAppAsDefault *)v35,
              v26,
              v25,
              v24,
              v23);
            if ( v33 )
              CoTaskMemFree((LPVOID)v33);
            if ( lpString2 )
              CoTaskMemFree((LPVOID)lpString2);
            if ( pv )
              CoTaskMemFree(pv);
            if ( v34[0] )
              CoTaskMemFree(v34[0]);
            PublisherFromCurrentProcess = -2147024891;
            goto LABEL_51;
          }
          v20 = SetDefaultAssociation(a3);
          PublisherFromCurrentProcess = v20;
          if ( v20 >= 0 )
          {
            v20 = ClearPromptCountForApp(a3, a2);
            PublisherFromCurrentProcess = v20;
            if ( v20 >= 0 )
            {
              if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x20000000000LL) != 0 )
                McTemplateU0z_EventWriteTransfer(v22, AppDefaults_Info, L"SetAppAsDefault Completed Successfully");
              wil::ActivityBase<DefaultAssocLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v35);
              if ( v33 )
                CoTaskMemFree((LPVOID)v33);
              if ( lpString2 )
                CoTaskMemFree((LPVOID)lpString2);
              if ( pv )
                CoTaskMemFree(pv);
              if ( v34[0] )
                CoTaskMemFree(v34[0]);
              DefaultAssocTelemetry::SetAppAsDefault::~SetAppAsDefault((DefaultAssocTelemetry::SetAppAsDefault *)v35);
              return 0;
            }
            v21 = 788;
          }
          else
          {
            v21 = 786;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v21,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\fileassoc.cpp",
            (const char *)(unsigned int)v20,
            bIgnoreCaseb);
        }
        if ( v33 )
          CoTaskMemFree((LPVOID)v33);
      }
      if ( lpString2 )
        CoTaskMemFree((LPVOID)lpString2);
    }
    if ( pv )
      CoTaskMemFree(pv);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F8,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\fileassoc.cpp",
      (const char *)(unsigned int)CurrentDefault,
      bIgnoreCasea);
  }
  if ( v34[0] )
    CoTaskMemFree(v34[0]);
LABEL_51:
  DefaultAssocTelemetry::SetAppAsDefault::~SetAppAsDefault((DefaultAssocTelemetry::SetAppAsDefault *)v35);
  return (unsigned int)PublisherFromCurrentProcess;
}

```

## disassembly

```asm
0x1805c42c0  mov     [rsp+arg_0], rbx
0x1805c42c5  mov     [rsp+arg_18], rsi
0x1805c42ca  push    rdi
0x1805c42cb  push    r12
0x1805c42cd  push    r14
0x1805c42cf  sub     rsp, 1C0h
0x1805c42d6  mov     rax, cs:__security_cookie
0x1805c42dd  xor     rax, rsp
0x1805c42e0  mov     [rsp+1D8h+var_28], rax
0x1805c42e8  mov     ebx, r9d
0x1805c42eb  mov     rdi, r8
0x1805c42ee  mov     rsi, rdx
0x1805c42f1  mov     r14, rcx
0x1805c42f4  mov     dword ptr [rsp+1D8h+var_188], 5
0x1805c42fc  lea     rcx, [rsp+1D8h+var_188]; enum winrt::Windows::Internal::ApplicationDefaults::AppDefaultsCapability *
0x1805c4301  call    ?HasCapability@AppDefaultHelpers@ApplicationDefaults@Internal@Windows@winrt@@SA@AEBW4AppDefaultsCapability@2345@@Z; winrt::Windows::Internal::ApplicationDefaults::AppDefaultHelpers::HasCapability(winrt::Windows::Internal::ApplicationDefaults::AppDefaultsCapability const &)
0x1805c4306  test    al, al
0x1805c4308  jnz     short loc_1805C4314
0x1805c430a  mov     eax, 80004001h
0x1805c430f  jmp     loc_1805C46D9
0x1805c4314  lea     eax, [rbx-2]
0x1805c4317  cmp     eax, 1
0x1805c431a  ja      short loc_1805C4357
0x1805c431c  mov     r9d, ebx; enum ASSOCIATIONTYPE
0x1805c431f  mov     r8, rdi; unsigned __int16 *
0x1805c4322  mov     rdx, rsi; unsigned __int16 *
0x1805c4325  call    ?_SetAppAsDefault@CApplicationAssociationRegistration@@AEAAJPEBG0W4ASSOCIATIONTYPE@@@Z; CApplicationAssociationRegistration::_SetAppAsDefault(ushort const *,ushort const *,ASSOCIATIONTYPE)
0x1805c432a  mov     ebx, eax
0x1805c432c  test    eax, eax
0x1805c432e  jns     loc_1805C4640
0x1805c4334  mov     rcx, [rsp+1D8h]; this
0x1805c433c  mov     r9d, eax; char *
0x1805c433f  lea     r8, aOnecoreuapShel_77; "onecoreuap\\shell\\windows.storage\\sha"...
0x1805c4346  mov     edx, 2E6h; void *
0x1805c434b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1805c4350  mov     eax, ebx
0x1805c4352  jmp     loc_1805C46D9
0x1805c4357  mov     rcx, rdi; lpString1
0x1805c435a  call    ?IsBrowserExtension@@YA_NPEBG@Z; IsBrowserExtension(ushort const *)
0x1805c435f  test    al, al
0x1805c4361  jnz     loc_1805C4640
0x1805c4367  mov     [rsp+1D8h+bIgnoreCase], 1; bIgnoreCase
0x1805c436f  or      r12d, 0FFFFFFFFh
0x1805c4373  mov     r9d, r12d; cchCount2
0x1805c4376  lea     r8, aPdf; ".pdf"
0x1805c437d  mov     edx, r12d; cchCount1
0x1805c4380  mov     rcx, rdi; lpString1
0x1805c4383  call    cs:__imp_CompareStringOrdinal
0x1805c4389  cmp     eax, 2
0x1805c438c  jz      loc_1805C4640
0x1805c4392  lea     rdx, aSetappasdefaul_3; "SetAppAsDefault"
0x1805c4399  lea     rcx, [rsp+1D8h+var_178]; struct wil::details::IFailureCallback *
0x1805c439e  call    ??0?$ActivityBase@VDefaultAssocLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DefaultAssocLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DefaultAssocLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1805c43a3  lea     rax, ??_7SetAppAsDefault@DefaultAssocTelemetry@@6B@; const DefaultAssocTelemetry::SetAppAsDefault::`vftable'
0x1805c43aa  mov     [rsp+1D8h+var_178], rax
0x1805c43af  xor     r9d, r9d; bool
0x1805c43b2  mov     r8, rdi; unsigned __int16 *
0x1805c43b5  mov     rdx, rsi; unsigned __int16 *
0x1805c43b8  lea     rcx, [rsp+1D8h+var_178]; this
0x1805c43bd  call    ?StartActivity@SetAppAsDefault@DefaultAssocTelemetry@@QEAAXPEBG0_N@Z; DefaultAssocTelemetry::SetAppAsDefault::StartActivity(ushort const *,ushort const *,bool)
0x1805c43c2  nop
0x1805c43c3  mov     r9, rsi
0x1805c43c6  mov     r8, rdi
0x1805c43c9  lea     rdx, aSetappasdefaul_1; "SetAppAsDefault-Info: Association=%ls, "...
0x1805c43d0  lea     rcx, [rsp+1D8h+var_1A8]
0x1805c43d5  call    ??$LogAppDefaultMessage@V_lambda_21d8748d23f009167a853bcb59d64c85_@@@@YAJAEBV_lambda_21d8748d23f009167a853bcb59d64c85_@@PEBGZZ; LogAppDefaultMessage<_lambda_21d8748d23f009167a853bcb59d64c85_>(_lambda_21d8748d23f009167a853bcb59d64c85_ const &,ushort const *,...)
0x1805c43da  mov     [rsp+1D8h+var_188], 0
0x1805c43e3  lea     rcx, [rsp+1D8h+var_188]
0x1805c43e8  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1805c43ed  mov     rdx, rax
0x1805c43f0  mov     rcx, rdi; unsigned __int16 *
0x1805c43f3  call    ?IsFileExtension@@YAHPEBG@Z; IsFileExtension(ushort const *)
0x1805c43f8  xor     r8d, r8d
0x1805c43fb  test    eax, eax
0x1805c43fd  setz    r8b; enum ASSOCIATIONTYPE
0x1805c4401  lea     rcx, [r14-8]; this
0x1805c4405  mov     qword ptr [rsp+1D8h+bIgnoreCase], rdx; int
0x1805c440a  lea     r9d, [r12+2]; enum ASSOCIATIONLEVEL
0x1805c440f  mov     rdx, rdi; unsigned __int16 *
0x1805c4412  call    ?QueryCurrentDefault@CApplicationAssociationRegistration@@UEAAJPEBGW4ASSOCIATIONTYPE@@W4ASSOCIATIONLEVEL@@PEAPEAG@Z; CApplicationAssociationRegistration::QueryCurrentDefault(ushort const *,ASSOCIATIONTYPE,ASSOCIATIONLEVEL,ushort * *)
0x1805c4417  mov     ebx, eax
0x1805c4419  test    eax, eax
0x1805c441b  jns     short loc_1805C443B
0x1805c441d  mov     rcx, [rsp+1D8h]; this
0x1805c4425  mov     r9d, eax; char *
0x1805c4428  lea     r8, aOnecoreuapShel_77; "onecoreuap\\shell\\windows.storage\\sha"...
0x1805c442f  mov     edx, 2F8h; void *
0x1805c4434  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1805c4439  jmp     short loc_1805C4483
0x1805c443b  mov     r8, [rsp+1D8h+var_188]
0x1805c4440  lea     rdx, aSetappasdefaul; "SetAppAsDefault-Info: PrevProgId=%ls"
0x1805c4447  lea     rcx, [rsp+1D8h+var_1A8]
0x1805c444c  call    ??$LogAppDefaultMessage@V_lambda_21d8748d23f009167a853bcb59d64c85_@@@@YAJAEBV_lambda_21d8748d23f009167a853bcb59d64c85_@@PEBGZZ; LogAppDefaultMessage<_lambda_21d8748d23f009167a853bcb59d64c85_>(_lambda_21d8748d23f009167a853bcb59d64c85_ const &,ushort const *,...)
0x1805c4451  mov     [rsp+1D8h+pv], 0
0x1805c445a  lea     rcx, [rsp+1D8h+pv]
0x1805c445f  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1805c4464  mov     rcx, rax; unsigned __int16 **
0x1805c4467  call    ?GetPublisherFromCurrentProcess@@YAJPEAPEAG@Z; GetPublisherFromCurrentProcess(ushort * *)
0x1805c446c  mov     ebx, eax
0x1805c446e  test    eax, eax
0x1805c4470  jns     short loc_1805C449C
0x1805c4472  mov     rcx, [rsp+1D8h+pv]; pv
0x1805c4477  test    rcx, rcx
0x1805c447a  jz      short loc_1805C4483
0x1805c447c  call    cs:__imp_CoTaskMemFree
0x1805c4482  nop
0x1805c4483  mov     rcx, [rsp+1D8h+var_188]; pv
0x1805c4488  test    rcx, rcx
0x1805c448b  jz      loc_1805C46C6
0x1805c4491  call    cs:__imp_CoTaskMemFree
0x1805c4497  jmp     loc_1805C46C6
0x1805c449c  mov     [rsp+1D8h+lpString2], 0
0x1805c44a5  lea     rcx, [rsp+1D8h+lpString2]
0x1805c44aa  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1805c44af  mov     rdx, rax; unsigned __int16 **
0x1805c44b2  mov     rcx, [rsp+1D8h+var_188]; unsigned __int16 *
0x1805c44b7  call    ?GetPublisherFromProgId@@YAJPEBGPEAPEAG@Z; GetPublisherFromProgId(ushort const *,ushort * *)
0x1805c44bc  mov     ebx, eax
0x1805c44be  test    eax, eax
0x1805c44c0  jns     short loc_1805C44D4
0x1805c44c2  mov     rcx, [rsp+1D8h+lpString2]; pv
0x1805c44c7  test    rcx, rcx
0x1805c44ca  jz      short loc_1805C4472
0x1805c44cc  call    cs:__imp_CoTaskMemFree
0x1805c44d2  jmp     short loc_1805C4472
0x1805c44d4  mov     [rsp+1D8h+var_190], 0
0x1805c44dd  lea     rcx, [rsp+1D8h+var_190]
0x1805c44e2  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1805c44e7  mov     rdx, rax; unsigned __int16 **
0x1805c44ea  mov     rcx, rsi; unsigned __int16 *
0x1805c44ed  call    ?GetPublisherFromProgId@@YAJPEBGPEAPEAG@Z; GetPublisherFromProgId(ushort const *,ushort * *)
0x1805c44f2  mov     ebx, eax
0x1805c44f4  test    eax, eax
0x1805c44f6  jns     short loc_1805C450A
0x1805c44f8  mov     rcx, [rsp+1D8h+var_190]; pv
0x1805c44fd  test    rcx, rcx
0x1805c4500  jz      short loc_1805C44C2
0x1805c4502  call    cs:__imp_CoTaskMemFree
0x1805c4508  jmp     short loc_1805C44C2
0x1805c450a  mov     rax, [rsp+1D8h+var_190]
0x1805c450f  mov     qword ptr [rsp+1D8h+bIgnoreCase], rax
0x1805c4514  mov     r9, [rsp+1D8h+lpString2]
0x1805c4519  mov     r8, [rsp+1D8h+pv]
0x1805c451e  lea     rdx, aSetappasdefaul_0; "SetAppAsDefault-Info: CallingAppPublish"...
0x1805c4525  lea     rcx, [rsp+1D8h+var_1A8]
0x1805c452a  call    ??$LogAppDefaultMessage@V_lambda_21d8748d23f009167a853bcb59d64c85_@@@@YAJAEBV_lambda_21d8748d23f009167a853bcb59d64c85_@@PEBGZZ; LogAppDefaultMessage<_lambda_21d8748d23f009167a853bcb59d64c85_>(_lambda_21d8748d23f009167a853bcb59d64c85_ const &,ushort const *,...)
0x1805c452f  mov     [rsp+1D8h+bIgnoreCase], 1; bIgnoreCase
0x1805c4537  mov     r9d, r12d; cchCount2
0x1805c453a  mov     r8, [rsp+1D8h+lpString2]; lpString2
0x1805c453f  mov     edx, r12d; cchCount1
0x1805c4542  mov     rcx, [rsp+1D8h+pv]; lpString1
0x1805c4547  call    cs:__imp_CompareStringOrdinal
0x1805c454d  cmp     eax, 2
0x1805c4550  jnz     loc_1805C4647
0x1805c4556  mov     [rsp+1D8h+bIgnoreCase], 1; int
0x1805c455e  mov     r9d, r12d; cchCount2
0x1805c4561  mov     r8, [rsp+1D8h+var_190]; lpString2
0x1805c4566  mov     edx, r12d; cchCount1
0x1805c4569  mov     rcx, [rsp+1D8h+lpString2]; lpString1
0x1805c456e  call    cs:__imp_CompareStringOrdinal
0x1805c4574  cmp     eax, 2
0x1805c4577  jnz     loc_1805C4647
0x1805c457d  lea     r9d, [rax+3Eh]
0x1805c4581  mov     rdx, rsi
0x1805c4584  mov     rcx, rdi; unsigned __int16 *
0x1805c4587  call    SetDefaultAssociation
0x1805c458c  mov     ebx, eax
0x1805c458e  test    eax, eax
0x1805c4590  jns     short loc_1805C45B3
0x1805c4592  mov     edx, 312h; void *
0x1805c4597  lea     r8, aOnecoreuapShel_77; "onecoreuap\\shell\\windows.storage\\sha"...
0x1805c459e  mov     r9d, eax; char *
0x1805c45a1  mov     rcx, [rsp+1D8h]; this
0x1805c45a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1805c45ae  jmp     loc_1805C44F8
0x1805c45b3  mov     rdx, rsi; unsigned __int16 *
0x1805c45b6  mov     rcx, rdi; unsigned __int16 *
0x1805c45b9  call    ?ClearPromptCountForApp@@YAJPEBG0@Z; ClearPromptCountForApp(ushort const *,ushort const *)
0x1805c45be  mov     ebx, eax
0x1805c45c0  test    eax, eax
0x1805c45c2  jns     short loc_1805C45CB
0x1805c45c4  mov     edx, 314h
0x1805c45c9  jmp     short loc_1805C4597
0x1805c45cb  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+5, 2
0x1805c45d2  jz      short loc_1805C45E7
0x1805c45d4  lea     r8, aSetappasdefaul_2; "SetAppAsDefault Completed Successfully"
0x1805c45db  lea     rdx, AppDefaults_Info
0x1805c45e2  call    McTemplateU0z_EventWriteTransfer
0x1805c45e7  lea     rcx, [rsp+1D8h+var_178]
0x1805c45ec  call    ?Stop@?$ActivityBase@VDefaultAssocLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DefaultAssocLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1805c45f1  nop
0x1805c45f2  mov     rcx, [rsp+1D8h+var_190]; pv
0x1805c45f7  test    rcx, rcx
0x1805c45fa  jz      short loc_1805C4603
0x1805c45fc  call    cs:__imp_CoTaskMemFree
0x1805c4602  nop
0x1805c4603  mov     rcx, [rsp+1D8h+lpString2]; pv
0x1805c4608  test    rcx, rcx
0x1805c460b  jz      short loc_1805C4614
0x1805c460d  call    cs:__imp_CoTaskMemFree
0x1805c4613  nop
0x1805c4614  mov     rcx, [rsp+1D8h+pv]; pv
0x1805c4619  test    rcx, rcx
0x1805c461c  jz      short loc_1805C4625
0x1805c461e  call    cs:__imp_CoTaskMemFree
0x1805c4624  nop
0x1805c4625  mov     rcx, [rsp+1D8h+var_188]; pv
0x1805c462a  test    rcx, rcx
0x1805c462d  jz      short loc_1805C4636
0x1805c462f  call    cs:__imp_CoTaskMemFree
0x1805c4635  nop
0x1805c4636  lea     rcx, [rsp+1D8h+var_178]; this
0x1805c463b  call    ??1SetAppAsDefault@DefaultAssocTelemetry@@QEAA@XZ; DefaultAssocTelemetry::SetAppAsDefault::~SetAppAsDefault(void)
0x1805c4640  xor     eax, eax
0x1805c4642  jmp     loc_1805C46D9
0x1805c4647  mov     rbx, [rsp+1D8h+var_190]
0x1805c464c  mov     rdi, [rsp+1D8h+lpString2]
0x1805c4651  mov     rsi, [rsp+1D8h+pv]
0x1805c4656  mov     r14, [rsp+1D8h+var_188]
0x1805c465b  lea     rcx, [rsp+1D8h+var_178]
0x1805c4660  call    ?SetStopResult@?$ActivityBase@VOpenWithLogging@@$00$0EAAAAAAAAAAA@$04$0IAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z; wil::ActivityBase<OpenWithLogging,1,70368744177664,5,2048,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1805c4665  mov     qword ptr [rsp+1D8h+bIgnoreCase], rbx; unsigned __int16 *
0x1805c466a  mov     r9, rdi; unsigned __int16 *
0x1805c466d  mov     r8, rsi; unsigned __int16 *
0x1805c4670  mov     rdx, r14; unsigned __int16 *
0x1805c4673  lea     rcx, [rsp+1D8h+var_178]; this
0x1805c4678  call    ?Stop@SetAppAsDefault@DefaultAssocTelemetry@@QEAAXPEBG000@Z; DefaultAssocTelemetry::SetAppAsDefault::Stop(ushort const *,ushort const *,ushort const *,ushort const *)
0x1805c467d  nop
0x1805c467e  mov     rcx, [rsp+1D8h+var_190]; pv
0x1805c4683  test    rcx, rcx
0x1805c4686  jz      short loc_1805C468F
0x1805c4688  call    cs:__imp_CoTaskMemFree
0x1805c468e  nop
0x1805c468f  mov     rcx, [rsp+1D8h+lpString2]; pv
0x1805c4694  test    rcx, rcx
0x1805c4697  jz      short loc_1805C46A0
0x1805c4699  call    cs:__imp_CoTaskMemFree
0x1805c469f  nop
0x1805c46a0  mov     rcx, [rsp+1D8h+pv]; pv
0x1805c46a5  test    rcx, rcx
0x1805c46a8  jz      short loc_1805C46B1
0x1805c46aa  call    cs:__imp_CoTaskMemFree
0x1805c46b0  nop
0x1805c46b1  mov     rcx, [rsp+1D8h+var_188]; pv
0x1805c46b6  test    rcx, rcx
0x1805c46b9  jz      short loc_1805C46C1
0x1805c46bb  call    cs:__imp_CoTaskMemFree
0x1805c46c1  mov     ebx, 80070005h
0x1805c46c6  lea     rcx, [rsp+1D8h+var_178]; this
0x1805c46cb  call    ??1SetAppAsDefault@DefaultAssocTelemetry@@QEAA@XZ; DefaultAssocTelemetry::SetAppAsDefault::~SetAppAsDefault(void)
0x1805c46d0  jmp     loc_1805C4350
0x1805c46d5  mov     eax, dword ptr [rsp+1D8h+var_188]
0x1805c46d9  mov     rcx, [rsp+1D8h+var_28]
0x1805c46e1  xor     rcx, rsp; StackCookie
0x1805c46e4  call    __security_check_cookie
0x1805c46e9  lea     r11, [rsp+1D8h+var_18]
0x1805c46f1  mov     rbx, [r11+20h]
0x1805c46f5  mov     rsi, [r11+38h]
0x1805c46f9  mov     rsp, r11
0x1805c46fc  pop     r14
0x1805c46fe  pop     r12
0x1805c4700  pop     rdi
0x1805c4701  retn
```
