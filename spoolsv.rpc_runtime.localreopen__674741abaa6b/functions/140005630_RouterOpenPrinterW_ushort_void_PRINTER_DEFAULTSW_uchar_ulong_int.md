# RouterOpenPrinterW(ushort *,void * *,_PRINTER_DEFAULTSW *,uchar *,ulong,int)

- ea: `0x140005630`
- end: `0x140006152`
- name: `?RouterOpenPrinterW@@YAHPEAGPEAPEAXPEAU_PRINTER_DEFAULTSW@@PEAEKH@Z`
- size: `2850`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpValueName@<rcx>, void **@<rdx>, struct _PRINTER_DEFAULTSW *@<r8>, unsigned __int8 *@<r9>, unsigned int, int)`
- caller_count: `8`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000487c`
- `0x140004e08`
- `0x140004fc0`
- `0x140005240`
- `0x140005450`
- `0x140005520`
- `0x1400623d0`
- `0x140062470`

## callees

- `0x140002c80`
- `0x140002f40`
- `0x140003e80`
- `0x140003f70`
- `0x140004790`
- `0x140004800`
- `0x140005630`
- `0x140006160`
- `0x140007090`
- `0x14000b4b0`
- `0x14000bca0`
- `0x14000c390`
- `0x14000c5e0`
- `0x14000de80`
- `0x14000deb0`
- `0x14000f600`
- `0x140012c48`
- `0x140012f18`
- `0x1400131fc`
- `0x140015290`
- `0x140015378`
- `0x1400161d0`
- `0x140016314`
- `0x140016350`
- `0x140025504`
- `0x1400257ec`
- `0x14005bc28`
- `0x14005c00c`
- `0x140072f1c`
- `0x140073040`
- `0x140081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140005f91`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140005f91`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14000579d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14000579d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000573d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000573d`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1400056d8`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1400056d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005dc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005eb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000603a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005dc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005eb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000603a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005dab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005e96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000600d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005dab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005e96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000600d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005bd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006114`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005bd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006114`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400057de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400057de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400056ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000570e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400059c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400059ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005aa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005b2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005fcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000604e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400060a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400060bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400060e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400056ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000570e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400059c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400059ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005aa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005b2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005fcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000604e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400060a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400060bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400060e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000569a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400057f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400058b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005a99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005c0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006098`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000569a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400057f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400058b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005a99`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005c0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006098`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140005c57`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140005c57`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000572d`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140005c6c`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14000572d`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140005c6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000574c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005c7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000574c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005c7c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140005bb3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140005bb3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140005afb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140005afb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140005a6b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140005a6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140005b5e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140005b5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005a85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005bf9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005a85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005bf9`

## string_xrefs

- `0x140005f8a`: `win32spl.dll`
- `0x1400060cb`: `Failed to open printer %ws. Error %d`
- `0x1400060f2`: `Failed to open printer %ws. Error %d`
- `0x1400060d5`: `RouterOpenPrinterW`
- `0x1400060fc`: `RouterOpenPrinterW`
- `0x140005810`: `DllAllocSplMem`
- `0x1400056fb`: `Failed to create Phase2Init event.  Error %d.`
- `0x140005793`: `,NoCache`

## pseudocode

```c
__int64 __fastcall RouterOpenPrinterW(
        wchar_t *lpValueName,
        void **a2,
        struct _PRINTER_DEFAULTSW *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        int a6)
{
  __int64 v9; // rax
  HANDLE v11; // rsi
  HANDLE v12; // rax
  void *v13; // rdi
  DWORD LastError; // eax
  DWORD v15; // eax
  NCoreLibrary *v16; // rcx
  unsigned int v17; // r8d
  DWORD v18; // eax
  wchar_t *v19; // rsi
  wchar_t *v20; // rdi
  __int64 v21; // rax
  _QWORD *v22; // rax
  _QWORD *v23; // rdi
  __int64 v24; // rax
  __int64 v25; // r13
  struct _PRINTER_DEFAULTSW *v26; // rdx
  unsigned int v27; // r12d
  __int64 v28; // rax
  const unsigned __int16 *v29; // rdx
  ProcessUtils *v30; // rcx
  int *v31; // r8
  int v32; // eax
  HKEY ClientUserHandle; // r14
  unsigned int v34; // r12d
  DWORD v35; // r14d
  const WCHAR *v36; // r12
  unsigned int IsValidDevmodeNo; // r8d
  HANDLE v38; // r14
  __int64 v39; // rax
  struct _PROVIDOR *EntryinRouterCache; // r14
  int v41; // eax
  DWORD v42; // eax
  unsigned __int16 *v43; // rdx
  unsigned int ClientLevel; // eax
  DWORD v45; // eax
  DWORD v46; // eax
  DWORD v47; // eax
  const WCHAR *ProvidorFromConnection; // rax
  unsigned __int16 *v49; // rdx
  struct _PROVIDOR *v50; // rcx
  unsigned int v51; // eax
  unsigned int v52; // r15d
  DWORD v53; // ecx
  bool v54; // zf
  const WCHAR *v55; // rcx
  __int64 (__fastcall *v56)(const WCHAR *, void **, struct _PRINTER_DEFAULTSW *, unsigned __int8 *, DWORD); // rax
  DWORD v57; // eax
  unsigned __int16 *v58; // rdx
  struct _PROVIDOR *v59; // r8
  DWORD v60; // eax
  DWORD v61; // eax
  DWORD v62; // eax
  DWORD v63; // ecx
  DWORD v64; // eax
  DWORD v65; // eax
  DWORD v66; // eax
  DWORD dwDisposition; // [rsp+60h] [rbp-79h] BYREF
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-75h] BYREF
  LPCWSTR lpValueNamea; // [rsp+68h] [rbp-71h]
  HKEY hKey; // [rsp+70h] [rbp-69h] BYREF
  void *v71; // [rsp+78h] [rbp-61h] BYREF
  HANDLE Token; // [rsp+80h] [rbp-59h] BYREF
  char v73; // [rsp+88h] [rbp-51h]
  unsigned __int8 v74[16]; // [rsp+90h] [rbp-49h] BYREF
  __int128 v75; // [rsp+A0h] [rbp-39h]
  __int128 v76; // [rsp+B0h] [rbp-29h]
  __int128 v77; // [rsp+C0h] [rbp-19h]
  __int128 v78; // [rsp+D0h] [rbp-9h] BYREF
  __int64 v79; // [rsp+E0h] [rbp+7h]
  unsigned int v80; // [rsp+130h] [rbp+57h] BYREF
  void **v81; // [rsp+138h] [rbp+5Fh]
  struct _PRINTER_DEFAULTSW *v82; // [rsp+140h] [rbp+67h]

  v82 = a3;
  v81 = a2;
  v80 = 123;
  v71 = 0;
  v79 = 0;
  v78 = 0;
  if ( lpValueName )
  {
    v9 = -1;
    do
      ++v9;
    while ( lpValueName[v9] );
    if ( (unsigned __int64)(v9 + 1) > 0x21B )
    {
      SetLastError(0x709u);
      return 0;
    }
  }
  if ( !Initialized )
  {
    v11 = RevertToPrinterSelf();
    v12 = OpenEventW(2u, 0, L"RouterPreInitEvent");
    v13 = v12;
    if ( !v12 )
    {
      LastError = GetLastError();
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "WaitForSpoolerInitialization",
        L"Failed to create Phase2Init event.  Error %d.",
        LastError);
      v15 = GetLastError();
      SplLogRouterEvent(&MSG_ROUTER_PHASE2INIT_FAILED, v15, 0);
      ExitProcess(0);
    }
    SetEvent(v12);
    CloseHandle(v13);
    if ( v11 && !ImpersonatePrinterClient(v11) )
    {
      v18 = GetLastError();
      ForceProcessShutdown(0x69u, v18);
    }
    NCoreLibrary::WaitForAutoEventHandle(v16, (struct NCoreLibrary::TAutoHandle *)0xFFFFFFFFLL, v17);
  }
  v19 = lpValueName;
  if ( lpValueName )
  {
    v20 = wcsstr(lpValueName, L",NoCache");
    if ( v20 )
    {
      v21 = AllocSplStr(lpValueName);
      v19 = (wchar_t *)v21;
      if ( !v21 )
        return 0;
      *(_WORD *)(v21 + 2 * (v20 - lpValueName)) = 0;
    }
  }
  v22 = HeapAlloc(g_hSpoolssHeap, 8u, 0x68u);
  v23 = v22;
  if ( !v22 )
  {
    SetLastError(8u);
    PrvSpoolssTelemetry::WriteDbgTraceError("DllAllocSplMem", L"Unable to allocate %d bytes of memory on heap.", 104);
    if ( v19 != lpValueName )
      DllFreeSplStr(v19);
    return 0;
  }
  *(_DWORD *)v22 = 24672;
  v22[7] = -1;
  v22[8] = 0;
  v22[10] = 0;
  *((_DWORD *)v22 + 22) = 0;
  v22[12] = 0;
  if ( v19 )
  {
    v24 = AllocSplStr(v19);
    v23[9] = v24;
    if ( !v24 )
    {
      if ( v19 != lpValueName )
        DllFreeSplStr(v19);
      FreePrinterHandle((struct _PRINTHANDLE *)v23);
      return 0;
    }
  }
  v25 = 0;
  if ( a3 && a3->pDevMode || (unsigned int)CheckLocalCall() )
    goto LABEL_31;
  LPatchUserDevmodes(v19);
  hKey = 0;
  if ( !v19 )
  {
    SetLastError(6u);
    goto LABEL_31;
  }
  Token = (HANDLE)-1LL;
  v73 = 0;
  cbMaxValueLen = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl)
    && ProcessUtils::IsCurrentProcess(v30, v29) )
  {
    v32 = (int)NSecurityLibrary::ElevateIntegrityLevelIfLowViaBroker(
                 (NSecurityLibrary *)&Token,
                 (void **)&cbMaxValueLen,
                 v31) >= 0;
  }
  else
  {
    v32 = NSecurityLibrary::ElevateIntegrityLevelIfLowDirectly((NSecurityLibrary *)&Token, (void **)&cbMaxValueLen, v31);
  }
  if ( v32 && cbMaxValueLen )
    v73 = 1;
  hKey = 0;
  lpValueNamea = 0;
  ClientUserHandle = (HKEY)SplGetClientUserHandle(131103);
  if ( !ClientUserHandle )
  {
    if ( GetLastError() != 5 )
    {
LABEL_45:
      v34 = GetLastError();
      goto LABEL_53;
    }
    ClientUserHandle = (HKEY)SplGetClientUserHandle(131097);
  }
  if ( !ClientUserHandle )
    goto LABEL_45;
  if ( *v19 == 92 && v19[1] == 92 && (v34 = RegOpenConnectionKey(ClientUserHandle, v19, &hKey)) == 0 )
  {
    lpValueNamea = L"DevMode";
  }
  else
  {
    dwDisposition = 0;
    v34 = RegCreateKeyExW(ClientUserHandle, L"Printers\\DevModePerUser", 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
    if ( !v34 )
      lpValueNamea = v19;
  }
  RegCloseKey(ClientUserHandle);
LABEL_53:
  if ( v34 )
  {
    SetLastError(v34);
    v35 = GetLastError();
    goto LABEL_70;
  }
  cbMaxValueLen = 0;
  v35 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueLen, 0, 0);
  if ( !v35 && cbMaxValueLen >= 0x48 )
  {
    v25 = DllAllocSplMem(cbMaxValueLen);
    if ( !v25 )
    {
      v35 = GetLastError();
      goto LABEL_69;
    }
    v36 = lpValueNamea;
    v35 = RegQueryValueExW(hKey, lpValueNamea, 0, 0, (LPBYTE)v25, &cbMaxValueLen);
    if ( !v35 )
    {
      IsValidDevmodeNo = -2147024883;
      if ( cbMaxValueLen >= 0x4CuLL
        && cbMaxValueLen >= *(unsigned __int16 *)(v25 + 68) + (unsigned __int64)*(unsigned __int16 *)(v25 + 70) )
      {
        IsValidDevmodeNo = SplIsValidDevmodeNoSize<_devicemodeW,unsigned short>(v25, cbMaxValueLen, 2147942413LL);
      }
      v35 = StatusFromHResult(IsValidDevmodeNo);
      if ( !v35 )
        goto LABEL_67;
      if ( !RegDeleteValueW(hKey, v36) )
        v35 = 2;
    }
    HeapFree(g_hSpoolssHeap, 0, (LPVOID)v25);
    v25 = 0;
LABEL_67:
    if ( v35 == 2 )
      v35 = 0;
  }
LABEL_69:
  RegCloseKey(hKey);
LABEL_70:
  if ( v35 )
  {
    SetLastError(v35);
    if ( v35 != 5 )
      PrvSpoolssTelemetry::WriteDbgTraceError("bGetDevModePerUser", L"Failed to get devmode. Error %d.", v35);
    NSecurityLibrary::Low2MediumIntegrity::~Low2MediumIntegrity((NSecurityLibrary::Low2MediumIntegrity *)&Token);
  }
  else
  {
    v38 = Token;
    if ( Token != (HANDLE)-1LL )
    {
      if ( Token && !SetThreadToken(0, Token) )
        ExitProcess(1u);
      CloseHandle(v38);
    }
    if ( v25 )
    {
      if ( v82 )
      {
        *(_QWORD *)&v78 = v82->pDatatype;
        LODWORD(v79) = v82->DesiredAccess;
      }
      else
      {
        *(_QWORD *)&v78 = 0;
        LODWORD(v79) = 0;
      }
      v26 = (struct _PRINTER_DEFAULTSW *)&v78;
      *((_QWORD *)&v78 + 1) = v25;
      v82 = (struct _PRINTER_DEFAULTSW *)&v78;
      goto LABEL_32;
    }
  }
LABEL_31:
  v26 = v82;
LABEL_32:
  v27 = a5;
  *(_OWORD *)v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  switch ( a5 )
  {
    case 4u:
      *((_DWORD *)v23 + 21) = *((_DWORD *)a4 + 12);
      *((_DWORD *)v23 + 22) = *((_DWORD *)a4 + 13);
      *(_DWORD *)&v74[4] = *(_DWORD *)a4;
      v75 = *(_OWORD *)(a4 + 8);
      *(_QWORD *)&v76 = *((_QWORD *)a4 + 3);
      DWORD2(v76) = *((_DWORD *)a4 + 8);
      WORD6(v76) = *((_WORD *)a4 + 18);
      v28 = *((_QWORD *)a4 + 5);
      a4 = v74;
      *(_QWORD *)&v77 = v28;
      *(_DWORD *)v74 = 56;
      *(_DWORD *)&v74[8] = 40;
      *((_QWORD *)&v77 + 1) = *(_QWORD *)((char *)v23 + 84);
      break;
    case 3u:
      *(_DWORD *)&v74[4] = *((_DWORD *)a4 + 1);
      v75 = *((_OWORD *)a4 + 1);
      *(_QWORD *)&v76 = *((_QWORD *)a4 + 4);
      DWORD2(v76) = *((_DWORD *)a4 + 10);
      WORD6(v76) = *((_WORD *)a4 + 22);
      v39 = *((_QWORD *)a4 + 6);
      a4 = v74;
      *(_QWORD *)&v77 = v39;
      *(_DWORD *)v74 = 56;
      *(_DWORD *)&v74[8] = 40;
      break;
    case 0x64u:
      *((_DWORD *)v23 + 21) = *((_DWORD *)a4 + 14);
      *((_DWORD *)v23 + 22) = *((_DWORD *)a4 + 15);
      break;
  }
  if ( a6 )
  {
    EntryinRouterCache = pLocalProvidor;
    if ( v27 == 4 )
    {
      v41 = 3;
      if ( *((_DWORD *)pLocalProvidor + 224) )
        v41 = 100;
    }
    else
    {
      v41 = v27;
    }
    dwDisposition = (*((__int64 (__fastcall **)(wchar_t *, void **, struct _PRINTER_DEFAULTSW *, unsigned __int8 *, int))pLocalProvidor
                     + 61))(
                      v19,
                      &v71,
                      v26,
                      a4,
                      v41);
    if ( dwDisposition == 1 )
      goto LABEL_112;
    v42 = GetLastError();
    UpdateSignificantError(v42, &v80);
    if ( dwDisposition == 2 )
      goto LABEL_137;
  }
  EnterCriticalSection(&RouterNotifySection);
  EntryinRouterCache = NRouter::FindEntryinRouterCache((NRouter *)v19, v43);
  LeaveCriticalSection(&RouterNotifySection);
  if ( !EntryinRouterCache )
  {
    ProvidorFromConnection = (const WCHAR *)FindProvidorFromConnection(v19);
    v50 = 0;
    goto LABEL_108;
  }
  ClientLevel = GetClientLevel(v27, EntryinRouterCache);
  v45 = (*((__int64 (__fastcall **)(wchar_t *, void **, struct _PRINTER_DEFAULTSW *, unsigned __int8 *, unsigned int))EntryinRouterCache
         + 61))(
          v19,
          &v71,
          v82,
          a4,
          ClientLevel);
  dwDisposition = v45;
  if ( v45 )
  {
    if ( v45 != 50 )
      goto LABEL_102;
  }
  else if ( GetLastError() != 50 )
  {
    v46 = GetLastError();
    UpdateSignificantError(v46, &v80);
LABEL_104:
    ProvidorFromConnection = (const WCHAR *)FindProvidorFromConnection(v19);
    lpValueNamea = ProvidorFromConnection;
    if ( ProvidorFromConnection != (const WCHAR *)EntryinRouterCache )
    {
      EnterCriticalSection(&RouterNotifySection);
      NRouter::DeleteEntryfromRouterCache((NRouter *)v19, v49);
      LeaveCriticalSection(&RouterNotifySection);
      v50 = EntryinRouterCache;
      EntryinRouterCache = (struct _PROVIDOR *)lpValueNamea;
LABEL_109:
      Token = v50;
      if ( EntryinRouterCache )
      {
        if ( EntryinRouterCache != v50 )
        {
          v51 = GetClientLevel(v27, EntryinRouterCache);
          if ( TryOpenPrinterAndCache(EntryinRouterCache, (NRouter *)v19, &v71, v82, &v80, a4, v51) == 1 )
            goto LABEL_112;
        }
LABEL_137:
        FreePrinterHandle((struct _PRINTHANDLE *)v23);
        v63 = v80;
        if ( v80 == 123 )
          v63 = 1801;
        SetLastError(v63);
        v52 = 0;
        v64 = GetLastError();
        if ( v64 == 5 || v64 == 1801 )
        {
          v66 = GetLastError();
          PrvSpoolssTelemetry::WriteDbgTraceInfo(
            "RouterOpenPrinterW",
            L"Failed to open printer %ws. Error %d",
            lpValueName,
            v66);
        }
        else
        {
          v65 = GetLastError();
          PrvSpoolssTelemetry::WriteDbgTraceError(
            "RouterOpenPrinterW",
            L"Failed to open printer %ws. Error %d",
            lpValueName,
            v65);
        }
        goto LABEL_143;
      }
      for ( EntryinRouterCache = *(struct _PROVIDOR **)pLocalProvidor;
            ;
            EntryinRouterCache = *(struct _PROVIDOR **)EntryinRouterCache )
      {
        if ( !EntryinRouterCache )
          goto LABEL_137;
        if ( EntryinRouterCache != v50 )
          break;
LABEL_136:
        ;
      }
      if ( v27 == 4 )
      {
        v53 = 3;
        if ( *((_DWORD *)EntryinRouterCache + 224) )
          v53 = 100;
        dwDisposition = v53;
      }
      else
      {
        dwDisposition = v27;
      }
      v54 = (unsigned int)_o__wcsicmp(*((_QWORD *)EntryinRouterCache + 1), L"win32spl.dll") == 0;
      v55 = lpValueName;
      if ( !v54 )
        v55 = v19;
      v56 = (__int64 (__fastcall *)(const WCHAR *, void **, struct _PRINTER_DEFAULTSW *, unsigned __int8 *, DWORD))*((_QWORD *)EntryinRouterCache + 61);
      lpValueNamea = v55;
      v57 = v56(v55, &v71, v82, a4, dwDisposition);
      dwDisposition = v57;
      if ( v57 )
      {
        if ( v57 != 50 )
        {
LABEL_128:
          if ( v57 - 1 <= 1 )
          {
            EnterCriticalSection(&RouterNotifySection);
            if ( !NRouter::FindEntryinRouterCache((NRouter *)lpValueNamea, v58) )
              NRouter::AddEntrytoRouterCache((NRouter *)lpValueNamea, (unsigned __int16 *)EntryinRouterCache, v59);
            LeaveCriticalSection(&RouterNotifySection);
            v60 = dwDisposition;
            if ( dwDisposition == 1 )
              goto LABEL_133;
          }
          goto LABEL_132;
        }
      }
      else if ( GetLastError() != 50 )
      {
LABEL_132:
        v61 = GetLastError();
        UpdateSignificantError(v61, &v80);
        v60 = dwDisposition;
LABEL_133:
        v62 = v60 - 1;
        if ( !v62 )
          goto LABEL_112;
        if ( v62 == 1 )
          goto LABEL_137;
        v50 = (struct _PROVIDOR *)Token;
        goto LABEL_136;
      }
      v57 = (*((__int64 (__fastcall **)(LPCWSTR, void **, struct _PRINTER_DEFAULTSW *))EntryinRouterCache + 4))(
              lpValueNamea,
              &v71,
              v82);
      dwDisposition = v57;
      goto LABEL_128;
    }
    v50 = EntryinRouterCache;
LABEL_108:
    EntryinRouterCache = (struct _PROVIDOR *)ProvidorFromConnection;
    goto LABEL_109;
  }
  v45 = (*((__int64 (__fastcall **)(wchar_t *, void **, struct _PRINTER_DEFAULTSW *))EntryinRouterCache + 4))(
          v19,
          &v71,
          v82);
  dwDisposition = v45;
LABEL_102:
  if ( v45 != 1 )
  {
    v47 = GetLastError();
    UpdateSignificantError(v47, &v80);
    if ( dwDisposition == 2 )
      goto LABEL_137;
    goto LABEL_104;
  }
LABEL_112:
  v23[1] = EntryinRouterCache;
  v52 = 1;
  v23[2] = v71;
  *v81 = v23;
LABEL_143:
  HeapFree(g_hSpoolssHeap, 0, (LPVOID)v25);
  if ( v19 != lpValueName )
    DllFreeSplStr(v19);
  return v52;
}

```

## disassembly

```asm
0x140005630  mov     [rsp-8+arg_10], r8
0x140005635  mov     [rsp-8+arg_8], rdx
0x14000563a  push    rbp
0x14000563b  push    rbx
0x14000563c  push    rdi
0x14000563d  push    r12
0x14000563f  push    r14
0x140005641  push    r15
0x140005643  lea     rbp, [rsp-1Fh]
0x140005648  sub     rsp, 0F8h
0x14000564f  xor     r12d, r12d
0x140005652  mov     [rbp+47h+arg_0], 7Bh ; '{'
0x140005659  xor     eax, eax
0x14000565b  mov     [rbp+47h+var_A8], r12
0x14000565f  mov     [rbp+47h+var_40], rax
0x140005663  xorps   xmm0, xmm0
0x140005666  mov     r15, r9
0x140005669  mov     r14, r8
0x14000566c  mov     rbx, rcx
0x14000566f  movups  [rbp+47h+var_50], xmm0
0x140005673  test    rcx, rcx
0x140005676  jz      short loc_1400056AD
0x140005678  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14000567f  nop
0x140005680  inc     rax
0x140005683  cmp     [rcx+rax*2], r12w
0x140005688  jnz     short loc_140005680
0x14000568a  inc     rax
0x14000568d  cmp     rax, 21Bh
0x140005693  jbe     short loc_1400056AD
0x140005695  mov     ecx, 709h; dwErrCode
0x14000569a  call    cs:__imp_SetLastError
0x1400056a1  nop     dword ptr [rax+rax+00h]
0x1400056a6  xor     eax, eax
0x1400056a8  jmp     loc_140006140
0x1400056ad  cmp     cs:?Initialized@@3HA, r12d; int Initialized
0x1400056b4  mov     [rsp+120h+arg_18], rsi
0x1400056bc  jnz     loc_14000578B
0x1400056c2  call    RevertToPrinterSelf
0x1400056c7  lea     r8, Name; "RouterPreInitEvent"
0x1400056ce  xor     edx, edx; bInheritHandle
0x1400056d0  mov     ecx, 2; dwDesiredAccess
0x1400056d5  mov     rsi, rax
0x1400056d8  call    cs:__imp_OpenEventW
0x1400056df  nop     dword ptr [rax+rax+00h]
0x1400056e4  mov     rdi, rax
0x1400056e7  test    rax, rax
0x1400056ea  jnz     short loc_14000573A
0x1400056ec  call    cs:__imp_GetLastError
0x1400056f3  nop     dword ptr [rax+rax+00h]
0x1400056f8  mov     r8d, eax
0x1400056fb  lea     rdx, aFailedToCreate_3; "Failed to create Phase2Init event.  Err"...
0x140005702  lea     rcx, aWaitforspooler; "WaitForSpoolerInitialization"
0x140005709  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000570e  call    cs:__imp_GetLastError
0x140005715  nop     dword ptr [rax+rax+00h]
0x14000571a  xor     r8d, r8d; unsigned __int16 *
0x14000571d  lea     rcx, MSG_ROUTER_PHASE2INIT_FAILED; struct _EVENT_DESCRIPTOR *
0x140005724  mov     edx, eax; unsigned int
0x140005726  call    ?SplLogRouterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBG@Z; SplLogRouterEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *)
0x14000572b  xor     ecx, ecx; uExitCode
0x14000572d  call    cs:__imp_ExitProcess
0x14000573a  mov     rcx, rdi; hEvent
0x14000573d  call    cs:__imp_SetEvent
0x140005744  nop     dword ptr [rax+rax+00h]
0x140005749  mov     rcx, rdi; hObject
0x14000574c  call    cs:__imp_CloseHandle
0x140005753  nop     dword ptr [rax+rax+00h]
0x140005758  test    rsi, rsi
0x14000575b  jz      short loc_140005781
0x14000575d  mov     rcx, rsi; hToken
0x140005760  call    ImpersonatePrinterClient
0x140005765  test    eax, eax
0x140005767  jnz     short loc_140005781
0x140005769  call    cs:__imp_GetLastError
0x140005770  nop     dword ptr [rax+rax+00h]
0x140005775  mov     edx, eax; unsigned int
0x140005777  mov     ecx, 69h ; 'i'; unsigned int
0x14000577c  call    ?ForceProcessShutdown@@YAXKK@Z; ForceProcessShutdown(ulong,ulong)
0x140005781  mov     edx, 0FFFFFFFFh; struct NCoreLibrary::TAutoHandle *
0x140005786  call    ?WaitForAutoEventHandle@NCoreLibrary@@YAJPEAVTAutoHandle@1@K@Z; NCoreLibrary::WaitForAutoEventHandle(NCoreLibrary::TAutoHandle *,ulong)
0x14000578b  mov     rsi, rbx
0x14000578e  test    rbx, rbx
0x140005791  jz      short loc_1400057CC
0x140005793  lea     rdx, szNoCache; ",NoCache"
0x14000579a  mov     rcx, rbx; Str
0x14000579d  call    cs:__imp_wcsstr
0x1400057a4  nop     dword ptr [rax+rax+00h]
0x1400057a9  mov     rdi, rax
0x1400057ac  test    rax, rax
0x1400057af  jz      short loc_1400057CC
0x1400057b1  mov     rcx, rbx; Src
0x1400057b4  call    AllocSplStr
0x1400057b9  mov     rsi, rax
0x1400057bc  test    rax, rax
0x1400057bf  jz      short loc_140005829
0x1400057c1  sub     rdi, rbx
0x1400057c4  sar     rdi, 1
0x1400057c7  mov     [rax+rdi*2], r12w
0x1400057cc  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x1400057d3  mov     edx, 8; dwFlags
0x1400057d8  mov     r8d, 68h ; 'h'; dwBytes
0x1400057de  call    cs:__imp_HeapAlloc
0x1400057e5  nop     dword ptr [rax+rax+00h]
0x1400057ea  mov     rdi, rax
0x1400057ed  test    rax, rax
0x1400057f0  jnz     short loc_140005830
0x1400057f2  mov     ecx, 8; dwErrCode
0x1400057f7  call    cs:__imp_SetLastError
0x1400057fe  nop     dword ptr [rax+rax+00h]
0x140005803  mov     r8d, 68h ; 'h'
0x140005809  lea     rdx, aUnableToAlloca; "Unable to allocate %d bytes of memory o"...
0x140005810  lea     rcx, aDllallocsplmem; "DllAllocSplMem"
0x140005817  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000581c  cmp     rsi, rbx
0x14000581f  jz      short loc_140005829
0x140005821  mov     rcx, rsi
0x140005824  call    DllFreeSplStr
0x140005829  xor     eax, eax
0x14000582b  jmp     loc_140006138
0x140005830  mov     dword ptr [rax], 6060h
0x140005836  mov     qword ptr [rax+38h], 0FFFFFFFFFFFFFFFFh
0x14000583e  mov     [rax+40h], r12
0x140005842  mov     [rax+50h], r12
0x140005846  mov     [rax+58h], r12d
0x14000584a  mov     [rax+60h], r12
0x14000584e  test    rsi, rsi
0x140005851  jz      short loc_140005880
0x140005853  mov     rcx, rsi; Src
0x140005856  call    AllocSplStr
0x14000585b  mov     [rdi+48h], rax
0x14000585f  test    rax, rax
0x140005862  jnz     short loc_140005880
0x140005864  cmp     rsi, rbx
0x140005867  jz      short loc_140005871
0x140005869  mov     rcx, rsi
0x14000586c  call    DllFreeSplStr
0x140005871  mov     rcx, rdi; struct _PRINTHANDLE *
0x140005874  call    ?FreePrinterHandle@@YAXPEAU_PRINTHANDLE@@@Z; FreePrinterHandle(_PRINTHANDLE *)
0x140005879  xor     eax, eax
0x14000587b  jmp     loc_140006138
0x140005880  mov     [rsp+120h+var_30], r13
0x140005888  mov     r13, r12
0x14000588b  test    r14, r14
0x14000588e  jz      short loc_140005896
0x140005890  cmp     [r14+8], r12
0x140005894  jnz     short loc_1400058C5
0x140005896  call    CheckLocalCall
0x14000589b  test    eax, eax
0x14000589d  jnz     short loc_1400058C5
0x14000589f  mov     rcx, rsi; lpValueName
0x1400058a2  call    LPatchUserDevmodes
0x1400058a7  mov     [rbp+47h+hKey], r12
0x1400058ab  test    rsi, rsi
0x1400058ae  jnz     loc_140005957
0x1400058b4  mov     ecx, 6; dwErrCode
0x1400058b9  call    cs:__imp_SetLastError
0x1400058c0  nop     dword ptr [rax+rax+00h]
0x1400058c5  mov     rdx, [rbp+47h+arg_10]
0x1400058c9  mov     r12d, [rbp+47h+arg_20]
0x1400058cd  xorps   xmm0, xmm0
0x1400058d0  movups  xmmword ptr [rbp+47h+var_90], xmm0
0x1400058d4  movups  [rbp+47h+var_80], xmm0
0x1400058d8  movups  [rbp+47h+var_70], xmm0
0x1400058dc  movups  [rbp+47h+var_60], xmm0
0x1400058e0  cmp     r12d, 4
0x1400058e4  jnz     loc_140005CC2
0x1400058ea  mov     eax, [r15+30h]
0x1400058ee  mov     [rdi+54h], eax
0x1400058f1  mov     eax, [r15+34h]
0x1400058f5  mov     [rdi+58h], eax
0x1400058f8  mov     eax, [r15]
0x1400058fb  mov     dword ptr [rbp+47h+var_90+4], eax
0x1400058fe  mov     rax, [r15+8]
0x140005902  mov     qword ptr [rbp+47h+var_80], rax
0x140005906  mov     rax, [r15+10h]
0x14000590a  mov     qword ptr [rbp+47h+var_80+8], rax
0x14000590e  mov     eax, [r15+18h]
0x140005912  mov     dword ptr [rbp+47h+var_70], eax
0x140005915  mov     eax, [r15+1Ch]
0x140005919  mov     dword ptr [rbp+47h+var_70+4], eax
0x14000591c  mov     eax, [r15+20h]
0x140005920  mov     dword ptr [rbp+47h+var_70+8], eax
0x140005923  movzx   eax, word ptr [r15+24h]
0x140005928  mov     word ptr [rbp+47h+var_70+0Ch], ax
0x14000592c  mov     rax, [r15+28h]
0x140005930  lea     r15, [rbp+47h+var_90]
0x140005934  mov     qword ptr [rbp+47h+var_60], rax
0x140005938  mov     dword ptr [rbp+47h+var_90], 38h ; '8'
0x14000593f  mov     dword ptr [rbp+47h+var_90+8], 28h ; '('
0x140005946  mov     eax, [rdi+54h]
0x140005949  mov     dword ptr [rbp+47h+var_60+8], eax
0x14000594c  mov     eax, [rdi+58h]
0x14000594f  mov     dword ptr [rbp+47h+var_60+0Ch], eax
0x140005952  jmp     loc_140005D2D
0x140005957  mov     [rbp+47h+Token], 0FFFFFFFFFFFFFFFFh
0x14000595f  mov     [rbp+47h+var_98], r12b
0x140005963  mov     [rbp+47h+cbMaxValueLen], r12d
0x140005967  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x14000596e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140005973  test    al, al
0x140005975  jz      short loc_140005994
0x140005977  call    ?IsCurrentProcess@ProcessUtils@@YA_NPEBG@Z; ProcessUtils::IsCurrentProcess(ushort const *)
0x14000597c  lea     rdx, [rbp+47h+cbMaxValueLen]; void **
0x140005980  lea     rcx, [rbp+47h+Token]; this
0x140005984  test    al, al
0x140005986  jz      short loc_14000599C
0x140005988  call    ?ElevateIntegrityLevelIfLowViaBroker@NSecurityLibrary@@YAJPEAPEAXPEAH@Z; NSecurityLibrary::ElevateIntegrityLevelIfLowViaBroker(void * *,int *)
0x14000598d  not     eax
0x14000598f  shr     eax, 1Fh
0x140005992  jmp     short loc_1400059A1
0x140005994  lea     rdx, [rbp+47h+cbMaxValueLen]; void **
0x140005998  lea     rcx, [rbp+47h+Token]; this
0x14000599c  call    ?ElevateIntegrityLevelIfLowDirectly@NSecurityLibrary@@YAHPEAPEAXPEAH@Z; NSecurityLibrary::ElevateIntegrityLevelIfLowDirectly(void * *,int *)
0x1400059a1  test    eax, eax
0x1400059a3  jz      short loc_1400059AF
0x1400059a5  cmp     [rbp+47h+cbMaxValueLen], r12d
0x1400059a9  jz      short loc_1400059AF
0x1400059ab  mov     [rbp+47h+var_98], 1
0x1400059af  mov     ecx, 2001Fh
0x1400059b4  mov     [rbp+47h+hKey], r12
0x1400059b8  mov     [rbp+47h+lpValueName], r12
0x1400059bc  call    SplGetClientUserHandle
0x1400059c1  mov     r14, rax
0x1400059c4  test    rax, rax
0x1400059c7  jnz     short loc_1400059E7
0x1400059c9  call    cs:__imp_GetLastError
0x1400059d0  nop     dword ptr [rax+rax+00h]
0x1400059d5  cmp     eax, 5
0x1400059d8  jnz     short loc_1400059EC
0x1400059da  mov     ecx, 20019h
0x1400059df  call    SplGetClientUserHandle
0x1400059e4  mov     r14, rax
0x1400059e7  test    r14, r14
0x1400059ea  jnz     short loc_140005A00
0x1400059ec  call    cs:__imp_GetLastError
0x1400059f3  nop     dword ptr [rax+rax+00h]
0x1400059f8  mov     r12d, eax
0x1400059fb  jmp     loc_140005A91
0x140005a00  cmp     word ptr [rsi], 5Ch ; '\'
0x140005a04  jnz     short loc_140005A33
0x140005a06  cmp     word ptr [rsi+2], 5Ch ; '\'
0x140005a0b  jnz     short loc_140005A33
0x140005a0d  lea     r8, [rbp+47h+hKey]; phkResult
0x140005a11  mov     rdx, rsi; unsigned __int16 *
0x140005a14  mov     rcx, r14; hKey
0x140005a17  call    ?RegOpenConnectionKey@@YAKPEAUHKEY__@@PEAGPEAPEAU1@@Z; RegOpenConnectionKey(HKEY__ *,ushort *,HKEY__ * *)
0x140005a1c  mov     r12d, eax
0x140005a1f  test    eax, eax
0x140005a21  jnz     short loc_140005A30
0x140005a23  lea     rax, gszDevMode; "DevMode"
0x140005a2a  mov     [rbp+47h+lpValueName], rax
0x140005a2e  jmp     short loc_140005A82
0x140005a30  xor     r12d, r12d
0x140005a33  lea     rax, [rbp+47h+dwDisposition]
0x140005a37  mov     [rbp+47h+dwDisposition], r12d
0x140005a3b  mov     [rsp+120h+lpdwDisposition], rax; lpdwDisposition
0x140005a40  lea     rdx, gszDevModePerUserLocal; "Printers\\DevModePerUser"
0x140005a47  lea     rax, [rbp+47h+hKey]
0x140005a4b  xor     r9d, r9d; lpClass
0x140005a4e  mov     [rsp+120h+phkResult], rax; phkResult
0x140005a53  xor     r8d, r8d; Reserved
0x140005a56  mov     [rsp+120h+lpSecurityAttributes], r12; lpSecurityAttributes
0x140005a5b  mov     rcx, r14; hKey
0x140005a5e  mov     [rsp+120h+samDesired], 2001Fh; samDesired
0x140005a66  mov     [rsp+120h+dwOptions], r12d; dwOptions
0x140005a6b  call    cs:__imp_RegCreateKeyExW
0x140005a72  nop     dword ptr [rax+rax+00h]
0x140005a77  mov     r12d, eax
0x140005a7a  test    eax, eax
0x140005a7c  jnz     short loc_140005A82
0x140005a7e  mov     [rbp+47h+lpValueName], rsi
0x140005a82  mov     rcx, r14; hKey
0x140005a85  call    cs:__imp_RegCloseKey
0x140005a8c  nop     dword ptr [rax+rax+00h]
0x140005a91  test    r12d, r12d
0x140005a94  jz      short loc_140005ABC
0x140005a96  mov     ecx, r12d; dwErrCode
0x140005a99  call    cs:__imp_SetLastError
0x140005aa0  nop     dword ptr [rax+rax+00h]
0x140005aa5  call    cs:__imp_GetLastError
0x140005aac  nop     dword ptr [rax+rax+00h]
0x140005ab1  mov     r14d, eax
0x140005ab4  xor     r12d, r12d
0x140005ab7  jmp     loc_140005C05
0x140005abc  mov     rcx, [rbp+47h+hKey]; hKey
0x140005ac0  lea     rax, [rbp+47h+cbMaxValueLen]
0x140005ac4  xor     r12d, r12d
0x140005ac7  xor     r9d, r9d; lpReserved
0x140005aca  mov     [rsp+120h+lpftLastWriteTime], r12; lpftLastWriteTime
0x140005acf  xor     r8d, r8d; lpcchClass
0x140005ad2  mov     [rsp+120h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x140005ad7  xor     edx, edx; lpClass
0x140005ad9  mov     [rsp+120h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x140005ade  mov     [rsp+120h+lpdwDisposition], r12; lpcbMaxValueNameLen
0x140005ae3  mov     [rsp+120h+phkResult], r12; lpcValues
0x140005ae8  mov     [rsp+120h+lpSecurityAttributes], r12; lpcbMaxClassLen
0x140005aed  mov     qword ptr [rsp+120h+samDesired], r12; lpcbMaxSubKeyLen
0x140005af2  mov     qword ptr [rsp+120h+dwOptions], r12; lpcSubKeys
0x140005af7  mov     [rbp+47h+cbMaxValueLen], r12d
  ... truncated ...
```
