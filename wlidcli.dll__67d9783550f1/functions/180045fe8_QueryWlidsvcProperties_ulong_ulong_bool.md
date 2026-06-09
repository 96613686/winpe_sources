# QueryWlidsvcProperties(ulong &,ulong &,bool &)

- ea: `0x180045fe8`
- end: `0x18004626e`
- name: `?QueryWlidsvcProperties@@YAJAEAK0AEA_N@Z`
- size: `646`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180046e64`

## callees

- `0x180002da0`
- `0x180003ca8`
- `0x1800083ac`
- `0x1800083cc`
- `0x180044c3c`
- `0x180045940`
- `0x180045960`
- `0x1800459e4`
- `0x180045fe8`
- `0x180046964`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004611d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004611d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004613b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004613b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180046041`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180046041`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004607e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004607e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800460f1`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004618b`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800460f1`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18004618b`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800460cd`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800460cd`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x1800461d5`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x1800461d5`

## string_xrefs

- `0x180046038`: `ServicesActive`

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
0x180045fe8  mov     [rsp-8+arg_18], rbx
0x180045fed  push    rbp
0x180045fee  push    rsi
0x180045fef  push    rdi
0x180045ff0  push    r14
0x180045ff2  push    r15
0x180045ff4  lea     rbp, [rsp-0D0h]
0x180045ffc  sub     rsp, 1D0h
0x180046003  mov     rax, cs:__security_cookie
0x18004600a  xor     rax, rsp
0x18004600d  mov     [rbp+0F0h+var_30], rax
0x180046014  or      eax, 0FFFFFFFFh
0x180046017  mov     rsi, rcx
0x18004601a  mov     [rcx], eax
0x18004601c  mov     r15, r8
0x18004601f  mov     [rdx], eax
0x180046021  lea     rcx, [rsp+1F0h+var_180]; this
0x180046026  mov     byte ptr [r8], 1
0x18004602a  mov     r14, rdx
0x18004602d  call    ??$?0$$V@QueryWlidsvcProperties@MSAClientTraceTelemetry@@AEAA@U?$integral_constant@D$0A@@wistd@@@Z; MSAClientTraceTelemetry::QueryWlidsvcProperties::QueryWlidsvcProperties(wistd::integral_constant<char,0>)
0x180046032  mov     r8d, 4; dwDesiredAccess
0x180046038  lea     rdx, DatabaseName; "ServicesActive"
0x18004603f  xor     ecx, ecx; lpMachineName
0x180046041  call    cs:__imp_OpenSCManagerW
0x180046047  mov     [rsp+1F0h+var_1B0], rax
0x18004604c  test    rax, rax
0x18004604f  jnz     short loc_18004606E
0x180046051  mov     rcx, [rbp+0F8h]; this
0x180046058  lea     r8, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004605f  lea     edx, [rax+64h]; void *
0x180046062  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180046067  mov     ebx, eax
0x180046069  jmp     loc_180046232
0x18004606e  mov     r8d, 5; dwDesiredAccess
0x180046074  lea     rdx, ServiceName; "wlidsvc"
0x18004607b  mov     rcx, rax; hSCManager
0x18004607e  call    cs:__imp_OpenServiceW
0x180046084  mov     [rsp+1F0h+var_1C8], rax
0x180046089  mov     rbx, rax
0x18004608c  test    rax, rax
0x18004608f  jnz     short loc_1800460B8
0x180046091  lea     edx, [rax+6Bh]; void *
0x180046094  mov     rcx, [rbp+0F8h]; this
0x18004609b  lea     r8, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800460a2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800460a7  mov     ebx, eax
0x1800460a9  lea     rcx, [rsp+1F0h+var_1C8]
0x1800460ae  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800460b3  jmp     loc_180046232
0x1800460b8  xorps   xmm0, xmm0
0x1800460bb  lea     rdx, [rsp+1F0h+ServiceStatus]; lpServiceStatus
0x1800460c0  movups  xmmword ptr [rsp+1F0h+ServiceStatus.dwServiceType], xmm0
0x1800460c5  mov     rcx, rbx; hService
0x1800460c8  movups  xmmword ptr [rsp+1F0h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800460cd  call    cs:__imp_QueryServiceStatus
0x1800460d3  test    eax, eax
0x1800460d5  jnz     short loc_1800460DC
0x1800460d7  lea     edx, [rax+70h]
0x1800460da  jmp     short loc_180046094
0x1800460dc  lea     r9, [rsp+1F0h+pcbBytesNeeded]; pcbBytesNeeded
0x1800460e1  mov     [rsp+1F0h+pcbBytesNeeded], 0; int
0x1800460e9  xor     r8d, r8d; cbBufSize
0x1800460ec  xor     edx, edx; lpServiceConfig
0x1800460ee  mov     rcx, rbx; hService
0x1800460f1  call    cs:__imp_QueryServiceConfigW
0x1800460f7  test    eax, eax
0x1800460f9  jz      short loc_18004611D
0x1800460fb  mov     rcx, [rbp+0F8h]; this
0x180046102  lea     r8, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180046109  mov     ebx, 8000FFFFh
0x18004610e  mov     edx, 7Ah ; 'z'; void *
0x180046113  mov     r9d, ebx; char *
0x180046116  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004611b  jmp     short loc_1800460A9
0x18004611d  call    cs:__imp_GetLastError
0x180046123  cmp     eax, 7Ah ; 'z'
0x180046126  jz      short loc_180046132
0x180046128  mov     edx, 7Bh ; '{'
0x18004612d  jmp     loc_180046094
0x180046132  mov     edx, [rsp+1F0h+pcbBytesNeeded]; uBytes
0x180046136  mov     ecx, 40h ; '@'; uFlags
0x18004613b  call    cs:__imp_LocalAlloc
0x180046141  mov     [rsp+1F0h+var_1B8], rax
0x180046146  mov     rdi, rax
0x180046149  test    rax, rax
0x18004614c  jnz     short loc_18004617B
0x18004614e  mov     ebx, 8007000Eh
0x180046153  lea     edx, [rax+7Fh]; void *
0x180046156  mov     rcx, [rbp+0F8h]; this
0x18004615d  lea     r8, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180046164  mov     r9d, ebx; char *
0x180046167  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004616c  lea     rcx, [rsp+1F0h+var_1B8]
0x180046171  call    ??1?$unique_storage@U?$resource_policy@PEAU_QUERY_SERVICE_CONFIGW@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>(void)
0x180046176  jmp     loc_1800460A9
0x18004617b  mov     r8d, [rsp+1F0h+pcbBytesNeeded]; cbBufSize
0x180046180  lea     r9, [rsp+1F0h+pcbBytesNeeded]; pcbBytesNeeded
0x180046185  mov     rdx, rdi; lpServiceConfig
0x180046188  mov     rcx, rbx; hService
0x18004618b  call    cs:__imp_QueryServiceConfigW
0x180046191  test    eax, eax
0x180046193  jnz     short loc_1800461B1
0x180046195  mov     rcx, [rbp+0F8h]; this
0x18004619c  lea     r8, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800461a3  mov     edx, 86h; void *
0x1800461a8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800461ad  mov     ebx, eax
0x1800461af  jmp     short loc_18004616C
0x1800461b1  mov     [rsp+1F0h+var_1C0], 0FFFFFFFFh
0x1800461b9  call    IsPolicyManager_GetPolicyIntPresent
0x1800461be  test    al, al
0x1800461c0  jz      short loc_1800461FB
0x1800461c2  lea     r8, [rsp+1F0h+var_1C0]
0x1800461c7  lea     rdx, aAllowmicrosoft; "AllowMicrosoftAccountSignInAssistant"
0x1800461ce  lea     rcx, aAccounts; "Accounts"
0x1800461d5  call    cs:__imp_PolicyManager_GetPolicyInt
0x1800461db  mov     ebx, eax
0x1800461dd  mov     eax, 80000000h
0x1800461e2  lea     ecx, [rbx+rax]
0x1800461e5  test    eax, ecx
0x1800461e7  jnz     short loc_1800461FB
0x1800461e9  cmp     ebx, 8007007Fh
0x1800461ef  jz      short loc_1800461FB
0x1800461f1  mov     edx, 8Eh
0x1800461f6  jmp     loc_180046156
0x1800461fb  cmp     [rsp+1F0h+var_1C0], 0
0x180046200  lea     rcx, [rsp+1F0h+var_180]
0x180046205  setnz   al
0x180046208  mov     [r15], al
0x18004620b  mov     eax, [rdi+4]
0x18004620e  mov     [r14], eax
0x180046211  mov     eax, [rsp+1F0h+ServiceStatus.dwCurrentState]
0x180046215  mov     [rsi], eax
0x180046217  call    ?Stop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18004621c  lea     rcx, [rsp+1F0h+var_1B8]
0x180046221  call    ??1?$unique_storage@U?$resource_policy@PEAU_QUERY_SERVICE_CONFIGW@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>(void)
0x180046226  lea     rcx, [rsp+1F0h+var_1C8]
0x18004622b  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180046230  xor     ebx, ebx
0x180046232  lea     rcx, [rsp+1F0h+var_1B0]
0x180046237  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18004623c  lea     rcx, [rsp+1F0h+var_180]; this
0x180046241  call    ??1QueryWlidsvcProperties@MSAClientTraceTelemetry@@QEAA@XZ; MSAClientTraceTelemetry::QueryWlidsvcProperties::~QueryWlidsvcProperties(void)
0x180046246  mov     eax, ebx
0x180046248  mov     rcx, [rbp+0F0h+var_30]
0x18004624f  xor     rcx, rsp; StackCookie
0x180046252  call    __security_check_cookie
0x180046257  mov     rbx, [rsp+1F0h+arg_18]
0x18004625f  add     rsp, 1D0h
0x180046266  pop     r15
0x180046268  pop     r14
0x18004626a  pop     rdi
0x18004626b  pop     rsi
0x18004626c  pop     rbp
0x18004626d  retn
```
