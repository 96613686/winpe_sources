# InitializeComSecurity(void)

- ea: `0x140001bdc`
- end: `0x140001e6b`
- name: `?InitializeComSecurity@@YAJXZ`
- size: `655`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140002a40`

## callees

- `0x140001bdc`
- `0x140004010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140001db2`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140001db2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140001de5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140001de5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001c77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001cc4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001d02`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001d40`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001c77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001cc4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001d02`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001d40`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001c33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001c33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001d5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001d5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140001e34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140001e51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140001e34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140001e51`
- `iisutil!InitializeSdFromProcessToken` at `0x140001d70`
- `iisutil!InitializeSdFromProcessToken` at `0x140001d70`

## string_xrefs

- `0x140001c19`: `System\CurrentControlSet\Services\w3svc\Parameters`
- `0x140001c6d`: `CoInitializeSecurityParam`
- `0x140001cfb`: `ImpersonationLevel`

## pseudocode

```c
__int64 InitializeComSecurity(void)
{
  DWORD v0; // edi
  DWORD v1; // esi
  DWORD dwCapabilities; // r14d
  HRESULT v3; // ebx
  LPVOID ppv; // [rsp+50h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR pSecDesc; // [rsp+58h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-10h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+30h] BYREF
  DWORD Data; // [rsp+A8h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+48h] BYREF

  v0 = 0;
  hKey = 0;
  pSecDesc = 0;
  hMem = 0;
  ppv = 0;
  v1 = 3;
  dwCapabilities = 64;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\w3svc\\Parameters", 0, 0x20019u, &hKey) )
  {
    Data = 0;
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"CoInitializeSecurityParam", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"AuthenticationLevel", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        v0 = Data;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"ImpersonationLevel", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        v1 = Data;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"AuthenticationCapabilities", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        dwCapabilities = Data;
    }
    RegCloseKey(hKey);
  }
  v3 = InitializeSdFromProcessToken(&pSecDesc, (struct _ACL **)&hMem);
  if ( v3 >= 0 )
  {
    v3 = CoInitializeSecurity(pSecDesc, -1, 0, 0, v0, v1, 0, dwCapabilities, 0);
    if ( v3 >= 0 )
    {
      v3 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &IID_IGlobalOptions, &ppv);
      if ( v3 >= 0 )
        v3 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1, 1);
    }
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( pSecDesc )
  {
    LocalFree(pSecDesc);
    pSecDesc = 0;
  }
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140001bdc  push    rbp
0x140001bde  push    rbx
0x140001bdf  push    rsi
0x140001be0  push    rdi
0x140001be1  push    r14
0x140001be3  mov     rbp, rsp
0x140001be6  sub     rsp, 70h
0x140001bea  xor     edi, edi
0x140001bec  mov     [rbp+hKey], 0
0x140001bf4  lea     rax, [rbp+hKey]
0x140001bf8  mov     [rbp+pSecDesc], 0
0x140001c00  mov     r9d, 20019h; samDesired
0x140001c06  mov     [rbp+hMem], 0
0x140001c0e  xor     r8d, r8d; ulOptions
0x140001c11  mov     [rbp+ppv], 0
0x140001c19  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\w3"...
0x140001c20  mov     [rsp+70h+phkResult], rax; phkResult
0x140001c25  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140001c2c  lea     esi, [rdi+3]
0x140001c2f  lea     r14d, [rdi+40h]
0x140001c33  call    cs:__imp_RegOpenKeyExW
0x140001c3a  nop     dword ptr [rax+rax+00h]
0x140001c3f  test    eax, eax
0x140001c41  jnz     loc_140001D68
0x140001c47  mov     rcx, [rbp+hKey]; hKey
0x140001c4b  lea     rax, [rbp+cbData]
0x140001c4f  mov     [rsp+70h+lpcbData], rax; lpcbData
0x140001c54  lea     ebx, [rdi+4]
0x140001c57  lea     rax, [rbp+Data]
0x140001c5b  mov     [rbp+Data], edi
0x140001c5e  lea     r9, [rbp+Type]; lpType
0x140001c62  mov     [rsp+70h+phkResult], rax; lpData
0x140001c67  xor     r8d, r8d; lpReserved
0x140001c6a  mov     [rbp+Type], edi
0x140001c6d  lea     rdx, ValueName; "CoInitializeSecurityParam"
0x140001c74  mov     [rbp+cbData], ebx
0x140001c77  call    cs:__imp_RegQueryValueExW
0x140001c7e  nop     dword ptr [rax+rax+00h]
0x140001c83  test    eax, eax
0x140001c85  jnz     loc_140001D58
0x140001c8b  cmp     [rbp+Type], ebx
0x140001c8e  jnz     loc_140001D58
0x140001c94  cmp     [rbp+Data], edi
0x140001c97  jz      loc_140001D58
0x140001c9d  mov     rcx, [rbp+hKey]; hKey
0x140001ca1  lea     rax, [rbp+cbData]
0x140001ca5  mov     [rsp+70h+lpcbData], rax; lpcbData
0x140001caa  lea     r9, [rbp+Type]; lpType
0x140001cae  lea     rax, [rbp+Data]
0x140001cb2  mov     [rbp+cbData], ebx
0x140001cb5  xor     r8d, r8d; lpReserved
0x140001cb8  mov     [rsp+70h+phkResult], rax; lpData
0x140001cbd  lea     rdx, aAuthentication; "AuthenticationLevel"
0x140001cc4  call    cs:__imp_RegQueryValueExW
0x140001ccb  nop     dword ptr [rax+rax+00h]
0x140001cd0  test    eax, eax
0x140001cd2  jnz     short loc_140001CDB
0x140001cd4  cmp     [rbp+Type], ebx
0x140001cd7  cmovz   edi, [rbp+Data]
0x140001cdb  mov     rcx, [rbp+hKey]; hKey
0x140001cdf  lea     rax, [rbp+cbData]
0x140001ce3  mov     [rsp+70h+lpcbData], rax; lpcbData
0x140001ce8  lea     r9, [rbp+Type]; lpType
0x140001cec  lea     rax, [rbp+Data]
0x140001cf0  mov     [rbp+cbData], ebx
0x140001cf3  xor     r8d, r8d; lpReserved
0x140001cf6  mov     [rsp+70h+phkResult], rax; lpData
0x140001cfb  lea     rdx, aImpersonationl; "ImpersonationLevel"
0x140001d02  call    cs:__imp_RegQueryValueExW
0x140001d09  nop     dword ptr [rax+rax+00h]
0x140001d0e  test    eax, eax
0x140001d10  jnz     short loc_140001D19
0x140001d12  cmp     [rbp+Type], ebx
0x140001d15  cmovz   esi, [rbp+Data]
0x140001d19  mov     rcx, [rbp+hKey]; hKey
0x140001d1d  lea     rax, [rbp+cbData]
0x140001d21  mov     [rsp+70h+lpcbData], rax; lpcbData
0x140001d26  lea     r9, [rbp+Type]; lpType
0x140001d2a  lea     rax, [rbp+Data]
0x140001d2e  mov     [rbp+cbData], ebx
0x140001d31  xor     r8d, r8d; lpReserved
0x140001d34  mov     [rsp+70h+phkResult], rax; lpData
0x140001d39  lea     rdx, aAuthentication_0; "AuthenticationCapabilities"
0x140001d40  call    cs:__imp_RegQueryValueExW
0x140001d47  nop     dword ptr [rax+rax+00h]
0x140001d4c  test    eax, eax
0x140001d4e  jnz     short loc_140001D58
0x140001d50  cmp     [rbp+Type], ebx
0x140001d53  cmovz   r14d, [rbp+Data]
0x140001d58  mov     rcx, [rbp+hKey]; hKey
0x140001d5c  call    cs:__imp_RegCloseKey
0x140001d63  nop     dword ptr [rax+rax+00h]
0x140001d68  lea     rdx, [rbp+hMem]
0x140001d6c  lea     rcx, [rbp+pSecDesc]
0x140001d70  call    cs:__imp_?InitializeSdFromProcessToken@@YAJPEAPEAXPEAPEAU_ACL@@@Z; InitializeSdFromProcessToken(void * *,_ACL * *)
0x140001d77  nop     dword ptr [rax+rax+00h]
0x140001d7c  mov     ebx, eax
0x140001d7e  test    eax, eax
0x140001d80  js      loc_140001E0E
0x140001d86  mov     rcx, [rbp+pSecDesc]; pSecDesc
0x140001d8a  xor     r9d, r9d; pReserved1
0x140001d8d  mov     [rsp+70h+pReserved3], 0; pReserved3
0x140001d96  xor     r8d, r8d; asAuthSvc
0x140001d99  mov     [rsp+70h+dwCapabilities], r14d; dwCapabilities
0x140001d9e  or      edx, 0FFFFFFFFh; cAuthSvc
0x140001da1  mov     [rsp+70h+pAuthList], 0; pAuthList
0x140001daa  mov     dword ptr [rsp+70h+lpcbData], esi; dwImpLevel
0x140001dae  mov     dword ptr [rsp+70h+phkResult], edi; dwAuthnLevel
0x140001db2  call    cs:__imp_CoInitializeSecurity
0x140001db9  nop     dword ptr [rax+rax+00h]
0x140001dbe  mov     ebx, eax
0x140001dc0  test    eax, eax
0x140001dc2  js      short loc_140001E0E
0x140001dc4  lea     rax, [rbp+ppv]
0x140001dc8  mov     edi, 1
0x140001dcd  mov     r8d, edi; dwClsContext
0x140001dd0  mov     [rsp+70h+phkResult], rax; ppv
0x140001dd5  lea     r9, IID_IGlobalOptions; riid
0x140001ddc  xor     edx, edx; pUnkOuter
0x140001dde  lea     rcx, CLSID_GlobalOptions; rclsid
0x140001de5  call    cs:__imp_CoCreateInstance
0x140001dec  nop     dword ptr [rax+rax+00h]
0x140001df1  mov     ebx, eax
0x140001df3  test    eax, eax
0x140001df5  js      short loc_140001E0E
0x140001df7  mov     rcx, [rbp+ppv]
0x140001dfb  mov     r8d, edi
0x140001dfe  mov     edx, edi
0x140001e00  mov     rax, [rcx]
0x140001e03  mov     rax, [rax+18h]
0x140001e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e0c  mov     ebx, eax
0x140001e0e  mov     rcx, [rbp+ppv]
0x140001e12  test    rcx, rcx
0x140001e15  jz      short loc_140001E2B
0x140001e17  mov     rax, [rcx]
0x140001e1a  mov     rax, [rax+10h]
0x140001e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e23  mov     [rbp+ppv], 0
0x140001e2b  mov     rcx, [rbp+pSecDesc]; hMem
0x140001e2f  test    rcx, rcx
0x140001e32  jz      short loc_140001E48
0x140001e34  call    cs:__imp_LocalFree
0x140001e3b  nop     dword ptr [rax+rax+00h]
0x140001e40  mov     [rbp+pSecDesc], 0
0x140001e48  mov     rcx, [rbp+hMem]; hMem
0x140001e4c  test    rcx, rcx
0x140001e4f  jz      short loc_140001E5D
0x140001e51  call    cs:__imp_LocalFree
0x140001e58  nop     dword ptr [rax+rax+00h]
0x140001e5d  mov     eax, ebx
0x140001e5f  add     rsp, 70h
0x140001e63  pop     r14
0x140001e65  pop     rdi
0x140001e66  pop     rsi
0x140001e67  pop     rbx
0x140001e68  pop     rbp
0x140001e69  retn
```
