# ServiceHelpers::CreateInstallAtShutdownKey(void)

- ea: `0x1800356fc`
- end: `0x180035a53`
- name: `?CreateInstallAtShutdownKey@ServiceHelpers@@SAJXZ`
- size: `855`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800349a8`
- `0x180035a5c`

## callees

- `0x180008e88`
- `0x180011680`
- `0x18001b064`
- `0x1800356fc`
- `0x18003624c`
- `0x18003639c`
- `0x1800364ec`
- `0x180039510`
- `0x18006ea28`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003592e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003592e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035a18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035a18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035a08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035a08`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800359a9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800359a9`

## string_xrefs

- `0x18003593c`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x1800359ba`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x1800359cf`: `USO service created InstallAtShutdownKey volatile registry key`

## pseudocode

```c
// Hidden C++ exception states: #wind=16 #try_helpers=1
__int64 ServiceHelpers::CreateInstallAtShutdownKey(void)
{
  bool IsInstallAtShutdown; // di
  __int64 *System; // rax
  __int64 **v2; // rax
  __int64 *v3; // rcx
  __int64 v4; // rax
  __int64 v5; // r8
  __int64 v6; // rdx
  volatile signed __int32 *v7; // rbx
  volatile signed __int32 *v8; // rbx
  __int64 *v9; // rax
  __int64 **v10; // rax
  __int64 *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdx
  volatile signed __int32 *v15; // rbx
  volatile signed __int32 *v16; // rbx
  const char *v17; // r9
  unsigned int LastError; // ebx
  const WCHAR *v19; // rdx
  unsigned int v20; // eax
  DWORD dwOptions; // [rsp+28h] [rbp-69h]
  __int128 v23; // [rsp+58h] [rbp-39h] BYREF
  const wchar_t *v24; // [rsp+68h] [rbp-29h] BYREF
  __int64 v25; // [rsp+70h] [rbp-21h]
  __int64 v26; // [rsp+78h] [rbp-19h] BYREF
  volatile signed __int32 *v27; // [rsp+80h] [rbp-11h]
  __int64 v28; // [rsp+88h] [rbp-9h] BYREF
  volatile signed __int32 *v29; // [rsp+90h] [rbp-1h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+98h] [rbp+7h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+B0h] [rbp+1Fh] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+27h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+C0h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  IsInstallAtShutdown = ServiceHelpers::IsInstallAtShutdown();
  System = SystemInterface::Service::GetSystem(&v28);
  v2 = (__int64 **)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*System + 32LL))(*System, &v26);
  v3 = *v2;
  v4 = **v2;
  v5 = -1;
  do
    ++v5;
  while ( SystemInterface::Registry::USO_INSTALL_AT_SHUTDOWN[v5] );
  v6 = -1;
  do
    ++v6;
  while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v6] );
  v24 = SystemInterface::Registry::USO_INSTALL_AT_SHUTDOWN;
  v25 = v5;
  *(_QWORD *)&v23 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
  *((_QWORD *)&v23 + 1) = v6;
  (*(void (__fastcall **)(__int64 *, __int128 *, const wchar_t **))(v4 + 72))(v3, &v23, &v24);
  v7 = v27;
  if ( v27 )
  {
    if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  v8 = v29;
  if ( v29 )
  {
    if ( _InterlockedExchangeAdd(v29 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  v9 = SystemInterface::Service::GetSystem(&v26);
  v10 = (__int64 **)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v9 + 32LL))(*v9, &v28);
  v11 = *v10;
  v12 = **v10;
  v13 = -1;
  do
    ++v13;
  while ( SystemInterface::Registry::USO_INSTALL_AT_SHUTDOWN[v13] );
  v14 = -1;
  do
    ++v14;
  while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v14] );
  *(_QWORD *)&v23 = SystemInterface::Registry::USO_INSTALL_AT_SHUTDOWN;
  *((_QWORD *)&v23 + 1) = v13;
  v24 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
  v25 = v14;
  (*(void (__fastcall **)(__int64 *, LPCWSTR *, const wchar_t **, __int128 *))(v12 + 96))(v11, lpSubKey, &v24, &v23);
  v15 = v29;
  if ( v29 )
  {
    if ( _InterlockedExchangeAdd(v29 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  v16 = v27;
  if ( v27 )
  {
    if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;CI;0x3001B;;;AU)", 1u, &SecurityDescriptor, 0) )
  {
    SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    SecurityAttributes.bInheritHandle = 0;
    hKey = 0;
    v19 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v19 = lpSubKey[0];
    v20 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0, 1u, 0x40000u, &SecurityAttributes, &hKey, 0);
    if ( v20 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x510,
                    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
                    (const char *)v20,
                    dwOptions);
    }
    else
    {
      *(_QWORD *)&v23 = L"USO service created InstallAtShutdownKey volatile registry key";
      *((_QWORD *)&v23 + 1) = 62;
      SystemInterface::Log<>(&v23);
      if ( IsInstallAtShutdown )
        ServiceHelpers::MarkInstallAtShutdown();
      else
        ServiceHelpers::UnmarkInstallAtShutdown();
      LastError = 0;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x509,
                  (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
                  v17);
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  std::wstring::~wstring(lpSubKey);
  return LastError;
}

```

## disassembly

```asm
0x1800356fc  mov     rax, rsp
0x1800356ff  mov     [rax+8], rbx
0x180035703  mov     [rax+10h], rsi
0x180035707  mov     [rax+18h], rdi
0x18003570b  mov     [rax+20h], r14
0x18003570f  push    rbp
0x180035710  lea     rbp, [rax-5Fh]
0x180035714  sub     rsp, 0E0h
0x18003571b  mov     rax, cs:__security_cookie
0x180035722  xor     rax, rsp
0x180035725  mov     [rbp+57h+var_8], rax
0x180035729  call    ?IsInstallAtShutdown@ServiceHelpers@@SA_NXZ; ServiceHelpers::IsInstallAtShutdown(void)
0x18003572e  mov     dil, al
0x180035731  lea     rcx, [rbp+57h+var_60]
0x180035735  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18003573a  nop
0x18003573b  mov     rcx, [rax]
0x18003573e  mov     rdx, [rcx]
0x180035741  mov     rax, [rdx+20h]
0x180035745  lea     rdx, [rbp+57h+var_70]
0x180035749  call    _guard_dispatch_icall
0x18003574e  nop
0x18003574f  mov     rcx, [rax]
0x180035752  mov     rax, [rcx]
0x180035755  mov     r10, cs:?USO_INSTALL_AT_SHUTDOWN@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USO_INSTALL_AT_SHUTDOWN
0x18003575c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180035760  mov     r8, rsi
0x180035763  xor     r14d, r14d
0x180035766  inc     r8
0x180035769  cmp     [r10+r8*2], r14w
0x18003576e  jnz     short loc_180035766
0x180035770  mov     r9, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x180035777  mov     rdx, rsi
0x18003577a  inc     rdx
0x18003577d  cmp     [r9+rdx*2], r14w
0x180035782  jnz     short loc_18003577A
0x180035784  mov     [rbp+57h+var_80], r10
0x180035788  mov     [rbp+57h+var_78], r8
0x18003578c  mov     [rbp+57h+var_90], r9
0x180035790  mov     [rbp+57h+var_88], rdx
0x180035794  lea     r8, [rbp+57h+var_80]
0x180035798  lea     rdx, [rbp+57h+var_90]
0x18003579c  mov     rax, [rax+48h]
0x1800357a0  call    _guard_dispatch_icall
0x1800357a5  nop
0x1800357a6  mov     rbx, [rbp+57h+var_68]
0x1800357aa  test    rbx, rbx
0x1800357ad  jz      short loc_1800357E3
0x1800357af  mov     eax, esi
0x1800357b1  lock xadd [rbx+8], eax
0x1800357b6  add     eax, esi
0x1800357b8  jnz     short loc_1800357E3
0x1800357ba  mov     rax, [rbx]
0x1800357bd  mov     rcx, rbx
0x1800357c0  mov     rax, [rax]
0x1800357c3  call    _guard_dispatch_icall
0x1800357c8  mov     eax, esi
0x1800357ca  lock xadd [rbx+0Ch], eax
0x1800357cf  add     eax, esi
0x1800357d1  jnz     short loc_1800357E3
0x1800357d3  mov     rax, [rbx]
0x1800357d6  mov     rcx, rbx
0x1800357d9  mov     rax, [rax+8]
0x1800357dd  call    _guard_dispatch_icall
0x1800357e2  nop
0x1800357e3  mov     rbx, [rbp+57h+var_58]
0x1800357e7  test    rbx, rbx
0x1800357ea  jz      short loc_18003581F
0x1800357ec  mov     eax, esi
0x1800357ee  lock xadd [rbx+8], eax
0x1800357f3  add     eax, esi
0x1800357f5  jnz     short loc_18003581F
0x1800357f7  mov     rax, [rbx]
0x1800357fa  mov     rcx, rbx
0x1800357fd  mov     rax, [rax]
0x180035800  call    _guard_dispatch_icall
0x180035805  mov     eax, esi
0x180035807  lock xadd [rbx+0Ch], eax
0x18003580c  add     eax, esi
0x18003580e  jnz     short loc_18003581F
0x180035810  mov     rax, [rbx]
0x180035813  mov     rcx, rbx
0x180035816  mov     rax, [rax+8]
0x18003581a  call    _guard_dispatch_icall
0x18003581f  lea     rcx, [rbp+57h+var_70]
0x180035823  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180035828  nop
0x180035829  mov     rcx, [rax]
0x18003582c  mov     rax, [rcx]
0x18003582f  lea     rdx, [rbp+57h+var_60]
0x180035833  mov     rax, [rax+20h]
0x180035837  call    _guard_dispatch_icall
0x18003583c  nop
0x18003583d  mov     rcx, [rax]
0x180035840  mov     rax, [rcx]
0x180035843  mov     r10, cs:?USO_INSTALL_AT_SHUTDOWN@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USO_INSTALL_AT_SHUTDOWN
0x18003584a  mov     r8, rsi
0x18003584d  inc     r8
0x180035850  cmp     [r10+r8*2], r14w
0x180035855  jnz     short loc_18003584D
0x180035857  mov     r9, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x18003585e  mov     rdx, rsi
0x180035861  inc     rdx
0x180035864  cmp     [r9+rdx*2], r14w
0x180035869  jnz     short loc_180035861
0x18003586b  mov     [rbp+57h+var_90], r10
0x18003586f  mov     [rbp+57h+var_88], r8
0x180035873  mov     [rbp+57h+var_80], r9
0x180035877  mov     [rbp+57h+var_78], rdx
0x18003587b  lea     r9, [rbp+57h+var_90]
0x18003587f  lea     r8, [rbp+57h+var_80]
0x180035883  lea     rdx, [rbp+57h+lpSubKey]
0x180035887  mov     rax, [rax+60h]
0x18003588b  call    _guard_dispatch_icall
0x180035890  nop
0x180035891  mov     rbx, [rbp+57h+var_58]
0x180035895  test    rbx, rbx
0x180035898  jz      short loc_1800358CE
0x18003589a  mov     eax, esi
0x18003589c  lock xadd [rbx+8], eax
0x1800358a1  add     eax, esi
0x1800358a3  jnz     short loc_1800358CE
0x1800358a5  mov     rax, [rbx]
0x1800358a8  mov     rcx, rbx
0x1800358ab  mov     rax, [rax]
0x1800358ae  call    _guard_dispatch_icall
0x1800358b3  mov     eax, esi
0x1800358b5  lock xadd [rbx+0Ch], eax
0x1800358ba  add     eax, esi
0x1800358bc  jnz     short loc_1800358CE
0x1800358be  mov     rax, [rbx]
0x1800358c1  mov     rcx, rbx
0x1800358c4  mov     rax, [rax+8]
0x1800358c8  call    _guard_dispatch_icall
0x1800358cd  nop
0x1800358ce  mov     rbx, [rbp+57h+var_68]
0x1800358d2  test    rbx, rbx
0x1800358d5  jz      short loc_18003590A
0x1800358d7  mov     eax, esi
0x1800358d9  lock xadd [rbx+8], eax
0x1800358de  add     eax, esi
0x1800358e0  jnz     short loc_18003590A
0x1800358e2  mov     rax, [rbx]
0x1800358e5  mov     rcx, rbx
0x1800358e8  mov     rax, [rax]
0x1800358eb  call    _guard_dispatch_icall
0x1800358f0  mov     eax, esi
0x1800358f2  lock xadd [rbx+0Ch], eax
0x1800358f7  add     eax, esi
0x1800358f9  jnz     short loc_18003590A
0x1800358fb  mov     rax, [rbx]
0x1800358fe  mov     rcx, rbx
0x180035901  mov     rax, [rax+8]
0x180035905  call    _guard_dispatch_icall
0x18003590a  xorps   xmm0, xmm0
0x18003590d  xor     eax, eax
0x18003590f  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x180035913  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x180035917  mov     [rbp+57h+SecurityDescriptor], r14
0x18003591b  xor     r9d, r9d; SecurityDescriptorSize
0x18003591e  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180035922  lea     ebx, [rax+1]
0x180035925  mov     edx, ebx; StringSDRevision
0x180035927  lea     rcx, aDACi0x3001bAu; "D:(A;CI;0x3001B;;;AU)"
0x18003592e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180035934  test    eax, eax
0x180035936  jnz     short loc_180035954
0x180035938  mov     rcx, [rbp+5Fh]; this
0x18003593c  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180035943  mov     edx, 509h; void *
0x180035948  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003594d  mov     ebx, eax
0x18003594f  jmp     loc_180035A0F
0x180035954  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x18003595b  mov     rax, [rbp+57h+SecurityDescriptor]
0x18003595f  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x180035963  mov     [rbp+57h+SecurityAttributes.bInheritHandle], r14d
0x180035967  mov     [rbp+57h+hKey], r14
0x18003596b  lea     rdx, [rbp+57h+lpSubKey]
0x18003596f  cmp     [rbp+57h+var_10], 7
0x180035974  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180035979  mov     [rsp+0E0h+lpdwDisposition], r14; lpdwDisposition
0x18003597e  lea     rax, [rbp+57h+hKey]
0x180035982  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180035987  lea     rax, [rbp+57h+SecurityAttributes]
0x18003598b  mov     [rsp+0E0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180035990  mov     [rsp+0E0h+samDesired], 40000h; samDesired
0x180035998  mov     [rsp+0E0h+dwOptions], ebx; unsigned int
0x18003599c  xor     r9d, r9d; lpClass
0x18003599f  xor     r8d, r8d; Reserved
0x1800359a2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800359a9  call    cs:__imp_RegCreateKeyExW
0x1800359af  test    eax, eax
0x1800359b1  jz      short loc_1800359CF
0x1800359b3  mov     rcx, [rbp+5Fh]; this
0x1800359b7  mov     r9d, eax; char *
0x1800359ba  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x1800359c1  mov     edx, 510h; void *
0x1800359c6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800359cb  mov     ebx, eax
0x1800359cd  jmp     short loc_1800359FF
0x1800359cf  lea     rax, aUsoServiceCrea_0; "USO service created InstallAtShutdownKe"...
0x1800359d6  mov     [rbp+57h+var_90], rax
0x1800359da  mov     [rbp+57h+var_88], 3Eh ; '>'
0x1800359e2  lea     rcx, [rbp+57h+var_90]
0x1800359e6  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x1800359eb  test    dil, dil
0x1800359ee  jz      short loc_1800359F7
0x1800359f0  call    ?MarkInstallAtShutdown@ServiceHelpers@@SAJXZ; ServiceHelpers::MarkInstallAtShutdown(void)
0x1800359f5  jmp     short loc_1800359FC
0x1800359f7  call    ?UnmarkInstallAtShutdown@ServiceHelpers@@SAJXZ; ServiceHelpers::UnmarkInstallAtShutdown(void)
0x1800359fc  mov     ebx, r14d
0x1800359ff  mov     rcx, [rbp+57h+hKey]; hKey
0x180035a03  test    rcx, rcx
0x180035a06  jz      short loc_180035A0F
0x180035a08  call    cs:__imp_RegCloseKey
0x180035a0e  nop
0x180035a0f  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x180035a13  test    rcx, rcx
0x180035a16  jz      short loc_180035A1F
0x180035a18  call    cs:__imp_LocalFree
0x180035a1e  nop
0x180035a1f  lea     rcx, [rbp+57h+lpSubKey]; void *
0x180035a23  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180035a28  mov     eax, ebx
0x180035a2a  mov     rcx, [rbp+57h+var_8]
0x180035a2e  xor     rcx, rsp; StackCookie
0x180035a31  call    __security_check_cookie
0x180035a36  lea     r11, [rsp+0E0h+var_s0]
0x180035a3e  mov     rbx, [r11+10h]
0x180035a42  mov     rsi, [r11+18h]
0x180035a46  mov     rdi, [r11+20h]
0x180035a4a  mov     r14, [r11+28h]
0x180035a4e  mov     rsp, r11
0x180035a51  pop     rbp
0x180035a52  retn
```
