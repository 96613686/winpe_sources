# CDlpActionLayoutUsb::SplitWimList(CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,ushort const *)

- ea: `0x18002cd9c`
- end: `0x18002da4a`
- name: `?SplitWimList@CDlpActionLayoutUsb@@AEAAJPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@0PEBG@Z`
- size: `3246`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000cad8`

## callees

- `0x180002898`
- `0x1800029b4`
- `0x180007bbc`
- `0x18000aba4`
- `0x18000b7f8`
- `0x18000d888`
- `0x18000ea20`
- `0x180012f5c`
- `0x18001ad34`
- `0x18001c9d0`
- `0x18001fd60`
- `0x180020468`
- `0x18002b5bc`
- `0x18002baec`
- `0x18002cd9c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002d371`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002d371`
- `WIMGAPI!WIMRegisterMessageCallback` at `0x18002d1b5`
- `WIMGAPI!WIMRegisterMessageCallback` at `0x18002d1b5`
- `WIMGAPI!WIMCloseHandle` at `0x18002d0fe`
- `WIMGAPI!WIMCloseHandle` at `0x18002d5d6`
- `WIMGAPI!WIMCloseHandle` at `0x18002d0fe`
- `WIMGAPI!WIMCloseHandle` at `0x18002d5d6`
- `WIMGAPI!WIMSetTemporaryPath` at `0x18002d195`
- `WIMGAPI!WIMSetTemporaryPath` at `0x18002d195`
- `WIMGAPI!WIMUnregisterMessageCallback` at `0x18002da3e`
- `WIMGAPI!WIMUnregisterMessageCallback` at `0x18002da3e`
- `WIMGAPI!WIMCreateFile` at `0x18002d0ed`
- `WIMGAPI!WIMCreateFile` at `0x18002d0ed`
- `WIMGAPI!WIMSplitFile` at `0x18002d3cc`
- `WIMGAPI!WIMSplitFile` at `0x18002d3cc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002cec5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002cfa7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002cec5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002cfa7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cf01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cf55`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d139`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d531`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d552`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d57d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d5a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cf01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cf55`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d139`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d531`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d552`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d57d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d5a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cf0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cf63`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d147`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d53f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d562`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d58b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d5b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cf0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cf63`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d147`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d53f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d562`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d58b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d5b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d4b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d65b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d69e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d76e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d8cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d4b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d65b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d69e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d76e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d8cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d3f5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d3f5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d2dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d31c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d2dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002d31c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d1d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d238`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d1d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d238`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d1fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d261`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d1fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d261`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d3e1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d3e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d2f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d331`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d382`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d5c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d2f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d331`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d382`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d5c7`

## string_xrefs

- `0x18002d9d2`: `LayoutUsb: Path [%s] not found!`
- `0x18002d0b0`: `LayoutUsb: Opening source WIM file: [%s]...`
- `0x18002d11d`: `LayoutUsb: Successfully opened source WIM file.`
- `0x18002d180`: `LayoutUsb: Setting temp path to [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDlpActionLayoutUsb::SplitWimList(char *lpParameter, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 v6; // rdi
  void *v7; // rsi
  char *v8; // r12
  unsigned __int64 v9; // r13
  signed int v10; // r14d
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  unsigned int v14; // edx
  __int64 v15; // r12
  DWORD FileAttributesW; // eax
  BOOL v17; // ebx
  char *v18; // rbx
  HANDLE ProcessHeap; // rax
  int v20; // eax
  WCHAR *v21; // rbx
  HANDLE v22; // rax
  int v23; // eax
  wchar_t *v24; // r14
  DWORD v25; // ebx
  int v26; // ebx
  int FolderPath; // eax
  int FileSize; // eax
  unsigned __int64 v29; // rbx
  unsigned __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // r14
  __int64 v34; // rcx
  void *v35; // r14
  HANDLE v36; // rax
  int TempDir; // eax
  __int64 v38; // r14
  int v39; // eax
  __int64 v40; // rbx
  void *v41; // rbx
  unsigned int v42; // edx
  int StringCch; // eax
  int v44; // eax
  HANDLE EventW; // rbx
  void *v46; // rcx
  HANDLE v47; // rbx
  void *v48; // rcx
  HANDLE Thread; // rbx
  __int64 v50; // rcx
  int v51; // eax
  int v52; // eax
  signed int v53; // eax
  __int64 v54; // rcx
  int v55; // eax
  void *v56; // rbx
  HANDLE v57; // rax
  HANDLE v58; // rax
  WCHAR *v59; // rbx
  HANDLE v60; // rax
  __int64 v61; // rbx
  HANDLE v62; // rax
  __int64 v64; // rcx
  signed int v65; // eax
  __int64 v66; // rcx
  signed int v67; // eax
  int v68; // eax
  signed int v69; // eax
  __int64 v70; // rcx
  signed int v71; // eax
  signed int v72; // eax
  signed int v73; // eax
  signed int LastError; // eax
  __int64 v75; // rcx
  int v76; // eax
  DWORD dwCreationFlags[2]; // [rsp+28h] [rbp-79h]
  int dwCreationFlagsa; // [rsp+28h] [rbp-79h]
  __int64 v79; // [rsp+30h] [rbp-71h]
  void *Src; // [rsp+38h] [rbp-69h] BYREF
  int v81; // [rsp+40h] [rbp-61h]
  unsigned int v82; // [rsp+44h] [rbp-5Dh] BYREF
  __int64 v83; // [rsp+48h] [rbp-59h] BYREF
  unsigned int v84; // [rsp+50h] [rbp-51h]
  LPCWSTR lpFileName; // [rsp+58h] [rbp-49h]
  unsigned __int64 v86; // [rsp+60h] [rbp-41h] BYREF
  __int64 v87; // [rsp+68h] [rbp-39h] BYREF
  __int64 v88; // [rsp+70h] [rbp-31h] BYREF
  __int64 v89; // [rsp+78h] [rbp-29h] BYREF
  unsigned __int64 v90; // [rsp+80h] [rbp-21h] BYREF
  __int64 v91; // [rsp+88h] [rbp-19h] BYREF
  HANDLE v92; // [rsp+90h] [rbp-11h]
  __int64 v93; // [rsp+98h] [rbp-9h]
  int v94; // [rsp+B0h] [rbp+Fh]

  v4 = a2;
  v6 = 0;
  v93 = 0;
  v7 = 0;
  v92 = 0;
  v89 = 0;
  lpFileName = 0;
  v8 = 0;
  Src = 0;
  v83 = 0;
  v90 = 0;
  v91 = 0;
  v9 = 0;
  v86 = 0;
  v88 = 0;
  v87 = 0;
  if ( !a2 )
  {
    v10 = -2147024809;
    v11 = *((_QWORD *)lpParameter + 11);
    if ( !v11 )
      goto LABEL_98;
    dwCreationFlagsa = 3783;
LABEL_4:
    v12 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v11,
            4u,
            (__int64)L"%s(%d): Result = 0x%X",
            L"CDlpActionLayoutUsb::SplitWimList",
            dwCreationFlagsa,
            -2147024809);
    v13 = (unsigned int)v12;
    if ( v12 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
    goto LABEL_98;
  }
  if ( !a3 )
  {
    v10 = -2147024809;
    v11 = *((_QWORD *)lpParameter + 11);
    if ( !v11 )
      goto LABEL_98;
    dwCreationFlagsa = 3784;
    goto LABEL_4;
  }
  if ( !a4 )
  {
    v10 = -2147024809;
    v11 = *((_QWORD *)lpParameter + 11);
    if ( !v11 )
      goto LABEL_98;
    dwCreationFlagsa = 3785;
    goto LABEL_4;
  }
  v81 = 0;
  v10 = 0;
  v14 = 0;
  v84 = 0;
  if ( !*(_DWORD *)(v4 + 4) )
    goto LABEL_98;
  while ( 1 )
  {
    v15 = (int)v14;
    FileAttributesW = GetFileAttributesW(*(LPCWSTR *)(*(_QWORD *)(v4 + 8) + 8LL * (int)v14));
    v17 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( !v17 )
    {
      v75 = *((_QWORD *)lpParameter + 11);
      if ( v75 )
        CDlpLogT<CEmptyType>::DlpLogFormat(
          v75,
          2u,
          (__int64)L"LayoutUsb: Path [%s] not found!",
          *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8 * v15));
      v10 = -2147024893;
      v32 = *((_QWORD *)lpParameter + 11);
      if ( v32 )
      {
        LODWORD(v79) = -2147024893;
        dwCreationFlags[0] = 3793;
        goto LABEL_195;
      }
      goto LABEL_198;
    }
    if ( Src )
    {
      v18 = (char *)Src - 4;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v18);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      Src = 0;
    }
    v20 = CDlpHelpersT<CEmptyType>::CombinePath(a4, *(_QWORD *)(*(_QWORD *)(a3 + 8) + 8 * v15), (__int64)&Src);
    v10 = v20;
    if ( v20 < 0 )
    {
      v32 = *((_QWORD *)lpParameter + 11);
      if ( v32 )
      {
        LODWORD(v79) = v20;
        dwCreationFlags[0] = 3797;
        goto LABEL_195;
      }
LABEL_198:
      v8 = (char *)Src;
      goto LABEL_199;
    }
    if ( lpFileName )
    {
      v21 = (WCHAR *)(lpFileName - 2);
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v21);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      lpFileName = 0;
    }
    v23 = CMiscHelpersT<CEmptyType>::ParseFileName(Src, 0);
    v10 = v23;
    if ( v23 < 0 )
    {
      v32 = *((_QWORD *)lpParameter + 11);
      if ( !v32 )
        goto LABEL_198;
      LODWORD(v79) = v23;
      dwCreationFlags[0] = 3806;
      goto LABEL_195;
    }
    v24 = (wchar_t *)lpFileName;
    v25 = GetFileAttributesW(lpFileName);
    if ( v25 == -1 )
      v26 = 0;
    else
      v26 = (v25 >> 4) & 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( !v26 )
    {
      FolderPath = CMiscHelpersT<CEmptyType>::CreateFolderPath(v24);
      v10 = FolderPath;
      if ( FolderPath < 0 )
      {
        v32 = *((_QWORD *)lpParameter + 11);
        if ( !v32 )
          goto LABEL_198;
        LODWORD(v79) = FolderPath;
        dwCreationFlags[0] = 3813;
        goto LABEL_195;
      }
    }
    FileSize = CDlpHelpersT<CEmptyType>::GetFileSize(*(_QWORD *)(*(_QWORD *)(a2 + 8) + 8 * v15), &v90);
    v10 = FileSize;
    if ( FileSize < 0 )
    {
      v32 = *((_QWORD *)lpParameter + 11);
      if ( !v32 )
        goto LABEL_198;
      LODWORD(v79) = FileSize;
      dwCreationFlags[0] = 3818;
      goto LABEL_195;
    }
    v29 = v90;
    if ( v90 + *((_QWORD *)lpParameter + 173) < v90 )
    {
      v10 = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
    }
    else
    {
      v9 = v90 + *((_QWORD *)lpParameter + 173);
      v86 = v9;
      v10 = 0;
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
    if ( v10 < 0 )
    {
      v32 = *((_QWORD *)lpParameter + 11);
      if ( !v32 )
        goto LABEL_198;
      LODWORD(v79) = v10;
      dwCreationFlags[0] = 3820;
      goto LABEL_195;
    }
    v30 = v9 - 1;
    if ( v9 )
    {
      --v9;
      v86 = v30;
      v10 = 0;
    }
    else
    {
      v10 = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
    if ( v10 < 0 )
    {
      v32 = *((_QWORD *)lpParameter + 11);
      if ( !v32 )
        goto LABEL_198;
      LODWORD(v79) = v10;
      dwCreationFlags[0] = 3821;
      goto LABEL_195;
    }
    v31 = SafeDiv<unsigned __int64>(v9, *((_QWORD *)lpParameter + 173), &v86);
    v10 = v31;
    v32 = *((_QWORD *)lpParameter + 11);
    if ( v31 < 0 )
    {
      if ( !v32 )
        goto LABEL_198;
      LODWORD(v79) = v31;
      dwCreationFlags[0] = 3822;
      goto LABEL_195;
    }
    if ( v32 )
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v32,
        2u,
        (__int64)L"LayoutUsb: Opening source WIM file: [%s]...",
        *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8 * v15));
    v33 = WIMCreateFile(*(_QWORD *)(*(_QWORD *)(a2 + 8) + 8 * v15), 0x80000000LL, 3, 0x20000000, 0, 0);
    if ( v6 )
      WIMCloseHandle(v6);
    if ( !v33 )
    {
      v6 = 0;
      v93 = 0;
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v10 = -2147467259;
      }
      if ( !*((_QWORD *)lpParameter + 11) )
        goto LABEL_198;
      v70 = 0;
      if ( v10 < 0 )
      {
        LODWORD(v79) = v10;
        dwCreationFlags[0] = 3834;
        goto LABEL_142;
      }
      goto LABEL_197;
    }
    v6 = v33;
    v93 = v33;
    v34 = *((_QWORD *)lpParameter + 11);
    if ( v34 )
      CDlpLogT<CEmptyType>::DlpLogFormat(v34, 2u, (__int64)L"LayoutUsb: Successfully opened source WIM file.");
    if ( v83 )
    {
      v35 = (void *)(v83 - 4);
      v36 = GetProcessHeap();
      HeapFree(v36, 0, v35);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v83 = 0;
    }
    TempDir = CMiscHelpersT<CEmptyType>::GetTempDir(&v83);
    v10 = TempDir;
    v32 = *((_QWORD *)lpParameter + 11);
    if ( TempDir < 0 )
    {
      if ( !v32 )
        goto LABEL_198;
      LODWORD(v79) = TempDir;
      dwCreationFlags[0] = 3840;
      goto LABEL_195;
    }
    v38 = v83;
    if ( v32 )
      CDlpLogT<CEmptyType>::DlpLogFormat(v32, 2u, (__int64)L"LayoutUsb: Setting temp path to [%s]", v83);
    if ( !(unsigned int)WIMSetTemporaryPath(v6, v38) )
    {
      v73 = GetLastError();
      v10 = v73;
      if ( v73 )
      {
        if ( v73 > 0 )
          v10 = (unsigned __int16)v73 | 0x80070000;
      }
      else
      {
        v10 = -2147467259;
      }
      if ( !*((_QWORD *)lpParameter + 11) )
        goto LABEL_198;
      v70 = 0;
      if ( v10 < 0 )
      {
        LODWORD(v79) = v10;
        dwCreationFlags[0] = 3842;
        goto LABEL_142;
      }
      goto LABEL_197;
    }
    if ( !v81 )
      break;
LABEL_55:
    EnterCriticalSection((LPCRITICAL_SECTION)(lpParameter + 624));
    v94 = 1;
    *((_QWORD *)lpParameter + 76) = v29;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( v94 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(lpParameter + 624));
      v94 = 0;
    }
    v39 = (*(__int64 (__fastcall **)(char *, __int64 *, __int64 *, _QWORD))(*(_QWORD *)lpParameter + 72LL))(
            lpParameter,
            &v88,
            &v87,
            0);
    v10 = v39;
    if ( v39 < 0 )
    {
      v32 = *((_QWORD *)lpParameter + 11);
      if ( !v32 )
        goto LABEL_198;
      LODWORD(v79) = v39;
      dwCreationFlags[0] = 3855;
      goto LABEL_195;
    }
    v40 = v87;
    EnterCriticalSection((LPCRITICAL_SECTION)(lpParameter + 688));
    v94 = 1;
    *((_QWORD *)lpParameter + 84) = v40;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( v94 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(lpParameter + 688));
      v94 = 0;
    }
    CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(lpParameter + 1128, 0);
    if ( !Src )
    {
      v41 = 0;
      v42 = 0;
      goto LABEL_62;
    }
    v41 = Src;
    v82 = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Src, &v82);
    v10 = StringCch;
    if ( StringCch >= 0 )
    {
      v42 = v82;
LABEL_62:
      StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v41, v42, &v89);
      v10 = StringCch;
      if ( StringCch >= 0 )
        goto LABEL_64;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
LABEL_64:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
    if ( v10 < 0 )
    {
      v32 = *((_QWORD *)lpParameter + 11);
      if ( !v32 )
        goto LABEL_198;
      LODWORD(v79) = v10;
      dwCreationFlags[0] = 3861;
LABEL_195:
      v76 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v32,
              4u,
              (__int64)L"%s(%d): Result = 0x%X",
              L"CDlpActionLayoutUsb::SplitWimList",
              *(_QWORD *)dwCreationFlags,
              v79);
      v70 = (unsigned int)v76;
      if ( v76 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v76);
      goto LABEL_197;
    }
    v44 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((__int64)(lpParameter + 1128), &v89);
    v10 = v44;
    if ( v44 < 0 )
    {
      v32 = *((_QWORD *)lpParameter + 11);
      if ( !v32 )
        goto LABEL_198;
      LODWORD(v79) = v44;
      dwCreationFlags[0] = 3862;
      goto LABEL_195;
    }
    EventW = CreateEventW(0, 0, 0, 0);
    v46 = (void *)*((_QWORD *)lpParameter + 108);
    if ( v46 )
    {
      CloseHandle(v46);
      *((_QWORD *)lpParameter + 108) = 0;
    }
    if ( !EventW )
    {
      *((_QWORD *)lpParameter + 108) = 0;
      v72 = GetLastError();
      v10 = v72;
      if ( v72 )
      {
        if ( v72 > 0 )
          v10 = (unsigned __int16)v72 | 0x80070000;
      }
      else
      {
        v10 = -2147467259;
      }
      if ( !*((_QWORD *)lpParameter + 11) )
        goto LABEL_198;
      v70 = 0;
      if ( v10 < 0 )
      {
        LODWORD(v79) = v10;
        dwCreationFlags[0] = 3867;
        goto LABEL_142;
      }
LABEL_197:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v70);
      goto LABEL_198;
    }
    *((_QWORD *)lpParameter + 108) = EventW;
    v47 = CreateEventW(0, 0, 0, 0);
    v48 = (void *)*((_QWORD *)lpParameter + 109);
    if ( v48 )
    {
      CloseHandle(v48);
      *((_QWORD *)lpParameter + 109) = 0;
    }
    if ( !v47 )
    {
      *((_QWORD *)lpParameter + 109) = 0;
      v71 = GetLastError();
      v10 = v71;
      if ( v71 )
      {
        if ( v71 > 0 )
          v10 = (unsigned __int16)v71 | 0x80070000;
      }
      else
      {
        v10 = -2147467259;
      }
      if ( !*((_QWORD *)lpParameter + 11) )
        goto LABEL_198;
      v70 = 0;
      if ( v10 >= 0 )
        goto LABEL_197;
      LODWORD(v79) = v10;
      dwCreationFlags[0] = 3872;
LABEL_142:
      v32 = *((_QWORD *)lpParameter + 11);
      goto LABEL_195;
    }
    *((_QWORD *)lpParameter + 109) = v47;
    Thread = CreateThread(0, 0, CDlpActionLayoutUsb::SplitProgressThreadProc, lpParameter, 0, 0);
    if ( v7 )
      CloseHandle(v7);
    if ( !Thread )
    {
      v7 = 0;
      v92 = 0;
      v69 = GetLastError();
      v10 = v69;
      if ( v69 )
      {
        if ( v69 > 0 )
          v10 = (unsigned __int16)v69 | 0x80070000;
      }
      else
      {
        v10 = -2147467259;
      }
      if ( !*((_QWORD *)lpParameter + 11) )
        goto LABEL_198;
      v70 = 0;
      if ( v10 >= 0 )
        goto LABEL_197;
      LODWORD(v79) = v10;
      dwCreationFlags[0] = 3882;
      goto LABEL_142;
    }
    v7 = Thread;
    v92 = Thread;
    v91 = *((_QWORD *)lpParameter + 173);
    v50 = *((_QWORD *)lpParameter + 11);
    if ( v50 )
      CDlpLogT<CEmptyType>::DlpLogFormat(v50, 2u, (__int64)L"LayoutUsb: Splitting WIM file...");
    v8 = (char *)Src;
    if ( !(unsigned int)WIMSplitFile(v6, Src, &v91, 0) )
    {
      v67 = GetLastError();
      v10 = v67;
      if ( v67 )
      {
        if ( v67 > 0 )
          v10 = (unsigned __int16)v67 | 0x80070000;
      }
      else
      {
        v10 = -2147467259;
      }
      if ( *((_QWORD *)lpParameter + 11) )
      {
        v66 = 0;
        if ( v10 < 0 )
        {
          LODWORD(v79) = v10;
          dwCreationFlags[0] = 3891;
LABEL_131:
          v64 = *((_QWORD *)lpParameter + 11);
LABEL_132:
          v68 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v64,
                  4u,
                  (__int64)L"%s(%d): Result = 0x%X",
                  L"CDlpActionLayoutUsb::SplitWimList",
                  *(_QWORD *)dwCreationFlags,
                  v79);
          v66 = (unsigned int)v68;
          if ( v68 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v68);
        }
LABEL_134:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v66);
      }
LABEL_199:
      if ( v81 )
        WIMUnregisterMessageCallback(0, CDlpActionLayoutUsb::WimSplitCallback);
      goto LABEL_98;
    }
    if ( !SetEvent(*((HANDLE *)lpParameter + 109)) )
    {
      v65 = GetLastError();
      v10 = v65;
      if ( v65 )
      {
        if ( v65 > 0 )
          v10 = (unsigned __int16)v65 | 0x80070000;
      }
      else
      {
        v10 = -2147467259;
      }
      if ( *((_QWORD *)lpParameter + 11) )
      {
        v66 = 0;
        if ( v10 < 0 )
        {
          LODWORD(v79) = v10;
          dwCreationFlags[0] = 3895;
          goto LABEL_131;
        }
        goto LABEL_134;
      }
      goto LABEL_199;
    }
    if ( WaitForSingleObject(Thread, 0xFFFFFFFF) )
    {
      v10 = -2147418113;
      v64 = *((_QWORD *)lpParameter + 11);
      if ( v64 )
      {
        LODWORD(v79) = -2147418113;
        dwCreationFlags[0] = 3897;
        goto LABEL_132;
      }
      goto LABEL_199;
    }
    v51 = (*(__int64 (__fastcall **)(char *, __int64 *, __int64 *, _QWORD))(*(_QWORD *)lpParameter + 72LL))(
            lpParameter,
            &v88,
            &v87,
            0);
    v10 = v51;
    if ( v51 < 0 )
    {
      v64 = *((_QWORD *)lpParameter + 11);
      if ( v64 )
      {
        LODWORD(v79) = v51;
        dwCreationFlags[0] = 3901;
        goto LABEL_132;
      }
      goto LABEL_199;
    }
    v52 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::SetProgress(
            lpParameter,
            v88,
            v88);
    v10 = v52;
    if ( v52 < 0 )
    {
      v64 = *((_QWORD *)lpParameter + 11);
      if ( v64 )
      {
        LODWORD(v79) = v52;
        dwCreationFlags[0] = 3902;
        goto LABEL_132;
      }
      goto LABEL_199;
    }
    v14 = v84 + 1;
    v84 = v14;
    v4 = a2;
    if ( v14 >= *(_DWORD *)(a2 + 4) )
      goto LABEL_199;
    v9 = v86;
  }
  if ( (unsigned int)WIMRegisterMessageCallback(0, CDlpActionLayoutUsb::WimSplitCallback, lpParameter) != -1 )
  {
    v81 = 1;
    goto LABEL_55;
  }
  v53 = GetLastError();
  v10 = v53;
  if ( v53 )
  {
    if ( v53 > 0 )
      v10 = (unsigned __int16)v53 | 0x80070000;
  }
  else
  {
    v10 = -2147467259;
  }
  if ( *((_QWORD *)lpParameter + 11) )
  {
    v54 = 0;
    if ( v10 < 0 )
    {
      LODWORD(v79) = v10;
      dwCreationFlags[0] = 3848;
      v55 = CDlpLogT<CEmptyType>::DlpLogFormat(
              *((_QWORD *)lpParameter + 11),
              4u,
              (__int64)L"%s(%d): Result = 0x%X",
              L"CDlpActionLayoutUsb::SplitWimList",
              *(_QWORD *)dwCreationFlags,
              v79);
      v54 = (unsigned int)v55;
      if ( v55 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v55);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v54);
  }
  v8 = (char *)Src;
LABEL_98:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
  if ( v83 )
  {
    v56 = (void *)(v83 - 4);
    v57 = GetProcessHeap();
    HeapFree(v57, 0, v56);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v8 )
  {
    v58 = GetProcessHeap();
    HeapFree(v58, 0, v8 - 4);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( lpFileName )
  {
    v59 = (WCHAR *)(lpFileName - 2);
    v60 = GetProcessHeap();
    HeapFree(v60, 0, v59);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  v61 = v89;
  if ( v89 )
  {
    v62 = GetProcessHeap();
    HeapFree(v62, 0, (LPVOID)(v61 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v7 )
    CloseHandle(v7);
  if ( v6 )
    WIMCloseHandle(v6);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002cd9c  mov     rax, rsp
0x18002cd9f  mov     [rax+8], rbx
0x18002cda3  mov     [rax+20h], r9
0x18002cda7  mov     [rax+18h], r8
0x18002cdab  mov     [rax+10h], rdx
0x18002cdaf  push    rbp
0x18002cdb0  push    rsi
0x18002cdb1  push    rdi
0x18002cdb2  push    r12
0x18002cdb4  push    r13
0x18002cdb6  push    r14
0x18002cdb8  push    r15
0x18002cdba  lea     rbp, [rax-5Fh]
0x18002cdbe  sub     rsp, 0C0h
0x18002cdc5  mov     rax, rdx
0x18002cdc8  mov     r15, rcx
0x18002cdcb  xor     ecx, ecx
0x18002cdcd  mov     edi, ecx
0x18002cdcf  mov     [rbp+57h+var_60], rcx
0x18002cdd3  mov     esi, ecx
0x18002cdd5  mov     [rbp+57h+var_68], rcx
0x18002cdd9  mov     [rbp+57h+var_80], rcx
0x18002cddd  mov     [rbp+57h+lpFileName], rcx
0x18002cde1  mov     r12d, ecx
0x18002cde4  mov     [rbp+57h+Src], rcx
0x18002cde8  mov     [rbp+57h+var_B0], rcx
0x18002cdec  mov     [rbp+57h+var_78], rcx
0x18002cdf0  mov     [rbp+57h+var_70], rcx
0x18002cdf4  mov     r13d, ecx
0x18002cdf7  mov     [rbp+57h+var_98], rcx
0x18002cdfb  mov     [rbp+57h+var_88], rcx
0x18002cdff  mov     [rbp+57h+var_90], rcx
0x18002ce03  test    rdx, rdx
0x18002ce06  jnz     short loc_18002CE56
0x18002ce08  mov     eax, 80070057h
0x18002ce0d  mov     r14d, eax
0x18002ce10  mov     rcx, [r15+58h]
0x18002ce14  test    rcx, rcx
0x18002ce17  jz      loc_18002D51B
0x18002ce1d  mov     [rsp+28h], eax
0x18002ce21  mov     [rsp+0F0h+dwCreationFlags], 0EC7h
0x18002ce29  lea     r9, aCdlpactionlayo_16; "CDlpActionLayoutUsb::SplitWimList"
0x18002ce30  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18002ce37  mov     edx, 4
0x18002ce3c  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002ce41  test    eax, eax
0x18002ce43  mov     ecx, eax
0x18002ce45  jns     short loc_18002CE4C
0x18002ce47  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002ce4c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002ce51  jmp     loc_18002D51B
0x18002ce56  test    r8, r8
0x18002ce59  jnz     short loc_18002CE7E
0x18002ce5b  mov     eax, 80070057h
0x18002ce60  mov     r14d, eax
0x18002ce63  mov     rcx, [r15+58h]
0x18002ce67  test    rcx, rcx
0x18002ce6a  jz      loc_18002D51B
0x18002ce70  mov     [rsp+28h], eax
0x18002ce74  mov     [rsp+0F0h+dwCreationFlags], 0EC8h
0x18002ce7c  jmp     short loc_18002CE29
0x18002ce7e  test    r9, r9
0x18002ce81  jnz     short loc_18002CEA6
0x18002ce83  mov     eax, 80070057h
0x18002ce88  mov     r14d, eax
0x18002ce8b  mov     rcx, [r15+58h]
0x18002ce8f  test    rcx, rcx
0x18002ce92  jz      loc_18002D51B
0x18002ce98  mov     [rsp+28h], eax
0x18002ce9c  mov     [rsp+0F0h+dwCreationFlags], 0EC9h
0x18002cea4  jmp     short loc_18002CE29
0x18002cea6  mov     [rbp+57h+var_B8], ecx
0x18002cea9  mov     r14d, ecx
0x18002ceac  mov     edx, ecx
0x18002ceae  mov     [rbp+57h+var_A8], ecx
0x18002ceb1  cmp     [rax+4], ecx
0x18002ceb4  jbe     loc_18002D51B
0x18002ceba  mov     rcx, [rax+8]
0x18002cebe  movsxd  r12, edx
0x18002cec1  mov     rcx, [rcx+r12*8]; lpFileName
0x18002cec5  call    cs:__imp_GetFileAttributesW
0x18002cecb  mov     ebx, eax
0x18002cecd  cmp     eax, 0FFFFFFFFh
0x18002ced0  jz      short loc_18002CEDC
0x18002ced2  shr     ebx, 4
0x18002ced5  not     ebx
0x18002ced7  and     ebx, 1
0x18002ceda  jmp     short loc_18002CEDE
0x18002cedc  xor     ebx, ebx
0x18002cede  xor     ecx, ecx
0x18002cee0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002cee5  xor     ecx, ecx
0x18002cee7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002ceec  test    ebx, ebx
0x18002ceee  jz      loc_18002D9BD
0x18002cef4  mov     rax, [rbp+57h+Src]
0x18002cef8  test    rax, rax
0x18002cefb  jz      short loc_18002CF24
0x18002cefd  lea     rbx, [rax-4]
0x18002cf01  call    cs:__imp_GetProcessHeap
0x18002cf07  mov     rcx, rax; hHeap
0x18002cf0a  mov     r8, rbx; lpMem
0x18002cf0d  xor     edx, edx; dwFlags
0x18002cf0f  call    cs:__imp_HeapFree
0x18002cf15  xor     ecx, ecx
0x18002cf17  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002cf1c  mov     [rbp+57h+Src], 0
0x18002cf24  mov     rax, [rbp+57h+arg_10]
0x18002cf28  mov     rax, [rax+8]
0x18002cf2c  lea     r8, [rbp+57h+Src]
0x18002cf30  mov     rdx, [rax+r12*8]
0x18002cf34  mov     rcx, [rbp+57h+arg_18]
0x18002cf38  call    ?CombinePath@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBG0PEAPEAG@Z; CDlpHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort * *)
0x18002cf3d  mov     r14d, eax
0x18002cf40  test    eax, eax
0x18002cf42  js      loc_18002D9A6
0x18002cf48  mov     rax, [rbp+57h+lpFileName]
0x18002cf4c  test    rax, rax
0x18002cf4f  jz      short loc_18002CF78
0x18002cf51  lea     rbx, [rax-4]
0x18002cf55  call    cs:__imp_GetProcessHeap
0x18002cf5b  mov     rcx, rax; hHeap
0x18002cf5e  mov     r8, rbx; lpMem
0x18002cf61  xor     edx, edx; dwFlags
0x18002cf63  call    cs:__imp_HeapFree
0x18002cf69  xor     ecx, ecx
0x18002cf6b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002cf70  mov     [rbp+57h+lpFileName], 0
0x18002cf78  mov     qword ptr [rsp+0F0h+dwCreationFlags], 0; __int64
0x18002cf81  xor     r9d, r9d
0x18002cf84  lea     r8, [rbp+57h+lpFileName]
0x18002cf88  lea     rdx, [rbp+57h+var_B4]
0x18002cf8c  mov     rcx, [rbp+57h+Src]; Src
0x18002cf90  call    ?ParseFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAHPEAPEAG22@Z; CMiscHelpersT<CEmptyType>::ParseFileName(ushort const *,int *,ushort * *,ushort * *,ushort * *)
0x18002cf95  mov     r14d, eax
0x18002cf98  test    eax, eax
0x18002cf9a  js      loc_18002D98B
0x18002cfa0  mov     r14, [rbp+57h+lpFileName]
0x18002cfa4  mov     rcx, r14; lpFileName
0x18002cfa7  call    cs:__imp_GetFileAttributesW
0x18002cfad  mov     ebx, eax
0x18002cfaf  cmp     eax, 0FFFFFFFFh
0x18002cfb2  jz      short loc_18002CFBC
0x18002cfb4  shr     ebx, 4
0x18002cfb7  and     ebx, 1
0x18002cfba  jmp     short loc_18002CFBE
0x18002cfbc  xor     ebx, ebx
0x18002cfbe  xor     ecx, ecx
0x18002cfc0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002cfc5  xor     ecx, ecx
0x18002cfc7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002cfcc  test    ebx, ebx
0x18002cfce  jnz     short loc_18002CFE3
0x18002cfd0  mov     rcx, r14
0x18002cfd3  call    ?CreateFolderPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CMiscHelpersT<CEmptyType>::CreateFolderPath(ushort const *,_SECURITY_ATTRIBUTES *)
0x18002cfd8  mov     r14d, eax
0x18002cfdb  test    eax, eax
0x18002cfdd  js      loc_18002D492
0x18002cfe3  mov     rax, [rbp+57h+arg_8]
0x18002cfe7  mov     rax, [rax+8]
0x18002cfeb  lea     rdx, [rbp+57h+var_78]
0x18002cfef  mov     rcx, [rax+r12*8]
0x18002cff3  call    ?GetFileSize@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBGPEAT_LARGE_INTEGER@@@Z; CDlpHelpersT<CEmptyType>::GetFileSize(ushort const *,_LARGE_INTEGER *)
0x18002cff8  mov     r14d, eax
0x18002cffb  test    eax, eax
0x18002cffd  js      loc_18002D970
0x18002d003  mov     rbx, [rbp+57h+var_78]
0x18002d007  mov     rcx, [r15+568h]
0x18002d00e  add     rcx, rbx
0x18002d011  cmp     rcx, rbx
0x18002d014  jb      short loc_18002D022
0x18002d016  mov     r13, rcx
0x18002d019  mov     [rbp+57h+var_98], rcx
0x18002d01d  xor     r14d, r14d
0x18002d020  jmp     short loc_18002D031
0x18002d022  mov     eax, 80070216h
0x18002d027  mov     r14d, eax
0x18002d02a  mov     ecx, eax
0x18002d02c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002d031  mov     ecx, r14d
0x18002d034  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002d039  test    r14d, r14d
0x18002d03c  js      loc_18002D951
0x18002d042  lea     rax, [r13-1]
0x18002d046  cmp     rax, r13
0x18002d049  ja      short loc_18002D057
0x18002d04b  mov     r13, rax
0x18002d04e  mov     [rbp+57h+var_98], rax
0x18002d052  xor     r14d, r14d
0x18002d055  jmp     short loc_18002D066
0x18002d057  mov     eax, 80070216h
0x18002d05c  mov     r14d, eax
0x18002d05f  mov     ecx, eax
0x18002d061  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002d066  mov     ecx, r14d
0x18002d069  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002d06e  test    r14d, r14d
0x18002d071  js      loc_18002D932
0x18002d077  lea     r8, [rbp+57h+var_98]
0x18002d07b  mov     rdx, [r15+568h]
0x18002d082  mov     rcx, r13
0x18002d085  call    ??$SafeDiv@_K@@YAJ_K0PEA_K@Z; SafeDiv<unsigned __int64>(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002d08a  mov     r14d, eax
0x18002d08d  mov     rcx, [r15+58h]
0x18002d091  test    eax, eax
0x18002d093  js      loc_18002D918
0x18002d099  mov     r13d, 2
0x18002d09f  test    rcx, rcx
0x18002d0a2  jz      short loc_18002D0BF
0x18002d0a4  mov     rax, [rbp+57h+arg_8]
0x18002d0a8  mov     rax, [rax+8]
0x18002d0ac  mov     r9, [rax+r12*8]
0x18002d0b0  lea     r8, aLayoutusbOpeni; "LayoutUsb: Opening source WIM file: [%s"...
0x18002d0b7  mov     edx, r13d
0x18002d0ba  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002d0bf  mov     rax, [rbp+57h+arg_8]
0x18002d0c3  mov     rax, [rax+8]
0x18002d0c7  mov     qword ptr [rsp+28h], 0
0x18002d0d0  mov     [rsp+0F0h+dwCreationFlags], 0
0x18002d0d8  mov     edx, 80000000h
0x18002d0dd  mov     r9d, 20000000h
0x18002d0e3  mov     r8d, 3
0x18002d0e9  mov     rcx, [rax+r12*8]
0x18002d0ed  call    cs:__imp_WIMCreateFile
0x18002d0f3  mov     r14, rax
0x18002d0f6  test    rdi, rdi
0x18002d0f9  jz      short loc_18002D104
0x18002d0fb  mov     rcx, rdi
0x18002d0fe  call    cs:__imp_WIMCloseHandle
0x18002d104  test    r14, r14
0x18002d107  jz      loc_18002D8C9
0x18002d10d  mov     rdi, r14
0x18002d110  mov     [rbp+57h+var_60], r14
0x18002d114  mov     rcx, [r15+58h]
0x18002d118  test    rcx, rcx
0x18002d11b  jz      short loc_18002D12C
0x18002d11d  lea     r8, aLayoutusbSucce_0; "LayoutUsb: Successfully opened source W"...
0x18002d124  mov     edx, r13d
0x18002d127  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002d12c  mov     rax, [rbp+57h+var_B0]
0x18002d130  test    rax, rax
0x18002d133  jz      short loc_18002D15C
0x18002d135  lea     r14, [rax-4]
0x18002d139  call    cs:__imp_GetProcessHeap
0x18002d13f  mov     rcx, rax; hHeap
0x18002d142  mov     r8, r14; lpMem
0x18002d145  xor     edx, edx; dwFlags
0x18002d147  call    cs:__imp_HeapFree
0x18002d14d  xor     ecx, ecx
0x18002d14f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002d154  mov     [rbp+57h+var_B0], 0
0x18002d15c  lea     rcx, [rbp+57h+var_B0]
0x18002d160  call    ?GetTempDir@?$CMiscHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z; CMiscHelpersT<CEmptyType>::GetTempDir(ushort * *)
0x18002d165  mov     r14d, eax
0x18002d168  mov     rcx, [r15+58h]
0x18002d16c  test    eax, eax
0x18002d16e  js      loc_18002D8AF
0x18002d174  mov     r14, [rbp+57h+var_B0]
0x18002d178  test    rcx, rcx
0x18002d17b  jz      short loc_18002D18F
0x18002d17d  mov     r9, r14
0x18002d180  lea     r8, aLayoutusbSetti; "LayoutUsb: Setting temp path to [%s]"
0x18002d187  mov     edx, r13d
0x18002d18a  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002d18f  mov     rdx, r14
0x18002d192  mov     rcx, rdi
0x18002d195  call    cs:__imp_WIMSetTemporaryPath
0x18002d19b  test    eax, eax
0x18002d19d  jz      loc_18002D865
0x18002d1a3  cmp     [rbp+57h+var_B8], 0
0x18002d1a7  jnz     short loc_18002D1CB
0x18002d1a9  mov     r8, r15
0x18002d1ac  lea     rdx, ?WimSplitCallback@CDlpActionLayoutUsb@@CAKK_K_JPEAX@Z; CDlpActionLayoutUsb::WimSplitCallback(ulong,unsigned __int64,__int64,void *)
0x18002d1b3  xor     ecx, ecx
0x18002d1b5  call    cs:__imp_WIMRegisterMessageCallback
0x18002d1bb  cmp     eax, 0FFFFFFFFh
0x18002d1be  jz      loc_18002D4B0
0x18002d1c4  mov     [rbp+57h+var_B8], 1
0x18002d1cb  lea     rcx, [r15+270h]; lpCriticalSection
0x18002d1d2  call    cs:__imp_EnterCriticalSection
0x18002d1d8  mov     [rbp+57h+var_48], 1
0x18002d1df  mov     [r15+260h], rbx
0x18002d1e6  xor     ecx, ecx
0x18002d1e8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002d1ed  mov     eax, [rbp+57h+var_48]
0x18002d1f0  test    eax, eax
0x18002d1f2  jz      short loc_18002D208
0x18002d1f4  lea     rcx, [r15+270h]; lpCriticalSection
0x18002d1fb  call    cs:__imp_LeaveCriticalSection
0x18002d201  mov     [rbp+57h+var_48], 0
0x18002d208  mov     rax, [r15]
0x18002d20b  xor     r9d, r9d
0x18002d20e  lea     r8, [rbp+57h+var_90]
0x18002d212  lea     rdx, [rbp+57h+var_88]
0x18002d216  mov     rcx, r15
0x18002d219  mov     rax, [rax+48h]
0x18002d21d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d222  mov     r14d, eax
0x18002d225  test    eax, eax
0x18002d227  js      loc_18002D847
  ... truncated ...
```
