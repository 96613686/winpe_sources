# WintrustAddDefaultForUsage

- ea: `0x180037b00`
- end: `0x180037d8e`
- name: `WintrustAddDefaultForUsage`
- size: `654`
- prototype: `BOOL __stdcall(const char *pszUsageOID, CRYPT_PROVIDER_REGDEFUSAGE *psDefUsage)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003f76c`
- `0x180045560`

## callees

- `0x18000bdb0`
- `0x18000cf50`
- `0x18000d1c0`
- `0x180037b00`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037d60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037d60`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180037b9d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180037b9d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180037cf7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180037d36`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180037cf7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180037d36`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037c73`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037cba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037c73`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037cba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037c29`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037c29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037d4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037d4b`

## pseudocode

```c
BOOL __stdcall WintrustAddDefaultForUsage(const char *pszUsageOID, CRYPT_PROVIDER_REGDEFUSAGE *psDefUsage)
{
  GUID *pgActionID; // rcx
  __int64 v5; // rbx
  int v6; // eax
  __int64 v7; // rax
  LSTATUS v8; // eax
  WCHAR *pwszDllName; // rcx
  LSTATUS v10; // edi
  __int64 v11; // rax
  LSTATUS v12; // eax
  char *pwszLoadCallbackDataFunctionName; // rcx
  __int64 v14; // rax
  LSTATUS v15; // eax
  char *pwszFreeCallbackDataFunctionName; // rcx
  _BOOL8 v17; // rax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  _WORD Data[40]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR WideCharStr[64]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[128]; // [rsp+130h] [rbp+30h] BYREF

  hKey = 0;
  dwDisposition = 0;
  if ( !pszUsageOID
    || !psDefUsage
    || psDefUsage->cbStruct <= 0x20
    || (pgActionID = psDefUsage->pgActionID) == 0
    || !(unsigned int)guid2wstr(pgActionID, Data)
    || (v5 = -1, WideCharStr[0] = 0, v6 = MultiByteToWideChar(0, 0, pszUsageOID, -1, WideCharStr, 64), v6 <= 0)
    || (unsigned __int64)(v6 + 56LL) > 0x80 )
  {
    SetLastError(0x57u);
    goto LABEL_23;
  }
  StringCchCopyW(SubKey, 0x80u, L"Software\\Microsoft\\Cryptography\\Providers\\Trust\\Usages");
  StringCchCatW(SubKey, 0x80u, L"\\");
  StringCchCatW(SubKey, 0x80u, WideCharStr);
  if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition) )
  {
LABEL_23:
    LODWORD(v17) = 0;
    return v17;
  }
  v7 = -1;
  do
    ++v7;
  while ( Data[v7] );
  v8 = RegSetValueExW(hKey, L"DefaultId", 0, 1u, (const BYTE *)Data, 2 * v7 + 2);
  pwszDllName = psDefUsage->pwszDllName;
  v10 = v8;
  if ( pwszDllName )
  {
    v11 = -1;
    do
      ++v11;
    while ( pwszDllName[v11] );
    v12 = RegSetValueExW(hKey, L"$DLL", 0, 1u, (const BYTE *)pwszDllName, 2 * v11 + 2);
    pwszLoadCallbackDataFunctionName = psDefUsage->pwszLoadCallbackDataFunctionName;
    v10 |= v12;
    if ( pwszLoadCallbackDataFunctionName )
    {
      v14 = -1;
      do
        ++v14;
      while ( pwszLoadCallbackDataFunctionName[v14] );
      v15 = RegSetValueExA(
              hKey,
              "CallbackAllocFunction",
              0,
              1u,
              (const BYTE *)pwszLoadCallbackDataFunctionName,
              v14 + 1);
      pwszFreeCallbackDataFunctionName = psDefUsage->pwszFreeCallbackDataFunctionName;
      if ( pwszFreeCallbackDataFunctionName )
      {
        do
          ++v5;
        while ( pwszFreeCallbackDataFunctionName[v5] );
        v10 |= v15
             | RegSetValueExA(
                 hKey,
                 "CallbackFreeFunction",
                 0,
                 1u,
                 (const BYTE *)pwszFreeCallbackDataFunctionName,
                 v5 + 1);
      }
      else
      {
        v10 |= v15;
      }
    }
  }
  RegCloseKey(hKey);
  return v10 == 0;
}

```

## disassembly

```asm
0x180037b00  mov     [rsp-8+arg_10], rbx
0x180037b05  push    rbp
0x180037b06  push    rsi
0x180037b07  push    rdi
0x180037b08  push    r14
0x180037b0a  push    r15
0x180037b0c  lea     rbp, [rsp-140h]
0x180037b14  sub     rsp, 240h
0x180037b1b  mov     rax, cs:__security_cookie
0x180037b22  xor     rax, rsp
0x180037b25  mov     [rbp+160h+var_30], rax
0x180037b2c  xor     r15d, r15d
0x180037b2f  mov     rsi, rdx
0x180037b32  mov     [rsp+260h+hKey], r15
0x180037b37  mov     rdi, rcx
0x180037b3a  mov     [rsp+260h+dwDisposition], r15d
0x180037b3f  test    rcx, rcx
0x180037b42  jz      loc_180037D5B
0x180037b48  test    rdx, rdx
0x180037b4b  jz      loc_180037D5B
0x180037b51  cmp     dword ptr [rdx], 20h ; ' '
0x180037b54  jbe     loc_180037D5B
0x180037b5a  mov     rcx, [rdx+8]
0x180037b5e  test    rcx, rcx
0x180037b61  jz      loc_180037D5B
0x180037b67  lea     rdx, [rsp+260h+Data]
0x180037b6c  call    guid2wstr
0x180037b71  test    eax, eax
0x180037b73  jz      loc_180037D5B
0x180037b79  lea     rax, [rbp+160h+WideCharStr]
0x180037b7d  mov     [rsp+260h+cchWideChar], 40h ; '@'; cchWideChar
0x180037b85  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180037b89  mov     [rbp+160h+WideCharStr], r15w
0x180037b8e  mov     r9d, ebx; cbMultiByte
0x180037b91  mov     [rsp+260h+lpWideCharStr], rax; lpWideCharStr
0x180037b96  mov     r8, rdi; lpMultiByteStr
0x180037b99  xor     edx, edx; dwFlags
0x180037b9b  xor     ecx, ecx; CodePage
0x180037b9d  call    cs:__imp_MultiByteToWideChar
0x180037ba3  test    eax, eax
0x180037ba5  jle     loc_180037D5B
0x180037bab  cdqe
0x180037bad  mov     edi, 80h
0x180037bb2  add     rax, 38h ; '8'
0x180037bb6  cmp     rax, rdi
0x180037bb9  ja      loc_180037D5B
0x180037bbf  lea     r8, aSoftwareMicros_14; "Software\\Microsoft\\Cryptography\\Prov"...
0x180037bc6  mov     edx, edi; unsigned __int64
0x180037bc8  lea     rcx, [rbp+160h+SubKey]; unsigned __int16 *
0x180037bcc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037bd1  lea     r8, asc_1800557E4; "\\"
0x180037bd8  mov     edx, edi; unsigned __int64
0x180037bda  lea     rcx, [rbp+160h+SubKey]; unsigned __int16 *
0x180037bde  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180037be3  lea     r8, [rbp+160h+WideCharStr]; unsigned __int16 *
0x180037be7  mov     edx, edi; unsigned __int64
0x180037be9  lea     rcx, [rbp+160h+SubKey]; unsigned __int16 *
0x180037bed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180037bf2  lea     rax, [rsp+260h+dwDisposition]
0x180037bf7  xor     r9d, r9d; lpClass
0x180037bfa  mov     [rsp+260h+lpdwDisposition], rax; lpdwDisposition
0x180037bff  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x180037c03  lea     rax, [rsp+260h+hKey]
0x180037c08  xor     r8d, r8d; Reserved
0x180037c0b  mov     [rsp+260h+phkResult], rax; phkResult
0x180037c10  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037c17  mov     [rsp+260h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180037c1c  mov     [rsp+260h+cchWideChar], 20006h; samDesired
0x180037c24  mov     dword ptr [rsp+260h+lpWideCharStr], r15d; dwOptions
0x180037c29  call    cs:__imp_RegCreateKeyExW
0x180037c2f  test    eax, eax
0x180037c31  jnz     loc_180037D66
0x180037c37  lea     rcx, [rsp+260h+Data]
0x180037c3c  mov     rax, rbx
0x180037c3f  inc     rax
0x180037c42  cmp     [rcx+rax*2], r15w
0x180037c47  jnz     short loc_180037C3F
0x180037c49  mov     rcx, [rsp+260h+hKey]; hKey
0x180037c4e  lea     eax, ds:2[rax*2]
0x180037c55  mov     [rsp+260h+cchWideChar], eax; cbData
0x180037c59  lea     rdx, aDefaultid; "DefaultId"
0x180037c60  lea     rax, [rsp+260h+Data]
0x180037c65  mov     r9d, 1; dwType
0x180037c6b  xor     r8d, r8d; Reserved
0x180037c6e  mov     [rsp+260h+lpWideCharStr], rax; lpData
0x180037c73  call    cs:__imp_RegSetValueExW
0x180037c79  mov     rcx, [rsi+10h]
0x180037c7d  mov     edi, eax
0x180037c7f  test    rcx, rcx
0x180037c82  jz      loc_180037D46
0x180037c88  mov     rax, rbx
0x180037c8b  inc     rax
0x180037c8e  cmp     [rcx+rax*2], r15w
0x180037c93  jnz     short loc_180037C8B
0x180037c95  lea     eax, ds:2[rax*2]
0x180037c9c  mov     r9d, 1; dwType
0x180037ca2  mov     [rsp+260h+cchWideChar], eax; cbData
0x180037ca6  lea     rdx, aDll; "$DLL"
0x180037cad  mov     [rsp+260h+lpWideCharStr], rcx; lpData
0x180037cb2  xor     r8d, r8d; Reserved
0x180037cb5  mov     rcx, [rsp+260h+hKey]; hKey
0x180037cba  call    cs:__imp_RegSetValueExW
0x180037cc0  mov     rcx, [rsi+18h]
0x180037cc4  or      edi, eax
0x180037cc6  test    rcx, rcx
0x180037cc9  jz      short loc_180037D46
0x180037ccb  mov     rax, rbx
0x180037cce  inc     rax
0x180037cd1  cmp     [rcx+rax], r15b
0x180037cd5  jnz     short loc_180037CCE
0x180037cd7  inc     eax
0x180037cd9  lea     rdx, aCallbackallocf; "CallbackAllocFunction"
0x180037ce0  mov     [rsp+260h+cchWideChar], eax; cbData
0x180037ce4  mov     r9d, 1; dwType
0x180037cea  mov     [rsp+260h+lpWideCharStr], rcx; lpData
0x180037cef  xor     r8d, r8d; Reserved
0x180037cf2  mov     rcx, [rsp+260h+hKey]; hKey
0x180037cf7  call    cs:__imp_RegSetValueExA
0x180037cfd  mov     rcx, [rsi+20h]
0x180037d01  mov     r14d, eax
0x180037d04  or      r14d, edi
0x180037d07  test    rcx, rcx
0x180037d0a  jz      short loc_180037D43
0x180037d0c  inc     rbx
0x180037d0f  cmp     [rcx+rbx], r15b
0x180037d13  jnz     short loc_180037D0C
0x180037d15  lea     eax, [rbx+1]
0x180037d18  mov     r9d, 1; dwType
0x180037d1e  mov     [rsp+260h+cchWideChar], eax; cbData
0x180037d22  lea     rdx, aCallbackfreefu; "CallbackFreeFunction"
0x180037d29  mov     [rsp+260h+lpWideCharStr], rcx; lpData
0x180037d2e  xor     r8d, r8d; Reserved
0x180037d31  mov     rcx, [rsp+260h+hKey]; hKey
0x180037d36  call    cs:__imp_RegSetValueExA
0x180037d3c  mov     edi, eax
0x180037d3e  or      edi, r14d
0x180037d41  jmp     short loc_180037D46
0x180037d43  mov     edi, r14d
0x180037d46  mov     rcx, [rsp+260h+hKey]; hKey
0x180037d4b  call    cs:__imp_RegCloseKey
0x180037d51  test    edi, edi
0x180037d53  mov     eax, r15d
0x180037d56  setz    al
0x180037d59  jmp     short loc_180037D68
0x180037d5b  mov     ecx, 57h ; 'W'; dwErrCode
0x180037d60  call    cs:__imp_SetLastError
0x180037d66  xor     eax, eax
0x180037d68  mov     rcx, [rbp+160h+var_30]
0x180037d6f  xor     rcx, rsp; StackCookie
0x180037d72  call    __security_check_cookie
0x180037d77  mov     rbx, [rsp+260h+arg_10]
0x180037d7f  add     rsp, 240h
0x180037d86  pop     r15
0x180037d88  pop     r14
0x180037d8a  pop     rdi
0x180037d8b  pop     rsi
0x180037d8c  pop     rbp
0x180037d8d  retn
```
