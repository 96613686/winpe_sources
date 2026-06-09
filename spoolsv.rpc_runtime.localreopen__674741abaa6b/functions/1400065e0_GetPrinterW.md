# GetPrinterW

- ea: `0x1400065e0`
- end: `0x14000707c`
- name: `GetPrinterW`
- size: `2716`
- prototype: `BOOL __stdcall(HANDLE hPrinter, DWORD Level, LPBYTE pPrinter, DWORD cbBuf, LPDWORD pcbNeeded)`
- caller_count: `5`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000487c`
- `0x140004a70`
- `0x140065eb4`
- `0x14007f694`
- `0x140080484`

## callees

- `0x140002c80`
- `0x140002f40`
- `0x1400042e4`
- `0x140004790`
- `0x140004800`
- `0x14000487c`
- `0x1400065e0`
- `0x140007090`
- `0x14000de80`
- `0x14000deb0`
- `0x140015378`
- `0x140016314`
- `0x140016350`
- `0x140017b40`
- `0x140018bc0`
- `0x140025504`
- `0x1400257ec`
- `0x140072664`
- `0x1400727d8`
- `0x140080828`
- `0x140081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140006c04`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140006c04`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140006882`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140006882`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006b49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006d2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006d94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006fb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006fce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006fe6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006b49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006d2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006d94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006fb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006fce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006672`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400066e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400067c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000694a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000696e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006a27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006c49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006cf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006e0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006672`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400066e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400067c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000694a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000696e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006a27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006c49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006cf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006e0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006641`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400066cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006759`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400067b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400068c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006a1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006b75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006c73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006ff4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007069`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006641`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400066cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006759`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400067b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400068c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006a1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006b75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006c73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006ff4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140007069`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140006bbb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140006bbb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14000689d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14000689d`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140006bd0`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140006bd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006be0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006be0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140006b27`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140006b27`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140006a77`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140006a77`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400069eb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400069eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140006ad5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140006ad5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006a06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006b63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006a06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006b63`

## string_xrefs

- `0x140006bf9`: `win32spl.dll`

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
      goto LABEL_105;
    }
    v26 = (unsigned __int16 *)*((_QWORD *)hPrinter + 9);
    phkResult = 0;
    if ( !v26 )
    {
      SetLastError(6u);
      goto LABEL_105;
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
        goto LABEL_62;
      }
    }
    if ( *v26 == 92 && v26[1] == 92 )
    {
      LODWORD(dwDisposition) = RegOpenConnectionKey(ClientUserHandle, v26, &phkResult);
      if ( !(_DWORD)dwDisposition )
      {
        lpValueName = L"DevMode";
LABEL_61:
        RegCloseKey(hKey);
        v32 = (unsigned int)dwDisposition;
LABEL_62:
        if ( v32 )
        {
          SetLastError(v32);
          InfoKeyW = GetLastError();
          goto LABEL_79;
        }
        LODWORD(dwDisposition) = 0;
        InfoKeyW = RegQueryInfoKeyW(phkResult, 0, 0, 0, 0, 0, 0, 0, 0, (LPDWORD)&dwDisposition, 0, 0);
        if ( InfoKeyW || (unsigned int)dwDisposition < 0x48 )
        {
LABEL_78:
          RegCloseKey(phkResult);
LABEL_79:
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
          goto LABEL_105;
        }
        v9 = (HKEY)DllAllocSplMem((unsigned int)dwDisposition);
        if ( !v9 )
        {
          InfoKeyW = GetLastError();
          goto LABEL_78;
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
            goto LABEL_76;
          if ( !RegDeleteValueW(phkResult, lpValueName) )
            InfoKeyW = 2;
        }
        HeapFree(g_hSpoolssHeap, 0, v9);
        v9 = 0;
LABEL_76:
        if ( InfoKeyW == 2 )
          InfoKeyW = 0;
        goto LABEL_78;
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
    goto LABEL_61;
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
        goto LABEL_22;
      if ( !v20 )
      {
        LODWORD(dwDisposition) = 1;
        *(_QWORD *)pPrinter = 0;
        goto LABEL_109;
      }
      v57 = pPrinter + 8;
      *(_QWORD *)pPrinter = pPrinter + 8;
      lpMem = pGetPrinterInfo2(hPrinter);
      v22 = lpMem != 0;
LABEL_108:
      LODWORD(dwDisposition) = v22;
      goto LABEL_109;
    }
LABEL_105:
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
    goto LABEL_108;
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
    if ( v5 < *pcbNeeded )
    {
LABEL_22:
      SetLastError(0x7Au);
      goto LABEL_109;
    }
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
LABEL_109:
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
    goto LABEL_140;
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
LABEL_130:
      v47 = HIDWORD(dwDisposition);
      v48 = &pPrinter[v5 - (unsigned __int64)HIDWORD(dwDisposition)];
      *((_QWORD *)pPrinter + 7) = v48;
      goto LABEL_141;
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
      goto LABEL_130;
LABEL_132:
    if ( v45->dmReserved1 != 877873479 )
      goto LABEL_149;
    goto LABEL_133;
  }
  if ( v43->dmReserved1 == 877873479 )
    goto LABEL_132;
LABEL_133:
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
LABEL_140:
    v47 = v66;
    v48 = (BYTE *)v57;
LABEL_141:
    if ( v48 )
    {
      memcpy_0(v48, v43, v47);
      LODWORD(dwDisposition) = 1;
    }
    goto LABEL_143;
  }
LABEL_149:
  bSetDevModePerUser(0, *((_QWORD *)hPrinter + 9), 0, v46);
LABEL_143:
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
0x1400065e0  mov     [rsp-8+arg_10], rbx
0x1400065e5  mov     [rsp-8+arg_18], rsi
0x1400065ea  push    rbp
0x1400065eb  push    r12
0x1400065ed  push    r13
0x1400065ef  push    r14
0x1400065f1  push    r15
0x1400065f3  lea     rbp, [rsp-2Fh]
0x1400065f8  sub     rsp, 0C0h
0x1400065ff  xor     eax, eax
0x140006601  mov     r13d, r9d
0x140006604  mov     [rbp+4Fh+hKey], rax
0x140006608  mov     r15, r8
0x14000660b  mov     [rbp+4Fh+var_48], rax
0x14000660f  mov     r12d, edx
0x140006612  mov     dword ptr [rbp+4Fh+Size], eax
0x140006615  mov     rbx, rcx
0x140006618  mov     esi, eax
0x14000661a  mov     r14d, eax
0x14000661d  test    rcx, rcx
0x140006620  jz      loc_140007064
0x140006626  cmp     dword ptr [rcx], 6060h
0x14000662c  jnz     loc_140007064
0x140006632  test    r8, r8
0x140006635  jnz     short loc_140006654
0x140006637  test    r9d, r9d
0x14000663a  jz      short loc_140006654
0x14000663c  mov     ecx, 6F8h; dwErrCode
0x140006641  call    cs:__imp_SetLastError
0x140006648  nop     dword ptr [rax+rax+00h]
0x14000664d  xor     eax, eax
0x14000664f  jmp     loc_140006CB1
0x140006654  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x14000665b  mov     qword ptr [rbp+4Fh+Size+4], rax
0x14000665f  mov     [rbp+4Fh+var_68], rax
0x140006663  mov     [rbp+4Fh+lpMem], rax
0x140006667  mov     [rbp+4Fh+arg_0], eax
0x14000666a  mov     [rbp+4Fh+var_50], eax
0x14000666d  mov     [rbp+4Fh+var_70], eax
0x140006670  jz      short loc_140006697
0x140006672  call    cs:__imp_GetLastError
0x140006679  nop     dword ptr [rax+rax+00h]
0x14000667e  mov     r8, [rbx+48h]
0x140006682  lea     rdx, DocPerf_GetPrinter_Start
0x140006689  mov     r9d, r12d
0x14000668c  mov     [rsp+0E0h+dwOptions], eax
0x140006690  call    McTemplateU0zqd_EtwEventWriteTransfer
0x140006695  xor     eax, eax
0x140006697  mov     [rsp+0E0h+arg_8], rdi
0x14000669f  cmp     r12d, 2
0x1400066a3  jz      loc_140006860
0x1400066a9  mov     [rbp+4Fh+dwDisposition], eax
0x1400066ac  mov     eax, r12d
0x1400066af  sub     eax, 8
0x1400066b2  jz      loc_1400067A5
0x1400066b8  cmp     eax, 1
0x1400066bb  jnz     loc_140006DC7
0x1400066c1  cmp     [rbx+48h], rsi
0x1400066c5  jnz     short loc_1400066FC
0x1400066c7  mov     ecx, 6; dwErrCode
0x1400066cc  call    cs:__imp_SetLastError
0x1400066d3  nop     dword ptr [rax+rax+00h]
0x1400066d8  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x1400066df  jz      loc_140006CA7
0x1400066e5  call    cs:__imp_GetLastError
0x1400066ec  nop     dword ptr [rax+rax+00h]
0x1400066f1  mov     r9d, 9
0x1400066f7  jmp     loc_1400067DB
0x1400066fc  call    CheckLocalCall
0x140006701  test    eax, eax
0x140006703  jz      short loc_14000670C
0x140006705  mov     ecx, 32h ; '2'
0x14000670a  jmp     short loc_1400066CC
0x14000670c  mov     rdi, [rbp+4Fh+pcbNeeded]
0x140006710  lea     r8, [rbp+4Fh+hKey]; struct _devicemodeW **
0x140006714  mov     dword ptr [rdi], 8
0x14000671a  mov     rdx, [rbx+48h]; unsigned __int16 *
0x14000671e  call    ?bGetDevModePerUserEvenForShares@@YAHPEAUHKEY__@@PEBGPEAPEAU_devicemodeW@@@Z; bGetDevModePerUserEvenForShares(HKEY__ *,ushort const *,_devicemodeW * *)
0x140006723  mov     rsi, [rbp+4Fh+hKey]
0x140006727  test    eax, eax
0x140006729  jz      short loc_14000674C
0x14000672b  mov     rdx, rsi
0x14000672e  mov     qword ptr [rbp+4Fh+Size+4], rdx
0x140006732  test    rsi, rsi
0x140006735  jz      short loc_14000674F
0x140006737  movzx   r8d, word ptr [rsi+46h]
0x14000673c  movzx   eax, word ptr [rsi+44h]
0x140006740  add     r8d, eax
0x140006743  add     [rdi], r8d
0x140006746  mov     [rbp+4Fh+arg_0], r8d
0x14000674a  jmp     short loc_14000674F
0x14000674c  mov     rdx, r14
0x14000674f  cmp     r13d, [rdi]
0x140006752  jnb     short loc_14000676A
0x140006754  mov     ecx, 7Ah ; 'z'; dwErrCode
0x140006759  call    cs:__imp_SetLastError
0x140006760  nop     dword ptr [rax+rax+00h]
0x140006765  jmp     loc_140006E0F
0x14000676a  test    rdx, rdx
0x14000676d  jz      short loc_140006796
0x14000676f  lea     rax, [r15+8]
0x140006773  mov     rcx, rbx; void *
0x140006776  mov     [rbp+4Fh+var_68], rax
0x14000677a  mov     [r15], rax
0x14000677d  call    ?pGetPrinterInfo2@@YAPEAU_PRINTER_INFO_2W@@PEAX@Z; pGetPrinterInfo2(void *)
0x140006782  mov     rcx, rax
0x140006785  mov     [rbp+4Fh+lpMem], rax
0x140006789  xor     eax, eax
0x14000678b  test    rcx, rcx
0x14000678e  setnz   al
0x140006791  jmp     loc_140006E0C
0x140006796  mov     [rbp+4Fh+dwDisposition], 1
0x14000679d  mov     [r15], r14
0x1400067a0  jmp     loc_140006E0F
0x1400067a5  cmp     [rbx+48h], rsi
0x1400067a9  jnz     short loc_1400067F4
0x1400067ab  mov     ecx, 2; dwErrCode
0x1400067b0  call    cs:__imp_SetLastError
0x1400067b7  nop     dword ptr [rax+rax+00h]
0x1400067bc  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x1400067c3  jz      loc_140006CA7
0x1400067c9  call    cs:__imp_GetLastError
0x1400067d0  nop     dword ptr [rax+rax+00h]
0x1400067d5  mov     r9d, 8
0x1400067db  mov     r8, [rbx+48h]
0x1400067df  lea     rdx, DocPerf_GetPrinter_Stop
0x1400067e6  mov     [rsp+0E0h+dwOptions], eax
0x1400067ea  call    McTemplateU0zqd_EtwEventWriteTransfer
0x1400067ef  jmp     loc_140006CA7
0x1400067f4  mov     rdi, [rbp+4Fh+pcbNeeded]
0x1400067f8  mov     rcx, rbx; void *
0x1400067fb  mov     dword ptr [rdi], 8
0x140006801  call    ?pGetPrinterInfo2@@YAPEAU_PRINTER_INFO_2W@@PEAX@Z; pGetPrinterInfo2(void *)
0x140006806  mov     [rbp+4Fh+lpMem], rax
0x14000680a  test    rax, rax
0x14000680d  jz      loc_140006E0F
0x140006813  mov     rdx, [rax+38h]
0x140006817  mov     qword ptr [rbp+4Fh+Size+4], rdx
0x14000681b  test    rdx, rdx
0x14000681e  jz      short loc_140006833
0x140006820  movzx   r8d, word ptr [rdx+46h]
0x140006825  movzx   eax, word ptr [rdx+44h]
0x140006829  add     r8d, eax
0x14000682c  add     [rdi], r8d
0x14000682f  mov     [rbp+4Fh+arg_0], r8d
0x140006833  cmp     r13d, [rdi]
0x140006836  jb      loc_140006754
0x14000683c  mov     [rbp+4Fh+dwDisposition], 1
0x140006843  test    rdx, rdx
0x140006846  jz      short loc_140006858
0x140006848  lea     rax, [r15+8]
0x14000684c  mov     [rbp+4Fh+var_68], rax
0x140006850  mov     [r15], rax
0x140006853  jmp     loc_140006E0F
0x140006858  mov     [r15], rsi
0x14000685b  jmp     loc_140006E0F
0x140006860  cmp     [rbx+48h], rsi
0x140006864  jz      loc_140006DC7
0x14000686a  call    CheckLocalCall
0x14000686f  test    eax, eax
0x140006871  jnz     loc_140006DC7
0x140006877  mov     rcx, [rbx+48h]; Str
0x14000687b  lea     rdx, gszDrvConvert; ",DrvConvert"
0x140006882  call    cs:__imp_wcsstr
0x140006889  nop     dword ptr [rax+rax+00h]
0x14000688e  test    rax, rax
0x140006891  jnz     loc_140006DC7
0x140006897  mov     ecx, cs:?gdwTlsGetPrinterIndex@@3KA; dwTlsIndex
0x14000689d  call    cs:__imp_TlsGetValue
0x1400068a4  nop     dword ptr [rax+rax+00h]
0x1400068a9  cmp     rax, 2
0x1400068ad  jz      loc_140006DC7
0x1400068b3  mov     rdi, [rbx+48h]
0x1400068b7  xor     eax, eax
0x1400068b9  mov     [rbp+4Fh+var_60], rax
0x1400068bd  test    rdi, rdi
0x1400068c0  jnz     short loc_1400068D8
0x1400068c2  mov     ecx, 6; dwErrCode
0x1400068c7  call    cs:__imp_SetLastError
0x1400068ce  nop     dword ptr [rax+rax+00h]
0x1400068d3  jmp     loc_140006DC7
0x1400068d8  mov     [rbp+4Fh+Token], 0FFFFFFFFFFFFFFFFh
0x1400068e0  mov     [rbp+4Fh+var_28], al
0x1400068e3  mov     [rbp+4Fh+dwDisposition], eax
0x1400068e6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x1400068ed  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x1400068f2  test    al, al
0x1400068f4  jz      short loc_140006913
0x1400068f6  call    ?IsCurrentProcess@ProcessUtils@@YA_NPEBG@Z; ProcessUtils::IsCurrentProcess(ushort const *)
0x1400068fb  lea     rdx, [rbp+4Fh+dwDisposition]; void **
0x1400068ff  lea     rcx, [rbp+4Fh+Token]; this
0x140006903  test    al, al
0x140006905  jz      short loc_14000691B
0x140006907  call    ?ElevateIntegrityLevelIfLowViaBroker@NSecurityLibrary@@YAJPEAPEAXPEAH@Z; NSecurityLibrary::ElevateIntegrityLevelIfLowViaBroker(void * *,int *)
0x14000690c  not     eax
0x14000690e  shr     eax, 1Fh
0x140006911  jmp     short loc_140006920
0x140006913  lea     rdx, [rbp+4Fh+dwDisposition]; void **
0x140006917  lea     rcx, [rbp+4Fh+Token]; this
0x14000691b  call    ?ElevateIntegrityLevelIfLowDirectly@NSecurityLibrary@@YAHPEAPEAXPEAH@Z; NSecurityLibrary::ElevateIntegrityLevelIfLowDirectly(void * *,int *)
0x140006920  test    eax, eax
0x140006922  jz      short loc_14000692D
0x140006924  cmp     [rbp+4Fh+dwDisposition], esi
0x140006927  jz      short loc_14000692D
0x140006929  mov     [rbp+4Fh+var_28], 1
0x14000692d  xor     eax, eax
0x14000692f  mov     ecx, 2001Fh
0x140006934  mov     [rbp+4Fh+var_60], rax
0x140006938  mov     [rbp+4Fh+lpValueName], rax
0x14000693c  call    SplGetClientUserHandle
0x140006941  mov     [rbp+4Fh+hKey], rax
0x140006945  test    rax, rax
0x140006948  jnz     short loc_14000697F
0x14000694a  call    cs:__imp_GetLastError
0x140006951  nop     dword ptr [rax+rax+00h]
0x140006956  cmp     eax, 5
0x140006959  jnz     short loc_14000696E
0x14000695b  mov     ecx, 20019h
0x140006960  call    SplGetClientUserHandle
0x140006965  mov     [rbp+4Fh+hKey], rax
0x140006969  test    rax, rax
0x14000696c  jnz     short loc_14000697F
0x14000696e  call    cs:__imp_GetLastError
0x140006975  nop     dword ptr [rax+rax+00h]
0x14000697a  jmp     loc_140006A15
0x14000697f  cmp     word ptr [rdi], 5Ch ; '\'
0x140006983  jnz     short loc_1400069B3
0x140006985  cmp     word ptr [rdi+2], 5Ch ; '\'
0x14000698a  jnz     short loc_1400069B3
0x14000698c  lea     r8, [rbp+4Fh+var_60]; phkResult
0x140006990  mov     rdx, rdi; unsigned __int16 *
0x140006993  mov     rcx, rax; hKey
0x140006996  call    ?RegOpenConnectionKey@@YAKPEAUHKEY__@@PEAGPEAPEAU1@@Z; RegOpenConnectionKey(HKEY__ *,ushort *,HKEY__ * *)
0x14000699b  mov     [rbp+4Fh+dwDisposition], eax
0x14000699e  test    eax, eax
0x1400069a0  jnz     short loc_1400069AF
0x1400069a2  lea     rax, gszDevMode; "DevMode"
0x1400069a9  mov     [rbp+4Fh+lpValueName], rax
0x1400069ad  jmp     short loc_140006A02
0x1400069af  mov     rax, [rbp+4Fh+hKey]
0x1400069b3  xor     edx, edx
0x1400069b5  lea     rcx, [rbp+4Fh+dwDisposition]
0x1400069b9  mov     [rsp+0E0h+lpdwDisposition], rcx; lpdwDisposition
0x1400069be  xor     r9d, r9d; lpClass
0x1400069c1  lea     rcx, [rbp+4Fh+var_60]
0x1400069c5  mov     [rbp+4Fh+dwDisposition], edx
0x1400069c8  mov     [rsp+0E0h+phkResult], rcx; phkResult
0x1400069cd  xor     r8d, r8d; Reserved
0x1400069d0  mov     [rsp+0E0h+lpSecurityAttributes], rdx; lpSecurityAttributes
0x1400069d5  mov     rcx, rax; hKey
0x1400069d8  mov     [rsp+0E0h+samDesired], 2001Fh; samDesired
0x1400069e0  mov     [rsp+0E0h+dwOptions], edx; dwOptions
0x1400069e4  lea     rdx, gszDevModePerUserLocal; "Printers\\DevModePerUser"
0x1400069eb  call    cs:__imp_RegCreateKeyExW
0x1400069f2  nop     dword ptr [rax+rax+00h]
0x1400069f7  mov     [rbp+4Fh+dwDisposition], eax
0x1400069fa  test    eax, eax
0x1400069fc  jnz     short loc_140006A02
0x1400069fe  mov     [rbp+4Fh+lpValueName], rdi
0x140006a02  mov     rcx, [rbp+4Fh+hKey]; hKey
0x140006a06  call    cs:__imp_RegCloseKey
0x140006a0d  nop     dword ptr [rax+rax+00h]
0x140006a12  mov     eax, [rbp+4Fh+dwDisposition]
0x140006a15  test    eax, eax
0x140006a17  jz      short loc_140006A3A
0x140006a19  mov     ecx, eax; dwErrCode
0x140006a1b  call    cs:__imp_SetLastError
0x140006a22  nop     dword ptr [rax+rax+00h]
0x140006a27  call    cs:__imp_GetLastError
0x140006a2e  nop     dword ptr [rax+rax+00h]
0x140006a33  mov     edi, eax
0x140006a35  jmp     loc_140006B6F
0x140006a3a  xor     ecx, ecx
0x140006a3c  lea     rax, [rbp+4Fh+dwDisposition]
0x140006a40  mov     [rsp+0E0h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x140006a45  xor     r9d, r9d; lpReserved
0x140006a48  mov     [rsp+0E0h+lpcbSecurityDescriptor], rcx; lpcbSecurityDescriptor
0x140006a4d  xor     r8d, r8d; lpcchClass
0x140006a50  mov     [rsp+0E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x140006a55  xor     edx, edx; lpClass
0x140006a57  mov     [rsp+0E0h+lpdwDisposition], rcx; lpcbMaxValueNameLen
0x140006a5c  mov     [rsp+0E0h+phkResult], rcx; lpcValues
0x140006a61  mov     [rsp+0E0h+lpSecurityAttributes], rcx; lpcbMaxClassLen
0x140006a66  mov     qword ptr [rsp+0E0h+samDesired], rcx; lpcbMaxSubKeyLen
0x140006a6b  mov     qword ptr [rsp+0E0h+dwOptions], rcx; lpcSubKeys
0x140006a70  mov     [rbp+4Fh+dwDisposition], ecx
0x140006a73  mov     rcx, [rbp+4Fh+var_60]; hKey
0x140006a77  call    cs:__imp_RegQueryInfoKeyW
0x140006a7e  nop     dword ptr [rax+rax+00h]
0x140006a83  mov     edi, eax
0x140006a85  test    eax, eax
0x140006a87  jnz     loc_140006B5F
0x140006a8d  mov     ecx, [rbp+4Fh+dwDisposition]; dwBytes
0x140006a90  cmp     ecx, 48h ; 'H'
0x140006a93  jb      loc_140006B5F
0x140006a99  call    DllAllocSplMem
0x140006a9e  mov     rsi, rax
0x140006aa1  test    rax, rax
0x140006aa4  jnz     short loc_140006AB9
0x140006aa6  call    cs:__imp_GetLastError
  ... truncated ...
```
