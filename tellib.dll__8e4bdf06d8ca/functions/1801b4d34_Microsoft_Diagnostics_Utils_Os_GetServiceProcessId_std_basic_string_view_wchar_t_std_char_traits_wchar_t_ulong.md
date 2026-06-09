# Microsoft::Diagnostics::Utils::Os::GetServiceProcessId(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,ulong &)

- ea: `0x1801b4d34`
- end: `0x1801b4f6f`
- name: `?GetServiceProcessId@Os@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAK@Z`
- size: `571`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180040454`
- `0x1802059c8`
- `0x180303120`

## callees

- `0x18001d160`
- `0x180035698`
- `0x18008bd1c`
- `0x1800d0d7c`
- `0x18012de40`
- `0x180170014`
- `0x1801b27a8`
- `0x1801b4d34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b4e5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b4e5c`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1801b4e48`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1801b4e9b`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1801b4e48`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1801b4e9b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1801b4dd1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1801b4dd1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1801b4d69`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1801b4d69`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::Utils::Os::GetServiceProcessId(_QWORD *a1, _DWORD *a2)
{
  SC_HANDLE v4; // rbx
  const char *v5; // r9
  unsigned int v6; // ebx
  __int64 v8; // rax
  SC_HANDLE v9; // rbx
  const char *v10; // r9
  unsigned int v11; // ebx
  const char *v12; // r9
  LPBYTE v13; // rdi
  const char *v14; // r9
  unsigned int v15; // ebx
  unsigned int LastError; // ebx
  DWORD cbBufSize; // [rsp+30h] [rbp-58h] BYREF
  SC_HANDLE v18; // [rsp+38h] [rbp-50h] BYREF
  SC_HANDLE v19; // [rsp+40h] [rbp-48h] BYREF
  LPBYTE lpBuffer; // [rsp+48h] [rbp-40h] BYREF
  _BYTE v21[32]; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *a2 = 0;
  v4 = OpenSCManagerW(0, 0, 4u);
  v18 = v4;
  if ( v4 )
  {
    v8 = std::wstring::wstring((__int64)v21, a1);
    if ( *(_QWORD *)(v8 + 24) > 7u )
      v8 = *(_QWORD *)v8;
    v9 = OpenServiceW(v4, (LPCWSTR)v8, 4u);
    v19 = v9;
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v21);
    if ( v9 )
    {
      cbBufSize = 0;
      if ( QueryServiceStatusEx(v9, SC_STATUS_PROCESS_INFO, 0, 0, &cbBufSize) || GetLastError() != 122 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x5FF,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                      v12);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v19);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
        return LastError;
      }
      else
      {
        std::make_unique<unsigned char [0],0>(&lpBuffer, cbBufSize);
        v13 = lpBuffer;
        if ( QueryServiceStatusEx(v9, SC_STATUS_PROCESS_INFO, lpBuffer, cbBufSize, &cbBufSize) )
        {
          *a2 = *((_DWORD *)v13 + 7);
          std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpBuffer);
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v19);
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
          return 0;
        }
        else
        {
          v15 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x605,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                  v14);
          std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&lpBuffer);
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v19);
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
          return v15;
        }
      }
    }
    else
    {
      v11 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x5F8,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
              v10);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v19);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
      return v11;
    }
  }
  else
  {
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x5F5,
           (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
           v5);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v18);
    return v6;
  }
}

```

## disassembly

```asm
0x1801b4d34  mov     [rsp+arg_10], rbx
0x1801b4d39  mov     [rsp+arg_18], rsi
0x1801b4d3e  push    rdi
0x1801b4d3f  sub     rsp, 80h
0x1801b4d46  mov     rax, cs:__security_cookie
0x1801b4d4d  xor     rax, rsp
0x1801b4d50  mov     [rsp+88h+var_18], rax
0x1801b4d55  mov     rsi, rdx
0x1801b4d58  mov     rdi, rcx
0x1801b4d5b  mov     dword ptr [rdx], 0
0x1801b4d61  xor     edx, edx; lpDatabaseName
0x1801b4d63  xor     ecx, ecx; lpMachineName
0x1801b4d65  lea     r8d, [rdx+4]; dwDesiredAccess
0x1801b4d69  call    cs:__imp_OpenSCManagerW
0x1801b4d70  nop     dword ptr [rax+rax+00h]
0x1801b4d75  mov     rbx, rax
0x1801b4d78  mov     [rsp+88h+var_50], rax
0x1801b4d7d  test    rax, rax
0x1801b4d80  jnz     short loc_1801B4DAE
0x1801b4d82  mov     rcx, [rsp+88h]; this
0x1801b4d8a  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x1801b4d91  mov     edx, 5F5h; void *
0x1801b4d96  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801b4d9b  mov     ebx, eax
0x1801b4d9d  lea     rcx, [rsp+88h+var_50]
0x1801b4da2  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1801b4da7  mov     eax, ebx
0x1801b4da9  jmp     loc_1801B4F4C
0x1801b4dae  mov     rdx, rdi
0x1801b4db1  lea     rcx, [rsp+88h+var_38]
0x1801b4db6  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1801b4dbb  cmp     qword ptr [rax+18h], 7
0x1801b4dc0  jbe     short loc_1801B4DC5
0x1801b4dc2  mov     rax, [rax]
0x1801b4dc5  mov     r8d, 4; dwDesiredAccess
0x1801b4dcb  mov     rdx, rax; lpServiceName
0x1801b4dce  mov     rcx, rbx; hSCManager
0x1801b4dd1  call    cs:__imp_OpenServiceW
0x1801b4dd8  nop     dword ptr [rax+rax+00h]
0x1801b4ddd  mov     rbx, rax
0x1801b4de0  mov     [rsp+88h+var_48], rax
0x1801b4de5  lea     rcx, [rsp+88h+var_38]; this
0x1801b4dea  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801b4def  test    rbx, rbx
0x1801b4df2  jnz     short loc_1801B4E2B
0x1801b4df4  mov     rcx, [rsp+88h]; this
0x1801b4dfc  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x1801b4e03  mov     edx, 5F8h; void *
0x1801b4e08  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801b4e0d  mov     ebx, eax
0x1801b4e0f  lea     rcx, [rsp+88h+var_48]
0x1801b4e14  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1801b4e19  nop
0x1801b4e1a  lea     rcx, [rsp+88h+var_50]
0x1801b4e1f  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1801b4e24  mov     eax, ebx
0x1801b4e26  jmp     loc_1801B4F4C
0x1801b4e2b  mov     [rsp+88h+cbBufSize], 0
0x1801b4e33  lea     rax, [rsp+88h+cbBufSize]
0x1801b4e38  mov     [rsp+88h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1801b4e3d  xor     r9d, r9d; cbBufSize
0x1801b4e40  xor     r8d, r8d; lpBuffer
0x1801b4e43  xor     edx, edx; InfoLevel
0x1801b4e45  mov     rcx, rbx; hService
0x1801b4e48  call    cs:__imp_QueryServiceStatusEx
0x1801b4e4f  nop     dword ptr [rax+rax+00h]
0x1801b4e54  test    eax, eax
0x1801b4e56  jnz     loc_1801B4F14
0x1801b4e5c  call    cs:__imp_GetLastError
0x1801b4e63  nop     dword ptr [rax+rax+00h]
0x1801b4e68  cmp     eax, 7Ah ; 'z'
0x1801b4e6b  jnz     loc_1801B4F14
0x1801b4e71  mov     edx, [rsp+88h+cbBufSize]
0x1801b4e75  lea     rcx, [rsp+88h+lpBuffer]
0x1801b4e7a  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x1801b4e7f  lea     rax, [rsp+88h+cbBufSize]
0x1801b4e84  mov     [rsp+88h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1801b4e89  mov     r9d, [rsp+88h+cbBufSize]; cbBufSize
0x1801b4e8e  mov     rdi, [rsp+88h+lpBuffer]
0x1801b4e93  mov     r8, rdi; lpBuffer
0x1801b4e96  xor     edx, edx; InfoLevel
0x1801b4e98  mov     rcx, rbx; hService
0x1801b4e9b  call    cs:__imp_QueryServiceStatusEx
0x1801b4ea2  nop     dword ptr [rax+rax+00h]
0x1801b4ea7  test    eax, eax
0x1801b4ea9  jnz     short loc_1801B4EEA
0x1801b4eab  mov     rcx, [rsp+88h]; this
0x1801b4eb3  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x1801b4eba  mov     edx, 605h; void *
0x1801b4ebf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801b4ec4  mov     ebx, eax
0x1801b4ec6  lea     rcx, [rsp+88h+lpBuffer]
0x1801b4ecb  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1801b4ed0  nop
0x1801b4ed1  lea     rcx, [rsp+88h+var_48]
0x1801b4ed6  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1801b4edb  nop
0x1801b4edc  lea     rcx, [rsp+88h+var_50]
0x1801b4ee1  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1801b4ee6  mov     eax, ebx
0x1801b4ee8  jmp     short loc_1801B4F4C
0x1801b4eea  mov     eax, [rdi+1Ch]
0x1801b4eed  mov     [rsi], eax
0x1801b4eef  lea     rcx, [rsp+88h+lpBuffer]
0x1801b4ef4  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1801b4ef9  nop
0x1801b4efa  lea     rcx, [rsp+88h+var_48]
0x1801b4eff  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1801b4f04  nop
0x1801b4f05  lea     rcx, [rsp+88h+var_50]
0x1801b4f0a  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1801b4f0f  nop
0x1801b4f10  xor     eax, eax
0x1801b4f12  jmp     short loc_1801B4F4C
0x1801b4f14  mov     rcx, [rsp+88h]; this
0x1801b4f1c  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x1801b4f23  mov     edx, 5FFh; void *
0x1801b4f28  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801b4f2d  mov     ebx, eax
0x1801b4f2f  lea     rcx, [rsp+88h+var_48]
0x1801b4f34  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1801b4f39  nop
0x1801b4f3a  lea     rcx, [rsp+88h+var_50]
0x1801b4f3f  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1801b4f44  mov     eax, ebx
0x1801b4f46  jmp     short loc_1801B4F4C
0x1801b4f48  mov     eax, [rsp+88h+cbBufSize]
0x1801b4f4c  mov     rcx, [rsp+88h+var_18]
0x1801b4f51  xor     rcx, rsp; StackCookie
0x1801b4f54  call    __security_check_cookie
0x1801b4f59  lea     r11, [rsp+88h+var_8]
0x1801b4f61  mov     rbx, [r11+20h]
0x1801b4f65  mov     rsi, [r11+28h]
0x1801b4f69  mov     rsp, r11
0x1801b4f6c  pop     rdi
0x1801b4f6d  retn
```
