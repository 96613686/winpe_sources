# ReadNtpServerFromParametersKey

- ea: `0x18004f5d4`
- end: `0x18004f8f4`
- name: `ReadNtpServerFromParametersKey`
- size: `800`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180049da0`
- `0x18004a3cc`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18003d270`
- `0x18003dd2c`
- `0x18004f5d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004f7f1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004f7f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f895`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a2a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f895`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a2a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f78c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004f78c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f6d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f820`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f6d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f820`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f8ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f8c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a2bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a2d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f8ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f8c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a2bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006a2d2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f746`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f7c8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f85c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f746`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f7c8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f85c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18004f661`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18004f661`

## string_xrefs

- `0x18004f653`: `System\CurrentControlSet\Services\W32Time\Parameters`
- `0x18004f69a`: `System\CurrentControlSet\Services\W32Time\Parameters`
- `0x18004f7e5`: `System\CurrentControlSet\Services\W32Time\Parameters`
- `0x18004f812`: `System\CurrentControlSet\Services\W32Time\Parameters`
- `0x18004f707`: `ReadNtpServerFromParametersKey:RegOpenKeyEx. Error: 0x%x\n`
- `0x18004f77c`: `ReadNtpServerFromParametersKey:RegGetValue. Error: 0x%x\n`

## pseudocode

```c
__int64 __fastcall ReadNtpServerFromParametersKey(_QWORD *a1, DWORD *a2)
{
  HLOCAL pvData; // rsi
  int PersistedRegistryLocationW; // eax
  unsigned int v6; // edi
  unsigned int v7; // ebx
  LSTATUS v8; // edi
  LSTATUS ValueW; // edi
  bool v10; // cc
  DWORD pdwType; // [rsp+44h] [rbp-254h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-250h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-248h] BYREF
  HLOCAL v15; // [rsp+58h] [rbp-240h]
  WCHAR SubKey; // [rsp+60h] [rbp-238h] BYREF
  _BYTE v17[526]; // [rsp+62h] [rbp-236h] BYREF

  pdwType = 0;
  hkey = 0;
  hKey = 0;
  pvData = 0;
  v15 = 0;
  SubKey = 0;
  memset_0(v17, 0, 0x206u);
  *a1 = 0;
  *a2 = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"W32TimeParameters",
                                 L"System\\CurrentControlSet\\Services\\W32Time\\Parameters",
                                 &SubKey,
                                 520,
                                 0);
  v6 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW )
  {
    if ( PersistedRegistryLocationW > 0 )
      v7 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    else
      v7 = PersistedRegistryLocationW;
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(
        L"Failed to get time regkey %s. Error: 0x%x\n",
        L"System\\CurrentControlSet\\Services\\W32Time\\Parameters",
        v6);
    goto LABEL_29;
  }
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, &SubKey, 0, 1u, &hkey);
  if ( v8 )
    goto LABEL_8;
  ValueW = RegGetValueW(hkey, 0, L"NtpServer", 2u, &pdwType, 0, a2);
  if ( ValueW )
  {
LABEL_15:
    v10 = ValueW <= 0;
    goto LABEL_16;
  }
  pvData = LocalAlloc(0x40u, *a2);
  v15 = pvData;
  ValueW = RegGetValueW(hkey, 0, L"NtpServer", 2u, &pdwType, pvData, a2);
  if ( ValueW == 2
    && (unsigned int)_o__wcsnicmp(&SubKey, L"System\\CurrentControlSet\\Services\\W32Time\\Parameters", 259) )
  {
    v8 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\W32Time\\Parameters",
           0,
           ValueW - 1,
           &hKey);
    if ( v8 )
    {
LABEL_8:
      if ( v8 > 0 )
        v7 = (unsigned __int16)v8 | 0x80070000;
      else
        v7 = v8;
      if ( (unsigned __int8)FileLogAllowEntry(0) )
        FileLogAdd(L"ReadNtpServerFromParametersKey:RegOpenKeyEx. Error: 0x%x\n", (unsigned int)v8);
      goto LABEL_29;
    }
    ValueW = RegGetValueW(hKey, 0, L"NtpServer", 2u, &pdwType, pvData, a2);
    if ( ValueW )
      goto LABEL_15;
  }
  else
  {
    v10 = ValueW <= 0;
    if ( ValueW )
    {
LABEL_16:
      if ( v10 )
        v7 = ValueW;
      else
        v7 = (unsigned __int16)ValueW | 0x80070000;
      if ( (unsigned __int8)FileLogAllowEntry(0) )
        FileLogAdd(L"ReadNtpServerFromParametersKey:RegGetValue. Error: 0x%x\n", (unsigned int)ValueW);
      goto LABEL_29;
    }
  }
  v7 = 0;
  if ( pvData )
    *a1 = pvData;
LABEL_29:
  if ( v7 && pvData )
    LocalFree(pvData);
  if ( hkey )
    RegCloseKey(hkey);
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x18004f5d4  mov     [rsp+arg_10], rbx
0x18004f5d9  push    rsi
0x18004f5da  push    rdi
0x18004f5db  push    r14
0x18004f5dd  sub     rsp, 280h
0x18004f5e4  mov     rax, cs:__security_cookie
0x18004f5eb  xor     rax, rsp
0x18004f5ee  mov     [rsp+298h+var_28], rax
0x18004f5f6  mov     rbx, rdx
0x18004f5f9  mov     r14, rcx
0x18004f5fc  mov     [rsp+298h+pdwType], 0
0x18004f604  mov     [rsp+298h+var_258], 0
0x18004f60c  mov     [rsp+298h+hkey], 0
0x18004f615  mov     [rsp+298h+hKey], 0
0x18004f61e  xor     esi, esi
0x18004f620  mov     [rsp+298h+var_240], rsi
0x18004f625  xor     eax, eax
0x18004f627  mov     [rsp+298h+SubKey], ax
0x18004f62c  xor     edx, edx; Val
0x18004f62e  mov     r8d, 206h; Size
0x18004f634  lea     rcx, [rsp+298h+var_236]; void *
0x18004f639  call    memset_0
0x18004f63e  mov     [r14], rsi
0x18004f641  mov     [rbx], esi
0x18004f643  mov     [rsp+298h+phkResult], rsi
0x18004f648  mov     r9d, 208h
0x18004f64e  lea     r8, [rsp+298h+SubKey]
0x18004f653  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\W3"...
0x18004f65a  lea     rcx, aW32timeparamet; "W32TimeParameters"
0x18004f661  call    cs:__imp_GetPersistedRegistryLocationW
0x18004f668  nop     dword ptr [rax+rax+00h]
0x18004f66d  mov     edi, eax
0x18004f66f  test    eax, eax
0x18004f671  jz      short loc_18004F6B2
0x18004f673  test    eax, eax
0x18004f675  jg      short loc_18004F67B
0x18004f677  mov     ebx, eax
0x18004f679  jmp     short loc_18004F684
0x18004f67b  movzx   ebx, di
0x18004f67e  or      ebx, 80070000h
0x18004f684  mov     [rsp+298h+var_258], ebx
0x18004f688  xor     ecx, ecx
0x18004f68a  call    FileLogAllowEntry
0x18004f68f  test    al, al
0x18004f691  jz      loc_18004F889
0x18004f697  mov     r8d, edi
0x18004f69a  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\W3"...
0x18004f6a1  lea     rcx, aFailedToGetTim; "Failed to get time regkey %s. Error: 0x"...
0x18004f6a8  call    FileLogAdd
0x18004f6ad  jmp     loc_18004F889
0x18004f6b2  lea     rax, [rsp+298h+hkey]
0x18004f6b7  mov     [rsp+298h+phkResult], rax; phkResult
0x18004f6bc  mov     r9d, 1; samDesired
0x18004f6c2  xor     r8d, r8d; ulOptions
0x18004f6c5  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x18004f6ca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004f6d1  call    cs:__imp_RegOpenKeyExW
0x18004f6d8  nop     dword ptr [rax+rax+00h]
0x18004f6dd  mov     edi, eax
0x18004f6df  test    eax, eax
0x18004f6e1  jz      short loc_18004F71A
0x18004f6e3  test    edi, edi
0x18004f6e5  jg      short loc_18004F6EB
0x18004f6e7  mov     ebx, edi
0x18004f6e9  jmp     short loc_18004F6F4
0x18004f6eb  movzx   ebx, di
0x18004f6ee  or      ebx, 80070000h
0x18004f6f4  mov     [rsp+298h+var_258], ebx
0x18004f6f8  xor     ecx, ecx
0x18004f6fa  call    FileLogAllowEntry
0x18004f6ff  test    al, al
0x18004f701  jz      loc_18004F889
0x18004f707  lea     rcx, aReadntpserverf_0; "ReadNtpServerFromParametersKey:RegOpenK"...
0x18004f70e  mov     edx, edi
0x18004f710  call    FileLogAdd
0x18004f715  jmp     loc_18004F889
0x18004f71a  mov     [rsp+298h+pcbData], rbx; pcbData
0x18004f71f  mov     [rsp+298h+pvData], 0; pvData
0x18004f728  lea     rax, [rsp+298h+pdwType]
0x18004f72d  mov     [rsp+298h+phkResult], rax; pdwType
0x18004f732  mov     r9d, 2; dwFlags
0x18004f738  lea     r8, aNtpserver; "NtpServer"
0x18004f73f  xor     edx, edx; lpSubKey
0x18004f741  mov     rcx, [rsp+298h+hkey]; hkey
0x18004f746  call    cs:__imp_RegGetValueW
0x18004f74d  nop     dword ptr [rax+rax+00h]
0x18004f752  mov     edi, eax
0x18004f754  test    eax, eax
0x18004f756  jz      short loc_18004F785
0x18004f758  test    edi, edi
0x18004f75a  jg      short loc_18004F760
0x18004f75c  mov     ebx, edi
0x18004f75e  jmp     short loc_18004F769
0x18004f760  movzx   ebx, di
0x18004f763  or      ebx, 80070000h
0x18004f769  mov     [rsp+298h+var_258], ebx
0x18004f76d  xor     ecx, ecx
0x18004f76f  call    FileLogAllowEntry
0x18004f774  test    al, al
0x18004f776  jz      loc_18004F889
0x18004f77c  lea     rcx, aReadntpserverf; "ReadNtpServerFromParametersKey:RegGetVa"...
0x18004f783  jmp     short loc_18004F70E
0x18004f785  mov     edx, [rbx]; uBytes
0x18004f787  mov     ecx, 40h ; '@'; uFlags
0x18004f78c  call    cs:__imp_LocalAlloc
0x18004f793  nop     dword ptr [rax+rax+00h]
0x18004f798  mov     rsi, rax
0x18004f79b  mov     [rsp+298h+var_240], rax
0x18004f7a0  mov     [rsp+298h+pcbData], rbx; pcbData
0x18004f7a5  mov     [rsp+298h+pvData], rax; pvData
0x18004f7aa  lea     rax, [rsp+298h+pdwType]
0x18004f7af  mov     [rsp+298h+phkResult], rax; pdwType
0x18004f7b4  mov     r9d, 2; dwFlags
0x18004f7ba  lea     r8, aNtpserver; "NtpServer"
0x18004f7c1  xor     edx, edx; lpSubKey
0x18004f7c3  mov     rcx, [rsp+298h+hkey]; hkey
0x18004f7c8  call    cs:__imp_RegGetValueW
0x18004f7cf  nop     dword ptr [rax+rax+00h]
0x18004f7d4  mov     edi, eax
0x18004f7d6  cmp     eax, 2
0x18004f7d9  jnz     loc_18004F873
0x18004f7df  mov     r8d, 103h
0x18004f7e5  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\W3"...
0x18004f7ec  lea     rcx, [rsp+298h+SubKey]
0x18004f7f1  call    cs:__imp__o__wcsnicmp
0x18004f7f8  nop     dword ptr [rax+rax+00h]
0x18004f7fd  test    eax, eax
0x18004f7ff  jz      short loc_18004F873
0x18004f801  lea     rax, [rsp+298h+hKey]
0x18004f806  mov     [rsp+298h+phkResult], rax; phkResult
0x18004f80b  lea     r9d, [rdi-1]; samDesired
0x18004f80f  xor     r8d, r8d; ulOptions
0x18004f812  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\W3"...
0x18004f819  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004f820  call    cs:__imp_RegOpenKeyExW
0x18004f827  nop     dword ptr [rax+rax+00h]
0x18004f82c  mov     edi, eax
0x18004f82e  test    eax, eax
0x18004f830  jnz     loc_18004F6E3
0x18004f836  mov     [rsp+298h+pcbData], rbx; pcbData
0x18004f83b  mov     [rsp+298h+pvData], rsi; pvData
0x18004f840  lea     rax, [rsp+298h+pdwType]
0x18004f845  mov     [rsp+298h+phkResult], rax; pdwType
0x18004f84a  lea     r9d, [rdi+2]; dwFlags
0x18004f84e  lea     r8, aNtpserver; "NtpServer"
0x18004f855  xor     edx, edx; lpSubKey
0x18004f857  mov     rcx, [rsp+298h+hKey]; hkey
0x18004f85c  call    cs:__imp_RegGetValueW
0x18004f863  nop     dword ptr [rax+rax+00h]
0x18004f868  mov     edi, eax
0x18004f86a  test    eax, eax
0x18004f86c  jz      short loc_18004F87B
0x18004f86e  jmp     loc_18004F758
0x18004f873  test    edi, edi
0x18004f875  jnz     loc_18004F75A
0x18004f87b  xor     ebx, ebx
0x18004f87d  mov     [rsp+298h+var_258], ebx
0x18004f881  test    rsi, rsi
0x18004f884  jz      short loc_18004F889
0x18004f886  mov     [r14], rsi
0x18004f889  test    ebx, ebx
0x18004f88b  jz      short loc_18004F8A1
0x18004f88d  test    rsi, rsi
0x18004f890  jz      short loc_18004F8A1
0x18004f892  mov     rcx, rsi; hMem
0x18004f895  call    cs:__imp_LocalFree
0x18004f89c  nop     dword ptr [rax+rax+00h]
0x18004f8a1  mov     rcx, [rsp+298h+hkey]; hKey
0x18004f8a6  test    rcx, rcx
0x18004f8a9  jz      short loc_18004F8B7
0x18004f8ab  call    cs:__imp_RegCloseKey
0x18004f8b2  nop     dword ptr [rax+rax+00h]
0x18004f8b7  mov     rcx, [rsp+298h+hKey]; hKey
0x18004f8bc  test    rcx, rcx
0x18004f8bf  jz      short loc_18004F8CD
0x18004f8c1  call    cs:__imp_RegCloseKey
0x18004f8c8  nop     dword ptr [rax+rax+00h]
0x18004f8cd  mov     eax, ebx
0x18004f8cf  mov     rcx, [rsp+298h+var_28]
0x18004f8d7  xor     rcx, rsp; StackCookie
0x18004f8da  call    __security_check_cookie
0x18004f8df  mov     rbx, [rsp+298h+arg_10]
0x18004f8e7  add     rsp, 280h
0x18004f8ee  pop     r14
0x18004f8f0  pop     rdi
0x18004f8f1  pop     rsi
0x18004f8f2  retn
0x18006a28e  push    rbp
0x18006a290  sub     rsp, 40h
0x18006a294  mov     rbp, rdx
0x18006a297  cmp     dword ptr [rbp+40h], 0
0x18006a29b  jz      short loc_18006A2B3
0x18006a29d  mov     rcx, [rbp+58h]; hMem
0x18006a2a1  test    rcx, rcx
0x18006a2a4  jz      short loc_18006A2B3
0x18006a2a6  call    cs:__imp_LocalFree
0x18006a2ad  nop     dword ptr [rax+rax+00h]
0x18006a2b2  nop
0x18006a2b3  mov     rcx, [rbp+48h]; hKey
0x18006a2b7  test    rcx, rcx
0x18006a2ba  jz      short loc_18006A2C9
0x18006a2bc  call    cs:__imp_RegCloseKey
0x18006a2c3  nop     dword ptr [rax+rax+00h]
0x18006a2c8  nop
0x18006a2c9  mov     rcx, [rbp+50h]; hKey
0x18006a2cd  test    rcx, rcx
0x18006a2d0  jz      short loc_18006A2DF
0x18006a2d2  call    cs:__imp_RegCloseKey
0x18006a2d9  nop     dword ptr [rax+rax+00h]
0x18006a2de  nop
0x18006a2df  add     rsp, 40h
0x18006a2e3  pop     rbp
0x18006a2e4  retn
```
