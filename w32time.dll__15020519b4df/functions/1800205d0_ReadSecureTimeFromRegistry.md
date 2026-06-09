# ReadSecureTimeFromRegistry

- ea: `0x1800205d0`
- end: `0x180020cfe`
- name: `ReadSecureTimeFromRegistry`
- size: `1838`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x18001fcc0`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x1800205d0`
- `0x180020d04`
- `0x18003d270`
- `0x18003dd2c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180020620`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180020620`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002071e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002076c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002071e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002076c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020cb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020ccd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066962`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006697f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020cb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020ccd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066962`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006697f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800207bc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002081f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020889`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800208e7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020945`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800207bc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002081f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020889`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800208e7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020945`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180020734`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180020734`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800206e6`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800206e6`

## string_xrefs

- `0x1800206d8`: `System\CurrentControlSet\Services\W32Time\SecureTimeLimits`
- `0x180020b50`: `System\CurrentControlSet\Services\W32Time\SecureTimeLimits`
- `0x180020b96`: `Failed to open secure time regkey. Error: 0x%x\n`
- `0x180020bbc`: `Invalid value type for tick count. Expected:%d Read:%d \n`
- `0x180020ab7`: `Invalid value type for confidence. Expected:%d Read:%d \n`
- `0x180020be6`: `Failed to read secure time runtime data. Ignoring Error: 0x%x and using the secure time data to establish minimum time.\n`
- `0x180020c0f`: `Invalid Secure Time tick count read from the registry. Considering runtime data invalid. TickCount From Registry:%I64u	 Current TickCount:%I64u\n`
- `0x180020c43`: `Failed to read Secure Time Lower limit. RetVal: 0x%x Type:%d\n`
- `0x180020c6d`: `Failed to read Secure Time estimated value. RetVal: 0x%x Type:%d\n`
- `0x180020c97`: `Failed to read Secure Time Upper limit. RetVal: 0x%x Type:%d\n`
- `0x180020a83`: `No usable prior data stored in the registry. Using default values.\n`

## pseudocode

```c
__int64 __fastcall ReadSecureTimeFromRegistry(__int64 a1)
{
  ULONGLONG TickCount64; // rsi
  unsigned int v3; // r14d
  int PersistedRegistryLocationW; // edi
  LSTATUS v5; // edi
  char IsStateSeparationEnabled; // al
  const WCHAR *v7; // rdx
  unsigned int ValueW; // edi
  unsigned int v9; // edi
  unsigned int v10; // edi
  unsigned int v11; // edi
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // r8
  DWORD pdwType; // [rsp+40h] [rbp-2E8h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-2E4h] BYREF
  int v17; // [rsp+48h] [rbp-2E0h]
  int v18; // [rsp+4Ch] [rbp-2DCh] BYREF
  HKEY hKey; // [rsp+50h] [rbp-2D8h] BYREF
  ULONGLONG pvData; // [rsp+58h] [rbp-2D0h] BYREF
  HKEY hkey; // [rsp+60h] [rbp-2C8h] BYREF
  unsigned __int64 v22; // [rsp+68h] [rbp-2C0h]
  __int64 v23; // [rsp+70h] [rbp-2B8h]
  __int64 v24; // [rsp+78h] [rbp-2B0h]
  __int64 v25; // [rsp+80h] [rbp-2A8h]
  unsigned __int64 v26; // [rsp+88h] [rbp-2A0h] BYREF
  unsigned __int64 v27; // [rsp+90h] [rbp-298h] BYREF
  _QWORD v28[7]; // [rsp+98h] [rbp-290h] BYREF
  WCHAR SubKey[264]; // [rsp+D0h] [rbp-258h] BYREF

  pcbData = 0;
  pdwType = 0;
  v26 = 0;
  v27 = 0;
  v28[0] = 0;
  pvData = 0;
  TickCount64 = GetTickCount64();
  v18 = 0;
  hKey = 0;
  hkey = 0;
  v3 = 0;
  memset_0(SubKey, 0, 0x208u);
  *(_OWORD *)a1 = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  v23 = 130828608000000000LL;
  *(_QWORD *)(a1 + 8) = 130828608000000000LL;
  v24 = 130828608000000000LL;
  *(_QWORD *)(a1 + 24) = 130828608000000000LL;
  v25 = 130828608000000000LL;
  *(_QWORD *)(a1 + 16) = 130828608000000000LL;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"W32TimeSecureTimeLimits",
                                 L"System\\CurrentControlSet\\Services\\W32Time\\SecureTimeLimits",
                                 SubKey,
                                 520,
                                 0);
  if ( PersistedRegistryLocationW )
  {
    if ( PersistedRegistryLocationW <= 0 )
      v3 = PersistedRegistryLocationW;
    else
      v3 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(
        L"Failed to get time regkey %s. Error: 0x%x\n",
        L"System\\CurrentControlSet\\Services\\W32Time\\SecureTimeLimits",
        (unsigned int)PersistedRegistryLocationW);
  }
  else
  {
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
    if ( !v5 )
    {
      IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
      v7 = L"RT";
      if ( !IsStateSeparationEnabled )
        v7 = L"RunTime";
      ValueW = RegOpenKeyExW(hKey, v7, 0, 1u, &hkey);
      v17 = ValueW;
      if ( !ValueW )
      {
        pcbData = 8;
        ValueW = RegGetValueW(hkey, 0, L"SecureTimeTickCount", 0xFFFFu, &pdwType, &pvData, &pcbData);
        v17 = ValueW;
        if ( !ValueW && pdwType != 11 )
        {
          if ( (unsigned __int8)FileLogAllowEntry(1001) )
            FileLogAdd(L"Invalid value type for tick count. Expected:%d Read:%d \n", 11, pdwType);
          ValueW = -1;
          v17 = -1;
        }
      }
      if ( ValueW )
        goto LABEL_71;
      pcbData = 4;
      ValueW = RegGetValueW(hkey, 0, L"SecureTimeConfidence", 0xFFFFu, &pdwType, &v18, &pcbData);
      v17 = ValueW;
      if ( !ValueW && pdwType != 4 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(1001) )
          FileLogAdd(L"Invalid value type for confidence. Expected:%d Read:%d \n", 4, pdwType);
        ValueW = -1;
        v17 = -1;
      }
      if ( ValueW )
      {
LABEL_71:
        if ( (unsigned __int8)FileLogAllowEntry(1001) )
          FileLogAdd(
            L"Failed to read secure time runtime data. Ignoring Error: 0x%x and using the secure time data to establish minimum time.\n",
            ValueW);
        v17 = 0;
      }
      else
      {
        if ( pvData <= TickCount64 )
        {
LABEL_12:
          pcbData = 8;
          v9 = RegGetValueW(hKey, 0, L"SecureTimeLow", 0xFFFFu, &pdwType, &v26, &pcbData);
          if ( (v9 || pdwType != 11) && (unsigned __int8)FileLogAllowEntry(1001) )
            FileLogAdd(L"Failed to read Secure Time Lower limit. RetVal: 0x%x Type:%d\n", v9, pdwType);
          pcbData = 8;
          v10 = RegGetValueW(hKey, 0, L"SecureTimeEstimated", 0xFFFFu, &pdwType, &v27, &pcbData);
          if ( (v10 || pdwType != 11) && (unsigned __int8)FileLogAllowEntry(1001) )
            FileLogAdd(L"Failed to read Secure Time estimated value. RetVal: 0x%x Type:%d\n", v10, pdwType);
          pcbData = 8;
          v11 = RegGetValueW(hKey, 0, L"SecureTimeHigh", 0xFFFFu, &pdwType, v28, &pcbData);
          if ( (v11 || pdwType != 11) && (unsigned __int8)FileLogAllowEntry(1001) )
            FileLogAdd(L"Failed to read Secure Time Upper limit. RetVal: 0x%x Type:%d\n", v11, pdwType);
          v12 = v27;
          if ( v26 > v27 || (v13 = v28[0], v27 > v28[0]) )
          {
            if ( (unsigned __int8)FileLogAllowEntry(0) )
              FileLogAdd(L"No usable prior data stored in the registry. Using default values.\n");
          }
          else
          {
            v22 = v26;
            v28[1] = 130828608000000000LL;
            v28[4] = 130828608000000000LL;
            if ( v26 > 0x1D0CBED024C8000LL )
              *(_QWORD *)(a1 + 8) = v26;
            v22 = v12;
            v28[2] = 130828608000000000LL;
            v28[5] = 130828608000000000LL;
            if ( v12 > 0x1D0CBED024C8000LL )
              *(_QWORD *)(a1 + 24) = v12;
            v22 = v13;
            v28[3] = 130828608000000000LL;
            v28[6] = 130828608000000000LL;
            if ( v13 > 0x1D0CBED024C8000LL )
              *(_QWORD *)(a1 + 16) = v13;
            *(_QWORD *)a1 = pvData;
            *(_DWORD *)(a1 + 32) = v18;
            LogSecureTime(a1);
          }
          goto LABEL_64;
        }
        if ( (unsigned __int8)FileLogAllowEntry(1001) )
          FileLogAdd(
            L"Invalid Secure Time tick count read from the registry. Considering runtime data invalid. TickCount From Regi"
             "stry:%I64u\t Current TickCount:%I64u\n",
            pvData,
            TickCount64);
      }
      pvData = 0;
      v18 = 0;
      goto LABEL_12;
    }
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"Failed to open secure time regkey. Error: 0x%x\n", (unsigned int)v5);
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    else
      v3 = v5;
  }
LABEL_64:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( hkey )
    RegCloseKey(hkey);
  return v3;
}

```

## disassembly

```asm
0x1800205d0  push    rbx
0x1800205d2  push    rsi
0x1800205d3  push    rdi
0x1800205d4  push    r12
0x1800205d6  push    r14
0x1800205d8  push    r15
0x1800205da  sub     rsp, 2F8h
0x1800205e1  mov     rax, cs:__security_cookie
0x1800205e8  xor     rax, rsp
0x1800205eb  mov     [rsp+328h+var_48], rax
0x1800205f3  mov     rbx, rcx
0x1800205f6  xor     r15d, r15d
0x1800205f9  mov     [rsp+328h+var_2E4], r15d
0x1800205fe  mov     [rsp+328h+pdwType], r15d
0x180020603  mov     [rsp+328h+var_2A0], r15
0x18002060b  mov     [rsp+328h+var_298], r15
0x180020613  mov     [rsp+328h+var_290], r15
0x18002061b  mov     [rsp+328h+var_2D0], r15
0x180020620  call    cs:__imp_GetTickCount64
0x180020627  nop     dword ptr [rax+rax+00h]
0x18002062c  mov     rsi, rax
0x18002062f  mov     [rsp+328h+var_2DC], r15d
0x180020634  mov     [rsp+328h+hKey], r15
0x180020639  mov     [rsp+328h+hkey], r15
0x18002063e  mov     r14d, r15d
0x180020641  xor     edx, edx; Val
0x180020643  mov     r8d, 208h; Size
0x180020649  lea     rcx, [rsp+328h+SubKey]; void *
0x180020651  call    memset_0
0x180020656  nop
0x180020657  xorps   xmm0, xmm0
0x18002065a  xor     eax, eax
0x18002065c  movups  xmmword ptr [rbx], xmm0
0x18002065f  movups  xmmword ptr [rbx+10h], xmm0
0x180020663  mov     [rbx+20h], rax
0x180020667  mov     [rsp+328h+var_2B8], r15
0x18002066c  mov     dword ptr [rsp+328h+var_2B8+4], 1D0CBEDh
0x180020674  mov     dword ptr [rsp+328h+var_2B8], 24C8000h
0x18002067c  mov     r12, 1D0CBED024C8000h
0x180020686  mov     [rbx+8], r12
0x18002068a  mov     [rsp+328h+var_2B0], r15
0x18002068f  mov     dword ptr [rsp+328h+var_2B0+4], 1D0CBEDh
0x180020697  mov     dword ptr [rsp+328h+var_2B0], 24C8000h
0x18002069f  mov     [rbx+18h], r12
0x1800206a3  mov     [rsp+328h+var_2A8], r15
0x1800206ab  mov     dword ptr [rsp+328h+var_2A8+4], 1D0CBEDh
0x1800206b6  mov     dword ptr [rsp+328h+var_2A8], 24C8000h
0x1800206c1  mov     [rbx+10h], r12
0x1800206c5  mov     [rsp+328h+phkResult], r15
0x1800206ca  mov     r9d, 208h
0x1800206d0  lea     r8, [rsp+328h+SubKey]
0x1800206d8  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\W3"...
0x1800206df  lea     rcx, aW32timesecuret; "W32TimeSecureTimeLimits"
0x1800206e6  call    cs:__imp_GetPersistedRegistryLocationW
0x1800206ed  nop     dword ptr [rax+rax+00h]
0x1800206f2  mov     edi, eax
0x1800206f4  test    eax, eax
0x1800206f6  jnz     loc_180020B2F
0x1800206fc  lea     rax, [rsp+328h+hKey]
0x180020701  mov     [rsp+328h+phkResult], rax; phkResult
0x180020706  mov     r9d, 1; samDesired
0x18002070c  xor     r8d, r8d; ulOptions
0x18002070f  lea     rdx, [rsp+328h+SubKey]; lpSubKey
0x180020717  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002071e  call    cs:__imp_RegOpenKeyExW
0x180020725  nop     dword ptr [rax+rax+00h]
0x18002072a  mov     edi, eax
0x18002072c  test    eax, eax
0x18002072e  jnz     loc_180020B89
0x180020734  call    cs:__imp_RtlIsStateSeparationEnabled
0x18002073b  nop     dword ptr [rax+rax+00h]
0x180020740  lea     rcx, aRuntime; "RunTime"
0x180020747  lea     rdx, aRt; "RT"
0x18002074e  test    al, al
0x180020750  cmovz   rdx, rcx; lpSubKey
0x180020754  lea     rax, [rsp+328h+hkey]
0x180020759  mov     [rsp+328h+phkResult], rax; phkResult
0x18002075e  mov     r9d, 1; samDesired
0x180020764  xor     r8d, r8d; ulOptions
0x180020767  mov     rcx, [rsp+328h+hKey]; hKey
0x18002076c  call    cs:__imp_RegOpenKeyExW
0x180020773  nop     dword ptr [rax+rax+00h]
0x180020778  mov     edi, eax
0x18002077a  mov     [rsp+328h+var_2E0], eax
0x18002077e  test    eax, eax
0x180020780  jnz     short loc_1800207DD
0x180020782  mov     [rsp+328h+var_2E4], 8
0x18002078a  lea     rax, [rsp+328h+var_2E4]
0x18002078f  mov     [rsp+328h+pcbData], rax; pcbData
0x180020794  lea     rax, [rsp+328h+var_2D0]
0x180020799  mov     [rsp+328h+pvData], rax; pvData
0x18002079e  lea     rax, [rsp+328h+pdwType]
0x1800207a3  mov     [rsp+328h+phkResult], rax; pdwType
0x1800207a8  mov     r9d, 0FFFFh; dwFlags
0x1800207ae  lea     r8, aSecuretimetick; "SecureTimeTickCount"
0x1800207b5  xor     edx, edx; lpSubKey
0x1800207b7  mov     rcx, [rsp+328h+hkey]; hkey
0x1800207bc  call    cs:__imp_RegGetValueW
0x1800207c3  nop     dword ptr [rax+rax+00h]
0x1800207c8  mov     edi, eax
0x1800207ca  mov     [rsp+328h+var_2E0], eax
0x1800207ce  test    eax, eax
0x1800207d0  jnz     short loc_1800207DD
0x1800207d2  cmp     [rsp+328h+pdwType], 0Bh
0x1800207d7  jnz     loc_180020BA4
0x1800207dd  test    edi, edi
0x1800207df  jnz     loc_180020BD6
0x1800207e5  mov     [rsp+328h+var_2E4], 4
0x1800207ed  lea     rax, [rsp+328h+var_2E4]
0x1800207f2  mov     [rsp+328h+pcbData], rax; pcbData
0x1800207f7  lea     rax, [rsp+328h+var_2DC]
0x1800207fc  mov     [rsp+328h+pvData], rax; pvData
0x180020801  lea     rax, [rsp+328h+pdwType]
0x180020806  mov     [rsp+328h+phkResult], rax; pdwType
0x18002080b  mov     r9d, 0FFFFh; dwFlags
0x180020811  lea     r8, aSecuretimeconf; "SecureTimeConfidence"
0x180020818  xor     edx, edx; lpSubKey
0x18002081a  mov     rcx, [rsp+328h+hkey]; hkey
0x18002081f  call    cs:__imp_RegGetValueW
0x180020826  nop     dword ptr [rax+rax+00h]
0x18002082b  mov     edi, eax
0x18002082d  mov     [rsp+328h+var_2E0], eax
0x180020831  test    eax, eax
0x180020833  jz      loc_180020A94
0x180020839  test    edi, edi
0x18002083b  jnz     loc_180020BD6
0x180020841  cmp     [rsp+328h+var_2D0], rsi
0x180020846  ja      loc_180020BF9
0x18002084c  mov     [rsp+328h+var_2E4], 8
0x180020854  lea     rax, [rsp+328h+var_2E4]
0x180020859  mov     [rsp+328h+pcbData], rax; pcbData
0x18002085e  lea     rax, [rsp+328h+var_2A0]
0x180020866  mov     [rsp+328h+pvData], rax; pvData
0x18002086b  lea     rax, [rsp+328h+pdwType]
0x180020870  mov     [rsp+328h+phkResult], rax; pdwType
0x180020875  mov     r9d, 0FFFFh; dwFlags
0x18002087b  lea     r8, aSecuretimelow; "SecureTimeLow"
0x180020882  xor     edx, edx; lpSubKey
0x180020884  mov     rcx, [rsp+328h+hKey]; hkey
0x180020889  call    cs:__imp_RegGetValueW
0x180020890  nop     dword ptr [rax+rax+00h]
0x180020895  mov     edi, eax
0x180020897  test    eax, eax
0x180020899  jnz     loc_180020C2A
0x18002089f  cmp     [rsp+328h+pdwType], 0Bh
0x1800208a4  jnz     loc_180020C2A
0x1800208aa  mov     [rsp+328h+var_2E4], 8
0x1800208b2  lea     rax, [rsp+328h+var_2E4]
0x1800208b7  mov     [rsp+328h+pcbData], rax; pcbData
0x1800208bc  lea     rax, [rsp+328h+var_298]
0x1800208c4  mov     [rsp+328h+pvData], rax; pvData
0x1800208c9  lea     rax, [rsp+328h+pdwType]
0x1800208ce  mov     [rsp+328h+phkResult], rax; pdwType
0x1800208d3  mov     r9d, 0FFFFh; dwFlags
0x1800208d9  lea     r8, aSecuretimeesti; "SecureTimeEstimated"
0x1800208e0  xor     edx, edx; lpSubKey
0x1800208e2  mov     rcx, [rsp+328h+hKey]; hkey
0x1800208e7  call    cs:__imp_RegGetValueW
0x1800208ee  nop     dword ptr [rax+rax+00h]
0x1800208f3  mov     edi, eax
0x1800208f5  test    eax, eax
0x1800208f7  jnz     loc_180020C54
0x1800208fd  cmp     [rsp+328h+pdwType], 0Bh
0x180020902  jnz     loc_180020C54
0x180020908  mov     [rsp+328h+var_2E4], 8
0x180020910  lea     rax, [rsp+328h+var_2E4]
0x180020915  mov     [rsp+328h+pcbData], rax; pcbData
0x18002091a  lea     rax, [rsp+328h+var_290]
0x180020922  mov     [rsp+328h+pvData], rax; pvData
0x180020927  lea     rax, [rsp+328h+pdwType]
0x18002092c  mov     [rsp+328h+phkResult], rax; pdwType
0x180020931  mov     r9d, 0FFFFh; dwFlags
0x180020937  lea     r8, aSecuretimehigh; "SecureTimeHigh"
0x18002093e  xor     edx, edx; lpSubKey
0x180020940  mov     rcx, [rsp+328h+hKey]; hkey
0x180020945  call    cs:__imp_RegGetValueW
0x18002094c  nop     dword ptr [rax+rax+00h]
0x180020951  mov     edi, eax
0x180020953  test    eax, eax
0x180020955  jnz     loc_180020C7E
0x18002095b  cmp     [rsp+328h+pdwType], 0Bh
0x180020960  jnz     loc_180020C7E
0x180020966  mov     rdx, [rsp+328h+var_2A0]
0x18002096e  mov     rcx, [rsp+328h+var_298]
0x180020976  cmp     rdx, rcx
0x180020979  ja      loc_180020A74
0x18002097f  mov     r8, [rsp+328h+var_290]
0x180020987  cmp     rcx, r8
0x18002098a  ja      loc_180020A74
0x180020990  mov     [rsp+328h+var_2C0], r15
0x180020995  mov     [rsp+328h+var_2C0], rdx
0x18002099a  mov     rax, rdx
0x18002099d  shr     rax, 20h
0x1800209a1  mov     [rsp+328h+var_288], r15
0x1800209a9  mov     dword ptr [rsp+328h+var_288+4], 1D0CBEDh
0x1800209b4  mov     dword ptr [rsp+328h+var_288], 24C8000h
0x1800209bf  mov     [rsp+328h+var_270], r12
0x1800209c7  cmp     eax, 1D0CBEDh
0x1800209cc  jbe     loc_180020AD1
0x1800209d2  mov     [rbx+8], rdx
0x1800209d6  mov     [rsp+328h+var_2C0], rcx
0x1800209db  mov     rax, rcx
0x1800209de  shr     rax, 20h
0x1800209e2  mov     [rsp+328h+var_280], r15
0x1800209ea  mov     dword ptr [rsp+328h+var_280+4], 1D0CBEDh
0x1800209f5  mov     dword ptr [rsp+328h+var_280], 24C8000h
0x180020a00  mov     [rsp+328h+var_268], r12
0x180020a08  cmp     eax, 1D0CBEDh
0x180020a0d  jbe     loc_180020AF0
0x180020a13  mov     [rbx+18h], rcx
0x180020a17  mov     [rsp+328h+var_2C0], r8
0x180020a1c  mov     rax, r8
0x180020a1f  shr     rax, 20h
0x180020a23  mov     [rsp+328h+var_278], r15
0x180020a2b  mov     dword ptr [rsp+328h+var_278+4], 1D0CBEDh
0x180020a36  mov     dword ptr [rsp+328h+var_278], 24C8000h
0x180020a41  mov     [rsp+328h+var_260], r12
0x180020a49  cmp     eax, 1D0CBEDh
0x180020a4e  jbe     loc_180020B0F
0x180020a54  mov     [rbx+10h], r8
0x180020a58  mov     rax, [rsp+328h+var_2D0]
0x180020a5d  mov     [rbx], rax
0x180020a60  mov     eax, [rsp+328h+var_2DC]
0x180020a64  mov     [rbx+20h], eax
0x180020a67  mov     rcx, rbx
0x180020a6a  call    LogSecureTime
0x180020a6f  jmp     loc_180020CA8
0x180020a74  xor     ecx, ecx
0x180020a76  call    FileLogAllowEntry
0x180020a7b  test    al, al
0x180020a7d  jz      loc_180020CA8
0x180020a83  lea     rcx, aNoUsablePriorD; "No usable prior data stored in the regi"...
0x180020a8a  call    FileLogAdd
0x180020a8f  jmp     loc_180020CA8
0x180020a94  cmp     [rsp+328h+pdwType], 4
0x180020a99  jz      loc_180020839
0x180020a9f  mov     ecx, 3E9h
0x180020aa4  call    FileLogAllowEntry
0x180020aa9  test    al, al
0x180020aab  jz      short loc_180020AC3
0x180020aad  mov     r8d, [rsp+328h+pdwType]
0x180020ab2  mov     edx, 4
0x180020ab7  lea     rcx, aInvalidValueTy; "Invalid value type for confidence. Expe"...
0x180020abe  call    FileLogAdd
0x180020ac3  mov     edi, 0FFFFFFFFh
0x180020ac8  mov     [rsp+328h+var_2E0], edi
0x180020acc  jmp     loc_180020839
0x180020ad1  jnz     loc_1800209D6
0x180020ad7  mov     eax, r15d
0x180020ada  cmp     edx, 24C8000h
0x180020ae0  setnbe  al
0x180020ae3  test    eax, eax
0x180020ae5  jnz     loc_1800209D2
0x180020aeb  jmp     loc_1800209D6
0x180020af0  jnz     loc_180020A17
0x180020af6  mov     eax, r15d
0x180020af9  cmp     ecx, 24C8000h
0x180020aff  setnbe  al
0x180020b02  test    eax, eax
0x180020b04  jnz     loc_180020A13
0x180020b0a  jmp     loc_180020A17
0x180020b0f  jnz     loc_180020A58
0x180020b15  mov     eax, r15d
0x180020b18  cmp     r8d, 24C8000h
0x180020b1f  setnbe  al
0x180020b22  test    eax, eax
0x180020b24  jnz     loc_180020A54
0x180020b2a  jmp     loc_180020A58
0x180020b2f  test    edi, edi
0x180020b31  jle     short loc_180020B68
0x180020b33  movzx   r14d, di
0x180020b37  or      r14d, 80070000h
0x180020b3e  xor     ecx, ecx
0x180020b40  call    FileLogAllowEntry
0x180020b45  test    al, al
0x180020b47  jz      loc_180020CA8
0x180020b4d  mov     r8d, edi
0x180020b50  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\W3"...
0x180020b57  lea     rcx, aFailedToGetTim; "Failed to get time regkey %s. Error: 0x"...
0x180020b5e  call    FileLogAdd
0x180020b63  jmp     loc_180020CA8
0x180020b68  mov     r14d, edi
0x180020b6b  jmp     short loc_180020B3E
0x180020b6d  test    edi, edi
0x180020b6f  jg      short loc_180020B79
0x180020b71  mov     r14d, edi
0x180020b74  jmp     loc_180020CA8
0x180020b79  movzx   r14d, di
0x180020b7d  or      r14d, 80070000h
0x180020b84  jmp     loc_180020CA8
0x180020b89  xor     ecx, ecx
0x180020b8b  call    FileLogAllowEntry
0x180020b90  test    al, al
0x180020b92  jz      short loc_180020B6D
0x180020b94  mov     edx, edi
0x180020b96  lea     rcx, aFailedToOpenSe; "Failed to open secure time regkey. Erro"...
0x180020b9d  call    FileLogAdd
0x180020ba2  jmp     short loc_180020B6D
0x180020ba4  mov     ecx, 3E9h
0x180020ba9  call    FileLogAllowEntry
  ... truncated ...
```
