# IsTimeZoneAutoUpdateEnabled

- ea: `0x18000c3c0`
- end: `0x18000c4ce`
- name: `IsTimeZoneAutoUpdateEnabled`
- size: `270`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000bf20`

## callees

- `0x1800045d4`
- `0x18000883c`
- `0x18000c3c0`
- `0x18001b150`
- `0x18001b210`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000c3ee`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000c3ee`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000c42e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000c42e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000c480`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18000c480`

## string_xrefs

- `0x18000c424`: `tzautoupdate`
- `0x18000c406`: `onecore\base\win32\winnls\tzautoupdate\api.cpp`
- `0x18000c44b`: `onecore\base\win32\winnls\tzautoupdate\api.cpp`

## pseudocode

```c
__int64 __fastcall IsTimeZoneAutoUpdateEnabled(_DWORD *a1)
{
  SC_HANDLE v2; // rax
  const char *v3; // r9
  unsigned int LastError; // ebx
  SC_HANDLE v5; // rax
  const char *v6; // r9
  __int64 v7; // rdx
  DWORD pcbBytesNeeded; // [rsp+20h] [rbp-2038h] BYREF
  SC_HANDLE v10; // [rsp+28h] [rbp-2030h] BYREF
  SC_HANDLE v11[2]; // [rsp+30h] [rbp-2028h] BYREF
  _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+40h] [rbp-2018h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2058h] [rbp+0h]

  v2 = OpenSCManagerW(0, 0, 0x80000000);
  v11[0] = v2;
  if ( v2 )
  {
    v5 = OpenServiceW(v2, L"tzautoupdate", 1u);
    v10 = v5;
    if ( v5 )
    {
      pcbBytesNeeded = 0;
      if ( QueryServiceConfigW(v5, &ServiceConfig, 0x2000u, &pcbBytesNeeded) )
      {
        *a1 = ServiceConfig.dwStartType != 4;
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v10);
        LastError = 0;
        goto LABEL_9;
      }
      v7 = 328;
    }
    else
    {
      v7 = 323;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v7,
                  (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\api.cpp",
                  v6);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v10);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x140,
                  (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\api.cpp",
                  v3);
  }
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v11);
  return LastError;
}

```

## disassembly

```asm
0x18000c3c0  push    rbx
0x18000c3c2  mov     eax, 2050h
0x18000c3c7  call    _alloca_probe
0x18000c3cc  sub     rsp, rax
0x18000c3cf  mov     rax, cs:__security_cookie
0x18000c3d6  xor     rax, rsp
0x18000c3d9  mov     [rsp+2058h+var_18], rax
0x18000c3e1  mov     rbx, rcx
0x18000c3e4  xor     edx, edx; lpDatabaseName
0x18000c3e6  xor     ecx, ecx; lpMachineName
0x18000c3e8  mov     r8d, 80000000h; dwDesiredAccess
0x18000c3ee  call    cs:__imp_OpenSCManagerW
0x18000c3f4  mov     [rsp+2058h+var_2028], rax
0x18000c3f9  test    rax, rax
0x18000c3fc  jnz     short loc_18000C41E
0x18000c3fe  mov     rcx, [rsp+2058h]; this
0x18000c406  lea     r8, aOnecoreBaseWin_3; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000c40d  mov     edx, 140h; void *
0x18000c412  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c417  mov     ebx, eax
0x18000c419  jmp     loc_18000C4A9
0x18000c41e  mov     r8d, 1; dwDesiredAccess
0x18000c424  lea     rdx, ServiceName; "tzautoupdate"
0x18000c42b  mov     rcx, rax; hSCManager
0x18000c42e  call    cs:__imp_OpenServiceW
0x18000c434  mov     [rsp+2058h+var_2030], rax
0x18000c439  test    rax, rax
0x18000c43c  jnz     short loc_18000C465
0x18000c43e  mov     edx, 143h; void *
0x18000c443  mov     rcx, [rsp+2058h]; this
0x18000c44b  lea     r8, aOnecoreBaseWin_3; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000c452  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c457  lea     rcx, [rsp+2058h+var_2030]
0x18000c45c  mov     ebx, eax
0x18000c45e  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000c463  jmp     short loc_18000C4A9
0x18000c465  lea     r9, [rsp+2058h+pcbBytesNeeded]; pcbBytesNeeded
0x18000c46a  mov     [rsp+2058h+pcbBytesNeeded], 0
0x18000c472  mov     r8d, 2000h; cbBufSize
0x18000c478  lea     rdx, [rsp+2058h+ServiceConfig]; lpServiceConfig
0x18000c47d  mov     rcx, rax; hService
0x18000c480  call    cs:__imp_QueryServiceConfigW
0x18000c486  test    eax, eax
0x18000c488  jnz     short loc_18000C491
0x18000c48a  mov     edx, 148h
0x18000c48f  jmp     short loc_18000C443
0x18000c491  xor     eax, eax
0x18000c493  lea     rcx, [rsp+2058h+var_2030]
0x18000c498  cmp     [rsp+2058h+ServiceConfig.dwStartType], 4
0x18000c49d  setnz   al
0x18000c4a0  mov     [rbx], eax
0x18000c4a2  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000c4a7  xor     ebx, ebx
0x18000c4a9  lea     rcx, [rsp+2058h+var_2028]
0x18000c4ae  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18000c4b3  mov     eax, ebx
0x18000c4b5  mov     rcx, [rsp+2058h+var_18]
0x18000c4bd  xor     rcx, rsp; StackCookie
0x18000c4c0  call    __security_check_cookie
0x18000c4c5  add     rsp, 2050h
0x18000c4cc  pop     rbx
0x18000c4cd  retn
```
