# CAudioSrvMonitor::Start(void)

- ea: `0x1800e9c78`
- end: `0x1800e9de3`
- name: `?Start@CAudioSrvMonitor@@QEAAJXZ`
- size: `363`
- prototype: `__int64 __fastcall(CAudioSrvMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800e9260`

## callees

- `0x180036c2c`
- `0x180037140`
- `0x180054130`
- `0x1800e9c14`
- `0x1800e9c78`
- `0x1800e9dec`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800e9ce9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800e9ce9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800e9ca8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800e9ca8`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800e9d3c`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800e9d3c`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x1800e9d7d`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x1800e9d7d`

## string_xrefs

- `0x1800e9c99`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall CAudioSrvMonitor::Start(CAudioSrvMonitor *this)
{
  SC_HANDLE v2; // rax
  const char *v3; // r9
  unsigned int v4; // ebx
  SC_HANDLE v5; // rax
  const char *v6; // r9
  SC_HANDLE v7; // rbx
  __int64 v8; // rdx
  unsigned int LastError; // eax
  unsigned int v10; // eax
  SC_HANDLE v12; // [rsp+30h] [rbp-48h] BYREF
  SC_HANDLE v13; // [rsp+38h] [rbp-40h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v2 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v13 = v2;
  if ( v2 )
  {
    v5 = OpenServiceW(v2, L"AudioSrv", 4u);
    v12 = v5;
    v7 = v5;
    if ( v5 )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( QueryServiceStatus(v5, &ServiceStatus) )
      {
        *((_DWORD *)this + 5) = ServiceStatus.dwCurrentState;
        wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&void UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(
          (char *)this + 24,
          0);
        v10 = SubscribeServiceChangeNotifications(v7, 2, CAudioSrvMonitor::AudioSrvStatusChangedCallback, this);
        if ( !v10 )
        {
          wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v12);
          v4 = 0;
          goto LABEL_12;
        }
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x25,
                      (unsigned int)"shell\\twinui\\playbackmanager\\audiosrvmonitor.cpp",
                      (const char *)v10,
                      (int)this + 24);
        goto LABEL_6;
      }
      v8 = 28;
    }
    else
    {
      v8 = 24;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v8,
                  (unsigned int)"shell\\twinui\\playbackmanager\\audiosrvmonitor.cpp",
                  v6);
LABEL_6:
    v4 = LastError;
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v12);
    goto LABEL_12;
  }
  v4 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)0x14,
         (unsigned int)"shell\\twinui\\playbackmanager\\audiosrvmonitor.cpp",
         v3);
LABEL_12:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v13);
  return v4;
}

```

## disassembly

```asm
0x1800e9c78  mov     [rsp+arg_8], rbx
0x1800e9c7d  mov     [rsp+arg_10], rsi
0x1800e9c82  push    rdi
0x1800e9c83  sub     rsp, 70h
0x1800e9c87  mov     rax, cs:__security_cookie
0x1800e9c8e  xor     rax, rsp
0x1800e9c91  mov     [rsp+78h+var_18], rax
0x1800e9c96  mov     rsi, rcx
0x1800e9c99  lea     rdx, DatabaseName; "ServicesActive"
0x1800e9ca0  xor     ecx, ecx; lpMachineName
0x1800e9ca2  mov     r8d, 1; dwDesiredAccess
0x1800e9ca8  call    cs:__imp_OpenSCManagerW
0x1800e9caf  nop     dword ptr [rax+rax+00h]
0x1800e9cb4  mov     [rsp+78h+var_40], rax
0x1800e9cb9  test    rax, rax
0x1800e9cbc  jnz     short loc_1800E9CD9
0x1800e9cbe  mov     rcx, [rsp+78h]; this
0x1800e9cc3  lea     r8, aShellTwinuiPla_0; "shell\\twinui\\playbackmanager\\audiosr"...
0x1800e9cca  lea     edx, [rax+14h]; void *
0x1800e9ccd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e9cd2  mov     ebx, eax
0x1800e9cd4  jmp     loc_1800E9DB7
0x1800e9cd9  mov     r8d, 4; dwDesiredAccess
0x1800e9cdf  lea     rdx, ServiceName; "AudioSrv"
0x1800e9ce6  mov     rcx, rax; hSCManager
0x1800e9ce9  call    cs:__imp_OpenServiceW
0x1800e9cf0  nop     dword ptr [rax+rax+00h]
0x1800e9cf5  mov     [rsp+78h+var_48], rax
0x1800e9cfa  mov     rbx, rax
0x1800e9cfd  test    rax, rax
0x1800e9d00  jnz     short loc_1800E9D27
0x1800e9d02  lea     edx, [rax+18h]; void *
0x1800e9d05  mov     rcx, [rsp+78h]; this
0x1800e9d0a  lea     r8, aShellTwinuiPla_0; "shell\\twinui\\playbackmanager\\audiosr"...
0x1800e9d11  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e9d16  lea     rcx, [rsp+78h+var_48]
0x1800e9d1b  mov     ebx, eax
0x1800e9d1d  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800e9d22  jmp     loc_1800E9DB7
0x1800e9d27  xorps   xmm0, xmm0
0x1800e9d2a  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x1800e9d2f  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x1800e9d34  mov     rcx, rbx; hService
0x1800e9d37  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800e9d3c  call    cs:__imp_QueryServiceStatus
0x1800e9d43  nop     dword ptr [rax+rax+00h]
0x1800e9d48  test    eax, eax
0x1800e9d4a  jnz     short loc_1800E9D51
0x1800e9d4c  lea     edx, [rax+1Ch]
0x1800e9d4f  jmp     short loc_1800E9D05
0x1800e9d51  mov     eax, [rsp+78h+ServiceStatus.dwCurrentState]
0x1800e9d55  lea     rdi, [rsi+18h]
0x1800e9d59  mov     rcx, rdi
0x1800e9d5c  mov     [rsi+14h], eax
0x1800e9d5f  xor     edx, edx
0x1800e9d61  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SC_NOTIFICATION_REGISTRATION@@P6AXPEAU1@@Z$1?UnsubscribeServiceChangeNotifications@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SC_NOTIFICATION_REGISTRATION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(_SC_NOTIFICATION_REGISTRATION *)
0x1800e9d66  mov     r9, rsi
0x1800e9d69  mov     qword ptr [rsp+78h+var_58], rdi; unsigned int
0x1800e9d6e  lea     r8, ?AudioSrvStatusChangedCallback@CAudioSrvMonitor@@SAXKPEAX@Z; CAudioSrvMonitor::AudioSrvStatusChangedCallback(ulong,void *)
0x1800e9d75  mov     edx, 2
0x1800e9d7a  mov     rcx, rbx
0x1800e9d7d  call    cs:__imp_SubscribeServiceChangeNotifications
0x1800e9d84  nop     dword ptr [rax+rax+00h]
0x1800e9d89  test    eax, eax
0x1800e9d8b  jz      short loc_1800E9DAB
0x1800e9d8d  mov     rcx, [rsp+78h]; this
0x1800e9d92  lea     r8, aShellTwinuiPla_0; "shell\\twinui\\playbackmanager\\audiosr"...
0x1800e9d99  mov     r9d, eax; char *
0x1800e9d9c  mov     edx, 25h ; '%'; void *
0x1800e9da1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800e9da6  jmp     loc_1800E9D16
0x1800e9dab  lea     rcx, [rsp+78h+var_48]
0x1800e9db0  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800e9db5  xor     ebx, ebx
0x1800e9db7  lea     rcx, [rsp+78h+var_40]
0x1800e9dbc  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800e9dc1  mov     eax, ebx
0x1800e9dc3  mov     rcx, [rsp+78h+var_18]
0x1800e9dc8  xor     rcx, rsp; StackCookie
0x1800e9dcb  call    __security_check_cookie
0x1800e9dd0  lea     r11, [rsp+78h+var_8]
0x1800e9dd5  mov     rbx, [r11+18h]
0x1800e9dd9  mov     rsi, [r11+20h]
0x1800e9ddd  mov     rsp, r11
0x1800e9de0  pop     rdi
0x1800e9de1  retn
```
