# CLuaSettingsChecktoid::OnGetStatus(void)

- ea: `0x180003a80`
- end: `0x180003ccf`
- name: `?OnGetStatus@CLuaSettingsChecktoid@@MEAAKXZ`
- size: `591`
- prototype: `__int64 __fastcall(CLuaSettingsChecktoid *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003a80`
- `0x180003cd8`
- `0x180005650`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ba3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ba3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cc4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003b99`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180003b99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003b84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180003b84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c62`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003ade`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003ade`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003b76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003b76`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b21`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b64`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b21`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b64`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180003c04`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180003c04`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180003c13`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180003c13`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003bf2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003c43`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003bf2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003c43`

## pseudocode

```c
__int64 __fastcall CLuaSettingsChecktoid::OnGetStatus(CLuaSettingsChecktoid *this)
{
  const WCHAR *v1; // rdx
  BOOL v2; // ebx
  HANDLE CurrentThread; // rax
  int v5; // edi
  PUCHAR SidSubAuthorityCount; // rax
  DWORD cbData; // [rsp+50h] [rbp-49h] BYREF
  BYTE Data[4]; // [rsp+54h] [rbp-45h] BYREF
  DWORD Type; // [rsp+58h] [rbp-41h] BYREF
  HKEY hKey[2]; // [rsp+60h] [rbp-39h] BYREF
  PSID TokenInformation[12]; // [rsp+70h] [rbp-29h] BYREF

  v1 = (const WCHAR *)*((_QWORD *)this + 1);
  v2 = 0;
  hKey[0] = 0;
  if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 0, 0, 1u, 0, hKey, 0) )
  {
    *(_DWORD *)Data = 0;
    cbData = 4;
    Type = 4;
    if ( !RegQueryValueExW(hKey[0], L"EnableLUA", 0, &Type, Data, &cbData) && Type == 4 )
      v2 = *(_DWORD *)Data == 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    Type = 4;
    if ( !RegQueryValueExW(hKey[0], L"ConsentPromptBehaviorAdmin", 0, &Type, Data, &cbData)
      && !*(_DWORD *)Data
      && Type == 4
      && (unsigned int)CLuaSettingsChecktoid::GetTokenType() == 1 )
    {
      v2 = 1;
    }
    RegCloseKey(hKey[0]);
  }
  if ( v2 )
    return v2;
  hKey[0] = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, (PHANDLE)hKey) )
  {
    GetLastError();
    return v2;
  }
  cbData = 0;
  v5 = 0;
  if ( GetTokenInformation(hKey[0], TokenUser, TokenInformation, 0x58u, &cbData) )
  {
    SidSubAuthorityCount = GetSidSubAuthorityCount(TokenInformation[0]);
    if ( *GetSidSubAuthority(TokenInformation[0], (unsigned int)*SidSubAuthorityCount - 1) == 500 )
      goto LABEL_15;
  }
  else
  {
    GetLastError();
  }
  *(_DWORD *)Data = 0;
  cbData = 0;
  if ( GetTokenInformation(hKey[0], TokenElevationType, &cbData, 4u, (PDWORD)Data) )
  {
    if ( cbData == 1 )
    {
      if ( (unsigned int)RunningAsAdministrator() )
        v5 = 1;
    }
  }
  else
  {
    GetLastError();
  }
LABEL_15:
  CloseHandle(hKey[0]);
  if ( !v5 )
    return v2;
  return 2;
}

```

## disassembly

```asm
0x180003a80  mov     [rsp-8+arg_10], rbx
0x180003a85  push    rbp
0x180003a86  push    rsi
0x180003a87  push    r14
0x180003a89  lea     rbp, [rsp-47h]
0x180003a8e  sub     rsp, 0E0h
0x180003a95  mov     rax, cs:__security_cookie
0x180003a9c  xor     rax, rsp
0x180003a9f  mov     [rbp+57h+var_20], rax
0x180003aa3  mov     rdx, [rcx+8]; lpSubKey
0x180003aa7  lea     rax, [rbp+57h+hKey]
0x180003aab  xor     esi, esi
0x180003aad  mov     r14d, 1
0x180003ab3  mov     [rsp+0F0h+lpdwDisposition], rsi; lpdwDisposition
0x180003ab8  xor     r9d, r9d; lpClass
0x180003abb  mov     [rsp+0F0h+phkResult], rax; phkResult
0x180003ac0  xor     r8d, r8d; Reserved
0x180003ac3  mov     [rsp+0F0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180003ac8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003acf  mov     [rsp+0F0h+samDesired], r14d; samDesired
0x180003ad4  mov     ebx, esi
0x180003ad6  mov     [rsp+0F0h+dwOptions], esi; dwOptions
0x180003ada  mov     [rbp+57h+hKey], rsi
0x180003ade  call    cs:__imp_RegCreateKeyExW
0x180003ae4  test    eax, eax
0x180003ae6  jnz     loc_180003B7C
0x180003aec  mov     rcx, [rbp+57h+hKey]; hKey
0x180003af0  lea     rax, [rbp+57h+cbData]
0x180003af4  mov     qword ptr [rsp+0F0h+samDesired], rax; lpcbData
0x180003af9  lea     r9, [rbp+57h+Type]; lpType
0x180003afd  lea     rax, [rbp+57h+Data]
0x180003b01  mov     dword ptr [rbp+57h+Data], esi
0x180003b04  xor     r8d, r8d; lpReserved
0x180003b07  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x180003b0c  lea     rdx, aEnablelua; "EnableLUA"
0x180003b13  mov     [rbp+57h+cbData], 4
0x180003b1a  mov     [rbp+57h+Type], 4
0x180003b21  call    cs:__imp_RegQueryValueExW
0x180003b27  test    eax, eax
0x180003b29  jz      loc_180003CA6
0x180003b2f  mov     rcx, [rbp+57h+hKey]; hKey
0x180003b33  lea     rax, [rbp+57h+cbData]
0x180003b37  mov     qword ptr [rsp+0F0h+samDesired], rax; lpcbData
0x180003b3c  lea     r9, [rbp+57h+Type]; lpType
0x180003b40  lea     rax, [rbp+57h+Data]
0x180003b44  mov     dword ptr [rbp+57h+Data], esi
0x180003b47  xor     r8d, r8d; lpReserved
0x180003b4a  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x180003b4f  lea     rdx, aConsentpromptb; "ConsentPromptBehaviorAdmin"
0x180003b56  mov     [rbp+57h+cbData], 4
0x180003b5d  mov     [rbp+57h+Type], 4
0x180003b64  call    cs:__imp_RegQueryValueExW
0x180003b6a  test    eax, eax
0x180003b6c  jz      loc_180003C82
0x180003b72  mov     rcx, [rbp+57h+hKey]; hKey
0x180003b76  call    cs:__imp_RegCloseKey
0x180003b7c  test    ebx, ebx
0x180003b7e  jnz     short loc_180003BA9
0x180003b80  mov     [rbp+57h+hKey], rsi
0x180003b84  call    cs:__imp_GetCurrentThread
0x180003b8a  lea     r9, [rbp+57h+hKey]; TokenHandle
0x180003b8e  xor     r8d, r8d; OpenAsSelf
0x180003b91  mov     rcx, rax; ThreadHandle
0x180003b94  mov     edx, 8; DesiredAccess
0x180003b99  call    cs:__imp_OpenThreadToken
0x180003b9f  test    eax, eax
0x180003ba1  jnz     short loc_180003BCB
0x180003ba3  call    cs:__imp_GetLastError
0x180003ba9  mov     eax, ebx
0x180003bab  mov     rcx, [rbp+57h+var_20]
0x180003baf  xor     rcx, rsp; StackCookie
0x180003bb2  call    __security_check_cookie
0x180003bb7  mov     rbx, [rsp+0F0h+arg_10]
0x180003bbf  add     rsp, 0E0h
0x180003bc6  pop     r14
0x180003bc8  pop     rsi
0x180003bc9  pop     rbp
0x180003bca  retn
0x180003bcb  mov     rcx, [rbp+57h+hKey]; TokenHandle
0x180003bcf  lea     rax, [rbp+57h+cbData]
0x180003bd3  mov     [rsp+0F0h+arg_8], rdi
0x180003bdb  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180003bdf  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180003be5  mov     qword ptr [rsp+0F0h+dwOptions], rax; ReturnLength
0x180003bea  mov     edx, r14d; TokenInformationClass
0x180003bed  mov     [rbp+57h+cbData], esi
0x180003bf0  mov     edi, esi
0x180003bf2  call    cs:__imp_GetTokenInformation
0x180003bf8  test    eax, eax
0x180003bfa  jz      loc_180003CC4
0x180003c00  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x180003c04  call    cs:__imp_GetSidSubAuthorityCount
0x180003c0a  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x180003c0e  movzx   edx, byte ptr [rax]
0x180003c11  dec     edx; nSubAuthority
0x180003c13  call    cs:__imp_GetSidSubAuthority
0x180003c19  cmp     dword ptr [rax], 1F4h
0x180003c1f  jz      short loc_180003C5E
0x180003c21  mov     rcx, [rbp+57h+hKey]; TokenHandle
0x180003c25  lea     rax, [rbp+57h+Data]
0x180003c29  mov     r9d, 4; TokenInformationLength
0x180003c2f  mov     qword ptr [rsp+0F0h+dwOptions], rax; ReturnLength
0x180003c34  lea     r8, [rbp+57h+cbData]; TokenInformation
0x180003c38  mov     dword ptr [rbp+57h+Data], esi
0x180003c3b  mov     edx, 12h; TokenInformationClass
0x180003c40  mov     [rbp+57h+cbData], esi
0x180003c43  call    cs:__imp_GetTokenInformation
0x180003c49  test    eax, eax
0x180003c4b  jz      short loc_180003CBC
0x180003c4d  cmp     [rbp+57h+cbData], r14d
0x180003c51  jnz     short loc_180003C5E
0x180003c53  call    RunningAsAdministrator
0x180003c58  test    eax, eax
0x180003c5a  cmovnz  edi, r14d
0x180003c5e  mov     rcx, [rbp+57h+hKey]; hObject
0x180003c62  call    cs:__imp_CloseHandle
0x180003c68  test    edi, edi
0x180003c6a  mov     rdi, [rsp+0F0h+arg_8]
0x180003c72  jz      loc_180003BA9
0x180003c78  mov     eax, 2
0x180003c7d  jmp     loc_180003BAB
0x180003c82  cmp     dword ptr [rbp+57h+Data], esi
0x180003c85  jnz     loc_180003B72
0x180003c8b  cmp     [rbp+57h+Type], 4
0x180003c8f  jnz     loc_180003B72
0x180003c95  call    ?GetTokenType@CLuaSettingsChecktoid@@CAKXZ; CLuaSettingsChecktoid::GetTokenType(void)
0x180003c9a  cmp     eax, r14d
0x180003c9d  cmovz   ebx, r14d
0x180003ca1  jmp     loc_180003B72
0x180003ca6  cmp     [rbp+57h+Type], 4
0x180003caa  jnz     loc_180003B2F
0x180003cb0  cmp     dword ptr [rbp+57h+Data], ebx
0x180003cb3  cmovz   ebx, r14d
0x180003cb7  jmp     loc_180003B2F
0x180003cbc  call    cs:__imp_GetLastError
0x180003cc2  jmp     short loc_180003C5E
0x180003cc4  call    cs:__imp_GetLastError
0x180003cca  jmp     loc_180003C21
```
