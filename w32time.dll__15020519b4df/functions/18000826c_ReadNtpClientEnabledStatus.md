# ReadNtpClientEnabledStatus

- ea: `0x18000826c`
- end: `0x18000851a`
- name: `ReadNtpClientEnabledStatus`
- size: `686`
- prototype: `__int64 __fastcall(PVOID pvData)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180007800`

## callees

- `0x18000826c`
- `0x180018138`
- `0x18001d9a0`
- `0x18003d270`
- `0x18003dd2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000842d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000842d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000831e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008462`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000831e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008462`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800084fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000850c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180064363`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180064379`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800084fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000850c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180064363`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180064379`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008367`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800084ab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008367`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800084ab`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800082eb`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800082eb`

## string_xrefs

- `0x1800082dd`: `System\CurrentControlSet\Services\W32Time\TimeProviders\NtpClient`
- `0x180008403`: `System\CurrentControlSet\Services\W32Time\TimeProviders\NtpClient`
- `0x180008421`: `System\CurrentControlSet\Services\W32Time\TimeProviders\NtpClient`
- `0x180008454`: `System\CurrentControlSet\Services\W32Time\TimeProviders\NtpClient`
- `0x1800083a0`: `ReadNtpClientEnabledStatus:RegGetValue. Error: 0x%x\n`
- `0x1800083cc`: `ReadNtpClientEnabledStatus:RegOpenKeyEx. Error: 0x%x\n`

## pseudocode

```c
__int64 __fastcall ReadNtpClientEnabledStatus(PVOID pvData)
{
  int PersistedRegistryLocationW; // edi
  LSTATUS v3; // edi
  LSTATUS ValueW; // edi
  bool v5; // cc
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  DWORD pcbData; // [rsp+40h] [rbp-248h] BYREF
  DWORD pdwType; // [rsp+44h] [rbp-244h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-240h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-238h] BYREF
  WCHAR SubKey; // [rsp+60h] [rbp-228h] BYREF
  _BYTE v14[526]; // [rsp+62h] [rbp-226h] BYREF

  pcbData = 0;
  hkey = 0;
  hKey = 0;
  SubKey = 0;
  memset_0(v14, 0, 0x206u);
  pdwType = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"W32TimeNtpClient",
                                 L"System\\CurrentControlSet\\Services\\W32Time\\TimeProviders\\NtpClient",
                                 &SubKey,
                                 520,
                                 0);
  if ( PersistedRegistryLocationW )
  {
    if ( PersistedRegistryLocationW > 0 )
      v6 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    else
      v6 = PersistedRegistryLocationW;
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(
        L"Failed to get time regkey %s. Error: 0x%x\n",
        L"System\\CurrentControlSet\\Services\\W32Time\\TimeProviders\\NtpClient",
        (unsigned int)PersistedRegistryLocationW);
  }
  else
  {
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, &SubKey, 0, 1u, &hkey);
    if ( !v3 )
    {
      pcbData = 4;
      ValueW = RegGetValueW(hkey, 0, L"Enabled", 0x18u, &pdwType, pvData, &pcbData);
      if ( ValueW != 2
        || !(unsigned int)_o__wcsnicmp(
                            &SubKey,
                            L"System\\CurrentControlSet\\Services\\W32Time\\TimeProviders\\NtpClient",
                            259) )
      {
        v5 = ValueW <= 0;
        if ( ValueW )
          goto LABEL_5;
        goto LABEL_24;
      }
      v3 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\W32Time\\TimeProviders\\NtpClient",
             0,
             1u,
             &hKey);
      if ( !v3 )
      {
        pcbData = 4;
        v7 = RegGetValueW(hKey, 0, L"Enabled", 0x18u, &pdwType, pvData, &pcbData);
        ValueW = v7;
        if ( v7 )
        {
          v5 = v7 < 0;
LABEL_5:
          if ( v5 )
            v6 = ValueW;
          else
            v6 = (unsigned __int16)ValueW | 0x80070000;
          if ( (unsigned __int8)FileLogAllowEntry(0) )
            FileLogAdd(L"ReadNtpClientEnabledStatus:RegGetValue. Error: 0x%x\n", (unsigned int)ValueW);
          goto LABEL_25;
        }
LABEL_24:
        v6 = 0;
        goto LABEL_25;
      }
    }
    if ( v3 > 0 )
      v6 = (unsigned __int16)v3 | 0x80070000;
    else
      v6 = v3;
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"ReadNtpClientEnabledStatus:RegOpenKeyEx. Error: 0x%x\n", (unsigned int)v3);
  }
LABEL_25:
  if ( hKey )
    RegCloseKey(hKey);
  if ( hkey )
    RegCloseKey(hkey);
  return v6;
}

```

## disassembly

```asm
0x18000826c  mov     [rsp+arg_8], rbx
0x180008271  push    rdi
0x180008272  sub     rsp, 280h
0x180008279  mov     rax, cs:__security_cookie
0x180008280  xor     rax, rsp
0x180008283  mov     [rsp+288h+var_18], rax
0x18000828b  mov     rbx, rcx
0x18000828e  mov     [rsp+288h+var_248], 0
0x180008296  mov     [rsp+288h+hkey], 0
0x18000829f  mov     [rsp+288h+hKey], 0
0x1800082a8  xor     eax, eax
0x1800082aa  mov     [rsp+288h+SubKey], ax
0x1800082af  xor     edx, edx; Val
0x1800082b1  mov     r8d, 206h; Size
0x1800082b7  lea     rcx, [rsp+288h+var_226]; void *
0x1800082bc  call    memset_0
0x1800082c1  mov     [rsp+288h+pdwType], 0
0x1800082c9  mov     [rsp+288h+phkResult], 0
0x1800082d2  mov     r9d, 208h
0x1800082d8  lea     r8, [rsp+288h+SubKey]
0x1800082dd  lea     rdx, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\W3"...
0x1800082e4  lea     rcx, aW32timentpclie; "W32TimeNtpClient"
0x1800082eb  call    cs:__imp_GetPersistedRegistryLocationW
0x1800082f2  nop     dword ptr [rax+rax+00h]
0x1800082f7  mov     edi, eax
0x1800082f9  test    eax, eax
0x1800082fb  jnz     loc_1800083E0
0x180008301  lea     rax, [rsp+288h+hkey]
0x180008306  mov     [rsp+288h+phkResult], rax; phkResult
0x18000830b  lea     r9d, [rdi+1]; samDesired
0x18000830f  xor     r8d, r8d; ulOptions
0x180008312  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x180008317  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000831e  call    cs:__imp_RegOpenKeyExW
0x180008325  nop     dword ptr [rax+rax+00h]
0x18000832a  mov     edi, eax
0x18000832c  test    eax, eax
0x18000832e  jnz     loc_1800083B7
0x180008334  mov     [rsp+288h+var_248], 4
0x18000833c  lea     rax, [rsp+288h+var_248]
0x180008341  mov     [rsp+288h+pcbData], rax; pcbData
0x180008346  mov     [rsp+288h+pvData], rbx; pvData
0x18000834b  lea     rax, [rsp+288h+pdwType]
0x180008350  mov     [rsp+288h+phkResult], rax; pdwType
0x180008355  lea     r9d, [rdi+18h]; dwFlags
0x180008359  lea     r8, aEnabled; "Enabled"
0x180008360  xor     edx, edx; lpSubKey
0x180008362  mov     rcx, [rsp+288h+hkey]; hkey
0x180008367  call    cs:__imp_RegGetValueW
0x18000836e  nop     dword ptr [rax+rax+00h]
0x180008373  mov     edi, eax
0x180008375  cmp     eax, 2
0x180008378  jz      loc_18000841B
0x18000837e  test    edi, edi
0x180008380  jz      loc_1800084C4
0x180008386  jle     short loc_1800083B3
0x180008388  movzx   ebx, di
0x18000838b  or      ebx, 80070000h
0x180008391  xor     ecx, ecx
0x180008393  call    FileLogAllowEntry
0x180008398  test    al, al
0x18000839a  jz      loc_1800084C6
0x1800083a0  lea     rcx, aReadntpcliente; "ReadNtpClientEnabledStatus:RegGetValue."...
0x1800083a7  mov     edx, edi
0x1800083a9  call    FileLogAdd
0x1800083ae  jmp     loc_1800084C6
0x1800083b3  mov     ebx, edi
0x1800083b5  jmp     short loc_180008391
0x1800083b7  test    edi, edi
0x1800083b9  jg      short loc_1800083D5
0x1800083bb  mov     ebx, edi
0x1800083bd  xor     ecx, ecx
0x1800083bf  call    FileLogAllowEntry
0x1800083c4  test    al, al
0x1800083c6  jz      loc_1800084C6
0x1800083cc  lea     rcx, aReadntpcliente_0; "ReadNtpClientEnabledStatus:RegOpenKeyEx"...
0x1800083d3  jmp     short loc_1800083A7
0x1800083d5  movzx   ebx, di
0x1800083d8  or      ebx, 80070000h
0x1800083de  jmp     short loc_1800083BD
0x1800083e0  test    edi, edi
0x1800083e2  jg      short loc_1800083E8
0x1800083e4  mov     ebx, edi
0x1800083e6  jmp     short loc_1800083F1
0x1800083e8  movzx   ebx, di
0x1800083eb  or      ebx, 80070000h
0x1800083f1  xor     ecx, ecx
0x1800083f3  call    FileLogAllowEntry
0x1800083f8  test    al, al
0x1800083fa  jz      loc_1800084C6
0x180008400  mov     r8d, edi
0x180008403  lea     rdx, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\W3"...
0x18000840a  lea     rcx, aFailedToGetTim; "Failed to get time regkey %s. Error: 0x"...
0x180008411  call    FileLogAdd
0x180008416  jmp     loc_1800084C6
0x18000841b  mov     r8d, 103h
0x180008421  lea     rdx, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\W3"...
0x180008428  lea     rcx, [rsp+288h+SubKey]
0x18000842d  call    cs:__imp__o__wcsnicmp
0x180008434  nop     dword ptr [rax+rax+00h]
0x180008439  test    eax, eax
0x18000843b  jz      loc_18000837E
0x180008441  lea     rax, [rsp+288h+hKey]
0x180008446  mov     [rsp+288h+phkResult], rax; phkResult
0x18000844b  mov     r9d, 1; samDesired
0x180008451  xor     r8d, r8d; ulOptions
0x180008454  lea     rdx, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\W3"...
0x18000845b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008462  call    cs:__imp_RegOpenKeyExW
0x180008469  nop     dword ptr [rax+rax+00h]
0x18000846e  mov     edi, eax
0x180008470  test    eax, eax
0x180008472  jnz     loc_1800083B7
0x180008478  mov     [rsp+288h+var_248], 4
0x180008480  lea     rax, [rsp+288h+var_248]
0x180008485  mov     [rsp+288h+pcbData], rax; pcbData
0x18000848a  mov     [rsp+288h+pvData], rbx; pvData
0x18000848f  lea     rax, [rsp+288h+pdwType]
0x180008494  mov     [rsp+288h+phkResult], rax; pdwType
0x180008499  lea     r9d, [rdi+18h]; dwFlags
0x18000849d  lea     r8, aEnabled; "Enabled"
0x1800084a4  xor     edx, edx; lpSubKey
0x1800084a6  mov     rcx, [rsp+288h+hKey]; hkey
0x1800084ab  call    cs:__imp_RegGetValueW
0x1800084b2  nop     dword ptr [rax+rax+00h]
0x1800084b7  mov     edi, eax
0x1800084b9  test    eax, eax
0x1800084bb  jz      short loc_1800084C4
0x1800084bd  test    eax, eax
0x1800084bf  jmp     loc_180008386
0x1800084c4  xor     ebx, ebx
0x1800084c6  mov     rcx, [rsp+288h+hKey]; hKey
0x1800084cb  test    rcx, rcx
0x1800084ce  jnz     short loc_1800084FE
0x1800084d0  mov     rcx, [rsp+288h+hkey]; hKey
0x1800084d5  test    rcx, rcx
0x1800084d8  jnz     short loc_18000850C
0x1800084da  mov     eax, ebx
0x1800084dc  mov     rcx, [rsp+288h+var_18]
0x1800084e4  xor     rcx, rsp; StackCookie
0x1800084e7  call    __security_check_cookie
0x1800084ec  mov     rbx, [rsp+288h+arg_8]
0x1800084f4  add     rsp, 280h
0x1800084fb  pop     rdi
0x1800084fc  retn
0x1800084fe  call    cs:__imp_RegCloseKey
0x180008505  nop     dword ptr [rax+rax+00h]
0x18000850a  jmp     short loc_1800084D0
0x18000850c  call    cs:__imp_RegCloseKey
0x180008513  nop     dword ptr [rax+rax+00h]
0x180008518  jmp     short loc_1800084DA
0x180064351  push    rbp
0x180064353  sub     rsp, 40h
0x180064357  mov     rbp, rdx
0x18006435a  mov     rcx, [rbp+48h]; hKey
0x18006435e  test    rcx, rcx
0x180064361  jz      short loc_180064370
0x180064363  call    cs:__imp_RegCloseKey
0x18006436a  nop     dword ptr [rax+rax+00h]
0x18006436f  nop
0x180064370  mov     rcx, [rbp+50h]; hKey
0x180064374  test    rcx, rcx
0x180064377  jz      short loc_180064386
0x180064379  call    cs:__imp_RegCloseKey
0x180064380  nop     dword ptr [rax+rax+00h]
0x180064385  nop
0x180064386  add     rsp, 40h
0x18006438a  pop     rbp
0x18006438b  retn
```
