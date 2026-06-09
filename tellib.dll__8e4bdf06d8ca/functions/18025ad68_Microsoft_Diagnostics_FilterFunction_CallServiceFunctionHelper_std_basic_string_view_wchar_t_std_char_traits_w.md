# Microsoft::Diagnostics::FilterFunction::CallServiceFunctionHelper(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool,bool)

- ea: `0x18025ad68`
- end: `0x18025afe8`
- name: `?CallServiceFunctionHelper@FilterFunction@Diagnostics@Microsoft@@SA?AU?$pair@JV?$variant@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_J_KN@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@_N1@Z`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18025d900`

## callees

- `0x18001d160`
- `0x180035698`
- `0x1800a1e24`
- `0x1800bc2e0`
- `0x1800d2b24`
- `0x18012de40`
- `0x1802533a8`
- `0x18025ad68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18025ade1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18025ae64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18025ade1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18025ae64`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18025ae3d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18025ae3d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18025adcd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18025adcd`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18025af31`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18025af31`

## string_xrefs

- `0x18025ae09`: `onecore\base\telemetry\utc\service\scenarios\filters\scriptfilternodes.cpp`
- `0x18025aed7`: `onecore\base\telemetry\utc\service\scenarios\filters\scriptfilternodes.cpp`
- `0x18025af49`: `onecore\base\telemetry\utc\service\scenarios\filters\scriptfilternodes.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::FilterFunction::CallServiceFunctionHelper(
        __int64 a1,
        _QWORD *a2,
        char a3,
        char a4)
{
  SC_HANDLE v9; // rbx
  signed int LastError; // eax
  __int64 v11; // rax
  SC_HANDLE v12; // rbx
  DWORD v13; // eax
  const char *v14; // r9
  char v15; // al
  unsigned int v16[2]; // [rsp+20h] [rbp-88h] BYREF
  _QWORD v17[3]; // [rsp+28h] [rbp-80h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v19[32]; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v17[1] = a1;
  if ( !a3 && a4 )
  {
    *(_DWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_BYTE *)(a1 + 40) = 2;
    return a1;
  }
  v9 = OpenSCManagerW(0, 0, 4u);
  v17[0] = v9;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( !v9 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5DF,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\scriptfilternodes.cpp",
      (const char *)(unsigned int)LastError,
      v16[0]);
  v11 = std::wstring::wstring((__int64)v19, a2);
  if ( *(_QWORD *)(v11 + 24) > 7u )
    v11 = *(_QWORD *)v11;
  v12 = OpenServiceW(v9, (LPCWSTR)v11, 4u);
  *(_QWORD *)v16 = v12;
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v19);
  if ( !v12 )
  {
    v13 = GetLastError();
    if ( v13 != 1060 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x5F5,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\scriptfilternodes.cpp",
        (const char *)v13,
        v16[0]);
    *(_DWORD *)a1 = 0;
    if ( a3 )
      *(_QWORD *)(a1 + 8) = 0;
    else
      *(_QWORD *)(a1 + 8) = 1;
LABEL_14:
    *(_BYTE *)(a1 + 40) = 2;
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v16);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v17);
    return a1;
  }
  if ( a3 )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( !QueryServiceStatus(v12, &ServiceStatus) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x602,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\scriptfilternodes.cpp",
        v14);
    v15 = ServiceStatus.dwCurrentState == 4;
    *(_DWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = a4 == v15;
    goto LABEL_14;
  }
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_BYTE *)(a1 + 40) = 2;
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v16);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v17);
  return a1;
}

```

## disassembly

```asm
0x18025ad68  mov     [rsp+arg_10], rbx
0x18025ad6d  mov     [rsp+arg_18], rsi
0x18025ad72  push    rdi
0x18025ad73  push    r14
0x18025ad75  push    r15
0x18025ad77  sub     rsp, 90h
0x18025ad7e  mov     rax, cs:__security_cookie
0x18025ad85  xor     rax, rsp
0x18025ad88  mov     [rsp+0A8h+var_28], rax
0x18025ad90  mov     r14b, r9b
0x18025ad93  mov     sil, r8b
0x18025ad96  mov     r15, rdx
0x18025ad99  mov     rdi, rcx
0x18025ad9c  mov     [rsp+0A8h+var_78], rcx
0x18025ada1  test    r8b, r8b
0x18025ada4  jnz     short loc_18025ADC5
0x18025ada6  test    r9b, r9b
0x18025ada9  jz      short loc_18025ADC5
0x18025adab  mov     dword ptr [rcx], 0
0x18025adb1  mov     qword ptr [rcx+8], 0
0x18025adb9  mov     byte ptr [rcx+28h], 2
0x18025adbd  mov     rax, rcx
0x18025adc0  jmp     loc_18025AFBE
0x18025adc5  xor     edx, edx; lpDatabaseName
0x18025adc7  xor     ecx, ecx; lpMachineName
0x18025adc9  lea     r8d, [rdx+4]; dwDesiredAccess
0x18025adcd  call    cs:__imp_OpenSCManagerW
0x18025add4  nop     dword ptr [rax+rax+00h]
0x18025add9  mov     rbx, rax
0x18025addc  mov     [rsp+0A8h+var_80], rax
0x18025ade1  call    cs:__imp_GetLastError
0x18025ade8  nop     dword ptr [rax+rax+00h]
0x18025aded  test    eax, eax
0x18025adef  jle     short loc_18025ADF9
0x18025adf1  movzx   eax, ax
0x18025adf4  or      eax, 80070000h
0x18025adf9  mov     rcx, [rsp+0A8h]; this
0x18025ae01  test    rbx, rbx
0x18025ae04  jnz     short loc_18025AE1A
0x18025ae06  mov     r9d, eax; char *
0x18025ae09  lea     r8, aOnecoreBaseTel_34; "onecore\\base\\telemetry\\utc\\service"...
0x18025ae10  mov     edx, 5DFh; void *
0x18025ae15  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18025ae1a  mov     rdx, r15
0x18025ae1d  lea     rcx, [rsp+0A8h+var_48]
0x18025ae22  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18025ae27  cmp     qword ptr [rax+18h], 7
0x18025ae2c  jbe     short loc_18025AE31
0x18025ae2e  mov     rax, [rax]
0x18025ae31  mov     r8d, 4; dwDesiredAccess
0x18025ae37  mov     rdx, rax; lpServiceName
0x18025ae3a  mov     rcx, rbx; hSCManager
0x18025ae3d  call    cs:__imp_OpenServiceW
0x18025ae44  nop     dword ptr [rax+rax+00h]
0x18025ae49  mov     rbx, rax
0x18025ae4c  mov     qword ptr [rsp+0A8h+var_88], rax; unsigned int
0x18025ae51  lea     rcx, [rsp+0A8h+var_48]; this
0x18025ae56  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18025ae5b  test    rbx, rbx
0x18025ae5e  jnz     loc_18025AEE8
0x18025ae64  call    cs:__imp_GetLastError
0x18025ae6b  nop     dword ptr [rax+rax+00h]
0x18025ae70  cmp     eax, 424h
0x18025ae75  jnz     short loc_18025AECC
0x18025ae77  mov     [rdi], ebx
0x18025ae79  test    sil, sil
0x18025ae7c  jz      short loc_18025AEA3
0x18025ae7e  mov     [rdi+8], rbx
0x18025ae82  mov     byte ptr [rdi+28h], 2
0x18025ae86  lea     rcx, [rsp+0A8h+var_88]
0x18025ae8b  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18025ae90  nop
0x18025ae91  lea     rcx, [rsp+0A8h+var_80]
0x18025ae96  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18025ae9b  mov     rax, rdi
0x18025ae9e  jmp     loc_18025AFBE
0x18025aea3  mov     qword ptr [rdi+8], 1
0x18025aeab  mov     byte ptr [rdi+28h], 2
0x18025aeaf  lea     rcx, [rsp+0A8h+var_88]
0x18025aeb4  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18025aeb9  nop
0x18025aeba  lea     rcx, [rsp+0A8h+var_80]
0x18025aebf  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18025aec4  mov     rax, rdi
0x18025aec7  jmp     loc_18025AFBE
0x18025aecc  mov     rcx, [rsp+0A8h]; this
0x18025aed4  mov     r9d, eax; char *
0x18025aed7  lea     r8, aOnecoreBaseTel_34; "onecore\\base\\telemetry\\utc\\service"...
0x18025aede  mov     edx, 5F5h; void *
0x18025aee3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18025aee8  test    sil, sil
0x18025aeeb  jnz     short loc_18025AF1C
0x18025aeed  mov     dword ptr [rdi], 0
0x18025aef3  mov     qword ptr [rdi+8], 0
0x18025aefb  mov     byte ptr [rdi+28h], 2
0x18025aeff  lea     rcx, [rsp+0A8h+var_88]
0x18025af04  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18025af09  nop
0x18025af0a  lea     rcx, [rsp+0A8h+var_80]
0x18025af0f  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18025af14  mov     rax, rdi
0x18025af17  jmp     loc_18025AFBE
0x18025af1c  xorps   xmm0, xmm0
0x18025af1f  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwServiceType], xmm0
0x18025af24  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwWin32ExitCode], xmm0
0x18025af29  lea     rdx, [rsp+0A8h+ServiceStatus]; lpServiceStatus
0x18025af2e  mov     rcx, rbx; hService
0x18025af31  call    cs:__imp_QueryServiceStatus
0x18025af38  nop     dword ptr [rax+rax+00h]
0x18025af3d  test    eax, eax
0x18025af3f  jnz     short loc_18025AF5A
0x18025af41  mov     rcx, [rsp+0A8h]; this
0x18025af49  lea     r8, aOnecoreBaseTel_34; "onecore\\base\\telemetry\\utc\\service"...
0x18025af50  mov     edx, 602h; void *
0x18025af55  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18025af5a  cmp     [rsp+0A8h+ServiceStatus.dwCurrentState], 4
0x18025af5f  setz    al
0x18025af62  mov     dword ptr [rdi], 0
0x18025af68  cmp     r14b, al
0x18025af6b  jnz     short loc_18025AF93
0x18025af6d  mov     qword ptr [rdi+8], 1
0x18025af75  mov     byte ptr [rdi+28h], 2
0x18025af79  lea     rcx, [rsp+0A8h+var_88]
0x18025af7e  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18025af83  nop
0x18025af84  lea     rcx, [rsp+0A8h+var_80]
0x18025af89  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18025af8e  mov     rax, rdi
0x18025af91  jmp     short loc_18025AFBE
0x18025af93  mov     qword ptr [rdi+8], 0
0x18025af9b  mov     byte ptr [rdi+28h], 2
0x18025af9f  lea     rcx, [rsp+0A8h+var_88]
0x18025afa4  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18025afa9  nop
0x18025afaa  lea     rcx, [rsp+0A8h+var_80]
0x18025afaf  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18025afb4  mov     rax, rdi
0x18025afb7  jmp     short loc_18025AFBE
0x18025afb9  mov     rax, [rsp+0A8h+var_78]
0x18025afbe  mov     rcx, [rsp+0A8h+var_28]
0x18025afc6  xor     rcx, rsp; StackCookie
0x18025afc9  call    __security_check_cookie
0x18025afce  lea     r11, [rsp+0A8h+var_18]
0x18025afd6  mov     rbx, [r11+30h]
0x18025afda  mov     rsi, [r11+38h]
0x18025afde  mov     rsp, r11
0x18025afe1  pop     r15
0x18025afe3  pop     r14
0x18025afe5  pop     rdi
0x18025afe6  retn
```
