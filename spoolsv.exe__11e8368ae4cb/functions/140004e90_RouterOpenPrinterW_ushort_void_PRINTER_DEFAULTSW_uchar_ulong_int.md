# RouterOpenPrinterW(ushort *,void * *,_PRINTER_DEFAULTSW *,uchar *,ulong,int)

- ea: `0x140004e90`
- end: `0x140005898`
- name: `?RouterOpenPrinterW@@YAHPEAGPEAPEAXPEAU_PRINTER_DEFAULTSW@@PEAEKH@Z`
- size: `2568`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpValueName@<rcx>, void **@<rdx>, struct _PRINTER_DEFAULTSW *@<r8>, unsigned __int8 *@<r9>, unsigned int, int)`
- caller_count: `8`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140004220`
- `0x140004708`
- `0x140004890`
- `0x140004ae0`
- `0x140004ce0`
- `0x140004da0`
- `0x14005c820`
- `0x14005c8c0`

## callees

- `0x140002070`
- `0x140002b00`
- `0x140003c70`
- `0x140003ce0`
- `0x140003db4`
- `0x1400041c0`
- `0x140004e90`
- `0x1400058a0`
- `0x1400065f0`
- `0x14000a620`
- `0x14000ad50`
- `0x14000b460`
- `0x14000b5f0`
- `0x14000cd50`
- `0x14000d640`
- `0x14000e590`
- `0x140011d30`
- `0x140011ebc`
- `0x140011f1c`
- `0x140013fe8`
- `0x1400140cc`
- `0x140014eb0`
- `0x140014fc4`
- `0x140015000`
- `0x1400235dc`
- `0x140023860`
- `0x140056768`
- `0x140056b18`
- `0x14006c280`
- `0x14006c39c`
- `0x14007a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140005714`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140005714`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140004fcd`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140004fcd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140004f7f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140004f7f`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140004f32`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140004f32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005575`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000563f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400057ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005575`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000563f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400057ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000555d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000562a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005784`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000555d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000562a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005784`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400053b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005861`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400053b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005861`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005008`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004f40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004f5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004f9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400051e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400051fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000529f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000553b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400055b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400055bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400055f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000574c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400057b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005815`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005836`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004f40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004f5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004f9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400051e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400051fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000529f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005319`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000553b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400055b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400055bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400055f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000574c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400057b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005815`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005836`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004efa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000501b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400050d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005299`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400053dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400057fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004efa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000501b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400050d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005299`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400053dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400057fd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140005421`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140005421`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140004f75`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140005430`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140004f75`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140005430`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004f88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000543a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004f88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000543a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140005395`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140005395`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400052ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400052ef`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140005277`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140005277`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140005346`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140005346`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000528b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400053cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000528b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400053cf`

## string_xrefs

- `0x14000570d`: `win32spl.dll`
- `0x14000581e`: `Failed to open printer %ws. Error %d`
- `0x14000583f`: `Failed to open printer %ws. Error %d`
- `0x140005828`: `RouterOpenPrinterW`
- `0x140005849`: `RouterOpenPrinterW`
- `0x14000502e`: `DllAllocSplMem`
- `0x140004f49`: `Failed to create Phase2Init event.  Error %d.`
- `0x140004fc3`: `,NoCache`

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
0x140004e90  mov     [rsp-8+arg_10], r8
0x140004e95  mov     [rsp-8+arg_8], rdx
0x140004e9a  push    rbp
0x140004e9b  push    rbx
0x140004e9c  push    rdi
0x140004e9d  push    r12
0x140004e9f  push    r14
0x140004ea1  push    r15
0x140004ea3  lea     rbp, [rsp-1Fh]
0x140004ea8  sub     rsp, 0F8h
0x140004eaf  xor     r12d, r12d
0x140004eb2  mov     [rbp+47h+arg_0], 7Bh ; '{'
0x140004eb9  xor     eax, eax
0x140004ebb  mov     [rbp+47h+var_A8], r12
0x140004ebf  mov     [rbp+47h+var_40], rax
0x140004ec3  xorps   xmm0, xmm0
0x140004ec6  mov     r15, r9
0x140004ec9  mov     r14, r8
0x140004ecc  mov     rbx, rcx
0x140004ecf  movups  [rbp+47h+var_50], xmm0
0x140004ed3  test    rcx, rcx
0x140004ed6  jz      short loc_140004F07
0x140004ed8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140004edf  nop
0x140004ee0  inc     rax
0x140004ee3  cmp     [rcx+rax*2], r12w
0x140004ee8  jnz     short loc_140004EE0
0x140004eea  inc     rax
0x140004eed  cmp     rax, 21Bh
0x140004ef3  jbe     short loc_140004F07
0x140004ef5  mov     ecx, 709h; dwErrCode
0x140004efa  call    cs:__imp_SetLastError
0x140004f00  xor     eax, eax
0x140004f02  jmp     loc_140005887
0x140004f07  cmp     cs:?Initialized@@3HA, r12d; int Initialized
0x140004f0e  mov     [rsp+120h+arg_18], rsi
0x140004f16  jnz     loc_140004FBB
0x140004f1c  call    RevertToPrinterSelf
0x140004f21  lea     r8, Name; "RouterPreInitEvent"
0x140004f28  xor     edx, edx; bInheritHandle
0x140004f2a  mov     ecx, 2; dwDesiredAccess
0x140004f2f  mov     rsi, rax
0x140004f32  call    cs:__imp_OpenEventW
0x140004f38  mov     rdi, rax
0x140004f3b  test    rax, rax
0x140004f3e  jnz     short loc_140004F7C
0x140004f40  call    cs:__imp_GetLastError
0x140004f46  mov     r8d, eax
0x140004f49  lea     rdx, aFailedToCreate_3; "Failed to create Phase2Init event.  Err"...
0x140004f50  lea     rcx, aWaitforspooler; "WaitForSpoolerInitialization"
0x140004f57  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140004f5c  call    cs:__imp_GetLastError
0x140004f62  xor     r8d, r8d; unsigned __int16 *
0x140004f65  lea     rcx, MSG_ROUTER_PHASE2INIT_FAILED; struct _EVENT_DESCRIPTOR *
0x140004f6c  mov     edx, eax; unsigned int
0x140004f6e  call    ?SplLogRouterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBG@Z; SplLogRouterEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *)
0x140004f73  xor     ecx, ecx; uExitCode
0x140004f75  call    cs:__imp_ExitProcess
0x140004f7c  mov     rcx, rdi; hEvent
0x140004f7f  call    cs:__imp_SetEvent
0x140004f85  mov     rcx, rdi; hObject
0x140004f88  call    cs:__imp_CloseHandle
0x140004f8e  test    rsi, rsi
0x140004f91  jz      short loc_140004FB1
0x140004f93  mov     rcx, rsi; hToken
0x140004f96  call    ImpersonatePrinterClient
0x140004f9b  test    eax, eax
0x140004f9d  jnz     short loc_140004FB1
0x140004f9f  call    cs:__imp_GetLastError
0x140004fa5  mov     edx, eax; unsigned int
0x140004fa7  mov     ecx, 69h ; 'i'; unsigned int
0x140004fac  call    ?ForceProcessShutdown@@YAXKK@Z; ForceProcessShutdown(ulong,ulong)
0x140004fb1  mov     edx, 0FFFFFFFFh; struct NCoreLibrary::TAutoHandle *
0x140004fb6  call    ?WaitForAutoEventHandle@NCoreLibrary@@YAJPEAVTAutoHandle@1@K@Z; NCoreLibrary::WaitForAutoEventHandle(NCoreLibrary::TAutoHandle *,ulong)
0x140004fbb  mov     rsi, rbx
0x140004fbe  test    rbx, rbx
0x140004fc1  jz      short loc_140004FF6
0x140004fc3  lea     rdx, szNoCache; ",NoCache"
0x140004fca  mov     rcx, rbx; Str
0x140004fcd  call    cs:__imp_wcsstr
0x140004fd3  mov     rdi, rax
0x140004fd6  test    rax, rax
0x140004fd9  jz      short loc_140004FF6
0x140004fdb  mov     rcx, rbx; Src
0x140004fde  call    AllocSplStr
0x140004fe3  mov     rsi, rax
0x140004fe6  test    rax, rax
0x140004fe9  jz      short loc_140005047
0x140004feb  sub     rdi, rbx
0x140004fee  sar     rdi, 1
0x140004ff1  mov     [rax+rdi*2], r12w
0x140004ff6  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140004ffd  mov     edx, 8; dwFlags
0x140005002  mov     r8d, 68h ; 'h'; dwBytes
0x140005008  call    cs:__imp_HeapAlloc
0x14000500e  mov     rdi, rax
0x140005011  test    rax, rax
0x140005014  jnz     short loc_14000504E
0x140005016  mov     ecx, 8; dwErrCode
0x14000501b  call    cs:__imp_SetLastError
0x140005021  mov     r8d, 68h ; 'h'
0x140005027  lea     rdx, aUnableToAlloca; "Unable to allocate %d bytes of memory o"...
0x14000502e  lea     rcx, aDllallocsplmem; "DllAllocSplMem"
0x140005035  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000503a  cmp     rsi, rbx
0x14000503d  jz      short loc_140005047
0x14000503f  mov     rcx, rsi
0x140005042  call    DllFreeSplStr
0x140005047  xor     eax, eax
0x140005049  jmp     loc_14000587F
0x14000504e  mov     dword ptr [rax], 6060h
0x140005054  mov     qword ptr [rax+38h], 0FFFFFFFFFFFFFFFFh
0x14000505c  mov     [rax+40h], r12
0x140005060  mov     [rax+50h], r12
0x140005064  mov     [rax+58h], r12d
0x140005068  mov     [rax+60h], r12
0x14000506c  test    rsi, rsi
0x14000506f  jz      short loc_14000509E
0x140005071  mov     rcx, rsi; Src
0x140005074  call    AllocSplStr
0x140005079  mov     [rdi+48h], rax
0x14000507d  test    rax, rax
0x140005080  jnz     short loc_14000509E
0x140005082  cmp     rsi, rbx
0x140005085  jz      short loc_14000508F
0x140005087  mov     rcx, rsi
0x14000508a  call    DllFreeSplStr
0x14000508f  mov     rcx, rdi; struct _PRINTHANDLE *
0x140005092  call    ?FreePrinterHandle@@YAXPEAU_PRINTHANDLE@@@Z; FreePrinterHandle(_PRINTHANDLE *)
0x140005097  xor     eax, eax
0x140005099  jmp     loc_14000587F
0x14000509e  mov     [rsp+120h+var_30], r13
0x1400050a6  mov     r13, r12
0x1400050a9  test    r14, r14
0x1400050ac  jz      short loc_1400050B4
0x1400050ae  cmp     [r14+8], r12
0x1400050b2  jnz     short loc_1400050DD
0x1400050b4  call    CheckLocalCall
0x1400050b9  test    eax, eax
0x1400050bb  jnz     short loc_1400050DD
0x1400050bd  mov     rcx, rsi; lpValueName
0x1400050c0  call    LPatchUserDevmodes
0x1400050c5  mov     [rbp+47h+hKey], r12
0x1400050c9  test    rsi, rsi
0x1400050cc  jnz     loc_14000516F
0x1400050d2  mov     ecx, 6; dwErrCode
0x1400050d7  call    cs:__imp_SetLastError
0x1400050dd  mov     rdx, [rbp+47h+arg_10]
0x1400050e1  mov     r12d, [rbp+47h+arg_20]
0x1400050e5  xorps   xmm0, xmm0
0x1400050e8  movups  xmmword ptr [rbp+47h+var_90], xmm0
0x1400050ec  movups  [rbp+47h+var_80], xmm0
0x1400050f0  movups  [rbp+47h+var_70], xmm0
0x1400050f4  movups  [rbp+47h+var_60], xmm0
0x1400050f8  cmp     r12d, 4
0x1400050fc  jnz     loc_14000547A
0x140005102  mov     eax, [r15+30h]
0x140005106  mov     [rdi+54h], eax
0x140005109  mov     eax, [r15+34h]
0x14000510d  mov     [rdi+58h], eax
0x140005110  mov     eax, [r15]
0x140005113  mov     dword ptr [rbp+47h+var_90+4], eax
0x140005116  mov     rax, [r15+8]
0x14000511a  mov     qword ptr [rbp+47h+var_80], rax
0x14000511e  mov     rax, [r15+10h]
0x140005122  mov     qword ptr [rbp+47h+var_80+8], rax
0x140005126  mov     eax, [r15+18h]
0x14000512a  mov     dword ptr [rbp+47h+var_70], eax
0x14000512d  mov     eax, [r15+1Ch]
0x140005131  mov     dword ptr [rbp+47h+var_70+4], eax
0x140005134  mov     eax, [r15+20h]
0x140005138  mov     dword ptr [rbp+47h+var_70+8], eax
0x14000513b  movzx   eax, word ptr [r15+24h]
0x140005140  mov     word ptr [rbp+47h+var_70+0Ch], ax
0x140005144  mov     rax, [r15+28h]
0x140005148  lea     r15, [rbp+47h+var_90]
0x14000514c  mov     qword ptr [rbp+47h+var_60], rax
0x140005150  mov     dword ptr [rbp+47h+var_90], 38h ; '8'
0x140005157  mov     dword ptr [rbp+47h+var_90+8], 28h ; '('
0x14000515e  mov     eax, [rdi+54h]
0x140005161  mov     dword ptr [rbp+47h+var_60+8], eax
0x140005164  mov     eax, [rdi+58h]
0x140005167  mov     dword ptr [rbp+47h+var_60+0Ch], eax
0x14000516a  jmp     loc_1400054E5
0x14000516f  mov     [rbp+47h+Token], 0FFFFFFFFFFFFFFFFh
0x140005177  mov     [rbp+47h+var_98], r12b
0x14000517b  mov     [rbp+47h+cbMaxValueLen], r12d
0x14000517f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x140005186  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x14000518b  test    al, al
0x14000518d  jz      short loc_1400051AC
0x14000518f  call    ?IsCurrentProcess@ProcessUtils@@YA_NPEBG@Z; ProcessUtils::IsCurrentProcess(ushort const *)
0x140005194  lea     rdx, [rbp+47h+cbMaxValueLen]; void **
0x140005198  lea     rcx, [rbp+47h+Token]; this
0x14000519c  test    al, al
0x14000519e  jz      short loc_1400051B4
0x1400051a0  call    ?ElevateIntegrityLevelIfLowViaBroker@NSecurityLibrary@@YAJPEAPEAXPEAH@Z; NSecurityLibrary::ElevateIntegrityLevelIfLowViaBroker(void * *,int *)
0x1400051a5  not     eax
0x1400051a7  shr     eax, 1Fh
0x1400051aa  jmp     short loc_1400051B9
0x1400051ac  lea     rdx, [rbp+47h+cbMaxValueLen]; void **
0x1400051b0  lea     rcx, [rbp+47h+Token]; this
0x1400051b4  call    ?ElevateIntegrityLevelIfLowDirectly@NSecurityLibrary@@YAHPEAPEAXPEAH@Z; NSecurityLibrary::ElevateIntegrityLevelIfLowDirectly(void * *,int *)
0x1400051b9  test    eax, eax
0x1400051bb  jz      short loc_1400051C7
0x1400051bd  cmp     [rbp+47h+cbMaxValueLen], r12d
0x1400051c1  jz      short loc_1400051C7
0x1400051c3  mov     [rbp+47h+var_98], 1
0x1400051c7  mov     ecx, 2001Fh
0x1400051cc  mov     [rbp+47h+hKey], r12
0x1400051d0  mov     [rbp+47h+lpValueName], r12
0x1400051d4  call    SplGetClientUserHandle
0x1400051d9  mov     r14, rax
0x1400051dc  test    rax, rax
0x1400051df  jnz     short loc_1400051F9
0x1400051e1  call    cs:__imp_GetLastError
0x1400051e7  cmp     eax, 5
0x1400051ea  jnz     short loc_1400051FE
0x1400051ec  mov     ecx, 20019h
0x1400051f1  call    SplGetClientUserHandle
0x1400051f6  mov     r14, rax
0x1400051f9  test    r14, r14
0x1400051fc  jnz     short loc_14000520C
0x1400051fe  call    cs:__imp_GetLastError
0x140005204  mov     r12d, eax
0x140005207  jmp     loc_140005291
0x14000520c  cmp     word ptr [rsi], 5Ch ; '\'
0x140005210  jnz     short loc_14000523F
0x140005212  cmp     word ptr [rsi+2], 5Ch ; '\'
0x140005217  jnz     short loc_14000523F
0x140005219  lea     r8, [rbp+47h+hKey]; phkResult
0x14000521d  mov     rdx, rsi; unsigned __int16 *
0x140005220  mov     rcx, r14; hKey
0x140005223  call    ?RegOpenConnectionKey@@YAKPEAUHKEY__@@PEAGPEAPEAU1@@Z; RegOpenConnectionKey(HKEY__ *,ushort *,HKEY__ * *)
0x140005228  mov     r12d, eax
0x14000522b  test    eax, eax
0x14000522d  jnz     short loc_14000523C
0x14000522f  lea     rax, gszDevMode; "DevMode"
0x140005236  mov     [rbp+47h+lpValueName], rax
0x14000523a  jmp     short loc_140005288
0x14000523c  xor     r12d, r12d
0x14000523f  lea     rax, [rbp+47h+dwDisposition]
0x140005243  mov     [rbp+47h+dwDisposition], r12d
0x140005247  mov     [rsp+120h+lpdwDisposition], rax; lpdwDisposition
0x14000524c  lea     rdx, gszDevModePerUserLocal; "Printers\\DevModePerUser"
0x140005253  lea     rax, [rbp+47h+hKey]
0x140005257  xor     r9d, r9d; lpClass
0x14000525a  mov     [rsp+120h+phkResult], rax; phkResult
0x14000525f  xor     r8d, r8d; Reserved
0x140005262  mov     [rsp+120h+lpSecurityAttributes], r12; lpSecurityAttributes
0x140005267  mov     rcx, r14; hKey
0x14000526a  mov     [rsp+120h+samDesired], 2001Fh; samDesired
0x140005272  mov     [rsp+120h+dwOptions], r12d; dwOptions
0x140005277  call    cs:__imp_RegCreateKeyExW
0x14000527d  mov     r12d, eax
0x140005280  test    eax, eax
0x140005282  jnz     short loc_140005288
0x140005284  mov     [rbp+47h+lpValueName], rsi
0x140005288  mov     rcx, r14; hKey
0x14000528b  call    cs:__imp_RegCloseKey
0x140005291  test    r12d, r12d
0x140005294  jz      short loc_1400052B0
0x140005296  mov     ecx, r12d; dwErrCode
0x140005299  call    cs:__imp_SetLastError
0x14000529f  call    cs:__imp_GetLastError
0x1400052a5  mov     r14d, eax
0x1400052a8  xor     r12d, r12d
0x1400052ab  jmp     loc_1400053D5
0x1400052b0  mov     rcx, [rbp+47h+hKey]; hKey
0x1400052b4  lea     rax, [rbp+47h+cbMaxValueLen]
0x1400052b8  xor     r12d, r12d
0x1400052bb  xor     r9d, r9d; lpReserved
0x1400052be  mov     [rsp+120h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1400052c3  xor     r8d, r8d; lpcchClass
0x1400052c6  mov     [rsp+120h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1400052cb  xor     edx, edx; lpClass
0x1400052cd  mov     [rsp+120h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1400052d2  mov     [rsp+120h+lpdwDisposition], r12; lpcbMaxValueNameLen
0x1400052d7  mov     [rsp+120h+phkResult], r12; lpcValues
0x1400052dc  mov     [rsp+120h+lpSecurityAttributes], r12; lpcbMaxClassLen
0x1400052e1  mov     qword ptr [rsp+120h+samDesired], r12; lpcbMaxSubKeyLen
0x1400052e6  mov     qword ptr [rsp+120h+dwOptions], r12; lpcSubKeys
0x1400052eb  mov     [rbp+47h+cbMaxValueLen], r12d
0x1400052ef  call    cs:__imp_RegQueryInfoKeyW
0x1400052f5  mov     r14d, eax
0x1400052f8  test    eax, eax
0x1400052fa  jnz     loc_1400053CB
0x140005300  mov     ecx, [rbp+47h+cbMaxValueLen]; dwBytes
0x140005303  cmp     ecx, 48h ; 'H'
0x140005306  jb      loc_1400053CB
0x14000530c  call    DllAllocSplMem
0x140005311  mov     r13, rax
0x140005314  test    rax, rax
0x140005317  jnz     short loc_140005327
0x140005319  call    cs:__imp_GetLastError
0x14000531f  mov     r14d, eax
0x140005322  jmp     loc_1400053CB
0x140005327  mov     r12, [rbp+47h+lpValueName]
0x14000532b  lea     rax, [rbp+47h+cbMaxValueLen]
0x14000532f  mov     rcx, [rbp+47h+hKey]; hKey
  ... truncated ...
```
