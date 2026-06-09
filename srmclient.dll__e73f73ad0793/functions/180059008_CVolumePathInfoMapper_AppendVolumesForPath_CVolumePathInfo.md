# CVolumePathInfoMapper::AppendVolumesForPath(CVolumePathInfo &)

- ea: `0x180059008`
- end: `0x180059d5a`
- name: `?AppendVolumesForPath@CVolumePathInfoMapper@@QEAAXAEAVCVolumePathInfo@@@Z`
- size: `3410`
- prototype: `void __fastcall(CVolumePathInfoMapper *__hidden this, struct CVolumePathInfo *)`
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callers

- `0x18005162c`
- `0x180059008`

## callees

- `0x180001350`
- `0x180001418`
- `0x18000ad14`
- `0x18000cd60`
- `0x18000ead4`
- `0x18000ebd4`
- `0x18000ee24`
- `0x18000eef4`
- `0x18001791c`
- `0x18001d7d4`
- `0x180058d98`
- `0x180058f38`
- `0x180059008`
- `0x180059d60`
- `0x180059e50`
- `0x180059f3c`
- `0x18005a03c`
- `0x18006febc`
- `0x18007006c`
- `0x1800700b8`
- `0x180070380`
- `0x180070648`
- `0x180071efc`
- `0x180074048`
- `0x18007f760`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `msvcrt!towlower` at `0x1800595c2`
- `ole32!CoTaskMemFree` at `0x180059488`
- `ole32!CoTaskMemFree` at `0x180059880`
- `ole32!CoTaskMemFree` at `0x180059b33`
- `ole32!CoTaskMemFree` at `0x180059cf4`
- `ole32!CoTaskMemFree` at `0x180059488`
- `ole32!CoTaskMemFree` at `0x180059880`
- `ole32!CoTaskMemFree` at `0x180059b33`
- `ole32!CoTaskMemFree` at `0x180059cf4`
- `KERNEL32!GetLastError` at `0x180059342`
- `KERNEL32!GetLastError` at `0x180059390`
- `KERNEL32!GetLastError` at `0x1800599e6`
- `KERNEL32!GetLastError` at `0x180059a38`
- `KERNEL32!GetLastError` at `0x180059342`
- `KERNEL32!GetLastError` at `0x180059390`
- `KERNEL32!GetLastError` at `0x1800599e6`
- `KERNEL32!GetLastError` at `0x180059a38`
- `KERNEL32!FindNextVolumeMountPointW` at `0x1800599d8`
- `KERNEL32!FindNextVolumeMountPointW` at `0x180059a2a`
- `KERNEL32!FindNextVolumeMountPointW` at `0x1800599d8`
- `KERNEL32!FindNextVolumeMountPointW` at `0x180059a2a`
- `KERNEL32!FindVolumeMountPointClose` at `0x180059c4c`
- `KERNEL32!FindVolumeMountPointClose` at `0x180059c4c`
- `KERNEL32!FindFirstVolumeMountPointW` at `0x18005932a`
- `KERNEL32!FindFirstVolumeMountPointW` at `0x180059378`
- `KERNEL32!FindFirstVolumeMountPointW` at `0x18005932a`
- `KERNEL32!FindFirstVolumeMountPointW` at `0x180059378`

## string_xrefs

- `0x180059057`: `base\fs\fsrm\service\pipeline\volmapper.cpp`
- `0x180059813`: `base\fs\fsrm\service\pipeline\volmapper.cpp`
- `0x180059065`: `CVolumePathInfoMapper::AppendVolumesForPath`
- `0x1800593be`: `CVolumePathInfoMapper::AppendVolumesForPath`
- `0x1800594b0`: `CVolumePathInfoMapper::AppendVolumesForPath`
- `0x180059550`: `CVolumePathInfoMapper::AppendVolumesForPath`
- `0x1800596ba`: `CVolumePathInfoMapper::AppendVolumesForPath`
- `0x18005981a`: `CVolumePathInfoMapper::AppendVolumesForPath`
- `0x180059a69`: `CVolumePathInfoMapper::AppendVolumesForPath`
- `0x180059b5b`: `CVolumePathInfoMapper::AppendVolumesForPath`
- `0x180059bff`: `CVolumePathInfoMapper::AppendVolumesForPath`
- `0x1800591c8`: `Current VolumePathInfo replaces`
- `0x180059179`: `Parent of VolumePathInfo already present`
- `0x18005941c`: `Volume has no more mount points`
- `0x180059ac7`: `Volume has no more mount points`
- `0x1800592d1`: `Querying mount points on VolumePathInfo`
- `0x18005945a`: `FindFirstVolumeMountPoint`
- `0x180059720`: `Ignoring mount point '%s' because it is not affected by the relative namespace '%s'`
- `0x180059b05`: `FindNextVolumeMountPoint`
- `0x18005984f`: `SrmGetVolumeNameForPathName`
- `0x180059cd2`: `FindVolumeMountPointClose(%s) failed: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
void __fastcall CVolumePathInfoMapper::AppendVolumesForPath(CVolumePathInfoMapper *this, struct CVolumePathInfo *a2)
{
  struct CVolumePathInfo *v2; // r13
  CVolumePathInfoMapper *v3; // r14
  unsigned __int16 *v4; // rcx
  unsigned __int16 **v5; // rbx
  unsigned __int16 *v6; // rbx
  unsigned __int16 **v7; // rdi
  __int64 v8; // rdx
  __int64 v9; // rax
  DWORD LastError; // ebx
  unsigned __int16 *v11; // rdi
  HANDLE FirstVolumeMountPointW; // r15
  CSrmDebugInfo *v13; // rax
  void **v14; // rbx
  void **v15; // rcx
  unsigned __int64 v16; // rdx
  void **v17; // rax
  __int64 v18; // r8
  unsigned __int16 *v19; // rdi
  void **v20; // rax
  void **v21; // r15
  void **v22; // rax
  void **v23; // rax
  unsigned __int16 *v24; // rdi
  void **v25; // rbx
  void **v26; // rax
  void *v27; // rbx
  CSrmDebugInfo *v28; // rax
  CSrmDebugInfo *v29; // rax
  unsigned __int16 **v30; // [rsp+20h] [rbp-548h]
  LPVOID pv; // [rsp+40h] [rbp-528h] BYREF
  unsigned __int16 *v32; // [rsp+48h] [rbp-520h] BYREF
  LPWSTR lpszVolumeMountPoint; // [rsp+50h] [rbp-518h] BYREF
  DWORD cchBufferLength; // [rsp+58h] [rbp-510h]
  unsigned __int16 *v35; // [rsp+60h] [rbp-508h]
  HANDLE v36; // [rsp+68h] [rbp-500h]
  LPVOID v37[2]; // [rsp+70h] [rbp-4F8h] BYREF
  struct CVolumePathInfo *v38; // [rsp+80h] [rbp-4E8h]
  CVolumePathInfoMapper *v39; // [rsp+90h] [rbp-4D8h]
  LPVOID v40; // [rsp+98h] [rbp-4D0h] BYREF
  const unsigned __int16 *v41; // [rsp+A0h] [rbp-4C8h] BYREF
  const unsigned __int16 *v42; // [rsp+A8h] [rbp-4C0h]
  const unsigned __int16 *v43; // [rsp+B0h] [rbp-4B8h]
  int v44; // [rsp+B8h] [rbp-4B0h]
  int v45; // [rsp+BCh] [rbp-4ACh]
  int v46; // [rsp+C0h] [rbp-4A8h]
  _BYTE v47[96]; // [rsp+C8h] [rbp-4A0h] BYREF
  int v48; // [rsp+128h] [rbp-440h]
  int v49; // [rsp+130h] [rbp-438h] BYREF
  const unsigned __int16 **v50; // [rsp+138h] [rbp-430h]
  const unsigned __int16 *v51; // [rsp+140h] [rbp-428h] BYREF
  const unsigned __int16 *v52; // [rsp+148h] [rbp-420h]
  const unsigned __int16 *v53; // [rsp+150h] [rbp-418h]
  int v54; // [rsp+158h] [rbp-410h]
  int v55; // [rsp+15Ch] [rbp-40Ch]
  int v56; // [rsp+160h] [rbp-408h]
  _BYTE v57[96]; // [rsp+168h] [rbp-400h] BYREF
  int v58; // [rsp+1C8h] [rbp-3A0h]
  const unsigned __int16 **v59; // [rsp+1D0h] [rbp-398h]
  _com_error *v60; // [rsp+1D8h] [rbp-390h] BYREF
  const exception *v61[3]; // [rsp+1E0h] [rbp-388h] BYREF
  _QWORD v62[3]; // [rsp+1F8h] [rbp-370h] BYREF
  int v63; // [rsp+210h] [rbp-358h]
  int v64; // [rsp+214h] [rbp-354h]
  int v65; // [rsp+218h] [rbp-350h]
  _DWORD v66[26]; // [rsp+220h] [rbp-348h] BYREF
  _QWORD v67[3]; // [rsp+288h] [rbp-2E0h] BYREF
  int v68; // [rsp+2A0h] [rbp-2C8h]
  int v69; // [rsp+2A4h] [rbp-2C4h]
  int v70; // [rsp+2A8h] [rbp-2C0h]
  _BYTE v71[96]; // [rsp+2B0h] [rbp-2B8h] BYREF
  int v72; // [rsp+310h] [rbp-258h]
  void *Src[2]; // [rsp+318h] [rbp-250h] BYREF
  __int64 v74; // [rsp+328h] [rbp-240h]
  unsigned __int64 v75; // [rsp+330h] [rbp-238h]
  void *Block[2]; // [rsp+340h] [rbp-228h] BYREF
  __int64 v77; // [rsp+350h] [rbp-218h]
  unsigned __int64 v78; // [rsp+358h] [rbp-210h]
  void **v79; // [rsp+370h] [rbp-1F8h] BYREF
  __int64 v80; // [rsp+378h] [rbp-1F0h]
  unsigned int v81; // [rsp+39Ch] [rbp-1CCh]
  void *v82[20]; // [rsp+420h] [rbp-148h] BYREF
  WCHAR szVolumeName[56]; // [rsp+4C0h] [rbp-A8h] BYREF

  v2 = a2;
  v3 = this;
  v39 = this;
  v38 = a2;
  v35 = (unsigned __int16 *)v62;
  v62[0] = L"base\\fs\\fsrm\\service\\pipeline\\volmapper.cpp";
  v62[1] = L"CVolumePathInfoMapper::AppendVolumesForPath";
  v62[2] = L"VOLMAPRC";
  v63 = 188;
  v64 = 22;
  v65 = 255;
  v66[24] = 0x1000000;
  memset_0(v66, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v79, (const struct CSrmDebugInfo *)v62, 0);
  CVolumePathInfo::TraceInfo(v2, (struct CSrmFunctionTracer *)&v79, L"Processing");
  v5 = *(unsigned __int16 ***)v3;
  while ( 1 )
  {
    v5 = (unsigned __int16 **)*v5;
    if ( v5 == *(unsigned __int16 ***)v3 )
      break;
    if ( CVolumePathInfo::IsParentOf((CVolumePathInfo *)(v5 + 2), v2) )
    {
      v35 = (unsigned __int16 *)&v41;
      v41 = L"base\\fs\\fsrm\\service\\pipeline\\volmapper.cpp";
      v42 = L"CVolumePathInfoMapper::AppendVolumesForPath";
      v43 = L"VOLMAPRC";
      v44 = 198;
      v45 = 22;
      v46 = 255;
      v48 = 0x1000000;
      memset_0(v47, 0, sizeof(v47));
      CSrmFunctionTracer::Trace(&v79, &v41, L"Parent of VolumePathInfo already present");
      v79 = &CSrmFunctionTracer::`vftable';
      goto LABEL_77;
    }
  }
  v6 = **(unsigned __int16 ***)v3;
  while ( 1 )
  {
    v7 = *(unsigned __int16 ***)v3;
    if ( v6 == *(unsigned __int16 **)v3 )
      break;
    if ( CVolumePathInfo::IsParentOf(v2, (struct CVolumePathInfo *)(v6 + 8)) )
    {
      CVolumePathInfo::TraceInfo(
        (CVolumePathInfo *)(v6 + 8),
        (struct CSrmFunctionTracer *)&v79,
        L"Current VolumePathInfo replaces");
      v4 = *(unsigned __int16 **)v6;
      v35 = *(unsigned __int16 **)v6;
      v32 = v6;
      if ( v6 != *(unsigned __int16 **)v3 )
      {
        **((_QWORD **)v6 + 1) = v4;
        *(_QWORD *)(*(_QWORD *)v6 + 8LL) = *((_QWORD *)v6 + 1);
        CVolumePathInfo::~CVolumePathInfo((void **)v6 + 2);
        operator delete(v6);
        --*((_QWORD *)v3 + 1);
        v4 = v35;
      }
      v6 = v4;
    }
    else
    {
      v6 = *(unsigned __int16 **)v6;
    }
  }
  v8 = std::_List_val<CVolumePathInfo>::_Buynode(v4, *(_QWORD *)v3, v7[1], v2);
  v9 = *((_QWORD *)v3 + 1);
  if ( v9 == 0x199999999999998LL )
    std::_Xlength_error("list<T> too long");
  *((_QWORD *)v3 + 1) = v9 + 1;
  v7[1] = (unsigned __int16 *)v8;
  **(_QWORD **)(v8 + 8) = v8;
  v35 = (unsigned __int16 *)&v41;
  v41 = L"base\\fs\\fsrm\\service\\pipeline\\volmapper.cpp";
  v42 = L"CVolumePathInfoMapper::AppendVolumesForPath";
  v43 = L"VOLMAPRC";
  v44 = 230;
  v45 = 22;
  v46 = 255;
  v48 = 0x1000000;
  memset_0(v47, 0, sizeof(v47));
  CSrmFunctionTracer::Trace(&v79, &v41, L"Querying mount points on VolumePathInfo");
  LastError = 0;
  v11 = (unsigned __int16 *)((char *)v2 + 80);
  if ( *((_QWORD *)v2 + 13) >= 8u )
    v11 = *(unsigned __int16 **)v11;
  v35 = v11;
  lpszVolumeMountPoint = 0;
  cchBufferLength = 260;
  CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&lpszVolumeMountPoint, 0x104u);
  FirstVolumeMountPointW = FindFirstVolumeMountPointW(v11, lpszVolumeMountPoint, 0x104u);
  v36 = FirstVolumeMountPointW;
  if ( FirstVolumeMountPointW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError == 234 )
    {
      LastError = 0;
      cchBufferLength = 0x7FFF;
      CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&lpszVolumeMountPoint, 0x7FFFu);
      FirstVolumeMountPointW = FindFirstVolumeMountPointW(v11, lpszVolumeMountPoint, 0x7FFFu);
      v36 = FirstVolumeMountPointW;
      if ( FirstVolumeMountPointW != (HANDLE)-1LL )
        goto LABEL_23;
      LastError = GetLastError();
    }
    if ( LastError )
    {
      if ( LastError == 18 )
      {
        v32 = (unsigned __int16 *)&v41;
        v41 = L"base\\fs\\fsrm\\service\\pipeline\\volmapper.cpp";
        v42 = L"CVolumePathInfoMapper::AppendVolumesForPath";
        v43 = L"VOLMAPRC";
        v44 = 267;
        v45 = 22;
        v46 = 255;
        v48 = 0x1000000;
        memset_0(v47, 0, sizeof(v47));
        CSrmFunctionTracer::Trace(&v79, &v41, L"Volume has no more mount points");
      }
      else
      {
        v32 = *(unsigned __int16 **)SrmFormatString(&pv, L"%d", LastError);
        v37[0] = L"FindFirstVolumeMountPoint";
        CSrmFunctionTracerBase::AddContext(&v79, 2, v37, &v32);
        CoTaskMemFree(pv);
        pv = 0;
        v40 = &v51;
        v41 = L"base\\fs\\fsrm\\service\\pipeline\\volmapper.cpp";
        v42 = L"CVolumePathInfoMapper::AppendVolumesForPath";
        v43 = L"VOLMAPRC";
        v44 = 273;
        v45 = 22;
        v46 = 255;
        v48 = 0x1000000;
        memset_0(v47, 0, sizeof(v47));
        v13 = CSrmDebugInfo::operator<<((struct CSrmDebugInfo *)&v41, (CSrmDebugInfo *)&v51, v11);
        CSrmFunctionTracer::LogError(&v79, 2147754024LL, v13, 2);
        CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)&v41);
      }
    }
  }
LABEL_23:
  while ( !LastError )
  {
    std::wstring::wstring(Src, lpszVolumeMountPoint);
    v14 = Src;
    v15 = (void **)Src[0];
    v16 = v75;
    if ( v75 >= 8 )
      v14 = (void **)Src[0];
    v17 = Src;
    if ( v75 >= 8 )
      v17 = (void **)Src[0];
    v18 = v74;
    v19 = (unsigned __int16 *)v17 + v74;
    v20 = Src;
    if ( v75 >= 8 )
      v20 = (void **)Src[0];
    if ( v20 != (void **)v19 )
    {
      v21 = v20;
      do
      {
        *(_WORD *)v14 = ((__int64 (__fastcall *)(_QWORD))towlower)(*(unsigned __int16 *)v21);
        v14 = (void **)((char *)v14 + 2);
        v21 = (void **)((char *)v21 + 2);
      }
      while ( v21 != (void **)v19 );
      v16 = v75;
      v18 = v74;
      v15 = (void **)Src[0];
      FirstVolumeMountPointW = v36;
    }
    v22 = Src;
    if ( v16 >= 8 )
      v22 = v15;
    if ( *((_WORD *)v22 + v18 - 1) != 92 )
    {
      std::wstring::append(Src, (void *)L"\\");
      v16 = v75;
      v15 = (void **)Src[0];
    }
    v23 = Src;
    if ( v16 >= 8 )
      v23 = v15;
    if ( *(_WORD *)v23 != 92 )
      std::wstring::insert(Src);
    v24 = (unsigned __int16 *)((char *)v2 + 40);
    if ( (unsigned __int8)CVolumePathInfo::IsParentPath((char *)v2 + 40, Src) )
    {
      std::wstring::wstring(Block, (char *)v2 + 120);
      v26 = Block;
      if ( v78 >= 8 )
        v26 = (void **)Block[0];
      if ( *((_WORD *)v26 + v77 - 1) == 92 )
        std::wstring::erase(Block, v77 - 1, 1);
      std::wstring::append(Block, Src, 0, -1, v30);
      v27 = Block;
      if ( v78 >= 8 )
        v27 = Block[0];
      pv = v27;
      v32 = 0;
      try
      {
        SrmGetVolumeNameForPathName((LPCWSTR)v27, szVolumeName, 0x32u, 0, &v32);
      }
      catch ( long v49 )
      {
        CSrmFunctionTracer::HandleHresultException(
          (CSrmFunctionTracer *)&v79,
          v49,
          L"base\\fs\\fsrm\\service\\pipeline\\volmapper.cpp",
          L"VOLMAPRC",
          L"CVolumePathInfoMapper::AppendVolumesForPath",
          0x147u,
          v81);
        v3 = v39;
        v2 = v38;
        v27 = pv;
        FirstVolumeMountPointW = v36;
      }
      catch ( _com_error *v60 )
      {
        CSrmFunctionTracer::HandleComException(
          (CSrmFunctionTracer *)&v79,
          v60,
          L"base\\fs\\fsrm\\service\\pipeline\\volmapper.cpp",
          L"VOLMAPRC",
          L"CVolumePathInfoMapper::AppendVolumesForPath",
          0x147u,
          v81);
      }
      catch ( std::bad_alloc )
      {
        CSrmFunctionTracer::HandleStdBadAllocException(
          (CSrmFunctionTracer *)&v79,
          L"base\\fs\\fsrm\\service\\pipeline\\volmapper.cpp",
          L"VOLMAPRC",
          L"CVolumePathInfoMapper::AppendVolumesForPath",
          0x147u,
          v81);
        v3 = v39;
        v2 = v38;
        v27 = pv;
        FirstVolumeMountPointW = v36;
      }
      catch ( const exception *v61 )
      {
        CSrmFunctionTracer::HandleStdGenericException(
          (CSrmFunctionTracer *)&v79,
          v61[0],
          L"base\\fs\\fsrm\\service\\pipeline\\volmapper.cpp",
          L"VOLMAPRC",
          L"CVolumePathInfoMapper::AppendVolumesForPath",
          0x147u,
          v81);
      }
      if ( (int)v80 >= 0 )
      {
        CVolumePathInfo::CVolumePathInfo(
          (CVolumePathInfo *)v82,
          (unsigned __int16 *)v27,
          v32,
          szVolumeName,
          (unsigned __int16 *)v27);
        CVolumePathInfoMapper::AppendVolumesForPath(v3, (struct CVolumePathInfo *)v82);
        CVolumePathInfo::~CVolumePathInfo(v82);
      }
      else
      {
        v32 = *(unsigned __int16 **)SrmFormatString(&v40, L"%#x");
        pv = L"SrmGetVolumeNameForPathName";
        CSrmFunctionTracerBase::AddContext(&v79, 2, &pv, &v32);
        CoTaskMemFree(v40);
        v40 = 0;
        v61[1] = (const exception *)&v41;
        v67[0] = L"base\\fs\\fsrm\\service\\pipeline\\volmapper.cpp";
        v67[1] = L"CVolumePathInfoMapper::AppendVolumesForPath";
        v67[2] = L"VOLMAPRC";
        v68 = 336;
        v69 = 22;
        v70 = 255;
        v72 = 0x1000000;
        memset_0(v71, 0, sizeof(v71));
        v28 = CSrmDebugInfo::operator<<((struct CSrmDebugInfo *)v67, (CSrmDebugInfo *)&v41, (unsigned __int16 *)v27);
        CSrmFunctionTracer::LogError(&v79, 2147754024LL, v28, 2);
        CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v67);
      }
      if ( v78 >= 8 )
        operator delete(Block[0]);
      v78 = 7;
      v77 = 0;
      LOWORD(Block[0]) = 0;
    }
    else
    {
      if ( *((_QWORD *)v2 + 8) >= 8u )
        v24 = *(unsigned __int16 **)v24;
      v25 = Src;
      if ( v75 >= 8 )
        v25 = (void **)Src[0];
      v59 = &v41;
      v41 = L"base\\fs\\fsrm\\service\\pipeline\\volmapper.cpp";
      v42 = L"CVolumePathInfoMapper::AppendVolumesForPath";
      v43 = L"VOLMAPRC";
      v44 = 300;
      v45 = 22;
      v46 = 255;
      v48 = 0x1000000;
      memset_0(v47, 0, sizeof(v47));
      v30 = (unsigned __int16 **)v24;
      CSrmFunctionTracer::Trace(
        &v79,
        &v41,
        L"Ignoring mount point '%s' because it is not affected by the relative namespace '%s'",
        v25);
    }
    LastError = 0;
    if ( !FindNextVolumeMountPointW(FirstVolumeMountPointW, lpszVolumeMountPoint, cchBufferLength) )
    {
      LastError = GetLastError();
      if ( LastError == 234 )
      {
        if ( cchBufferLength < 0x7FFF )
        {
          LastError = 0;
          cchBufferLength = 0x7FFF;
          CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&lpszVolumeMountPoint, 0x7FFFu);
          if ( FindNextVolumeMountPointW(FirstVolumeMountPointW, lpszVolumeMountPoint, 0x7FFFu) )
            goto LABEL_70;
          LastError = GetLastError();
          goto LABEL_66;
        }
      }
      else
      {
LABEL_66:
        if ( !LastError )
          goto LABEL_70;
        if ( LastError == 18 )
        {
          v61[2] = (const exception *)&v41;
          v41 = L"base\\fs\\fsrm\\service\\pipeline\\volmapper.cpp";
          v42 = L"CVolumePathInfoMapper::AppendVolumesForPath";
          v43 = L"VOLMAPRC";
          v44 = 373;
          v45 = 22;
          v46 = 255;
          v48 = 0x1000000;
          memset_0(v47, 0, sizeof(v47));
          CSrmFunctionTracer::Trace(&v79, &v41, L"Volume has no more mount points");
          goto LABEL_70;
        }
      }
      v32 = *(unsigned __int16 **)SrmFormatString(v37, L"%d", LastError);
      pv = L"FindNextVolumeMountPoint";
      CSrmFunctionTracerBase::AddContext(&v79, 2, &pv, &v32);
      CoTaskMemFree(v37[0]);
      v37[0] = 0;
      v50 = &v41;
      v51 = L"base\\fs\\fsrm\\service\\pipeline\\volmapper.cpp";
      v52 = L"CVolumePathInfoMapper::AppendVolumesForPath";
      v53 = L"VOLMAPRC";
      v54 = 379;
      v55 = 22;
      v56 = 255;
      v58 = 0x1000000;
      memset_0(v57, 0, sizeof(v57));
      v29 = CSrmDebugInfo::operator<<((struct CSrmDebugInfo *)&v51, (CSrmDebugInfo *)&v41, v35);
      CSrmFunctionTracer::LogError(&v79, 2147754024LL, v29, 2);
      CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)&v51);
    }
LABEL_70:
    if ( v75 >= 8 )
      operator delete(Src[0]);
    v75 = 7;
    v74 = 0;
    LOWORD(Src[0]) = 0;
  }
  if ( FirstVolumeMountPointW != (HANDLE)-1LL && !FindVolumeMountPointClose(FirstVolumeMountPointW) )
  {
    v50 = &v51;
    v51 = L"base\\fs\\fsrm\\service\\pipeline\\volmapper.cpp";
    v52 = L"CVolumePathInfoMapper::AppendVolumesForPath";
    v53 = L"VOLMAPRC";
    v54 = 390;
    v55 = 22;
    v56 = 255;
    v58 = 0x1000000;
    memset_0(v57, 0, sizeof(v57));
    LODWORD(v30) = LastError;
    CSrmFunctionTracer::Trace(&v79, &v51, L"FindVolumeMountPointClose(%s) failed: %d", v35, v30);
  }
  CoTaskMemFree(lpszVolumeMountPoint);
  lpszVolumeMountPoint = 0;
  v79 = &CSrmFunctionTracer::`vftable';
LABEL_77:
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v79);
}

```

## disassembly

```asm
0x180059008  mov     r11, rsp
0x18005900b  mov     [r11+18h], rbx
0x18005900f  mov     [r11+20h], rsi
0x180059013  push    rdi
0x180059014  push    r12
0x180059016  push    r13
0x180059018  push    r14
0x18005901a  push    r15
0x18005901c  sub     rsp, 540h
0x180059023  mov     rax, cs:__security_cookie
0x18005902a  xor     rax, rsp
0x18005902d  mov     [rsp+568h+var_38], rax
0x180059035  mov     r13, rdx
0x180059038  mov     r14, rcx
0x18005903b  mov     [rsp+568h+var_4D8], rcx
0x180059043  mov     [rsp+568h+var_4E8], rdx
0x18005904b  lea     rax, [r11-370h]
0x180059052  mov     [rsp+568h+var_508], rax
0x180059057  lea     r12, aBaseFsFsrmServ_10; "base\\fs\\fsrm\\service\\pipeline\\volm"...
0x18005905e  mov     [r11-370h], r12
0x180059065  lea     r15, aCvolumepathinf_0; "CVolumePathInfoMapper::AppendVolumesFor"...
0x18005906c  mov     [r11-368h], r15
0x180059073  lea     rdi, aVolmaprc; "VOLMAPRC"
0x18005907a  mov     [r11-360h], rdi
0x180059081  mov     [rsp+568h+var_358], 0BCh
0x18005908c  mov     [rsp+568h+var_354], 16h
0x180059097  mov     [rsp+568h+var_350], 0FFh
0x1800590a2  xor     esi, esi
0x1800590a4  mov     [rsp+568h+var_2E8], 1000000h
0x1800590af  xor     edx, edx; Val
0x1800590b1  lea     r8d, [rsi+60h]; Size
0x1800590b5  lea     rcx, [r11-348h]; void *
0x1800590bc  call    memset_0
0x1800590c1  nop
0x1800590c2  xor     r8d, r8d
0x1800590c5  lea     rdx, [rsp+568h+var_370]
0x1800590cd  lea     rcx, [rsp+568h+var_1F8]
0x1800590d5  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800590da  nop
0x1800590db  lea     r8, aProcessing; "Processing"
0x1800590e2  lea     rdx, [rsp+568h+var_1F8]; struct CSrmFunctionTracer *
0x1800590ea  mov     rcx, r13; this
0x1800590ed  call    ?TraceInfo@CVolumePathInfo@@QEAAXAEAVCSrmFunctionTracer@@PEBG@Z; CVolumePathInfo::TraceInfo(CSrmFunctionTracer &,ushort const *)
0x1800590f2  mov     rbx, [r14]
0x1800590f5  mov     rbx, [rbx]
0x1800590f8  mov     rax, [r14]
0x1800590fb  cmp     rbx, rax
0x1800590fe  jz      loc_1800591AA
0x180059104  lea     rcx, [rbx+10h]; this
0x180059108  mov     rdx, r13; struct CVolumePathInfo *
0x18005910b  call    ?IsParentOf@CVolumePathInfo@@QEAA_NAEAV1@@Z; CVolumePathInfo::IsParentOf(CVolumePathInfo &)
0x180059110  test    al, al
0x180059112  jz      short loc_1800590F5
0x180059114  lea     rax, [rsp+568h+var_4C8]
0x18005911c  mov     [rsp+568h+var_508], rax
0x180059121  mov     [rsp+568h+var_4C8], r12
0x180059129  mov     [rsp+568h+var_4C0], r15
0x180059131  mov     [rsp+568h+var_4B8], rdi
0x180059139  mov     [rsp+568h+var_4B0], 0C6h
0x180059144  mov     [rsp+568h+var_4AC], 16h
0x18005914f  mov     [rsp+568h+var_4A8], 0FFh
0x18005915a  mov     [rsp+568h+var_440], 1000000h
0x180059165  xor     edx, edx; Val
0x180059167  lea     r8d, [rdx+60h]; Size
0x18005916b  lea     rcx, [rsp+568h+var_4A0]; void *
0x180059173  call    memset_0
0x180059178  nop
0x180059179  lea     r8, aParentOfVolume; "Parent of VolumePathInfo already presen"...
0x180059180  lea     rdx, [rsp+568h+var_4C8]
0x180059188  lea     rcx, [rsp+568h+var_1F8]
0x180059190  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180059195  nop
0x180059196  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18005919d  mov     [rsp+568h+var_1F8], rax
0x1800591a5  jmp     loc_180059D13
0x1800591aa  mov     rbx, [rax]
0x1800591ad  mov     rdi, [r14]
0x1800591b0  cmp     rbx, rdi
0x1800591b3  jz      short loc_180059226
0x1800591b5  lea     rdi, [rbx+10h]
0x1800591b9  mov     rdx, rdi; struct CVolumePathInfo *
0x1800591bc  mov     rcx, r13; this
0x1800591bf  call    ?IsParentOf@CVolumePathInfo@@QEAA_NAEAV1@@Z; CVolumePathInfo::IsParentOf(CVolumePathInfo &)
0x1800591c4  test    al, al
0x1800591c6  jz      short loc_180059221
0x1800591c8  lea     r8, aCurrentVolumep; "Current VolumePathInfo replaces"
0x1800591cf  lea     rdx, [rsp+568h+var_1F8]; struct CSrmFunctionTracer *
0x1800591d7  mov     rcx, rdi; this
0x1800591da  call    ?TraceInfo@CVolumePathInfo@@QEAAXAEAVCSrmFunctionTracer@@PEBG@Z; CVolumePathInfo::TraceInfo(CSrmFunctionTracer &,ushort const *)
0x1800591df  mov     rcx, [rbx]
0x1800591e2  mov     [rsp+568h+var_508], rcx
0x1800591e7  mov     [rsp+568h+var_520], rbx
0x1800591ec  cmp     rbx, [r14]
0x1800591ef  jz      short loc_18005921C
0x1800591f1  mov     rax, [rbx+8]
0x1800591f5  mov     [rax], rcx
0x1800591f8  mov     rdx, [rbx]
0x1800591fb  mov     rax, [rbx+8]
0x1800591ff  mov     [rdx+8], rax
0x180059203  mov     rcx, rdi; this
0x180059206  call    ??1CVolumePathInfo@@QEAA@XZ; CVolumePathInfo::~CVolumePathInfo(void)
0x18005920b  mov     rcx, rbx; Block
0x18005920e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180059213  dec     qword ptr [r14+8]
0x180059217  mov     rcx, [rsp+568h+var_508]
0x18005921c  mov     rbx, rcx
0x18005921f  jmp     short loc_1800591AD
0x180059221  mov     rbx, [rbx]
0x180059224  jmp     short loc_1800591AD
0x180059226  mov     r9, r13
0x180059229  mov     r8, [rdi+8]
0x18005922d  mov     rdx, rdi
0x180059230  call    ?_Buynode@?$_List_val@VCVolumePathInfo@@V?$allocator@VCVolumePathInfo@@@std@@@std@@QEAAPEAU_Node@?$_List_nod@VCVolumePathInfo@@V?$allocator@VCVolumePathInfo@@@std@@@2@PEAU342@0AEBVCVolumePathInfo@@@Z; std::_List_val<CVolumePathInfo>::_Buynode(std::_List_nod<CVolumePathInfo>::_Node *,std::_List_nod<CVolumePathInfo>::_Node *,CVolumePathInfo const &)
0x180059235  mov     rdx, rax
0x180059238  mov     rax, [r14+8]
0x18005923c  mov     rcx, 199999999999998h
0x180059246  sub     rcx, rax
0x180059249  cmp     rcx, 1
0x18005924d  jb      loc_180059D4D
0x180059253  inc     rax
0x180059256  mov     [r14+8], rax
0x18005925a  mov     [rdi+8], rdx
0x18005925e  mov     rax, [rdx+8]
0x180059262  mov     [rax], rdx
0x180059265  lea     rax, [rsp+568h+var_4C8]
0x18005926d  mov     [rsp+568h+var_508], rax
0x180059272  mov     [rsp+568h+var_4C8], r12
0x18005927a  mov     [rsp+568h+var_4C0], r15
0x180059282  lea     rax, aVolmaprc; "VOLMAPRC"
0x180059289  mov     [rsp+568h+var_4B8], rax
0x180059291  mov     [rsp+568h+var_4B0], 0E6h
0x18005929c  mov     [rsp+568h+var_4AC], 16h
0x1800592a7  mov     [rsp+568h+var_4A8], 0FFh
0x1800592b2  mov     [rsp+568h+var_440], 1000000h
0x1800592bd  xor     edx, edx; Val
0x1800592bf  lea     r8d, [rdx+60h]; Size
0x1800592c3  lea     rcx, [rsp+568h+var_4A0]; void *
0x1800592cb  call    memset_0
0x1800592d0  nop
0x1800592d1  lea     r8, aQueryingMountP; "Querying mount points on VolumePathInfo"
0x1800592d8  lea     rdx, [rsp+568h+var_4C8]
0x1800592e0  lea     rcx, [rsp+568h+var_1F8]
0x1800592e8  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x1800592ed  mov     ebx, esi
0x1800592ef  lea     rdi, [r13+50h]
0x1800592f3  cmp     qword ptr [rdi+18h], 8
0x1800592f8  jb      short loc_1800592FD
0x1800592fa  mov     rdi, [rdi]
0x1800592fd  mov     [rsp+568h+var_508], rdi
0x180059302  mov     [rsp+568h+lpszVolumeMountPoint], rsi
0x180059307  mov     r15d, 104h
0x18005930d  mov     [rsp+568h+cchBufferLength], r15d
0x180059312  mov     edx, r15d; unsigned __int64
0x180059315  lea     rcx, [rsp+568h+lpszVolumeMountPoint]; this
0x18005931a  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x18005931f  mov     r8d, r15d; cchBufferLength
0x180059322  mov     rdx, [rsp+568h+lpszVolumeMountPoint]; lpszVolumeMountPoint
0x180059327  mov     rcx, rdi; lpszRootPathName
0x18005932a  call    cs:__imp_FindFirstVolumeMountPointW
0x180059330  mov     r15, rax
0x180059333  mov     [rsp+568h+var_500], rax
0x180059338  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005933c  jnz     loc_180059550
0x180059342  call    cs:__imp_GetLastError
0x180059348  mov     ebx, eax
0x18005934a  cmp     eax, 0EAh
0x18005934f  jnz     short loc_180059398
0x180059351  mov     ebx, esi
0x180059353  mov     [rsp+568h+cchBufferLength], 7FFFh
0x18005935b  mov     edx, 7FFFh; unsigned __int64
0x180059360  lea     rcx, [rsp+568h+lpszVolumeMountPoint]; this
0x180059365  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x18005936a  mov     r8d, 7FFFh; cchBufferLength
0x180059370  mov     rdx, [rsp+568h+lpszVolumeMountPoint]; lpszVolumeMountPoint
0x180059375  mov     rcx, rdi; lpszRootPathName
0x180059378  call    cs:__imp_FindFirstVolumeMountPointW
0x18005937e  mov     r15, rax
0x180059381  mov     [rsp+568h+var_500], rax
0x180059386  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005938a  jnz     loc_180059550
0x180059390  call    cs:__imp_GetLastError
0x180059396  mov     ebx, eax
0x180059398  test    ebx, ebx
0x18005939a  jz      loc_180059550
0x1800593a0  cmp     ebx, 12h
0x1800593a3  jnz     loc_18005943D
0x1800593a9  lea     rax, [rsp+568h+var_4C8]
0x1800593b1  mov     [rsp+568h+var_520], rax
0x1800593b6  mov     [rsp+568h+var_4C8], r12
0x1800593be  lea     rdi, aCvolumepathinf_0; "CVolumePathInfoMapper::AppendVolumesFor"...
0x1800593c5  mov     [rsp+568h+var_4C0], rdi
0x1800593cd  lea     rax, aVolmaprc; "VOLMAPRC"
0x1800593d4  mov     [rsp+568h+var_4B8], rax
0x1800593dc  mov     [rsp+568h+var_4B0], 10Bh
0x1800593e7  mov     [rsp+568h+var_4AC], 16h
0x1800593f2  mov     [rsp+568h+var_4A8], 0FFh
0x1800593fd  mov     [rsp+568h+var_440], 1000000h
0x180059408  xor     edx, edx; Val
0x18005940a  lea     r8d, [rbx+4Eh]; Size
0x18005940e  lea     rcx, [rsp+568h+var_4A0]; void *
0x180059416  call    memset_0
0x18005941b  nop
0x18005941c  lea     r8, aVolumeHasNoMor; "Volume has no more mount points"
0x180059423  lea     rdx, [rsp+568h+var_4C8]
0x18005942b  lea     rcx, [rsp+568h+var_1F8]
0x180059433  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180059438  jmp     loc_180059557
0x18005943d  mov     r8d, ebx
0x180059440  lea     rdx, aD; "%d"
0x180059447  lea     rcx, [rsp+568h+pv]
0x18005944c  call    ?SrmFormatString@@YA?AVCSrmAutoPWSZ@@PEBGZZ; SrmFormatString(ushort const *,...)
0x180059451  nop
0x180059452  mov     rax, [rax]
0x180059455  mov     [rsp+568h+var_520], rax
0x18005945a  lea     rax, aFindfirstvolum; "FindFirstVolumeMountPoint"
0x180059461  mov     [rsp+568h+var_4F8], rax
0x180059466  lea     r9, [rsp+568h+var_520]
0x18005946b  lea     r8, [rsp+568h+var_4F8]
0x180059470  mov     edx, 2
0x180059475  lea     rcx, [rsp+568h+var_1F8]
0x18005947d  call    ?AddContext@CSrmFunctionTracerBase@@QEAAXW4_SrmContextType@@AEBUResIdOrStringParam@@1@Z; CSrmFunctionTracerBase::AddContext(_SrmContextType,ResIdOrStringParam const &,ResIdOrStringParam const &)
0x180059482  nop
0x180059483  mov     rcx, [rsp+568h+pv]; pv
0x180059488  call    cs:__imp_CoTaskMemFree
0x18005948e  mov     [rsp+568h+pv], rsi
0x180059493  mov     [rsp+568h+pv], rsi
0x180059498  lea     rax, [rsp+568h+var_428]
0x1800594a0  mov     [rsp+568h+var_4D0], rax
0x1800594a8  mov     [rsp+568h+var_4C8], r12
0x1800594b0  lea     rax, aCvolumepathinf_0; "CVolumePathInfoMapper::AppendVolumesFor"...
0x1800594b7  mov     [rsp+568h+var_4C0], rax
0x1800594bf  lea     rax, aVolmaprc; "VOLMAPRC"
0x1800594c6  mov     [rsp+568h+var_4B8], rax
0x1800594ce  mov     [rsp+568h+var_4B0], 111h
0x1800594d9  mov     [rsp+568h+var_4AC], 16h
0x1800594e4  mov     [rsp+568h+var_4A8], 0FFh
0x1800594ef  mov     [rsp+568h+var_440], 1000000h
0x1800594fa  xor     edx, edx; Val
0x1800594fc  lea     r8d, [rdx+60h]; Size
0x180059500  lea     rcx, [rsp+568h+var_4A0]; void *
0x180059508  call    memset_0
0x18005950d  nop
0x18005950e  mov     r8, rdi; unsigned __int16 *
0x180059511  lea     rdx, [rsp+568h+var_428]; this
0x180059519  lea     rcx, [rsp+568h+var_4C8]; struct CSrmDebugInfo *
0x180059521  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x180059526  nop
0x180059527  mov     r9d, 2
0x18005952d  mov     r8, rax
0x180059530  mov     edx, 80042028h
0x180059535  lea     rcx, [rsp+568h+var_1F8]
0x18005953d  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x180059542  nop
0x180059543  lea     rcx, [rsp+568h+var_4C8]; this
0x18005954b  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180059550  lea     rdi, aCvolumepathinf_0; "CVolumePathInfoMapper::AppendVolumesFor"...
0x180059557  test    ebx, ebx
0x180059559  jnz     loc_180059C3F
0x18005955f  mov     rdx, [rsp+568h+lpszVolumeMountPoint]
0x180059564  lea     rcx, [rsp+568h+Src]; void *
0x18005956c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180059571  nop
0x180059572  lea     rbx, [rsp+568h+Src]
0x18005957a  mov     rcx, [rsp+568h+Src]
0x180059582  mov     rdx, [rsp+568h+var_238]
0x18005958a  cmp     rdx, 8
0x18005958e  cmovnb  rbx, rcx
0x180059592  lea     rax, [rsp+568h+Src]
0x18005959a  cmovnb  rax, rcx
0x18005959e  mov     r8, [rsp+568h+var_240]
0x1800595a6  lea     rdi, [rax+r8*2]
0x1800595aa  lea     rax, [rsp+568h+Src]
0x1800595b2  cmovnb  rax, rcx
0x1800595b6  cmp     rax, rdi
0x1800595b9  jz      short loc_1800595FB
0x1800595bb  mov     r15, rax
0x1800595be  movzx   ecx, word ptr [r15]
0x1800595c2  mov     rax, cs:__imp_towlower
0x1800595c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800595ce  mov     [rbx], ax
0x1800595d1  lea     rbx, [rbx+2]
0x1800595d5  add     r15, 2
0x1800595d9  cmp     r15, rdi
0x1800595dc  jnz     short loc_1800595BE
0x1800595de  mov     rdx, [rsp+568h+var_238]
0x1800595e6  mov     r8, [rsp+568h+var_240]
0x1800595ee  mov     rcx, [rsp+568h+Src]
0x1800595f6  mov     r15, [rsp+568h+var_500]
0x1800595fb  lea     rax, [rsp+568h+Src]
0x180059603  cmp     rdx, 8
0x180059607  cmovnb  rax, rcx
0x18005960b  cmp     word ptr [rax+r8*2-2], 5Ch ; '\'
0x180059612  jz      short loc_180059638
0x180059614  lea     rdx, psz; "\\"
0x18005961b  lea     rcx, [rsp+568h+Src]; Src
0x180059623  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180059628  mov     rdx, [rsp+568h+var_238]
0x180059630  mov     rcx, [rsp+568h+Src]
0x180059638  lea     rax, [rsp+568h+Src]
0x180059640  cmp     rdx, 8
  ... truncated ...
```
