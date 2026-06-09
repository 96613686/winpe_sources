# InitializeComSecurity(void)

- ea: `0x140001b54`
- end: `0x140001d9c`
- name: `?InitializeComSecurity@@YAJXZ`
- size: `584`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400027b0`

## callees

- `0x140001b54`
- `0x140004010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140001cfc`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140001cfc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140001d29`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140001d29`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001be9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001c30`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001c68`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001ca0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001be9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001c30`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001c68`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140001ca0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001bab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140001bab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001cb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001cb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140001d72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140001d89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140001d72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140001d89`
- `iisutil!InitializeSdFromProcessToken` at `0x140001cc4`
- `iisutil!InitializeSdFromProcessToken` at `0x140001cc4`

## string_xrefs

- `0x140001b91`: `System\CurrentControlSet\Services\w3svc\Parameters`
- `0x140001bdf`: `CoInitializeSecurityParam`
- `0x140001c61`: `ImpersonationLevel`

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
0x140001b54  push    rbp
0x140001b56  push    rbx
0x140001b57  push    rsi
0x140001b58  push    rdi
0x140001b59  push    r14
0x140001b5b  mov     rbp, rsp
0x140001b5e  sub     rsp, 70h
0x140001b62  xor     edi, edi
0x140001b64  mov     [rbp+hKey], 0
0x140001b6c  lea     rax, [rbp+hKey]
0x140001b70  mov     [rbp+pSecDesc], 0
0x140001b78  mov     r9d, 20019h; samDesired
0x140001b7e  mov     [rbp+hMem], 0
0x140001b86  xor     r8d, r8d; ulOptions
0x140001b89  mov     [rbp+ppv], 0
0x140001b91  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\w3"...
0x140001b98  mov     [rsp+70h+phkResult], rax; phkResult
0x140001b9d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140001ba4  lea     esi, [rdi+3]
0x140001ba7  lea     r14d, [rdi+40h]
0x140001bab  call    cs:__imp_RegOpenKeyExW
0x140001bb1  test    eax, eax
0x140001bb3  jnz     loc_140001CBC
0x140001bb9  mov     rcx, [rbp+hKey]; hKey
0x140001bbd  lea     rax, [rbp+cbData]
0x140001bc1  mov     [rsp+70h+lpcbData], rax; lpcbData
0x140001bc6  lea     ebx, [rdi+4]
0x140001bc9  lea     rax, [rbp+Data]
0x140001bcd  mov     [rbp+Data], edi
0x140001bd0  lea     r9, [rbp+Type]; lpType
0x140001bd4  mov     [rsp+70h+phkResult], rax; lpData
0x140001bd9  xor     r8d, r8d; lpReserved
0x140001bdc  mov     [rbp+Type], edi
0x140001bdf  lea     rdx, ValueName; "CoInitializeSecurityParam"
0x140001be6  mov     [rbp+cbData], ebx
0x140001be9  call    cs:__imp_RegQueryValueExW
0x140001bef  test    eax, eax
0x140001bf1  jnz     loc_140001CB2
0x140001bf7  cmp     [rbp+Type], ebx
0x140001bfa  jnz     loc_140001CB2
0x140001c00  cmp     [rbp+Data], edi
0x140001c03  jz      loc_140001CB2
0x140001c09  mov     rcx, [rbp+hKey]; hKey
0x140001c0d  lea     rax, [rbp+cbData]
0x140001c11  mov     [rsp+70h+lpcbData], rax; lpcbData
0x140001c16  lea     r9, [rbp+Type]; lpType
0x140001c1a  lea     rax, [rbp+Data]
0x140001c1e  mov     [rbp+cbData], ebx
0x140001c21  xor     r8d, r8d; lpReserved
0x140001c24  mov     [rsp+70h+phkResult], rax; lpData
0x140001c29  lea     rdx, aAuthentication; "AuthenticationLevel"
0x140001c30  call    cs:__imp_RegQueryValueExW
0x140001c36  test    eax, eax
0x140001c38  jnz     short loc_140001C41
0x140001c3a  cmp     [rbp+Type], ebx
0x140001c3d  cmovz   edi, [rbp+Data]
0x140001c41  mov     rcx, [rbp+hKey]; hKey
0x140001c45  lea     rax, [rbp+cbData]
0x140001c49  mov     [rsp+70h+lpcbData], rax; lpcbData
0x140001c4e  lea     r9, [rbp+Type]; lpType
0x140001c52  lea     rax, [rbp+Data]
0x140001c56  mov     [rbp+cbData], ebx
0x140001c59  xor     r8d, r8d; lpReserved
0x140001c5c  mov     [rsp+70h+phkResult], rax; lpData
0x140001c61  lea     rdx, aImpersonationl; "ImpersonationLevel"
0x140001c68  call    cs:__imp_RegQueryValueExW
0x140001c6e  test    eax, eax
0x140001c70  jnz     short loc_140001C79
0x140001c72  cmp     [rbp+Type], ebx
0x140001c75  cmovz   esi, [rbp+Data]
0x140001c79  mov     rcx, [rbp+hKey]; hKey
0x140001c7d  lea     rax, [rbp+cbData]
0x140001c81  mov     [rsp+70h+lpcbData], rax; lpcbData
0x140001c86  lea     r9, [rbp+Type]; lpType
0x140001c8a  lea     rax, [rbp+Data]
0x140001c8e  mov     [rbp+cbData], ebx
0x140001c91  xor     r8d, r8d; lpReserved
0x140001c94  mov     [rsp+70h+phkResult], rax; lpData
0x140001c99  lea     rdx, aAuthentication_0; "AuthenticationCapabilities"
0x140001ca0  call    cs:__imp_RegQueryValueExW
0x140001ca6  test    eax, eax
0x140001ca8  jnz     short loc_140001CB2
0x140001caa  cmp     [rbp+Type], ebx
0x140001cad  cmovz   r14d, [rbp+Data]
0x140001cb2  mov     rcx, [rbp+hKey]; hKey
0x140001cb6  call    cs:__imp_RegCloseKey
0x140001cbc  lea     rdx, [rbp+hMem]
0x140001cc0  lea     rcx, [rbp+pSecDesc]
0x140001cc4  call    cs:__imp_?InitializeSdFromProcessToken@@YAJPEAPEAXPEAPEAU_ACL@@@Z; InitializeSdFromProcessToken(void * *,_ACL * *)
0x140001cca  mov     ebx, eax
0x140001ccc  test    eax, eax
0x140001cce  js      short loc_140001D4C
0x140001cd0  mov     rcx, [rbp+pSecDesc]; pSecDesc
0x140001cd4  xor     r9d, r9d; pReserved1
0x140001cd7  mov     [rsp+70h+pReserved3], 0; pReserved3
0x140001ce0  xor     r8d, r8d; asAuthSvc
0x140001ce3  mov     [rsp+70h+dwCapabilities], r14d; dwCapabilities
0x140001ce8  or      edx, 0FFFFFFFFh; cAuthSvc
0x140001ceb  mov     [rsp+70h+pAuthList], 0; pAuthList
0x140001cf4  mov     dword ptr [rsp+70h+lpcbData], esi; dwImpLevel
0x140001cf8  mov     dword ptr [rsp+70h+phkResult], edi; dwAuthnLevel
0x140001cfc  call    cs:__imp_CoInitializeSecurity
0x140001d02  mov     ebx, eax
0x140001d04  test    eax, eax
0x140001d06  js      short loc_140001D4C
0x140001d08  lea     rax, [rbp+ppv]
0x140001d0c  mov     edi, 1
0x140001d11  mov     r8d, edi; dwClsContext
0x140001d14  mov     [rsp+70h+phkResult], rax; ppv
0x140001d19  lea     r9, IID_IGlobalOptions; riid
0x140001d20  xor     edx, edx; pUnkOuter
0x140001d22  lea     rcx, CLSID_GlobalOptions; rclsid
0x140001d29  call    cs:__imp_CoCreateInstance
0x140001d2f  mov     ebx, eax
0x140001d31  test    eax, eax
0x140001d33  js      short loc_140001D4C
0x140001d35  mov     rcx, [rbp+ppv]
0x140001d39  mov     r8d, edi
0x140001d3c  mov     edx, edi
0x140001d3e  mov     rax, [rcx]
0x140001d41  mov     rax, [rax+18h]
0x140001d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001d4a  mov     ebx, eax
0x140001d4c  mov     rcx, [rbp+ppv]
0x140001d50  test    rcx, rcx
0x140001d53  jz      short loc_140001D69
0x140001d55  mov     rax, [rcx]
0x140001d58  mov     rax, [rax+10h]
0x140001d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001d61  mov     [rbp+ppv], 0
0x140001d69  mov     rcx, [rbp+pSecDesc]; hMem
0x140001d6d  test    rcx, rcx
0x140001d70  jz      short loc_140001D80
0x140001d72  call    cs:__imp_LocalFree
0x140001d78  mov     [rbp+pSecDesc], 0
0x140001d80  mov     rcx, [rbp+hMem]; hMem
0x140001d84  test    rcx, rcx
0x140001d87  jz      short loc_140001D8F
0x140001d89  call    cs:__imp_LocalFree
0x140001d8f  mov     eax, ebx
0x140001d91  add     rsp, 70h
0x140001d95  pop     r14
0x140001d97  pop     rdi
0x140001d98  pop     rsi
0x140001d99  pop     rbx
0x140001d9a  pop     rbp
0x140001d9b  retn
```
