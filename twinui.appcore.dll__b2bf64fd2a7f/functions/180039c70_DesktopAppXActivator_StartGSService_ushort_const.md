# DesktopAppXActivator::StartGSService(ushort const *)

- ea: `0x180039c70`
- end: `0x180039d38`
- name: `?StartGSService@DesktopAppXActivator@@AEAAXPEBG@Z`
- size: `200`
- prototype: `void __fastcall(DesktopAppXActivator *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180006f30`

## callees

- `0x180036900`
- `0x180039c70`
- `0x18003a1a8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180039d13`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180039d13`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180039c87`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180039c87`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180039cf0`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180039cf0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180039cbd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180039cbd`

## string_xrefs

- `0x180039cb3`: `GamingServices`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DesktopAppXActivator::StartGSService(DesktopAppXActivator *this, const unsigned __int16 *a2)
{
  SC_HANDLE v2; // rax
  const char *v3; // r9
  SC_HANDLE v4; // rax
  const char *v5; // r9
  const char *v6; // r9
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  DesktopAppXActivator *v9; // [rsp+30h] [rbp+8h] BYREF
  const unsigned __int16 *v10; // [rsp+38h] [rbp+10h] BYREF

  v10 = a2;
  v9 = this;
  v2 = OpenSCManagerW(0, 0, 1u);
  try
  {
    v9 = (DesktopAppXActivator *)v2;
    if ( !v2 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x18A,
        (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
        v3);
    v4 = OpenServiceW(v2, L"GamingServices", 0x14u);
    v10 = (const unsigned __int16 *)v4;
    if ( !v4 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x18D,
        (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
        v5);
    if ( !StartServiceW(v4, 0, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x18F,
        (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
        v6);
    Sleep(0x1388u);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v10);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v9);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x195,
      (unsigned int)"onecoreuap\\shell\\twinui\\centennial\\lib\\centennialactivation.cpp",
      v7);
  }
}

```

## disassembly

```asm
0x180039c70  mov     [rsp+arg_8], rdx
0x180039c75  mov     [rsp+arg_0], rcx
0x180039c7a  push    rbx
0x180039c7b  sub     rsp, 20h
0x180039c7f  xor     edx, edx; lpDatabaseName
0x180039c81  lea     r8d, [rdx+1]; dwDesiredAccess
0x180039c85  xor     ecx, ecx; lpMachineName
0x180039c87  call    cs:__imp_OpenSCManagerW
0x180039c8d  mov     [rsp+28h+arg_0], rax
0x180039c92  mov     rcx, [rsp+28h]; this
0x180039c97  test    rax, rax
0x180039c9a  jnz     short loc_180039CAD
0x180039c9c  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180039ca3  mov     edx, 18Ah; void *
0x180039ca8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180039cad  mov     r8d, 14h; dwDesiredAccess
0x180039cb3  lea     rdx, ServiceName; "GamingServices"
0x180039cba  mov     rcx, rax; hSCManager
0x180039cbd  call    cs:__imp_OpenServiceW
0x180039cc3  mov     [rsp+28h+arg_8], rax
0x180039cc8  mov     rcx, [rsp+28h]; this
0x180039ccd  test    rax, rax
0x180039cd0  jnz     short loc_180039CE3
0x180039cd2  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180039cd9  mov     edx, 18Dh; void *
0x180039cde  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180039ce3  mov     rbx, [rsp+28h]
0x180039ce8  xor     r8d, r8d; lpServiceArgVectors
0x180039ceb  xor     edx, edx; dwNumServiceArgs
0x180039ced  mov     rcx, rax; hService
0x180039cf0  call    cs:__imp_StartServiceW
0x180039cf6  test    eax, eax
0x180039cf8  jnz     short loc_180039D0E
0x180039cfa  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\twinui\\centennial\\"...
0x180039d01  mov     edx, 18Fh; void *
0x180039d06  mov     rcx, rbx; this
0x180039d09  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180039d0e  mov     ecx, 1388h; dwMilliseconds
0x180039d13  call    cs:__imp_Sleep
0x180039d19  nop
0x180039d1a  lea     rcx, [rsp+28h+arg_8]
0x180039d1f  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180039d24  nop
0x180039d25  lea     rcx, [rsp+28h+arg_0]
0x180039d2a  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180039d2f  nop
0x180039d30  jmp     short $+2
0x180039d32  add     rsp, 20h
0x180039d36  pop     rbx
0x180039d37  retn
```
