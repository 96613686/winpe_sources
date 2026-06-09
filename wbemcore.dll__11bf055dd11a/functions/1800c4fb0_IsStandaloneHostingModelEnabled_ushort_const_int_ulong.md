# IsStandaloneHostingModelEnabled(ushort const *,int &,ulong &)

- ea: `0x1800c4fb0`
- end: `0x1800c52ca`
- name: `?IsStandaloneHostingModelEnabled@@YAJPEBGAEAHAEAK@Z`
- size: `794`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c6954`

## callees

- `0x1800c4fb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c504a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c50bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c512e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c519c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c521b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5287`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c504a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c50bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c512e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c519c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c521b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5287`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c503e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c50b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c5122`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c5190`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c520f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c527b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c503e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c50b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c5122`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c5190`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c520f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c527b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c500b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5083`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c50f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5163`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c51e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5250`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c500b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5083`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c50f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5163`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c51e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5250`

## string_xrefs

- `0x1800c50e7`: `SOFTWARE\Microsoft\WBEM\CIMOM\CompatibleHostProviders`
- `0x1800c5155`: `SOFTWARE\Microsoft\WBEM\CIMOM\CompatibleHostProviders`

## pseudocode

```c
__int64 __fastcall IsStandaloneHostingModelEnabled(LPCWSTR lpValueName, int *a2, BYTE *a3)
{
  LSTATUS v6; // ebx
  LSTATUS v7; // ebx
  LSTATUS v8; // ebx
  LSTATUS v9; // ebx
  LSTATUS v11; // ebx
  LSTATUS v12; // ebx
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  hKey = 0;
  cbData = 4;
  Type = 1;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\SecuredHostProviders", 0, 0x20019u, &hKey) )
  {
    cbData = 0;
    v6 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
    RegCloseKey(hKey);
    if ( (!v6 || v6 == 234) && Type == 1 )
      goto LABEL_17;
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\SecuredHostProviders", 0, 0x20219u, &hKey) )
  {
    cbData = 0;
    v7 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
    RegCloseKey(hKey);
    if ( (!v7 || v7 == 234) && Type == 1 )
      goto LABEL_17;
  }
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\CompatibleHostProviders",
          0,
          0x20019u,
          &hKey)
    && ((cbData = 0, v8 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData), RegCloseKey(hKey), !v8) || v8 == 234)
    && Type == 1
    || !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\CompatibleHostProviders",
          0,
          0x20219u,
          &hKey)
    && ((cbData = 0, v9 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData), RegCloseKey(hKey), !v9) || v9 == 234)
    && Type == 1 )
  {
LABEL_17:
    *a2 = 0;
    return 0;
  }
  Type = 1;
  cbData = 4;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\StandaloneProviders", 0, 0x20019u, &hKey)
    && ((v11 = RegQueryValueExW(hKey, lpValueName, 0, &Type, a3, &cbData), RegCloseKey(hKey), !v11) || v11 == 234)
    && Type == 1
    || (v12 = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\WBEM\\CIMOM\\StandaloneProviders",
                0,
                0x20219u,
                &hKey)) == 0
    && ((cbData = 0, v12 = RegQueryValueExW(hKey, lpValueName, 0, &Type, a3, &cbData), RegCloseKey(hKey), !v12)
     || v12 == 234)
    && Type == 1 )
  {
    *a2 = 1;
    return 0;
  }
  if ( v12 > 0 )
    return (unsigned __int16)v12 | 0x80070000;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800c4fb0  mov     [rsp-28h+arg_0], rbx
0x1800c4fb5  mov     [rsp-28h+arg_8], rsi
0x1800c4fba  push    rbp
0x1800c4fbb  push    rdi
0x1800c4fbc  push    r12
0x1800c4fbe  push    r13
0x1800c4fc0  push    r14
0x1800c4fc2  mov     rbp, rsp
0x1800c4fc5  sub     rsp, 40h
0x1800c4fc9  mov     r14, r8
0x1800c4fcc  mov     [rbp+hKey], 0
0x1800c4fd4  mov     rsi, rdx
0x1800c4fd7  mov     [rbp+cbData], 4
0x1800c4fde  mov     rdi, rcx
0x1800c4fe1  lea     rax, [rbp+hKey]
0x1800c4fe5  mov     r12d, 1
0x1800c4feb  mov     [rsp+40h+phkResult], rax; phkResult
0x1800c4ff0  xor     r8d, r8d; ulOptions
0x1800c4ff3  mov     [rbp+Type], r12d
0x1800c4ff7  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Secur"...
0x1800c4ffe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c5005  mov     r9d, 20019h; samDesired
0x1800c500b  call    cs:__imp_RegOpenKeyExW
0x1800c5011  mov     r13d, 0EAh
0x1800c5017  test    eax, eax
0x1800c5019  jnz     short loc_1800C5063
0x1800c501b  mov     rcx, [rbp+hKey]; hKey
0x1800c501f  lea     r9, [rbp+Type]; lpType
0x1800c5023  mov     [rbp+cbData], eax
0x1800c5026  xor     r8d, r8d; lpReserved
0x1800c5029  lea     rax, [rbp+cbData]
0x1800c502d  mov     rdx, rdi; lpValueName
0x1800c5030  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800c5035  mov     [rsp+40h+phkResult], 0; lpData
0x1800c503e  call    cs:__imp_RegQueryValueExW
0x1800c5044  mov     rcx, [rbp+hKey]; hKey
0x1800c5048  mov     ebx, eax
0x1800c504a  call    cs:__imp_RegCloseKey
0x1800c5050  test    ebx, ebx
0x1800c5052  jz      short loc_1800C5059
0x1800c5054  cmp     ebx, r13d
0x1800c5057  jnz     short loc_1800C5063
0x1800c5059  cmp     [rbp+Type], r12d
0x1800c505d  jz      loc_1800C51B1
0x1800c5063  lea     rax, [rbp+hKey]
0x1800c5067  mov     r9d, 20219h; samDesired
0x1800c506d  xor     r8d, r8d; ulOptions
0x1800c5070  mov     [rsp+40h+phkResult], rax; phkResult
0x1800c5075  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Secur"...
0x1800c507c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c5083  call    cs:__imp_RegOpenKeyExW
0x1800c5089  test    eax, eax
0x1800c508b  jnz     short loc_1800C50D5
0x1800c508d  mov     rcx, [rbp+hKey]; hKey
0x1800c5091  lea     r9, [rbp+Type]; lpType
0x1800c5095  mov     [rbp+cbData], eax
0x1800c5098  xor     r8d, r8d; lpReserved
0x1800c509b  lea     rax, [rbp+cbData]
0x1800c509f  mov     rdx, rdi; lpValueName
0x1800c50a2  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800c50a7  mov     [rsp+40h+phkResult], 0; lpData
0x1800c50b0  call    cs:__imp_RegQueryValueExW
0x1800c50b6  mov     rcx, [rbp+hKey]; hKey
0x1800c50ba  mov     ebx, eax
0x1800c50bc  call    cs:__imp_RegCloseKey
0x1800c50c2  test    ebx, ebx
0x1800c50c4  jz      short loc_1800C50CB
0x1800c50c6  cmp     ebx, r13d
0x1800c50c9  jnz     short loc_1800C50D5
0x1800c50cb  cmp     [rbp+Type], r12d
0x1800c50cf  jz      loc_1800C51B1
0x1800c50d5  lea     rax, [rbp+hKey]
0x1800c50d9  mov     r9d, 20019h; samDesired
0x1800c50df  xor     r8d, r8d; ulOptions
0x1800c50e2  mov     [rsp+40h+phkResult], rax; phkResult
0x1800c50e7  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Compa"...
0x1800c50ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c50f5  call    cs:__imp_RegOpenKeyExW
0x1800c50fb  test    eax, eax
0x1800c50fd  jnz     short loc_1800C5143
0x1800c50ff  mov     rcx, [rbp+hKey]; hKey
0x1800c5103  lea     r9, [rbp+Type]; lpType
0x1800c5107  mov     [rbp+cbData], eax
0x1800c510a  xor     r8d, r8d; lpReserved
0x1800c510d  lea     rax, [rbp+cbData]
0x1800c5111  mov     rdx, rdi; lpValueName
0x1800c5114  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800c5119  mov     [rsp+40h+phkResult], 0; lpData
0x1800c5122  call    cs:__imp_RegQueryValueExW
0x1800c5128  mov     rcx, [rbp+hKey]; hKey
0x1800c512c  mov     ebx, eax
0x1800c512e  call    cs:__imp_RegCloseKey
0x1800c5134  test    ebx, ebx
0x1800c5136  jz      short loc_1800C513D
0x1800c5138  cmp     ebx, r13d
0x1800c513b  jnz     short loc_1800C5143
0x1800c513d  cmp     [rbp+Type], r12d
0x1800c5141  jz      short loc_1800C51B1
0x1800c5143  lea     rax, [rbp+hKey]
0x1800c5147  mov     r9d, 20219h; samDesired
0x1800c514d  xor     r8d, r8d; ulOptions
0x1800c5150  mov     [rsp+40h+phkResult], rax; phkResult
0x1800c5155  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Compa"...
0x1800c515c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c5163  call    cs:__imp_RegOpenKeyExW
0x1800c5169  test    eax, eax
0x1800c516b  jnz     short loc_1800C51BE
0x1800c516d  mov     rcx, [rbp+hKey]; hKey
0x1800c5171  lea     r9, [rbp+Type]; lpType
0x1800c5175  mov     [rbp+cbData], eax
0x1800c5178  xor     r8d, r8d; lpReserved
0x1800c517b  lea     rax, [rbp+cbData]
0x1800c517f  mov     rdx, rdi; lpValueName
0x1800c5182  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800c5187  mov     [rsp+40h+phkResult], 0; lpData
0x1800c5190  call    cs:__imp_RegQueryValueExW
0x1800c5196  mov     rcx, [rbp+hKey]; hKey
0x1800c519a  mov     ebx, eax
0x1800c519c  call    cs:__imp_RegCloseKey
0x1800c51a2  test    ebx, ebx
0x1800c51a4  jz      short loc_1800C51AB
0x1800c51a6  cmp     ebx, r13d
0x1800c51a9  jnz     short loc_1800C51BE
0x1800c51ab  cmp     [rbp+Type], r12d
0x1800c51af  jnz     short loc_1800C51BE
0x1800c51b1  mov     dword ptr [rsi], 0
0x1800c51b7  xor     eax, eax
0x1800c51b9  jmp     loc_1800C52B3
0x1800c51be  lea     rax, [rbp+hKey]
0x1800c51c2  mov     [rbp+Type], r12d
0x1800c51c6  mov     r9d, 20019h; samDesired
0x1800c51cc  mov     [rsp+40h+phkResult], rax; phkResult
0x1800c51d1  xor     r8d, r8d; ulOptions
0x1800c51d4  mov     [rbp+cbData], 4
0x1800c51db  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Stand"...
0x1800c51e2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c51e9  call    cs:__imp_RegOpenKeyExW
0x1800c51ef  test    eax, eax
0x1800c51f1  jnz     short loc_1800C5230
0x1800c51f3  mov     rcx, [rbp+hKey]; hKey
0x1800c51f7  lea     rax, [rbp+cbData]
0x1800c51fb  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800c5200  lea     r9, [rbp+Type]; lpType
0x1800c5204  xor     r8d, r8d; lpReserved
0x1800c5207  mov     [rsp+40h+phkResult], r14; lpData
0x1800c520c  mov     rdx, rdi; lpValueName
0x1800c520f  call    cs:__imp_RegQueryValueExW
0x1800c5215  mov     rcx, [rbp+hKey]; hKey
0x1800c5219  mov     ebx, eax
0x1800c521b  call    cs:__imp_RegCloseKey
0x1800c5221  test    ebx, ebx
0x1800c5223  jz      short loc_1800C522A
0x1800c5225  cmp     ebx, r13d
0x1800c5228  jnz     short loc_1800C5230
0x1800c522a  cmp     [rbp+Type], r12d
0x1800c522e  jz      short loc_1800C529C
0x1800c5230  lea     rax, [rbp+hKey]
0x1800c5234  mov     r9d, 20219h; samDesired
0x1800c523a  xor     r8d, r8d; ulOptions
0x1800c523d  mov     [rsp+40h+phkResult], rax; phkResult
0x1800c5242  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\WBEM\\CIMOM\\Stand"...
0x1800c5249  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c5250  call    cs:__imp_RegOpenKeyExW
0x1800c5256  mov     ebx, eax
0x1800c5258  test    eax, eax
0x1800c525a  jnz     short loc_1800C52A4
0x1800c525c  mov     rcx, [rbp+hKey]; hKey
0x1800c5260  lea     r9, [rbp+Type]; lpType
0x1800c5264  mov     [rbp+cbData], eax
0x1800c5267  xor     r8d, r8d; lpReserved
0x1800c526a  lea     rax, [rbp+cbData]
0x1800c526e  mov     rdx, rdi; lpValueName
0x1800c5271  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800c5276  mov     [rsp+40h+phkResult], r14; lpData
0x1800c527b  call    cs:__imp_RegQueryValueExW
0x1800c5281  mov     rcx, [rbp+hKey]; hKey
0x1800c5285  mov     ebx, eax
0x1800c5287  call    cs:__imp_RegCloseKey
0x1800c528d  test    ebx, ebx
0x1800c528f  jz      short loc_1800C5296
0x1800c5291  cmp     ebx, r13d
0x1800c5294  jnz     short loc_1800C52A4
0x1800c5296  cmp     [rbp+Type], r12d
0x1800c529a  jnz     short loc_1800C52A4
0x1800c529c  mov     [rsi], r12d
0x1800c529f  jmp     loc_1800C51B7
0x1800c52a4  test    ebx, ebx
0x1800c52a6  jle     short loc_1800C52B1
0x1800c52a8  movzx   ebx, bx
0x1800c52ab  or      ebx, 80070000h
0x1800c52b1  mov     eax, ebx
0x1800c52b3  mov     rbx, [rsp+40h+arg_0]
0x1800c52b8  mov     rsi, [rsp+40h+arg_8]
0x1800c52bd  add     rsp, 40h
0x1800c52c1  pop     r14
0x1800c52c3  pop     r13
0x1800c52c5  pop     r12
0x1800c52c7  pop     rdi
0x1800c52c8  pop     rbp
0x1800c52c9  retn
```
