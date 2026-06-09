# QueryWlidsvcProperties(ulong &,ulong &,bool &)

- ea: `0x18000cec8`
- end: `0x18000d14e`
- name: `?QueryWlidsvcProperties@@YAJAEAK0AEA_N@Z`
- size: `646`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000dd84`

## callees

- `0x1800027f0`
- `0x180003590`
- `0x1800085f4`
- `0x180008614`
- `0x18000c3ac`
- `0x18000c804`
- `0x18000c824`
- `0x18000c8c8`
- `0x18000cec8`
- `0x18000d88c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cffd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000cf21`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000cf21`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000cf5e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000cf5e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000cfd1`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000d06b`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000cfd1`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000d06b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d01b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d01b`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18000cfad`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18000cfad`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18000d0b5`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18000d0b5`

## string_xrefs

- `0x18000cf18`: `ServicesActive`

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
0x18000cec8  mov     [rsp-8+arg_18], rbx
0x18000cecd  push    rbp
0x18000cece  push    rsi
0x18000cecf  push    rdi
0x18000ced0  push    r14
0x18000ced2  push    r15
0x18000ced4  lea     rbp, [rsp-0D0h]
0x18000cedc  sub     rsp, 1D0h
0x18000cee3  mov     rax, cs:__security_cookie
0x18000ceea  xor     rax, rsp
0x18000ceed  mov     [rbp+0F0h+var_30], rax
0x18000cef4  or      eax, 0FFFFFFFFh
0x18000cef7  mov     rsi, rcx
0x18000cefa  mov     [rcx], eax
0x18000cefc  mov     r15, r8
0x18000ceff  mov     [rdx], eax
0x18000cf01  lea     rcx, [rsp+1F0h+var_180]; this
0x18000cf06  mov     byte ptr [r8], 1
0x18000cf0a  mov     r14, rdx
0x18000cf0d  call    ??$?0$$V@QueryWlidsvcProperties@MSAClientTraceTelemetry@@AEAA@U?$integral_constant@D$0A@@wistd@@@Z; MSAClientTraceTelemetry::QueryWlidsvcProperties::QueryWlidsvcProperties(wistd::integral_constant<char,0>)
0x18000cf12  mov     r8d, 4; dwDesiredAccess
0x18000cf18  lea     rdx, DatabaseName; "ServicesActive"
0x18000cf1f  xor     ecx, ecx; lpMachineName
0x18000cf21  call    cs:__imp_OpenSCManagerW
0x18000cf27  mov     [rsp+1F0h+var_1B0], rax
0x18000cf2c  test    rax, rax
0x18000cf2f  jnz     short loc_18000CF4E
0x18000cf31  mov     rcx, [rbp+0F8h]; this
0x18000cf38  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000cf3f  lea     edx, [rax+64h]; void *
0x18000cf42  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cf47  mov     ebx, eax
0x18000cf49  jmp     loc_18000D112
0x18000cf4e  mov     r8d, 5; dwDesiredAccess
0x18000cf54  lea     rdx, ServiceName; "wlidsvc"
0x18000cf5b  mov     rcx, rax; hSCManager
0x18000cf5e  call    cs:__imp_OpenServiceW
0x18000cf64  mov     [rsp+1F0h+var_1C8], rax
0x18000cf69  mov     rbx, rax
0x18000cf6c  test    rax, rax
0x18000cf6f  jnz     short loc_18000CF98
0x18000cf71  lea     edx, [rax+6Bh]; void *
0x18000cf74  mov     rcx, [rbp+0F8h]; this
0x18000cf7b  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000cf82  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cf87  mov     ebx, eax
0x18000cf89  lea     rcx, [rsp+1F0h+var_1C8]
0x18000cf8e  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000cf93  jmp     loc_18000D112
0x18000cf98  xorps   xmm0, xmm0
0x18000cf9b  lea     rdx, [rsp+1F0h+ServiceStatus]; lpServiceStatus
0x18000cfa0  movups  xmmword ptr [rsp+1F0h+ServiceStatus.dwServiceType], xmm0
0x18000cfa5  mov     rcx, rbx; hService
0x18000cfa8  movups  xmmword ptr [rsp+1F0h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000cfad  call    cs:__imp_QueryServiceStatus
0x18000cfb3  test    eax, eax
0x18000cfb5  jnz     short loc_18000CFBC
0x18000cfb7  lea     edx, [rax+70h]
0x18000cfba  jmp     short loc_18000CF74
0x18000cfbc  lea     r9, [rsp+1F0h+pcbBytesNeeded]; pcbBytesNeeded
0x18000cfc1  mov     [rsp+1F0h+pcbBytesNeeded], 0; int
0x18000cfc9  xor     r8d, r8d; cbBufSize
0x18000cfcc  xor     edx, edx; lpServiceConfig
0x18000cfce  mov     rcx, rbx; hService
0x18000cfd1  call    cs:__imp_QueryServiceConfigW
0x18000cfd7  test    eax, eax
0x18000cfd9  jz      short loc_18000CFFD
0x18000cfdb  mov     rcx, [rbp+0F8h]; this
0x18000cfe2  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000cfe9  mov     ebx, 8000FFFFh
0x18000cfee  mov     edx, 7Ah ; 'z'; void *
0x18000cff3  mov     r9d, ebx; char *
0x18000cff6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cffb  jmp     short loc_18000CF89
0x18000cffd  call    cs:__imp_GetLastError
0x18000d003  cmp     eax, 7Ah ; 'z'
0x18000d006  jz      short loc_18000D012
0x18000d008  mov     edx, 7Bh ; '{'
0x18000d00d  jmp     loc_18000CF74
0x18000d012  mov     edx, [rsp+1F0h+pcbBytesNeeded]; uBytes
0x18000d016  mov     ecx, 40h ; '@'; uFlags
0x18000d01b  call    cs:__imp_LocalAlloc
0x18000d021  mov     [rsp+1F0h+var_1B8], rax
0x18000d026  mov     rdi, rax
0x18000d029  test    rax, rax
0x18000d02c  jnz     short loc_18000D05B
0x18000d02e  mov     ebx, 8007000Eh
0x18000d033  lea     edx, [rax+7Fh]; void *
0x18000d036  mov     rcx, [rbp+0F8h]; this
0x18000d03d  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000d044  mov     r9d, ebx; char *
0x18000d047  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d04c  lea     rcx, [rsp+1F0h+var_1B8]
0x18000d051  call    ??1?$unique_storage@U?$resource_policy@PEAU_QUERY_SERVICE_CONFIGW@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>(void)
0x18000d056  jmp     loc_18000CF89
0x18000d05b  mov     r8d, [rsp+1F0h+pcbBytesNeeded]; cbBufSize
0x18000d060  lea     r9, [rsp+1F0h+pcbBytesNeeded]; pcbBytesNeeded
0x18000d065  mov     rdx, rdi; lpServiceConfig
0x18000d068  mov     rcx, rbx; hService
0x18000d06b  call    cs:__imp_QueryServiceConfigW
0x18000d071  test    eax, eax
0x18000d073  jnz     short loc_18000D091
0x18000d075  mov     rcx, [rbp+0F8h]; this
0x18000d07c  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18000d083  mov     edx, 86h; void *
0x18000d088  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d08d  mov     ebx, eax
0x18000d08f  jmp     short loc_18000D04C
0x18000d091  mov     [rsp+1F0h+var_1C0], 0FFFFFFFFh
0x18000d099  call    IsPolicyManager_GetPolicyIntPresent
0x18000d09e  test    al, al
0x18000d0a0  jz      short loc_18000D0DB
0x18000d0a2  lea     r8, [rsp+1F0h+var_1C0]
0x18000d0a7  lea     rdx, aAllowmicrosoft; "AllowMicrosoftAccountSignInAssistant"
0x18000d0ae  lea     rcx, aAccounts; "Accounts"
0x18000d0b5  call    cs:__imp_PolicyManager_GetPolicyInt
0x18000d0bb  mov     ebx, eax
0x18000d0bd  mov     eax, 80000000h
0x18000d0c2  lea     ecx, [rbx+rax]
0x18000d0c5  test    eax, ecx
0x18000d0c7  jnz     short loc_18000D0DB
0x18000d0c9  cmp     ebx, 8007007Fh
0x18000d0cf  jz      short loc_18000D0DB
0x18000d0d1  mov     edx, 8Eh
0x18000d0d6  jmp     loc_18000D036
0x18000d0db  cmp     [rsp+1F0h+var_1C0], 0
0x18000d0e0  lea     rcx, [rsp+1F0h+var_180]
0x18000d0e5  setnz   al
0x18000d0e8  mov     [r15], al
0x18000d0eb  mov     eax, [rdi+4]
0x18000d0ee  mov     [r14], eax
0x18000d0f1  mov     eax, [rsp+1F0h+ServiceStatus.dwCurrentState]
0x18000d0f5  mov     [rsi], eax
0x18000d0f7  call    ?Stop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000d0fc  lea     rcx, [rsp+1F0h+var_1B8]
0x18000d101  call    ??1?$unique_storage@U?$resource_policy@PEAU_QUERY_SERVICE_CONFIGW@@$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_QUERY_SERVICE_CONFIGW *,void * (void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_QUERY_SERVICE_CONFIGW *,_QUERY_SERVICE_CONFIGW *,0,std::nullptr_t>>(void)
0x18000d106  lea     rcx, [rsp+1F0h+var_1C8]
0x18000d10b  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000d110  xor     ebx, ebx
0x18000d112  lea     rcx, [rsp+1F0h+var_1B0]
0x18000d117  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000d11c  lea     rcx, [rsp+1F0h+var_180]; this
0x18000d121  call    ??1QueryWlidsvcProperties@MSAClientTraceTelemetry@@QEAA@XZ; MSAClientTraceTelemetry::QueryWlidsvcProperties::~QueryWlidsvcProperties(void)
0x18000d126  mov     eax, ebx
0x18000d128  mov     rcx, [rbp+0F0h+var_30]
0x18000d12f  xor     rcx, rsp; StackCookie
0x18000d132  call    __security_check_cookie
0x18000d137  mov     rbx, [rsp+1F0h+arg_18]
0x18000d13f  add     rsp, 1D0h
0x18000d146  pop     r15
0x18000d148  pop     r14
0x18000d14a  pop     rdi
0x18000d14b  pop     rsi
0x18000d14c  pop     rbp
0x18000d14d  retn
```
