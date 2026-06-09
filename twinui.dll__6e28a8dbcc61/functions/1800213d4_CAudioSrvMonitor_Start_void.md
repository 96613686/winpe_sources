# CAudioSrvMonitor::Start(void)

- ea: `0x1800213d4`
- end: `0x180021579`
- name: `?Start@CAudioSrvMonitor@@QEAAJXZ`
- size: `421`
- prototype: `__int64 __fastcall(CAudioSrvMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180021180`

## callees

- `0x18001fbb4`
- `0x1800213d4`
- `0x1800215d0`
- `0x1800ead54`
- `0x1801045d4`
- `0x18013d330`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800214c2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800214cc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180021530`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002153a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800214c2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800214cc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180021530`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002153a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800213fe`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800213fe`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002144f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002144f`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180021477`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180021477`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x1800214b1`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x1800214b1`

## string_xrefs

- `0x1800213f5`: `ServicesActive`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioSrvMonitor::Start(CAudioSrvMonitor *this)
{
  SC_HANDLE v2; // rax
  const char *v3; // r9
  SC_HANDLE v4; // rsi
  SC_HANDLE v6; // rax
  const char *v7; // r9
  SC_HANDLE v8; // rdi
  const char *v9; // r9
  unsigned int v10; // eax
  unsigned int LastError; // ebx
  SC_HANDLE v12; // [rsp+30h] [rbp-68h] BYREF
  SC_HANDLE v13; // [rsp+38h] [rbp-60h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v2 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v4 = v2;
  v13 = v2;
  if ( !v2 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x14,
             (unsigned int)"shell\\twinui\\playbackmanager\\audiosrvmonitor.cpp",
             v3);
  v6 = OpenServiceW(v2, L"AudioSrv", 4u);
  v8 = v6;
  v12 = v6;
  if ( v6 )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( QueryServiceStatus(v6, &ServiceStatus) )
    {
      *((_DWORD *)this + 5) = ServiceStatus.dwCurrentState;
      wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&void UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(
        (char *)this + 24,
        0);
      v10 = SubscribeServiceChangeNotifications(v8, 2, CAudioSrvMonitor::AudioSrvStatusChangedCallback, this);
      if ( !v10 )
      {
        CloseServiceHandle(v8);
        CloseServiceHandle(v4);
        return 0;
      }
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x25,
                    (unsigned int)"shell\\twinui\\playbackmanager\\audiosrvmonitor.cpp",
                    (const char *)v10,
                    (_DWORD)this + 24);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v12);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1C,
                    (unsigned int)"shell\\twinui\\playbackmanager\\audiosrvmonitor.cpp",
                    v9);
      CloseServiceHandle(v8);
      CloseServiceHandle(v4);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x18,
                  (unsigned int)"shell\\twinui\\playbackmanager\\audiosrvmonitor.cpp",
                  v7);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v12);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v13);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800213d4  push    rbx
0x1800213d6  push    rbp
0x1800213d7  push    rsi
0x1800213d8  push    rdi
0x1800213d9  sub     rsp, 78h
0x1800213dd  mov     rax, cs:__security_cookie
0x1800213e4  xor     rax, rsp
0x1800213e7  mov     [rsp+98h+var_38], rax
0x1800213ec  mov     rbp, rcx
0x1800213ef  mov     r8d, 1; dwDesiredAccess
0x1800213f5  lea     rdx, DatabaseName; "ServicesActive"
0x1800213fc  xor     ecx, ecx; lpMachineName
0x1800213fe  call    cs:__imp_OpenSCManagerW
0x180021404  mov     rsi, rax
0x180021407  mov     [rsp+98h+var_60], rax
0x18002140c  test    rax, rax
0x18002140f  jnz     short loc_18002143F
0x180021411  mov     rcx, [rsp+98h]; this
0x180021419  lea     r8, aShellTwinuiPla_1; "shell\\twinui\\playbackmanager\\audiosr"...
0x180021420  lea     edx, [rax+14h]; void *
0x180021423  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021428  nop
0x180021429  mov     rcx, [rsp+98h+var_38]
0x18002142e  xor     rcx, rsp; StackCookie
0x180021431  call    __security_check_cookie
0x180021436  add     rsp, 78h
0x18002143a  pop     rdi
0x18002143b  pop     rsi
0x18002143c  pop     rbp
0x18002143d  pop     rbx
0x18002143e  retn
0x18002143f  mov     r8d, 4; dwDesiredAccess
0x180021445  lea     rdx, ServiceName; "AudioSrv"
0x18002144c  mov     rcx, rsi; hSCManager
0x18002144f  call    cs:__imp_OpenServiceW
0x180021455  mov     rdi, rax
0x180021458  mov     [rsp+98h+var_68], rax
0x18002145d  test    rax, rax
0x180021460  jz      short loc_1800214DA
0x180021462  xorps   xmm0, xmm0
0x180021465  movups  xmmword ptr [rsp+98h+ServiceStatus.dwServiceType], xmm0
0x18002146a  movups  xmmword ptr [rsp+98h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002146f  lea     rdx, [rsp+98h+ServiceStatus]; lpServiceStatus
0x180021474  mov     rcx, rax; hService
0x180021477  call    cs:__imp_QueryServiceStatus
0x18002147d  test    eax, eax
0x18002147f  jz      loc_180021512
0x180021485  mov     eax, [rsp+98h+ServiceStatus.dwCurrentState]
0x180021489  mov     [rbp+14h], eax
0x18002148c  lea     rbx, [rbp+18h]
0x180021490  xor     edx, edx
0x180021492  mov     rcx, rbx
0x180021495  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SC_NOTIFICATION_REGISTRATION@@P6AXPEAU1@@Z$1?UnsubscribeServiceChangeNotifications@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SC_NOTIFICATION_REGISTRATION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(_SC_NOTIFICATION_REGISTRATION *)
0x18002149a  mov     qword ptr [rsp+98h+var_78], rbx; unsigned int
0x18002149f  mov     r9, rbp
0x1800214a2  lea     r8, ?AudioSrvStatusChangedCallback@CAudioSrvMonitor@@SAXKPEAX@Z; CAudioSrvMonitor::AudioSrvStatusChangedCallback(ulong,void *)
0x1800214a9  mov     edx, 2
0x1800214ae  mov     rcx, rdi
0x1800214b1  call    cs:__imp_SubscribeServiceChangeNotifications
0x1800214b7  test    eax, eax
0x1800214b9  jnz     loc_180021543
0x1800214bf  mov     rcx, rdi; hSCObject
0x1800214c2  call    cs:__imp_CloseServiceHandle
0x1800214c8  nop
0x1800214c9  mov     rcx, rsi; hSCObject
0x1800214cc  call    cs:__imp_CloseServiceHandle
0x1800214d2  nop
0x1800214d3  xor     eax, eax
0x1800214d5  jmp     loc_180021429
0x1800214da  mov     rcx, [rsp+98h]; this
0x1800214e2  lea     r8, aShellTwinuiPla_1; "shell\\twinui\\playbackmanager\\audiosr"...
0x1800214e9  mov     edx, 18h; void *
0x1800214ee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800214f3  mov     ebx, eax
0x1800214f5  lea     rcx, [rsp+98h+var_68]
0x1800214fa  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800214ff  nop
0x180021500  lea     rcx, [rsp+98h+var_60]
0x180021505  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18002150a  nop
0x18002150b  mov     eax, ebx
0x18002150d  jmp     loc_180021429
0x180021512  mov     rcx, [rsp+98h]; this
0x18002151a  lea     r8, aShellTwinuiPla_1; "shell\\twinui\\playbackmanager\\audiosr"...
0x180021521  mov     edx, 1Ch; void *
0x180021526  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002152b  mov     ebx, eax
0x18002152d  mov     rcx, rdi; hSCObject
0x180021530  call    cs:__imp_CloseServiceHandle
0x180021536  nop
0x180021537  mov     rcx, rsi; hSCObject
0x18002153a  call    cs:__imp_CloseServiceHandle
0x180021540  nop
0x180021541  jmp     short loc_18002150B
0x180021543  mov     rcx, [rsp+98h]; this
0x18002154b  mov     r9d, eax; char *
0x18002154e  lea     r8, aShellTwinuiPla_1; "shell\\twinui\\playbackmanager\\audiosr"...
0x180021555  mov     edx, 25h ; '%'; void *
0x18002155a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002155f  mov     ebx, eax
0x180021561  lea     rcx, [rsp+98h+var_68]
0x180021566  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18002156b  nop
0x18002156c  lea     rcx, [rsp+98h+var_60]
0x180021571  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180021576  nop
0x180021577  jmp     short loc_18002150B
```
