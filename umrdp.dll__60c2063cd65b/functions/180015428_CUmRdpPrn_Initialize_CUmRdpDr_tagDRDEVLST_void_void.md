# CUmRdpPrn::Initialize(CUmRdpDr *,tagDRDEVLST *,void *,void *)

- ea: `0x180015428`
- end: `0x180015cd1`
- name: `?Initialize@CUmRdpPrn@@QEAAHPEAVCUmRdpDr@@PEAUtagDRDEVLST@@PEAX2@Z`
- size: `2217`
- prototype: `__int64 __usercall@<rax>(CUmRdpPrn *__hidden this@<rcx>, struct CUmRdpDr *@<rdx>, struct tagDRDEVLST *@<r8>, void *@<r9>, void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180011850`

## callees

- `0x18000ae30`
- `0x18000b8f8`
- `0x18000f75c`
- `0x18000f79c`
- `0x180012be8`
- `0x1800134cc`
- `0x180014570`
- `0x180015428`
- `0x1800161e8`
- `0x1800164c8`
- `0x1800165c8`
- `0x1800169a0`
- `0x180017400`
- `0x180017d14`
- `0x1800197e8`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001560f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001592f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015adf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001560f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001592f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015adf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800154bb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800154bb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015c9b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015c9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001594e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015969`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001594e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015969`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015b9e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015b9e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180015566`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180015566`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800154e4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800154e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015bf3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015c1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015c43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015c6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015bf3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015c1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015c43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015c6e`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18001565e`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18001565e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001581c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001581c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015860`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015860`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800158d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015c8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800158d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015c8a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800158e7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800158e7`
- `WINSPOOL!OpenPrinterW` at `0x180015559`
- `WINSPOOL!OpenPrinterW` at `0x180015559`
- `WINSPOOL!ClosePrinter` at `0x1800157ae`
- `WINSPOOL!ClosePrinter` at `0x180015bce`
- `WINSPOOL!ClosePrinter` at `0x1800157ae`
- `WINSPOOL!ClosePrinter` at `0x180015bce`
- `WINSPOOL!FindFirstPrinterChangeNotification` at `0x180015702`
- `WINSPOOL!FindFirstPrinterChangeNotification` at `0x180015702`

## string_xrefs

- `0x1800158e0`: `printui.dll`

## pseudocode

```c
__int64 __fastcall CUmRdpPrn::Initialize(
        CUmRdpPrn *this,
        struct CUmRdpDr *a2,
        struct tagDRDEVLST *a3,
        void *a4,
        HANDLE hToken)
{
  int v5; // r14d
  BOOL v6; // r15d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v12; // eax
  __int64 v13; // r8
  HANDLE *v14; // r12
  unsigned int v15; // esi
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // r8
  CUmRdpDr *v19; // rcx
  HANDLE WaitableTimerW; // rax
  void *v21; // rax
  HANDLE v22; // rax
  unsigned int v23; // eax
  unsigned int v24; // eax
  HANDLE v25; // rcx
  unsigned int v26; // eax
  __int64 v27; // r8
  HKEY v28; // rcx
  unsigned int v29; // eax
  __int64 v30; // r8
  HMODULE LibraryW; // rax
  unsigned int v32; // eax
  __int64 v33; // r8
  __int64 v34; // rdx
  FARPROC ProcAddress; // rax
  HMODULE v36; // rcx
  FARPROC v37; // rax
  bool v38; // zf
  int v39; // ebx
  unsigned int v40; // eax
  unsigned int v41; // eax
  __int64 v42; // r8
  LPVOID *v43; // rbx
  unsigned int v44; // r9d
  unsigned int v45; // eax
  HMODULE v46; // rcx
  HANDLE v47; // rcx
  void *v48; // r8
  void *v49; // r8
  void *v50; // r8
  HKEY v51; // rcx
  DWORD cbData; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-30h] BYREF
  struct _EVENT_DESCRIPTOR v55; // [rsp+40h] [rbp-28h] BYREF

  hKey = 0;
  v5 = 0;
  cbData = 0;
  v55 = 0;
  v6 = 0;
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      18,
      WPP_efc62aea55d5318435cc8fa94ffbd72c_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  *(_QWORD *)this = a2;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  *((_QWORD *)this + 12) = (char *)this + 88;
  *((_QWORD *)this + 11) = (char *)this + 88;
  *((_QWORD *)this + 5) = a3;
  *((_QWORD *)this + 15) = a4;
  *((_QWORD *)this + 23) = hToken;
  if ( hToken )
  {
    v6 = ImpersonateLoggedOnUser(hToken);
    if ( !v6
      && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      GetLastError();
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dl(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 19, v13, v12);
    }
    *((_DWORD *)this + 212) = ServerHasExistingQueues(*((void **)this + 23));
  }
  v14 = (HANDLE *)((char *)this + 192);
  v15 = OpenPrinterW(0, (LPHANDLE)this + 24, 0);
  if ( !v6 || RevertToSelf() )
  {
    if ( v15 )
      goto LABEL_25;
  }
  else
  {
    v15 = 0;
  }
  if ( (unsigned int)IsSpoolerEnabled() )
  {
    v5 = 1;
    v55 = (struct _EVENT_DESCRIPTOR)EVENT_NOTIFY_SPOOLERERROR;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      GetLastError();
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dl(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 21, v18, v17);
    }
  }
  else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
         && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 3u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      20,
      WPP_efc62aea55d5318435cc8fa94ffbd72c_Traceguids,
      v16);
  }
LABEL_25:
  CUmRdpPrn::LoadConfigurableValues(this);
  if ( !v15 )
    goto LABEL_81;
  WaitableTimerW = CreateWaitableTimerW(0, 1, 0);
  *((_QWORD *)this + 27) = WaitableTimerW;
  if ( !WaitableTimerW )
  {
    v5 = 1;
    v55 = EVENT_NOTIFY_INSUFFICIENTRESOURCES;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      GetLastError();
      v41 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dl(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 22, v42, v41);
    }
    goto LABEL_80;
  }
  if ( WTBLOBJ_AddWaitableObject(
         *((void **)this + 15),
         this,
         WaitableTimerW,
         (void (*)(void *, void *))CUmRdpPrn::staticWaitableTimerSignaled) )
  {
    v5 = 1;
    v15 = 0;
    v55 = EVENT_NOTIFY_INSUFFICIENTRESOURCES;
  }
  if ( !v15 )
    goto LABEL_81;
  v21 = CUmRdpPrn::RegisterForPrinterPrefNotify(this);
  *((_QWORD *)this + 19) = v21;
  if ( !v21 )
  {
LABEL_80:
    v15 = 0;
    goto LABEL_81;
  }
  if ( WTBLOBJ_AddWaitableObject(
         *((void **)this + 15),
         this,
         v21,
         (void (*)(void *, void *))CUmRdpPrn::staticPrintPreferenceChangeEventSignaled) )
  {
    v5 = 1;
    v15 = 0;
    v55 = EVENT_NOTIFY_INSUFFICIENTRESOURCES;
  }
  if ( !v15 )
    goto LABEL_81;
  v22 = FindFirstPrinterChangeNotification(*v14, 0, 0, (char *)this + 264);
  *((_QWORD *)this + 18) = v22;
  if ( v22 == (HANDLE)-1LL )
  {
    if ( (unsigned int)IsSpoolerEnabled() )
    {
      GetLastError();
      v25 = *v14;
      v5 = 1;
      v55 = (struct _EVENT_DESCRIPTOR)EVENT_NOTIFY_SPOOLERERROR;
      ClosePrinter(v25);
      *v14 = 0;
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v26 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dl(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 24, v27, v26);
      }
    }
    else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
           && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 3u )
    {
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        23,
        WPP_efc62aea55d5318435cc8fa94ffbd72c_Traceguids,
        v24);
    }
  }
  else
  {
    v23 = WTBLOBJ_AddWaitableObject(
            *((void **)this + 15),
            this,
            v22,
            (void (*)(void *, void *))CUmRdpPrn::staticGlobalPrintNotifyObjectSignaled);
    v15 = v23 == 0;
    if ( v23 )
      goto LABEL_81;
  }
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", 0, 0x20019u, &hKey) )
  {
    v15 = 0;
    v5 = 1;
    v55 = (struct _EVENT_DESCRIPTOR)EVENT_NOTIFY_INTERNALERROR;
    v19 = (CUmRdpDr *)&WPP_GLOBAL_Control;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v32 = RdpWppGetCurrentThreadActivityIdPrefix();
      v34 = 26;
      goto LABEL_71;
    }
    goto LABEL_81;
  }
  v28 = hKey;
  *((_WORD *)this + 404) = 0;
  cbData = 260;
  if ( RegQueryValueExW(v28, L"SystemRoot", 0, 0, (LPBYTE)this + 288, &cbData) )
  {
    v15 = 0;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v29 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dl(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 25, v30, v29);
    }
  }
  else
  {
    v15 = 1;
    StringCchCatW((unsigned __int16 *)this + 144, 0x117u, L"\\inf\\ntprint.inf");
  }
  RegCloseKey(hKey);
  if ( !v15 )
    goto LABEL_81;
  LibraryW = LoadLibraryW(L"printui.dll");
  *((_QWORD *)this + 20) = LibraryW;
  if ( !LibraryW )
  {
    v15 = 0;
    v5 = 1;
    v55 = (struct _EVENT_DESCRIPTOR)EVENT_NOTIFY_INTERNALERROR;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      GetLastError();
      v32 = RdpWppGetCurrentThreadActivityIdPrefix();
      v34 = 27;
LABEL_71:
      WPP_SF_Dl(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), v34, v33, v32);
      goto LABEL_81;
    }
    goto LABEL_81;
  }
  ProcAddress = GetProcAddress(LibraryW, "PrintUIEntryW");
  v36 = (HMODULE)*((_QWORD *)this + 20);
  *((_QWORD *)this + 21) = ProcAddress;
  v37 = GetProcAddress(v36, "PnPInterface");
  v38 = *((_QWORD *)this + 21) == 0;
  *((_QWORD *)this + 22) = v37;
  if ( !v38 && v37 )
  {
    v15 = 1;
    v39 = CUmRdpPrn::InstallTSPrintDriver(this);
    v19 = (CUmRdpDr *)(v39 == 0);
    *((_DWORD *)this + 8) = (_DWORD)v19;
    if ( !v39 || *((_DWORD *)this + 5) != 1 )
      goto LABEL_81;
    v5 = 1;
    v55 = (struct _EVENT_DESCRIPTOR)EVENT_NOTIFY_INTERNALERROR;
    v19 = (CUmRdpDr *)&WPP_GLOBAL_Control;
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v40 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        29,
        WPP_efc62aea55d5318435cc8fa94ffbd72c_Traceguids,
        v40,
        v39);
    }
    goto LABEL_80;
  }
  v15 = 0;
  v55 = (struct _EVENT_DESCRIPTOR)EVENT_NOTIFY_INTERNALERROR;
  v5 = 1;
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    GetLastError();
    v32 = RdpWppGetCurrentThreadActivityIdPrefix();
    v34 = 28;
    goto LABEL_71;
  }
LABEL_81:
  v43 = (LPVOID *)((char *)this + 248);
  CUmRdpDr::ResizeBuffer(v19, (void **)this + 31, 0x208u, (unsigned int *)this + 64);
  if ( v15 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      v45 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        30,
        WPP_efc62aea55d5318435cc8fa94ffbd72c_Traceguids,
        v45);
    }
    *((_DWORD *)this + 7) = 1;
  }
  else
  {
    if ( v5 )
      TsLogError(&v55, 0, 0, v44);
    v46 = (HMODULE)*((_QWORD *)this + 20);
    if ( v46 )
    {
      FreeLibrary(v46);
      *((_QWORD *)this + 20) = 0;
    }
    *((_QWORD *)this + 21) = 0;
    *((_QWORD *)this + 22) = 0;
    CUmRdpPrn::CloseWaitablePrintingObjects(this);
    v47 = *v14;
    *((_QWORD *)this + 15) = 0;
    if ( v47 )
    {
      ClosePrinter(v47);
      *v14 = 0;
    }
    v48 = (void *)*((_QWORD *)this + 29);
    if ( v48 )
    {
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, v48);
      *((_QWORD *)this + 29) = 0;
    }
    v49 = (void *)*((_QWORD *)this + 30);
    if ( v49 )
    {
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, v49);
      *((_QWORD *)this + 30) = 0;
    }
    v50 = (void *)*((_QWORD *)this + 25);
    if ( v50 )
    {
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, v50);
      *((_QWORD *)this + 25) = 0;
      *((_DWORD *)this + 52) = 0;
    }
    if ( *v43 )
    {
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, *v43);
      *v43 = 0;
      *((_DWORD *)this + 64) = 0;
    }
    v51 = (HKEY)*((_QWORD *)this + 16);
    if ( v51 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      RegCloseKey(v51);
      *((_QWORD *)this + 16) = -1;
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    *((_QWORD *)this + 23) = -1;
  }
  *((_DWORD *)this + 212) = 1;
  return v15;
}

```

## disassembly

```asm
0x180015428  push    rbp
0x18001542a  push    rbx
0x18001542b  push    rsi
0x18001542c  push    rdi
0x18001542d  push    r12
0x18001542f  push    r13
0x180015431  push    r14
0x180015433  push    r15
0x180015435  mov     rbp, rsp
0x180015438  sub     rsp, 68h
0x18001543c  mov     rax, cs:__security_cookie
0x180015443  xor     rax, rsp
0x180015446  mov     [rbp+var_18], rax
0x18001544a  xorps   xmm0, xmm0
0x18001544d  mov     [rbp+hKey], 0
0x180015455  xor     r14d, r14d
0x180015458  mov     [rbp+cbData], 0
0x18001545f  movups  xmmword ptr [rbp+var_28.Id], xmm0
0x180015463  xor     r15d, r15d
0x180015466  mov     rbx, r9
0x180015469  mov     rsi, r8
0x18001546c  mov     r12, rdx
0x18001546f  mov     rdi, rcx
0x180015472  mov     rax, cs:WPP_GLOBAL_Control
0x180015479  lea     rcx, WPP_GLOBAL_Control
0x180015480  cmp     rax, rcx
0x180015483  jz      short loc_1800154B4
0x180015485  test    byte ptr [rax+1Ch], 1
0x180015489  jz      short loc_1800154B4
0x18001548b  cmp     byte ptr [rax+19h], 4
0x18001548f  jb      short loc_1800154B4
0x180015491  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180015496  mov     rcx, cs:WPP_GLOBAL_Control
0x18001549d  lea     edx, [r14+12h]
0x1800154a1  mov     r9d, eax
0x1800154a4  lea     r8, WPP_efc62aea55d5318435cc8fa94ffbd72c_Traceguids
0x1800154ab  mov     rcx, [rcx+10h]
0x1800154af  call    WPP_SF_D
0x1800154b4  lea     rcx, [rdi+30h]; lpCriticalSection
0x1800154b8  mov     [rdi], r12
0x1800154bb  call    cs:__imp_InitializeCriticalSection
0x1800154c1  mov     rcx, [rbp+hToken]; hToken
0x1800154c5  lea     rax, [rdi+58h]
0x1800154c9  mov     [rdi+60h], rax
0x1800154cd  mov     [rax], rax
0x1800154d0  mov     [rdi+28h], rsi
0x1800154d4  mov     [rdi+78h], rbx
0x1800154d8  mov     [rdi+0B8h], rcx
0x1800154df  test    rcx, rcx
0x1800154e2  jz      short loc_18001554A
0x1800154e4  call    cs:__imp_ImpersonateLoggedOnUser
0x1800154ea  mov     r15d, eax
0x1800154ed  test    eax, eax
0x1800154ef  jnz     short loc_180015538
0x1800154f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800154f8  lea     rax, WPP_GLOBAL_Control
0x1800154ff  cmp     rcx, rax
0x180015502  jz      short loc_180015538
0x180015504  test    byte ptr [rcx+1Ch], 1
0x180015508  jz      short loc_180015538
0x18001550a  cmp     byte ptr [rcx+19h], 2
0x18001550e  jb      short loc_180015538
0x180015510  call    cs:__imp_GetLastError
0x180015516  mov     ebx, eax
0x180015518  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001551d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015524  lea     edx, [r15+13h]
0x180015528  mov     r9d, eax
0x18001552b  mov     dword ptr [rsp+68h+phkResult], ebx
0x18001552f  mov     rcx, [rcx+10h]
0x180015533  call    WPP_SF_Dl
0x180015538  mov     rcx, [rdi+0B8h]; void *
0x18001553f  call    ?ServerHasExistingQueues@@YAHPEAX@Z; ServerHasExistingQueues(void *)
0x180015544  mov     [rdi+350h], eax
0x18001554a  lea     r12, [rdi+0C0h]
0x180015551  xor     r8d, r8d; pDefault
0x180015554  mov     rdx, r12; phPrinter
0x180015557  xor     ecx, ecx; pPrinterName
0x180015559  call    cs:__imp_OpenPrinterW
0x18001555f  mov     esi, eax
0x180015561  test    r15d, r15d
0x180015564  jz      short loc_180015574
0x180015566  call    cs:__imp_RevertToSelf
0x18001556c  test    eax, eax
0x18001556e  jnz     short loc_180015574
0x180015570  xor     esi, esi
0x180015572  jmp     short loc_18001557C
0x180015574  test    esi, esi
0x180015576  jnz     loc_180015639
0x18001557c  call    ?IsSpoolerEnabled@@YAHXZ; IsSpoolerEnabled(void)
0x180015581  test    eax, eax
0x180015583  jnz     short loc_1800155DB
0x180015585  mov     rax, cs:WPP_GLOBAL_Control
0x18001558c  lea     rbx, WPP_GLOBAL_Control
0x180015593  mov     r15d, 1
0x180015599  cmp     rax, rbx
0x18001559c  jz      loc_180015646
0x1800155a2  test    [rax+1Ch], r15b
0x1800155a6  jz      loc_180015646
0x1800155ac  cmp     byte ptr [rax+19h], 3
0x1800155b0  jb      loc_180015646
0x1800155b6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800155bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800155c2  lea     edx, [r15+13h]
0x1800155c6  mov     r9d, eax
0x1800155c9  lea     r8, WPP_efc62aea55d5318435cc8fa94ffbd72c_Traceguids
0x1800155d0  mov     rcx, [rcx+10h]
0x1800155d4  call    WPP_SF_D
0x1800155d9  jmp     short loc_180015646
0x1800155db  movups  xmm0, cs:EVENT_NOTIFY_SPOOLERERROR
0x1800155e2  mov     r15d, 1
0x1800155e8  mov     r14d, r15d
0x1800155eb  movdqu  xmmword ptr [rbp+var_28.Id], xmm0
0x1800155f0  mov     rax, cs:WPP_GLOBAL_Control
0x1800155f7  lea     rbx, WPP_GLOBAL_Control
0x1800155fe  cmp     rax, rbx
0x180015601  jz      short loc_180015646
0x180015603  test    [rax+1Ch], r15b
0x180015607  jz      short loc_180015646
0x180015609  cmp     byte ptr [rax+19h], 2
0x18001560d  jb      short loc_180015646
0x18001560f  call    cs:__imp_GetLastError
0x180015615  mov     ebx, eax
0x180015617  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001561c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015623  lea     edx, [r15+14h]
0x180015627  mov     r9d, eax
0x18001562a  mov     dword ptr [rsp+68h+phkResult], ebx
0x18001562e  mov     rcx, [rcx+10h]
0x180015632  call    WPP_SF_Dl
0x180015637  jmp     short loc_18001563F
0x180015639  mov     r15d, 1
0x18001563f  lea     rbx, WPP_GLOBAL_Control
0x180015646  mov     rcx, rdi; this
0x180015649  call    ?LoadConfigurableValues@CUmRdpPrn@@AEAAXXZ; CUmRdpPrn::LoadConfigurableValues(void)
0x18001564e  test    esi, esi
0x180015650  jz      loc_180015B0A
0x180015656  xor     r8d, r8d; lpTimerName
0x180015659  mov     edx, r15d; bManualReset
0x18001565c  xor     ecx, ecx; lpTimerAttributes
0x18001565e  call    cs:__imp_CreateWaitableTimerW
0x180015664  mov     [rdi+0D8h], rax
0x18001566b  test    rax, rax
0x18001566e  jz      loc_180015AB8
0x180015674  mov     rcx, [rdi+78h]; void *
0x180015678  lea     r9, ?staticWaitableTimerSignaled@CUmRdpPrn@@CAXPEAX0@Z; void (*)(void *, void *)
0x18001567f  mov     r8, rax; void *
0x180015682  mov     rdx, rdi; void *
0x180015685  call    ?WTBLOBJ_AddWaitableObject@@YAKPEAX00P6AX00@Z@Z; WTBLOBJ_AddWaitableObject(void *,void *,void *,void (*)(void *,void *))
0x18001568a  test    eax, eax
0x18001568c  jz      short loc_18001569F
0x18001568e  movups  xmm0, xmmword ptr cs:EVENT_NOTIFY_INSUFFICIENTRESOURCES.Id
0x180015695  mov     r14d, r15d
0x180015698  xor     esi, esi
0x18001569a  movdqu  xmmword ptr [rbp+var_28.Id], xmm0
0x18001569f  test    esi, esi
0x1800156a1  jz      loc_180015B0A
0x1800156a7  mov     rcx, rdi; this
0x1800156aa  call    ?RegisterForPrinterPrefNotify@CUmRdpPrn@@AEAAPEAXXZ; CUmRdpPrn::RegisterForPrinterPrefNotify(void)
0x1800156af  mov     [rdi+98h], rax
0x1800156b6  test    rax, rax
0x1800156b9  jz      loc_180015B08
0x1800156bf  mov     rcx, [rdi+78h]; void *
0x1800156c3  lea     r9, ?staticPrintPreferenceChangeEventSignaled@CUmRdpPrn@@CAXPEAX0@Z; void (*)(void *, void *)
0x1800156ca  mov     r8, rax; void *
0x1800156cd  mov     rdx, rdi; void *
0x1800156d0  call    ?WTBLOBJ_AddWaitableObject@@YAKPEAX00P6AX00@Z@Z; WTBLOBJ_AddWaitableObject(void *,void *,void *,void (*)(void *,void *))
0x1800156d5  test    eax, eax
0x1800156d7  jz      short loc_1800156EA
0x1800156d9  movups  xmm0, xmmword ptr cs:EVENT_NOTIFY_INSUFFICIENTRESOURCES.Id
0x1800156e0  mov     r14d, r15d
0x1800156e3  xor     esi, esi
0x1800156e5  movdqu  xmmword ptr [rbp+var_28.Id], xmm0
0x1800156ea  test    esi, esi
0x1800156ec  jz      loc_180015B0A
0x1800156f2  mov     rcx, [r12]; hPrinter
0x1800156f6  lea     r9, [rdi+108h]; pPrinterNotifyOptions
0x1800156fd  xor     r8d, r8d; fdwOptions
0x180015700  xor     edx, edx; fdwFilter
0x180015702  call    cs:__imp_FindFirstPrinterChangeNotification
0x180015708  mov     [rdi+90h], rax
0x18001570f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015713  jz      short loc_180015740
0x180015715  mov     rcx, [rdi+78h]; void *
0x180015719  lea     r9, ?staticGlobalPrintNotifyObjectSignaled@CUmRdpPrn@@CAXPEAX0@Z; void (*)(void *, void *)
0x180015720  mov     r8, rax; void *
0x180015723  mov     rdx, rdi; void *
0x180015726  call    ?WTBLOBJ_AddWaitableObject@@YAKPEAX00P6AX00@Z@Z; WTBLOBJ_AddWaitableObject(void *,void *,void *,void (*)(void *,void *))
0x18001572b  xor     esi, esi
0x18001572d  test    eax, eax
0x18001572f  setz    sil
0x180015733  test    eax, eax
0x180015735  jz      loc_1800157FC
0x18001573b  jmp     loc_180015B0A
0x180015740  call    ?IsSpoolerEnabled@@YAHXZ; IsSpoolerEnabled(void)
0x180015745  test    eax, eax
0x180015747  jnz     short loc_180015793
0x180015749  mov     rax, cs:WPP_GLOBAL_Control
0x180015750  cmp     rax, rbx
0x180015753  jz      loc_1800157FC
0x180015759  test    [rax+1Ch], r15b
0x18001575d  jz      loc_1800157FC
0x180015763  cmp     byte ptr [rax+19h], 3
0x180015767  jb      loc_1800157FC
0x18001576d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180015772  mov     rcx, cs:WPP_GLOBAL_Control
0x180015779  lea     r8, WPP_efc62aea55d5318435cc8fa94ffbd72c_Traceguids
0x180015780  mov     edx, 17h
0x180015785  mov     r9d, eax
0x180015788  mov     rcx, [rcx+10h]
0x18001578c  call    WPP_SF_D
0x180015791  jmp     short loc_1800157FC
0x180015793  call    cs:__imp_GetLastError
0x180015799  movups  xmm0, cs:EVENT_NOTIFY_SPOOLERERROR
0x1800157a0  mov     rcx, [r12]; hPrinter
0x1800157a4  mov     ebx, eax
0x1800157a6  mov     r14d, r15d
0x1800157a9  movdqu  xmmword ptr [rbp+var_28.Id], xmm0
0x1800157ae  call    cs:__imp_ClosePrinter
0x1800157b4  mov     qword ptr [r12], 0
0x1800157bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800157c3  lea     rax, WPP_GLOBAL_Control
0x1800157ca  cmp     rcx, rax
0x1800157cd  jz      short loc_1800157FC
0x1800157cf  test    [rcx+1Ch], r15b
0x1800157d3  jz      short loc_1800157FC
0x1800157d5  cmp     byte ptr [rcx+19h], 2
0x1800157d9  jb      short loc_1800157FC
0x1800157db  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800157e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800157e7  mov     edx, 18h
0x1800157ec  mov     r9d, eax
0x1800157ef  mov     dword ptr [rsp+68h+phkResult], ebx
0x1800157f3  mov     rcx, [rcx+10h]
0x1800157f7  call    WPP_SF_Dl
0x1800157fc  lea     rax, [rbp+hKey]
0x180015800  mov     r9d, 20019h; samDesired
0x180015806  xor     r8d, r8d; ulOptions
0x180015809  mov     [rsp+68h+phkResult], rax; phkResult
0x18001580e  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180015815  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001581c  call    cs:__imp_RegOpenKeyExW
0x180015822  mov     ebx, eax
0x180015824  test    eax, eax
0x180015826  jnz     loc_180015A7E
0x18001582c  mov     rcx, [rbp+hKey]; hKey
0x180015830  lea     rbx, [rdi+120h]
0x180015837  mov     [rdi+328h], ax
0x18001583e  lea     rdx, aSystemroot; "SystemRoot"
0x180015845  lea     rax, [rbp+cbData]
0x180015849  mov     [rbp+cbData], 104h
0x180015850  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180015855  xor     r9d, r9d; lpType
0x180015858  xor     r8d, r8d; lpReserved
0x18001585b  mov     [rsp+68h+phkResult], rbx; lpData
0x180015860  call    cs:__imp_RegQueryValueExW
0x180015866  mov     r15d, eax
0x180015869  test    eax, eax
0x18001586b  jnz     short loc_18001588D
0x18001586d  lea     r8, aInfNtprintInf; "\\inf\\ntprint.inf"
0x180015874  mov     edx, 117h; unsigned __int64
0x180015879  mov     rcx, rbx; unsigned __int16 *
0x18001587c  lea     esi, [rax+1]
0x18001587f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015884  lea     rbx, WPP_GLOBAL_Control
0x18001588b  jmp     short loc_1800158CE
0x18001588d  xor     esi, esi
0x18001588f  mov     rax, cs:WPP_GLOBAL_Control
0x180015896  lea     rbx, WPP_GLOBAL_Control
0x18001589d  cmp     rax, rbx
0x1800158a0  jz      short loc_1800158CE
0x1800158a2  test    byte ptr [rax+1Ch], 1
0x1800158a6  jz      short loc_1800158CE
0x1800158a8  cmp     byte ptr [rax+19h], 2
0x1800158ac  jb      short loc_1800158CE
0x1800158ae  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800158b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158ba  lea     edx, [rsi+19h]
0x1800158bd  mov     r9d, eax
0x1800158c0  mov     dword ptr [rsp+68h+phkResult], r15d
0x1800158c5  mov     rcx, [rcx+10h]
0x1800158c9  call    WPP_SF_Dl
0x1800158ce  mov     rcx, [rbp+hKey]; hKey
0x1800158d2  call    cs:__imp_RegCloseKey
0x1800158d8  test    esi, esi
0x1800158da  jz      loc_180015B0A
0x1800158e0  lea     rcx, aPrintuiDll; "printui.dll"
0x1800158e7  call    cs:__imp_LoadLibraryW
0x1800158ed  mov     [rdi+0A0h], rax
0x1800158f4  test    rax, rax
0x1800158f7  jnz     short loc_180015944
0x1800158f9  movups  xmm0, cs:EVENT_NOTIFY_INTERNALERROR
0x180015900  xor     esi, esi
0x180015902  lea     r14d, [rax+1]
0x180015906  movdqu  xmmword ptr [rbp+var_28.Id], xmm0
0x18001590b  mov     rax, cs:WPP_GLOBAL_Control
0x180015912  cmp     rax, rbx
0x180015915  jz      loc_180015B0A
0x18001591b  test    [rax+1Ch], r14b
0x18001591f  jz      loc_180015B0A
  ... truncated ...
```
