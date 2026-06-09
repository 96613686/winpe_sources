# StpGetHKeyFromToken(void *,HKEY__ * *)

- ea: `0x1800986bc`
- end: `0x1800987dd`
- name: `?StpGetHKeyFromToken@@YAKPEAXPEAPEAUHKEY__@@@Z`
- size: `289`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, HKEY *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180201508`
- `0x180201c0c`

## callees

- `0x18000c5a0`
- `0x18002f450`
- `0x1800986bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009873a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009873a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098766`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009879e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009879e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180098701`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009875c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180098701`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009875c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800987c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800987c2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180098777`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180098777`

## pseudocode

```c
__int64 __fastcall StpGetHKeyFromToken(HANDLE TokenHandle, HKEY *a2)
{
  DWORD v4; // ebx
  DWORD LastError; // eax
  PSID *v6; // rdi
  HKEY phkResult; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+78h] [rbp+38h] BYREF

  TokenInformationLength = 0;
  StringSid = 0;
  phkResult = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v4 = 1008;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError == 122 || !LastError )
    {
      v6 = (PSID *)AllocWLMem(TokenInformationLength);
      if ( v6 )
      {
        if ( GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &TokenInformationLength)
          && ConvertSidToStringSidW(*v6, &StringSid) )
        {
          v4 = RegOpenKeyExW(HKEY_USERS, StringSid, 0, 0xF003Fu, &phkResult);
          if ( !v4 )
            *a2 = phkResult;
        }
        else
        {
          v4 = GetLastError();
        }
        FreeWLMem(v6);
      }
      else
      {
        v4 = GetLastError();
      }
    }
  }
  if ( StringSid )
    LocalFree(StringSid);
  return v4;
}

```

## disassembly

```asm
0x1800986bc  mov     [rsp-18h+arg_0], rbx
0x1800986c1  mov     [rsp-18h+arg_8], rsi
0x1800986c6  push    rbp
0x1800986c7  push    rdi
0x1800986c8  push    r14
0x1800986ca  mov     rbp, rsp
0x1800986cd  sub     rsp, 40h
0x1800986d1  xor     r9d, r9d; TokenInformationLength
0x1800986d4  mov     [rbp+TokenInformationLength], 0
0x1800986db  mov     r14, rdx
0x1800986de  mov     [rbp+StringSid], 0
0x1800986e6  lea     rax, [rbp+TokenInformationLength]
0x1800986ea  mov     [rbp+phkResult], 0
0x1800986f2  xor     r8d, r8d; TokenInformation
0x1800986f5  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800986fa  lea     edx, [r9+1]; TokenInformationClass
0x1800986fe  mov     rsi, rcx
0x180098701  call    cs:__imp_GetTokenInformation
0x180098707  test    eax, eax
0x180098709  jz      short loc_180098715
0x18009870b  mov     ebx, 3F0h
0x180098710  jmp     loc_1800987B9
0x180098715  call    cs:__imp_GetLastError
0x18009871b  mov     ebx, eax
0x18009871d  cmp     eax, 7Ah ; 'z'
0x180098720  jz      short loc_18009872A
0x180098722  test    eax, eax
0x180098724  jnz     loc_1800987B9
0x18009872a  mov     ecx, [rbp+TokenInformationLength]; dwBytes
0x18009872d  call    AllocWLMem
0x180098732  mov     rdi, rax
0x180098735  test    rax, rax
0x180098738  jnz     short loc_180098744
0x18009873a  call    cs:__imp_GetLastError
0x180098740  mov     ebx, eax
0x180098742  jmp     short loc_1800987B9
0x180098744  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180098748  lea     rax, [rbp+TokenInformationLength]
0x18009874c  mov     r8, rdi; TokenInformation
0x18009874f  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180098754  mov     edx, 1; TokenInformationClass
0x180098759  mov     rcx, rsi; TokenHandle
0x18009875c  call    cs:__imp_GetTokenInformation
0x180098762  test    eax, eax
0x180098764  jnz     short loc_180098770
0x180098766  call    cs:__imp_GetLastError
0x18009876c  mov     ebx, eax
0x18009876e  jmp     short loc_1800987B1
0x180098770  mov     rcx, [rdi]; Sid
0x180098773  lea     rdx, [rbp+StringSid]; StringSid
0x180098777  call    cs:__imp_ConvertSidToStringSidW
0x18009877d  test    eax, eax
0x18009877f  jz      short loc_180098766
0x180098781  mov     rdx, [rbp+StringSid]; lpSubKey
0x180098785  lea     rax, [rbp+phkResult]
0x180098789  mov     r9d, 0F003Fh; samDesired
0x18009878f  mov     [rsp+40h+ReturnLength], rax; phkResult
0x180098794  xor     r8d, r8d; ulOptions
0x180098797  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18009879e  call    cs:__imp_RegOpenKeyExW
0x1800987a4  mov     ebx, eax
0x1800987a6  test    eax, eax
0x1800987a8  jnz     short loc_1800987B1
0x1800987aa  mov     rax, [rbp+phkResult]
0x1800987ae  mov     [r14], rax
0x1800987b1  mov     rcx, rdi
0x1800987b4  call    FreeWLMem
0x1800987b9  mov     rcx, [rbp+StringSid]; hMem
0x1800987bd  test    rcx, rcx
0x1800987c0  jz      short loc_1800987C8
0x1800987c2  call    cs:__imp_LocalFree
0x1800987c8  mov     rsi, [rsp+40h+arg_8]
0x1800987cd  mov     eax, ebx
0x1800987cf  mov     rbx, [rsp+40h+arg_0]
0x1800987d4  add     rsp, 40h
0x1800987d8  pop     r14
0x1800987da  pop     rdi
0x1800987db  pop     rbp
0x1800987dc  retn
```
