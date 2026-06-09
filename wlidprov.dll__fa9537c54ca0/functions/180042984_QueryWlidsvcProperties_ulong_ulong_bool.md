# QueryWlidsvcProperties(ulong &,ulong &,bool &)

- ea: `0x180042984`
- end: `0x180042c0a`
- name: `?QueryWlidsvcProperties@@YAJAEAK0AEA_N@Z`
- size: `646`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800433c4`

## callees

- `0x180016758`
- `0x18001a0d0`
- `0x18001bf94`
- `0x180021e84`
- `0x180041988`
- `0x180042538`
- `0x180042558`
- `0x18004257c`
- `0x180042984`
- `0x180042f40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042ab9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042ad7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042ad7`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180042a1a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180042a1a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800429dd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800429dd`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180042a8d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180042b27`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180042a8d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180042b27`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180042a69`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180042a69`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180042b71`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180042b71`

## string_xrefs

- `0x1800429d4`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall QueryWlidsvcProperties(unsigned int *a1, unsigned int *a2, bool *a3)
{
  SC_HANDLE v6; // rax
  const char *v7; // r9
  unsigned int LastError; // ebx
  SC_HANDLE v9; // rax
  const char *v10; // r9
  SC_HANDLE v11; // rbx
  __int64 v12; // rdx
  struct _QUERY_SERVICE_CONFIGW *v13; // rax
  struct _QUERY_SERVICE_CONFIGW *v14; // rdi
  __int64 v15; // rdx
  const char *v16; // r9
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-E0h] BYREF
  SC_HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  struct _QUERY_SERVICE_CONFIGW *v21; // [rsp+38h] [rbp-C8h] BYREF
  SC_HANDLE v22; // [rsp+40h] [rbp-C0h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v24[336]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  *a1 = -1;
  *a2 = -1;
  *a3 = 1;
  MSAClientTraceTelemetry::QueryWlidsvcProperties::QueryWlidsvcProperties((MSAClientTraceTelemetry::QueryWlidsvcProperties *)v24);
  v6 = OpenSCManagerW(0, L"ServicesActive", 4u);
  v22 = v6;
  if ( v6 )
  {
    v9 = OpenServiceW(v6, L"wlidsvc", 5u);
    v19 = v9;
    v11 = v9;
    if ( !v9 )
    {
      v12 = 107;
LABEL_5:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v12,
                    (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
                    v10);
LABEL_6:
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v19);
      goto LABEL_24;
    }
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( !QueryServiceStatus(v9, &ServiceStatus) )
    {
      v12 = 112;
      goto LABEL_5;
    }
    pcbBytesNeeded = 0;
    if ( QueryServiceConfigW(v11, 0, 0, &pcbBytesNeeded) )
    {
      LastError = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
        (const char *)0x8000FFFFLL,
        pcbBytesNeeded);
      goto LABEL_6;
    }
    if ( GetLastError() != 122 )
    {
      v12 = 123;
      goto LABEL_5;
    }
    v13 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0x40u, pcbBytesNeeded);
    v21 = v13;
    v14 = v13;
    if ( v13 )
    {
      if ( !QueryServiceConfigW(v11, v13, pcbBytesNeeded, &pcbBytesNeeded) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x86,
                      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
                      v16);
        goto LABEL_16;
      }
      v20 = -1;
      if ( !(unsigned __int8)IsPolicyManager_GetPolicyIntPresent()
        || (LastError = PolicyManager_GetPolicyInt(L"Accounts", L"AllowMicrosoftAccountSignInAssistant", &v20),
            (int)(LastError + 0x80000000) < 0)
        || LastError == -2147024769 )
      {
        *a3 = v20 != 0;
        *a2 = v14->dwStartType;
        *a1 = ServiceStatus.dwCurrentState;
        wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v24);
        wil::details::unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>(&v21);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v19);
        LastError = 0;
        goto LABEL_24;
      }
      v15 = 142;
    }
    else
    {
      LastError = -2147024882;
      v15 = 127;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
      (const char *)LastError,
      pcbBytesNeeded);
LABEL_16:
    wil::details::unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>(&v21);
    goto LABEL_6;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x64,
                (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\rpcclient\\wlidclient.cpp",
                v7);
LABEL_24:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v22);
  MSAClientTraceTelemetry::QueryWlidsvcProperties::~QueryWlidsvcProperties((MSAClientTraceTelemetry::QueryWlidsvcProperties *)v24);
  return LastError;
}

```

## disassembly

```asm
0x180042984  mov     [rsp-8+arg_18], rbx
0x180042989  push    rbp
0x18004298a  push    rsi
0x18004298b  push    rdi
0x18004298c  push    r14
0x18004298e  push    r15
0x180042990  lea     rbp, [rsp-0D0h]
0x180042998  sub     rsp, 1D0h
0x18004299f  mov     rax, cs:__security_cookie
0x1800429a6  xor     rax, rsp
0x1800429a9  mov     [rbp+0F0h+var_30], rax
0x1800429b0  or      eax, 0FFFFFFFFh
0x1800429b3  mov     rsi, rcx
0x1800429b6  mov     [rcx], eax
0x1800429b8  mov     r15, r8
0x1800429bb  mov     [rdx], eax
0x1800429bd  lea     rcx, [rsp+1F0h+var_180]; this
0x1800429c2  mov     byte ptr [r8], 1
0x1800429c6  mov     r14, rdx
0x1800429c9  call    ??$?0$$V@QueryWlidsvcProperties@MSAClientTraceTelemetry@@AEAA@U?$integral_constant@D$0A@@wistd@@@Z; MSAClientTraceTelemetry::QueryWlidsvcProperties::QueryWlidsvcProperties(wistd::integral_constant<char,0>)
0x1800429ce  mov     r8d, 4; dwDesiredAccess
0x1800429d4  lea     rdx, DatabaseName; "ServicesActive"
0x1800429db  xor     ecx, ecx; lpMachineName
0x1800429dd  call    cs:__imp_OpenSCManagerW
0x1800429e3  mov     [rsp+1F0h+var_1B0], rax
0x1800429e8  test    rax, rax
0x1800429eb  jnz     short loc_180042A0A
0x1800429ed  mov     rcx, [rbp+0F8h]; this
0x1800429f4  lea     r8, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800429fb  lea     edx, [rax+64h]; void *
0x1800429fe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180042a03  mov     ebx, eax
0x180042a05  jmp     loc_180042BCE
0x180042a0a  mov     r8d, 5; dwDesiredAccess
0x180042a10  lea     rdx, ServiceName; "wlidsvc"
0x180042a17  mov     rcx, rax; hSCManager
0x180042a1a  call    cs:__imp_OpenServiceW
0x180042a20  mov     [rsp+1F0h+var_1C8], rax
0x180042a25  mov     rbx, rax
0x180042a28  test    rax, rax
0x180042a2b  jnz     short loc_180042A54
0x180042a2d  lea     edx, [rax+6Bh]; void *
0x180042a30  mov     rcx, [rbp+0F8h]; this
0x180042a37  lea     r8, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180042a3e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180042a43  mov     ebx, eax
0x180042a45  lea     rcx, [rsp+1F0h+var_1C8]
0x180042a4a  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180042a4f  jmp     loc_180042BCE
0x180042a54  xorps   xmm0, xmm0
0x180042a57  lea     rdx, [rsp+1F0h+ServiceStatus]; lpServiceStatus
0x180042a5c  movups  xmmword ptr [rsp+1F0h+ServiceStatus.dwServiceType], xmm0
0x180042a61  mov     rcx, rbx; hService
0x180042a64  movups  xmmword ptr [rsp+1F0h+ServiceStatus.dwWin32ExitCode], xmm0
0x180042a69  call    cs:__imp_QueryServiceStatus
0x180042a6f  test    eax, eax
0x180042a71  jnz     short loc_180042A78
0x180042a73  lea     edx, [rax+70h]
0x180042a76  jmp     short loc_180042A30
0x180042a78  lea     r9, [rsp+1F0h+pcbBytesNeeded]; pcbBytesNeeded
0x180042a7d  mov     [rsp+1F0h+pcbBytesNeeded], 0; int
0x180042a85  xor     r8d, r8d; cbBufSize
0x180042a88  xor     edx, edx; lpServiceConfig
0x180042a8a  mov     rcx, rbx; hService
0x180042a8d  call    cs:__imp_QueryServiceConfigW
0x180042a93  test    eax, eax
0x180042a95  jz      short loc_180042AB9
0x180042a97  mov     rcx, [rbp+0F8h]; this
0x180042a9e  lea     r8, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180042aa5  mov     ebx, 8000FFFFh
0x180042aaa  mov     edx, 7Ah ; 'z'; void *
0x180042aaf  mov     r9d, ebx; char *
0x180042ab2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042ab7  jmp     short loc_180042A45
0x180042ab9  call    cs:__imp_GetLastError
0x180042abf  cmp     eax, 7Ah ; 'z'
0x180042ac2  jz      short loc_180042ACE
0x180042ac4  mov     edx, 7Bh ; '{'
0x180042ac9  jmp     loc_180042A30
0x180042ace  mov     edx, [rsp+1F0h+pcbBytesNeeded]; uBytes
0x180042ad2  mov     ecx, 40h ; '@'; uFlags
0x180042ad7  call    cs:__imp_LocalAlloc
0x180042add  mov     [rsp+1F0h+var_1B8], rax
0x180042ae2  mov     rdi, rax
0x180042ae5  test    rax, rax
0x180042ae8  jnz     short loc_180042B17
0x180042aea  mov     ebx, 8007000Eh
0x180042aef  lea     edx, [rax+7Fh]; void *
0x180042af2  mov     rcx, [rbp+0F8h]; this
0x180042af9  lea     r8, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180042b00  mov     r9d, ebx; char *
0x180042b03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042b08  lea     rcx, [rsp+1F0h+var_1B8]
0x180042b0d  call    ??1?$unique_storage@U?$resource_policy@PEAU_QUERY_SERVICE_CONFIGW@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>(void)
0x180042b12  jmp     loc_180042A45
0x180042b17  mov     r8d, [rsp+1F0h+pcbBytesNeeded]; cbBufSize
0x180042b1c  lea     r9, [rsp+1F0h+pcbBytesNeeded]; pcbBytesNeeded
0x180042b21  mov     rdx, rdi; lpServiceConfig
0x180042b24  mov     rcx, rbx; hService
0x180042b27  call    cs:__imp_QueryServiceConfigW
0x180042b2d  test    eax, eax
0x180042b2f  jnz     short loc_180042B4D
0x180042b31  mov     rcx, [rbp+0F8h]; this
0x180042b38  lea     r8, aOnecoreuapDsEx_14; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180042b3f  mov     edx, 86h; void *
0x180042b44  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180042b49  mov     ebx, eax
0x180042b4b  jmp     short loc_180042B08
0x180042b4d  mov     [rsp+1F0h+var_1C0], 0FFFFFFFFh
0x180042b55  call    IsPolicyManager_GetPolicyIntPresent
0x180042b5a  test    al, al
0x180042b5c  jz      short loc_180042B97
0x180042b5e  lea     r8, [rsp+1F0h+var_1C0]
0x180042b63  lea     rdx, aAllowmicrosoft; "AllowMicrosoftAccountSignInAssistant"
0x180042b6a  lea     rcx, aAccounts; "Accounts"
0x180042b71  call    cs:__imp_PolicyManager_GetPolicyInt
0x180042b77  mov     ebx, eax
0x180042b79  mov     eax, 80000000h
0x180042b7e  lea     ecx, [rbx+rax]
0x180042b81  test    eax, ecx
0x180042b83  jnz     short loc_180042B97
0x180042b85  cmp     ebx, 8007007Fh
0x180042b8b  jz      short loc_180042B97
0x180042b8d  mov     edx, 8Eh
0x180042b92  jmp     loc_180042AF2
0x180042b97  cmp     [rsp+1F0h+var_1C0], 0
0x180042b9c  lea     rcx, [rsp+1F0h+var_180]
0x180042ba1  setnz   al
0x180042ba4  mov     [r15], al
0x180042ba7  mov     eax, [rdi+4]
0x180042baa  mov     [r14], eax
0x180042bad  mov     eax, [rsp+1F0h+ServiceStatus.dwCurrentState]
0x180042bb1  mov     [rsi], eax
0x180042bb3  call    ?Stop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180042bb8  lea     rcx, [rsp+1F0h+var_1B8]
0x180042bbd  call    ??1?$unique_storage@U?$resource_policy@PEAU_QUERY_SERVICE_CONFIGW@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>(void)
0x180042bc2  lea     rcx, [rsp+1F0h+var_1C8]
0x180042bc7  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180042bcc  xor     ebx, ebx
0x180042bce  lea     rcx, [rsp+1F0h+var_1B0]
0x180042bd3  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180042bd8  lea     rcx, [rsp+1F0h+var_180]; this
0x180042bdd  call    ??1QueryWlidsvcProperties@MSAClientTraceTelemetry@@QEAA@XZ; MSAClientTraceTelemetry::QueryWlidsvcProperties::~QueryWlidsvcProperties(void)
0x180042be2  mov     eax, ebx
0x180042be4  mov     rcx, [rbp+0F0h+var_30]
0x180042beb  xor     rcx, rsp; StackCookie
0x180042bee  call    __security_check_cookie
0x180042bf3  mov     rbx, [rsp+1F0h+arg_18]
0x180042bfb  add     rsp, 1D0h
0x180042c02  pop     r15
0x180042c04  pop     r14
0x180042c06  pop     rdi
0x180042c07  pop     rsi
0x180042c08  pop     rbp
0x180042c09  retn
```
