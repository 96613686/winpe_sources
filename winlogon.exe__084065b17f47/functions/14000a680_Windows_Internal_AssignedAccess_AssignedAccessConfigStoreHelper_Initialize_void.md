# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::Initialize(void)

- ea: `0x14000a680`
- end: `0x14000a798`
- name: `?Initialize@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@AEAA_NXZ`
- size: `280`
- prototype: `bool __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140009900`

## callees

- `0x14000a240`
- `0x14000a680`
- `0x14000b41c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a701`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a701`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000a73c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000a73c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a74f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a74f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a779`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a779`

## string_xrefs

- `0x14000a696`: `SOFTWARE\Microsoft\Windows\AssignedAccessConfiguration`
- `0x14000a6a1`: `AssignedAccessConfiguration`

## pseudocode

```c
char __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::Initialize(
        LPVOID *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  const WCHAR *v5; // rbx
  LSTATUS v6; // eax
  HKEY v7; // rcx
  int v8; // ebx
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  LPCWSTR lpSubKey; // [rsp+68h] [rbp+28h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF

  lpSubKey = 0;
  if ( (int)Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(
              L"SOFTWARE\\Microsoft\\Windows\\AssignedAccessConfiguration",
              (__int64)L"AssignedAccessConfiguration",
              (char *)&lpSubKey,
              a4) < 0 )
  {
    if ( lpSubKey )
      CoTaskMemFree((LPVOID)lpSubKey);
  }
  else
  {
    v5 = lpSubKey;
    if ( lpSubKey )
    {
      if ( *this )
        CoTaskMemFree(*this);
      *this = (LPVOID)v5;
      this[2] = (LPVOID)-1LL;
      this[1] = (LPVOID)-1LL;
      hKey[0] = 0;
      v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, hKey);
      v7 = hKey[0];
      if ( !v6 )
      {
        LODWORD(lpSubKey) = 0;
        Data = 0;
        cbData = 4;
        if ( !RegQueryValueExW(hKey[0], L"Version", 0, (LPDWORD)&lpSubKey, (LPBYTE)&Data, &cbData)
          && (_DWORD)lpSubKey == 4 )
        {
          v8 = Data;
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
LABEL_11:
          *((_DWORD *)this + 6) = v8;
          return 1;
        }
        v7 = hKey[0];
      }
      if ( v7 )
        RegCloseKey(v7);
      v8 = 0;
      goto LABEL_11;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000a680  push    rbp
0x14000a682  push    rbx
0x14000a683  push    rdi
0x14000a684  mov     rbp, rsp
0x14000a687  sub     rsp, 40h
0x14000a68b  mov     rdi, rcx
0x14000a68e  mov     [rbp+lpSubKey], 0
0x14000a696  lea     rcx, aSoftwareMicros_31; "SOFTWARE\\Microsoft\\Windows\\AssignedA"...
0x14000a69d  lea     r8, [rbp+lpSubKey]
0x14000a6a1  lea     rdx, aAssignedaccess; "AssignedAccessConfiguration"
0x14000a6a8  call    ?GetRedirectedPathIfNeeded@PersistentLocationHelper@AssignedAccess@Internal@Windows@@SAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14000a6ad  test    eax, eax
0x14000a6af  js      loc_14000A76E
0x14000a6b5  mov     rbx, [rbp+lpSubKey]
0x14000a6b9  test    rbx, rbx
0x14000a6bc  jz      loc_14000A76A
0x14000a6c2  mov     rcx, [rdi]; pv
0x14000a6c5  test    rcx, rcx
0x14000a6c8  jnz     loc_14000A779
0x14000a6ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000a6d2  mov     [rdi], rbx
0x14000a6d5  mov     [rdi+10h], rax
0x14000a6d9  mov     r9d, 20019h; samDesired
0x14000a6df  mov     [rdi+8], rax
0x14000a6e3  xor     r8d, r8d; ulOptions
0x14000a6e6  lea     rax, [rbp+hKey]
0x14000a6ea  mov     [rbp+hKey], 0
0x14000a6f2  mov     rdx, rbx; lpSubKey
0x14000a6f5  mov     [rsp+40h+phkResult], rax; phkResult
0x14000a6fa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000a701  call    cs:__imp_RegOpenKeyExW
0x14000a707  mov     rcx, [rbp+hKey]; hKey
0x14000a70b  test    eax, eax
0x14000a70d  jnz     short loc_14000A74A
0x14000a70f  mov     dword ptr [rbp+lpSubKey], eax
0x14000a712  lea     r9, [rbp+lpSubKey]; lpType
0x14000a716  mov     [rbp+Data], eax
0x14000a719  lea     rdx, aVersion; "Version"
0x14000a720  lea     rax, [rbp+cbData]
0x14000a724  mov     [rbp+cbData], 4
0x14000a72b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x14000a730  xor     r8d, r8d; lpReserved
0x14000a733  lea     rax, [rbp+Data]
0x14000a737  mov     [rsp+40h+phkResult], rax; lpData
0x14000a73c  call    cs:__imp_RegQueryValueExW
0x14000a742  test    eax, eax
0x14000a744  jz      short loc_14000A784
0x14000a746  mov     rcx, [rbp+hKey]; hKey
0x14000a74a  test    rcx, rcx
0x14000a74d  jz      short loc_14000A755
0x14000a74f  call    cs:__imp_RegCloseKey
0x14000a755  xor     ebx, ebx
0x14000a757  mov     [rdi+18h], ebx
0x14000a75a  mov     al, 1
0x14000a75c  add     rsp, 40h
0x14000a760  pop     rdi
0x14000a761  pop     rbx
0x14000a762  pop     rbp
0x14000a763  retn
0x14000a764  call    cs:__imp_CoTaskMemFree
0x14000a76a  xor     al, al
0x14000a76c  jmp     short loc_14000A75C
0x14000a76e  mov     rcx, [rbp+lpSubKey]; pv
0x14000a772  test    rcx, rcx
0x14000a775  jz      short loc_14000A76A
0x14000a777  jmp     short loc_14000A764
0x14000a779  call    cs:__imp_CoTaskMemFree
0x14000a77f  jmp     loc_14000A6CE
0x14000a784  cmp     dword ptr [rbp+lpSubKey], 4
0x14000a788  jnz     short loc_14000A746
0x14000a78a  mov     ebx, [rbp+Data]
0x14000a78d  lea     rcx, [rbp+hKey]
0x14000a791  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000a796  jmp     short loc_14000A757
```
