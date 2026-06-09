# ServerInit

- ea: `0x18002c8fc`
- end: `0x18002d275`
- name: `ServerInit`
- size: `2425`
- prototype: `__int64 __fastcall(int)`
- caller_count: `4`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010750`
- `0x180023060`
- `0x180028b00`
- `0x18002d6d0`

## callees

- `0x180001600`
- `0x180001640`
- `0x18001b1dc`
- `0x18001b4c4`
- `0x18001c854`
- `0x18001c8a4`
- `0x18002617c`
- `0x1800263e4`
- `0x180026600`
- `0x18002a420`
- `0x18002a440`
- `0x18002ba10`
- `0x18002c8d4`
- `0x18002c8fc`
- `0x18002ff78`
- `0x18003d1ac`
- `0x18003dc84`
- `0x180040010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ca5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d10a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d115`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ca5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d10a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d115`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ca1d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ca48`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ca1d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ca48`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ca99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002cb28`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002cb84`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ca99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002cb28`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002cb84`
- `KERNEL32!lstrcmpiW` at `0x18002cbf5`
- `KERNEL32!lstrcmpiW` at `0x18002cbf5`
- `KERNEL32!GetProcessHeap` at `0x18002c944`
- `KERNEL32!GetProcessHeap` at `0x18002c944`
- `KERNEL32!DeleteCriticalSection` at `0x18002d00d`
- `KERNEL32!DeleteCriticalSection` at `0x18002d00d`
- `KERNEL32!HeapCompact` at `0x18002c958`
- `KERNEL32!HeapCompact` at `0x18002c958`
- `KERNEL32!HeapAlloc` at `0x18002c97e`
- `KERNEL32!HeapAlloc` at `0x18002c9af`
- `KERNEL32!HeapAlloc` at `0x18002cc46`
- `KERNEL32!HeapAlloc` at `0x18002cf87`
- `KERNEL32!HeapAlloc` at `0x18002c97e`
- `KERNEL32!HeapAlloc` at `0x18002c9af`
- `KERNEL32!HeapAlloc` at `0x18002cc46`
- `KERNEL32!HeapAlloc` at `0x18002cf87`
- `KERNEL32!CreateEventW` at `0x18002cf64`
- `KERNEL32!CreateEventW` at `0x18002cf64`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18002cf54`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18002cf54`
- `KERNEL32!CompareStringW` at `0x18002cdd7`
- `KERNEL32!CompareStringW` at `0x18002ce10`
- `KERNEL32!CompareStringW` at `0x18002cdd7`
- `KERNEL32!CompareStringW` at `0x18002ce10`
- `KERNEL32!FreeLibrary` at `0x18002cf1d`
- `KERNEL32!FreeLibrary` at `0x18002cf1d`
- `KERNEL32!GetProcAddress` at `0x18002ccd2`
- `KERNEL32!GetProcAddress` at `0x18002ccd2`
- `KERNEL32!LoadLibraryW` at `0x18002cc5c`
- `KERNEL32!LoadLibraryW` at `0x18002cc5c`
- `KERNEL32!CloseHandle` at `0x18002d041`
- `KERNEL32!CloseHandle` at `0x18002d041`
- `KERNEL32!GetLastError` at `0x18002cc6b`
- `KERNEL32!GetLastError` at `0x18002cc6b`
- `KERNEL32!ReleaseMutex` at `0x18002d122`
- `KERNEL32!ReleaseMutex` at `0x18002d122`
- `KERNEL32!WaitForSingleObject` at `0x18002c9f1`
- `KERNEL32!WaitForSingleObject` at `0x18002c9f1`
- `KERNEL32!CreateMutexW` at `0x18002cf3e`
- `KERNEL32!CreateMutexW` at `0x18002cf3e`
- `KERNEL32!lstrlenW` at `0x18002cc22`
- `KERNEL32!lstrlenW` at `0x18002cc22`

## string_xrefs

- `0x18002cc7d`: `ServerInit: LoadLibrary(%S) failed, err=x%x`

## pseudocode

```c
__int64 __fastcall ServerInit(int a1)
{
  int v1; // esi
  HANDLE ProcessHeap; // rax
  HANDLE v4; // rcx
  _DWORD *v5; // rax
  unsigned int v6; // r14d
  HANDLE v7; // rcx
  _DWORD *v8; // rax
  unsigned int i; // eax
  unsigned __int64 v10; // rcx
  int v11; // r15d
  unsigned __int16 v12; // ax
  BYTE *v13; // rcx
  LPVOID j; // rbx
  int v15; // eax
  size_t v16; // rbx
  _DWORD *v17; // rdi
  HMODULE LibraryW; // rax
  DWORD LastError; // eax
  __int64 k; // rsi
  unsigned int v21; // ecx
  unsigned int (__fastcall *v22)(__int64, __int64, __int64, _DWORD *); // rax
  unsigned int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // rcx
  unsigned int NumLineLookupEntries; // eax
  HKEY *v29; // r11
  unsigned int v30; // eax
  int v31; // eax
  __int64 v32; // rbx
  int v33; // edx
  __int64 v34; // r9
  HANDLE EventW; // rax
  HANDLE v36; // rcx
  _QWORD *v37; // rax
  __int64 v38; // rdx
  _QWORD *v39; // rcx
  int v40; // eax
  void *v41; // rcx
  void *v42; // rcx
  __int64 v43; // rcx
  unsigned int v44; // ebx
  __int64 v45; // r8
  __int64 v46; // rdx
  unsigned int v47; // esi
  unsigned int NumPhoneLookupEntries; // ebx
  unsigned int m; // esi
  unsigned int v50; // edi
  unsigned int v51; // ebx
  __int64 v52; // rdx
  __int64 v53; // rcx
  unsigned int v54; // r8d
  int v55; // r9d
  unsigned int v56; // edx
  unsigned int v57; // esi
  unsigned int v58; // esi
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int v62; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v63; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v65[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  BYTE Data[4]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v68; // [rsp+68h] [rbp-98h]
  HKEY v69; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  _DWORD v71[8]; // [rsp+80h] [rbp-80h]
  BYTE v72[2]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t pszDest[32]; // [rsp+1A0h] [rbp+A0h] BYREF

  v1 = 0;
  *(_DWORD *)Data = 0;
  hKey = 0;
  v69 = 0;
  cbData = 0;
  Type = 0;
  ProcessHeap = GetProcessHeap();
  v4 = ghTapisrvHeap;
  if ( ghTapisrvHeap != ProcessHeap )
  {
    HeapCompact(ghTapisrvHeap, 0);
    v4 = ghTapisrvHeap;
  }
  if ( !a1 )
  {
    qword_180051910 = 0;
    v5 = HeapAlloc(v4, 8u, 0x290u);
    qword_180051920 = v5;
    if ( !v5 )
      return (unsigned int)-2147483580;
    v7 = ghTapisrvHeap;
    *v5 = 16;
    v8 = HeapAlloc(v7, 8u, 0x290u);
    qword_180051930 = v8;
    if ( !v8 )
    {
      ServerFree(qword_180051920);
      qword_180051920 = 0;
      return (unsigned int)-2147483580;
    }
    *v8 = 16;
    gbQueueSPEvents = 1;
    OnProxySCPInit();
  }
  WaitForSingleObject(ghProvRegistryMutex, 0xFFFFFFFF);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony", 0, 0xF003Fu, &hKey);
  if ( v6 )
    return v6;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony\\Providers",
         0,
         0xF003Fu,
         &v69);
  if ( v6 )
  {
    RegCloseKey(hKey);
    return v6;
  }
  cbData = 4;
  *(_DWORD *)Data = 0;
  RegQueryValueExW(v69, L"NumProviders", 0, &Type, Data, &cbData);
  TRACELogPrint(262146, "ServerInit: NumProviders=%d", *(_DWORD *)Data);
  for ( i = 0; ; i = v68 + 1 )
  {
    v68 = i;
    if ( i >= *(_DWORD *)Data )
      break;
    v63 = 0;
    v62 = 0;
    *(_DWORD *)v65 = 0;
    LODWORD(phkResult) = i;
    StringCbPrintfW(pszDest, 0x40u, L"%s%d", L"ProviderID", phkResult);
    cbData = 4;
    *(_DWORD *)v65 = 0;
    RegQueryValueExW(v69, pszDest, 0, &Type, v65, &cbData);
    LODWORD(phkResulta) = v68;
    cbData = 128;
    StringCbPrintfW(pszDest, 0x40u, L"%s%d", L"ProviderFilename", phkResulta);
    if ( RegQueryValueExW(v69, pszDest, 0, &Type, v72, &cbData) )
      continue;
    v10 = (cbData & 0xFFFFFFFE) - 2LL;
    if ( v10 >= 0x100 )
      _report_rangecheckfailure();
    *(_WORD *)&v72[v10] = 0;
    v11 = 0;
    v12 = *(_WORD *)v72;
    if ( *(_WORD *)v72 )
    {
      v13 = v72;
      do
      {
        v13 += 2;
        v1 += v12;
        v12 = *(_WORD *)v13;
      }
      while ( *(_WORD *)v13 );
    }
    if ( a1 )
    {
      for ( j = qword_180051910; j; j = (LPVOID)*((_QWORD *)j + 6) )
      {
        if ( *((_DWORD *)j + 298) == v1 && !lstrcmpiW((LPCWSTR)j + 598, (LPCWSTR)v72) )
          goto LABEL_28;
      }
    }
    TRACELogPrint(262146, "ServerInit: ProviderFilename=%S", (const wchar_t *)v72);
    v15 = lstrlenW((LPCWSTR)v72);
    v16 = 2LL * v15 + 2;
    v17 = HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)(2 * v15 + 1202));
    if ( !v17 )
      break;
    LibraryW = LoadLibraryW((LPCWSTR)v72);
    *((_QWORD *)v17 + 2) = LibraryW;
    if ( LibraryW )
    {
      v17[298] = v1;
      StringCbCopyW((STRSAFE_LPWSTR)v17 + 598, v16, (STRSAFE_LPCWSTR)v72);
      for ( k = 0; gaszTSPIFuncNames[k]; k = (unsigned int)(k + 1) )
        *(_QWORD *)&v17[2 * k + 32] = GetProcAddress(*((HMODULE *)v17 + 2), gaszTSPIFuncNames[k]);
      v1 = 0;
      v21 = 0;
      v63 = 0;
      v62 = 0;
      v22 = (unsigned int (__fastcall *)(__int64, __int64, __int64, _DWORD *))*((_QWORD *)v17 + 57);
      if ( v22 && *((_QWORD *)v17 + 120) && *((_QWORD *)v17 + 123) && *((_QWORD *)v17 + 124) )
      {
        if ( v22(0xFFFFFFFFLL, 65539, 196609, v17 + 7) )
          goto LABEL_67;
        phkResult = (PHKEY)LineEventProcSP;
        v23 = (*((__int64 (__fastcall **)(_QWORD, unsigned int *, unsigned int *, _DWORD *))v17 + 120))(
                *(unsigned int *)v65,
                &v63,
                &v62,
                v17);
        if ( v23 )
        {
          TRACELogPrint(65538, "ServerInit: %ls: failed TSPI_providerEnumDevices, err=x%x - skipping it...", v72, v23);
LABEL_67:
          if ( *((_QWORD *)v17 + 1) )
            MyCloseMutex();
          v41 = (void *)*((_QWORD *)v17 + 10);
          if ( v41 )
            CloseHandle(v41);
          v42 = (void *)*((_QWORD *)v17 + 8);
          if ( v42 )
            ServerFree(v42);
LABEL_52:
          FreeLibrary(*((HMODULE *)v17 + 2));
          ServerFree(v17);
          continue;
        }
        TRACELogPrint(262146, "ServerInit: %ls: Calling TSPI_providerInit", (const wchar_t *)v72);
        v11 = 1;
        if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)v72, -1, L"kmddsp.tsp", -1) != 2
          && CompareStringW(0x7Fu, 1u, (PCNZWCH)v72, -1, L"remotesp.tsp", -1) == 2 )
        {
          pRemoteSP = (__int64)v17;
        }
        GetNumPhoneLookupEntries(v24, v17 + 6, v25);
        NumLineLookupEntries = GetNumLineLookupEntries(v27, v26);
        phkResult = v29;
        v30 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))v17 + 123))(
                (unsigned int)v17[7],
                *(unsigned int *)v65,
                NumLineLookupEntries);
        if ( v30 )
        {
          TRACELogPrint(65538, "ServerInit: %ls: failed TSPI_providerInit, err=x%x - skipping it...", v72, v30);
          goto LABEL_67;
        }
        TRACELogPrint(262146, "ServerInit: %ls init'd, dwNumLines=%lu, dwNumPhones=%lu", (const wchar_t *)v72, v63, v62);
        v21 = v62;
      }
      v71[0] = 41;
      v31 = 90;
      v71[1] = 107;
      v71[2] = 108;
      v71[4] = -1;
      LODWORD(v32) = 0;
      v33 = 1;
      if ( !v21 )
        v31 = -1;
      v71[3] = v31;
      do
      {
        v34 = (unsigned int)v71[(unsigned int)v32];
        if ( !*(_QWORD *)&v17[2 * v34 + 32] )
        {
          TRACELogPrint(
            65538,
            "ServerInit: %ls: can't init, function [%hs] not exported",
            (const wchar_t *)v72,
            gaszTSPIFuncNames[v34]);
          v33 = 0;
        }
        v32 = (unsigned int)(v32 + 1);
      }
      while ( v71[v32] != -1 );
      if ( !v33 )
        goto LABEL_52;
      v17[8] = *(_DWORD *)v65;
      *((_QWORD *)v17 + 1) = CreateMutexW(0, 0, 0);
      InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v17 + 22), 0x3E8u);
      EventW = CreateEventW(0, 0, 0, 0);
      v36 = ghTapisrvHeap;
      *((_QWORD *)v17 + 10) = EventW;
      v17[14] = 31;
      v37 = HeapAlloc(v36, 8u, 0x4D8u);
      *((_QWORD *)v17 + 8) = v37;
      if ( v37 )
      {
        v38 = 0;
        if ( v17[14] )
        {
          v39 = v37 + 1;
          do
          {
            v37[2] = v39;
            v37 += 5;
            *v39 = v39;
            v38 = (unsigned int)(v38 + 1);
            v39 += 5;
          }
          while ( (unsigned int)v38 < v17[14] );
        }
      }
      else
      {
        v17[14] = 0;
      }
      if ( !*((_QWORD *)v17 + 1) || !*((_QWORD *)v17 + 10) || !*((_QWORD *)v17 + 8) )
        goto LABEL_65;
      if ( gbNTServer )
      {
        v40 = AddProviderToIdArrayList(v17, v63, v62);
        if ( v40 )
        {
          TRACELogPrint(
            65538,
            "ServerInit: %ls: failed AddProviderToIdArrayList [x%x] - skipping it...",
            (const wchar_t *)v17 + 598,
            v40);
LABEL_65:
          DeleteCriticalSection((LPCRITICAL_SECTION)(v17 + 22));
          if ( v11 )
            (*((void (__fastcall **)(_QWORD, _QWORD))v17 + 124))((unsigned int)v17[7], (unsigned int)v17[8]);
          goto LABEL_67;
        }
      }
      v44 = GetNumLineLookupEntries(v39, v38);
      v46 = v44 + v63;
      v47 = v44;
      if ( v44 < (unsigned int)v46 )
      {
        do
        {
          AddLine(v17, v47++, a1 == 0);
          v43 = v44 + v63;
        }
        while ( v47 < (unsigned int)v43 );
      }
      NumPhoneLookupEntries = GetNumPhoneLookupEntries(v43, v46, v45);
      for ( m = NumPhoneLookupEntries; m < NumPhoneLookupEntries + v62; ++m )
        AddPhone(v17, m, a1 == 0);
      v1 = 0;
      *((_QWORD *)v17 + 5) = 0;
      *((_QWORD *)v17 + 6) = qword_180051910;
      if ( qword_180051910 )
        *((_QWORD *)qword_180051910 + 5) = v17;
      qword_180051910 = v17;
      *v17 = 1448038992;
    }
    else
    {
      LastError = GetLastError();
      TRACELogPrint(65538, "ServerInit: LoadLibrary(%S) failed, err=x%x", (const wchar_t *)v72, LastError);
      ServerFree(v17);
LABEL_28:
      v1 = 0;
    }
  }
  RegCloseKey(v69);
  RegCloseKey(hKey);
  ReleaseMutex(ghProvRegistryMutex);
  if ( a1 )
  {
    v50 = dword_18005191C;
    v51 = dword_18005192C;
  }
  else
  {
    v50 = 0;
    v51 = 0;
  }
  dword_18005191C = ((__int64 (*)(void))GetNumLineLookupEntries)();
  dword_18005192C = GetNumPhoneLookupEntries(v53, v52, (unsigned int)dword_18005191C);
  v56 = dword_18005192C;
  if ( a1 )
  {
    v57 = v50;
    if ( v50 < v54 )
    {
      do
        SendAMsgToAllLineApps(-2147418108, 19, v57++, 0, 0);
      while ( v57 < dword_18005191C );
      v56 = dword_18005192C;
    }
    if ( v50 < dword_18005191C )
    {
      SendAMsgToAllLineApps(65539, 8, 0x40000, 0, 0);
      v56 = dword_18005192C;
    }
    v58 = v51;
    if ( v51 < v56 )
    {
      do
      {
        SendAMsgToAllPhoneApps(-2147418108, 20, v58, v55, (_DWORD)phkResult);
        v56 = dword_18005192C;
        ++v58;
      }
      while ( v58 < dword_18005192C );
      if ( v51 < dword_18005192C )
      {
        SendAMsgToAllPhoneApps(65539, 18, 0x200000, v55, (_DWORD)phkResult);
        v56 = dword_18005192C;
      }
    }
    if ( v50 >= dword_18005191C )
      goto LABEL_99;
    do
      AppendNewDeviceInfo(1, v50++);
    while ( v50 < dword_18005191C );
    while ( 1 )
    {
      v56 = dword_18005192C;
LABEL_99:
      if ( v51 >= v56 )
        break;
      AppendNewDeviceInfo(0, v51++);
    }
  }
  dword_1800518A4 = dword_18005191C;
  dword_1800518A8 = v56;
  return v6;
}

```

## disassembly

```asm
0x18002c8fc  push    rbp
0x18002c8fe  push    rbx
0x18002c8ff  push    rsi
0x18002c900  push    rdi
0x18002c901  push    r12
0x18002c903  push    r13
0x18002c905  push    r14
0x18002c907  push    r15
0x18002c909  lea     rbp, [rsp-0F8h]
0x18002c911  sub     rsp, 1F8h
0x18002c918  mov     rax, cs:__security_cookie
0x18002c91f  xor     rax, rsp
0x18002c922  mov     [rbp+130h+var_50], rax
0x18002c929  xor     esi, esi
0x18002c92b  mov     r12d, ecx
0x18002c92e  mov     dword ptr [rsp+230h+Data], esi
0x18002c932  mov     [rsp+230h+hKey], rsi
0x18002c937  mov     [rsp+230h+var_1C0], rsi
0x18002c93c  mov     [rsp+230h+cbData], esi
0x18002c940  mov     [rsp+230h+Type], esi
0x18002c944  call    cs:__imp_GetProcessHeap
0x18002c94a  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002c951  cmp     rcx, rax
0x18002c954  jz      short loc_18002C965
0x18002c956  xor     edx, edx; dwFlags
0x18002c958  call    cs:__imp_HeapCompact
0x18002c95e  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002c965  test    r12d, r12d
0x18002c968  jnz     short loc_18002C9E7
0x18002c96a  mov     edi, 290h
0x18002c96f  mov     cs:qword_180051910, rsi
0x18002c976  mov     r8d, edi; dwBytes
0x18002c979  lea     edx, [r12+8]; dwFlags
0x18002c97e  call    cs:__imp_HeapAlloc
0x18002c984  mov     cs:qword_180051920, rax
0x18002c98b  test    rax, rax
0x18002c98e  jnz     short loc_18002C99B
0x18002c990  mov     r14d, 80000044h
0x18002c996  jmp     loc_18002D24F
0x18002c99b  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002c9a2  mov     ebx, 10h
0x18002c9a7  mov     r8, rdi; dwBytes
0x18002c9aa  mov     [rax], ebx
0x18002c9ac  lea     edx, [rbx-8]; dwFlags
0x18002c9af  call    cs:__imp_HeapAlloc
0x18002c9b5  mov     cs:qword_180051930, rax
0x18002c9bc  test    rax, rax
0x18002c9bf  jnz     short loc_18002C9D6
0x18002c9c1  mov     rcx, cs:qword_180051920; lpMem
0x18002c9c8  call    ServerFree
0x18002c9cd  mov     cs:qword_180051920, rsi
0x18002c9d4  jmp     short loc_18002C990
0x18002c9d6  mov     [rax], ebx
0x18002c9d8  mov     cs:gbQueueSPEvents, 1
0x18002c9e2  call    OnProxySCPInit
0x18002c9e7  mov     rcx, cs:ghProvRegistryMutex; hHandle
0x18002c9ee  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002c9f1  call    cs:__imp_WaitForSingleObject
0x18002c9f7  lea     rax, [rsp+230h+hKey]
0x18002c9fc  mov     ebx, 0F003Fh
0x18002ca01  mov     rdi, 0FFFFFFFF80000002h
0x18002ca08  mov     [rsp+230h+phkResult], rax; phkResult
0x18002ca0d  mov     r9d, ebx; samDesired
0x18002ca10  lea     rdx, gszRegKeyTelephony; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002ca17  mov     rcx, rdi; hKey
0x18002ca1a  xor     r8d, r8d; ulOptions
0x18002ca1d  call    cs:__imp_RegOpenKeyExW
0x18002ca23  mov     r14d, eax
0x18002ca26  test    eax, eax
0x18002ca28  jnz     loc_18002D24F
0x18002ca2e  lea     rax, [rsp+230h+var_1C0]
0x18002ca33  mov     r9d, ebx; samDesired
0x18002ca36  xor     r8d, r8d; ulOptions
0x18002ca39  mov     [rsp+230h+phkResult], rax; phkResult
0x18002ca3e  lea     rdx, gszRegKeyProviders; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002ca45  mov     rcx, rdi; hKey
0x18002ca48  call    cs:__imp_RegOpenKeyExW
0x18002ca4e  mov     r14d, eax
0x18002ca51  test    eax, eax
0x18002ca53  jz      short loc_18002CA65
0x18002ca55  mov     rcx, [rsp+230h+hKey]; hKey
0x18002ca5a  call    cs:__imp_RegCloseKey
0x18002ca60  jmp     loc_18002D24F
0x18002ca65  mov     rcx, [rsp+230h+var_1C0]; hKey
0x18002ca6a  lea     rax, [rsp+230h+cbData]
0x18002ca6f  mov     [rsp+230h+lpcbData], rax; lpcbData
0x18002ca74  lea     r9, [rsp+230h+Type]; lpType
0x18002ca79  lea     rax, [rsp+230h+Data]
0x18002ca7e  mov     [rsp+230h+cbData], 4
0x18002ca86  xor     r8d, r8d; lpReserved
0x18002ca89  mov     [rsp+230h+phkResult], rax; lpData
0x18002ca8e  lea     rdx, gszNumProviders; "NumProviders"
0x18002ca95  mov     dword ptr [rsp+230h+Data], esi
0x18002ca99  call    cs:__imp_RegQueryValueExW
0x18002ca9f  mov     r8d, dword ptr [rsp+230h+Data]
0x18002caa4  lea     rdx, aServerinitNump; "ServerInit: NumProviders=%d"
0x18002caab  mov     ecx, 40002h
0x18002cab0  call    TRACELogPrint
0x18002cab5  mov     eax, esi
0x18002cab7  mov     [rsp+230h+var_1C8], eax
0x18002cabb  cmp     eax, dword ptr [rsp+230h+Data]
0x18002cabf  jnb     loc_18002D105
0x18002cac5  lea     r9, gszProviderID; "ProviderID"
0x18002cacc  mov     [rsp+230h+var_1DC], esi
0x18002cad0  lea     r8, aSD; "%s%d"
0x18002cad7  mov     [rsp+230h+var_1E0], esi
0x18002cadb  mov     edx, 40h ; '@'; cbDest
0x18002cae0  mov     dword ptr [rsp+230h+var_1D4], esi
0x18002cae4  lea     rcx, [rbp+130h+pszDest]; pszDest
0x18002caeb  mov     dword ptr [rsp+230h+phkResult], eax
0x18002caef  call    StringCbPrintfW
0x18002caf4  mov     rcx, [rsp+230h+var_1C0]; hKey
0x18002caf9  lea     rax, [rsp+230h+cbData]
0x18002cafe  mov     [rsp+230h+lpcbData], rax; lpcbData
0x18002cb03  lea     r9, [rsp+230h+Type]; lpType
0x18002cb08  lea     rax, [rsp+230h+var_1D4]
0x18002cb0d  mov     [rsp+230h+cbData], 4
0x18002cb15  xor     r8d, r8d; lpReserved
0x18002cb18  mov     [rsp+230h+phkResult], rax; lpData
0x18002cb1d  lea     rdx, [rbp+130h+pszDest]; lpValueName
0x18002cb24  mov     dword ptr [rsp+230h+var_1D4], esi
0x18002cb28  call    cs:__imp_RegQueryValueExW
0x18002cb2e  mov     eax, [rsp+230h+var_1C8]
0x18002cb32  lea     r9, gszProviderFilename; "ProviderFilename"
0x18002cb39  lea     r8, aSD; "%s%d"
0x18002cb40  mov     dword ptr [rsp+230h+phkResult], eax
0x18002cb44  mov     edx, 40h ; '@'; cbDest
0x18002cb49  mov     [rsp+230h+cbData], 80h
0x18002cb51  lea     rcx, [rbp+130h+pszDest]; pszDest
0x18002cb58  call    StringCbPrintfW
0x18002cb5d  mov     rcx, [rsp+230h+var_1C0]; hKey
0x18002cb62  lea     rax, [rsp+230h+cbData]
0x18002cb67  mov     [rsp+230h+lpcbData], rax; lpcbData
0x18002cb6c  lea     r9, [rsp+230h+Type]; lpType
0x18002cb71  lea     rax, [rbp+130h+var_190]
0x18002cb75  xor     r8d, r8d; lpReserved
0x18002cb78  lea     rdx, [rbp+130h+pszDest]; lpValueName
0x18002cb7f  mov     [rsp+230h+phkResult], rax; lpData
0x18002cb84  call    cs:__imp_RegQueryValueExW
0x18002cb8a  test    eax, eax
0x18002cb8c  jnz     loc_18002CC93
0x18002cb92  mov     ecx, [rsp+230h+cbData]
0x18002cb96  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18002cb9a  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18002cb9e  cmp     rcx, 100h
0x18002cba5  jnb     loc_18002D0FD
0x18002cbab  mov     word ptr [rbp+rcx+130h+var_190], si
0x18002cbb0  xor     r15d, r15d
0x18002cbb3  movzx   eax, word ptr [rbp+130h+var_190]
0x18002cbb7  test    ax, ax
0x18002cbba  jz      short loc_18002CBD1
0x18002cbbc  lea     rcx, [rbp+130h+var_190]
0x18002cbc0  movzx   eax, ax
0x18002cbc3  lea     rcx, [rcx+2]
0x18002cbc7  add     esi, eax
0x18002cbc9  movzx   eax, word ptr [rcx]
0x18002cbcc  test    ax, ax
0x18002cbcf  jnz     short loc_18002CBC0
0x18002cbd1  test    r12d, r12d
0x18002cbd4  jz      short loc_18002CC09
0x18002cbd6  mov     rbx, cs:qword_180051910
0x18002cbdd  test    rbx, rbx
0x18002cbe0  jz      short loc_18002CC09
0x18002cbe2  cmp     [rbx+4A8h], esi
0x18002cbe8  jnz     short loc_18002CC03
0x18002cbea  lea     rcx, [rbx+4ACh]; lpString1
0x18002cbf1  lea     rdx, [rbp+130h+var_190]; lpString2
0x18002cbf5  call    cs:__imp_lstrcmpiW
0x18002cbfb  test    eax, eax
0x18002cbfd  jz      loc_18002CC91
0x18002cc03  mov     rbx, [rbx+30h]
0x18002cc07  jmp     short loc_18002CBDD
0x18002cc09  lea     r8, [rbp+130h+var_190]
0x18002cc0d  mov     ecx, 40002h
0x18002cc12  lea     rdx, aServerinitProv; "ServerInit: ProviderFilename=%S"
0x18002cc19  call    TRACELogPrint
0x18002cc1e  lea     rcx, [rbp+130h+var_190]; lpString
0x18002cc22  call    cs:__imp_lstrlenW
0x18002cc28  movsxd  rcx, eax
0x18002cc2b  mov     edx, 8; dwFlags
0x18002cc30  lea     rbx, ds:2[rcx*2]
0x18002cc38  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002cc3f  lea     r8d, [rbx+4B0h]; dwBytes
0x18002cc46  call    cs:__imp_HeapAlloc
0x18002cc4c  mov     rdi, rax
0x18002cc4f  test    rax, rax
0x18002cc52  jz      loc_18002D103
0x18002cc58  lea     rcx, [rbp+130h+var_190]; lpLibFileName
0x18002cc5c  call    cs:__imp_LoadLibraryW
0x18002cc62  mov     [rdi+10h], rax
0x18002cc66  test    rax, rax
0x18002cc69  jnz     short loc_18002CC9E
0x18002cc6b  call    cs:__imp_GetLastError
0x18002cc71  lea     r8, [rbp+130h+var_190]
0x18002cc75  mov     ecx, 10002h
0x18002cc7a  mov     r9d, eax
0x18002cc7d  lea     rdx, aServerinitLoad; "ServerInit: LoadLibrary(%S) failed, err"...
0x18002cc84  call    TRACELogPrint
0x18002cc89  mov     rcx, rdi; lpMem
0x18002cc8c  call    ServerFree
0x18002cc91  xor     esi, esi
0x18002cc93  mov     eax, [rsp+230h+var_1C8]
0x18002cc97  inc     eax
0x18002cc99  jmp     loc_18002CAB7
0x18002cc9e  lea     rcx, [rdi+4ACh]; pszDest
0x18002cca5  mov     [rdi+4A8h], esi
0x18002ccab  lea     r8, [rbp+130h+var_190]; pszSrc
0x18002ccaf  mov     rdx, rbx; cbDest
0x18002ccb2  call    StringCbCopyW
0x18002ccb7  xor     esi, esi
0x18002ccb9  cmp     cs:gaszTSPIFuncNames, rsi
0x18002ccc0  jz      short loc_18002CCE9
0x18002ccc2  lea     r13, gaszTSPIFuncNames
0x18002ccc9  mov     rdx, [r13+rsi*8+0]; lpProcName
0x18002ccce  mov     rcx, [rdi+10h]; hModule
0x18002ccd2  call    cs:__imp_GetProcAddress
0x18002ccd8  mov     [rdi+rsi*8+80h], rax
0x18002cce0  inc     esi
0x18002cce2  cmp     [r13+rsi*8+0], r15
0x18002cce7  jnz     short loc_18002CCC9
0x18002cce9  xor     esi, esi
0x18002cceb  mov     ecx, esi
0x18002cced  mov     [rsp+230h+var_1DC], esi
0x18002ccf1  mov     [rsp+230h+var_1E0], ecx
0x18002ccf5  mov     rax, [rdi+1C8h]
0x18002ccfc  test    rax, rax
0x18002ccff  jz      loc_18002CEA4
0x18002cd05  cmp     [rdi+3C0h], rsi
0x18002cd0c  jz      loc_18002CEA4
0x18002cd12  cmp     [rdi+3D8h], rsi
0x18002cd19  jz      loc_18002CEA4
0x18002cd1f  cmp     [rdi+3E0h], rsi
0x18002cd26  jz      loc_18002CEA4
0x18002cd2c  lea     r9, [rdi+1Ch]
0x18002cd30  mov     edx, 10003h
0x18002cd35  mov     r8d, 30001h
0x18002cd3b  or      ecx, 0FFFFFFFFh
0x18002cd3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd43  test    eax, eax
0x18002cd45  jnz     loc_18002D02A
0x18002cd4b  mov     ecx, dword ptr [rsp+230h+var_1D4]
0x18002cd4f  lea     rax, PhoneEventProcSP
0x18002cd56  mov     [rsp+230h+lpcbData], rax
0x18002cd5b  lea     r8, [rsp+230h+var_1E0]
0x18002cd60  lea     rax, LineEventProcSP
0x18002cd67  mov     r9, rdi
0x18002cd6a  mov     [rsp+230h+phkResult], rax
0x18002cd6f  lea     rdx, [rsp+230h+var_1DC]
0x18002cd74  mov     rax, [rdi+3C0h]
0x18002cd7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd80  lea     r8, [rbp+130h+var_190]
0x18002cd84  test    eax, eax
0x18002cd86  jz      short loc_18002CDA1
0x18002cd88  lea     rdx, aServerinitLsFa_1; "ServerInit: %ls: failed TSPI_providerEn"...
0x18002cd8f  mov     r9d, eax
0x18002cd92  mov     ecx, 10002h
0x18002cd97  call    TRACELogPrint
0x18002cd9c  jmp     loc_18002D02A
0x18002cda1  lea     rdx, aServerinitLsCa; "ServerInit: %ls: Calling TSPI_providerI"...
0x18002cda8  mov     ecx, 40002h
0x18002cdad  call    TRACELogPrint
0x18002cdb2  or      ecx, 0FFFFFFFFh
0x18002cdb5  lea     rax, aKmddspTsp; "kmddsp.tsp"
0x18002cdbc  mov     dword ptr [rsp+230h+lpcbData], ecx; cchCount2
0x18002cdc0  lea     r8, [rbp+130h+var_190]; lpString1
0x18002cdc4  mov     r9d, ecx; cchCount1
0x18002cdc7  mov     [rsp+230h+phkResult], rax; lpString2
0x18002cdcc  lea     r15d, [rcx+2]
0x18002cdd0  mov     edx, r15d; dwCmpFlags
0x18002cdd3  lea     ecx, [r15+7Eh]; Locale
0x18002cdd7  call    cs:__imp_CompareStringW
0x18002cddd  cmp     eax, 2
0x18002cde0  jnz     short loc_18002CDEE
0x18002cde2  lea     r10, [rsp+230h+var_1E0]
0x18002cde7  lea     r11, [rsp+230h+var_1DC]
0x18002cdec  jmp     short loc_18002CE2C
0x18002cdee  or      ecx, 0FFFFFFFFh
0x18002cdf1  lea     rax, String2; "remotesp.tsp"
0x18002cdf8  mov     dword ptr [rsp+230h+lpcbData], ecx; cchCount2
0x18002cdfc  lea     r8, [rbp+130h+var_190]; lpString1
0x18002ce00  mov     r9d, ecx; cchCount1
0x18002ce03  mov     [rsp+230h+phkResult], rax; lpString2
0x18002ce08  mov     ecx, 7Fh; Locale
0x18002ce0d  mov     edx, r15d; dwCmpFlags
0x18002ce10  call    cs:__imp_CompareStringW
0x18002ce16  cmp     eax, 2
0x18002ce19  jnz     short loc_18002CE22
0x18002ce1b  mov     cs:pRemoteSP, rdi
0x18002ce22  mov     r10d, [rsp+230h+var_1E0]
0x18002ce27  mov     r11d, [rsp+230h+var_1DC]
0x18002ce2c  lea     rdx, [rdi+18h]
0x18002ce30  call    GetNumPhoneLookupEntries
0x18002ce35  mov     r9d, eax
0x18002ce38  call    GetNumLineLookupEntries
0x18002ce3d  mov     ecx, [rdi+1Ch]
0x18002ce40  mov     r8d, eax
0x18002ce43  mov     [rsp+230h+var_1F8], rdx
0x18002ce48  lea     rax, CompletionProcSP
0x18002ce4f  mov     edx, dword ptr [rsp+230h+var_1D4]
0x18002ce53  mov     [rsp+230h+var_200], rax
  ... truncated ...
```
