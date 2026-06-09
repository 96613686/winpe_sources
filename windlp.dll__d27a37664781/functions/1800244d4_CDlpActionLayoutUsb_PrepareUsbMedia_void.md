# CDlpActionLayoutUsb::PrepareUsbMedia(void)

- ea: `0x1800244d4`
- end: `0x180026039`
- name: `?PrepareUsbMedia@CDlpActionLayoutUsb@@AEAAJXZ`
- size: `7013`
- prototype: `__int64 __fastcall(CDlpActionLayoutUsb *__hidden this)`
- caller_count: `1`
- callee_count: `40`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016460`

## callees

- `0x18000a4f0`
- `0x18000a950`
- `0x18000aba4`
- `0x18000abc4`
- `0x18000b9a8`
- `0x18000cad8`
- `0x180012c6c`
- `0x180012f5c`
- `0x180016a74`
- `0x180017320`
- `0x180017848`
- `0x180019448`
- `0x180019de8`
- `0x18001b704`
- `0x18001ba90`
- `0x18001c9d0`
- `0x18001fd60`
- `0x180021178`
- `0x180021988`
- `0x180023210`
- `0x1800244d4`
- `0x180027f1c`
- `0x180028640`
- `0x180029424`
- `0x1800294ac`
- `0x18002b5bc`
- `0x180039394`
- `0x180039b70`
- `0x18003e030`
- `0x18003e3c0`
- `0x18003f9f8`
- `0x180040140`
- `0x180040c1c`
- `0x180041198`
- `0x1800417a8`
- `0x180041c40`
- `0x180041f90`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180024616`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180024616`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024c82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024c9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024cc6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025ad0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025b64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024c82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024c9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024cc6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025ad0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025b64`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025ae2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025ae2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024c90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024cab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024cd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025b74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024c90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024cab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024cd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025b74`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002482d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024873`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002482d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002486b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800246e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002486b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d81`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180024551`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180024c6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180024551`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180024c6b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180024577`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800246cf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180024577`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800246cf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024c31`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024c43`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024c31`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024c43`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800247bb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800247bb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180024cfd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180024cfd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024fc7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024fc7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetVolumeLabelW` at `0x180025d6b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetVolumeLabelW` at `0x180025d6b`

## string_xrefs

- `0x180024570`: `dismapi.dll`
- `0x180024694`: `System32\migwiz\MigApp.dll`
- `0x180024e59`: `LayoutUsb: Source directory size -> [%I64u] bytes`
- `0x180024e76`: `LayoutUsb: Target directory size -> [%I64u] bytes`
- `0x180025e94`: `LayoutUsb: Copying files to [%s]...`
- `0x180024fd3`: `InitVDSServiceNoStatic:Loading VDS service... `
- `0x180024f90`: `InitVDSServiceNoStatic:Creating VDS loader...`
- `0x180025046`: `InitVDSServiceNoStatic: Failed to load VDS service; hr = 0x%x.`
- `0x18002501f`: `InitVDSServiceNoStatic:Successfully launched service.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CDlpActionLayoutUsb::PrepareUsbMedia(CDlpActionLayoutUsb *this)
{
  int DataSize; // esi
  int v3; // edi
  const unsigned __int16 *v4; // r13
  const unsigned __int16 *v5; // r8
  signed int LastError; // eax
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  unsigned int v14; // eax
  HRESULT v15; // eax
  __int64 v16; // rcx
  DWORD v17; // eax
  int v18; // ebx
  const unsigned __int16 *v19; // rdx
  int v20; // eax
  const unsigned __int16 *v21; // rdx
  const unsigned __int16 *v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rcx
  int TempDir; // eax
  int v26; // eax
  __int64 v27; // rcx
  int v28; // eax
  int DriversSize; // eax
  unsigned __int64 v30; // rsi
  char *v31; // rbx
  char *v32; // r13
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // rcx
  UINT v37; // ebx
  void *v38; // rbx
  HANDLE v39; // rax
  HANDLE v40; // rax
  WCHAR *v41; // rbx
  HANDLE v42; // rax
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  int v47; // eax
  int MaxFileSize; // eax
  unsigned __int64 v49; // rbx
  unsigned __int64 v50; // rsi
  int v51; // eax
  unsigned int v52; // ebx
  int DiskSize; // eax
  unsigned __int64 v54; // rsi
  const wchar_t *v55; // r9
  __int64 v56; // rcx
  unsigned int v57; // r13d
  __int64 v58; // rcx
  int v59; // eax
  __int64 v60; // rcx
  unsigned int v61; // r13d
  int v62; // eax
  __int64 v63; // rcx
  int v64; // eax
  int v65; // eax
  int v66; // eax
  int v67; // eax
  int v68; // eax
  __int64 v69; // r8
  struct IVdsService *v70; // rbx
  int Partition; // eax
  int v72; // eax
  LPVOID v73; // r13
  int v74; // eax
  int v75; // ebx
  int v76; // eax
  __int64 v77; // rcx
  __int64 v78; // rcx
  unsigned int v79; // ebx
  int PartitionInfo; // eax
  int v81; // eax
  int v82; // eax
  int v83; // eax
  unsigned int v84; // ebx
  const wchar_t *v85; // rax
  __int64 v86; // rcx
  int v87; // eax
  __int64 v88; // r9
  signed int v89; // ebx
  int v90; // eax
  int v91; // eax
  int v92; // eax
  unsigned __int16 v93; // r13
  unsigned __int64 v94; // rbx
  unsigned __int16 v95; // cx
  HANDLE ProcessHeap; // rax
  void *v97; // r8
  unsigned __int16 v98; // bx
  unsigned int i; // edx
  unsigned __int16 v100; // dx
  HANDLE v101; // rax
  unsigned __int16 v102; // cx
  unsigned __int16 v103; // ax
  unsigned __int16 v104; // ax
  int v105; // eax
  int v106; // eax
  __int64 v107; // rcx
  int v108; // eax
  signed int v109; // eax
  __int64 v110; // rcx
  int v111; // eax
  int v112; // eax
  __int64 v113; // rcx
  __int64 v114; // rcx
  int v115; // eax
  __int64 v116; // rcx
  int v117; // eax
  int v118; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v120; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v121; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpRootPathName; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v123; // [rsp+48h] [rbp-B8h] BYREF
  struct IVdsService *v124; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v125; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v126; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v127; // [rsp+68h] [rbp-98h] BYREF
  __int64 v128; // [rsp+70h] [rbp-90h] BYREF
  struct IVdsAdvancedDisk *v129; // [rsp+78h] [rbp-88h] BYREF
  struct IVdsDisk *v130; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v131; // [rsp+88h] [rbp-78h] BYREF
  LPVOID v132; // [rsp+90h] [rbp-70h] BYREF
  UINT uMode; // [rsp+98h] [rbp-68h]
  HMODULE hLibModule; // [rsp+A0h] [rbp-60h]
  HMODULE Library; // [rsp+A8h] [rbp-58h]
  int v136; // [rsp+B0h] [rbp-50h]
  LPVOID lpMem; // [rsp+B8h] [rbp-48h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Buffer[520]; // [rsp+D0h] [rbp-30h] BYREF

  DataSize = 0;
  v3 = 0;
  v136 = 0;
  v124 = 0;
  lpLibFileName[0] = 0;
  v4 = 0;
  lpRootPathName = 0;
  v132 = 0;
  v127 = 0;
  v125 = 0;
  v129 = 0;
  v123 = 0;
  v126 = 0;
  lpLibFileName[1] = 0;
  lpMem = 0;
  LODWORD(v130) = 0;
  hLibModule = 0;
  uMode = SetErrorMode(1u);
  if ( (*((_BYTE *)this + 1368) & 0x40) != 0 )
  {
    hLibModule = LoadLibraryExW(L"dismapi.dll", 0, 0x800u);
    if ( !hLibModule )
    {
      LastError = GetLastError();
      DataSize = LastError;
      if ( LastError > 0 )
        DataSize = (unsigned __int16)LastError | 0x80070000;
      if ( *((_QWORD *)this + 11) )
      {
        v7 = 0;
        if ( DataSize < 0 )
        {
          v8 = CDlpLogT<CEmptyType>::DlpLogFormat(
                 *((_QWORD *)this + 11),
                 4,
                 L"%s(%d): Result = 0x%X",
                 L"CDlpActionLayoutUsb::PrepareUsbMedia",
                 2888,
                 DataSize);
          v7 = (unsigned int)v8;
          if ( v8 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v8);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
      }
      goto LABEL_120;
    }
  }
  Library = 0;
  if ( *((char *)this + 1368) < 0 )
  {
    memset_0(Buffer, 0, sizeof(Buffer));
    if ( !GetSystemWindowsDirectoryW(Buffer, 0x208u) )
    {
      DataSize = GetLastError();
      if ( DataSize )
      {
        if ( DataSize > 0 )
          DataSize = (unsigned __int16)DataSize | 0x80070000;
      }
      else
      {
        DataSize = -2147467259;
      }
      if ( !*((_QWORD *)this + 11) )
        goto LABEL_116;
      LODWORD(v120) = DataSize;
      LODWORD(ppv) = 2897;
      goto LABEL_18;
    }
    v12 = CMiscHelpersT<CEmptyType>::CombinePath(Buffer, L"System32\\migwiz\\MigApp.dll", 0, lpLibFileName);
    DataSize = v12;
    if ( v12 < 0 )
    {
      v9 = *((_QWORD *)this + 11);
      if ( !v9 )
        goto LABEL_116;
      LODWORD(v120) = v12;
      LODWORD(ppv) = 2900;
      goto LABEL_19;
    }
    Library = LoadLibraryExW(lpLibFileName[0], 0, 8u);
    DataSize = 0;
    if ( !Library )
    {
      DataSize = GetLastError();
      if ( DataSize > 0 )
        DataSize = (unsigned __int16)DataSize | 0x80070000;
      if ( !*((_QWORD *)this + 11) )
        goto LABEL_116;
      v11 = 0;
      if ( DataSize >= 0 )
        goto LABEL_21;
      LODWORD(v120) = DataSize;
      LODWORD(ppv) = 2902;
      goto LABEL_18;
    }
  }
  if ( *((_WORD *)this + 680) && (*((_BYTE *)this + 1368) & 8) == 0 )
  {
    v13 = CDlpActionLayoutUsb::CheckBitLocker(this, (int *)&v126 + 1);
    DataSize = v13;
    if ( v13 < 0 )
    {
      v9 = *((_QWORD *)this + 11);
      if ( !v9 )
        goto LABEL_116;
      LODWORD(v120) = v13;
      LODWORD(ppv) = 2910;
      goto LABEL_19;
    }
    DataSize = 0;
    if ( HIDWORD(v126) )
    {
      DataSize = -1048575733;
      v9 = *((_QWORD *)this + 11);
      if ( !v9 )
        goto LABEL_116;
      LODWORD(v120) = -1048575733;
      LODWORD(ppv) = 2911;
      goto LABEL_19;
    }
  }
  v14 = -1;
  if ( !*((_WORD *)this + 680) && (*((_BYTE *)this + 1368) & 0x10) != 0 )
  {
    LODWORD(v128) = -1;
    goto LABEL_59;
  }
  v15 = CoInitializeEx(0, 0);
  if ( v15 < 0 )
  {
    if ( v15 != -2147417850 )
    {
      DataSize = v15;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v15);
    }
  }
  else
  {
    v3 = 1;
    v136 = 1;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)DataSize);
  if ( DataSize < 0 )
  {
    v9 = *((_QWORD *)this + 11);
    if ( !v9 )
      goto LABEL_116;
    LODWORD(v120) = DataSize;
    LODWORD(ppv) = 2919;
    goto LABEL_19;
  }
  v16 = *((unsigned __int16 *)this + 680);
  v131 = 0;
  if ( (unsigned __int16)(v16 - 97) <= 0x19u || (unsigned __int16)(v16 - 65) <= 0x19u )
  {
    if ( (unsigned int)GetDiskAndOffsetFromDriveLetter(v16, &v123, &v131) == 1 )
    {
      v17 = 0;
      v18 = 1;
    }
    else
    {
      v18 = 0;
      v17 = GetLastError();
    }
    SetLastError(v17);
    if ( v18 )
    {
      v14 = v123;
      LODWORD(v128) = v123;
LABEL_59:
      v123 = v14;
      v19 = (const unsigned __int16 *)*((_QWORD *)this + 111);
      if ( v19 )
      {
        v20 = CDlpActionLayoutUsb::PopulateSwmPaths(this, v19);
        DataSize = v20;
        if ( v20 < 0 )
        {
          v9 = *((_QWORD *)this + 11);
          if ( !v9 )
            goto LABEL_116;
          LODWORD(v120) = v20;
          LODWORD(ppv) = 2938;
          goto LABEL_19;
        }
      }
      if ( (*((_BYTE *)this + 1368) & 0x20) != 0 )
      {
        DataSize = CDlpActionLayoutUsb::PopulateOemPaths(
                     this,
                     *((const unsigned __int16 **)this + 111),
                     *((const unsigned __int16 **)this + 112),
                     *((const unsigned __int16 **)this + 114),
                     *((const unsigned __int16 **)this + 115),
                     L"sources",
                     1);
        if ( DataSize < 0 )
        {
          v9 = *((_QWORD *)this + 11);
          if ( !v9 )
            goto LABEL_116;
          LODWORD(v120) = DataSize;
          LODWORD(ppv) = 2950;
          goto LABEL_19;
        }
        v21 = (const unsigned __int16 *)*((_QWORD *)this + 116);
        if ( v21 )
        {
          DataSize = CDlpActionLayoutUsb::PopulateOemPaths(this, v21, 0, 0, 0, L"sources\\recovery\\old", 0);
          if ( DataSize < 0 )
          {
            v9 = *((_QWORD *)this + 11);
            if ( !v9 )
              goto LABEL_116;
            LODWORD(v120) = DataSize;
            LODWORD(ppv) = 2954;
            goto LABEL_19;
          }
        }
      }
      v22 = (const unsigned __int16 *)*((_QWORD *)this + 117);
      if ( v22 )
      {
        DataSize = CDlpActionLayoutUsb::PopulateCloudPath(this, v22, v5);
        if ( DataSize < 0 )
        {
          v9 = *((_QWORD *)this + 11);
          if ( !v9 )
            goto LABEL_116;
          LODWORD(v120) = DataSize;
          LODWORD(ppv) = 2962;
          goto LABEL_19;
        }
      }
      if ( !*((_QWORD *)this + 118) )
        goto LABEL_91;
      v23 = *((_QWORD *)this + 11);
      if ( v23 )
      {
        *((_QWORD *)this + 164) = v23;
        *((_DWORD *)this + 326) = 1;
        TempDir = CMiscHelpersT<CEmptyType>::GetTempDir((char *)this + 1264);
        DataSize = TempDir;
        if ( TempDir >= 0 )
          goto LABEL_85;
        v24 = *((_QWORD *)this + 164);
        if ( !v24 )
          goto LABEL_85;
        LODWORD(v120) = TempDir;
        LODWORD(ppv) = 65;
      }
      else
      {
        DataSize = -2147024809;
        v24 = *((_QWORD *)this + 164);
        if ( !v24 )
          goto LABEL_85;
        LODWORD(v120) = -2147024809;
        LODWORD(ppv) = 60;
      }
      v26 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v24,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpWimCapture::Initialize",
              ppv,
              v120);
      v27 = (unsigned int)v26;
      if ( v26 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v26);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v27);
LABEL_85:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)DataSize);
      if ( DataSize < 0 )
      {
        v9 = *((_QWORD *)this + 11);
        if ( !v9 )
          goto LABEL_116;
        LODWORD(v120) = DataSize;
        LODWORD(ppv) = 2969;
        goto LABEL_19;
      }
      v28 = CDlpWimCapture::Gather((char *)this + 1192, *((_QWORD *)this + 118), (char *)this + 1144);
      DataSize = v28;
      if ( v28 < 0 )
      {
        v9 = *((_QWORD *)this + 11);
        if ( !v9 )
          goto LABEL_116;
        LODWORD(v120) = v28;
        LODWORD(ppv) = 2970;
        goto LABEL_19;
      }
LABEL_91:
      DataSize = CDlpActionLayoutUsb::GetDataSize(this, (unsigned __int64 *)&v132, (unsigned __int64 *)&v127);
      if ( DataSize < 0 )
      {
        v9 = *((_QWORD *)this + 11);
        if ( !v9 )
          goto LABEL_116;
        LODWORD(v120) = DataSize;
        LODWORD(ppv) = 2975;
        goto LABEL_19;
      }
      v131 = 0;
      if ( (*((_BYTE *)this + 1368) & 0x40) != 0 )
      {
        DriversSize = CDlpActionLayoutUsb::GetDriversSize(this, hLibModule, &v131);
        DataSize = DriversSize;
        v9 = *((_QWORD *)this + 11);
        if ( DriversSize < 0 )
        {
          if ( !v9 )
            goto LABEL_116;
          LODWORD(v120) = DriversSize;
          LODWORD(ppv) = 2982;
          goto LABEL_19;
        }
        v30 = v131;
        if ( v9 )
          CDlpLogT<CEmptyType>::DlpLogFormat(v9, 2, L"LayoutUsb: Driver size estimation -> [%I64u] bytes", v131);
        v31 = (char *)v132;
        if ( (char *)v132 + v30 < v132 )
        {
          DataSize = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v31 = (char *)v132 + v30;
          DataSize = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)DataSize);
        if ( DataSize < 0 )
        {
          v9 = *((_QWORD *)this + 11);
          if ( !v9 )
            goto LABEL_116;
          LODWORD(v120) = DataSize;
          LODWORD(ppv) = 2984;
          goto LABEL_19;
        }
        v32 = (char *)v127;
        if ( (char *)v127 + v131 < v127 )
        {
          DataSize = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v32 = (char *)v127 + v131;
          DataSize = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)DataSize);
        if ( DataSize < 0 )
        {
          v33 = *((_QWORD *)this + 11);
          if ( v33 )
          {
            LODWORD(v120) = DataSize;
            LODWORD(ppv) = 2985;
LABEL_112:
            v34 = CDlpLogT<CEmptyType>::DlpLogFormat(
                    v33,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDlpActionLayoutUsb::PrepareUsbMedia",
                    ppv,
                    v120);
            v35 = (unsigned int)v34;
            if ( v34 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v34);
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v35);
            goto LABEL_115;
          }
          goto LABEL_115;
        }
      }
      else
      {
        v31 = (char *)v132;
        v32 = (char *)v127;
      }
      HIDWORD(v126) = 0;
      if ( *((char *)this + 1368) < 0 )
      {
        DataSize = CDlpActionLayoutUsb::DiscoverApps(this, Library, (int *)&v126 + 1);
        if ( DataSize < 0 )
        {
          v33 = *((_QWORD *)this + 11);
          if ( v33 )
          {
            LODWORD(v120) = DataSize;
            LODWORD(ppv) = 2993;
            goto LABEL_112;
          }
LABEL_115:
          v4 = lpRootPathName;
          goto LABEL_116;
        }
        if ( HIDWORD(v126) )
        {
          v44 = *((_QWORD *)this + 11);
          if ( v44 )
            CDlpLogT<CEmptyType>::DlpLogFormat(
              v44,
              2,
              L"LayoutUsb: Registered app estimation -> Source [%I64u] bytes, Target [%I64u] bytes",
              0x100000000LL,
              0x80000000LL);
          if ( v31 + 0x100000000LL < v31 )
          {
            DataSize = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v31 += 0x100000000LL;
            DataSize = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)DataSize);
          if ( DataSize < 0 )
          {
            v33 = *((_QWORD *)this + 11);
            if ( v33 )
            {
              LODWORD(v120) = DataSize;
              LODWORD(ppv) = 3000;
              goto LABEL_112;
            }
            goto LABEL_115;
          }
          if ( v32 + 0x80000000LL < v32 )
          {
            DataSize = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v32 += 0x80000000LL;
            DataSize = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)DataSize);
          if ( DataSize < 0 )
          {
            v33 = *((_QWORD *)this + 11);
            if ( v33 )
            {
              LODWORD(v120) = DataSize;
              LODWORD(ppv) = 3001;
              goto LABEL_112;
            }
            goto LABEL_115;
          }
        }
      }
      v45 = *((_QWORD *)this + 11);
      if ( v45 )
        CDlpLogT<CEmptyType>::DlpLogFormat(v45, 2, L"LayoutUsb: Source directory size -> [%I64u] bytes", v31);
      v46 = *((_QWORD *)this + 11);
      if ( v46 )
        CDlpLogT<CEmptyType>::DlpLogFormat(v46, 2, L"LayoutUsb: Target directory size -> [%I64u] bytes", v32);
      v47 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(this);
      DataSize = v47;
      if ( v47 < 0 )
      {
        v33 = *((_QWORD *)this + 11);
        if ( v33 )
        {
          LODWORD(v120) = v47;
          LODWORD(ppv) = 3007;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      MaxFileSize = CDlpActionLayoutUsb::GetMaxFileSize(this, (unsigned __int64 *)&v129);
      DataSize = MaxFileSize;
      v33 = *((_QWORD *)this + 11);
      if ( MaxFileSize < 0 )
      {
        if ( v33 )
        {
          LODWORD(v120) = MaxFileSize;
          LODWORD(ppv) = 3011;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      if ( v33 )
        CDlpLogT<CEmptyType>::DlpLogFormat(v33, 2, L"LayoutUsb: Source maximum file size -> [%I64u] bytes", v129);
      DataSize = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(this);
      if ( DataSize < 0 )
      {
        v33 = *((_QWORD *)this + 11);
        if ( v33 )
        {
          LODWORD(v120) = DataSize;
          LODWORD(ppv) = 3013;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      DataSize = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::SetProgress(
                   this,
                   v31,
                   0);
      if ( DataSize < 0 )
      {
        v33 = *((_QWORD *)this + 11);
        if ( v33 )
        {
          LODWORD(v120) = DataSize;
          LODWORD(ppv) = 3019;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      if ( *((_WORD *)this + 680) || (*((_BYTE *)this + 1368) & 0x10) == 0 )
      {
        v132 = 0;
        v127 = 0;
        v124 = 0;
        LibLog(&g_VdsLibLog, 0x4000000, L"InitVDSServiceNoStatic:Creating VDS loader...");
        DataSize = CoCreateInstance(&CLSID_VdsLoader, 0, 0x10004u, &IID_IVdsServiceLoader, &v132);
        if ( DataSize < 0
          || (LibLog(&g_VdsLibLog, 0x4000000, L"InitVDSServiceNoStatic:Loading VDS service... "),
              DataSize = (*(__int64 (__fastcall **)(LPVOID, _QWORD, LPVOID *))(*(_QWORD *)v132 + 24LL))(v132, 0, &v127),
              DataSize < 0)
          || (DataSize = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v127 + 32LL))(v127), DataSize < 0) )
        {
          LibLog(
            &g_VdsLibLog,
            0x2000000,
            L"InitVDSServiceNoStatic: Failed to load VDS service; hr = 0x%x.",
            (unsigned int)DataSize);
        }
        else
        {
          LibLog(&g_VdsLibLog, 0x4000000, L"InitVDSServiceNoStatic:Successfully launched service.");
          v124 = (struct IVdsService *)v127;
        }
        if ( v132 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v132 + 16LL))(v132);
        if ( DataSize < 0 )
        {
          v33 = *((_QWORD *)this + 11);
          if ( v33 )
          {
            LODWORD(v120) = DataSize;
            LODWORD(ppv) = 3026;
            goto LABEL_112;
          }
          goto LABEL_115;
        }
        v51 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(this);
        DataSize = v51;
        if ( v51 < 0 )
        {
          v33 = *((_QWORD *)this + 11);
          if ( v33 )
          {
            LODWORD(v120) = v51;
            LODWORD(ppv) = 3027;
            goto LABEL_112;
          }
          goto LABEL_115;
        }
        v52 = v128;
        DiskSize = GetDiskSize(v124, v128, &v125);
        DataSize = DiskSize;
        if ( DiskSize < 0 )
        {
          v33 = *((_QWORD *)this + 11);
          if ( v33 )
          {
            LODWORD(v120) = DiskSize;
            LODWORD(ppv) = 3031;
            goto LABEL_112;
          }
          goto LABEL_115;
        }
        DataSize = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(this);
        v33 = *((_QWORD *)this + 11);
        if ( DataSize < 0 )
        {
          if ( v33 )
          {
            LODWORD(v120) = DataSize;
            LODWORD(ppv) = 3032;
            goto LABEL_112;
          }
          goto LABEL_115;
        }
        v50 = v125;
        if ( v33 )
        {
          CDlpLogT<CEmptyType>::DlpLogFormat(v33, 2, L"LayoutUsb: Disk [%d] size -> [%I64u] bytes", v52, v125);
          v33 = *((_QWORD *)this + 11);
        }
        else
        {
          v33 = 0;
        }
        if ( !v50 )
        {
          DataSize = -1048575722;
          if ( v33 )
          {
            LODWORD(v120) = -1048575722;
            LODWORD(ppv) = 3034;
            goto LABEL_112;
          }
          goto LABEL_115;
        }
        v49 = *((_QWORD *)this + 172) & -(__int64)(*((_QWORD *)this + 172) < v50);
      }
      else
      {
        v49 = 0;
        v50 = v125;
      }
      DataSize = CDlpActionLayoutUsb::SendActionMessage(this, 0, v123, v50, v32, v129);
      if ( DataSize < 0 )
      {
        v33 = *((_QWORD *)this + 11);
        if ( v33 )
        {
          LODWORD(v120) = DataSize;
          LODWORD(ppv) = 3061;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      if ( *((_WORD *)this + 680) || (*((_BYTE *)this + 1368) & 0x10) == 0 )
      {
        if ( v49 )
        {
          if ( (unsigned __int64)v32 >= v49 )
          {
            DataSize = -1048575731;
            v33 = *((_QWORD *)this + 11);
            if ( v33 )
            {
              LODWORD(v120) = -1048575731;
              LODWORD(ppv) = 3070;
              goto LABEL_112;
            }
            goto LABEL_115;
          }
          v54 = v125;
        }
        else
        {
          v54 = v125;
          if ( (unsigned __int64)v32 >= v125 )
          {
            DataSize = -1048575732;
            v33 = *((_QWORD *)this + 11);
            if ( v33 )
            {
              LODWORD(v120) = -1048575732;
              LODWORD(ppv) = 3076;
              goto LABEL_112;
            }
            goto LABEL_115;
          }
        }
        if ( !*((_DWORD *)this + 341) )
        {
          if ( (v54 <= 0x800000000LL || v49 - 1 <= 0x7FFFFFFFFLL) && (unsigned __int64)v129 <= 0xFFFFFFFF )
          {
            *((_DWORD *)this + 341) = 2;
            v55 = L"FAT32";
          }
          else
          {
            *((_DWORD *)this + 341) = 1;
            v55 = L"NTFS";
          }
          v56 = *((_QWORD *)this + 11);
          if ( v56 )
            CDlpLogT<CEmptyType>::DlpLogFormat(v56, 2, L"LayoutUsb: Automatic file system selection: [%s]", v55);
        }
        if ( *((_DWORD *)this + 341) == 2 )
        {
          if ( (unsigned __int64)v129 > 0xFFFFFFFF )
          {
            DataSize = -1048575730;
            v33 = *((_QWORD *)this + 11);
            if ( v33 )
            {
              LODWORD(v120) = -1048575730;
              LODWORD(ppv) = 3110;
              goto LABEL_112;
            }
            goto LABEL_115;
          }
          if ( v54 > 0x800000000LL && v49 - 1 > 0x7FFFFFFFFLL )
          {
            DataSize = -1048575729;
            v33 = *((_QWORD *)this + 11);
            if ( v33 )
            {
              LODWORD(v120) = -1048575729;
              LODWORD(ppv) = 3116;
              goto LABEL_112;
            }
            goto LABEL_115;
          }
        }
      }
      if ( (*((_BYTE *)this + 1368) & 1) == 0 )
      {
        v57 = v128;
        DataSize = IsDiskEmptyOfFiles(v124, v128, (int *)&v126);
        if ( DataSize < 0 )
        {
          v33 = *((_QWORD *)this + 11);
          if ( v33 )
          {
            LODWORD(v120) = DataSize;
            LODWORD(ppv) = 3126;
            goto LABEL_112;
          }
          goto LABEL_115;
        }
        if ( !(_DWORD)v126 )
        {
          v58 = *((_QWORD *)this + 11);
          if ( v58 )
            CDlpLogT<CEmptyType>::DlpLogFormat(
              v58,
              4,
              L"LayoutUsb: A volume on disk [%d] contains data. Aborting operation.",
              v57);
          DataSize = -1048575742;
          v33 = *((_QWORD *)this + 11);
          if ( !v33 )
            goto LABEL_115;
          LODWORD(v120) = -1048575742;
          LODWORD(ppv) = 3132;
          goto LABEL_112;
        }
        v59 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(this);
        DataSize = v59;
        if ( v59 < 0 )
        {
          v33 = *((_QWORD *)this + 11);
          if ( v33 )
          {
            LODWORD(v120) = v59;
            LODWORD(ppv) = 3133;
            goto LABEL_112;
          }
          goto LABEL_115;
        }
      }
      v60 = *((_QWORD *)this + 11);
      if ( (*((_BYTE *)this + 1368) & 2) != 0 )
      {
        if ( v60 )
          CDlpLogT<CEmptyType>::DlpLogFormat(
            v60,
            2,
            L"LayoutUsb: Skipped disk prep for drive %c",
            *((unsigned __int16 *)this + 680));
        v111 = STRAPI_Format((unsigned __int16 **)&lpRootPathName, L"%c:\\", *((unsigned __int16 *)this + 680));
        DataSize = v111;
        if ( v111 < 0 )
        {
          v33 = *((_QWORD *)this + 11);
          if ( v33 )
          {
            LODWORD(v120) = v111;
            LODWORD(ppv) = 3243;
            goto LABEL_112;
          }
          goto LABEL_115;
        }
        goto LABEL_412;
      }
      v61 = v123;
      if ( v60 )
        CDlpLogT<CEmptyType>::DlpLogFormat(v60, 2, L"LayoutUsb: Wiping disk [%u]", v123);
      v62 = CDlpActionLayoutUsb::SendActionMessage(this, 1);
      DataSize = v62;
      if ( v62 < 0 )
      {
        v33 = *((_QWORD *)this + 11);
        if ( v33 )
        {
          LODWORD(v120) = v62;
          LODWORD(ppv) = 3141;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      DataSize = WipeDisk(v124, v61);
      if ( DataSize == -2147024891 )
      {
        v63 = *((_QWORD *)this + 11);
        if ( v63 )
          CDlpLogT<CEmptyType>::DlpLogFormat(v63, 3, L"LayoutUsb: Retrying wipe of disk [%u]", v61);
        v64 = WipeDisk(v124, v61);
        DataSize = v64;
        if ( v64 < 0 )
        {
          v33 = *((_QWORD *)this + 11);
          if ( v33 )
          {
            LODWORD(v120) = v64;
            LODWORD(ppv) = 3146;
            goto LABEL_112;
          }
          goto LABEL_115;
        }
      }
      else if ( DataSize < 0 )
      {
        v33 = *((_QWORD *)this + 11);
        if ( v33 )
        {
          LODWORD(v120) = DataSize;
          LODWORD(ppv) = 3150;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      v65 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(this);
      DataSize = v65;
      v33 = *((_QWORD *)this + 11);
      if ( v65 < 0 )
      {
        if ( v33 )
        {
          LODWORD(v120) = v65;
          LODWORD(ppv) = 3152;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      if ( v33 )
        CDlpLogT<CEmptyType>::DlpLogFormat(v33, 2, L"LayoutUsb: Converting partition layout to MBR on disk [%u]", v61);
      v66 = CDlpActionLayoutUsb::SendActionMessage(this, 2);
      DataSize = v66;
      if ( v66 < 0 )
      {
        v33 = *((_QWORD *)this + 11);
        if ( v33 )
        {
          LODWORD(v120) = v66;
          LODWORD(ppv) = 3157;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      v67 = ConvertDiskStyle(v124, v61, 1u);
      DataSize = v67;
      if ( v67 != -2147210971 && v67 < 0 )
      {
        v33 = *((_QWORD *)this + 11);
        if ( v33 )
        {
          LODWORD(v120) = v67;
          LODWORD(ppv) = 3158;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      v68 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(this);
      DataSize = v68;
      v33 = *((_QWORD *)this + 11);
      if ( v68 < 0 )
      {
        if ( v33 )
        {
          LODWORD(v120) = v68;
          LODWORD(ppv) = 3159;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      if ( v33 )
        CDlpLogT<CEmptyType>::DlpLogFormat(v33, 2, L"LayoutUsb: Creating partition on disk [%u]", v61);
      DataSize = CDlpActionLayoutUsb::SendActionMessage(this, 4);
      if ( DataSize < 0 )
      {
        v33 = *((_QWORD *)this + 11);
        if ( v33 )
        {
          LODWORD(v120) = DataSize;
          LODWORD(ppv) = 3164;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      v127 = 0;
      v121 = (unsigned __int16 *)v49;
      v70 = v124;
      Partition = CreatePartition(v124, v61, v69, 0, (unsigned __int64 *)&v127, (unsigned __int64)v121);
      DataSize = Partition;
      if ( Partition < 0 )
      {
        v33 = *((_QWORD *)this + 11);
        if ( v33 )
        {
          LODWORD(v120) = Partition;
          LODWORD(ppv) = 3166;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      v72 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(this);
      DataSize = v72;
      v33 = *((_QWORD *)this + 11);
      if ( v72 < 0 )
      {
        if ( v33 )
        {
          LODWORD(v120) = v72;
          LODWORD(ppv) = 3167;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      v73 = v127;
      v125 = (unsigned __int64)v127;
      if ( v33 )
        CDlpLogT<CEmptyType>::DlpLogFormat(
          v33,
          2,
          L"LayoutUsb: Setting as active the new partition at offset [0x%I64X]",
          v127);
      v74 = CDlpActionLayoutUsb::SendActionMessage(this, 3);
      DataSize = v74;
      if ( v74 < 0 )
      {
        v33 = *((_QWORD *)this + 11);
        if ( v33 )
        {
          LODWORD(v120) = v74;
          LODWORD(ppv) = 3172;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      v75 = SetPartitionActive(v70, v123, (unsigned __int64)v73);
      if ( (int)(v75 + 0x80000000) >= 0 && v75 != -2147212283 )
      {
        DataSize = v75;
        v33 = *((_QWORD *)this + 11);
        if ( v33 )
        {
          LODWORD(v120) = v75;
          LODWORD(ppv) = 3175;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      v76 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(this);
      DataSize = v76;
      if ( v76 < 0 )
      {
        v33 = *((_QWORD *)this + 11);
        if ( v33 )
        {
          LODWORD(v120) = v76;
          LODWORD(ppv) = 3176;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      if ( v75 == -2147212283 )
      {
        v77 = *((_QWORD *)this + 11);
        if ( v77 )
          CDlpLogT<CEmptyType>::DlpLogFormat(
            v77,
            2,
            L"LayoutUsb: Failed to set new partition at offset [0x%I64X] active - partition not found",
            v73);
        v78 = *((_QWORD *)this + 11);
        v79 = v123;
        if ( v78 )
          CDlpLogT<CEmptyType>::DlpLogFormat(v78, 2, L"LayoutUsb: Retrying partition acquisition on disk [%u]", v123);
        PartitionInfo = CDlpActionLayoutUsb::GetPartitionInfo(
                          this,
                          v79,
                          (unsigned int *)&v130,
                          (struct _DRIVE_LAYOUT_INFORMATION_EX **)&lpMem);
        DataSize = PartitionInfo;
        if ( PartitionInfo < 0 )
        {
          v33 = *((_QWORD *)this + 11);
          if ( v33 )
          {
            LODWORD(v120) = PartitionInfo;
            LODWORD(ppv) = 3187;
            goto LABEL_112;
          }
          goto LABEL_115;
        }
        if ( (_DWORD)v130 != 1 )
        {
          DataSize = -2147212283;
          v33 = *((_QWORD *)this + 11);
          if ( v33 )
          {
            LODWORD(v120) = -2147212283;
            LODWORD(ppv) = 3188;
            goto LABEL_112;
          }
          goto LABEL_115;
        }
        v73 = (LPVOID)*((_QWORD *)lpMem + 7);
        v125 = (unsigned __int64)v73;
        v81 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(this);
        DataSize = v81;
        v33 = *((_QWORD *)this + 11);
        if ( v81 < 0 )
        {
          if ( v33 )
          {
            LODWORD(v120) = v81;
            LODWORD(ppv) = 3190;
            goto LABEL_112;
          }
          goto LABEL_115;
        }
        if ( v33 )
          CDlpLogT<CEmptyType>::DlpLogFormat(
            v33,
            2,
            L"LayoutUsb: Setting as active the new partition at offset [0x%I64X]",
            v73);
        v82 = SetPartitionActive(v124, v79, (unsigned __int64)v73);
        DataSize = v82;
        if ( v82 < 0 )
        {
          v33 = *((_QWORD *)this + 11);
          if ( v33 )
          {
            LODWORD(v120) = v82;
            LODWORD(ppv) = 3193;
            goto LABEL_112;
          }
          goto LABEL_115;
        }
        v83 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(this);
        DataSize = v83;
        if ( v83 < 0 )
        {
          v33 = *((_QWORD *)this + 11);
          if ( v33 )
          {
            LODWORD(v120) = v83;
            LODWORD(ppv) = 3194;
            goto LABEL_112;
          }
          goto LABEL_115;
        }
      }
      switch ( *((_DWORD *)this + 341) )
      {
        case 1:
          v84 = 3;
          v85 = L"NTFS";
          break;
        case 2:
          v84 = 4;
          v85 = L"FAT32";
          break;
        case 3:
          v84 = 8;
          v85 = L"EXFAT";
          break;
        default:
          DataSize = -2147024883;
          v33 = *((_QWORD *)this + 11);
          if ( v33 )
          {
            LODWORD(v120) = -2147024883;
            LODWORD(ppv) = 3204;
            goto LABEL_112;
          }
          goto LABEL_115;
      }
      v86 = *((_QWORD *)this + 11);
      if ( v86 )
        CDlpLogT<CEmptyType>::DlpLogFormat(
          v86,
          2,
          L"LayoutUsb: Formatting the partition at offset [0x%I64X] with filesystem [%s]",
          v73,
          v85);
      v87 = CDlpActionLayoutUsb::SendActionMessage(this, 9);
      DataSize = v87;
      if ( v87 < 0 )
      {
        v33 = *((_QWORD *)this + 11);
        if ( v33 )
        {
          LODWORD(v120) = v87;
          LODWORD(ppv) = 3208;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      v88 = v84;
      v89 = v123;
      v90 = FormatPartitionEx(v124, v123, v73, v88);
      DataSize = v90;
      if ( v90 < 0 )
      {
        v33 = *((_QWORD *)this + 11);
        if ( v33 )
        {
          LODWORD(v120) = v90;
          LODWORD(ppv) = 3209;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      v91 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(this);
      DataSize = v91;
      v33 = *((_QWORD *)this + 11);
      if ( v91 < 0 )
      {
        if ( v33 )
        {
          LODWORD(v120) = v91;
          LODWORD(ppv) = 3210;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      if ( v33 )
        CDlpLogT<CEmptyType>::DlpLogFormat(
          v33,
          2,
          L"LayoutUsb: Assigning drive letter to partition at offset [0x%I64X]",
          v73);
      v92 = CDlpActionLayoutUsb::SendActionMessage(this, 10);
      DataSize = v92;
      if ( v92 < 0 )
      {
        v33 = *((_QWORD *)this + 11);
        if ( v33 )
        {
          LODWORD(v120) = v92;
          LODWORD(ppv) = 3215;
          goto LABEL_112;
        }
        goto LABEL_115;
      }
      v130 = 0;
      v129 = 0;
      LOWORD(v126) = 0;
      if ( !v124 || v89 < 0 || !v73 )
      {
        DataSize = -2147024809;
        goto LABEL_405;
      }
      v93 = 0;
      DataSize = GetDisk(v124, v89, &v130, &v129, 0);
      if ( DataSize < 0 )
        goto LABEL_376;
      if ( v130 && v129 )
      {
        v94 = v125;
        DataSize = InternalGetSetDriveLetter(v124, v125, (__int64)&v126);
        if ( DataSize < 0 )
          goto LABEL_377;
        v95 = v126;
        if ( (unsigned __int16)(v126 - 97) <= 0x19u )
          v95 = v126 - 32;
        LOWORD(v126) = v95;
        if ( (unsigned __int16)(v95 - 67) <= 0x17u )
        {
          DataSize = 0;
          v93 = v95;
          goto LABEL_377;
        }
        ProcessHeap = GetProcessHeap();
        v97 = HeapAlloc(ProcessHeap, 8u, 0x2A0u);
        v127 = v97;
        if ( !v97 )
        {
          DataSize = -2147024882;
LABEL_377:
          if ( v129 )
          {
            ((void (__fastcall *)(struct IVdsAdvancedDisk *))v129->lpVtbl->Release)(v129);
            v129 = 0;
          }
          if ( v130 )
            ((void (__fastcall *)(struct IVdsDisk *))v130->lpVtbl->Release)(v130);
          if ( DataSize >= 0 )
          {
            v105 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(this);
            DataSize = v105;
            v33 = *((_QWORD *)this + 11);
            if ( v105 < 0 )
            {
              if ( v33 )
              {
                LODWORD(v120) = v105;
                LODWORD(ppv) = 3218;
                goto LABEL_112;
              }
              goto LABEL_115;
            }
            if ( v33 )
            {
              LODWORD(ppv) = v93;
              CDlpLogT<CEmptyType>::DlpLogFormat(
                v33,
                2,
                L"LayoutUsb: Partition at offset [0x%I64X] has drive letter [%c]",
                v94,
                ppv);
            }
            v106 = STRAPI_Format((unsigned __int16 **)&lpRootPathName, L"%c:\\", v93);
            DataSize = v106;
            if ( v106 < 0 )
            {
              v33 = *((_QWORD *)this + 11);
              if ( v33 )
              {
                LODWORD(v120) = v106;
                LODWORD(ppv) = 3221;
                goto LABEL_112;
              }
              goto LABEL_115;
            }
            *((_WORD *)this + 680) = v93;
            if ( *((_QWORD *)this + 120) )
            {
              v107 = *((_QWORD *)this + 11);
              if ( v107 )
                CDlpLogT<CEmptyType>::DlpLogFormat(v107, 2, L"LayoutUsb: Setting volume label to: [%s]");
              v108 = CDlpActionLayoutUsb::SendActionMessage(this, 11);
              DataSize = v108;
              if ( v108 < 0 )
              {
                v33 = *((_QWORD *)this + 11);
                if ( v33 )
                {
                  LODWORD(v120) = v108;
                  LODWORD(ppv) = 3231;
                  goto LABEL_112;
                }
                goto LABEL_115;
              }
              v4 = lpRootPathName;
              if ( !SetVolumeLabelW(lpRootPathName, *((LPCWSTR *)this + 120)) )
              {
                if ( *((_QWORD *)this + 11) )
                {
                  v109 = GetLastError();
                  if ( v109 > 0 )
                    v109 = (unsigned __int16)v109 | 0x80070000;
                  CDlpLogT<CEmptyType>::DlpLogFormat(
                    *((_QWORD *)this + 11),
                    3,
                    L"LayoutUsb: Error setting volume label!  hr = [0x%X]",
                    (unsigned int)v109);
                }
                v110 = *((_QWORD *)this + 11);
                if ( v110 )
                  CDlpLogT<CEmptyType>::DlpLogFormat(v110, 2, L"LayoutUsb: Leaving volume label blank!");
              }
LABEL_413:
              if ( (*((_BYTE *)this + 1368) & 4) != 0 )
                goto LABEL_116;
              v112 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::ResetActionProgress(this);
              DataSize = v112;
              v9 = *((_QWORD *)this + 11);
              if ( v112 >= 0 )
              {
                if ( v9 )
                  CDlpLogT<CEmptyType>::DlpLogFormat(v9, 2, L"LayoutUsb: Copying files to [%s]...", v4);
                DataSize = CDlpActionLayoutUsb::CopyFileLists(this, v4);
                if ( DataSize >= 0 )
                {
                  if ( (*((_BYTE *)this + 1368) & 0x40) == 0 )
                    goto LABEL_449;
                  v113 = *((_QWORD *)this + 11);
                  if ( v113 )
                    CDlpLogT<CEmptyType>::DlpLogFormat(
                      v113,
                      2,
                      L"LayoutUsb: Exporting 3rd party drivers to [%s]...",
                      v4);
                  DataSize = CDlpActionLayoutUsb::ExportDrivers(this, hLibModule, v4, v131);
                  if ( DataSize < 0 )
                  {
                    v9 = *((_QWORD *)this + 11);
                    if ( !v9 )
                      goto LABEL_116;
                    LODWORD(v120) = DataSize;
                    LODWORD(ppv) = 3262;
                  }
                  else
                  {
LABEL_449:
                    if ( *((char *)this + 1368) >= 0 || !HIDWORD(v126) )
                      goto LABEL_435;
                    v114 = *((_QWORD *)this + 11);
                    if ( v114 )
                      CDlpLogT<CEmptyType>::DlpLogFormat(v114, 2, L"LayoutUsb: Capture registered apps to [%s]...", v4);
                    v115 = CDlpActionLayoutUsb::CaptureApps(this, Library, v4);
                    DataSize = v115;
                    if ( v115 < 0 )
                    {
                      v9 = *((_QWORD *)this + 11);
                      if ( !v9 )
                        goto LABEL_116;
                      LODWORD(v120) = v115;
                      LODWORD(ppv) = 3270;
                    }
                    else
                    {
LABEL_435:
                      v116 = *((_QWORD *)this + 11);
                      if ( v116 )
                        CDlpLogT<CEmptyType>::DlpLogFormat(v116, 2, L"LayoutUsb: Flushing volume [%s]...", v4);
                      v117 = CDlpActionLayoutUsb::SendActionMessage(this, 8);
                      DataSize = v117;
                      if ( v117 >= 0 )
                      {
                        v118 = CDlpHelpersT<CEmptyType>::FlushVolumeToDisk(v4);
                        DataSize = v118;
                        if ( v118 >= 0 )
                          goto LABEL_116;
                        v9 = *((_QWORD *)this + 11);
                        if ( !v9 )
                          goto LABEL_116;
                        LODWORD(v120) = v118;
                        LODWORD(ppv) = 3277;
                      }
                      else
                      {
                        v9 = *((_QWORD *)this + 11);
                        if ( !v9 )
                          goto LABEL_116;
                        LODWORD(v120) = v117;
                        LODWORD(ppv) = 3276;
                      }
                    }
                  }
                }
                else
                {
                  v9 = *((_QWORD *)this + 11);
                  if ( !v9 )
                    goto LABEL_116;
                  LODWORD(v120) = DataSize;
                  LODWORD(ppv) = 3255;
                }
              }
              else
              {
                if ( !v9 )
                  goto LABEL_116;
                LODWORD(v120) = v112;
                LODWORD(ppv) = 3250;
              }
              goto LABEL_19;
            }
LABEL_412:
            v4 = lpRootPathName;
            goto LABEL_413;
          }
LABEL_405:
          v33 = *((_QWORD *)this + 11);
          if ( v33 )
          {
            LODWORD(v120) = DataSize;
            LODWORD(ppv) = 3217;
            goto LABEL_112;
          }
          goto LABEL_115;
        }
        v98 = 0;
        DataSize = ((__int64 (__fastcall *)(struct IVdsService *, __int64, __int64, void *))v124->lpVtbl->QueryDriveLetters)(
                     v124,
                     67,
                     24,
                     v97);
        if ( DataSize >= 0 )
        {
          for ( i = 0; i < 0x18; ++i )
          {
            if ( *((_DWORD *)v127 + 7 * (int)i + 6) != 1 )
              break;
          }
          if ( i >= 0x18 )
          {
            DataSize = -2147467259;
          }
          else
          {
            v100 = *((_WORD *)v127 + 14 * (int)i);
            v98 = v100 - 32;
            if ( (unsigned __int16)(v100 - 97) > 0x19u )
              v98 = v100;
          }
        }
        v101 = GetProcessHeap();
        HeapFree(v101, 0, v127);
        if ( DataSize < 0 )
        {
LABEL_376:
          v94 = v125;
          goto LABEL_377;
        }
        v102 = v98 - 97;
        v103 = v98 - 32;
        if ( (unsigned __int16)(v98 - 97) > 0x19u )
          v103 = v98;
        if ( v103 >= 0x61u )
        {
          v93 = v98;
          if ( v102 <= 0x19u )
            v93 = v98 - 32;
          if ( v93 <= 0x7Au )
            goto LABEL_374;
        }
        v104 = v98;
        v93 = v98;
        if ( v102 <= 0x19u )
          v93 = v98 - 32;
        if ( v93 >= 0x41u )
        {
          if ( (unsigned __int16)(v98 - 97) <= 0x19u )
            v104 = v98 - 32;
          v93 = v104;
          if ( v104 <= 0x5Au )
          {
LABEL_374:
            LOWORD(v128) = v93;
            v94 = v125;
            DataSize = InternalGetSetDriveLetter(v124, v125, (__int64)&v128);
            goto LABEL_377;
          }
        }
      }
      DataSize = -2147024883;
      goto LABEL_376;
    }
  }
  else
  {
    SetLastError(0x57u);
  }
  DataSize = GetLastError();
  if ( DataSize )
  {
    if ( DataSize > 0 )
      DataSize = (unsigned __int16)DataSize | 0x80070000;
  }
  else
  {
    DataSize = -2147467259;
  }
  if ( !*((_QWORD *)this + 11) )
    goto LABEL_116;
  LODWORD(v120) = DataSize;
  LODWORD(ppv) = 2923;
LABEL_18:
  v9 = *((_QWORD *)this + 11);
LABEL_19:
  v10 = CDlpLogT<CEmptyType>::DlpLogFormat(
          v9,
          4,
          L"%s(%d): Result = 0x%X",
          L"CDlpActionLayoutUsb::PrepareUsbMedia",
          ppv,
          v120);
  v11 = (unsigned int)v10;
  if ( v10 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v10);
LABEL_21:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
LABEL_116:
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( Library )
    FreeLibrary(Library);
LABEL_120:
  v36 = *((_QWORD *)this + 11);
  v37 = uMode;
  if ( v36 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v36, 2, L"LayoutUsb: Restoring previous error mode: [0x%X]...", uMode);
  SetErrorMode(v37);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)DataSize);
  v38 = lpMem;
  if ( lpMem )
  {
    v39 = GetProcessHeap();
    HeapFree(v39, 0, v38);
  }
  if ( v4 )
  {
    v40 = GetProcessHeap();
    HeapFree(v40, 0, (LPVOID)(v4 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( lpLibFileName[0] )
  {
    v41 = (WCHAR *)(lpLibFileName[0] - 2);
    v42 = GetProcessHeap();
    HeapFree(v42, 0, v41);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v124 )
    ((void (__fastcall *)(struct IVdsService *))v124->lpVtbl->Release)(v124);
  if ( v3 )
    CoUninitialize();
  return (unsigned int)DataSize;
}

```

## disassembly

```asm
0x1800244d4  push    rbp
0x1800244d6  push    rbx
0x1800244d7  push    rsi
0x1800244d8  push    rdi
0x1800244d9  push    r12
0x1800244db  push    r13
0x1800244dd  push    r14
0x1800244df  push    r15
0x1800244e1  lea     rbp, [rsp-3F8h]
0x1800244e9  sub     rsp, 4F8h
0x1800244f0  mov     rax, cs:__security_cookie
0x1800244f7  xor     rax, rsp
0x1800244fa  mov     [rbp+430h+var_50], rax
0x180024501  mov     r14, rcx
0x180024504  xor     esi, esi
0x180024506  mov     edi, esi
0x180024508  mov     [rbp+430h+var_480], esi
0x18002450b  mov     [rsp+530h+var_4E0], rsi
0x180024510  mov     [rbp+430h+lpLibFileName], rsi
0x180024514  mov     r13d, esi
0x180024517  mov     [rsp+530h+lpRootPathName], rsi
0x18002451c  mov     [rbp+430h+var_4A0], rsi
0x180024520  mov     [rsp+530h+var_4C8], rsi
0x180024525  mov     [rsp+530h+var_4D8], rsi
0x18002452a  mov     [rsp+530h+var_4B8], rsi
0x18002452f  mov     [rsp+530h+var_4E8], esi
0x180024533  mov     dword ptr [rsp+530h+var_4D0+4], esi
0x180024537  mov     dword ptr [rsp+530h+var_4D0], esi
0x18002453b  mov     [rbp+430h+var_468], rsi
0x18002453f  mov     [rbp+430h+lpMem], rsi
0x180024543  mov     dword ptr [rbp+430h+var_4B0], esi
0x180024546  mov     [rbp+430h+hLibModule], rsi
0x18002454a  lea     r15d, [rsi+1]
0x18002454e  mov     ecx, r15d; uMode
0x180024551  call    cs:__imp_SetErrorMode
0x180024557  mov     [rbp+430h+uMode], eax
0x18002455a  test    byte ptr [r14+558h], 40h
0x180024562  jz      loc_1800245EA
0x180024568  xor     edx, edx; hFile
0x18002456a  mov     r8d, 800h; dwFlags
0x180024570  lea     rcx, aDismapiDll; "dismapi.dll"
0x180024577  call    cs:__imp_LoadLibraryExW
0x18002457d  mov     [rbp+430h+hLibModule], rax
0x180024581  test    rax, rax
0x180024584  jnz     short loc_1800245EA
0x180024586  call    cs:__imp_GetLastError
0x18002458c  mov     esi, eax
0x18002458e  xor     ebx, ebx
0x180024590  test    eax, eax
0x180024592  jle     short loc_18002459D
0x180024594  movzx   esi, ax
0x180024597  or      esi, 80070000h
0x18002459d  cmp     [r14+58h], rbx
0x1800245a1  jz      loc_180024C49
0x1800245a7  mov     ecx, ebx
0x1800245a9  test    esi, esi
0x1800245ab  jns     short loc_1800245E0
0x1800245ad  mov     dword ptr [rsp+530h+var_508], esi
0x1800245b1  mov     dword ptr [rsp+530h+ppv], 0B48h
0x1800245b9  lea     r9, aCdlpactionlayo_9; "CDlpActionLayoutUsb::PrepareUsbMedia"
0x1800245c0  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800245c7  mov     edx, 4
0x1800245cc  mov     rcx, [r14+58h]
0x1800245d0  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800245d5  mov     ecx, eax
0x1800245d7  test    eax, eax
0x1800245d9  jns     short loc_1800245E0
0x1800245db  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800245e0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800245e5  jmp     loc_180024C49
0x1800245ea  mov     [rbp+430h+var_488], rsi
0x1800245ee  test    byte ptr [r14+558h], 80h
0x1800245f6  jz      loc_18002471C
0x1800245fc  xor     edx, edx; Val
0x1800245fe  mov     r8d, 410h; Size
0x180024604  lea     rcx, [rbp+430h+Buffer]; void *
0x180024608  call    memset_0
0x18002460d  mov     edx, 208h; uSize
0x180024612  lea     rcx, [rbp+430h+Buffer]; lpBuffer
0x180024616  call    cs:__imp_GetSystemWindowsDirectoryW
0x18002461c  test    eax, eax
0x18002461e  jnz     short loc_18002468D
0x180024620  call    cs:__imp_GetLastError
0x180024626  mov     esi, eax
0x180024628  xor     eax, eax
0x18002462a  test    esi, esi
0x18002462c  jnz     short loc_180024635
0x18002462e  mov     esi, 80004005h
0x180024633  jmp     short loc_180024640
0x180024635  jle     short loc_180024640
0x180024637  movzx   esi, si
0x18002463a  or      esi, 80070000h
0x180024640  cmp     [r14+58h], rax
0x180024644  jz      loc_180024C25
0x18002464a  mov     ecx, eax
0x18002464c  test    esi, esi
0x18002464e  jns     short loc_180024683
0x180024650  mov     dword ptr [rsp+530h+var_508], esi
0x180024654  mov     dword ptr [rsp+530h+ppv], 0B51h
0x18002465c  mov     rcx, [r14+58h]
0x180024660  mov     edx, 4
0x180024665  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18002466c  lea     r9, aCdlpactionlayo_9; "CDlpActionLayoutUsb::PrepareUsbMedia"
0x180024673  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180024678  test    eax, eax
0x18002467a  mov     ecx, eax
0x18002467c  jns     short loc_180024683
0x18002467e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180024683  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180024688  jmp     loc_180024C25
0x18002468d  lea     r9, [rbp+430h+lpLibFileName]
0x180024691  xor     r8d, r8d
0x180024694  lea     rdx, aSystem32Migwiz; "System32\\migwiz\\MigApp.dll"
0x18002469b  lea     rcx, [rbp+430h+Buffer]
0x18002469f  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800246a4  mov     esi, eax
0x1800246a6  test    eax, eax
0x1800246a8  jns     short loc_1800246C5
0x1800246aa  mov     rcx, [r14+58h]
0x1800246ae  test    rcx, rcx
0x1800246b1  jz      loc_180024C25
0x1800246b7  mov     dword ptr [rsp+530h+var_508], eax
0x1800246bb  mov     dword ptr [rsp+530h+ppv], 0B54h
0x1800246c3  jmp     short loc_180024660
0x1800246c5  xor     edx, edx; hFile
0x1800246c7  lea     r8d, [rdx+8]; dwFlags
0x1800246cb  mov     rcx, [rbp+430h+lpLibFileName]; lpLibFileName
0x1800246cf  call    cs:__imp_LoadLibraryExW
0x1800246d5  mov     [rbp+430h+var_488], rax
0x1800246d9  xor     esi, esi
0x1800246db  test    rax, rax
0x1800246de  jnz     short loc_18002471C
0x1800246e0  call    cs:__imp_GetLastError
0x1800246e6  mov     esi, eax
0x1800246e8  xor     eax, eax
0x1800246ea  test    esi, esi
0x1800246ec  jle     short loc_1800246F7
0x1800246ee  movzx   esi, si
0x1800246f1  or      esi, 80070000h
0x1800246f7  cmp     [r14+58h], rax
0x1800246fb  jz      loc_180024C25
0x180024701  mov     ecx, eax
0x180024703  test    esi, esi
0x180024705  jns     loc_180024683
0x18002470b  mov     dword ptr [rsp+530h+var_508], esi
0x18002470f  mov     dword ptr [rsp+530h+ppv], 0B56h
0x180024717  jmp     loc_18002465C
0x18002471c  cmp     [r14+550h], si
0x180024724  jz      short loc_18002478C
0x180024726  test    byte ptr [r14+558h], 8
0x18002472e  jnz     short loc_18002478C
0x180024730  lea     rdx, [rsp+530h+var_4D0+4]; int *
0x180024735  mov     rcx, r14; this
0x180024738  call    ?CheckBitLocker@CDlpActionLayoutUsb@@AEAAJPEAH@Z; CDlpActionLayoutUsb::CheckBitLocker(int *)
0x18002473d  mov     esi, eax
0x18002473f  test    eax, eax
0x180024741  jns     short loc_180024761
0x180024743  mov     rcx, [r14+58h]
0x180024747  test    rcx, rcx
0x18002474a  jz      loc_180024C25
0x180024750  mov     dword ptr [rsp+530h+var_508], eax
0x180024754  mov     dword ptr [rsp+530h+ppv], 0B5Eh
0x18002475c  jmp     loc_180024660
0x180024761  xor     esi, esi
0x180024763  cmp     dword ptr [rsp+530h+var_4D0+4], esi
0x180024767  jz      short loc_18002478C
0x180024769  mov     esi, 0C180010Bh
0x18002476e  mov     rcx, [r14+58h]
0x180024772  test    rcx, rcx
0x180024775  jz      loc_180024C25
0x18002477b  mov     dword ptr [rsp+530h+var_508], esi
0x18002477f  mov     dword ptr [rsp+530h+ppv], 0B5Fh
0x180024787  jmp     loc_180024660
0x18002478c  mov     ebx, 41h ; 'A'
0x180024791  mov     eax, 0FFFFFFFFh
0x180024796  cmp     [r14+550h], si
0x18002479e  jnz     short loc_1800247B7
0x1800247a0  test    byte ptr [r14+558h], 10h
0x1800247a8  jz      short loc_1800247B7
0x1800247aa  mov     dword ptr [rsp+530h+var_4C0], 0FFFFFFFFh
0x1800247b2  jmp     loc_180024885
0x1800247b7  xor     edx, edx; dwCoInit
0x1800247b9  xor     ecx, ecx; pvReserved
0x1800247bb  call    cs:__imp_CoInitializeEx
0x1800247c1  test    eax, eax
0x1800247c3  js      short loc_1800247CE
0x1800247c5  mov     edi, r15d
0x1800247c8  mov     [rbp+430h+var_480], r15d
0x1800247cc  jmp     short loc_1800247DE
0x1800247ce  cmp     eax, 80010106h
0x1800247d3  jz      short loc_1800247DE
0x1800247d5  mov     esi, eax
0x1800247d7  mov     ecx, eax
0x1800247d9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800247de  mov     ecx, esi
0x1800247e0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800247e5  test    esi, esi
0x1800247e7  jns     short loc_180024807
0x1800247e9  mov     rcx, [r14+58h]
0x1800247ed  test    rcx, rcx
0x1800247f0  jz      loc_180024C25
0x1800247f6  mov     dword ptr [rsp+530h+var_508], esi
0x1800247fa  mov     dword ptr [rsp+530h+ppv], 0B67h
0x180024802  jmp     loc_180024660
0x180024807  movzx   ecx, word ptr [r14+550h]
0x18002480f  xor     esi, esi
0x180024811  mov     [rbp+430h+var_4A8], rsi
0x180024815  lea     eax, [rcx-61h]
0x180024818  cmp     ax, 19h
0x18002481c  jbe     short loc_18002484F
0x18002481e  movzx   eax, cx
0x180024821  sub     ax, bx
0x180024824  cmp     ax, 19h
0x180024828  jbe     short loc_18002484F
0x18002482a  lea     ecx, [rsi+57h]; dwErrCode
0x18002482d  call    cs:__imp_SetLastError
0x180024833  call    cs:__imp_GetLastError
0x180024839  mov     esi, eax
0x18002483b  xor     eax, eax
0x18002483d  test    esi, esi
0x18002483f  jnz     loc_180026008
0x180024845  mov     esi, 80004005h
0x18002484a  jmp     loc_180026013
0x18002484f  lea     r8, [rbp+430h+var_4A8]
0x180024853  lea     rdx, [rsp+530h+var_4E8]
0x180024858  call    GetDiskAndOffsetFromDriveLetter
0x18002485d  cmp     eax, r15d
0x180024860  jnz     short loc_180024869
0x180024862  mov     eax, esi
0x180024864  mov     ebx, r15d
0x180024867  jmp     short loc_180024871
0x180024869  mov     ebx, esi
0x18002486b  call    cs:__imp_GetLastError
0x180024871  mov     ecx, eax; dwErrCode
0x180024873  call    cs:__imp_SetLastError
0x180024879  test    ebx, ebx
0x18002487b  jz      short loc_180024833
0x18002487d  mov     eax, [rsp+530h+var_4E8]
0x180024881  mov     dword ptr [rsp+530h+var_4C0], eax
0x180024885  mov     [rsp+530h+var_4E8], eax
0x180024889  mov     rdx, [r14+378h]; unsigned __int16 *
0x180024890  test    rdx, rdx
0x180024893  jz      short loc_1800248C1
0x180024895  mov     rcx, r14; this
0x180024898  call    ?PopulateSwmPaths@CDlpActionLayoutUsb@@AEAAJPEBG@Z; CDlpActionLayoutUsb::PopulateSwmPaths(ushort const *)
0x18002489d  mov     esi, eax
0x18002489f  test    eax, eax
0x1800248a1  jns     short loc_1800248C1
0x1800248a3  mov     rcx, [r14+58h]
0x1800248a7  test    rcx, rcx
0x1800248aa  jz      loc_180024C25
0x1800248b0  mov     dword ptr [rsp+530h+var_508], eax
0x1800248b4  mov     dword ptr [rsp+530h+ppv], 0B7Ah
0x1800248bc  jmp     loc_180024660
0x1800248c1  test    byte ptr [r14+558h], 20h
0x1800248c9  jz      loc_180024988
0x1800248cf  mov     rax, [r14+398h]
0x1800248d6  mov     [rsp+530h+var_500], r15d; int
0x1800248db  lea     rcx, aSources; "sources"
0x1800248e2  mov     [rsp+530h+var_508], rcx; unsigned __int16 *
0x1800248e7  mov     [rsp+530h+ppv], rax; unsigned __int16 *
0x1800248ec  mov     r9, [r14+390h]; unsigned __int16 *
0x1800248f3  mov     r8, [r14+380h]; unsigned __int16 *
0x1800248fa  mov     rdx, [r14+378h]; Src
0x180024901  mov     rcx, r14; this
0x180024904  call    ?PopulateOemPaths@CDlpActionLayoutUsb@@AEAAJPEBG0000H@Z; CDlpActionLayoutUsb::PopulateOemPaths(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int)
0x180024909  mov     esi, eax
0x18002490b  xor     eax, eax
0x18002490d  test    esi, esi
0x18002490f  jns     short loc_18002492F
0x180024911  mov     rcx, [r14+58h]
0x180024915  test    rcx, rcx
0x180024918  jz      loc_180024C25
0x18002491e  mov     dword ptr [rsp+530h+var_508], esi
0x180024922  mov     dword ptr [rsp+530h+ppv], 0B86h
0x18002492a  jmp     loc_180024660
0x18002492f  mov     rdx, [r14+3A0h]; Src
0x180024936  test    rdx, rdx
0x180024939  jz      short loc_18002498A
0x18002493b  mov     [rsp+530h+var_500], eax; int
0x18002493f  lea     rax, aSourcesRecover; "sources\\recovery\\old"
0x180024946  mov     [rsp+530h+var_508], rax; unsigned __int16 *
0x18002494b  mov     [rsp+530h+ppv], 0; unsigned __int16 *
0x180024954  xor     r9d, r9d; unsigned __int16 *
0x180024957  xor     r8d, r8d; unsigned __int16 *
0x18002495a  mov     rcx, r14; this
0x18002495d  call    ?PopulateOemPaths@CDlpActionLayoutUsb@@AEAAJPEBG0000H@Z; CDlpActionLayoutUsb::PopulateOemPaths(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int)
0x180024962  mov     esi, eax
0x180024964  xor     eax, eax
0x180024966  test    esi, esi
0x180024968  jns     short loc_18002498A
0x18002496a  mov     rcx, [r14+58h]
0x18002496e  test    rcx, rcx
0x180024971  jz      loc_180024C25
0x180024977  mov     dword ptr [rsp+530h+var_508], esi
0x18002497b  mov     dword ptr [rsp+530h+ppv], 0B8Ah
0x180024983  jmp     loc_180024660
0x180024988  xor     eax, eax
0x18002498a  mov     rdx, [r14+3A8h]; unsigned __int16 *
0x180024991  test    rdx, rdx
  ... truncated ...
```
