# WcmRoutePolicyInitOnceCallback

- ea: `0x180061030`
- end: `0x180061155`
- name: `WcmRoutePolicyInitOnceCallback`
- size: `293`
- prototype: `__int64 __fastcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callees

- `0x1800355b4`
- `0x180061030`
- `0x18006124c`
- `0x1800612c8`
- `0x18007103c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800610c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800610c7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061113`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061113`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180061085`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180061085`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18006103e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18006103e`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800610bd`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800610bd`

## string_xrefs

- `0x180061055`: `onecoreuap\net\wcm\service\base\selection\lib\routepolicydriver.cpp`
- `0x18006109a`: `onecoreuap\net\wcm\service\base\selection\lib\routepolicydriver.cpp`
- `0x1800610d9`: `onecoreuap\net\wcm\service\base\selection\lib\routepolicydriver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WcmRoutePolicyInitOnceCallback(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  SC_HANDLE v3; // rax
  const char *v4; // r9
  unsigned int v5; // ebx
  SC_HANDLE v7; // rax
  const char *v8; // r9
  DWORD LastError; // eax
  HANDLE FileW; // rax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-38h]
  _QWORD v12[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  SC_HANDLE v14; // [rsp+78h] [rbp+20h] BYREF

  v3 = OpenSCManagerW(0, 0, 1u);
  v5 = 0;
  v14 = v3;
  if ( !v3 )
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\selection\\lib\\routepolicydriver.cpp",
      v4);
LABEL_3:
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v14);
    return 0;
  }
  v7 = OpenServiceW(v3, L"RoutePolicy", 0x10u);
  v12[0] = v7;
  if ( !v7 )
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\selection\\lib\\routepolicydriver.cpp",
      v8);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v12);
    goto LABEL_3;
  }
  if ( StartServiceW(v7, 0, 0) || (LastError = GetLastError(), LastError == 1056) )
  {
    FileW = CreateFileW(L"\\\\.\\RoutePolicy", 0, 3u, 0, 3u, 0x40000000u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &WcmRoutePolicy::g_deviceHandle,
      FileW);
    LOBYTE(v5) = (char *)WcmRoutePolicy::g_deviceHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
  }
  else
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\selection\\lib\\routepolicydriver.cpp",
      (const char *)LastError,
      dwCreationDisposition);
  }
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v12);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v14);
  return v5;
}

```

## disassembly

```asm
0x180061030  push    rbx
0x180061032  sub     rsp, 50h
0x180061036  xor     edx, edx; lpDatabaseName
0x180061038  xor     ecx, ecx; lpMachineName
0x18006103a  lea     r8d, [rdx+1]; dwDesiredAccess
0x18006103e  call    cs:__imp_OpenSCManagerW
0x180061044  xor     ebx, ebx
0x180061046  mov     [rsp+58h+arg_18], rax
0x18006104b  test    rax, rax
0x18006104e  jnz     short loc_180061075
0x180061050  mov     rcx, [rsp+58h]; this
0x180061055  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18006105c  lea     edx, [rax+19h]; void *
0x18006105f  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180061064  lea     rcx, [rsp+58h+arg_18]
0x180061069  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18006106e  xor     eax, eax
0x180061070  jmp     loc_18006114F
0x180061075  mov     r8d, 10h; dwDesiredAccess
0x18006107b  lea     rdx, aRoutepolicy_0; "RoutePolicy"
0x180061082  mov     rcx, rax; hSCManager
0x180061085  call    cs:__imp_OpenServiceW
0x18006108b  mov     [rsp+58h+var_18], rax
0x180061090  test    rax, rax
0x180061093  jnz     short loc_1800610B5
0x180061095  mov     rcx, [rsp+58h]; this
0x18006109a  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x1800610a1  lea     edx, [rax+20h]; void *
0x1800610a4  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800610a9  lea     rcx, [rsp+58h+var_18]
0x1800610ae  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800610b3  jmp     short loc_180061064
0x1800610b5  xor     r8d, r8d; lpServiceArgVectors
0x1800610b8  xor     edx, edx; dwNumServiceArgs
0x1800610ba  mov     rcx, rax; hService
0x1800610bd  call    cs:__imp_StartServiceW
0x1800610c3  test    eax, eax
0x1800610c5  jnz     short loc_1800610EF
0x1800610c7  call    cs:__imp_GetLastError
0x1800610cd  cmp     eax, 420h
0x1800610d2  jz      short loc_1800610EF
0x1800610d4  mov     rcx, [rsp+58h]; this
0x1800610d9  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x1800610e0  mov     r9d, eax; char *
0x1800610e3  mov     edx, 2Ah ; '*'; void *
0x1800610e8  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800610ed  jmp     short loc_180061139
0x1800610ef  mov     [rsp+58h+hTemplateFile], rbx; hTemplateFile
0x1800610f4  lea     rcx, aRoutepolicy; "\\\\.\\RoutePolicy"
0x1800610fb  mov     r8d, 3; dwShareMode
0x180061101  mov     [rsp+58h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180061109  xor     r9d, r9d; lpSecurityAttributes
0x18006110c  mov     [rsp+58h+dwCreationDisposition], r8d; dwCreationDisposition
0x180061111  xor     edx, edx; dwDesiredAccess
0x180061113  call    cs:__imp_CreateFileW
0x180061119  mov     rdx, rax
0x18006111c  lea     rcx, ?g_deviceHandle@WcmRoutePolicy@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> WcmRoutePolicy::g_deviceHandle
0x180061123  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180061128  mov     rax, cs:?g_deviceHandle@WcmRoutePolicy@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> WcmRoutePolicy::g_deviceHandle
0x18006112f  dec     rax
0x180061132  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180061136  setbe   bl
0x180061139  lea     rcx, [rsp+58h+var_18]
0x18006113e  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180061143  lea     rcx, [rsp+58h+arg_18]
0x180061148  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18006114d  mov     eax, ebx
0x18006114f  add     rsp, 50h
0x180061153  pop     rbx
0x180061154  retn
```
