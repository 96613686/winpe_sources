# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2::IsGlobalProfileConfiguredInStore(void)

- ea: `0x140009000`
- end: `0x140009134`
- name: `?IsGlobalProfileConfiguredInStore@AssignedAccessConfigStoreV2@AssignedAccess@Internal@Windows@@EEAA_NXZ`
- size: `308`
- prototype: `bool __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2 *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140009000`
- `0x140009300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009116`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009129`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009129`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140009083`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140009083`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400090b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400090b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400090d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400090e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140009121`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400090d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400090e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140009121`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400090c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400090fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400090c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400090fb`

## string_xrefs

- `0x14000900f`: `Configs`

## pseudocode

```c
char __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2::IsGlobalProfileConfiguredInStore(
        Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV2 *this)
{
  __int64 v1; // r8
  HKEY v2; // rdi
  WCHAR *v3; // rbx
  WCHAR *v5; // rcx
  DWORD LastError; // ebx
  LPCWSTR lpSubKey[4]; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+20h] BYREF
  DWORD Type; // [rsp+78h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF

  v1 = *((_QWORD *)this + 1);
  hKey = 0;
  memset(lpSubKey, 0, 24);
  if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              lpSubKey,
              L"%s\\%s",
              v1,
              L"Configs") < 0 )
  {
    v5 = (WCHAR *)lpSubKey[0];
    if ( lpSubKey[0] )
LABEL_13:
      CoTaskMemFree(v5);
  }
  else
  {
    v2 = hKey;
    if ( hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v2);
      SetLastError(LastError);
    }
    v3 = (WCHAR *)lpSubKey[0];
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKey) )
    {
      Type = 0;
      cbData = 0;
      if ( !RegQueryValueExW(hKey, L"GlobalProfileId", 0, &Type, 0, &cbData) )
      {
        if ( v3 )
          CoTaskMemFree(v3);
        if ( hKey )
          RegCloseKey(hKey);
        return 1;
      }
    }
    if ( v3 )
    {
      v5 = v3;
      goto LABEL_13;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x140009000  push    rbp
0x140009002  push    rbx
0x140009003  push    rdi
0x140009004  mov     rbp, rsp
0x140009007  sub     rsp, 50h
0x14000900b  mov     r8, [rcx+8]
0x14000900f  lea     r9, aConfigs; "Configs"
0x140009016  lea     rcx, [rbp+lpSubKey]
0x14000901a  mov     [rbp+hKey], 0
0x140009022  lea     rdx, aSS; "%s\\%s"
0x140009029  mov     [rbp+lpSubKey], 0
0x140009031  mov     [rbp+var_18], 0
0x140009039  mov     [rbp+var_10], 0
0x140009041  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x140009046  test    eax, eax
0x140009048  js      loc_1400090F2
0x14000904e  mov     rdi, [rbp+hKey]
0x140009052  test    rdi, rdi
0x140009055  jnz     loc_140009116
0x14000905b  mov     rbx, [rbp+lpSubKey]
0x14000905f  lea     rax, [rbp+hKey]
0x140009063  mov     rdx, rbx; lpSubKey
0x140009066  mov     [rbp+hKey], 0
0x14000906e  mov     r9d, 20019h; samDesired
0x140009074  mov     [rsp+50h+phkResult], rax; phkResult
0x140009079  xor     r8d, r8d; ulOptions
0x14000907c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140009083  call    cs:__imp_RegOpenKeyExW
0x140009089  test    eax, eax
0x14000908b  jnz     short loc_14000910C
0x14000908d  mov     rcx, [rbp+hKey]; hKey
0x140009091  lea     r9, [rbp+Type]; lpType
0x140009095  mov     [rbp+Type], eax
0x140009098  lea     rdx, aGlobalprofilei; "GlobalProfileId"
0x14000909f  mov     [rbp+cbData], eax
0x1400090a2  xor     r8d, r8d; lpReserved
0x1400090a5  lea     rax, [rbp+cbData]
0x1400090a9  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1400090ae  mov     [rsp+50h+phkResult], 0; lpData
0x1400090b7  call    cs:__imp_RegQueryValueExW
0x1400090bd  test    eax, eax
0x1400090bf  jnz     short loc_14000910C
0x1400090c1  test    rbx, rbx
0x1400090c4  jz      short loc_1400090CF
0x1400090c6  mov     rcx, rbx; pv
0x1400090c9  call    cs:__imp_CoTaskMemFree
0x1400090cf  mov     rcx, [rbp+hKey]; hKey
0x1400090d3  test    rcx, rcx
0x1400090d6  jz      short loc_1400090DE
0x1400090d8  call    cs:__imp_RegCloseKey
0x1400090de  mov     al, 1
0x1400090e0  jmp     short loc_1400090EA
0x1400090e2  call    cs:__imp_RegCloseKey
0x1400090e8  xor     al, al
0x1400090ea  add     rsp, 50h
0x1400090ee  pop     rdi
0x1400090ef  pop     rbx
0x1400090f0  pop     rbp
0x1400090f1  retn
0x1400090f2  mov     rcx, [rbp+lpSubKey]; pv
0x1400090f6  test    rcx, rcx
0x1400090f9  jz      short loc_140009101
0x1400090fb  call    cs:__imp_CoTaskMemFree
0x140009101  mov     rcx, [rbp+hKey]; hKey
0x140009105  test    rcx, rcx
0x140009108  jz      short loc_1400090E8
0x14000910a  jmp     short loc_1400090E2
0x14000910c  test    rbx, rbx
0x14000910f  jz      short loc_140009101
0x140009111  mov     rcx, rbx
0x140009114  jmp     short loc_1400090FB
0x140009116  call    cs:__imp_GetLastError
0x14000911c  mov     rcx, rdi; hKey
0x14000911f  mov     ebx, eax
0x140009121  call    cs:__imp_RegCloseKey
0x140009127  mov     ecx, ebx; dwErrCode
0x140009129  call    cs:__imp_SetLastError
0x14000912f  jmp     loc_14000905B
```
