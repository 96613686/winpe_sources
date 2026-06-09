# DoesSessionSidKeyExists

- ea: `0x140017970`
- end: `0x140017b39`
- name: `DoesSessionSidKeyExists`
- size: `457`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140071470`

## callees

- `0x140017970`
- `0x14005f014`
- `0x1400618ac`
- `0x1400618f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017ad4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017b0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017ad4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017b0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400179dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400179dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140017ae9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140017b21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140017ae9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140017b21`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140017aa2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140017aa2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017ab6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017ab6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400179c7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140017a1c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400179c7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140017a1c`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140017a39`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140017a39`

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
0x140017970  push    rbp
0x140017972  push    rbx
0x140017973  push    rsi
0x140017974  push    rdi
0x140017975  mov     rbp, rsp
0x140017978  sub     rsp, 58h
0x14001797c  xor     ebx, ebx
0x14001797e  xor     edi, edi
0x140017980  mov     [rbp+hMem], rbx
0x140017984  mov     rsi, rcx
0x140017987  mov     [rbp+StringSid], rbx
0x14001798b  mov     [rbp+TokenInformationLength], ebx
0x14001798e  mov     [rbp+lpSubKey], rbx
0x140017992  mov     [rbp+phkResult], rbx
0x140017996  test    rcx, rcx
0x140017999  jz      loc_140017AC7
0x14001799f  lea     rdx, [rbp+hMem]
0x1400179a3  call    GetUniqueSessionKey
0x1400179a8  mov     ebx, eax
0x1400179aa  test    eax, eax
0x1400179ac  jz      loc_140017AC7
0x1400179b2  lea     rax, [rbp+TokenInformationLength]
0x1400179b6  xor     r9d, r9d; TokenInformationLength
0x1400179b9  xor     r8d, r8d; TokenInformation
0x1400179bc  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1400179c1  lea     edx, [rdi+1]; TokenInformationClass
0x1400179c4  mov     rcx, rsi; TokenHandle
0x1400179c7  call    cs:__imp_GetTokenInformation
0x1400179ce  nop     dword ptr [rax+rax+00h]
0x1400179d3  mov     ebx, eax
0x1400179d5  test    eax, eax
0x1400179d7  jnz     loc_140017AC7
0x1400179dd  call    cs:__imp_GetLastError
0x1400179e4  nop     dword ptr [rax+rax+00h]
0x1400179e9  cmp     eax, 7Ah ; 'z'
0x1400179ec  jnz     loc_140017AC7
0x1400179f2  mov     ecx, [rbp+TokenInformationLength]; dwBytes
0x1400179f5  call    ALLOCMEM
0x1400179fa  mov     rdi, rax
0x1400179fd  test    rax, rax
0x140017a00  jz      loc_140017AC7
0x140017a06  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x140017a0a  lea     rax, [rbp+TokenInformationLength]
0x140017a0e  mov     r8, rdi; TokenInformation
0x140017a11  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x140017a16  lea     edx, [rbx+1]; TokenInformationClass
0x140017a19  mov     rcx, rsi; TokenHandle
0x140017a1c  call    cs:__imp_GetTokenInformation
0x140017a23  nop     dword ptr [rax+rax+00h]
0x140017a28  mov     ebx, eax
0x140017a2a  test    eax, eax
0x140017a2c  jz      loc_140017AC7
0x140017a32  mov     rcx, [rdi]; Sid
0x140017a35  lea     rdx, [rbp+StringSid]; StringSid
0x140017a39  call    cs:__imp_ConvertSidToStringSidW
0x140017a40  nop     dword ptr [rax+rax+00h]
0x140017a45  mov     ebx, eax
0x140017a47  test    eax, eax
0x140017a49  jz      short loc_140017AC7
0x140017a4b  mov     rax, [rbp+hMem]
0x140017a4f  lea     r8, asc_1400B7668; "\\"
0x140017a56  mov     rdx, [rbp+StringSid]
0x140017a5a  lea     r9, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x140017a61  mov     [rsp+58h+var_28], 0
0x140017a6a  lea     rcx, [rbp+lpSubKey]
0x140017a6e  mov     [rsp+58h+var_30], rax
0x140017a73  mov     [rsp+58h+ReturnLength], r8
0x140017a78  call    StrCatAlloc
0x140017a7d  test    eax, eax
0x140017a7f  jz      short loc_140017A85
0x140017a81  xor     ebx, ebx
0x140017a83  jmp     short loc_140017AC7
0x140017a85  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x140017a89  lea     rax, [rbp+phkResult]
0x140017a8d  mov     r9d, 20019h; samDesired
0x140017a93  mov     [rsp+58h+ReturnLength], rax; phkResult
0x140017a98  xor     r8d, r8d; ulOptions
0x140017a9b  mov     rcx, 0FFFFFFFF80000003h; hKey
0x140017aa2  call    cs:__imp_RegOpenKeyExW
0x140017aa9  nop     dword ptr [rax+rax+00h]
0x140017aae  test    eax, eax
0x140017ab0  jnz     short loc_140017A81
0x140017ab2  mov     rcx, [rbp+phkResult]; hKey
0x140017ab6  call    cs:__imp_RegCloseKey
0x140017abd  nop     dword ptr [rax+rax+00h]
0x140017ac2  mov     ebx, 1
0x140017ac7  mov     r8, [rbp+lpSubKey]; lpMem
0x140017acb  xor     edx, edx; dwFlags
0x140017acd  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140017ad4  call    cs:__imp_HeapFree
0x140017adb  nop     dword ptr [rax+rax+00h]
0x140017ae0  mov     rcx, [rbp+StringSid]; hMem
0x140017ae4  test    rcx, rcx
0x140017ae7  jz      short loc_140017AF5
0x140017ae9  call    cs:__imp_LocalFree
0x140017af0  nop     dword ptr [rax+rax+00h]
0x140017af5  test    rdi, rdi
0x140017af8  jz      short loc_140017B18
0x140017afa  mov     rcx, gs:60h
0x140017b03  mov     r8, rdi; lpMem
0x140017b06  xor     edx, edx; dwFlags
0x140017b08  mov     rcx, [rcx+30h]; hHeap
0x140017b0c  call    cs:__imp_HeapFree
0x140017b13  nop     dword ptr [rax+rax+00h]
0x140017b18  mov     rcx, [rbp+hMem]; hMem
0x140017b1c  test    rcx, rcx
0x140017b1f  jz      short loc_140017B2D
0x140017b21  call    cs:__imp_LocalFree
0x140017b28  nop     dword ptr [rax+rax+00h]
0x140017b2d  mov     eax, ebx
0x140017b2f  add     rsp, 58h
0x140017b33  pop     rdi
0x140017b34  pop     rsi
0x140017b35  pop     rbx
0x140017b36  pop     rbp
0x140017b37  retn
```
