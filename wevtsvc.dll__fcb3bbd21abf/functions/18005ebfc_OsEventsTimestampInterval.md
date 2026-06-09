# OsEventsTimestampInterval

- ea: `0x18005ebfc`
- end: `0x18005ed9b`
- name: `OsEventsTimestampInterval`
- size: `415`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005eac4`
- `0x18005eda4`

## callees

- `0x180017b98`
- `0x18005ebfc`
- `0x18005fef4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005ec89`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005ecc6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005ed43`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005ec89`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005ecc6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005ed43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ed7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ed8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ed7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ed8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ec50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ed0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ec50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ed0e`

## pseudocode

```c
__int64 OsEventsTimestampInterval()
{
  unsigned int v0; // ebx
  HKEY hKey[3]; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+18h] BYREF
  unsigned int v4; // [rsp+68h] [rbp+20h] BYREF
  int Data; // [rsp+70h] [rbp+28h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+30h] BYREF

  v4 = 0;
  Data = 0;
  cbData = 0;
  if ( !(unsigned __int8)NtSetupKey() )
  {
    hKey[0] = 0;
    RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows NT\\Reliability", 0, 0x20019u, hKey);
    if ( hKey[0] )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey[0], L"TimeStampEnabled", 0, 0, (LPBYTE)&Data, &cbData) )
      {
        if ( !Data )
          goto LABEL_11;
        cbData = 4;
        if ( !RegQueryValueExW(hKey[0], L"TimeStampInterval", 0, 0, (LPBYTE)&v4, &cbData) )
        {
          v0 = v4;
          if ( v4 <= 0x15180 )
            goto LABEL_12;
        }
        v4 = 0;
      }
    }
    phkResult = 0;
    RegOpenKeyExW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Reliability",
      0,
      0x20019u,
      &phkResult);
    if ( phkResult )
    {
      cbData = 4;
      if ( !RegQueryValueExW(phkResult, L"TimeStampInterval", 0, 0, (LPBYTE)&v4, &cbData) )
      {
        v4 *= 60;
        v0 = v4;
        tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&phkResult);
        if ( v0 <= 0x15180 )
        {
LABEL_12:
          tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(hKey);
          return v0;
        }
LABEL_11:
        v0 = 0;
        goto LABEL_12;
      }
      if ( phkResult )
        RegCloseKey(phkResult);
    }
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
  }
  return 0;
}

```

## disassembly

```asm
0x18005ebfc  push    rbp
0x18005ebfe  push    rbx
0x18005ebff  mov     rbp, rsp
0x18005ec02  sub     rsp, 48h
0x18005ec06  mov     [rbp+arg_8], 0
0x18005ec0d  mov     [rbp+Data], 0
0x18005ec14  mov     [rbp+cbData], 0
0x18005ec1b  call    NtSetupKey
0x18005ec20  test    al, al
0x18005ec22  jnz     loc_18005ED92
0x18005ec28  lea     rax, [rbp+hKey]
0x18005ec2c  mov     [rbp+hKey], 0
0x18005ec34  mov     r9d, 20019h; samDesired
0x18005ec3a  mov     [rsp+48h+phkResult], rax; phkResult
0x18005ec3f  xor     r8d, r8d; ulOptions
0x18005ec42  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x18005ec49  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005ec50  call    cs:__imp_RegOpenKeyExW
0x18005ec56  mov     rcx, [rbp+hKey]; hKey
0x18005ec5a  test    rcx, rcx
0x18005ec5d  jz      loc_18005ECE6
0x18005ec63  lea     rax, [rbp+cbData]
0x18005ec67  mov     [rbp+cbData], 4
0x18005ec6e  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18005ec73  lea     rdx, aTimestampenabl; "TimeStampEnabled"
0x18005ec7a  lea     rax, [rbp+Data]
0x18005ec7e  xor     r9d, r9d; lpType
0x18005ec81  xor     r8d, r8d; lpReserved
0x18005ec84  mov     [rsp+48h+phkResult], rax; lpData
0x18005ec89  call    cs:__imp_RegQueryValueExW
0x18005ec8f  test    eax, eax
0x18005ec91  jnz     short loc_18005ECE6
0x18005ec93  cmp     [rbp+Data], eax
0x18005ec96  jz      loc_18005ED65
0x18005ec9c  mov     rcx, [rbp+hKey]; hKey
0x18005eca0  lea     rax, [rbp+cbData]
0x18005eca4  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18005eca9  lea     rdx, aTimestampinter; "TimeStampInterval"
0x18005ecb0  lea     rax, [rbp+arg_8]
0x18005ecb4  mov     [rbp+cbData], 4
0x18005ecbb  xor     r9d, r9d; lpType
0x18005ecbe  mov     [rsp+48h+phkResult], rax; lpData
0x18005ecc3  xor     r8d, r8d; lpReserved
0x18005ecc6  call    cs:__imp_RegQueryValueExW
0x18005eccc  test    eax, eax
0x18005ecce  jnz     short loc_18005ECDF
0x18005ecd0  mov     ebx, [rbp+arg_8]
0x18005ecd3  cmp     ebx, 15180h
0x18005ecd9  jbe     loc_18005ED67
0x18005ecdf  mov     [rbp+arg_8], 0
0x18005ece6  lea     rax, [rbp+arg_18]
0x18005ecea  mov     [rbp+arg_18], 0
0x18005ecf2  mov     r9d, 20019h; samDesired
0x18005ecf8  mov     [rsp+48h+phkResult], rax; phkResult
0x18005ecfd  xor     r8d, r8d; ulOptions
0x18005ed00  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005ed07  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005ed0e  call    cs:__imp_RegOpenKeyExW
0x18005ed14  mov     rcx, [rbp+arg_18]; hKey
0x18005ed18  test    rcx, rcx
0x18005ed1b  jz      short loc_18005ED83
0x18005ed1d  lea     rax, [rbp+cbData]
0x18005ed21  mov     [rbp+cbData], 4
0x18005ed28  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18005ed2d  lea     rdx, aTimestampinter; "TimeStampInterval"
0x18005ed34  lea     rax, [rbp+arg_8]
0x18005ed38  xor     r9d, r9d; lpType
0x18005ed3b  xor     r8d, r8d; lpReserved
0x18005ed3e  mov     [rsp+48h+phkResult], rax; lpData
0x18005ed43  call    cs:__imp_RegQueryValueExW
0x18005ed49  test    eax, eax
0x18005ed4b  jnz     short loc_18005ED74
0x18005ed4d  imul    ebx, [rbp+arg_8], 3Ch ; '<'
0x18005ed51  lea     rcx, [rbp+arg_18]
0x18005ed55  mov     [rbp+arg_8], ebx
0x18005ed58  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005ed5d  cmp     ebx, 15180h
0x18005ed63  jbe     short loc_18005ED67
0x18005ed65  xor     ebx, ebx
0x18005ed67  lea     rcx, [rbp+hKey]
0x18005ed6b  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18005ed70  mov     eax, ebx
0x18005ed72  jmp     short loc_18005ED94
0x18005ed74  mov     rcx, [rbp+arg_18]; hKey
0x18005ed78  test    rcx, rcx
0x18005ed7b  jz      short loc_18005ED83
0x18005ed7d  call    cs:__imp_RegCloseKey
0x18005ed83  mov     rcx, [rbp+hKey]; hKey
0x18005ed87  test    rcx, rcx
0x18005ed8a  jz      short loc_18005ED92
0x18005ed8c  call    cs:__imp_RegCloseKey
0x18005ed92  xor     eax, eax
0x18005ed94  add     rsp, 48h
0x18005ed98  pop     rbx
0x18005ed99  pop     rbp
0x18005ed9a  retn
```
