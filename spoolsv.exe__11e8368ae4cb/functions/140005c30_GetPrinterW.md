# GetPrinterW

- ea: `0x140005c30`
- end: `0x1400065e7`
- name: `GetPrinterW`
- size: `2487`
- prototype: `BOOL __stdcall(HANDLE hPrinter, DWORD Level, LPBYTE pPrinter, DWORD cbBuf, LPDWORD pcbNeeded)`
- caller_count: `5`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140004220`
- `0x1400043c0`
- `0x140060028`
- `0x1400782e0`
- `0x140078fd0`

## callees

- `0x140002070`
- `0x140002b00`
- `0x140003c70`
- `0x1400040d8`
- `0x1400041c0`
- `0x140004220`
- `0x140005c30`
- `0x1400065f0`
- `0x14000cd50`
- `0x14000d640`
- `0x1400140cc`
- `0x140014fc4`
- `0x140015000`
- `0x1400166e8`
- `0x140017710`
- `0x1400235dc`
- `0x140023860`
- `0x14006ba60`
- `0x14006bbc8`
- `0x140079338`
- `0x14007a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400061c4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400061c4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140005eb4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140005eb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000612d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400062ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006329`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000653e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006551`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006563`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000612d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400062ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006329`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000653e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006551`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006563`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005cbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006029`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000609c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000622d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400062a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400062f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000639e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005cbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006029`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000609c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000622d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400062a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400062f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000639e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005c91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005d10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005d91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005de2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005e63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005eed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006023`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000614d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006227`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000656b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400065da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005c91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005d10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005d91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005de2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005e63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005eed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006023`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000614d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006227`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000656b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400065da`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14000618d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14000618d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140005ec9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x140005ec9`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000619c`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000619c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400061a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400061a6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140006111`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140006111`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140006073`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140006073`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140005fff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140005fff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400060c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400060c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006014`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006141`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006014`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006141`

## string_xrefs

- `0x1400061b9`: `win32spl.dll`

## pseudocode

```c
BOOL __stdcall GetPrinterW(HANDLE hPrinter, DWORD Level, LPBYTE pPrinter, DWORD cbBuf, LPDWORD pcbNeeded)
{
  DWORD v5; // r13d
  HKEY v9; // rsi
  struct _devicemodeW *v10; // r14
  char LastError; // al
  int v13; // ecx
  DWORD v14; // ecx
  char v15; // al
  int v16; // ecx
  int v17; // r9d
  HKEY v18; // rcx
  int DevModePerUserEvenForShares; // eax
  HKEY v20; // rdx
  int v21; // r8d
  __int64 v22; // rax
  struct _PRINTER_INFO_2W *PrinterInfo2; // rax
  HKEY pDevMode; // rdx
  int v25; // r8d
  unsigned __int16 *v26; // rdi
  const unsigned __int16 *v27; // rdx
  ProcessUtils *v28; // rcx
  int *v29; // r8
  int v30; // eax
  HKEY ClientUserHandle; // rax
  DWORD v32; // eax
  DWORD InfoKeyW; // edi
  unsigned int IsValidDevmodeNo; // r8d
  HANDLE v35; // rdi
  __int64 v36; // rax
  _BYTE *v37; // rdi
  DWORD v38; // eax
  DWORD v39; // eax
  DWORD v40; // eax
  DWORD v41; // r9d
  DWORD v42; // eax
  struct _devicemodeW *v43; // r10
  DWORD v44; // edi
  struct _devicemodeW *v45; // r8
  __int64 v46; // r9
  unsigned int v47; // eax
  BYTE *v48; // rcx
  struct _devicemodeW *v49; // r8
  unsigned __int64 v50; // rcx
  int v51; // ecx
  int v52; // esi
  DWORD dwOptions[2]; // [rsp+20h] [rbp-71h]
  void *dwDisposition; // [rsp+60h] [rbp-31h] BYREF
  HKEY Size_4; // [rsp+68h] [rbp-29h]
  int v56; // [rsp+70h] [rbp-21h]
  void *v57; // [rsp+78h] [rbp-19h]
  HKEY phkResult; // [rsp+80h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-9h] BYREF
  int v60; // [rsp+90h] [rbp-1h]
  struct _devicemodeW *v61; // [rsp+98h] [rbp+7h] BYREF
  LPCWSTR lpValueName; // [rsp+A0h] [rbp+Fh]
  LPVOID lpMem; // [rsp+A8h] [rbp+17h]
  HANDLE Token; // [rsp+B0h] [rbp+1Fh] BYREF
  char v65; // [rsp+B8h] [rbp+27h]
  int v66; // [rsp+F0h] [rbp+5Fh]

  v5 = cbBuf;
  hKey = 0;
  v61 = 0;
  HIDWORD(dwDisposition) = 0;
  v9 = 0;
  v10 = 0;
  if ( !hPrinter || *(_DWORD *)hPrinter != 24672 )
  {
    SetLastError(6u);
    return 0;
  }
  if ( !pPrinter && cbBuf )
  {
    SetLastError(0x6F8u);
    return 0;
  }
  Size_4 = 0;
  v57 = 0;
  lpMem = 0;
  v66 = 0;
  v60 = 0;
  v56 = 0;
  if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
  {
    LastError = GetLastError();
    McTemplateU0zqd_EtwEventWriteTransfer(
      v13,
      (unsigned int)DocPerf_GetPrinter_Start,
      *((_QWORD *)hPrinter + 9),
      Level,
      LastError);
  }
  if ( Level == 2 )
  {
    if ( !*((_QWORD *)hPrinter + 9)
      || (unsigned int)CheckLocalCall()
      || wcsstr(*((const wchar_t **)hPrinter + 9), L",DrvConvert")
      || TlsGetValue(gdwTlsGetPrinterIndex) == (LPVOID)2 )
    {
      goto LABEL_106;
    }
    v26 = (unsigned __int16 *)*((_QWORD *)hPrinter + 9);
    phkResult = 0;
    if ( !v26 )
    {
      SetLastError(6u);
      goto LABEL_106;
    }
    Token = (HANDLE)-1LL;
    v65 = 0;
    LODWORD(dwDisposition) = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl)
      && ProcessUtils::IsCurrentProcess(v28, v27) )
    {
      v30 = (int)NSecurityLibrary::ElevateIntegrityLevelIfLowViaBroker((NSecurityLibrary *)&Token, &dwDisposition, v29) >= 0;
    }
    else
    {
      v30 = NSecurityLibrary::ElevateIntegrityLevelIfLowDirectly((NSecurityLibrary *)&Token, &dwDisposition, v29);
    }
    if ( v30 && (_DWORD)dwDisposition )
      v65 = 1;
    phkResult = 0;
    lpValueName = 0;
    ClientUserHandle = (HKEY)SplGetClientUserHandle(131103);
    hKey = ClientUserHandle;
    if ( !ClientUserHandle )
    {
      if ( GetLastError() != 5
        || (ClientUserHandle = (HKEY)SplGetClientUserHandle(131097), (hKey = ClientUserHandle) == 0) )
      {
        v32 = GetLastError();
        goto LABEL_63;
      }
    }
    if ( *v26 == 92 && v26[1] == 92 )
    {
      LODWORD(dwDisposition) = RegOpenConnectionKey(ClientUserHandle, v26, &phkResult);
      if ( !(_DWORD)dwDisposition )
      {
        lpValueName = L"DevMode";
LABEL_62:
        RegCloseKey(hKey);
        v32 = (unsigned int)dwDisposition;
LABEL_63:
        if ( v32 )
        {
          SetLastError(v32);
          InfoKeyW = GetLastError();
          goto LABEL_80;
        }
        LODWORD(dwDisposition) = 0;
        InfoKeyW = RegQueryInfoKeyW(phkResult, 0, 0, 0, 0, 0, 0, 0, 0, (LPDWORD)&dwDisposition, 0, 0);
        if ( InfoKeyW || (unsigned int)dwDisposition < 0x48 )
        {
LABEL_79:
          RegCloseKey(phkResult);
LABEL_80:
          if ( InfoKeyW )
          {
            SetLastError(InfoKeyW);
            if ( InfoKeyW != 5 )
              PrvSpoolssTelemetry::WriteDbgTraceError(
                "bGetDevModePerUser",
                L"Failed to get devmode. Error %d.",
                InfoKeyW);
            NSecurityLibrary::Low2MediumIntegrity::~Low2MediumIntegrity((NSecurityLibrary::Low2MediumIntegrity *)&Token);
          }
          else
          {
            v35 = Token;
            if ( Token != (HANDLE)-1LL )
            {
              if ( Token && !SetThreadToken(0, Token) )
                ExitProcess(1u);
              CloseHandle(v35);
            }
          }
          if ( v9 )
          {
            if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)(*((_QWORD *)hPrinter + 1) + 8LL), L"win32spl.dll") )
            {
              v36 = *((_QWORD *)hPrinter + 1);
              LODWORD(dwDisposition) = 0;
              if ( (*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, void **))(v36 + 88))(
                     *((_QWORD *)hPrinter + 2),
                     4,
                     0,
                     0,
                     &dwDisposition) )
              {
                v37 = 0;
              }
              else
              {
                if ( GetLastError() != 122 )
                {
                  v40 = GetLastError();
                  PrvSpoolssTelemetry::WriteDbgTraceError(
                    "GetPrinterW",
                    L"1st GetPrinter level %u from print providor failed. Error %d",
                    4,
                    v40);
                  return 0;
                }
                v37 = (_BYTE *)DllAllocSplMem((unsigned int)dwDisposition);
                if ( !v37 )
                {
                  SetLastError(0xEu);
                  v38 = GetLastError();
                  PrvSpoolssTelemetry::WriteDbgTraceError(
                    "GetPrinterW",
                    L"Allocating memory for GetPrinter level %u failed. Error %d",
                    4,
                    v38);
                  return 0;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64, _BYTE *, _QWORD, void **))(*((_QWORD *)hPrinter
                                                                                                  + 1)
                                                                                                + 88LL))(
                        *((_QWORD *)hPrinter + 2),
                        4,
                        v37,
                        (unsigned int)dwDisposition,
                        &dwDisposition) )
                {
                  v39 = GetLastError();
                  PrvSpoolssTelemetry::WriteDbgTraceError(
                    "GetPrinterW",
                    L"2nd GetPrinter level %u from print providor failed. Error %d",
                    4,
                    v39);
                  HeapFree(g_hSpoolssHeap, 0, v37);
                  return 0;
                }
                if ( (v37[16] & 0x50) != 0x50 )
                {
                  GetCachedDefaultDevModeAndSize(hPrinter, &v61, (unsigned int *)&dwDisposition + 1);
                  v10 = v61;
                }
              }
              v56 = 1;
              HeapFree(g_hSpoolssHeap, 0, v37);
            }
            Size_4 = v9;
            if ( !v10 )
              HIDWORD(dwDisposition) = (*((unsigned __int16 *)v9 + 35) + *((unsigned __int16 *)v9 + 34) + 3)
                                     & 0xFFFFFFFC;
            v60 = 3;
            v5 &= 0xFFFFFFFC;
          }
          goto LABEL_106;
        }
        v9 = (HKEY)DllAllocSplMem((unsigned int)dwDisposition);
        if ( !v9 )
        {
          InfoKeyW = GetLastError();
          goto LABEL_79;
        }
        InfoKeyW = RegQueryValueExW(phkResult, lpValueName, 0, 0, (LPBYTE)v9, (LPDWORD)&dwDisposition);
        if ( !InfoKeyW )
        {
          IsValidDevmodeNo = -2147024883;
          if ( (unsigned int)dwDisposition >= 0x4CuLL
            && (unsigned int)dwDisposition >= *((unsigned __int16 *)v9 + 34)
                                            + (unsigned __int64)*((unsigned __int16 *)v9 + 35) )
          {
            IsValidDevmodeNo = SplIsValidDevmodeNoSize<_devicemodeW,unsigned short>(
                                 v9,
                                 (unsigned int)dwDisposition,
                                 2147942413LL);
          }
          InfoKeyW = StatusFromHResult(IsValidDevmodeNo);
          if ( !InfoKeyW )
            goto LABEL_77;
          if ( !RegDeleteValueW(phkResult, lpValueName) )
            InfoKeyW = 2;
        }
        HeapFree(g_hSpoolssHeap, 0, v9);
        v9 = 0;
LABEL_77:
        if ( InfoKeyW == 2 )
          InfoKeyW = 0;
        goto LABEL_79;
      }
      ClientUserHandle = hKey;
    }
    LODWORD(dwDisposition) = 0;
    LODWORD(dwDisposition) = RegCreateKeyExW(
                               ClientUserHandle,
                               L"Printers\\DevModePerUser",
                               0,
                               0,
                               0,
                               0x2001Fu,
                               0,
                               &phkResult,
                               (LPDWORD)&dwDisposition);
    if ( !(_DWORD)dwDisposition )
      lpValueName = v26;
    goto LABEL_62;
  }
  LODWORD(dwDisposition) = 0;
  if ( Level != 8 )
  {
    if ( Level == 9 )
    {
      if ( !*((_QWORD *)hPrinter + 9) )
      {
        v14 = 6;
        goto LABEL_13;
      }
      if ( (unsigned int)CheckLocalCall() )
      {
        v14 = 50;
LABEL_13:
        SetLastError(v14);
        if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
        {
          v15 = GetLastError();
          v17 = 9;
LABEL_29:
          McTemplateU0zqd_EtwEventWriteTransfer(
            v16,
            (unsigned int)DocPerf_GetPrinter_Stop,
            *((_QWORD *)hPrinter + 9),
            v17,
            v15);
          return 0;
        }
        return 0;
      }
      *pcbNeeded = 8;
      DevModePerUserEvenForShares = bGetDevModePerUserEvenForShares(
                                      v18,
                                      *((const unsigned __int16 **)hPrinter + 9),
                                      (struct _devicemodeW **)&hKey);
      v9 = hKey;
      if ( DevModePerUserEvenForShares )
      {
        v20 = hKey;
        Size_4 = hKey;
        if ( hKey )
        {
          v21 = *((unsigned __int16 *)hKey + 34) + *((unsigned __int16 *)hKey + 35);
          *pcbNeeded += v21;
          v66 = v21;
        }
      }
      else
      {
        v20 = 0;
      }
      if ( v5 < *pcbNeeded )
      {
        SetLastError(0x7Au);
        goto LABEL_110;
      }
      if ( !v20 )
      {
        LODWORD(dwDisposition) = 1;
        *(_QWORD *)pPrinter = 0;
        goto LABEL_110;
      }
      v57 = pPrinter + 8;
      *(_QWORD *)pPrinter = pPrinter + 8;
      lpMem = pGetPrinterInfo2(hPrinter);
      v22 = lpMem != 0;
LABEL_109:
      LODWORD(dwDisposition) = v22;
      goto LABEL_110;
    }
LABEL_106:
    v41 = 0;
    if ( v5 >= HIDWORD(dwDisposition) )
      v41 = v5 - HIDWORD(dwDisposition);
    LODWORD(v22) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPBYTE, _QWORD, LPDWORD))(*((_QWORD *)hPrinter + 1) + 88LL))(
                     *((_QWORD *)hPrinter + 2),
                     Level,
                     pPrinter,
                     v41 & 0xFFFFFFF8,
                     pcbNeeded);
    *pcbNeeded = HIDWORD(dwDisposition) + v60 + ((*pcbNeeded + 7) & 0xFFFFFFF8);
    goto LABEL_109;
  }
  if ( !*((_QWORD *)hPrinter + 9) )
  {
    SetLastError(2u);
    if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
    {
      v15 = GetLastError();
      v17 = 8;
      goto LABEL_29;
    }
    return 0;
  }
  *pcbNeeded = 8;
  PrinterInfo2 = pGetPrinterInfo2(hPrinter);
  lpMem = PrinterInfo2;
  if ( PrinterInfo2 )
  {
    pDevMode = (HKEY)PrinterInfo2->pDevMode;
    Size_4 = pDevMode;
    if ( pDevMode )
    {
      v25 = *((unsigned __int16 *)pDevMode + 34) + *((unsigned __int16 *)pDevMode + 35);
      *pcbNeeded += v25;
      v66 = v25;
    }
    if ( v5 >= *pcbNeeded )
    {
      LODWORD(dwDisposition) = 1;
      if ( pDevMode )
      {
        v57 = pPrinter + 8;
        *(_QWORD *)pPrinter = pPrinter + 8;
      }
      else
      {
        *(_QWORD *)pPrinter = 0;
      }
    }
    else
    {
      SetLastError(0x7Au);
    }
  }
LABEL_110:
  v42 = GetLastError();
  v43 = (struct _devicemodeW *)Size_4;
  v44 = v42;
  if ( v42 != 122 && Level == 9 && !Size_4 && pPrinter )
  {
    if ( *(_QWORD *)pPrinter )
      v43 = *(struct _devicemodeW **)pPrinter;
    Size_4 = (HKEY)v43;
  }
  if ( !HIDWORD(dwDisposition) || !pPrinter || !(_DWORD)dwDisposition )
    goto LABEL_141;
  v61 = v10;
  v45 = v10;
  if ( v10 )
  {
    v46 = HIDWORD(dwDisposition);
  }
  else
  {
    v45 = (struct _devicemodeW *)*((_QWORD *)pPrinter + 7);
    v61 = v45;
    if ( !v45 )
    {
LABEL_131:
      v47 = HIDWORD(dwDisposition);
      v48 = &pPrinter[v5 - (unsigned __int64)HIDWORD(dwDisposition)];
      *((_QWORD *)pPrinter + 7) = v48;
      goto LABEL_142;
    }
    v46 = (v45->dmDriverExtra + v45->dmSize + 3) & 0xFFFFFFFC;
  }
  if ( v43
    && v45->dmSize == v43->dmSize
    && v45->dmDriverExtra == v43->dmDriverExtra
    && v45->dmSpecVersion == v43->dmSpecVersion
    && v45->dmDriverVersion == v43->dmDriverVersion )
  {
    if ( v45->dmReserved1 == 877873479 || v43->dmReserved1 != 877873479 )
      goto LABEL_131;
LABEL_133:
    if ( v45->dmReserved1 != 877873479 )
      goto LABEL_150;
    goto LABEL_134;
  }
  if ( v43->dmReserved1 == 877873479 )
    goto LABEL_133;
LABEL_134:
  if ( (v56 || *((struct _PROVIDOR **)hPrinter + 1) == pLocalProvidor && (pPrinter[104] & 0x50) != 0x50)
    && (unsigned int)ConvertDevMode(hPrinter, v43, v45, v46) )
  {
    v49 = v61;
    v57 = 0;
    if ( v61 == v10 )
    {
      v50 = v5 - (unsigned __int64)HIDWORD(dwDisposition);
      v66 = HIDWORD(dwDisposition);
      Size_4 = (HKEY)v10;
      v57 = &pPrinter[v50];
      *((_QWORD *)pPrinter + 7) = &pPrinter[v50];
    }
    bSetDevModePerUser(0, *((_QWORD *)hPrinter + 9), v49, v46);
    v43 = (struct _devicemodeW *)Size_4;
LABEL_141:
    v47 = v66;
    v48 = (BYTE *)v57;
LABEL_142:
    if ( v48 )
    {
      memcpy_0(v48, v43, v47);
      LODWORD(dwDisposition) = 1;
    }
    goto LABEL_144;
  }
LABEL_150:
  bSetDevModePerUser(0, *((_QWORD *)hPrinter + 9), 0, v46);
LABEL_144:
  HeapFree(g_hSpoolssHeap, 0, v9);
  HeapFree(g_hSpoolssHeap, 0, lpMem);
  HeapFree(g_hSpoolssHeap, 0, v10);
  SetLastError(v44);
  v52 = (int)dwDisposition;
  if ( !(_DWORD)dwDisposition && v44 != 122 )
  {
    dwOptions[0] = v44;
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "GetPrinterW",
      L"Failed to get printer %ws level %u. Error %d",
      *((_QWORD *)hPrinter + 9),
      Level,
      *(_QWORD *)dwOptions);
  }
  if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
    McTemplateU0zqd_EtwEventWriteTransfer(
      v51,
      (unsigned int)DocPerf_GetPrinter_Stop,
      *((_QWORD *)hPrinter + 9),
      Level,
      v44);
  return v52;
}

```

## disassembly

```asm
0x140005c30  mov     [rsp-8+arg_10], rbx
0x140005c35  mov     [rsp-8+arg_18], rsi
0x140005c3a  push    rbp
0x140005c3b  push    r12
0x140005c3d  push    r13
0x140005c3f  push    r14
0x140005c41  push    r15
0x140005c43  lea     rbp, [rsp-2Fh]
0x140005c48  sub     rsp, 0C0h
0x140005c4f  xor     eax, eax
0x140005c51  mov     r13d, r9d
0x140005c54  mov     [rbp+4Fh+hKey], rax
0x140005c58  mov     r15, r8
0x140005c5b  mov     [rbp+4Fh+var_48], rax
0x140005c5f  mov     r12d, edx
0x140005c62  mov     dword ptr [rbp+4Fh+Size], eax
0x140005c65  mov     rbx, rcx
0x140005c68  mov     esi, eax
0x140005c6a  mov     r14d, eax
0x140005c6d  test    rcx, rcx
0x140005c70  jz      loc_1400065D5
0x140005c76  cmp     dword ptr [rcx], 6060h
0x140005c7c  jnz     loc_1400065D5
0x140005c82  test    r8, r8
0x140005c85  jnz     short loc_140005C9E
0x140005c87  test    r9d, r9d
0x140005c8a  jz      short loc_140005C9E
0x140005c8c  mov     ecx, 6F8h; dwErrCode
0x140005c91  call    cs:__imp_SetLastError
0x140005c97  xor     eax, eax
0x140005c99  jmp     loc_140006259
0x140005c9e  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x140005ca5  mov     qword ptr [rbp+4Fh+Size+4], rax
0x140005ca9  mov     [rbp+4Fh+var_68], rax
0x140005cad  mov     [rbp+4Fh+lpMem], rax
0x140005cb1  mov     [rbp+4Fh+arg_0], eax
0x140005cb4  mov     [rbp+4Fh+var_50], eax
0x140005cb7  mov     [rbp+4Fh+var_70], eax
0x140005cba  jz      short loc_140005CDB
0x140005cbc  call    cs:__imp_GetLastError
0x140005cc2  mov     r8, [rbx+48h]
0x140005cc6  lea     rdx, DocPerf_GetPrinter_Start
0x140005ccd  mov     r9d, r12d
0x140005cd0  mov     [rsp+0E0h+dwOptions], eax
0x140005cd4  call    McTemplateU0zqd_EtwEventWriteTransfer
0x140005cd9  xor     eax, eax
0x140005cdb  mov     [rsp+0E0h+arg_8], rdi
0x140005ce3  cmp     r12d, 2
0x140005ce7  jz      loc_140005E92
0x140005ced  mov     [rbp+4Fh+dwDisposition], eax
0x140005cf0  mov     eax, r12d
0x140005cf3  sub     eax, 8
0x140005cf6  jz      loc_140005DD7
0x140005cfc  cmp     eax, 1
0x140005cff  jnz     loc_140006356
0x140005d05  cmp     [rbx+48h], rsi
0x140005d09  jnz     short loc_140005D34
0x140005d0b  mov     ecx, 6; dwErrCode
0x140005d10  call    cs:__imp_SetLastError
0x140005d16  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x140005d1d  jz      loc_14000624F
0x140005d23  call    cs:__imp_GetLastError
0x140005d29  mov     r9d, 9
0x140005d2f  jmp     loc_140005E01
0x140005d34  call    CheckLocalCall
0x140005d39  test    eax, eax
0x140005d3b  jz      short loc_140005D44
0x140005d3d  mov     ecx, 32h ; '2'
0x140005d42  jmp     short loc_140005D10
0x140005d44  mov     rdi, [rbp+4Fh+pcbNeeded]
0x140005d48  lea     r8, [rbp+4Fh+hKey]; struct _devicemodeW **
0x140005d4c  mov     dword ptr [rdi], 8
0x140005d52  mov     rdx, [rbx+48h]; unsigned __int16 *
0x140005d56  call    ?bGetDevModePerUserEvenForShares@@YAHPEAUHKEY__@@PEBGPEAPEAU_devicemodeW@@@Z; bGetDevModePerUserEvenForShares(HKEY__ *,ushort const *,_devicemodeW * *)
0x140005d5b  mov     rsi, [rbp+4Fh+hKey]
0x140005d5f  test    eax, eax
0x140005d61  jz      short loc_140005D84
0x140005d63  mov     rdx, rsi
0x140005d66  mov     qword ptr [rbp+4Fh+Size+4], rdx
0x140005d6a  test    rsi, rsi
0x140005d6d  jz      short loc_140005D87
0x140005d6f  movzx   r8d, word ptr [rsi+46h]
0x140005d74  movzx   eax, word ptr [rsi+44h]
0x140005d78  add     r8d, eax
0x140005d7b  add     [rdi], r8d
0x140005d7e  mov     [rbp+4Fh+arg_0], r8d
0x140005d82  jmp     short loc_140005D87
0x140005d84  mov     rdx, r14
0x140005d87  cmp     r13d, [rdi]
0x140005d8a  jnb     short loc_140005D9C
0x140005d8c  mov     ecx, 7Ah ; 'z'; dwErrCode
0x140005d91  call    cs:__imp_SetLastError
0x140005d97  jmp     loc_14000639E
0x140005d9c  test    rdx, rdx
0x140005d9f  jz      short loc_140005DC8
0x140005da1  lea     rax, [r15+8]
0x140005da5  mov     rcx, rbx; void *
0x140005da8  mov     [rbp+4Fh+var_68], rax
0x140005dac  mov     [r15], rax
0x140005daf  call    ?pGetPrinterInfo2@@YAPEAU_PRINTER_INFO_2W@@PEAX@Z; pGetPrinterInfo2(void *)
0x140005db4  mov     rcx, rax
0x140005db7  mov     [rbp+4Fh+lpMem], rax
0x140005dbb  xor     eax, eax
0x140005dbd  test    rcx, rcx
0x140005dc0  setnz   al
0x140005dc3  jmp     loc_14000639B
0x140005dc8  mov     [rbp+4Fh+dwDisposition], 1
0x140005dcf  mov     [r15], r14
0x140005dd2  jmp     loc_14000639E
0x140005dd7  cmp     [rbx+48h], rsi
0x140005ddb  jnz     short loc_140005E1A
0x140005ddd  mov     ecx, 2; dwErrCode
0x140005de2  call    cs:__imp_SetLastError
0x140005de8  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x140005def  jz      loc_14000624F
0x140005df5  call    cs:__imp_GetLastError
0x140005dfb  mov     r9d, 8
0x140005e01  mov     r8, [rbx+48h]
0x140005e05  lea     rdx, DocPerf_GetPrinter_Stop
0x140005e0c  mov     [rsp+0E0h+dwOptions], eax
0x140005e10  call    McTemplateU0zqd_EtwEventWriteTransfer
0x140005e15  jmp     loc_14000624F
0x140005e1a  mov     rdi, [rbp+4Fh+pcbNeeded]
0x140005e1e  mov     rcx, rbx; void *
0x140005e21  mov     dword ptr [rdi], 8
0x140005e27  call    ?pGetPrinterInfo2@@YAPEAU_PRINTER_INFO_2W@@PEAX@Z; pGetPrinterInfo2(void *)
0x140005e2c  mov     [rbp+4Fh+lpMem], rax
0x140005e30  test    rax, rax
0x140005e33  jz      loc_14000639E
0x140005e39  mov     rdx, [rax+38h]
0x140005e3d  mov     qword ptr [rbp+4Fh+Size+4], rdx
0x140005e41  test    rdx, rdx
0x140005e44  jz      short loc_140005E59
0x140005e46  movzx   r8d, word ptr [rdx+46h]
0x140005e4b  movzx   eax, word ptr [rdx+44h]
0x140005e4f  add     r8d, eax
0x140005e52  add     [rdi], r8d
0x140005e55  mov     [rbp+4Fh+arg_0], r8d
0x140005e59  cmp     r13d, [rdi]
0x140005e5c  jnb     short loc_140005E6E
0x140005e5e  mov     ecx, 7Ah ; 'z'; dwErrCode
0x140005e63  call    cs:__imp_SetLastError
0x140005e69  jmp     loc_14000639E
0x140005e6e  mov     [rbp+4Fh+dwDisposition], 1
0x140005e75  test    rdx, rdx
0x140005e78  jz      short loc_140005E8A
0x140005e7a  lea     rax, [r15+8]
0x140005e7e  mov     [rbp+4Fh+var_68], rax
0x140005e82  mov     [r15], rax
0x140005e85  jmp     loc_14000639E
0x140005e8a  mov     [r15], rsi
0x140005e8d  jmp     loc_14000639E
0x140005e92  cmp     [rbx+48h], rsi
0x140005e96  jz      loc_140006356
0x140005e9c  call    CheckLocalCall
0x140005ea1  test    eax, eax
0x140005ea3  jnz     loc_140006356
0x140005ea9  mov     rcx, [rbx+48h]; Str
0x140005ead  lea     rdx, gszDrvConvert; ",DrvConvert"
0x140005eb4  call    cs:__imp_wcsstr
0x140005eba  test    rax, rax
0x140005ebd  jnz     loc_140006356
0x140005ec3  mov     ecx, cs:?gdwTlsGetPrinterIndex@@3KA; dwTlsIndex
0x140005ec9  call    cs:__imp_TlsGetValue
0x140005ecf  cmp     rax, 2
0x140005ed3  jz      loc_140006356
0x140005ed9  mov     rdi, [rbx+48h]
0x140005edd  xor     eax, eax
0x140005edf  mov     [rbp+4Fh+var_60], rax
0x140005ee3  test    rdi, rdi
0x140005ee6  jnz     short loc_140005EF8
0x140005ee8  mov     ecx, 6; dwErrCode
0x140005eed  call    cs:__imp_SetLastError
0x140005ef3  jmp     loc_140006356
0x140005ef8  mov     [rbp+4Fh+Token], 0FFFFFFFFFFFFFFFFh
0x140005f00  mov     [rbp+4Fh+var_28], al
0x140005f03  mov     [rbp+4Fh+dwDisposition], eax
0x140005f06  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x140005f0d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140005f12  test    al, al
0x140005f14  jz      short loc_140005F33
0x140005f16  call    ?IsCurrentProcess@ProcessUtils@@YA_NPEBG@Z; ProcessUtils::IsCurrentProcess(ushort const *)
0x140005f1b  lea     rdx, [rbp+4Fh+dwDisposition]; void **
0x140005f1f  lea     rcx, [rbp+4Fh+Token]; this
0x140005f23  test    al, al
0x140005f25  jz      short loc_140005F3B
0x140005f27  call    ?ElevateIntegrityLevelIfLowViaBroker@NSecurityLibrary@@YAJPEAPEAXPEAH@Z; NSecurityLibrary::ElevateIntegrityLevelIfLowViaBroker(void * *,int *)
0x140005f2c  not     eax
0x140005f2e  shr     eax, 1Fh
0x140005f31  jmp     short loc_140005F40
0x140005f33  lea     rdx, [rbp+4Fh+dwDisposition]; void **
0x140005f37  lea     rcx, [rbp+4Fh+Token]; this
0x140005f3b  call    ?ElevateIntegrityLevelIfLowDirectly@NSecurityLibrary@@YAHPEAPEAXPEAH@Z; NSecurityLibrary::ElevateIntegrityLevelIfLowDirectly(void * *,int *)
0x140005f40  test    eax, eax
0x140005f42  jz      short loc_140005F4D
0x140005f44  cmp     [rbp+4Fh+dwDisposition], esi
0x140005f47  jz      short loc_140005F4D
0x140005f49  mov     [rbp+4Fh+var_28], 1
0x140005f4d  xor     eax, eax
0x140005f4f  mov     ecx, 2001Fh
0x140005f54  mov     [rbp+4Fh+var_60], rax
0x140005f58  mov     [rbp+4Fh+lpValueName], rax
0x140005f5c  call    SplGetClientUserHandle
0x140005f61  mov     [rbp+4Fh+hKey], rax
0x140005f65  test    rax, rax
0x140005f68  jnz     short loc_140005F93
0x140005f6a  call    cs:__imp_GetLastError
0x140005f70  cmp     eax, 5
0x140005f73  jnz     short loc_140005F88
0x140005f75  mov     ecx, 20019h
0x140005f7a  call    SplGetClientUserHandle
0x140005f7f  mov     [rbp+4Fh+hKey], rax
0x140005f83  test    rax, rax
0x140005f86  jnz     short loc_140005F93
0x140005f88  call    cs:__imp_GetLastError
0x140005f8e  jmp     loc_14000601D
0x140005f93  cmp     word ptr [rdi], 5Ch ; '\'
0x140005f97  jnz     short loc_140005FC7
0x140005f99  cmp     word ptr [rdi+2], 5Ch ; '\'
0x140005f9e  jnz     short loc_140005FC7
0x140005fa0  lea     r8, [rbp+4Fh+var_60]; phkResult
0x140005fa4  mov     rdx, rdi; unsigned __int16 *
0x140005fa7  mov     rcx, rax; hKey
0x140005faa  call    ?RegOpenConnectionKey@@YAKPEAUHKEY__@@PEAGPEAPEAU1@@Z; RegOpenConnectionKey(HKEY__ *,ushort *,HKEY__ * *)
0x140005faf  mov     [rbp+4Fh+dwDisposition], eax
0x140005fb2  test    eax, eax
0x140005fb4  jnz     short loc_140005FC3
0x140005fb6  lea     rax, gszDevMode; "DevMode"
0x140005fbd  mov     [rbp+4Fh+lpValueName], rax
0x140005fc1  jmp     short loc_140006010
0x140005fc3  mov     rax, [rbp+4Fh+hKey]
0x140005fc7  xor     edx, edx
0x140005fc9  lea     rcx, [rbp+4Fh+dwDisposition]
0x140005fcd  mov     [rsp+0E0h+lpdwDisposition], rcx; lpdwDisposition
0x140005fd2  xor     r9d, r9d; lpClass
0x140005fd5  lea     rcx, [rbp+4Fh+var_60]
0x140005fd9  mov     [rbp+4Fh+dwDisposition], edx
0x140005fdc  mov     [rsp+0E0h+phkResult], rcx; phkResult
0x140005fe1  xor     r8d, r8d; Reserved
0x140005fe4  mov     [rsp+0E0h+lpSecurityAttributes], rdx; lpSecurityAttributes
0x140005fe9  mov     rcx, rax; hKey
0x140005fec  mov     [rsp+0E0h+samDesired], 2001Fh; samDesired
0x140005ff4  mov     [rsp+0E0h+dwOptions], edx; dwOptions
0x140005ff8  lea     rdx, gszDevModePerUserLocal; "Printers\\DevModePerUser"
0x140005fff  call    cs:__imp_RegCreateKeyExW
0x140006005  mov     [rbp+4Fh+dwDisposition], eax
0x140006008  test    eax, eax
0x14000600a  jnz     short loc_140006010
0x14000600c  mov     [rbp+4Fh+lpValueName], rdi
0x140006010  mov     rcx, [rbp+4Fh+hKey]; hKey
0x140006014  call    cs:__imp_RegCloseKey
0x14000601a  mov     eax, [rbp+4Fh+dwDisposition]
0x14000601d  test    eax, eax
0x14000601f  jz      short loc_140006036
0x140006021  mov     ecx, eax; dwErrCode
0x140006023  call    cs:__imp_SetLastError
0x140006029  call    cs:__imp_GetLastError
0x14000602f  mov     edi, eax
0x140006031  jmp     loc_140006147
0x140006036  xor     ecx, ecx
0x140006038  lea     rax, [rbp+4Fh+dwDisposition]
0x14000603c  mov     [rsp+0E0h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x140006041  xor     r9d, r9d; lpReserved
0x140006044  mov     [rsp+0E0h+lpcbSecurityDescriptor], rcx; lpcbSecurityDescriptor
0x140006049  xor     r8d, r8d; lpcchClass
0x14000604c  mov     [rsp+0E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x140006051  xor     edx, edx; lpClass
0x140006053  mov     [rsp+0E0h+lpdwDisposition], rcx; lpcbMaxValueNameLen
0x140006058  mov     [rsp+0E0h+phkResult], rcx; lpcValues
0x14000605d  mov     [rsp+0E0h+lpSecurityAttributes], rcx; lpcbMaxClassLen
0x140006062  mov     qword ptr [rsp+0E0h+samDesired], rcx; lpcbMaxSubKeyLen
0x140006067  mov     qword ptr [rsp+0E0h+dwOptions], rcx; lpcSubKeys
0x14000606c  mov     [rbp+4Fh+dwDisposition], ecx
0x14000606f  mov     rcx, [rbp+4Fh+var_60]; hKey
0x140006073  call    cs:__imp_RegQueryInfoKeyW
0x140006079  mov     edi, eax
0x14000607b  test    eax, eax
0x14000607d  jnz     loc_14000613D
0x140006083  mov     ecx, [rbp+4Fh+dwDisposition]; dwBytes
0x140006086  cmp     ecx, 48h ; 'H'
0x140006089  jb      loc_14000613D
0x14000608f  call    DllAllocSplMem
0x140006094  mov     rsi, rax
0x140006097  test    rax, rax
0x14000609a  jnz     short loc_1400060A9
0x14000609c  call    cs:__imp_GetLastError
0x1400060a2  mov     edi, eax
0x1400060a4  jmp     loc_14000613D
0x1400060a9  mov     rdx, [rbp+4Fh+lpValueName]; lpValueName
0x1400060ad  lea     rax, [rbp+4Fh+dwDisposition]
0x1400060b1  mov     rcx, [rbp+4Fh+var_60]; hKey
0x1400060b5  xor     r9d, r9d; lpType
0x1400060b8  mov     qword ptr [rsp+0E0h+samDesired], rax; lpcbData
0x1400060bd  xor     r8d, r8d; lpReserved
0x1400060c0  mov     qword ptr [rsp+0E0h+dwOptions], rsi; lpData
0x1400060c5  call    cs:__imp_RegQueryValueExW
0x1400060cb  mov     edi, eax
0x1400060cd  test    eax, eax
0x1400060cf  jnz     short loc_140006121
0x1400060d1  mov     edx, [rbp+4Fh+dwDisposition]
  ... truncated ...
```
