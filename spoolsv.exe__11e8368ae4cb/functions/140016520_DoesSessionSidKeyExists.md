# DoesSessionSidKeyExists

- ea: `0x140016520`
- end: `0x1400166ac`
- name: `DoesSessionSidKeyExists`
- size: `396`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14006a910`

## callees

- `0x140016520`
- `0x14005983c`
- `0x14005bdc8`
- `0x14005be08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140016660`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001668c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140016660`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001668c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016587`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001666f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001669b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001666f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001669b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001663a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001663a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016648`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016648`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140016577`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400165c0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140016577`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400165c0`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1400165d7`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1400165d7`

## pseudocode

```c
__int64 __fastcall DoesSessionSidKeyExists(HANDLE TokenHandle)
{
  unsigned int UniqueSessionKey; // ebx
  PSID *v2; // rdi
  HKEY phkResult; // [rsp+40h] [rbp-18h] BYREF
  DWORD TokenInformationLength; // [rsp+80h] [rbp+28h] BYREF
  LPCWSTR lpSubKey; // [rsp+88h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+90h] [rbp+38h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp+40h] BYREF

  UniqueSessionKey = 0;
  v2 = 0;
  hMem = 0;
  StringSid = 0;
  TokenInformationLength = 0;
  lpSubKey = 0;
  phkResult = 0;
  if ( TokenHandle )
  {
    UniqueSessionKey = GetUniqueSessionKey(TokenHandle, (LPWSTR *)&hMem);
    if ( UniqueSessionKey )
    {
      UniqueSessionKey = GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
      if ( !UniqueSessionKey && GetLastError() == 122 )
      {
        v2 = (PSID *)ALLOCMEM(TokenInformationLength);
        if ( v2 )
        {
          UniqueSessionKey = GetTokenInformation(
                               TokenHandle,
                               TokenUser,
                               v2,
                               TokenInformationLength,
                               &TokenInformationLength);
          if ( UniqueSessionKey )
          {
            UniqueSessionKey = ConvertSidToStringSidW(*v2, &StringSid);
            if ( UniqueSessionKey )
            {
              if ( (unsigned int)StrCatAlloc(
                                   &lpSubKey,
                                   StringSid,
                                   L"\\",
                                   L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows\\SessionDefaultDevices",
                                   L"\\",
                                   hMem,
                                   0)
                || RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x20019u, &phkResult) )
              {
                UniqueSessionKey = 0;
              }
              else
              {
                RegCloseKey(phkResult);
                UniqueSessionKey = 1;
              }
            }
          }
        }
      }
    }
  }
  HeapFree(g_hSpoolssHeap, 0, (LPVOID)lpSubKey);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v2 )
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v2);
  if ( hMem )
    LocalFree(hMem);
  return UniqueSessionKey;
}

```

## disassembly

```asm
0x140016520  push    rbp
0x140016522  push    rbx
0x140016523  push    rsi
0x140016524  push    rdi
0x140016525  mov     rbp, rsp
0x140016528  sub     rsp, 58h
0x14001652c  xor     ebx, ebx
0x14001652e  xor     edi, edi
0x140016530  mov     [rbp+hMem], rbx
0x140016534  mov     rsi, rcx
0x140016537  mov     [rbp+StringSid], rbx
0x14001653b  mov     [rbp+TokenInformationLength], ebx
0x14001653e  mov     [rbp+lpSubKey], rbx
0x140016542  mov     [rbp+phkResult], rbx
0x140016546  test    rcx, rcx
0x140016549  jz      loc_140016653
0x14001654f  lea     rdx, [rbp+hMem]
0x140016553  call    GetUniqueSessionKey
0x140016558  mov     ebx, eax
0x14001655a  test    eax, eax
0x14001655c  jz      loc_140016653
0x140016562  lea     rax, [rbp+TokenInformationLength]
0x140016566  xor     r9d, r9d; TokenInformationLength
0x140016569  xor     r8d, r8d; TokenInformation
0x14001656c  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x140016571  lea     edx, [rdi+1]; TokenInformationClass
0x140016574  mov     rcx, rsi; TokenHandle
0x140016577  call    cs:__imp_GetTokenInformation
0x14001657d  mov     ebx, eax
0x14001657f  test    eax, eax
0x140016581  jnz     loc_140016653
0x140016587  call    cs:__imp_GetLastError
0x14001658d  cmp     eax, 7Ah ; 'z'
0x140016590  jnz     loc_140016653
0x140016596  mov     ecx, [rbp+TokenInformationLength]; dwBytes
0x140016599  call    ALLOCMEM
0x14001659e  mov     rdi, rax
0x1400165a1  test    rax, rax
0x1400165a4  jz      loc_140016653
0x1400165aa  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1400165ae  lea     rax, [rbp+TokenInformationLength]
0x1400165b2  mov     r8, rdi; TokenInformation
0x1400165b5  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1400165ba  lea     edx, [rbx+1]; TokenInformationClass
0x1400165bd  mov     rcx, rsi; TokenHandle
0x1400165c0  call    cs:__imp_GetTokenInformation
0x1400165c6  mov     ebx, eax
0x1400165c8  test    eax, eax
0x1400165ca  jz      loc_140016653
0x1400165d0  mov     rcx, [rdi]; Sid
0x1400165d3  lea     rdx, [rbp+StringSid]; StringSid
0x1400165d7  call    cs:__imp_ConvertSidToStringSidW
0x1400165dd  mov     ebx, eax
0x1400165df  test    eax, eax
0x1400165e1  jz      short loc_140016653
0x1400165e3  mov     rax, [rbp+hMem]
0x1400165e7  lea     r8, asc_1400B0668; "\\"
0x1400165ee  mov     rdx, [rbp+StringSid]
0x1400165f2  lea     r9, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400165f9  mov     [rsp+58h+var_28], 0
0x140016602  lea     rcx, [rbp+lpSubKey]
0x140016606  mov     [rsp+58h+var_30], rax
0x14001660b  mov     [rsp+58h+ReturnLength], r8
0x140016610  call    StrCatAlloc
0x140016615  test    eax, eax
0x140016617  jz      short loc_14001661D
0x140016619  xor     ebx, ebx
0x14001661b  jmp     short loc_140016653
0x14001661d  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x140016621  lea     rax, [rbp+phkResult]
0x140016625  mov     r9d, 20019h; samDesired
0x14001662b  mov     [rsp+58h+ReturnLength], rax; phkResult
0x140016630  xor     r8d, r8d; ulOptions
0x140016633  mov     rcx, 0FFFFFFFF80000003h; hKey
0x14001663a  call    cs:__imp_RegOpenKeyExW
0x140016640  test    eax, eax
0x140016642  jnz     short loc_140016619
0x140016644  mov     rcx, [rbp+phkResult]; hKey
0x140016648  call    cs:__imp_RegCloseKey
0x14001664e  mov     ebx, 1
0x140016653  mov     r8, [rbp+lpSubKey]; lpMem
0x140016657  xor     edx, edx; dwFlags
0x140016659  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140016660  call    cs:__imp_HeapFree
0x140016666  mov     rcx, [rbp+StringSid]; hMem
0x14001666a  test    rcx, rcx
0x14001666d  jz      short loc_140016675
0x14001666f  call    cs:__imp_LocalFree
0x140016675  test    rdi, rdi
0x140016678  jz      short loc_140016692
0x14001667a  mov     rcx, gs:60h
0x140016683  mov     r8, rdi; lpMem
0x140016686  xor     edx, edx; dwFlags
0x140016688  mov     rcx, [rcx+30h]; hHeap
0x14001668c  call    cs:__imp_HeapFree
0x140016692  mov     rcx, [rbp+hMem]; hMem
0x140016696  test    rcx, rcx
0x140016699  jz      short loc_1400166A1
0x14001669b  call    cs:__imp_LocalFree
0x1400166a1  mov     eax, ebx
0x1400166a3  add     rsp, 58h
0x1400166a7  pop     rdi
0x1400166a8  pop     rsi
0x1400166a9  pop     rbx
0x1400166aa  pop     rbp
0x1400166ab  retn
```
