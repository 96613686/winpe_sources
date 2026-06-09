# GetUIDllName

- ea: `0x18002a8c0`
- end: `0x18002b05e`
- name: `GetUIDllName`
- size: `1950`
- prototype: `void __fastcall(unsigned __int64, int *, unsigned int, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028100`

## callees

- `0x180001600`
- `0x180006f24`
- `0x1800072e4`
- `0x18001c8a4`
- `0x18001f494`
- `0x180021640`
- `0x18002a8c0`
- `0x18002c8d4`
- `0x18003dc84`
- `0x18003e15c`
- `0x18003e2f0`
- `0x18003fb7c`
- `0x180040010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002abf5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ae90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002abf5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ae90`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ae85`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ae85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002aa15`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ae03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002aa15`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ae03`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002aa80`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002aae3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ab4c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ae3e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002aa80`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002aae3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ab4c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ae3e`
- `KERNEL32!HeapAlloc` at `0x18002a991`
- `KERNEL32!HeapAlloc` at `0x18002ada4`
- `KERNEL32!HeapAlloc` at `0x18002a991`
- `KERNEL32!HeapAlloc` at `0x18002ada4`
- `KERNEL32!CompareStringW` at `0x18002ac55`
- `KERNEL32!CompareStringW` at `0x18002ac55`
- `KERNEL32!FreeLibrary` at `0x18002acb6`
- `KERNEL32!FreeLibrary` at `0x18002acb6`
- `KERNEL32!GetProcAddress` at `0x18002ab97`
- `KERNEL32!GetProcAddress` at `0x18002abd8`
- `KERNEL32!GetProcAddress` at `0x18002ad6e`
- `KERNEL32!GetProcAddress` at `0x18002add8`
- `KERNEL32!GetProcAddress` at `0x18002ab97`
- `KERNEL32!GetProcAddress` at `0x18002abd8`
- `KERNEL32!GetProcAddress` at `0x18002ad6e`
- `KERNEL32!GetProcAddress` at `0x18002add8`
- `KERNEL32!LoadLibraryW` at `0x18002ab56`
- `KERNEL32!LoadLibraryW` at `0x18002ad40`
- `KERNEL32!LoadLibraryW` at `0x18002ab56`
- `KERNEL32!LoadLibraryW` at `0x18002ad40`
- `KERNEL32!GetLastError` at `0x18002aa1f`
- `KERNEL32!GetLastError` at `0x18002ab65`
- `KERNEL32!GetLastError` at `0x18002aba5`
- `KERNEL32!GetLastError` at `0x18002ad4f`
- `KERNEL32!GetLastError` at `0x18002aa1f`
- `KERNEL32!GetLastError` at `0x18002ab65`
- `KERNEL32!GetLastError` at `0x18002aba5`
- `KERNEL32!GetLastError` at `0x18002ad4f`
- `KERNEL32!LeaveCriticalSection` at `0x18002b053`
- `KERNEL32!LeaveCriticalSection` at `0x18002b053`
- `KERNEL32!lstrlenW` at `0x18002ac8c`
- `KERNEL32!lstrlenW` at `0x18002ad83`
- `KERNEL32!lstrlenW` at `0x18002ac8c`
- `KERNEL32!lstrlenW` at `0x18002ad83`

## string_xrefs

- `0x18002a90d`: `Entering GetUIDllName`
- `0x18002aa25`: `RegOpenKeyEx(/Providers) failed, err=%u`
- `0x18002ab6f`: `LoadLibrary('%ls') failed - err=%u`
- `0x18002ad58`: `LoadLibrary('%ls') failed   err=%u`

## pseudocode

```c
void __fastcall GetUIDllName(unsigned __int64 a1, int *a2, unsigned int a3, _DWORD *a4, __int64 a5)
{
  __int64 v5; // r13
  _DWORD *v6; // rbx
  int v7; // eax
  int v10; // edi
  FARPROC ProcAddress; // r12
  unsigned int *v12; // rsi
  unsigned int *v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // eax
  __int64 v16; // r8
  DWORD LastError; // eax
  __int64 v18; // rcx
  int v19; // ebx
  HMODULE LibraryW; // rax
  DWORD v21; // eax
  DWORD v22; // eax
  unsigned int v23; // edi
  unsigned int v24; // ebx
  HMODULE v25; // rcx
  void *v26; // rcx
  __int64 v27; // rcx
  const WCHAR *v28; // rbx
  HMODULE v29; // rax
  DWORD v30; // eax
  void *v31; // rax
  HKEY v32; // rcx
  int v33; // eax
  __int64 PhoneLookupEntry; // rax
  __int64 v35; // r12
  __int64 LineLookupEntry; // rax
  __int64 v37; // rax
  _DWORD *v38; // rcx
  __int64 v39; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  int v42; // [rsp+34h] [rbp-CCh]
  BYTE Data[4]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v44[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD lpcbData; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v48[4]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v49; // [rsp+58h] [rbp-A8h]
  HKEY v50; // [rsp+60h] [rbp-A0h] BYREF
  void *v51; // [rsp+68h] [rbp-98h]
  DWORD v52; // [rsp+70h] [rbp-90h] BYREF
  __int64 v53; // [rsp+78h] [rbp-88h]
  wchar_t pszDest[32]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR v55[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR String[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v5 = 0;
  v53 = a5;
  v6 = a4;
  v7 = a2[2];
  v51 = a4;
  v49 = a3;
  v42 = v7;
  v10 = 0;
  ProcAddress = 0;
  v12 = 0;
  TRACELogPrint(524290, "Entering GetUIDllName");
  if ( a2[3] == 1 )
  {
    if ( (dword_180051900 & 2) == 0 || (*(_BYTE *)(a1 + 216) & 1) != 0 )
    {
      v23 = v42;
    }
    else
    {
      if ( (unsigned int)a2[2] >= *(_DWORD *)(a1 + 96) )
      {
        *a2 = -2147483576;
        return;
      }
      v23 = *(_DWORD *)(*(_QWORD *)(a1 + 88) + 4LL * (unsigned int)a2[2]);
      v42 = v23;
    }
    if ( !dword_180051918 )
    {
      v10 = -2147483568;
      goto LABEL_43;
    }
    LineLookupEntry = GetLineLookupEntry(v23);
    v5 = LineLookupEntry;
    if ( !LineLookupEntry )
    {
      v10 = -2147483646;
      goto LABEL_43;
    }
    v37 = *(_QWORD *)(LineLookupEntry + 24);
    if ( v37 && !*(_DWORD *)(v5 + 32) )
    {
      ProcAddress = *(FARPROC *)(v37 + 1000);
      if ( !ProcAddress )
      {
        v10 = -2147483575;
        goto LABEL_43;
      }
      goto LABEL_32;
    }
    v10 = -2147483582;
LABEL_29:
    if ( !ProcAddress )
      goto LABEL_43;
    if ( !v5 )
    {
LABEL_34:
      v10 = ((__int64 (__fastcall *)(WCHAR *))ProcAddress)(String);
      if ( !v10 )
      {
        v24 = 2 * lstrlenW(String) + 2;
        if ( v49 >= v24 )
        {
          memcpy_0(v51, String, v24);
          v38 = (_DWORD *)v53;
          a2[4] = 0;
          a2[5] = v24;
          *v38 = v24 + 60;
          if ( WaitForExclusiveClientAccess(a1) )
          {
            if ( v12 )
            {
              *v12 = 1196379204;
              v39 = *(_QWORD *)(a1 + 184);
              *((_QWORD *)v12 + 10) = v39;
              if ( v39 )
                *(_QWORD *)(v39 + 72) = v12;
              *(_QWORD *)(a1 + 184) = v12;
              a2[8] = v12[22];
            }
            LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits
                                                                 & (a1 >> 4)));
          }
          goto LABEL_43;
        }
        v10 = -2147483576;
      }
      if ( v12 )
        goto LABEL_38;
LABEL_43:
      *a2 = v10;
      return;
    }
    v23 = v42;
LABEL_32:
    if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)(*(_QWORD *)(v5 + 24) + 1196LL), -1, L"remotesp.tsp", -1) == 2 )
    {
      *v6 = 1381521745;
      v6[1] = v23;
      v6[2] = a2[3];
    }
    goto LABEL_34;
  }
  if ( a2[3] == 2 )
  {
    if ( (dword_180051900 & 2) == 0 || (*(_BYTE *)(a1 + 216) & 1) != 0 )
    {
      v23 = v42;
    }
    else
    {
      if ( (unsigned int)a2[2] >= *(_DWORD *)(a1 + 120) )
      {
        *a2 = -1879048164;
        return;
      }
      v23 = *(_DWORD *)(*(_QWORD *)(a1 + 112) + 4LL * (unsigned int)a2[2]);
    }
    if ( !dword_180051928 )
    {
      v10 = -1879048158;
      goto LABEL_43;
    }
    PhoneLookupEntry = GetPhoneLookupEntry(v23);
    v5 = PhoneLookupEntry;
    if ( !PhoneLookupEntry )
    {
      v10 = -1879048190;
      goto LABEL_43;
    }
    v35 = *(_QWORD *)(PhoneLookupEntry + 24);
    if ( !v35 || *(_DWORD *)(PhoneLookupEntry + 32) )
    {
      v10 = -1879048168;
      goto LABEL_43;
    }
    ProcAddress = *(FARPROC *)(v35 + 1000);
    if ( !ProcAddress )
    {
      v10 = -1879048163;
      goto LABEL_43;
    }
    goto LABEL_32;
  }
  if ( a2[3] != 3 )
    goto LABEL_43;
  TRACELogPrint(262146, "Looking for provider...");
  if ( (*(_BYTE *)(a1 + 216) & 8) == 0 && (a2[7] || a2[6] != -1) )
    goto LABEL_7;
  v13 = (unsigned int *)HeapAlloc(ghTapisrvHeap, 8u, 0x60u);
  v12 = v13;
  if ( !v13 )
  {
LABEL_9:
    v10 = -2147483580;
    goto LABEL_43;
  }
  v15 = NewObject(v14, v13, 0);
  v12[22] = v15;
  if ( !v15 )
  {
    ServerFree(v12);
    goto LABEL_9;
  }
  v12[4] = *(_DWORD *)(a1 + 248);
  v16 = (unsigned int)a2[6];
  if ( (_DWORD)v16 == -1 )
  {
    *(_DWORD *)Data = 0;
    hKey = 0;
    cbData = 0;
    Type = 0;
    *(_DWORD *)v44 = 0;
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony\\Providers",
           0,
           0xF003Fu,
           &hKey) )
    {
      LastError = GetLastError();
      TRACELogPrint(65538, "RegOpenKeyEx(/Providers) failed, err=%u", LastError);
      DereferenceObject(v18, v12[22], 1);
LABEL_7:
      v10 = -2147483576;
      goto LABEL_43;
    }
    cbData = 4;
    *(_DWORD *)Data = 0;
    RegQueryValueExW(hKey, L"NumProviders", 0, &Type, Data, &cbData);
    v19 = 0;
    if ( *(int *)Data > 0 )
    {
      while ( 1 )
      {
        LODWORD(phkResult) = v19;
        StringCbPrintfW(pszDest, 0x40u, L"%s%d", L"ProviderID", phkResult);
        cbData = 4;
        *(_DWORD *)v44 = 0;
        RegQueryValueExW(hKey, pszDest, 0, &Type, v44, &cbData);
        if ( *(_DWORD *)v44 == a2[2] )
          break;
        if ( ++v19 >= *(int *)Data )
          goto LABEL_26;
      }
      LODWORD(phkResult) = v19;
      StringCbPrintfW(pszDest, 0x40u, L"%s%d", L"ProviderFilename", phkResult);
      cbData = 520;
      RegQueryValueExW(hKey, pszDest, 0, &Type, (LPBYTE)v55, &cbData);
      LibraryW = LoadLibraryW(v55);
      *((_QWORD *)v12 + 3) = LibraryW;
      if ( !LibraryW )
      {
        v21 = GetLastError();
        TRACELogPrint(65538, "LoadLibrary('%ls') failed - err=%u", v55, v21);
LABEL_21:
        v10 = -2147483576;
LABEL_38:
        v25 = (HMODULE)*((_QWORD *)v12 + 3);
        if ( v25 )
          FreeLibrary(v25);
        v26 = (void *)*((_QWORD *)v12 + 7);
        if ( v26 )
          ServerFree(v26);
        DereferenceObject(v26, v12[22], 1);
        goto LABEL_43;
      }
      ProcAddress = GetProcAddress(LibraryW, "TSPI_providerUIIdentify");
      if ( !ProcAddress )
      {
        v22 = GetLastError();
        TRACELogPrint(65538, "GetProcAddress(TSPI_providerUIIdentify) on [%ls] failed, err=%u", v55, v22);
        goto LABEL_24;
      }
      *((_QWORD *)v12 + 4) = GetProcAddress(*((HMODULE *)v12 + 3), "TSPI_providerGenericDialogData");
      v12[5] = a2[2];
      v12[16] = a2[7];
    }
LABEL_26:
    RegCloseKey(hKey);
    if ( v19 == *(_DWORD *)Data )
    {
      TRACELogPrint(65538, "Ran out of list...");
      v10 = -2147483598;
    }
LABEL_28:
    v6 = v51;
    goto LABEL_29;
  }
  v50 = 0;
  lpcbData = 0;
  v52 = 0;
  *(_DWORD *)v48 = 0;
  if ( !(unsigned int)IsBadStringParam(v49, v6, v16) )
  {
    v28 = (const WCHAR *)((char *)v6 + (unsigned int)a2[6]);
    v29 = LoadLibraryW(v28);
    *((_QWORD *)v12 + 3) = v29;
    if ( !v29 )
    {
      v30 = GetLastError();
      TRACELogPrint(65538, "LoadLibrary('%ls') failed   err=%u", v28, v30);
      goto LABEL_21;
    }
    ProcAddress = GetProcAddress(v29, "TSPI_providerUIIdentify");
    if ( !ProcAddress )
    {
LABEL_24:
      v10 = -2147483575;
      goto LABEL_38;
    }
    hKey = (HKEY)(unsigned int)(2 * lstrlenW(v28) + 2);
    v31 = HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)hKey);
    *((_QWORD *)v12 + 7) = v31;
    if ( !v31 )
    {
      v10 = -2147483580;
      goto LABEL_38;
    }
    memcpy_0(v31, v28, (size_t)hKey);
    *((_QWORD *)v12 + 4) = GetProcAddress(*((HMODULE *)v12 + 3), "TSPI_providerGenericDialogData");
    RegOpenKeyExW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony\\Providers",
      0,
      0xF003Fu,
      &v50);
    v32 = v50;
    lpcbData = 4;
    v12[5] = 1;
    RegQueryValueExW(v32, L"NextProviderID", 0, &v52, (LPBYTE)v12 + 20, &lpcbData);
    a2[2] = v12[5];
    v33 = 1;
    if ( ((v12[5] + 1) & 0xFFFF0000) == 0 )
      v33 = v12[5] + 1;
    *(_DWORD *)v48 = v33;
    RegSetValueExW(v50, L"NextProviderID", 0, 4u, v48, 4u);
    RegCloseKey(v50);
    goto LABEL_28;
  }
  *a2 = -2147483576;
  DereferenceObject(v27, v12[22], 1);
}

```

## disassembly

```asm
0x18002a8c0  push    rbp
0x18002a8c2  push    rbx
0x18002a8c3  push    rsi
0x18002a8c4  push    rdi
0x18002a8c5  push    r12
0x18002a8c7  push    r13
0x18002a8c9  push    r14
0x18002a8cb  push    r15
0x18002a8cd  lea     rbp, [rsp-3F8h]
0x18002a8d5  sub     rsp, 4F8h
0x18002a8dc  mov     rax, cs:__security_cookie
0x18002a8e3  xor     rax, rsp
0x18002a8e6  mov     [rbp+430h+var_50], rax
0x18002a8ed  mov     rax, [rbp+430h+arg_20]
0x18002a8f4  xor     r13d, r13d
0x18002a8f7  mov     [rsp+530h+var_4B8], rax
0x18002a8fc  mov     rbx, r9
0x18002a8ff  mov     eax, [rdx+8]
0x18002a902  mov     r14, rdx
0x18002a905  mov     r15, rcx
0x18002a908  mov     [rsp+530h+var_4C8], rbx
0x18002a90d  lea     rdx, aEnteringGetuid; "Entering GetUIDllName"
0x18002a914  mov     [rsp+530h+var_4D8], r8d
0x18002a919  mov     ecx, 80002h
0x18002a91e  mov     [rsp+530h+var_4FC], eax
0x18002a922  mov     edi, r13d
0x18002a925  mov     r12d, r13d
0x18002a928  mov     esi, r13d
0x18002a92b  call    TRACELogPrint
0x18002a930  mov     ecx, [r14+0Ch]
0x18002a934  sub     ecx, 1
0x18002a937  jz      loc_18002AF33
0x18002a93d  sub     ecx, 1
0x18002a940  jz      loc_18002AE9B
0x18002a946  cmp     ecx, 1
0x18002a949  jnz     loc_18002ACD8
0x18002a94f  lea     rdx, aLookingForProv; "Looking for provider..."
0x18002a956  mov     ecx, 40002h
0x18002a95b  call    TRACELogPrint
0x18002a960  test    byte ptr [r15+0D8h], 8
0x18002a968  jnz     short loc_18002A981
0x18002a96a  cmp     [r14+1Ch], r13d
0x18002a96e  jnz     short loc_18002A977
0x18002a970  cmp     dword ptr [r14+18h], 0FFFFFFFFh
0x18002a975  jz      short loc_18002A981
0x18002a977  mov     edi, 80000048h
0x18002a97c  jmp     loc_18002ACD8
0x18002a981  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002a988  mov     edx, 8; dwFlags
0x18002a98d  lea     r8d, [rdx+58h]; dwBytes
0x18002a991  call    cs:__imp_HeapAlloc
0x18002a997  mov     rsi, rax
0x18002a99a  test    rax, rax
0x18002a99d  jnz     short loc_18002A9A9
0x18002a99f  mov     edi, 80000044h
0x18002a9a4  jmp     loc_18002ACD8
0x18002a9a9  xor     r8d, r8d
0x18002a9ac  mov     rdx, rsi
0x18002a9af  call    NewObject
0x18002a9b4  xor     ecx, ecx
0x18002a9b6  mov     [rsi+58h], eax
0x18002a9b9  test    eax, eax
0x18002a9bb  jnz     short loc_18002A9C7
0x18002a9bd  mov     rcx, rsi; lpMem
0x18002a9c0  call    ServerFree
0x18002a9c5  jmp     short loc_18002A99F
0x18002a9c7  mov     eax, [r15+0F8h]
0x18002a9ce  mov     [rsi+10h], eax
0x18002a9d1  mov     r8d, [r14+18h]
0x18002a9d5  cmp     r8d, 0FFFFFFFFh
0x18002a9d9  jnz     loc_18002ACFE
0x18002a9df  mov     dword ptr [rsp+530h+Data], ecx
0x18002a9e3  lea     rax, [rsp+530h+hKey]
0x18002a9e8  mov     [rsp+530h+hKey], rcx
0x18002a9ed  lea     rdx, gszRegKeyProviders; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002a9f4  mov     [rsp+530h+cbData], ecx
0x18002a9f8  mov     r9d, 0F003Fh; samDesired
0x18002a9fe  mov     [rsp+530h+Type], ecx
0x18002aa02  xor     r8d, r8d; ulOptions
0x18002aa05  mov     dword ptr [rsp+530h+var_4F4], ecx
0x18002aa09  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002aa10  mov     [rsp+530h+phkResult], rax; phkResult
0x18002aa15  call    cs:__imp_RegOpenKeyExW
0x18002aa1b  test    eax, eax
0x18002aa1d  jz      short loc_18002AA4C
0x18002aa1f  call    cs:__imp_GetLastError
0x18002aa25  lea     rdx, aRegopenkeyexPr; "RegOpenKeyEx(/Providers) failed, err=%u"
0x18002aa2c  mov     ecx, 10002h
0x18002aa31  mov     r8d, eax
0x18002aa34  call    TRACELogPrint
0x18002aa39  mov     edx, [rsi+58h]
0x18002aa3c  mov     r8d, 1
0x18002aa42  call    DereferenceObject
0x18002aa47  jmp     loc_18002A977
0x18002aa4c  mov     rcx, [rsp+530h+hKey]; hKey
0x18002aa51  lea     rax, [rsp+530h+cbData]
0x18002aa56  mov     [rsp+530h+lpcbData], rax; lpcbData
0x18002aa5b  lea     r9, [rsp+530h+Type]; lpType
0x18002aa60  lea     rax, [rsp+530h+Data]
0x18002aa65  mov     [rsp+530h+cbData], 4
0x18002aa6d  xor     r8d, r8d; lpReserved
0x18002aa70  mov     [rsp+530h+phkResult], rax; lpData
0x18002aa75  lea     rdx, gszNumProviders; "NumProviders"
0x18002aa7c  mov     dword ptr [rsp+530h+Data], edi
0x18002aa80  call    cs:__imp_RegQueryValueExW
0x18002aa86  xor     ebx, ebx
0x18002aa88  cmp     dword ptr [rsp+530h+Data], ebx
0x18002aa8c  jle     loc_18002ABF0
0x18002aa92  lea     r9, gszProviderID; "ProviderID"
0x18002aa99  mov     dword ptr [rsp+530h+phkResult], ebx
0x18002aa9d  lea     r8, aSD; "%s%d"
0x18002aaa4  mov     edx, 40h ; '@'; cbDest
0x18002aaa9  lea     rcx, [rbp+430h+pszDest]; pszDest
0x18002aaad  call    StringCbPrintfW
0x18002aab2  mov     rcx, [rsp+530h+hKey]; hKey
0x18002aab7  lea     rax, [rsp+530h+cbData]
0x18002aabc  mov     [rsp+530h+lpcbData], rax; lpcbData
0x18002aac1  lea     r9, [rsp+530h+Type]; lpType
0x18002aac6  lea     rax, [rsp+530h+var_4F4]
0x18002aacb  mov     [rsp+530h+cbData], 4
0x18002aad3  xor     r8d, r8d; lpReserved
0x18002aad6  mov     [rsp+530h+phkResult], rax; lpData
0x18002aadb  lea     rdx, [rbp+430h+pszDest]; lpValueName
0x18002aadf  mov     dword ptr [rsp+530h+var_4F4], edi
0x18002aae3  call    cs:__imp_RegQueryValueExW
0x18002aae9  mov     eax, [r14+8]
0x18002aaed  cmp     dword ptr [rsp+530h+var_4F4], eax
0x18002aaf1  jz      short loc_18002AB00
0x18002aaf3  inc     ebx
0x18002aaf5  cmp     ebx, dword ptr [rsp+530h+Data]
0x18002aaf9  jl      short loc_18002AA92
0x18002aafb  jmp     loc_18002ABF0
0x18002ab00  lea     r9, gszProviderFilename; "ProviderFilename"
0x18002ab07  mov     dword ptr [rsp+530h+phkResult], ebx
0x18002ab0b  lea     r8, aSD; "%s%d"
0x18002ab12  mov     edx, 40h ; '@'; cbDest
0x18002ab17  lea     rcx, [rbp+430h+pszDest]; pszDest
0x18002ab1b  call    StringCbPrintfW
0x18002ab20  mov     rcx, [rsp+530h+hKey]; hKey
0x18002ab25  lea     rax, [rsp+530h+cbData]
0x18002ab2a  mov     [rsp+530h+lpcbData], rax; lpcbData
0x18002ab2f  lea     r9, [rsp+530h+Type]; lpType
0x18002ab34  lea     rax, [rbp+430h+var_470]
0x18002ab38  mov     [rsp+530h+cbData], 208h
0x18002ab40  xor     r8d, r8d; lpReserved
0x18002ab43  mov     [rsp+530h+phkResult], rax; lpData
0x18002ab48  lea     rdx, [rbp+430h+pszDest]; lpValueName
0x18002ab4c  call    cs:__imp_RegQueryValueExW
0x18002ab52  lea     rcx, [rbp+430h+var_470]; lpLibFileName
0x18002ab56  call    cs:__imp_LoadLibraryW
0x18002ab5c  mov     [rsi+18h], rax
0x18002ab60  test    rax, rax
0x18002ab63  jnz     short loc_18002AB8D
0x18002ab65  call    cs:__imp_GetLastError
0x18002ab6b  lea     r8, [rbp+430h+var_470]
0x18002ab6f  lea     rdx, aLoadlibraryLsF; "LoadLibrary('%ls') failed - err=%u"
0x18002ab76  mov     r9d, eax
0x18002ab79  mov     ecx, 10002h
0x18002ab7e  call    TRACELogPrint
0x18002ab83  mov     edi, 80000048h
0x18002ab88  jmp     loc_18002ACAD
0x18002ab8d  mov     rdx, cs:lpProcName; lpProcName
0x18002ab94  mov     rcx, rax; hModule
0x18002ab97  call    cs:__imp_GetProcAddress
0x18002ab9d  mov     r12, rax
0x18002aba0  test    rax, rax
0x18002aba3  jnz     short loc_18002ABCD
0x18002aba5  call    cs:__imp_GetLastError
0x18002abab  lea     r8, [rbp+430h+var_470]
0x18002abaf  mov     ecx, 10002h
0x18002abb4  mov     r9d, eax
0x18002abb7  lea     rdx, aGetprocaddress_0; "GetProcAddress(TSPI_providerUIIdentify)"...
0x18002abbe  call    TRACELogPrint
0x18002abc3  mov     edi, 80000049h
0x18002abc8  jmp     loc_18002ACAD
0x18002abcd  mov     rdx, cs:off_180041B60; lpProcName
0x18002abd4  mov     rcx, [rsi+18h]; hModule
0x18002abd8  call    cs:__imp_GetProcAddress
0x18002abde  mov     [rsi+20h], rax
0x18002abe2  mov     eax, [r14+8]
0x18002abe6  mov     [rsi+14h], eax
0x18002abe9  mov     eax, [r14+1Ch]
0x18002abed  mov     [rsi+40h], eax
0x18002abf0  mov     rcx, [rsp+530h+hKey]; hKey
0x18002abf5  call    cs:__imp_RegCloseKey
0x18002abfb  cmp     ebx, dword ptr [rsp+530h+Data]
0x18002abff  jnz     short loc_18002AC17
0x18002ac01  lea     rdx, aRanOutOfList; "Ran out of list..."
0x18002ac08  mov     ecx, 10002h
0x18002ac0d  call    TRACELogPrint
0x18002ac12  mov     edi, 80000032h
0x18002ac17  mov     rbx, [rsp+530h+var_4C8]
0x18002ac1c  test    r12, r12
0x18002ac1f  jz      loc_18002ACD8
0x18002ac25  test    r13, r13
0x18002ac28  jz      short loc_18002AC70
0x18002ac2a  mov     edi, [rsp+530h+var_4FC]
0x18002ac2e  mov     r8, [r13+18h]
0x18002ac32  lea     rax, String2; "remotesp.tsp"
0x18002ac39  or      r9d, 0FFFFFFFFh; cchCount1
0x18002ac3d  add     r8, 4ACh; lpString1
0x18002ac44  mov     dword ptr [rsp+530h+lpcbData], r9d; cchCount2
0x18002ac49  mov     [rsp+530h+phkResult], rax; lpString2
0x18002ac4e  lea     edx, [r9+2]; dwCmpFlags
0x18002ac52  lea     ecx, [rdx+7Eh]; Locale
0x18002ac55  call    cs:__imp_CompareStringW
0x18002ac5b  cmp     eax, 2
0x18002ac5e  jnz     short loc_18002AC70
0x18002ac60  mov     dword ptr [rbx], 52585951h
0x18002ac66  mov     [rbx+4], edi
0x18002ac69  mov     eax, [r14+0Ch]
0x18002ac6d  mov     [rbx+8], eax
0x18002ac70  lea     rcx, [rbp+430h+String]
0x18002ac77  mov     rax, r12
0x18002ac7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac7f  mov     edi, eax
0x18002ac81  test    eax, eax
0x18002ac83  jnz     short loc_18002ACA8
0x18002ac85  lea     rcx, [rbp+430h+String]; lpString
0x18002ac8c  call    cs:__imp_lstrlenW
0x18002ac92  lea     ebx, ds:2[rax*2]
0x18002ac99  cmp     [rsp+530h+var_4D8], ebx
0x18002ac9d  jnb     loc_18002AFCF
0x18002aca3  mov     edi, 80000048h
0x18002aca8  test    rsi, rsi
0x18002acab  jz      short loc_18002ACD8
0x18002acad  mov     rcx, [rsi+18h]; hLibModule
0x18002acb1  test    rcx, rcx
0x18002acb4  jz      short loc_18002ACBC
0x18002acb6  call    cs:__imp_FreeLibrary
0x18002acbc  mov     rcx, [rsi+38h]; lpMem
0x18002acc0  test    rcx, rcx
0x18002acc3  jz      short loc_18002ACCA
0x18002acc5  call    ServerFree
0x18002acca  mov     edx, [rsi+58h]
0x18002accd  mov     r8d, 1
0x18002acd3  call    DereferenceObject
0x18002acd8  mov     [r14], edi
0x18002acdb  mov     rcx, [rbp+430h+var_50]
0x18002ace2  xor     rcx, rsp; StackCookie
0x18002ace5  call    __security_check_cookie
0x18002acea  add     rsp, 4F8h
0x18002acf1  pop     r15
0x18002acf3  pop     r14
0x18002acf5  pop     r13
0x18002acf7  pop     r12
0x18002acf9  pop     rdi
0x18002acfa  pop     rsi
0x18002acfb  pop     rbx
0x18002acfc  pop     rbp
0x18002acfd  retn
0x18002acfe  mov     [rsp+530h+var_4D0], rcx
0x18002ad03  mov     rdx, rbx
0x18002ad06  mov     [rsp+530h+var_4E0], ecx
0x18002ad0a  mov     [rsp+530h+var_4C0], ecx
0x18002ad0e  mov     dword ptr [rsp+530h+var_4DC], ecx
0x18002ad12  mov     ecx, [rsp+530h+var_4D8]
0x18002ad16  call    IsBadStringParam
0x18002ad1b  test    eax, eax
0x18002ad1d  jz      short loc_18002AD36
0x18002ad1f  mov     dword ptr [r14], 80000048h
0x18002ad26  mov     r8d, 1
0x18002ad2c  mov     edx, [rsi+58h]
0x18002ad2f  call    DereferenceObject
0x18002ad34  jmp     short loc_18002ACDB
0x18002ad36  mov     eax, [r14+18h]
0x18002ad3a  add     rbx, rax
0x18002ad3d  mov     rcx, rbx; lpLibFileName
0x18002ad40  call    cs:__imp_LoadLibraryW
0x18002ad46  mov     [rsi+18h], rax
0x18002ad4a  test    rax, rax
0x18002ad4d  jnz     short loc_18002AD64
0x18002ad4f  call    cs:__imp_GetLastError
0x18002ad55  mov     r8, rbx
0x18002ad58  lea     rdx, aLoadlibraryLsF_0; "LoadLibrary('%ls') failed   err=%u"
0x18002ad5f  jmp     loc_18002AB76
0x18002ad64  mov     rdx, cs:lpProcName; lpProcName
0x18002ad6b  mov     rcx, rax; hModule
0x18002ad6e  call    cs:__imp_GetProcAddress
0x18002ad74  mov     r12, rax
0x18002ad77  test    rax, rax
0x18002ad7a  jz      loc_18002ABC3
0x18002ad80  mov     rcx, rbx; lpString
0x18002ad83  call    cs:__imp_lstrlenW
0x18002ad89  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002ad90  mov     edx, 8; dwFlags
0x18002ad95  lea     eax, ds:2[rax*2]
0x18002ad9c  mov     r8d, eax; dwBytes
0x18002ad9f  mov     [rsp+530h+hKey], rax
0x18002ada4  call    cs:__imp_HeapAlloc
0x18002adaa  mov     [rsi+38h], rax
0x18002adae  test    rax, rax
0x18002adb1  jnz     short loc_18002ADBD
0x18002adb3  mov     edi, 80000044h
0x18002adb8  jmp     loc_18002ACAD
0x18002adbd  mov     r8, [rsp+530h+hKey]; Size
0x18002adc2  mov     rdx, rbx; Src
0x18002adc5  mov     rcx, rax; void *
0x18002adc8  call    memcpy_0
0x18002adcd  mov     rdx, cs:off_180041B60; lpProcName
  ... truncated ...
```
