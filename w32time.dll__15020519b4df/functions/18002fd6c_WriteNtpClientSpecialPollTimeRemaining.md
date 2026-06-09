# WriteNtpClientSpecialPollTimeRemaining

- ea: `0x18002fd6c`
- end: `0x18002ff1c`
- name: `WriteNtpClientSpecialPollTimeRemaining`
- size: `432`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180017a70`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18002fd6c`
- `0x18003d270`
- `0x18003dd2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fe46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fe46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fee8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067bfa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fee8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067bfa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fea5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fea5`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002fdda`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002fdda`

## string_xrefs

- `0x18002fdcc`: `System\CurrentControlSet\Services\W32Time\TimeProviders\NtpClient`
- `0x18002fe0f`: `System\CurrentControlSet\Services\W32Time\TimeProviders\NtpClient`
- `0x18002fe74`: `WriteNtpClientSpecialPollTimeRemaining:RegOpenKeyEx. Error: 0x%x\n`
- `0x18002fed3`: `WriteNtpClientSpecialPollTimeRemaining:RegSetValueEx. Error: 0x%x\n`

## pseudocode

```c
__int64 __fastcall WriteNtpClientSpecialPollTimeRemaining(BYTE *lpData, int a2)
{
  int PersistedRegistryLocationW; // eax
  unsigned int v5; // edi
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  unsigned int v8; // edi
  LSTATUS v9; // eax
  unsigned int v10; // edi
  HKEY hKey; // [rsp+30h] [rbp-238h] BYREF
  WCHAR SubKey; // [rsp+40h] [rbp-228h] BYREF
  _BYTE v14[526]; // [rsp+42h] [rbp-226h] BYREF

  SubKey = 0;
  memset_0(v14, 0, 0x206u);
  hKey = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"W32TimeNtpClient",
                                 L"System\\CurrentControlSet\\Services\\W32Time\\TimeProviders\\NtpClient",
                                 &SubKey,
                                 520,
                                 0);
  v5 = PersistedRegistryLocationW;
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
        v5);
  }
  else
  {
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, &SubKey, 0, 2u, &hKey);
    v8 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0x80070000;
      else
        v6 = v7;
      if ( (unsigned __int8)FileLogAllowEntry(0) )
        FileLogAdd(L"WriteNtpClientSpecialPollTimeRemaining:RegOpenKeyEx. Error: 0x%x\n", v8);
    }
    else
    {
      v9 = RegSetValueExW(hKey, L"SpecialPollTimeRemaining", 0, 7u, lpData, 2 * a2);
      v10 = v9;
      if ( v9 )
      {
        if ( v9 > 0 )
          v6 = (unsigned __int16)v9 | 0x80070000;
        else
          v6 = v9;
        if ( (unsigned __int8)FileLogAllowEntry(0) )
          FileLogAdd(L"WriteNtpClientSpecialPollTimeRemaining:RegSetValueEx. Error: 0x%x\n", v10);
      }
      else
      {
        v6 = 0;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x18002fd6c  mov     [rsp+arg_10], rbx
0x18002fd71  mov     [rsp+arg_18], rsi
0x18002fd76  push    rdi
0x18002fd77  sub     rsp, 260h
0x18002fd7e  mov     rax, cs:__security_cookie
0x18002fd85  xor     rax, rsp
0x18002fd88  mov     [rsp+268h+var_18], rax
0x18002fd90  mov     rsi, rdx
0x18002fd93  mov     rbx, rcx
0x18002fd96  xor     eax, eax
0x18002fd98  mov     [rsp+268h+SubKey], ax
0x18002fd9d  xor     edx, edx; Val
0x18002fd9f  mov     r8d, 206h; Size
0x18002fda5  lea     rcx, [rsp+268h+var_226]; void *
0x18002fdaa  call    memset_0
0x18002fdaf  mov     [rsp+268h+hKey], 0
0x18002fdb8  mov     [rsp+268h+phkResult], 0
0x18002fdc1  mov     r9d, 208h
0x18002fdc7  lea     r8, [rsp+268h+SubKey]
0x18002fdcc  lea     rdx, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\W3"...
0x18002fdd3  lea     rcx, aW32timentpclie; "W32TimeNtpClient"
0x18002fdda  call    cs:__imp_GetPersistedRegistryLocationW
0x18002fde1  nop     dword ptr [rax+rax+00h]
0x18002fde6  mov     edi, eax
0x18002fde8  test    eax, eax
0x18002fdea  jz      short loc_18002FE27
0x18002fdec  test    eax, eax
0x18002fdee  jg      short loc_18002FDF4
0x18002fdf0  mov     ebx, eax
0x18002fdf2  jmp     short loc_18002FDFD
0x18002fdf4  movzx   ebx, di
0x18002fdf7  or      ebx, 80070000h
0x18002fdfd  xor     ecx, ecx
0x18002fdff  call    FileLogAllowEntry
0x18002fe04  test    al, al
0x18002fe06  jz      loc_18002FEDE
0x18002fe0c  mov     r8d, edi
0x18002fe0f  lea     rdx, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\W3"...
0x18002fe16  lea     rcx, aFailedToGetTim; "Failed to get time regkey %s. Error: 0x"...
0x18002fe1d  call    FileLogAdd
0x18002fe22  jmp     loc_18002FEDE
0x18002fe27  lea     rax, [rsp+268h+hKey]
0x18002fe2c  mov     [rsp+268h+phkResult], rax; phkResult
0x18002fe31  mov     r9d, 2; samDesired
0x18002fe37  xor     r8d, r8d; ulOptions
0x18002fe3a  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x18002fe3f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002fe46  call    cs:__imp_RegOpenKeyExW
0x18002fe4d  nop     dword ptr [rax+rax+00h]
0x18002fe52  mov     edi, eax
0x18002fe54  test    eax, eax
0x18002fe56  jz      short loc_18002FE84
0x18002fe58  test    eax, eax
0x18002fe5a  jg      short loc_18002FE60
0x18002fe5c  mov     ebx, eax
0x18002fe5e  jmp     short loc_18002FE69
0x18002fe60  movzx   ebx, di
0x18002fe63  or      ebx, 80070000h
0x18002fe69  xor     ecx, ecx
0x18002fe6b  call    FileLogAllowEntry
0x18002fe70  test    al, al
0x18002fe72  jz      short loc_18002FEDE
0x18002fe74  lea     rcx, aWritentpclient_1; "WriteNtpClientSpecialPollTimeRemaining:"...
0x18002fe7b  mov     edx, edi
0x18002fe7d  call    FileLogAdd
0x18002fe82  jmp     short loc_18002FEDE
0x18002fe84  lea     eax, [rsi+rsi]
0x18002fe87  mov     [rsp+268h+cbData], eax; cbData
0x18002fe8b  mov     [rsp+268h+phkResult], rbx; lpData
0x18002fe90  mov     r9d, 7; dwType
0x18002fe96  xor     r8d, r8d; Reserved
0x18002fe99  lea     rdx, aSpecialpolltim; "SpecialPollTimeRemaining"
0x18002fea0  mov     rcx, [rsp+268h+hKey]; hKey
0x18002fea5  call    cs:__imp_RegSetValueExW
0x18002feac  nop     dword ptr [rax+rax+00h]
0x18002feb1  mov     edi, eax
0x18002feb3  test    eax, eax
0x18002feb5  jz      short loc_18002FEDC
0x18002feb7  test    eax, eax
0x18002feb9  jg      short loc_18002FEBF
0x18002febb  mov     ebx, eax
0x18002febd  jmp     short loc_18002FEC8
0x18002febf  movzx   ebx, di
0x18002fec2  or      ebx, 80070000h
0x18002fec8  xor     ecx, ecx
0x18002feca  call    FileLogAllowEntry
0x18002fecf  test    al, al
0x18002fed1  jz      short loc_18002FEDE
0x18002fed3  lea     rcx, aWritentpclient; "WriteNtpClientSpecialPollTimeRemaining:"...
0x18002feda  jmp     short loc_18002FE7B
0x18002fedc  xor     ebx, ebx
0x18002fede  mov     rcx, [rsp+268h+hKey]; hKey
0x18002fee3  test    rcx, rcx
0x18002fee6  jz      short loc_18002FEF4
0x18002fee8  call    cs:__imp_RegCloseKey
0x18002feef  nop     dword ptr [rax+rax+00h]
0x18002fef4  mov     eax, ebx
0x18002fef6  mov     rcx, [rsp+268h+var_18]
0x18002fefe  xor     rcx, rsp; StackCookie
0x18002ff01  call    __security_check_cookie
0x18002ff06  lea     r11, [rsp+268h+var_8]
0x18002ff0e  mov     rbx, [r11+20h]
0x18002ff12  mov     rsi, [r11+28h]
0x18002ff16  mov     rsp, r11
0x18002ff19  pop     rdi
0x18002ff1a  retn
0x180067be8  push    rbp
0x180067bea  sub     rsp, 30h
0x180067bee  mov     rbp, rdx
0x180067bf1  mov     rcx, [rbp+30h]; hKey
0x180067bf5  test    rcx, rcx
0x180067bf8  jz      short loc_180067C07
0x180067bfa  call    cs:__imp_RegCloseKey
0x180067c01  nop     dword ptr [rax+rax+00h]
0x180067c06  nop
0x180067c07  add     rsp, 30h
0x180067c0b  pop     rbp
0x180067c0c  retn
```
