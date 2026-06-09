# ReadNtpServerConfig(NtpServerConfig * *)

- ea: `0x180025c14`
- end: `0x1800261eb`
- name: `?ReadNtpServerConfig@@YAJPEAPEAUNtpServerConfig@@@Z`
- size: `1495`
- prototype: `__int64 __fastcall(struct NtpServerConfig **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002522c`
- `0x1800468c0`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x180025c14`
- `0x1800273a0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002613b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002613b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025c5d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025c5d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025c9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025e66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025fb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025c9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025e66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025fb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002615c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026172`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026188`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002619e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800261b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800261ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002615c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026172`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026188`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002619e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800261b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800261ca`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180025cf5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180025d6f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180025df2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180025cf5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180025d6f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180025df2`

## string_xrefs

- `0x180025cce`: `AllowNonstandardModeCombinations`
- `0x180025d27`: `AllowNonstandardModeCombinations`
- `0x180025f6e`: `System\CurrentControlSet\Services\W32Time\Parameters`
- `0x180025e58`: `Software\Policies\Microsoft\W32Time\Config`
- `0x180025e81`: `Software\Policies\Microsoft\W32Time\Config`
- `0x180025c8d`: `System\CurrentControlSet\Services\W32Time\TimeProviders\NtpServer`
- `0x180025f5a`: `System\CurrentControlSet\Services\W32Time\TimeProviders\NtpServer`
- `0x180025d31`: `ReadConfig: '%s'=0x%08X (%d)\n`
- `0x180025db4`: `ReadConfig: '%s'=0x%08X (%d)\n`
- `0x180025e39`: `ReadConfig: '%s'=0x%08X (%d)\n`
- `0x180025f05`: `ReadConfig: '%s'=0x%08X (%d)\n`
- `0x18002610f`: `ReadConfig: '%s'=0x%08X (%d)\n`
- `0x180025e88`: `ReadConfig: failed to open '%s' key, treating as non-fatal\n`
- `0x1800260f2`: `ReadConfig: '%s'=0x%08X (%d) [Using Default]\n`

## pseudocode

```c
__int64 __fastcall ReadNtpServerConfig(struct NtpServerConfig **a1)
{
  unsigned int *pvData; // rdi
  unsigned int v3; // ebx
  LSTATUS ValueW; // eax
  bool v5; // cc
  int v6; // ebx
  unsigned int *v7; // rsi
  int v8; // eax
  unsigned int *v9; // rsi
  unsigned int *v10; // rbx
  unsigned int *v11; // rsi
  unsigned int v12; // esi
  LSTATUS v13; // eax
  unsigned int v14; // ebx
  unsigned int *v15; // r15
  unsigned int *v16; // r14
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v19; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v20; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v21; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v22; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpSubKey; // [rsp+70h] [rbp-90h]
  PHKEY v24; // [rsp+78h] [rbp-88h]
  __int64 v25; // [rsp+80h] [rbp-80h]
  const WCHAR *v26; // [rsp+88h] [rbp-78h]
  HKEY *v27; // [rsp+90h] [rbp-70h]
  unsigned int *v28; // [rsp+98h] [rbp-68h]
  const WCHAR *v29; // [rsp+A0h] [rbp-60h]
  HKEY *v30; // [rsp+A8h] [rbp-58h]
  const wchar_t *v31; // [rsp+B0h] [rbp-50h]
  const WCHAR *v32; // [rsp+B8h] [rbp-48h]
  HKEY *v33; // [rsp+C0h] [rbp-40h]
  int v34; // [rsp+C8h] [rbp-38h]
  const wchar_t *v35; // [rsp+D0h] [rbp-30h]
  unsigned int *v36; // [rsp+D8h] [rbp-28h]
  unsigned int *v37; // [rsp+E0h] [rbp-20h]
  int v38; // [rsp+E8h] [rbp-18h]
  const wchar_t *v39; // [rsp+F0h] [rbp-10h]
  unsigned int *v40; // [rsp+F8h] [rbp-8h]
  unsigned int *v41; // [rsp+100h] [rbp+0h]
  int v42; // [rsp+108h] [rbp+8h]
  DWORD pcbData; // [rsp+158h] [rbp+58h] BYREF
  DWORD pdwType; // [rsp+160h] [rbp+60h] BYREF
  HKEY hkey; // [rsp+168h] [rbp+68h] BYREF

  pcbData = 0;
  pdwType = 0;
  hkey = 0;
  hKey = 0;
  v19 = 0;
  v21 = 0;
  v20 = 0;
  v22 = 0;
  pvData = (unsigned int *)LocalAlloc(0x40u, 0x48u);
  if ( !pvData )
  {
    v3 = -2147024882;
    goto LABEL_49;
  }
  ValueW = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\W32Time\\TimeProviders\\NtpServer",
             0,
             0x20019u,
             &hkey);
  v3 = ValueW;
  v5 = ValueW <= 0;
  if ( ValueW
    || (pcbData = 4,
        ValueW = RegGetValueW(hkey, 0, L"AllowNonstandardModeCombinations", 0xFFFFu, &pdwType, pvData, &pcbData),
        v3 = ValueW,
        v5 = ValueW <= 0,
        ValueW) )
  {
    if ( !v5 )
      v3 = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_47;
  }
  if ( pdwType != 4 )
    goto LABEL_46;
  v6 = 2;
  pvData[2] = 2;
  if ( (unsigned __int8)FileLogAllowEntry(112) )
    FileLogAdd(L"ReadConfig: '%s'=0x%08X (%d)\n", L"AllowNonstandardModeCombinations", *pvData, pvData[2]);
  v7 = pvData + 1;
  pcbData = 4;
  if ( RegGetValueW(hkey, 0, L"EventLogFlags", 0xFFFFu, &pdwType, pvData + 1, &pcbData) )
  {
    *v7 = 0;
    v8 = 1;
  }
  else
  {
    if ( pdwType != 4 )
      goto LABEL_46;
    v8 = 2;
  }
  pvData[2] = v8;
  if ( (unsigned __int8)FileLogAllowEntry(112) )
    FileLogAdd(L"ReadConfig: '%s'=0x%08X (%d)\n", L"EventLogFlags", *v7, pvData[3]);
  v9 = pvData + 16;
  pcbData = 4;
  if ( RegGetValueW(hkey, 0, L"UnsecureTimeSyncRequestsLogThrottlePeriod", 0xFFFFu, &pdwType, pvData + 16, &pcbData) )
  {
    *v9 = 86400000;
    v6 = 1;
    goto LABEL_19;
  }
  if ( pdwType != 4 )
  {
LABEL_46:
    v3 = -2147418113;
LABEL_47:
    LocalFree(pvData);
    goto LABEL_49;
  }
LABEL_19:
  pvData[17] = v6;
  if ( (unsigned __int8)FileLogAllowEntry(112) )
    FileLogAdd(L"ReadConfig: '%s'=0x%08X (%d)\n", L"UnsecureTimeSyncRequestsLogThrottlePeriod", *v9);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\W32Time\\Config", 0, 0x20019u, &hKey)
    && (unsigned __int8)FileLogAllowEntry(112) )
  {
    FileLogAdd(
      L"ReadConfig: failed to open '%s' key, treating as non-fatal\n",
      L"Software\\Policies\\Microsoft\\W32Time\\Config");
  }
  v10 = pvData + 15;
  v11 = pvData + 14;
  pcbData = 4;
  if ( (int)MyRegQueryPolicyValueEx(
              hkey,
              hKey,
              L"RequireSecureTimeSyncRequests",
              &pdwType,
              pvData + 14,
              (__int64)&pcbData,
              (__int64)(pvData + 15)) >= 0 )
  {
    if ( pdwType == 4 )
      goto LABEL_27;
    goto LABEL_46;
  }
  *v11 = 0;
  *v10 = 1;
LABEL_27:
  if ( (unsigned __int8)FileLogAllowEntry(112) )
    FileLogAdd(L"ReadConfig: '%s'=0x%08X (%d)\n", L"RequireSecureTimeSyncRequests", *v11, *v10);
  if ( *((_BYTE *)g_pnpstate + 508) )
  {
    LOBYTE(v25) = 0;
    lpSubKey = L"Software\\Policies\\Microsoft\\W32Time\\TimeProviders\\NtpServer";
    v12 = 0;
    LOBYTE(v28) = 0;
    v24 = &v19;
    v26 = L"Software\\Policies\\Microsoft\\W32Time\\Parameters";
    v27 = &v21;
    v29 = L"System\\CurrentControlSet\\Services\\W32Time\\TimeProviders\\NtpServer";
    v30 = &v20;
    v32 = L"System\\CurrentControlSet\\Services\\W32Time\\Parameters";
    v33 = &v22;
    LOBYTE(v31) = 1;
    LOBYTE(v34) = 1;
    while ( v12 < 4 )
    {
      v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (&lpSubKey)[3 * v12], 0, 0x20019u, (&v24)[3 * v12]);
      v3 = v13;
      if ( v13 )
      {
        if ( v13 > 0 )
          v3 = (unsigned __int16)v13 | 0x80070000;
        if ( *((_BYTE *)&v25 + 24 * v12) )
          goto LABEL_47;
      }
      ++v12;
    }
    LODWORD(v26) = 4;
    lpSubKey = L"ChainEntryTimeout";
    v14 = 0;
    LODWORD(v30) = 128;
    v24 = (PHKEY)(pvData + 4);
    v25 = (__int64)(pvData + 5);
    v27 = (HKEY *)L"ChainMaxEntries";
    v28 = pvData + 6;
    v29 = (const WCHAR *)(pvData + 7);
    v31 = L"ChainMaxHostEntries";
    v32 = (const WCHAR *)(pvData + 8);
    v33 = (HKEY *)(pvData + 9);
    v35 = L"ChainDisable";
    v36 = pvData + 10;
    v37 = pvData + 11;
    v39 = L"ChainLoggingRate";
    v40 = pvData + 12;
    v41 = pvData + 13;
    v34 = 4;
    v38 = 0;
    v42 = 30;
    while ( v14 < 5 )
    {
      pcbData = 4;
      v15 = (unsigned int *)*(&v25 + 4 * v14);
      v16 = (unsigned int *)(&v24)[4 * v14];
      if ( (unsigned int)MyRegQueryPolicyValueEx(
                           v20,
                           v19,
                           (&lpSubKey)[4 * v14],
                           &pdwType,
                           v16,
                           (__int64)&pcbData,
                           (__int64)v15) )
      {
        *v16 = (unsigned int)(&v26)[4 * v14];
        if ( (unsigned __int8)FileLogAllowEntry(112) )
          FileLogAdd(L"ReadConfig: '%s'=0x%08X (%d) [Using Default]\n", (&lpSubKey)[4 * v14], *v16, *v15);
      }
      else
      {
        if ( pdwType != 4 )
          goto LABEL_46;
        if ( (unsigned __int8)FileLogAllowEntry(112) )
          FileLogAdd(L"ReadConfig: '%s'=0x%08X (%d)\n", (&lpSubKey)[4 * v14], *v16, *v15);
      }
      ++v14;
    }
  }
  v3 = 0;
  *a1 = (struct NtpServerConfig *)pvData;
LABEL_49:
  if ( hkey )
    RegCloseKey(hkey);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v19 )
    RegCloseKey(v19);
  if ( v21 )
    RegCloseKey(v21);
  if ( v20 )
    RegCloseKey(v20);
  if ( v22 )
    RegCloseKey(v22);
  return v3;
}

```

## disassembly

```asm
0x180025c14  push    rbp
0x180025c16  push    rbx
0x180025c17  push    rsi
0x180025c18  push    rdi
0x180025c19  push    r13
0x180025c1b  push    r14
0x180025c1d  push    r15
0x180025c1f  lea     rbp, [rsp-10h]
0x180025c24  sub     rsp, 110h
0x180025c2b  xor     r15d, r15d
0x180025c2e  mov     r13, rcx
0x180025c31  mov     [rbp+40h+arg_8], r15d
0x180025c35  mov     [rbp+40h+pdwType], r15d
0x180025c39  mov     [rbp+40h+hkey], r15
0x180025c3d  lea     edx, [r15+48h]; uBytes
0x180025c41  mov     [rsp+140h+hKey], r15
0x180025c46  lea     ecx, [rdx-8]; uFlags
0x180025c49  mov     [rsp+140h+var_F8], r15
0x180025c4e  mov     [rsp+140h+var_E8], r15
0x180025c53  mov     [rsp+140h+var_F0], r15
0x180025c58  mov     [rsp+140h+var_E0], r15
0x180025c5d  call    cs:__imp_LocalAlloc
0x180025c64  nop     dword ptr [rax+rax+00h]
0x180025c69  mov     rdi, rax
0x180025c6c  test    rax, rax
0x180025c6f  jnz     short loc_180025C7B
0x180025c71  mov     ebx, 8007000Eh
0x180025c76  jmp     loc_180026153
0x180025c7b  lea     rax, [rbp+40h+hkey]
0x180025c7f  mov     r9d, 20019h; samDesired
0x180025c85  xor     r8d, r8d; ulOptions
0x180025c88  mov     [rsp+140h+phkResult], rax; phkResult
0x180025c8d  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\W3"...
0x180025c94  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025c9b  call    cs:__imp_RegOpenKeyExW
0x180025ca2  nop     dword ptr [rax+rax+00h]
0x180025ca7  mov     ebx, eax
0x180025ca9  test    eax, eax
0x180025cab  jz      short loc_180025CC1
0x180025cad  jle     loc_180026138
0x180025cb3  movzx   ebx, ax
0x180025cb6  or      ebx, 80070000h
0x180025cbc  jmp     loc_180026138
0x180025cc1  mov     rcx, [rbp+40h+hkey]; hkey
0x180025cc5  lea     rax, [rbp+40h+arg_8]
0x180025cc9  mov     [rsp+140h+pcbData], rax; pcbData
0x180025cce  lea     r8, aAllownonstanda; "AllowNonstandardModeCombinations"
0x180025cd5  lea     rax, [rbp+40h+pdwType]
0x180025cd9  mov     [rsp+140h+pvData], rdi; pvData
0x180025cde  mov     r14d, 4
0x180025ce4  mov     [rsp+140h+phkResult], rax; pdwType
0x180025ce9  mov     r9d, 0FFFFh; dwFlags
0x180025cef  mov     [rbp+40h+arg_8], r14d
0x180025cf3  xor     edx, edx; lpSubKey
0x180025cf5  call    cs:__imp_RegGetValueW
0x180025cfc  nop     dword ptr [rax+rax+00h]
0x180025d01  mov     ebx, eax
0x180025d03  test    eax, eax
0x180025d05  jnz     short loc_180025CAD
0x180025d07  cmp     [rbp+40h+pdwType], r14d
0x180025d0b  jnz     loc_180026133
0x180025d11  lea     ebx, [rax+2]
0x180025d14  lea     ecx, [rax+70h]
0x180025d17  mov     [rdi+8], ebx
0x180025d1a  call    FileLogAllowEntry
0x180025d1f  test    al, al
0x180025d21  jz      short loc_180025D3D
0x180025d23  mov     r9d, [rdi+8]
0x180025d27  lea     rdx, aAllownonstanda; "AllowNonstandardModeCombinations"
0x180025d2e  mov     r8d, [rdi]
0x180025d31  lea     rcx, aReadconfigS0x0; "ReadConfig: '%s'=0x%08X (%d)\n"
0x180025d38  call    FileLogAdd
0x180025d3d  mov     rcx, [rbp+40h+hkey]; hkey
0x180025d41  lea     rax, [rbp+40h+arg_8]
0x180025d45  mov     [rsp+140h+pcbData], rax; pcbData
0x180025d4a  lea     rsi, [rdi+4]
0x180025d4e  lea     rax, [rbp+40h+pdwType]
0x180025d52  mov     [rsp+140h+pvData], rsi; pvData
0x180025d57  mov     r9d, 0FFFFh; dwFlags
0x180025d5d  mov     [rsp+140h+phkResult], rax; pdwType
0x180025d62  lea     r8, aEventlogflags; "EventLogFlags"
0x180025d69  mov     [rbp+40h+arg_8], r14d
0x180025d6d  xor     edx, edx; lpSubKey
0x180025d6f  call    cs:__imp_RegGetValueW
0x180025d76  nop     dword ptr [rax+rax+00h]
0x180025d7b  test    eax, eax
0x180025d7d  jz      short loc_180025D89
0x180025d7f  mov     [rsi], r15d
0x180025d82  mov     eax, 1
0x180025d87  jmp     short loc_180025D95
0x180025d89  cmp     [rbp+40h+pdwType], r14d
0x180025d8d  jnz     loc_180026133
0x180025d93  mov     eax, ebx
0x180025d95  mov     ecx, 70h ; 'p'
0x180025d9a  mov     [rdi+8], eax
0x180025d9d  call    FileLogAllowEntry
0x180025da2  test    al, al
0x180025da4  jz      short loc_180025DC0
0x180025da6  mov     r9d, [rdi+0Ch]
0x180025daa  lea     rdx, aEventlogflags; "EventLogFlags"
0x180025db1  mov     r8d, [rsi]
0x180025db4  lea     rcx, aReadconfigS0x0; "ReadConfig: '%s'=0x%08X (%d)\n"
0x180025dbb  call    FileLogAdd
0x180025dc0  mov     rcx, [rbp+40h+hkey]; hkey
0x180025dc4  lea     rax, [rbp+40h+arg_8]
0x180025dc8  mov     [rsp+140h+pcbData], rax; pcbData
0x180025dcd  lea     rsi, [rdi+40h]
0x180025dd1  lea     rax, [rbp+40h+pdwType]
0x180025dd5  mov     [rsp+140h+pvData], rsi; pvData
0x180025dda  mov     r9d, 0FFFFh; dwFlags
0x180025de0  mov     [rsp+140h+phkResult], rax; pdwType
0x180025de5  lea     r8, aUnsecuretimesy; "UnsecureTimeSyncRequestsLogThrottlePeri"...
0x180025dec  mov     [rbp+40h+arg_8], r14d
0x180025df0  xor     edx, edx; lpSubKey
0x180025df2  call    cs:__imp_RegGetValueW
0x180025df9  nop     dword ptr [rax+rax+00h]
0x180025dfe  test    eax, eax
0x180025e00  jz      short loc_180025E0F
0x180025e02  mov     dword ptr [rsi], 5265C00h
0x180025e08  mov     ebx, 1
0x180025e0d  jmp     short loc_180025E19
0x180025e0f  cmp     [rbp+40h+pdwType], r14d
0x180025e13  jnz     loc_180026133
0x180025e19  mov     [rdi+44h], ebx
0x180025e1c  mov     ebx, 70h ; 'p'
0x180025e21  mov     ecx, ebx
0x180025e23  call    FileLogAllowEntry
0x180025e28  test    al, al
0x180025e2a  jz      short loc_180025E45
0x180025e2c  mov     r9d, [rsi]
0x180025e2f  lea     rdx, aUnsecuretimesy; "UnsecureTimeSyncRequestsLogThrottlePeri"...
0x180025e36  mov     r8d, r9d
0x180025e39  lea     rcx, aReadconfigS0x0; "ReadConfig: '%s'=0x%08X (%d)\n"
0x180025e40  call    FileLogAdd
0x180025e45  lea     rax, [rsp+140h+hKey]
0x180025e4a  mov     r9d, 20019h; samDesired
0x180025e50  xor     r8d, r8d; ulOptions
0x180025e53  mov     [rsp+140h+phkResult], rax; phkResult
0x180025e58  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\W32Time"...
0x180025e5f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025e66  call    cs:__imp_RegOpenKeyExW
0x180025e6d  nop     dword ptr [rax+rax+00h]
0x180025e72  test    eax, eax
0x180025e74  jz      short loc_180025E94
0x180025e76  mov     ecx, ebx
0x180025e78  call    FileLogAllowEntry
0x180025e7d  test    al, al
0x180025e7f  jz      short loc_180025E94
0x180025e81  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\W32Time"...
0x180025e88  lea     rcx, aReadconfigFail; "ReadConfig: failed to open '%s' key, tr"...
0x180025e8f  call    FileLogAdd
0x180025e94  mov     rdx, [rsp+140h+hKey]; HKEY
0x180025e99  lea     rax, [rbp+40h+arg_8]
0x180025e9d  mov     rcx, [rbp+40h+hkey]; hkey
0x180025ea1  lea     rbx, [rdi+3Ch]
0x180025ea5  mov     [rsp+140h+var_108], rbx; __int64
0x180025eaa  lea     rsi, [rdi+38h]
0x180025eae  mov     [rsp+140h+pcbData], rax; __int64
0x180025eb3  lea     r8, aRequiresecuret; "RequireSecureTimeSyncRequests"
0x180025eba  lea     rax, [rbp+40h+pdwType]
0x180025ebe  mov     [rsp+140h+pvData], rsi; PVOID
0x180025ec3  mov     [rsp+140h+phkResult], rax; LPDWORD
0x180025ec8  mov     [rbp+40h+arg_8], r14d
0x180025ecc  call    MyRegQueryPolicyValueEx
0x180025ed1  test    eax, eax
0x180025ed3  jns     short loc_180025EE0
0x180025ed5  mov     [rsi], r15d
0x180025ed8  mov     dword ptr [rbx], 1
0x180025ede  jmp     short loc_180025EEA
0x180025ee0  cmp     [rbp+40h+pdwType], r14d
0x180025ee4  jnz     loc_180026133
0x180025eea  mov     ecx, 70h ; 'p'
0x180025eef  call    FileLogAllowEntry
0x180025ef4  test    al, al
0x180025ef6  jz      short loc_180025F11
0x180025ef8  mov     r9d, [rbx]
0x180025efb  lea     rdx, aRequiresecuret; "RequireSecureTimeSyncRequests"
0x180025f02  mov     r8d, [rsi]
0x180025f05  lea     rcx, aReadconfigS0x0; "ReadConfig: '%s'=0x%08X (%d)\n"
0x180025f0c  call    FileLogAdd
0x180025f11  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180025f18  cmp     [rax+1FCh], r15b
0x180025f1f  jz      loc_18002614C
0x180025f25  lea     rax, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\W32Time"...
0x180025f2c  mov     byte ptr [rbp+40h+var_C0], r15b
0x180025f30  mov     [rsp+140h+lpSubKey], rax
0x180025f35  mov     esi, r15d
0x180025f38  lea     rax, [rsp+140h+var_F8]
0x180025f3d  mov     byte ptr [rbp+40h+var_A8], r15b
0x180025f41  mov     [rsp+140h+var_C8], rax
0x180025f46  lea     rax, aSoftwarePolici; "Software\\Policies\\Microsoft\\W32Time"...
0x180025f4d  mov     [rbp+40h+var_B8], rax
0x180025f51  lea     rax, [rsp+140h+var_E8]
0x180025f56  mov     [rbp+40h+var_B0], rax
0x180025f5a  lea     rax, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\W3"...
0x180025f61  mov     [rbp+40h+var_A0], rax
0x180025f65  lea     rax, [rsp+140h+var_F0]
0x180025f6a  mov     [rbp+40h+var_98], rax
0x180025f6e  lea     rax, aSystemCurrentc_7; "System\\CurrentControlSet\\Services\\W3"...
0x180025f75  mov     [rbp+40h+var_88], rax
0x180025f79  lea     rax, [rsp+140h+var_E0]
0x180025f7e  mov     [rbp+40h+var_80], rax
0x180025f82  mov     byte ptr [rbp+40h+var_90], 1
0x180025f86  mov     byte ptr [rbp+40h+var_78], 1
0x180025f8a  cmp     esi, r14d
0x180025f8d  jnb     short loc_180025FE6
0x180025f8f  mov     eax, esi
0x180025f91  mov     r9d, 20019h; samDesired
0x180025f97  xor     r8d, r8d; ulOptions
0x180025f9a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025fa1  lea     r14, [rax+rax*2]
0x180025fa5  mov     rax, [rsp+r14*8+140h+var_C8]
0x180025faa  mov     rdx, [rsp+r14*8+140h+lpSubKey]; lpSubKey
0x180025faf  mov     [rsp+140h+phkResult], rax; phkResult
0x180025fb4  call    cs:__imp_RegOpenKeyExW
0x180025fbb  nop     dword ptr [rax+rax+00h]
0x180025fc0  mov     ebx, eax
0x180025fc2  test    eax, eax
0x180025fc4  jz      short loc_180025FDC
0x180025fc6  jle     short loc_180025FD1
0x180025fc8  movzx   ebx, ax
0x180025fcb  or      ebx, 80070000h
0x180025fd1  cmp     byte ptr [rbp+r14*8+40h+var_C0], r15b
0x180025fd6  jnz     loc_180026138
0x180025fdc  inc     esi
0x180025fde  mov     r14d, 4
0x180025fe4  jmp     short loc_180025F8A
0x180025fe6  lea     rax, aChainentrytime; "ChainEntryTimeout"
0x180025fed  mov     dword ptr [rbp+40h+var_B8], r14d
0x180025ff1  mov     [rsp+140h+lpSubKey], rax
0x180025ff6  mov     ebx, r15d
0x180025ff9  lea     rax, [rdi+10h]
0x180025ffd  mov     dword ptr [rbp+40h+var_98], 80h
0x180026004  mov     [rsp+140h+var_C8], rax
0x180026009  lea     rax, [rdi+14h]
0x18002600d  mov     [rbp+40h+var_C0], rax
0x180026011  lea     rax, aChainmaxentrie; "ChainMaxEntries"
0x180026018  mov     [rbp+40h+var_B0], rax
0x18002601c  lea     rax, [rdi+18h]
0x180026020  mov     [rbp+40h+var_A8], rax
0x180026024  lea     rax, [rdi+1Ch]
0x180026028  mov     [rbp+40h+var_A0], rax
0x18002602c  lea     rax, aChainmaxhosten; "ChainMaxHostEntries"
0x180026033  mov     [rbp+40h+var_90], rax
0x180026037  lea     rax, [rdi+20h]
0x18002603b  mov     [rbp+40h+var_88], rax
0x18002603f  lea     rax, [rdi+24h]
0x180026043  mov     [rbp+40h+var_80], rax
0x180026047  lea     rax, aChaindisable; "ChainDisable"
0x18002604e  mov     [rbp+40h+var_70], rax
0x180026052  lea     rax, [rdi+28h]
0x180026056  mov     [rbp+40h+var_68], rax
0x18002605a  lea     rax, [rdi+2Ch]
0x18002605e  mov     [rbp+40h+var_60], rax
0x180026062  lea     rax, aChainloggingra; "ChainLoggingRate"
0x180026069  mov     [rbp+40h+var_50], rax
0x18002606d  lea     rax, [rdi+30h]
0x180026071  mov     [rbp+40h+var_48], rax
0x180026075  lea     rax, [rdi+34h]
0x180026079  mov     [rbp+40h+var_40], rax
0x18002607d  mov     [rbp+40h+var_78], r14d
0x180026081  mov     [rbp+40h+var_58], r15d
0x180026085  mov     [rbp+40h+var_38], 1Eh
0x18002608c  cmp     ebx, 5
0x18002608f  jnb     loc_180026149
0x180026095  mov     rdx, [rsp+140h+var_F8]; HKEY
0x18002609a  lea     rax, [rbp+40h+arg_8]
0x18002609e  mov     rcx, [rsp+140h+var_F0]; hkey
0x1800260a3  mov     [rbp+40h+arg_8], r14d
0x1800260a7  mov     esi, ebx
0x1800260a9  shl     rsi, 5
0x1800260ad  mov     r15, [rbp+rsi+40h+var_C0]
0x1800260b2  mov     r14, [rsp+rsi+140h+var_C8]
0x1800260b7  mov     r8, [rsp+rsi+140h+lpSubKey]; lpValue
0x1800260bc  mov     [rsp+140h+var_108], r15; __int64
0x1800260c1  mov     [rsp+140h+pcbData], rax; __int64
0x1800260c6  lea     rax, [rbp+40h+pdwType]
0x1800260ca  mov     [rsp+140h+pvData], r14; PVOID
0x1800260cf  mov     [rsp+140h+phkResult], rax; LPDWORD
0x1800260d4  call    MyRegQueryPolicyValueEx
0x1800260d9  test    eax, eax
0x1800260db  jz      short loc_1800260FB
0x1800260dd  mov     eax, dword ptr [rbp+rsi+40h+var_B8]
0x1800260e1  mov     ecx, 70h ; 'p'
0x1800260e6  mov     [r14], eax
0x1800260e9  call    FileLogAllowEntry
0x1800260ee  test    al, al
0x1800260f0  jz      short loc_180026126
0x1800260f2  lea     rcx, aReadconfigS0x0_2; "ReadConfig: '%s'=0x%08X (%d) [Using Def"...
0x1800260f9  jmp     short loc_180026116
0x1800260fb  cmp     [rbp+40h+pdwType], 4
0x1800260ff  jnz     short loc_180026133
0x180026101  mov     ecx, 70h ; 'p'
0x180026106  call    FileLogAllowEntry
0x18002610b  test    al, al
0x18002610d  jz      short loc_180026126
0x18002610f  lea     rcx, aReadconfigS0x0; "ReadConfig: '%s'=0x%08X (%d)\n"
0x180026116  mov     r9d, [r15]
0x180026119  mov     r8d, [r14]
0x18002611c  mov     rdx, [rsp+rsi+140h+lpSubKey]
  ... truncated ...
```
