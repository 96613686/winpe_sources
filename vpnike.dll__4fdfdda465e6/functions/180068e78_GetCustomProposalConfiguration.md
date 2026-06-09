# GetCustomProposalConfiguration

- ea: `0x180068e78`
- end: `0x180069142`
- name: `GetCustomProposalConfiguration`
- size: `714`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180067b78`

## callees

- `0x180046d6c`
- `0x180068cb4`
- `0x180068e78`
- `0x180069428`
- `0x18006947c`
- `0x180069508`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180068ef7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180068fb9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180069003`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18006904d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180069096`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180068ef7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180068fb9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180069003`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18006904d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180069096`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800690b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006910e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800690b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006910e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180068f80`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180068f80`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068f1a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068f1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800690fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800690fe`

## string_xrefs

- `0x180068f43`: `System\CurrentControlSet\Services\rasman\IKEv2`

## pseudocode

```c
char *__fastcall GetCustomProposalConfiguration(_DWORD *a1)
{
  char *i; // rdi
  HKEY CustomCofigurationKey; // r14
  unsigned int v4; // r15d
  __int64 v5; // rbx
  __int64 v6; // rbx
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  BYTE lpData[272]; // [rsp+40h] [rbp-C0h] BYREF
  char pszDest[272]; // [rsp+150h] [rbp+50h] BYREF

  i = 0;
  phkResult = 0;
  CustomCofigurationKey = (HKEY)GetCustomCofigurationKey();
  *a1 = 0;
  if ( CustomCofigurationKey )
  {
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( RegQueryValueExA(CustomCofigurationKey, "CustomProposalsCount", 0, 0, Data, &cbData) )
    {
LABEL_23:
      RegCloseKey(CustomCofigurationKey);
      return i;
    }
    if ( *(_DWORD *)Data )
    {
      v4 = 0;
      for ( i = (char *)LocalAlloc(0x40u, 32LL * *(unsigned int *)Data); v4 < *(_DWORD *)Data; ++v4 )
      {
        StringCchPrintfA(
          pszDest,
          0x104u,
          "%s\\%s\\%d",
          "System\\CurrentControlSet\\Services\\rasman\\IKEv2",
          "Proposals",
          v4);
        if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, pszDest, 0, 1u, &phkResult) )
        {
          cbData = 260;
          if ( !RegQueryValueExA(phkResult, "esp_encr", 0, 0, lpData, &cbData) )
          {
            v5 = 32LL * (unsigned int)*a1;
            *(_QWORD *)&i[v5 + 8] = StringToEncrTransform((char *)lpData);
          }
          cbData = 260;
          if ( !RegQueryValueExA(phkResult, "esp_auth", 0, 0, lpData, &cbData) )
          {
            v6 = 32LL * (unsigned int)*a1;
            *(_QWORD *)&i[v6 + 16] = StringToAuthTransform((char *)lpData);
          }
          cbData = 260;
          if ( !RegQueryValueExA(phkResult, "AH", 0, 0, lpData, &cbData) )
          {
            v7 = 32LL * (unsigned int)*a1;
            *(_QWORD *)&i[v7] = StringToAuthTransform((char *)lpData);
          }
          cbData = 260;
          if ( !RegQueryValueExA(phkResult, "PFS", 0, 0, lpData, &cbData) )
          {
            v8 = 32LL * (unsigned int)*a1;
            *(_DWORD *)&i[v8 + 24] = StringToPFSTransform((char *)lpData);
          }
          RegCloseKey(phkResult);
          v9 = 32LL * (unsigned int)*a1;
          if ( *(_QWORD *)&i[v9] || *(_QWORD *)&i[v9 + 8] || *(_QWORD *)&i[v9 + 16] )
            ++*a1;
        }
      }
    }
  }
  if ( !*a1 && i )
  {
    LocalFree(i);
    i = 0;
  }
  if ( CustomCofigurationKey )
    goto LABEL_23;
  return i;
}

```

## disassembly

```asm
0x180068e78  mov     [rsp-8+arg_8], rbx
0x180068e7d  mov     [rsp-8+arg_10], rsi
0x180068e82  push    rbp
0x180068e83  push    rdi
0x180068e84  push    r13
0x180068e86  push    r14
0x180068e88  push    r15
0x180068e8a  lea     rbp, [rsp-170h]
0x180068e92  sub     rsp, 270h
0x180068e99  mov     rax, cs:__security_cookie
0x180068ea0  xor     rax, rsp
0x180068ea3  mov     [rbp+190h+var_30], rax
0x180068eaa  mov     rsi, rcx
0x180068ead  xor     edi, edi
0x180068eaf  call    GetCustomCofigurationKey
0x180068eb4  mov     [rsp+290h+phkResult], rdi
0x180068eb9  mov     r14, rax
0x180068ebc  mov     [rsi], edi
0x180068ebe  test    rax, rax
0x180068ec1  jz      loc_1800690F1
0x180068ec7  lea     rax, [rsp+290h+cbData]
0x180068ecc  mov     dword ptr [rsp+290h+Data], edi
0x180068ed0  mov     [rsp+290h+lpcbData], rax; lpcbData
0x180068ed5  lea     rdx, aCustomproposal; "CustomProposalsCount"
0x180068edc  lea     rax, [rsp+290h+Data]
0x180068ee1  mov     [rsp+290h+cbData], 4
0x180068ee9  xor     r9d, r9d; lpType
0x180068eec  mov     [rsp+290h+lpData], rax; lpData
0x180068ef1  xor     r8d, r8d; lpReserved
0x180068ef4  mov     rcx, r14; hKey
0x180068ef7  call    cs:__imp_RegQueryValueExA
0x180068efd  test    eax, eax
0x180068eff  jnz     loc_18006910B
0x180068f05  mov     eax, dword ptr [rsp+290h+Data]
0x180068f09  test    eax, eax
0x180068f0b  jz      loc_1800690F1
0x180068f11  mov     edx, eax
0x180068f13  lea     ecx, [rdi+40h]; uFlags
0x180068f16  shl     rdx, 5; uBytes
0x180068f1a  call    cs:__imp_LocalAlloc
0x180068f20  xor     r15d, r15d
0x180068f23  mov     rdi, rax
0x180068f26  cmp     dword ptr [rsp+290h+Data], r15d
0x180068f2b  jbe     loc_1800690F1
0x180068f31  mov     r13d, 104h
0x180068f37  lea     rax, aProposals; "Proposals"
0x180068f3e  mov     dword ptr [rsp+290h+lpcbData], r15d
0x180068f43  lea     r9, SubKey; "System\\CurrentControlSet\\Services\\ra"...
0x180068f4a  mov     [rsp+290h+lpData], rax
0x180068f4f  lea     r8, aSSD; "%s\\%s\\%d"
0x180068f56  mov     rdx, r13; cchDest
0x180068f59  lea     rcx, [rbp+190h+pszDest]; pszDest
0x180068f5d  call    StringCchPrintfA
0x180068f62  lea     rax, [rsp+290h+phkResult]
0x180068f67  mov     r9d, 1; samDesired
0x180068f6d  xor     r8d, r8d; ulOptions
0x180068f70  mov     [rsp+290h+lpData], rax; phkResult
0x180068f75  lea     rdx, [rbp+190h+pszDest]; lpSubKey
0x180068f79  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180068f80  call    cs:__imp_RegOpenKeyExA
0x180068f86  test    eax, eax
0x180068f88  jnz     loc_1800690E3
0x180068f8e  mov     rcx, [rsp+290h+phkResult]; hKey
0x180068f93  lea     rax, [rsp+290h+cbData]
0x180068f98  mov     [rsp+290h+lpcbData], rax; lpcbData
0x180068f9d  lea     rdx, aEspEncr; "esp_encr"
0x180068fa4  lea     rax, [rsp+290h+var_250]
0x180068fa9  mov     [rsp+290h+cbData], r13d
0x180068fae  xor     r9d, r9d; lpType
0x180068fb1  mov     [rsp+290h+lpData], rax; lpData
0x180068fb6  xor     r8d, r8d; lpReserved
0x180068fb9  call    cs:__imp_RegQueryValueExA
0x180068fbf  test    eax, eax
0x180068fc1  jnz     short loc_180068FD8
0x180068fc3  mov     ebx, [rsi]
0x180068fc5  lea     rcx, [rsp+290h+var_250]; String1
0x180068fca  shl     rbx, 5
0x180068fce  call    StringToEncrTransform
0x180068fd3  mov     [rbx+rdi+8], rax
0x180068fd8  mov     rcx, [rsp+290h+phkResult]; hKey
0x180068fdd  lea     rax, [rsp+290h+cbData]
0x180068fe2  mov     [rsp+290h+lpcbData], rax; lpcbData
0x180068fe7  lea     rdx, aEspAuth; "esp_auth"
0x180068fee  lea     rax, [rsp+290h+var_250]
0x180068ff3  mov     [rsp+290h+cbData], r13d
0x180068ff8  xor     r9d, r9d; lpType
0x180068ffb  mov     [rsp+290h+lpData], rax; lpData
0x180069000  xor     r8d, r8d; lpReserved
0x180069003  call    cs:__imp_RegQueryValueExA
0x180069009  test    eax, eax
0x18006900b  jnz     short loc_180069022
0x18006900d  mov     ebx, [rsi]
0x18006900f  lea     rcx, [rsp+290h+var_250]; String1
0x180069014  shl     rbx, 5
0x180069018  call    StringToAuthTransform
0x18006901d  mov     [rbx+rdi+10h], rax
0x180069022  mov     rcx, [rsp+290h+phkResult]; hKey
0x180069027  lea     rax, [rsp+290h+cbData]
0x18006902c  mov     [rsp+290h+lpcbData], rax; lpcbData
0x180069031  lea     rdx, aAh; "AH"
0x180069038  lea     rax, [rsp+290h+var_250]
0x18006903d  mov     [rsp+290h+cbData], r13d
0x180069042  xor     r9d, r9d; lpType
0x180069045  mov     [rsp+290h+lpData], rax; lpData
0x18006904a  xor     r8d, r8d; lpReserved
0x18006904d  call    cs:__imp_RegQueryValueExA
0x180069053  test    eax, eax
0x180069055  jnz     short loc_18006906B
0x180069057  mov     ebx, [rsi]
0x180069059  lea     rcx, [rsp+290h+var_250]; String1
0x18006905e  shl     rbx, 5
0x180069062  call    StringToAuthTransform
0x180069067  mov     [rbx+rdi], rax
0x18006906b  mov     rcx, [rsp+290h+phkResult]; hKey
0x180069070  lea     rax, [rsp+290h+cbData]
0x180069075  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18006907a  lea     rdx, aPfs; "PFS"
0x180069081  lea     rax, [rsp+290h+var_250]
0x180069086  mov     [rsp+290h+cbData], r13d
0x18006908b  xor     r9d, r9d; lpType
0x18006908e  mov     [rsp+290h+lpData], rax; lpData
0x180069093  xor     r8d, r8d; lpReserved
0x180069096  call    cs:__imp_RegQueryValueExA
0x18006909c  test    eax, eax
0x18006909e  jnz     short loc_1800690B4
0x1800690a0  mov     ebx, [rsi]
0x1800690a2  lea     rcx, [rsp+290h+var_250]; String1
0x1800690a7  shl     rbx, 5
0x1800690ab  call    StringToPFSTransform
0x1800690b0  mov     [rbx+rdi+18h], eax
0x1800690b4  mov     rcx, [rsp+290h+phkResult]; hKey
0x1800690b9  call    cs:__imp_RegCloseKey
0x1800690bf  mov     ecx, [rsi]
0x1800690c1  mov     eax, ecx
0x1800690c3  shl     rax, 5
0x1800690c7  cmp     qword ptr [rax+rdi], 0
0x1800690cc  jnz     short loc_1800690DE
0x1800690ce  cmp     qword ptr [rax+rdi+8], 0
0x1800690d4  jnz     short loc_1800690DE
0x1800690d6  cmp     qword ptr [rax+rdi+10h], 0
0x1800690dc  jz      short loc_1800690E3
0x1800690de  lea     eax, [rcx+1]
0x1800690e1  mov     [rsi], eax
0x1800690e3  inc     r15d
0x1800690e6  cmp     r15d, dword ptr [rsp+290h+Data]
0x1800690eb  jb      loc_180068F37
0x1800690f1  cmp     dword ptr [rsi], 0
0x1800690f4  jnz     short loc_180069106
0x1800690f6  test    rdi, rdi
0x1800690f9  jz      short loc_180069106
0x1800690fb  mov     rcx, rdi; hMem
0x1800690fe  call    cs:__imp_LocalFree
0x180069104  xor     edi, edi
0x180069106  test    r14, r14
0x180069109  jz      short loc_180069114
0x18006910b  mov     rcx, r14; hKey
0x18006910e  call    cs:__imp_RegCloseKey
0x180069114  mov     rax, rdi
0x180069117  mov     rcx, [rbp+190h+var_30]
0x18006911e  xor     rcx, rsp; StackCookie
0x180069121  call    __security_check_cookie
0x180069126  lea     r11, [rsp+290h+var_20]
0x18006912e  mov     rbx, [r11+38h]
0x180069132  mov     rsi, [r11+40h]
0x180069136  mov     rsp, r11
0x180069139  pop     r15
0x18006913b  pop     r14
0x18006913d  pop     r13
0x18006913f  pop     rdi
0x180069140  pop     rbp
0x180069141  retn
```
