# Microsoft::Diagnostics::ServiceStatusFilterDef::IsSatisfiedWorker(void)

- ea: `0x180253664`
- end: `0x18025388b`
- name: `?IsSatisfiedWorker@ServiceStatusFilterDef@Diagnostics@Microsoft@@AEBA?AU?$pair@JVResult@Filters@Diagnostics@Microsoft@@@std@@XZ`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180253fe0`

## callees

- `0x1800a1e24`
- `0x1800bc2e0`
- `0x1800d2b24`
- `0x18012de40`
- `0x1802533a8`
- `0x180253664`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802536c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180253729`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802536c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180253729`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18025370f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18025370f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1802536b0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1802536b0`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1802537e9`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1802537e9`

## string_xrefs

- `0x1802536e9`: `onecore\base\telemetry\utc\service\scenarios\filters\servicestatusfilter.cpp`
- `0x180253799`: `onecore\base\telemetry\utc\service\scenarios\filters\servicestatusfilter.cpp`
- `0x1802537fe`: `onecore\base\telemetry\utc\service\scenarios\filters\servicestatusfilter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::ServiceStatusFilterDef::IsSatisfiedWorker(__int64 a1, __int64 a2)
{
  SC_HANDLE v5; // rbx
  signed int LastError; // eax
  const WCHAR *v7; // rdx
  SC_HANDLE v8; // rax
  DWORD v9; // eax
  char v10; // al
  const char *v11; // r9
  char v12; // cl
  char v13; // al
  unsigned int v14[2]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v15[2]; // [rsp+28h] [rbp-40h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v15[1] = a2;
  if ( !*(_BYTE *)(a1 + 88) && *(_BYTE *)(a1 + 89) )
  {
    *(_QWORD *)a2 = 0;
    return a2;
  }
  v5 = OpenSCManagerW(0, 0, 4u);
  v15[0] = v5;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( !v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\servicestatusfilter.cpp",
      (const char *)(unsigned int)LastError,
      v14[0]);
  v7 = (const WCHAR *)(a1 + 56);
  if ( *(_QWORD *)(a1 + 80) > 7u )
    v7 = *(const WCHAR **)v7;
  v8 = OpenServiceW(v5, v7, 4u);
  *(_QWORD *)v14 = v8;
  if ( !v8 )
  {
    v9 = GetLastError();
    if ( v9 != 1060 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x84,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\servicestatusfilter.cpp",
        (const char *)v9,
        v14[0]);
    v10 = *(_BYTE *)(a1 + 88);
    *(_DWORD *)a2 = 0;
    if ( v10 )
      *(_DWORD *)(a2 + 4) = 0;
    else
      *(_DWORD *)(a2 + 4) = 1;
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v14);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v15);
    return a2;
  }
  if ( *(_BYTE *)(a1 + 88) )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( !QueryServiceStatus(v8, &ServiceStatus) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\servicestatusfilter.cpp",
        v11);
    v12 = ServiceStatus.dwCurrentState == 4;
    v13 = *(_BYTE *)(a1 + 89);
    *(_DWORD *)a2 = 0;
    *(_DWORD *)(a2 + 4) = v13 == v12;
    goto LABEL_14;
  }
  *(_QWORD *)a2 = 0;
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v14);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v15);
  return a2;
}

```

## disassembly

```asm
0x180253664  mov     [rsp+arg_10], rbx
0x180253669  mov     [rsp+arg_18], rsi
0x18025366e  push    rdi
0x18025366f  sub     rsp, 60h
0x180253673  mov     rax, cs:__security_cookie
0x18025367a  xor     rax, rsp
0x18025367d  mov     [rsp+68h+var_10], rax
0x180253682  mov     rdi, rdx
0x180253685  mov     rsi, rcx
0x180253688  mov     [rsp+68h+var_38], rdx
0x18025368d  cmp     byte ptr [rcx+58h], 0
0x180253691  jnz     short loc_1802536A8
0x180253693  cmp     byte ptr [rcx+59h], 0
0x180253697  jz      short loc_1802536A8
0x180253699  mov     qword ptr [rdx], 0
0x1802536a0  mov     rax, rdx
0x1802536a3  jmp     loc_18025386B
0x1802536a8  xor     edx, edx; lpDatabaseName
0x1802536aa  xor     ecx, ecx; lpMachineName
0x1802536ac  lea     r8d, [rdx+4]; dwDesiredAccess
0x1802536b0  call    cs:__imp_OpenSCManagerW
0x1802536b7  nop     dword ptr [rax+rax+00h]
0x1802536bc  mov     rbx, rax
0x1802536bf  mov     [rsp+68h+var_40], rax
0x1802536c4  call    cs:__imp_GetLastError
0x1802536cb  nop     dword ptr [rax+rax+00h]
0x1802536d0  test    eax, eax
0x1802536d2  jle     short loc_1802536DC
0x1802536d4  movzx   eax, ax
0x1802536d7  or      eax, 80070000h
0x1802536dc  mov     rcx, [rsp+68h]; this
0x1802536e1  test    rbx, rbx
0x1802536e4  jnz     short loc_1802536F8
0x1802536e6  mov     r9d, eax; char *
0x1802536e9  lea     r8, aOnecoreBaseTel_130; "onecore\\base\\telemetry\\utc\\service"...
0x1802536f0  lea     edx, [rbx+6Eh]; void *
0x1802536f3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802536f8  lea     rdx, [rsi+38h]
0x1802536fc  cmp     qword ptr [rdx+18h], 7
0x180253701  jbe     short loc_180253706
0x180253703  mov     rdx, [rdx]; lpServiceName
0x180253706  mov     r8d, 4; dwDesiredAccess
0x18025370c  mov     rcx, rbx; hSCManager
0x18025370f  call    cs:__imp_OpenServiceW
0x180253716  nop     dword ptr [rax+rax+00h]
0x18025371b  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x180253720  test    rax, rax
0x180253723  jnz     loc_1802537AA
0x180253729  call    cs:__imp_GetLastError
0x180253730  nop     dword ptr [rax+rax+00h]
0x180253735  cmp     eax, 424h
0x18025373a  jnz     short loc_180253791
0x18025373c  mov     al, [rsi+58h]
0x18025373f  mov     dword ptr [rdi], 0
0x180253745  test    al, al
0x180253747  jz      short loc_18025376D
0x180253749  mov     dword ptr [rdi+4], 0
0x180253750  lea     rcx, [rsp+68h+var_48]
0x180253755  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18025375a  nop
0x18025375b  lea     rcx, [rsp+68h+var_40]
0x180253760  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180253765  mov     rax, rdi
0x180253768  jmp     loc_18025386B
0x18025376d  mov     dword ptr [rdi+4], 1
0x180253774  lea     rcx, [rsp+68h+var_48]
0x180253779  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18025377e  nop
0x18025377f  lea     rcx, [rsp+68h+var_40]
0x180253784  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180253789  mov     rax, rdi
0x18025378c  jmp     loc_18025386B
0x180253791  mov     rcx, [rsp+68h]; this
0x180253796  mov     r9d, eax; char *
0x180253799  lea     r8, aOnecoreBaseTel_130; "onecore\\base\\telemetry\\utc\\service"...
0x1802537a0  mov     edx, 84h; void *
0x1802537a5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1802537aa  cmp     byte ptr [rsi+58h], 0
0x1802537ae  jnz     short loc_1802537D4
0x1802537b0  mov     qword ptr [rdi], 0
0x1802537b7  lea     rcx, [rsp+68h+var_48]
0x1802537bc  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802537c1  nop
0x1802537c2  lea     rcx, [rsp+68h+var_40]
0x1802537c7  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1802537cc  mov     rax, rdi
0x1802537cf  jmp     loc_18025386B
0x1802537d4  xorps   xmm0, xmm0
0x1802537d7  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x1802537dc  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x1802537e1  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x1802537e6  mov     rcx, rax; hService
0x1802537e9  call    cs:__imp_QueryServiceStatus
0x1802537f0  nop     dword ptr [rax+rax+00h]
0x1802537f5  test    eax, eax
0x1802537f7  jnz     short loc_18025380F
0x1802537f9  mov     rcx, [rsp+68h]; this
0x1802537fe  lea     r8, aOnecoreBaseTel_130; "onecore\\base\\telemetry\\utc\\service"...
0x180253805  mov     edx, 91h; void *
0x18025380a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18025380f  cmp     [rsp+68h+ServiceStatus.dwCurrentState], 4
0x180253814  setz    cl
0x180253817  mov     al, [rsi+59h]
0x18025381a  mov     dword ptr [rdi], 0
0x180253820  cmp     al, cl
0x180253822  jnz     short loc_180253845
0x180253824  mov     dword ptr [rdi+4], 1
0x18025382b  lea     rcx, [rsp+68h+var_48]
0x180253830  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180253835  nop
0x180253836  lea     rcx, [rsp+68h+var_40]
0x18025383b  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180253840  mov     rax, rdi
0x180253843  jmp     short loc_18025386B
0x180253845  mov     dword ptr [rdi+4], 0
0x18025384c  lea     rcx, [rsp+68h+var_48]
0x180253851  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180253856  nop
0x180253857  lea     rcx, [rsp+68h+var_40]
0x18025385c  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@$$A6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180253861  mov     rax, rdi
0x180253864  jmp     short loc_18025386B
0x180253866  mov     rax, [rsp+68h+var_38]
0x18025386b  mov     rcx, [rsp+68h+var_10]
0x180253870  xor     rcx, rsp; StackCookie
0x180253873  call    __security_check_cookie
0x180253878  lea     r11, [rsp+68h+var_8]
0x18025387d  mov     rbx, [r11+20h]
0x180253881  mov     rsi, [r11+28h]
0x180253885  mov     rsp, r11
0x180253888  pop     rdi
0x180253889  retn
```
