# CSdRestoreServiceModule::Register(void)

- ea: `0x18000b868`
- end: `0x18000bcb5`
- name: `?Register@CSdRestoreServiceModule@@QEAAJXZ`
- size: `1101`
- prototype: `__int64 __fastcall(CSdRestoreServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000e800`

## callees

- `0x18000b868`
- `0x18000c170`
- `0x18000d7ec`
- `0x18001586c`
- `0x180015974`
- `0x18001c58c`
- `0x18001fba8`
- `0x180020488`
- `0x18002170a`
- `0x180021740`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000ba2a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000ba2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bb77`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bbff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bb77`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bbff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bc42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bc55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bc42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bc55`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bafe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bbb5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bafe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bbb5`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x18000b9a7`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x18000b9a7`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000b923`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18000b923`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000bc67`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000bc75`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000bc67`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000bc75`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000b9d2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000b9d2`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18000ba6a`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18000ba6a`

## string_xrefs

- `0x18000b899`: `CSdRestoreServiceModule::Register`
- `0x18000bbe8`: `%Systemroot%\System32\SDRSVC.dll`
- `0x18000bbd9`: `ServiceDll`
- `0x18000bb9c`: `System\CurrentControlSet\Services\SDRSVC\Parameters`
- `0x18000b97b`: `%SystemRoot%\System32\svchost.exe -k SDRSVC`

## pseudocode

```c
__int64 __fastcall CSdRestoreServiceModule::Register(CSdRestoreServiceModule *this)
{
  SC_HANDLE ServiceW; // rsi
  unsigned int v2; // r8d
  __int16 v3; // ax
  SC_HANDLE v4; // rdi
  __int64 v5; // rcx
  int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rcx
  int LastFailureAsHRESULT; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // edx
  ATL::CComModule *v13; // rcx
  const struct _GUID *v14; // r8
  int v15; // eax
  bool v16; // sf
  const BYTE *v17; // rcx
  int v18; // r8d
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  unsigned int v24; // ebx
  int StringResource; // [rsp+70h] [rbp-90h] BYREF
  __int16 v27; // [rsp+74h] [rbp-8Ch]
  __int16 v28; // [rsp+76h] [rbp-8Ah]
  HKEY phkResult; // [rsp+A8h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR *Info; // [rsp+B8h] [rbp-48h] BYREF
  LPCWSTR lpDisplayName[2]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Buffer; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v34[206]; // [rsp+D2h] [rbp-2Eh] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&StringResource,
    "CSdRestoreServiceModule::Register",
    0x32Au,
    1u);
  Buffer = 0;
  ServiceW = 0;
  memset_0(v34, 0, 0xC6u);
  lpDisplayName[0] = (LPCWSTR)qword_180028260;
  Info = 0;
  phkResult = 0;
  hKey = 0;
  lpDisplayName[1] = 0;
  StringResource = CBsString::LoadStringResource((CBsString *)lpDisplayName, hInstance, v2);
  v3 = 826;
  if ( StringResource < 0 )
  {
    v4 = 0;
LABEL_3:
    v28 = v3;
    goto LABEL_36;
  }
  v27 = 826;
  v4 = OpenSCManagerW(0, 0, 2u);
  if ( v4 )
  {
    StringResource = 0;
    v27 = 830;
    v6 = 0;
    while ( 1 )
    {
      ServiceW = CreateServiceW(
                   v4,
                   L"SDRSVC",
                   lpDisplayName[0],
                   2u,
                   0x10u,
                   3u,
                   1u,
                   L"%SystemRoot%\\System32\\svchost.exe -k SDRSVC",
                   0,
                   0,
                   L"RPCSS",
                   0,
                   &Password);
      if ( ServiceW )
        break;
      if ( GetLastError() != 1072 )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
        v28 = 857;
        goto LABEL_35;
      }
      StringResource = 0;
      v27 = 857;
      Sleep(0x1388u);
      if ( (unsigned int)++v6 >= 0x3C )
      {
        StringResource = GetLastFailureAsHRESULT(v8);
        v3 = 862;
        goto LABEL_3;
      }
    }
    StringResource = 0;
    v27 = 862;
    if ( !LoadStringW(hInstance, 0x66u, &Buffer, 100) )
    {
      StringResource = GetLastFailureAsHRESULT(v10);
      v3 = 864;
      goto LABEL_3;
    }
    StringResource = 0;
    v27 = 864;
    Info = &Buffer;
    if ( !ChangeServiceConfig2W(ServiceW, 1u, &Info) )
    {
      StringResource = GetLastFailureAsHRESULT(v11);
      v3 = 868;
      goto LABEL_3;
    }
    StringResource = 0;
    v27 = 868;
    StringResource = ATL::CAtlModule::UpdateRegistryFromResourceS((ATL::CAtlModule *)&_Module, 0x65u, 1, 0);
    v3 = 871;
    if ( StringResource < 0 )
      goto LABEL_3;
    v27 = 871;
    StringResource = ATL::CComModule::RegisterServer(v13, v12, v14);
    v3 = 878;
    if ( StringResource < 0 )
      goto LABEL_3;
    v27 = 878;
    v15 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\SvcHost",
            0,
            2u,
            &phkResult);
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    StringResource = v15;
    v16 = v15 < 0;
    v3 = 885;
    if ( v16 )
      goto LABEL_3;
    v27 = 885;
    v17 = L"SDRSVC";
    v18 = 0;
    do
    {
      v19 = -1;
      do
        ++v19;
      while ( *(_WORD *)&v17[2 * v19] );
      v20 = (unsigned int)(v19 + 1);
      v18 += v20;
      v17 += 2 * v20;
    }
    while ( *(_WORD *)v17 );
    v21 = RegSetValueExW(phkResult, L"SDRSVC", 0, 7u, L"SDRSVC", 2 * v18 + 2);
    if ( v21 > 0 )
      v21 = (unsigned __int16)v21 | 0x80070000;
    StringResource = v21;
    v16 = v21 < 0;
    v3 = 900;
    if ( v16 )
      goto LABEL_3;
    v27 = 900;
    v22 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\SDRSVC\\Parameters", 0, 2u, &hKey);
    if ( v22 > 0 )
      v22 = (unsigned __int16)v22 | 0x80070000;
    StringResource = v22;
    v16 = v22 < 0;
    v3 = 909;
    if ( v16 )
      goto LABEL_3;
    v27 = 909;
    v23 = RegSetValueExW(hKey, L"ServiceDll", 0, 2u, L"%Systemroot%\\System32\\SDRSVC.dll", 0x42u);
    if ( v23 > 0 )
      v23 = (unsigned __int16)v23 | 0x80070000;
    StringResource = v23;
    v16 = v23 < 0;
    v3 = 914;
    if ( v16 )
      goto LABEL_3;
    v27 = 914;
  }
  else
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v5);
    v28 = 830;
LABEL_35:
    StringResource = LastFailureAsHRESULT;
  }
LABEL_36:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( ServiceW )
    CloseServiceHandle(ServiceW);
  if ( v4 )
    CloseServiceHandle(v4);
  v24 = StringResource;
  CBsString::_Release((CBsString *)lpDisplayName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&StringResource);
  return v24;
}

```

## disassembly

```asm
0x18000b868  push    rbp
0x18000b86a  push    rbx
0x18000b86b  push    rsi
0x18000b86c  push    rdi
0x18000b86d  push    r13
0x18000b86f  push    r14
0x18000b871  push    r15
0x18000b873  lea     rbp, [rsp-0B0h]
0x18000b87b  sub     rsp, 1B0h
0x18000b882  mov     rax, cs:__security_cookie
0x18000b889  xor     rax, rsp
0x18000b88c  mov     [rbp+0E0h+var_40], rax
0x18000b893  mov     r9d, 1; unsigned __int16
0x18000b899  lea     rdx, aCsdrestoreserv_1; "CSdRestoreServiceModule::Register"
0x18000b8a0  mov     r8d, 32Ah; unsigned __int16
0x18000b8a6  lea     rcx, [rsp+1E0h+var_170]; this
0x18000b8ab  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000b8b0  xor     r14d, r14d
0x18000b8b3  lea     rcx, [rbp+0E0h+var_10E]; void *
0x18000b8b7  xor     edx, edx; Val
0x18000b8b9  mov     [rbp+0E0h+Buffer], r14w
0x18000b8be  mov     r8d, 0C6h; Size
0x18000b8c4  mov     esi, r14d
0x18000b8c7  call    memset_0
0x18000b8cc  mov     rdx, cs:hInstance; hInstance
0x18000b8d3  lea     rax, qword_180028260
0x18000b8da  lea     rcx, [rbp+0E0h+lpDisplayName]; this
0x18000b8de  mov     [rbp+0E0h+lpDisplayName], rax
0x18000b8e2  mov     [rbp+0E0h+Info], r14
0x18000b8e6  mov     [rbp+0E0h+phkResult], r14
0x18000b8ea  mov     [rbp+0E0h+hKey], r14
0x18000b8ee  mov     [rbp+0E0h+var_118], r14
0x18000b8f2  call    ?LoadStringResource@CBsString@@QEAAJPEAUHINSTANCE__@@I@Z; CBsString::LoadStringResource(HINSTANCE__ *,uint)
0x18000b8f7  mov     [rsp+1E0h+var_170], eax
0x18000b8fb  test    eax, eax
0x18000b8fd  mov     eax, 33Ah
0x18000b902  jns     short loc_18000B911
0x18000b904  mov     edi, r14d
0x18000b907  mov     [rsp+1E0h+var_16A], ax
0x18000b90c  jmp     loc_18000BC39
0x18000b911  mov     r13d, 2
0x18000b917  mov     [rsp+1E0h+var_16C], ax
0x18000b91c  mov     r8d, r13d; dwDesiredAccess
0x18000b91f  xor     edx, edx; lpDatabaseName
0x18000b921  xor     ecx, ecx; lpMachineName
0x18000b923  call    cs:__imp_OpenSCManagerW
0x18000b929  mov     rdi, rax
0x18000b92c  test    rax, rax
0x18000b92f  jz      loc_18000BC26
0x18000b935  mov     ecx, 33Eh
0x18000b93a  mov     [rsp+1E0h+var_170], r14d
0x18000b93f  mov     [rsp+1E0h+var_16C], cx
0x18000b944  mov     ebx, r14d
0x18000b947  lea     r15d, [rcx+1Bh]
0x18000b94b  mov     r8, [rbp+0E0h+lpDisplayName]; lpDisplayName
0x18000b94f  lea     rax, Password
0x18000b956  mov     [rsp+1E0h+lpPassword], rax; lpPassword
0x18000b95b  lea     rdx, ?s_wszSvcName@CSdRestoreServiceModule@@0QBGB; "SDRSVC"
0x18000b962  mov     [rsp+1E0h+lpServiceStartName], r14; lpServiceStartName
0x18000b967  lea     rax, ?s_wszSvcDependencies@CSdRestoreServiceModule@@0QBGB; "RPCSS"
0x18000b96e  mov     [rsp+1E0h+lpDependencies], rax; lpDependencies
0x18000b973  mov     r9d, r13d; dwDesiredAccess
0x18000b976  mov     [rsp+1E0h+lpdwTagId], r14; lpdwTagId
0x18000b97b  lea     rax, ?s_wszSvcBinaryPath@CSdRestoreServiceModule@@0QBGB; "%SystemRoot%\\System32\\svchost.exe -k "...
0x18000b982  mov     [rsp+1E0h+lpLoadOrderGroup], r14; lpLoadOrderGroup
0x18000b987  mov     rcx, rdi; hSCManager
0x18000b98a  mov     [rsp+1E0h+lpBinaryPathName], rax; lpBinaryPathName
0x18000b98f  mov     [rsp+1E0h+dwErrorControl], 1; dwErrorControl
0x18000b997  mov     [rsp+1E0h+dwStartType], 3; dwStartType
0x18000b99f  mov     [rsp+1E0h+dwServiceType], 10h; dwServiceType
0x18000b9a7  call    cs:__imp_CreateServiceW
0x18000b9ad  mov     rsi, rax
0x18000b9b0  test    rax, rax
0x18000b9b3  jnz     short loc_18000BA06
0x18000b9b5  call    cs:__imp_GetLastError
0x18000b9bb  cmp     eax, 430h
0x18000b9c0  jnz     short loc_18000B9F6
0x18000b9c2  mov     ecx, 1388h; dwMilliseconds
0x18000b9c7  mov     [rsp+1E0h+var_170], r14d
0x18000b9cc  mov     [rsp+1E0h+var_16C], r15w
0x18000b9d2  call    cs:__imp_Sleep
0x18000b9d8  inc     ebx
0x18000b9da  cmp     ebx, 3Ch ; '<'
0x18000b9dd  jb      loc_18000B94B
0x18000b9e3  call    GetLastFailureAsHRESULT
0x18000b9e8  mov     [rsp+1E0h+var_170], eax
0x18000b9ec  mov     eax, 35Eh
0x18000b9f1  jmp     loc_18000B907
0x18000b9f6  call    GetLastFailureAsHRESULT
0x18000b9fb  mov     [rsp+1E0h+var_16A], r15w
0x18000ba01  jmp     loc_18000BC35
0x18000ba06  mov     rcx, cs:hInstance; hInstance
0x18000ba0d  lea     r8, [rbp+0E0h+Buffer]; lpBuffer
0x18000ba11  mov     r9d, 64h ; 'd'; cchBufferMax
0x18000ba17  mov     [rsp+1E0h+var_170], r14d
0x18000ba1c  mov     eax, 35Eh
0x18000ba21  mov     [rsp+1E0h+var_16C], ax
0x18000ba26  lea     edx, [r9+2]; uID
0x18000ba2a  call    cs:__imp_LoadStringW
0x18000ba30  test    eax, eax
0x18000ba32  jnz     short loc_18000BA47
0x18000ba34  call    GetLastFailureAsHRESULT
0x18000ba39  mov     [rsp+1E0h+var_170], eax
0x18000ba3d  mov     eax, 360h
0x18000ba42  jmp     loc_18000B907
0x18000ba47  mov     eax, 360h
0x18000ba4c  mov     [rsp+1E0h+var_170], r14d
0x18000ba51  mov     [rsp+1E0h+var_16C], ax
0x18000ba56  lea     r8, [rbp+0E0h+Info]; lpInfo
0x18000ba5a  lea     rax, [rbp+0E0h+Buffer]
0x18000ba5e  mov     edx, 1; dwInfoLevel
0x18000ba63  mov     rcx, rsi; hService
0x18000ba66  mov     [rbp+0E0h+Info], rax
0x18000ba6a  call    cs:__imp_ChangeServiceConfig2W
0x18000ba70  test    eax, eax
0x18000ba72  jnz     short loc_18000BA87
0x18000ba74  call    GetLastFailureAsHRESULT
0x18000ba79  mov     [rsp+1E0h+var_170], eax
0x18000ba7d  mov     eax, 364h
0x18000ba82  jmp     loc_18000B907
0x18000ba87  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x18000ba8a  mov     [rsp+1E0h+var_170], r14d
0x18000ba8f  mov     eax, 364h
0x18000ba94  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x18000ba9b  mov     [rsp+1E0h+var_16C], ax
0x18000baa0  lea     edx, [r9+65h]; unsigned int
0x18000baa4  lea     r8d, [r9+1]; int
0x18000baa8  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x18000baad  mov     [rsp+1E0h+var_170], eax
0x18000bab1  test    eax, eax
0x18000bab3  mov     eax, 367h
0x18000bab8  js      loc_18000B907
0x18000babe  mov     [rsp+1E0h+var_16C], ax
0x18000bac3  call    ?RegisterServer@CComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CComModule::RegisterServer(int,_GUID const *)
0x18000bac8  mov     [rsp+1E0h+var_170], eax
0x18000bacc  test    eax, eax
0x18000bace  mov     eax, 36Eh
0x18000bad3  js      loc_18000B907
0x18000bad9  mov     [rsp+1E0h+var_16C], ax
0x18000bade  lea     rdx, ?s_wszSvchostKey@CSdRestoreServiceModule@@0QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000bae5  lea     rax, [rbp+0E0h+phkResult]
0x18000bae9  mov     r15, 0FFFFFFFF80000002h
0x18000baf0  mov     rcx, r15; hKey
0x18000baf3  mov     qword ptr [rsp+1E0h+dwServiceType], rax; phkResult
0x18000baf8  mov     r9d, r13d; samDesired
0x18000bafb  xor     r8d, r8d; ulOptions
0x18000bafe  call    cs:__imp_RegOpenKeyExW
0x18000bb04  mov     ebx, 80070000h
0x18000bb09  test    eax, eax
0x18000bb0b  jle     short loc_18000BB12
0x18000bb0d  movzx   eax, ax
0x18000bb10  or      eax, ebx
0x18000bb12  mov     [rsp+1E0h+var_170], eax
0x18000bb16  test    eax, eax
0x18000bb18  mov     eax, 375h
0x18000bb1d  js      loc_18000B907
0x18000bb23  lea     r9, ?s_wszMultiszSvcName@CSdRestoreServiceModule@@0QBGB; "SDRSVC"
0x18000bb2a  mov     [rsp+1E0h+var_16C], ax
0x18000bb2f  mov     rcx, r9
0x18000bb32  mov     r8d, r14d
0x18000bb35  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bb39  inc     rax
0x18000bb3c  cmp     [rcx+rax*2], r14w
0x18000bb41  jnz     short loc_18000BB39
0x18000bb43  inc     eax
0x18000bb45  add     r8d, eax
0x18000bb48  lea     rcx, [rcx+rax*2]
0x18000bb4c  cmp     [rcx], r14w
0x18000bb50  jnz     short loc_18000BB35
0x18000bb52  mov     rcx, [rbp+0E0h+phkResult]; hKey
0x18000bb56  lea     eax, ds:2[r8*2]
0x18000bb5e  mov     [rsp+1E0h+dwStartType], eax; cbData
0x18000bb62  lea     rdx, ?s_wszSvcName@CSdRestoreServiceModule@@0QBGB; "SDRSVC"
0x18000bb69  mov     qword ptr [rsp+1E0h+dwServiceType], r9; lpData
0x18000bb6e  xor     r8d, r8d; Reserved
0x18000bb71  mov     r9d, 7; dwType
0x18000bb77  call    cs:__imp_RegSetValueExW
0x18000bb7d  test    eax, eax
0x18000bb7f  jle     short loc_18000BB86
0x18000bb81  movzx   eax, ax
0x18000bb84  or      eax, ebx
0x18000bb86  mov     [rsp+1E0h+var_170], eax
0x18000bb8a  test    eax, eax
0x18000bb8c  mov     eax, 384h
0x18000bb91  js      loc_18000B907
0x18000bb97  mov     [rsp+1E0h+var_16C], ax
0x18000bb9c  lea     rdx, ?s_wszServiceDllKey@CSdRestoreServiceModule@@0QBGB; "System\\CurrentControlSet\\Services\\SD"...
0x18000bba3  lea     rax, [rbp+0E0h+hKey]
0x18000bba7  mov     r9d, r13d; samDesired
0x18000bbaa  xor     r8d, r8d; ulOptions
0x18000bbad  mov     qword ptr [rsp+1E0h+dwServiceType], rax; phkResult
0x18000bbb2  mov     rcx, r15; hKey
0x18000bbb5  call    cs:__imp_RegOpenKeyExW
0x18000bbbb  test    eax, eax
0x18000bbbd  jle     short loc_18000BBC4
0x18000bbbf  movzx   eax, ax
0x18000bbc2  or      eax, ebx
0x18000bbc4  mov     [rsp+1E0h+var_170], eax
0x18000bbc8  test    eax, eax
0x18000bbca  mov     eax, 38Dh
0x18000bbcf  js      loc_18000B907
0x18000bbd5  mov     rcx, [rbp+0E0h+hKey]; hKey
0x18000bbd9  lea     rdx, ?s_wszServiceDllValName@CSdRestoreServiceModule@@0QBGB; "ServiceDll"
0x18000bbe0  mov     [rsp+1E0h+var_16C], ax
0x18000bbe5  mov     r9d, r13d; dwType
0x18000bbe8  lea     rax, ?s_wszServiceDllValue@CSdRestoreServiceModule@@0QBGB; "%Systemroot%\\System32\\SDRSVC.dll"
0x18000bbef  mov     [rsp+1E0h+dwStartType], 42h ; 'B'; cbData
0x18000bbf7  xor     r8d, r8d; Reserved
0x18000bbfa  mov     qword ptr [rsp+1E0h+dwServiceType], rax; lpData
0x18000bbff  call    cs:__imp_RegSetValueExW
0x18000bc05  test    eax, eax
0x18000bc07  jle     short loc_18000BC0E
0x18000bc09  movzx   eax, ax
0x18000bc0c  or      eax, ebx
0x18000bc0e  mov     [rsp+1E0h+var_170], eax
0x18000bc12  test    eax, eax
0x18000bc14  mov     eax, 392h
0x18000bc19  js      loc_18000B907
0x18000bc1f  mov     [rsp+1E0h+var_16C], ax
0x18000bc24  jmp     short loc_18000BC39
0x18000bc26  call    GetLastFailureAsHRESULT
0x18000bc2b  mov     ecx, 33Eh
0x18000bc30  mov     [rsp+1E0h+var_16A], cx
0x18000bc35  mov     [rsp+1E0h+var_170], eax
0x18000bc39  mov     rcx, [rbp+0E0h+phkResult]; hKey
0x18000bc3d  test    rcx, rcx
0x18000bc40  jz      short loc_18000BC4C
0x18000bc42  call    cs:__imp_RegCloseKey
0x18000bc48  mov     [rbp+0E0h+phkResult], r14
0x18000bc4c  mov     rcx, [rbp+0E0h+hKey]; hKey
0x18000bc50  test    rcx, rcx
0x18000bc53  jz      short loc_18000BC5F
0x18000bc55  call    cs:__imp_RegCloseKey
0x18000bc5b  mov     [rbp+0E0h+hKey], r14
0x18000bc5f  test    rsi, rsi
0x18000bc62  jz      short loc_18000BC6D
0x18000bc64  mov     rcx, rsi; hSCObject
0x18000bc67  call    cs:__imp_CloseServiceHandle
0x18000bc6d  test    rdi, rdi
0x18000bc70  jz      short loc_18000BC7B
0x18000bc72  mov     rcx, rdi; hSCObject
0x18000bc75  call    cs:__imp_CloseServiceHandle
0x18000bc7b  mov     ebx, [rsp+1E0h+var_170]
0x18000bc7f  lea     rcx, [rbp+0E0h+lpDisplayName]; this
0x18000bc83  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000bc88  lea     rcx, [rsp+1E0h+var_170]; this
0x18000bc8d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000bc92  mov     eax, ebx
0x18000bc94  mov     rcx, [rbp+0E0h+var_40]
0x18000bc9b  xor     rcx, rsp; StackCookie
0x18000bc9e  call    __security_check_cookie
0x18000bca3  add     rsp, 1B0h
0x18000bcaa  pop     r15
0x18000bcac  pop     r14
0x18000bcae  pop     r13
0x18000bcb0  pop     rdi
0x18000bcb1  pop     rsi
0x18000bcb2  pop     rbx
0x18000bcb3  pop     rbp
0x18000bcb4  retn
```
