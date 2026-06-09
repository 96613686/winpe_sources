# DesktopAppXActivator::IsServiceRunning(ushort const *)

- ea: `0x180038e18`
- end: `0x180038f0d`
- name: `?IsServiceRunning@DesktopAppXActivator@@AEAA_NPEBG@Z`
- size: `245`
- prototype: `bool __fastcall(DesktopAppXActivator *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180006f30`

## callees

- `0x18002b1b0`
- `0x180036900`
- `0x180038e18`
- `0x18003a1a8`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180038e35`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180038e35`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180038e73`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180038e73`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180038eb8`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180038eb8`

## string_xrefs

- `0x180038e69`: `GamingServices`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
bool __fastcall DesktopAppXActivator::IsServiceRunning(DesktopAppXActivator *this, const unsigned __int16 *a2)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rax
  const char *v4; // r9
  const char *v5; // r9
  bool v6; // bl
  SC_HANDLE v8; // [rsp+20h] [rbp-48h] BYREF
  SC_HANDLE v9; // [rsp+28h] [rbp-40h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = OpenSCManagerW(0, 0, 1u);
  v9 = v2;
  if ( !v2 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x17A,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      (const char *)retaddr);
  v3 = OpenServiceW(v2, L"GamingServices", 4u);
  v8 = v3;
  if ( !v3 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x17D,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      v4);
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( !QueryServiceStatus(v3, &ServiceStatus) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x180,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      v5);
  v6 = ServiceStatus.dwCurrentState == 4;
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v8);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v9);
  return v6;
}

```

## disassembly

```asm
0x180038e18  push    rbx
0x180038e1a  sub     rsp, 60h
0x180038e1e  mov     rax, cs:__security_cookie
0x180038e25  xor     rax, rsp
0x180038e28  mov     [rsp+68h+var_18], rax
0x180038e2d  xor     edx, edx; lpDatabaseName
0x180038e2f  lea     r8d, [rdx+1]; dwDesiredAccess
0x180038e33  xor     ecx, ecx; lpMachineName
0x180038e35  call    cs:__imp_OpenSCManagerW
0x180038e3b  mov     [rsp+68h+var_40], rax
0x180038e40  test    rax, rax
0x180038e43  setz    cl
0x180038e46  mov     r9, [rsp+68h]; char *
0x180038e4b  test    cl, cl
0x180038e4d  jz      short loc_180038E63
0x180038e4f  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180038e56  mov     edx, 17Ah; void *
0x180038e5b  mov     rcx, r9; this
0x180038e5e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180038e63  mov     r8d, 4; dwDesiredAccess
0x180038e69  lea     rdx, ServiceName; "GamingServices"
0x180038e70  mov     rcx, rax; hSCManager
0x180038e73  call    cs:__imp_OpenServiceW
0x180038e79  mov     [rsp+68h+var_48], rax
0x180038e7e  test    rax, rax
0x180038e81  setz    dl
0x180038e84  mov     rcx, [rsp+68h]; this
0x180038e89  test    dl, dl
0x180038e8b  jz      short loc_180038E9E
0x180038e8d  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180038e94  mov     edx, 17Dh; void *
0x180038e99  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180038e9e  xorps   xmm0, xmm0
0x180038ea1  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x180038ea6  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x180038eab  mov     rbx, [rsp+68h]
0x180038eb0  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x180038eb5  mov     rcx, rax; hService
0x180038eb8  call    cs:__imp_QueryServiceStatus
0x180038ebe  test    eax, eax
0x180038ec0  jnz     short loc_180038ED6
0x180038ec2  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180038ec9  mov     edx, 180h; void *
0x180038ece  mov     rcx, rbx; this
0x180038ed1  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180038ed6  cmp     [rsp+68h+ServiceStatus.dwCurrentState], 4
0x180038edb  setz    bl
0x180038ede  lea     rcx, [rsp+68h+var_48]
0x180038ee3  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180038ee8  nop
0x180038ee9  lea     rcx, [rsp+68h+var_40]
0x180038eee  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180038ef3  mov     al, bl
0x180038ef5  jmp     short loc_180038EF9
0x180038ef7  xor     al, al
0x180038ef9  mov     rcx, [rsp+68h+var_18]
0x180038efe  xor     rcx, rsp; StackCookie
0x180038f01  call    __security_check_cookie
0x180038f06  add     rsp, 60h
0x180038f0a  pop     rbx
0x180038f0b  retn
```
