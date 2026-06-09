# CDlpActionWimLayout::ApplyMediaLayoutImage(ushort const *,ushort const *,int,int)

- ea: `0x180007f78`
- end: `0x18000902a`
- name: `?ApplyMediaLayoutImage@CDlpActionWimLayout@@AEAAJPEBG0HH@Z`
- size: `4274`
- prototype: `__int64 __fastcall(CDlpActionWimLayout *this, unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180004978`
- `0x180006700`

## callees

- `0x180007f78`
- `0x180009030`
- `0x18000aba4`
- `0x18000b9a8`
- `0x1800107bc`
- `0x180012f5c`
- `0x18001cc44`
- `0x18001fd60`
- `0x180027f1c`
- `0x180028688`
- `0x18002eae4`
- `0x18002fa74`
- `0x1800302d0`
- `0x180030434`
- `0x1800392f4`
- `0x18003abd0`
- `0x18007ec76`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `WIMGAPI!WIMGetAttributes` at `0x1800081d7`
- `WIMGAPI!WIMGetAttributes` at `0x1800081d7`
- `WIMGAPI!WIMRegisterMessageCallback` at `0x18000864c`
- `WIMGAPI!WIMRegisterMessageCallback` at `0x18000864c`
- `WIMGAPI!WIMCloseHandle` at `0x180008e22`
- `WIMGAPI!WIMCloseHandle` at `0x180008fd2`
- `WIMGAPI!WIMCloseHandle` at `0x180008fe1`
- `WIMGAPI!WIMCloseHandle` at `0x180008ff0`
- `WIMGAPI!WIMCloseHandle` at `0x180008e22`
- `WIMGAPI!WIMCloseHandle` at `0x180008fd2`
- `WIMGAPI!WIMCloseHandle` at `0x180008fe1`
- `WIMGAPI!WIMCloseHandle` at `0x180008ff0`
- `WIMGAPI!WIMSetTemporaryPath` at `0x1800085c2`
- `WIMGAPI!WIMSetTemporaryPath` at `0x180008b2c`
- `WIMGAPI!WIMSetTemporaryPath` at `0x180008d4e`
- `WIMGAPI!WIMSetTemporaryPath` at `0x1800085c2`
- `WIMGAPI!WIMSetTemporaryPath` at `0x180008b2c`
- `WIMGAPI!WIMSetTemporaryPath` at `0x180008d4e`
- `WIMGAPI!WIMUnregisterMessageCallback` at `0x180008e8f`
- `WIMGAPI!WIMUnregisterMessageCallback` at `0x180008e8f`
- `WIMGAPI!WIMCreateFile` at `0x180008138`
- `WIMGAPI!WIMCreateFile` at `0x180008aa0`
- `WIMGAPI!WIMCreateFile` at `0x180008cbe`
- `WIMGAPI!WIMCreateFile` at `0x180008138`
- `WIMGAPI!WIMCreateFile` at `0x180008aa0`
- `WIMGAPI!WIMCreateFile` at `0x180008cbe`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000889f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000889f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180008522`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000875d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180008522`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000875d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000847b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000857a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800086b0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000847b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000857a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800086b0`
- `OLEAUT32!__imp_SysFreeString` at `0x180008f40`
- `OLEAUT32!__imp_SysFreeString` at `0x180008f40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008097`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800082d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008efc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008fae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008097`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800082d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008efc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008fae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800080a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800082e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008fbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800080a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800082e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008fbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000814b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000852c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000814b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000852c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d58`

## string_xrefs

- `0x180008052`: `sources\install.esd`
- `0x1800080c0`: `sources\install.wim`
- `0x180008102`: `WimLayout: Opening ESD package file: [%s]`
- `0x1800081a9`: `WimLayout: Successfully opened ESD package file.`
- `0x180008340`: `WimLayout: ESD package info: %d images, %d install images`
- `0x180008376`: `WimLayout: ESD package info: Flags: 0x%X, CompressionType: %d, BootIndex: %d`
- `0x1800083bd`: `WimLayout: Layout Index: %d, WinPe Index: %d, MediaBoot Index: %d, Install Index: %d`
- `0x180008497`: `WimLayout: Cleaning scratch path: [%s]`
- `0x18000850c`: `WimLayout: Creating scratch path: [%s]`
- `0x1800085ad`: `WimLayout: Setting scratch path for [%s] to [%s]`
- `0x180008b17`: `WimLayout: Setting scratch path for [%s] to [%s]`
- `0x180008d35`: `WimLayout: Setting scratch path for [%s] to [%s]`
- `0x1800086e6`: `WimLayout: Cleaning target path: [%s]`
- `0x180008db0`: `WimLayout: Exporting install images to [%s]...`

## pseudocode

```c
__int64 __fastcall CDlpActionWimLayout::ApplyMediaLayoutImage(
        CDlpActionWimLayout *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5)
{
  void *v7; // rdi
  void *v8; // rsi
  void *v9; // r14
  int v10; // eax
  signed int v11; // r15d
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rbx
  HANDLE ProcessHeap; // rax
  int v16; // eax
  __int64 v17; // rax
  signed int LastError; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  signed int v21; // eax
  int v22; // eax
  int v23; // r8d
  __int64 v24; // r15
  __int64 v25; // rbx
  HANDLE v26; // rax
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  int WorkingPath; // eax
  int v31; // eax
  const WCHAR *v32; // rbx
  __int64 v33; // rcx
  signed int v34; // eax
  __int64 v35; // rcx
  signed int v36; // eax
  __int64 v37; // rcx
  signed int v38; // eax
  __int64 v39; // rcx
  int v40; // eax
  signed int v41; // eax
  DWORD FileAttributesW; // ebx
  int v43; // ebx
  __int64 v44; // rcx
  signed int v45; // eax
  __int64 v46; // rcx
  __int64 v47; // rcx
  signed int v48; // eax
  int v49; // eax
  __int64 v50; // rcx
  int v51; // eax
  __int64 v52; // rcx
  __int64 v53; // rcx
  int v54; // eax
  signed int v55; // eax
  __int64 v56; // rcx
  int v57; // eax
  int v58; // eax
  int v59; // eax
  double v60; // xmm6_8
  unsigned int v61; // ebx
  unsigned int v62; // r15d
  double v63; // xmm7_8
  __int64 v64; // rcx
  int v65; // eax
  __int64 v66; // r15
  __int64 v67; // rax
  signed int v68; // eax
  __int64 v69; // rcx
  signed int v70; // eax
  unsigned int v71; // r13d
  unsigned int v72; // ebx
  __int64 v73; // rcx
  int v74; // eax
  int v75; // eax
  __int64 v76; // r9
  _QWORD *v77; // r15
  __int64 v78; // rax
  signed int v79; // eax
  __int64 v80; // rcx
  signed int v81; // eax
  __int64 v82; // rcx
  int v83; // eax
  int v84; // eax
  int v85; // eax
  int v86; // eax
  void *v87; // rbx
  HANDLE v88; // rax
  void *v89; // rbx
  HANDLE v90; // rax
  __int64 v91; // rbx
  HANDLE v92; // rax
  void *v93; // rbx
  HANDLE v94; // rax
  WCHAR *v95; // rbx
  HANDLE v96; // rax
  void *v98; // [rsp+28h] [rbp-E0h]
  __int64 v99; // [rsp+30h] [rbp-D8h]
  LPCWSTR lpFileName; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v101[2]; // [rsp+50h] [rbp-B8h] BYREF
  unsigned __int16 *v102; // [rsp+58h] [rbp-B0h]
  BSTR bstrString; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v104; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v105; // [rsp+70h] [rbp-98h] BYREF
  __int64 v106; // [rsp+78h] [rbp-90h]
  __int64 v107; // [rsp+80h] [rbp-88h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp-80h] BYREF
  __int64 v109; // [rsp+90h] [rbp-78h]
  __int64 v110; // [rsp+98h] [rbp-70h]
  __int128 Buf2; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v112[536]; // [rsp+B8h] [rbp-50h] BYREF
  unsigned int v113; // [rsp+2D0h] [rbp+1C8h]
  int v114; // [rsp+2D4h] [rbp+1CCh]
  int v115; // [rsp+2DCh] [rbp+1D4h]
  unsigned int v116; // [rsp+2E0h] [rbp+1D8h]

  v101[0] = a4;
  v102 = a2;
  v7 = 0;
  v106 = 0;
  v8 = 0;
  v109 = 0;
  v9 = 0;
  v110 = 0;
  lpFileName = 0;
  v105 = 0;
  v104 = 0;
  bstrString = 0;
  Buf2 = 0;
  memset_0(v112, 0, 0x230u);
  lpMem = 0;
  v101[1] = 0;
  v107 = 0;
  v10 = CMiscHelpersT<CEmptyType>::CombinePath(a3, L"sources\\boot.wim", 0, &v105);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = *((_QWORD *)this + 11);
    if ( !v12 )
      goto LABEL_241;
    LODWORD(v99) = v10;
    LODWORD(v98) = 1168;
    goto LABEL_238;
  }
  v13 = CMiscHelpersT<CEmptyType>::CombinePath(a3, L"sources\\install.esd", 0, &v104);
  v11 = v13;
  if ( v13 < 0 )
  {
    v12 = *((_QWORD *)this + 11);
    if ( !v12 )
      goto LABEL_241;
    LODWORD(v99) = v13;
    LODWORD(v98) = 1173;
    goto LABEL_238;
  }
  v14 = *((_QWORD *)this + 93);
  if ( v14 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v14 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 93) = 0;
  }
  v16 = CMiscHelpersT<CEmptyType>::CombinePath(a3, L"sources\\install.wim", 0, (char *)this + 744);
  v11 = v16;
  v12 = *((_QWORD *)this + 11);
  if ( v16 < 0 )
  {
    if ( !v12 )
      goto LABEL_241;
    LODWORD(v99) = v16;
    LODWORD(v98) = 1179;
    goto LABEL_238;
  }
  if ( v12 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v12, 2, L"WimLayout: Opening ESD package file: [%s]", v102);
  v17 = WIMCreateFile(v102, 0x80000000LL, 3, 0x20000000, 0, 0);
  v7 = (void *)v17;
  if ( !v17 )
  {
    v106 = 0;
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v11 = -2147467259;
    }
    if ( *((_QWORD *)this + 11) )
    {
      v19 = 0;
      if ( v11 < 0 )
      {
        LODWORD(v99) = v11;
        LODWORD(v98) = 1190;
LABEL_22:
        v12 = *((_QWORD *)this + 11);
LABEL_238:
        v86 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v12,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionWimLayout::ApplyMediaLayoutImage",
                v98,
                v99);
        v19 = (unsigned int)v86;
        if ( v86 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v86);
        goto LABEL_240;
      }
      goto LABEL_240;
    }
    goto LABEL_241;
  }
  v106 = v17;
  v20 = *((_QWORD *)this + 11);
  if ( v20 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v20, 2, L"WimLayout: Successfully opened ESD package file.");
  memset_0(v112, 0, 0x230u);
  if ( (unsigned int)WIMGetAttributes(v7, v112, 560) )
  {
    if ( v113 <= 2 )
    {
      v11 = -2147024883;
      v12 = *((_QWORD *)this + 11);
      if ( !v12 )
        goto LABEL_241;
      LODWORD(v99) = -2147024883;
      LODWORD(v98) = 1199;
      goto LABEL_238;
    }
    v22 = (*(__int64 (__fastcall **)(CDlpActionWimLayout *, __int128 *))(*(_QWORD *)this + 56LL))(this, &Buf2);
    v11 = v22;
    if ( v22 < 0 )
    {
      v12 = *((_QWORD *)this + 11);
      if ( !v12 )
        goto LABEL_241;
      LODWORD(v99) = v22;
      LODWORD(v98) = 1203;
      goto LABEL_238;
    }
    if ( v114 == 3 || !memcmp_0(&WINDLP_ACTION_UPGLAYOUT, &Buf2, 0x10u) )
    {
      v24 = v104;
      v104 = 0;
      v25 = *((_QWORD *)this + 93);
      if ( v25 )
      {
        v26 = GetProcessHeap();
        HeapFree(v26, 0, (LPVOID)(v25 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      *((_QWORD *)this + 93) = v24;
    }
    v27 = CDlpActionWimLayout::WimDetermineImages(this, v7, v23);
    v11 = v27;
    v12 = *((_QWORD *)this + 11);
    if ( v27 < 0 )
    {
      if ( !v12 )
        goto LABEL_241;
      LODWORD(v99) = v27;
      LODWORD(v98) = 1214;
      goto LABEL_238;
    }
    if ( v12 )
    {
      LODWORD(v98) = *((_DWORD *)this + 190);
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v12,
        2,
        L"WimLayout: ESD package info: %d images, %d install images",
        v113,
        v98);
    }
    v28 = *((_QWORD *)this + 11);
    if ( v28 )
    {
      LODWORD(v99) = v115;
      LODWORD(v98) = v114;
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v28,
        2,
        L"WimLayout: ESD package info: Flags: 0x%X, CompressionType: %d, BootIndex: %d",
        v116,
        v98,
        v99);
    }
    v29 = *((_QWORD *)this + 11);
    if ( v29 )
    {
      LODWORD(v99) = *((_DWORD *)this + 194);
      LODWORD(v98) = *((_DWORD *)this + 193);
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v29,
        2,
        L"WimLayout: Layout Index: %d, WinPe Index: %d, MediaBoot Index: %d, Install Index: %d",
        *((unsigned int *)this + 192),
        v98,
        v99,
        *((_DWORD *)this + 191));
    }
    WorkingPath = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::GetWorkingPath(
                    this,
                    &bstrString);
    v11 = WorkingPath;
    if ( WorkingPath < 0 )
    {
      v12 = *((_QWORD *)this + 11);
      if ( !v12 )
        goto LABEL_241;
      LODWORD(v99) = WorkingPath;
      LODWORD(v98) = 1241;
      goto LABEL_238;
    }
    v31 = CMiscHelpersT<CEmptyType>::CombinePath(bstrString, L"{d3536bdb-3c4a-4896-84fd-825e4d700b4f}", 0, &lpFileName);
    v11 = v31;
    if ( v31 < 0 )
    {
      v12 = *((_QWORD *)this + 11);
      if ( !v12 )
        goto LABEL_241;
      LODWORD(v99) = v31;
      LODWORD(v98) = 1242;
      goto LABEL_238;
    }
    v32 = lpFileName;
    if ( (unsigned int)FileExists(lpFileName) )
    {
      v11 = -2147024735;
      v12 = *((_QWORD *)this + 11);
      if ( !v12 )
        goto LABEL_241;
      LODWORD(v99) = -2147024735;
      LODWORD(v98) = 1243;
      goto LABEL_238;
    }
    if ( GetFileAttributesW(v32) != -1 )
    {
      v33 = *((_QWORD *)this + 11);
      if ( v33 )
        CDlpLogT<CEmptyType>::DlpLogFormat(v33, 2, L"WimLayout: Cleaning scratch path: [%s]", v32);
      if ( !(unsigned int)DeletePathEx(v32) )
      {
        v34 = GetLastError();
        v11 = v34;
        if ( v34 )
        {
          if ( v34 > 0 )
            v11 = (unsigned __int16)v34 | 0x80070000;
        }
        else
        {
          v11 = -2147467259;
        }
        if ( *((_QWORD *)this + 11) )
        {
          v19 = 0;
          if ( v11 < 0 )
          {
            LODWORD(v99) = v11;
            LODWORD(v98) = 1247;
            goto LABEL_22;
          }
          goto LABEL_240;
        }
        goto LABEL_241;
      }
    }
    v35 = *((_QWORD *)this + 11);
    if ( v35 )
      CDlpLogT<CEmptyType>::DlpLogFormat(v35, 2, L"WimLayout: Creating scratch path: [%s]", v32);
    if ( !CreateDirectoryW(v32, 0) )
    {
      v36 = GetLastError();
      v11 = v36;
      if ( v36 )
      {
        if ( v36 > 0 )
          v11 = (unsigned __int16)v36 | 0x80070000;
      }
      else
      {
        v11 = -2147467259;
      }
      if ( *((_QWORD *)this + 11) )
      {
        v19 = 0;
        if ( v11 < 0 )
        {
          LODWORD(v99) = v11;
          LODWORD(v98) = 1253;
          goto LABEL_22;
        }
        goto LABEL_240;
      }
      goto LABEL_241;
    }
    if ( GetFileAttributesW(v32) == -1 || (unsigned int)FileExists(v32) )
    {
      v11 = -2147024735;
      v12 = *((_QWORD *)this + 11);
      if ( !v12 )
        goto LABEL_241;
      LODWORD(v99) = -2147024735;
      LODWORD(v98) = 1254;
      goto LABEL_238;
    }
    v37 = *((_QWORD *)this + 11);
    if ( v37 )
      CDlpLogT<CEmptyType>::DlpLogFormat(v37, 2, L"WimLayout: Setting scratch path for [%s] to [%s]", v102, v32);
    if ( !(unsigned int)WIMSetTemporaryPath(v7, v32) )
    {
      v38 = GetLastError();
      v11 = v38;
      if ( v38 )
      {
        if ( v38 > 0 )
          v11 = (unsigned __int16)v38 | 0x80070000;
      }
      else
      {
        v11 = -2147467259;
      }
      if ( !*((_QWORD *)this + 11) )
        goto LABEL_235;
      v39 = 0;
      if ( v11 >= 0 )
        goto LABEL_97;
      LODWORD(v99) = v11;
      LODWORD(v98) = 1260;
      goto LABEL_95;
    }
    if ( (unsigned int)WIMRegisterMessageCallback(0, CDlpActionWimLayout::WimLayoutCallback, this) == -1 )
    {
      v41 = GetLastError();
      v11 = v41;
      if ( v41 )
      {
        if ( v41 > 0 )
          v11 = (unsigned __int16)v41 | 0x80070000;
      }
      else
      {
        v11 = -2147467259;
      }
      if ( !*((_QWORD *)this + 11) )
        goto LABEL_235;
      v39 = 0;
      if ( v11 >= 0 )
        goto LABEL_97;
      LODWORD(v99) = v11;
      LODWORD(v98) = 1264;
LABEL_95:
      v40 = CDlpLogT<CEmptyType>::DlpLogFormat(
              *((_QWORD *)this + 11),
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpActionWimLayout::ApplyMediaLayoutImage",
              v98,
              v99);
      v39 = (unsigned int)v40;
      if ( v40 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v40);
LABEL_97:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v39);
LABEL_235:
      DeletePathEx(v32);
      goto LABEL_241;
    }
    if ( *((_DWORD *)this + 205) )
    {
      FileAttributesW = GetFileAttributesW(a3);
      if ( FileAttributesW == -1 )
        v43 = 0;
      else
        v43 = (FileAttributesW >> 4) & 1;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      if ( v43 )
      {
        v44 = *((_QWORD *)this + 11);
        if ( v44 )
          CDlpLogT<CEmptyType>::DlpLogFormat(v44, 2, L"WimLayout: Cleaning target path: [%s]", a3);
        if ( !(unsigned int)DeletePathEx(*((LPCWSTR *)this + 91)) )
        {
          v45 = GetLastError();
          v11 = v45;
          if ( v45 )
          {
            if ( v45 > 0 )
              v11 = (unsigned __int16)v45 | 0x80070000;
          }
          else
          {
            v11 = -2147467259;
          }
          if ( !*((_QWORD *)this + 11) )
            goto LABEL_233;
          v46 = 0;
          if ( v11 >= 0 )
            goto LABEL_232;
          LODWORD(v99) = v11;
          LODWORD(v98) = 1273;
LABEL_121:
          v47 = *((_QWORD *)this + 11);
          goto LABEL_230;
        }
      }
      if ( !CreateDirectoryW(a3, 0) )
      {
        v48 = GetLastError();
        v11 = v48;
        if ( v48 )
        {
          if ( v48 > 0 )
            v11 = (unsigned __int16)v48 | 0x80070000;
        }
        else
        {
          v11 = -2147467259;
        }
        if ( !*((_QWORD *)this + 11) )
          goto LABEL_233;
        v46 = 0;
        if ( v11 >= 0 )
          goto LABEL_232;
        LODWORD(v99) = v11;
        LODWORD(v98) = 1276;
        goto LABEL_121;
      }
      v32 = lpFileName;
    }
    v49 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::ResetActionProgress(this);
    v11 = v49;
    if ( v49 < 0 )
    {
      v50 = *((_QWORD *)this + 11);
      if ( !v50 )
      {
LABEL_234:
        WIMUnregisterMessageCallback(0, CDlpActionWimLayout::WimLayoutCallback);
        goto LABEL_235;
      }
      LODWORD(v99) = v49;
      LODWORD(v98) = 1281;
      goto LABEL_134;
    }
    if ( !memcmp_0(&WINDLP_ACTION_UPGLAYOUT, &Buf2, 0x10u) )
    {
      v53 = *((_QWORD *)this + 11);
      if ( v53 )
        CDlpLogT<CEmptyType>::DlpLogFormat(v53, 2, L"WimLayout: Applying Media Layout image to [%s]...", a3);
      v54 = CDlpActionWimLayout::WimLayoutApplyImage(
              this,
              v7,
              *((_DWORD *)this + 192),
              *((const unsigned __int16 **)this + 91),
              v101[0],
              a5);
      v11 = v54;
      if ( v54 < 0 )
      {
        v50 = *((_QWORD *)this + 11);
        if ( !v50 )
          goto LABEL_234;
        LODWORD(v99) = v54;
        LODWORD(v98) = 1288;
        goto LABEL_134;
      }
      if ( !SetFileAttributesW(a3, 0x2002u) )
      {
        v55 = GetLastError();
        v11 = v55;
        if ( v55 )
        {
          if ( v55 > 0 )
            v11 = (unsigned __int16)v55 | 0x80070000;
        }
        else
        {
          v11 = -2147467259;
        }
        if ( !*((_QWORD *)this + 11) )
          goto LABEL_234;
        v52 = 0;
        if ( v11 >= 0 )
          goto LABEL_136;
        LODWORD(v99) = v11;
        LODWORD(v98) = 1289;
LABEL_151:
        v50 = *((_QWORD *)this + 11);
LABEL_134:
        v51 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v50,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionWimLayout::ApplyMediaLayoutImage",
                v98,
                v99);
        v52 = (unsigned int)v51;
        if ( v51 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v51);
LABEL_136:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v52);
        goto LABEL_234;
      }
      v56 = *((_QWORD *)this + 92);
      if ( v56 )
      {
        v57 = CStringConvertT<unsigned long>::Base64Decode(v56, &lpMem, &v101[1]);
        v11 = v57;
        if ( v57 < 0 )
        {
          v50 = *((_QWORD *)this + 11);
          if ( !v50 )
            goto LABEL_234;
          LODWORD(v99) = v57;
          LODWORD(v98) = 1297;
          goto LABEL_134;
        }
        v58 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 91), L"sources\\FP", 0, &v107);
        v11 = v58;
        if ( v58 < 0 )
        {
          v50 = *((_QWORD *)this + 11);
          if ( !v50 )
            goto LABEL_234;
          LODWORD(v99) = v58;
          LODWORD(v98) = 1298;
          goto LABEL_134;
        }
        v59 = CMiscHelpersT<CEmptyType>::SaveBinaryAsFile(v107, v101[1], lpMem);
        v11 = v59;
        if ( v59 < 0 )
        {
          v50 = *((_QWORD *)this + 11);
          if ( !v50 )
            goto LABEL_234;
          LODWORD(v99) = v59;
          LODWORD(v98) = 1299;
          goto LABEL_134;
        }
      }
LABEL_226:
      if ( !*((_DWORD *)this + 204) )
        goto LABEL_233;
      WIMCloseHandle(v7);
      v7 = 0;
      v106 = 0;
      v84 = CDlpActionWimLayout::DeleteSourceFile(this, v102);
      v11 = v84;
      if ( v84 >= 0 )
        goto LABEL_233;
      v47 = *((_QWORD *)this + 11);
      if ( !v47 )
        goto LABEL_233;
      LODWORD(v99) = v84;
      LODWORD(v98) = 1376;
      goto LABEL_230;
    }
    if ( *((_DWORD *)this + 206) )
      v60 = DOUBLE_0_6;
    else
      v60 = DOUBLE_0_1;
    v61 = a5;
    v62 = v101[0];
    v63 = (double)(int)(a5 - v101[0]);
    v64 = *((_QWORD *)this + 11);
    if ( v64 )
      CDlpLogT<CEmptyType>::DlpLogFormat(v64, 2, L"WimLayout: Applying Media Layout image to [%s]...", a3);
    v65 = CDlpActionWimLayout::WimLayoutApplyImage(this, v7, *((_DWORD *)this + 192), a3, v62, v62 + (int)(v63 * v60));
    v11 = v65;
    if ( v65 < 0 )
    {
      v47 = *((_QWORD *)this + 11);
      if ( v47 )
      {
        LODWORD(v99) = v65;
        LODWORD(v98) = 1309;
        goto LABEL_230;
      }
LABEL_233:
      v32 = lpFileName;
      goto LABEL_234;
    }
    if ( *((_DWORD *)this + 206) )
    {
      v71 = v101[0];
    }
    else
    {
      v66 = v105;
      v67 = WIMCreateFile(v105, 3221225472LL, 2, 0, 2, 0);
      v8 = (void *)v67;
      if ( !v67 )
      {
        v109 = 0;
        v68 = GetLastError();
        v11 = v68;
        if ( v68 )
        {
          if ( v68 > 0 )
            v11 = (unsigned __int16)v68 | 0x80070000;
        }
        else
        {
          v11 = -2147467259;
        }
        if ( !*((_QWORD *)this + 11) )
          goto LABEL_233;
        v46 = 0;
        if ( v11 >= 0 )
          goto LABEL_232;
        LODWORD(v99) = v11;
        LODWORD(v98) = 1321;
        goto LABEL_121;
      }
      v109 = v67;
      v69 = *((_QWORD *)this + 11);
      v32 = lpFileName;
      if ( v69 )
        CDlpLogT<CEmptyType>::DlpLogFormat(v69, 2, L"WimLayout: Setting scratch path for [%s] to [%s]", v66, lpFileName);
      if ( !(unsigned int)WIMSetTemporaryPath(v8, v32) )
      {
        v70 = GetLastError();
        v11 = v70;
        if ( v70 )
        {
          if ( v70 > 0 )
            v11 = (unsigned __int16)v70 | 0x80070000;
        }
        else
        {
          v11 = -2147467259;
        }
        if ( !*((_QWORD *)this + 11) )
          goto LABEL_234;
        v52 = 0;
        if ( v11 >= 0 )
          goto LABEL_136;
        LODWORD(v99) = v11;
        LODWORD(v98) = 1326;
        goto LABEL_151;
      }
      v71 = v101[0];
      v72 = v101[0] - (int)(v63 * -0.5);
      v73 = *((_QWORD *)this + 11);
      if ( v73 )
        CDlpLogT<CEmptyType>::DlpLogFormat(v73, 2, L"WimLayout: Exporting HdBoot WinPe image to [%s]...", v66);
      v74 = CDlpActionWimLayout::WimLayoutExportImage(
              this,
              v7,
              *((_DWORD *)this + 193),
              v8,
              v71 - (int)(v63 * -0.1),
              v72);
      v11 = v74;
      v47 = *((_QWORD *)this + 11);
      if ( v74 < 0 )
      {
        if ( !v47 )
          goto LABEL_233;
        LODWORD(v99) = v74;
        LODWORD(v98) = 1333;
        goto LABEL_230;
      }
      if ( v47 )
        CDlpLogT<CEmptyType>::DlpLogFormat(v47, 2, L"WimLayout: Exporting MediaBoot WinPe image to [%s]...", v105);
      v75 = CDlpActionWimLayout::WimLayoutExportImage(
              this,
              v7,
              *((_DWORD *)this + 194),
              v8,
              v72,
              v71 - (int)(v63 * -0.6));
      v11 = v75;
      if ( v75 < 0 )
      {
        v47 = *((_QWORD *)this + 11);
        if ( !v47 )
          goto LABEL_233;
        LODWORD(v99) = v75;
        LODWORD(v98) = 1340;
        goto LABEL_230;
      }
      v61 = a5;
    }
    v76 = 0x20000000;
    if ( v114 != 3 )
      v76 = 0;
    v77 = (_QWORD *)((char *)this + 744);
    v78 = WIMCreateFile(*((_QWORD *)this + 93), 3221225472LL, 2, v76, v114, 0);
    v9 = (void *)v78;
    if ( !v78 )
    {
      v110 = 0;
      v79 = GetLastError();
      v11 = v79;
      if ( v79 )
      {
        if ( v79 > 0 )
          v11 = (unsigned __int16)v79 | 0x80070000;
      }
      else
      {
        v11 = -2147467259;
      }
      if ( !*((_QWORD *)this + 11) )
        goto LABEL_233;
      v46 = 0;
      if ( v11 >= 0 )
        goto LABEL_232;
      LODWORD(v99) = v11;
      LODWORD(v98) = 1351;
      goto LABEL_121;
    }
    v110 = v78;
    v80 = *((_QWORD *)this + 11);
    if ( v80 )
      CDlpLogT<CEmptyType>::DlpLogFormat(v80, 2, L"WimLayout: Setting scratch path for [%s] to [%s]", *v77, lpFileName);
    if ( !(unsigned int)WIMSetTemporaryPath(v9, lpFileName) )
    {
      v81 = GetLastError();
      v11 = v81;
      if ( v81 )
      {
        if ( v81 > 0 )
          v11 = (unsigned __int16)v81 | 0x80070000;
      }
      else
      {
        v11 = -2147467259;
      }
      if ( !*((_QWORD *)this + 11) )
        goto LABEL_233;
      v46 = 0;
      if ( v11 >= 0 )
        goto LABEL_232;
      LODWORD(v99) = v11;
      LODWORD(v98) = 1356;
      goto LABEL_121;
    }
    v82 = *((_QWORD *)this + 11);
    if ( v82 )
      CDlpLogT<CEmptyType>::DlpLogFormat(v82, 2, L"WimLayout: Exporting install images to [%s]...", *v77);
    v83 = CDlpActionWimLayout::WimLayoutExportImages(
            this,
            v7,
            *((_DWORD *)this + 191),
            *((_DWORD *)this + 190),
            v9,
            v71 - (int)(v63 * -0.6),
            v61);
    v11 = v83;
    if ( v83 >= 0 )
      goto LABEL_226;
    v47 = *((_QWORD *)this + 11);
    if ( !v47 )
      goto LABEL_233;
    LODWORD(v99) = v83;
    LODWORD(v98) = 1363;
LABEL_230:
    v85 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v47,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpActionWimLayout::ApplyMediaLayoutImage",
            v98,
            v99);
    v46 = (unsigned int)v85;
    if ( v85 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v85);
LABEL_232:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v46);
    goto LABEL_233;
  }
  v21 = GetLastError();
  v11 = v21;
  if ( v21 )
  {
    if ( v21 > 0 )
      v11 = (unsigned __int16)v21 | 0x80070000;
  }
  else
  {
    v11 = -2147467259;
  }
  if ( *((_QWORD *)this + 11) )
  {
    v19 = 0;
    if ( v11 < 0 )
    {
      LODWORD(v99) = v11;
      LODWORD(v98) = 1198;
      goto LABEL_22;
    }
LABEL_240:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v19);
  }
LABEL_241:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
  if ( v107 )
  {
    v87 = (void *)(v107 - 4);
    v88 = GetProcessHeap();
    HeapFree(v88, 0, v87);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  v89 = lpMem;
  if ( lpMem )
  {
    v90 = GetProcessHeap();
    HeapFree(v90, 0, v89);
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  v91 = v104;
  if ( v104 )
  {
    v92 = GetProcessHeap();
    HeapFree(v92, 0, (LPVOID)(v91 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v105 )
  {
    v93 = (void *)(v105 - 4);
    v94 = GetProcessHeap();
    HeapFree(v94, 0, v93);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( lpFileName )
  {
    v95 = (WCHAR *)(lpFileName - 2);
    v96 = GetProcessHeap();
    HeapFree(v96, 0, v95);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v9 )
    WIMCloseHandle(v9);
  if ( v8 )
    WIMCloseHandle(v8);
  if ( v7 )
    WIMCloseHandle(v7);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180007f78  mov     rax, rsp
0x180007f7b  push    rbp
0x180007f7c  push    rbx
0x180007f7d  push    rsi
0x180007f7e  push    rdi
0x180007f7f  push    r12
0x180007f81  push    r13
0x180007f83  push    r14
0x180007f85  push    r15
0x180007f87  lea     rbp, [rax-258h]
0x180007f8e  sub     rsp, 318h
0x180007f95  movaps  xmmword ptr [rax-58h], xmm6
0x180007f99  movaps  xmmword ptr [rax-68h], xmm7
0x180007f9d  mov     rax, cs:__security_cookie
0x180007fa4  xor     rax, rsp
0x180007fa7  mov     [rbp+250h+var_70], rax
0x180007fae  mov     [rsp+350h+var_308], r9d
0x180007fb3  mov     r13, r8
0x180007fb6  mov     [rsp+350h+var_300], rdx
0x180007fbb  mov     r12, rcx
0x180007fbe  xor     ebx, ebx
0x180007fc0  mov     edi, ebx
0x180007fc2  mov     [rsp+350h+var_2E0], rbx
0x180007fc7  mov     esi, ebx
0x180007fc9  mov     [rbp+250h+var_2C8], rbx
0x180007fcd  mov     r14d, ebx
0x180007fd0  mov     [rbp+250h+var_2C0], rbx
0x180007fd4  mov     [rsp+350h+lpFileName], rbx
0x180007fd9  mov     [rsp+350h+var_2E8], rbx
0x180007fde  mov     [rsp+350h+var_2F0], rbx
0x180007fe3  mov     [rsp+350h+bstrString], rbx
0x180007fe8  xorps   xmm0, xmm0
0x180007feb  movups  [rbp+250h+Buf2], xmm0
0x180007fef  xor     edx, edx; Val
0x180007ff1  mov     r8d, 230h; Size
0x180007ff7  lea     rcx, [rbp+250h+var_2A0]; void *
0x180007ffb  call    memset_0
0x180008000  mov     [rbp+250h+lpMem], rbx
0x180008004  mov     [rsp+350h+var_308+4], ebx
0x180008008  mov     [rsp+350h+var_2D8], rbx
0x18000800d  lea     r9, [rsp+350h+var_2E8]
0x180008012  xor     r8d, r8d
0x180008015  lea     rdx, aSourcesBootWim; "sources\\boot.wim"
0x18000801c  mov     rcx, r13
0x18000801f  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180008024  mov     r15d, eax
0x180008027  test    eax, eax
0x180008029  jns     short loc_18000804A
0x18000802b  mov     rcx, [r12+58h]
0x180008030  test    rcx, rcx
0x180008033  jz      loc_180008EE5
0x180008039  mov     dword ptr [rsp+350h+var_328], eax
0x18000803d  mov     dword ptr [rsp+350h+var_330], 490h
0x180008045  jmp     loc_180008EBD
0x18000804a  lea     r9, [rsp+350h+var_2F0]
0x18000804f  xor     r8d, r8d
0x180008052  lea     rdx, aSourcesInstall_0; "sources\\install.esd"
0x180008059  mov     rcx, r13
0x18000805c  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180008061  mov     r15d, eax
0x180008064  test    eax, eax
0x180008066  jns     short loc_180008087
0x180008068  mov     rcx, [r12+58h]
0x18000806d  test    rcx, rcx
0x180008070  jz      loc_180008EE5
0x180008076  mov     dword ptr [rsp+350h+var_328], eax
0x18000807a  mov     dword ptr [rsp+350h+var_330], 495h
0x180008082  jmp     loc_180008EBD
0x180008087  lea     r15, [r12+2E8h]
0x18000808f  mov     rbx, [r15]
0x180008092  test    rbx, rbx
0x180008095  jz      short loc_1800080BA
0x180008097  call    cs:__imp_GetProcessHeap
0x18000809d  mov     rcx, rax; hHeap
0x1800080a0  lea     r8, [rbx-4]; lpMem
0x1800080a4  xor     edx, edx; dwFlags
0x1800080a6  call    cs:__imp_HeapFree
0x1800080ac  xor     ecx, ecx
0x1800080ae  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800080b3  mov     qword ptr [r15], 0
0x1800080ba  mov     r9, r15
0x1800080bd  xor     r8d, r8d
0x1800080c0  lea     rdx, aSourcesInstall; "sources\\install.wim"
0x1800080c7  mov     rcx, r13
0x1800080ca  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800080cf  mov     r15d, eax
0x1800080d2  mov     rcx, [r12+58h]
0x1800080d7  test    eax, eax
0x1800080d9  jns     short loc_1800080F5
0x1800080db  test    rcx, rcx
0x1800080de  jz      loc_180008EE5
0x1800080e4  mov     dword ptr [rsp+350h+var_328], eax
0x1800080e8  mov     dword ptr [rsp+350h+var_330], 49Bh
0x1800080f0  jmp     loc_180008EBD
0x1800080f5  mov     rbx, [rsp+350h+var_300]
0x1800080fa  test    rcx, rcx
0x1800080fd  jz      short loc_180008113
0x1800080ff  mov     r9, rbx
0x180008102  lea     r8, aWimlayoutOpeni; "WimLayout: Opening ESD package file: [%"...
0x180008109  mov     edx, 2
0x18000810e  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180008113  mov     [rsp+350h+var_328], 0
0x18000811c  mov     dword ptr [rsp+350h+var_330], 0
0x180008124  mov     edx, 80000000h
0x180008129  mov     r9d, 20000000h
0x18000812f  mov     r8d, 3
0x180008135  mov     rcx, rbx
0x180008138  call    cs:__imp_WIMCreateFile
0x18000813e  mov     rdi, rax
0x180008141  test    rax, rax
0x180008144  jnz     short loc_18000819A
0x180008146  mov     [rsp+350h+var_2E0], rax
0x18000814b  call    cs:__imp_GetLastError
0x180008151  mov     r15d, eax
0x180008154  test    eax, eax
0x180008156  jnz     short loc_180008160
0x180008158  mov     r15d, 80004005h
0x18000815e  jmp     short loc_18000816D
0x180008160  jle     short loc_18000816D
0x180008162  movzx   r15d, ax
0x180008166  or      r15d, 80070000h
0x18000816d  cmp     [r12+58h], rdi
0x180008172  jz      loc_180008EE5
0x180008178  xor     ecx, ecx
0x18000817a  test    r15d, r15d
0x18000817d  jns     loc_180008EE0
0x180008183  mov     dword ptr [rsp+350h+var_328], r15d
0x180008188  mov     dword ptr [rsp+350h+var_330], 4A6h
0x180008190  mov     rcx, [r12+58h]
0x180008195  jmp     loc_180008EBD
0x18000819a  mov     [rsp+350h+var_2E0], rdi
0x18000819f  mov     rcx, [r12+58h]
0x1800081a4  test    rcx, rcx
0x1800081a7  jz      short loc_1800081BA
0x1800081a9  lea     r8, aWimlayoutSucce; "WimLayout: Successfully opened ESD pack"...
0x1800081b0  mov     edx, 2
0x1800081b5  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800081ba  mov     ebx, 230h
0x1800081bf  mov     r8d, ebx; Size
0x1800081c2  xor     edx, edx; Val
0x1800081c4  lea     rcx, [rbp+250h+var_2A0]; void *
0x1800081c8  call    memset_0
0x1800081cd  mov     r8d, ebx
0x1800081d0  lea     rdx, [rbp+250h+var_2A0]
0x1800081d4  mov     rcx, rdi
0x1800081d7  call    cs:__imp_WIMGetAttributes
0x1800081dd  test    eax, eax
0x1800081df  jnz     short loc_18000822C
0x1800081e1  call    cs:__imp_GetLastError
0x1800081e7  mov     r15d, eax
0x1800081ea  test    eax, eax
0x1800081ec  jnz     short loc_1800081F6
0x1800081ee  mov     r15d, 80004005h
0x1800081f4  jmp     short loc_180008203
0x1800081f6  jle     short loc_180008203
0x1800081f8  movzx   r15d, ax
0x1800081fc  or      r15d, 80070000h
0x180008203  cmp     qword ptr [r12+58h], 0
0x180008209  jz      loc_180008EE5
0x18000820f  xor     ecx, ecx
0x180008211  test    r15d, r15d
0x180008214  jns     loc_180008EE0
0x18000821a  mov     dword ptr [rsp+350h+var_328], r15d
0x18000821f  mov     dword ptr [rsp+350h+var_330], 4AEh
0x180008227  jmp     loc_180008190
0x18000822c  cmp     [rbp+250h+var_88], 2
0x180008233  ja      short loc_18000825B
0x180008235  mov     r15d, 8007000Dh
0x18000823b  mov     rcx, [r12+58h]
0x180008240  test    rcx, rcx
0x180008243  jz      loc_180008EE5
0x180008249  mov     dword ptr [rsp+350h+var_328], r15d
0x18000824e  mov     dword ptr [rsp+350h+var_330], 4AFh
0x180008256  jmp     loc_180008EBD
0x18000825b  mov     rax, [r12]
0x18000825f  lea     rdx, [rbp+250h+Buf2]
0x180008263  mov     rcx, r12
0x180008266  mov     rax, [rax+38h]
0x18000826a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000826f  mov     r15d, eax
0x180008272  test    eax, eax
0x180008274  jns     short loc_180008295
0x180008276  mov     rcx, [r12+58h]
0x18000827b  test    rcx, rcx
0x18000827e  jz      loc_180008EE5
0x180008284  mov     dword ptr [rsp+350h+var_328], eax
0x180008288  mov     dword ptr [rsp+350h+var_330], 4B3h
0x180008290  jmp     loc_180008EBD
0x180008295  cmp     [rbp+250h+var_84], 3
0x18000829c  jz      short loc_1800082B8
0x18000829e  mov     r8d, 10h; Size
0x1800082a4  lea     rdx, [rbp+250h+Buf2]; Buf2
0x1800082a8  lea     rcx, WINDLP_ACTION_UPGLAYOUT; Buf1
0x1800082af  call    memcmp_0
0x1800082b4  test    eax, eax
0x1800082b6  jnz     short loc_1800082F7
0x1800082b8  mov     r15, [rsp+350h+var_2F0]
0x1800082bd  mov     [rsp+350h+var_2F0], 0
0x1800082c6  mov     rbx, [r12+2E8h]
0x1800082ce  test    rbx, rbx
0x1800082d1  jz      short loc_1800082EF
0x1800082d3  call    cs:__imp_GetProcessHeap
0x1800082d9  mov     rcx, rax; hHeap
0x1800082dc  lea     r8, [rbx-4]; lpMem
0x1800082e0  xor     edx, edx; dwFlags
0x1800082e2  call    cs:__imp_HeapFree
0x1800082e8  xor     ecx, ecx
0x1800082ea  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800082ef  mov     [r12+2E8h], r15
0x1800082f7  mov     rdx, rdi; void *
0x1800082fa  mov     rcx, r12; this
0x1800082fd  call    ?WimDetermineImages@CDlpActionWimLayout@@AEAAJPEAXH@Z; CDlpActionWimLayout::WimDetermineImages(void *,int)
0x180008302  mov     r15d, eax
0x180008305  mov     rcx, [r12+58h]
0x18000830a  test    eax, eax
0x18000830c  jns     short loc_180008328
0x18000830e  test    rcx, rcx
0x180008311  jz      loc_180008EE5
0x180008317  mov     dword ptr [rsp+350h+var_328], eax
0x18000831b  mov     dword ptr [rsp+350h+var_330], 4BEh
0x180008323  jmp     loc_180008EBD
0x180008328  test    rcx, rcx
0x18000832b  jz      short loc_180008351
0x18000832d  mov     eax, [r12+2F8h]
0x180008335  mov     dword ptr [rsp+350h+var_330], eax
0x180008339  mov     r9d, [rbp+250h+var_88]
0x180008340  lea     r8, aWimlayoutEsdPa_0; "WimLayout: ESD package info: %d images,"...
0x180008347  mov     edx, 2
0x18000834c  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180008351  mov     rcx, [r12+58h]
0x180008356  test    rcx, rcx
0x180008359  jz      short loc_180008387
0x18000835b  mov     eax, [rbp+250h+var_7C]
0x180008361  mov     dword ptr [rsp+350h+var_328], eax
0x180008365  mov     eax, [rbp+250h+var_84]
0x18000836b  mov     dword ptr [rsp+350h+var_330], eax
0x18000836f  mov     r9d, [rbp+250h+var_78]
0x180008376  lea     r8, aWimlayoutEsdPa; "WimLayout: ESD package info: Flags: 0x%"...
0x18000837d  mov     edx, 2
0x180008382  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180008387  mov     rcx, [r12+58h]
0x18000838c  test    rcx, rcx
0x18000838f  jz      short loc_1800083CE
0x180008391  mov     eax, [r12+2FCh]
0x180008399  mov     [rsp+350h+var_320], eax
0x18000839d  mov     eax, [r12+308h]
0x1800083a5  mov     dword ptr [rsp+350h+var_328], eax
0x1800083a9  mov     eax, [r12+304h]
0x1800083b1  mov     dword ptr [rsp+350h+var_330], eax
0x1800083b5  mov     r9d, [r12+300h]
0x1800083bd  lea     r8, aWimlayoutLayou; "WimLayout: Layout Index: %d, WinPe Inde"...
0x1800083c4  mov     edx, 2
0x1800083c9  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800083ce  lea     rdx, [rsp+350h+bstrString]
0x1800083d3  mov     rcx, r12
0x1800083d6  call    ?GetWorkingPath@?$CDlpActionImpl@V?$CDlpErrorImpl@V?$CDlpObjectInternalImpl@V?$CUnknownImpl@VIDlpAction@@@@@@@@@@QEAAJPEAPEAG@Z; CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::GetWorkingPath(ushort * *)
0x1800083db  mov     r15d, eax
0x1800083de  test    eax, eax
0x1800083e0  jns     short loc_180008401
0x1800083e2  mov     rcx, [r12+58h]
0x1800083e7  test    rcx, rcx
0x1800083ea  jz      loc_180008EE5
0x1800083f0  mov     dword ptr [rsp+350h+var_328], eax
0x1800083f4  mov     dword ptr [rsp+350h+var_330], 4D9h
0x1800083fc  jmp     loc_180008EBD
0x180008401  lea     r9, [rsp+350h+lpFileName]
0x180008406  xor     r8d, r8d
0x180008409  lea     rdx, aD3536bdb3c4a48; "{d3536bdb-3c4a-4896-84fd-825e4d700b4f}"
0x180008410  mov     rcx, [rsp+350h+bstrString]
0x180008415  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x18000841a  mov     r15d, eax
0x18000841d  test    eax, eax
0x18000841f  jns     short loc_180008440
0x180008421  mov     rcx, [r12+58h]
0x180008426  test    rcx, rcx
0x180008429  jz      loc_180008EE5
0x18000842f  mov     dword ptr [rsp+350h+var_328], eax
0x180008433  mov     dword ptr [rsp+350h+var_330], 4DAh
0x18000843b  jmp     loc_180008EBD
0x180008440  mov     rbx, [rsp+350h+lpFileName]
0x180008445  mov     rcx, rbx
0x180008448  call    FileExists
0x18000844d  test    eax, eax
0x18000844f  jz      short loc_180008478
0x180008451  mov     eax, 800700A1h
0x180008456  mov     r15d, eax
0x180008459  mov     rcx, [r12+58h]
0x18000845e  test    rcx, rcx
0x180008461  jz      loc_180008EE5
0x180008467  mov     dword ptr [rsp+350h+var_328], eax
0x18000846b  mov     dword ptr [rsp+350h+var_330], 4DBh
0x180008473  jmp     loc_180008EBD
0x180008478  mov     rcx, rbx; lpFileName
0x18000847b  call    cs:__imp_GetFileAttributesW
0x180008481  or      r15d, 0FFFFFFFFh
0x180008485  cmp     eax, r15d
0x180008488  jz      short loc_1800084FF
0x18000848a  mov     rcx, [r12+58h]
0x18000848f  test    rcx, rcx
0x180008492  jz      short loc_1800084A8
  ... truncated ...
```
