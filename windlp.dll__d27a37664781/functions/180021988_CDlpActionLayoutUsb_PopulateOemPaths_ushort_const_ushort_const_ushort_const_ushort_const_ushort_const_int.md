# CDlpActionLayoutUsb::PopulateOemPaths(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int)

- ea: `0x180021988`
- end: `0x1800228d7`
- name: `?PopulateOemPaths@CDlpActionLayoutUsb@@AEAAJPEBG0000H@Z`
- size: `3919`
- prototype: `__int64 __usercall@<rax>(CDlpActionLayoutUsb *__hidden this@<rcx>, const unsigned __int16 *Src@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800244d4`

## callees

- `0x180002898`
- `0x18000aba4`
- `0x18000b7f8`
- `0x18000b9a8`
- `0x18000ea20`
- `0x180012f5c`
- `0x180017148`
- `0x18001fd60`
- `0x180020468`
- `0x180021698`
- `0x180021988`
- `0x1800228e0`
- `0x18007ec9a`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180021a47`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180021a47`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800227ea`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800227ea`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180021fa4`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180021fa4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180022036`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180022036`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021c46`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021db9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800223e6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180022585`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800226f2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021c46`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021db9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800223e6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180022585`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800226f2`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180022200`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180022200`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180022076`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800220aa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180022076`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800220aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021bb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021bdb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021d24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021d4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021e99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021ec2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800220be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022108`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002234f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002241a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800224ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800225b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002265b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022726`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800227ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022829`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022853`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022874`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022896`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021bb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021bdb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021d24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021d4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021e99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021ec2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800220be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022108`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002234f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002241a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800224ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800225b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002265b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022726`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800227ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022829`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022853`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022874`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022896`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021bc0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021bea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021d33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021d5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021ea8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021ed1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800220cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022117`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002235e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022429`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800224fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800225c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002266a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022735`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002280d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022837`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022861`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022883`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800228a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021bc0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021bea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021d33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021d5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021ea8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021ed1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800220cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022117`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002235e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022429`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800224fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800225c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002266a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022735`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002280d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022837`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022861`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022883`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800228a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002220e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002221d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002220e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002221d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222f9`

## string_xrefs

- `0x180021acf`: `CDlpActionLayoutUsb::PopulateOemPaths`
- `0x18002226a`: `CDlpActionLayoutUsb::PopulateOemPaths`
- `0x180022473`: `CDlpActionLayoutUsb::PopulateOemPaths`
- `0x1800227ad`: `CDlpActionLayoutUsb::PopulateOemPaths`
- `0x180021aa1`: `system32\recovery\reagent.xml`
- `0x180021b0e`: `reagent.xml`
- `0x180021b32`: `reagent.xml`
- `0x180021c07`: `system32\recovery\$PBR_ResetConfig.xml`
- `0x180021c82`: `sources\$PBR_ResetConfig.xml`
- `0x180021ca6`: `sources\$PBR_ResetConfig.xml`
- `0x180021d7a`: `system32\recovery\$PBR_Diskpart.txt`
- `0x1800221a5`: `LayoutUsb: Skipping OEM Path: [%s]`
- `0x1800221e8`: `LayoutUsb: Skipping duplicate file path: [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDlpActionLayoutUsb::PopulateOemPaths(
        CDlpActionLayoutUsb *this,
        unsigned __int16 *Src,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6,
        int a7)
{
  const unsigned __int16 *v9; // r14
  unsigned __int16 *v10; // r15
  signed int v11; // esi
  __int64 FirstFileW; // rbx
  signed int LastError; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  int StringCch; // eax
  int Internal; // eax
  int v22; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v24; // rax
  int v25; // eax
  DWORD FileAttributesW; // eax
  BOOL v27; // edi
  int v28; // eax
  int v29; // eax
  int v30; // eax
  HANDLE v31; // rax
  HANDLE v32; // rax
  int v33; // eax
  DWORD v34; // eax
  int v35; // edi
  int v36; // eax
  int v37; // eax
  int v38; // eax
  HANDLE v39; // rax
  HANDLE v40; // rax
  int v41; // eax
  __int64 v42; // rdi
  int v43; // eax
  LPCWSTR v44; // rsi
  BOOL VolumeInformationW; // r12d
  __int64 v46; // rcx
  const wchar_t *v47; // rdx
  int v48; // eax
  HANDLE v49; // rax
  int v50; // eax
  HANDLE v51; // rax
  int v52; // eax
  int OemFilePath; // eax
  int v54; // eax
  __int64 v55; // rcx
  __int64 v56; // rcx
  signed int v57; // eax
  __int64 v58; // rcx
  int v59; // eax
  __int64 v60; // rcx
  signed int v61; // eax
  void *v62; // rdi
  HANDLE v63; // rax
  int v64; // eax
  int v65; // eax
  DWORD v66; // edi
  BOOL v67; // edi
  HANDLE v68; // rax
  const unsigned __int16 *v69; // r12
  int v70; // eax
  __int64 v71; // rcx
  int v72; // eax
  __int64 v73; // rcx
  int v74; // eax
  void *v75; // rdi
  HANDLE v76; // rax
  int v77; // eax
  int v78; // eax
  DWORD v79; // edi
  BOOL v80; // edi
  HANDLE v81; // rax
  int v82; // eax
  int v83; // eax
  void *v84; // rdi
  HANDLE v85; // rax
  int v86; // eax
  int v87; // eax
  DWORD v88; // edi
  int v89; // edi
  HANDLE v90; // rax
  int v91; // eax
  int v92; // eax
  int v93; // eax
  WCHAR *v94; // rbx
  HANDLE v95; // rax
  WCHAR *v96; // rbx
  HANDLE v97; // rax
  void *v98; // rbx
  HANDLE v99; // rax
  HANDLE v100; // rax
  HANDLE v101; // rax
  LPDWORD lpMaximumComponentLength; // [rsp+20h] [rbp-E0h]
  LPDWORD lpFileSystemFlags; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v106; // [rsp+48h] [rbp-B8h] BYREF
  int v107; // [rsp+50h] [rbp-B0h] BYREF
  int v108; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v109; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v110; // [rsp+60h] [rbp-A0h]
  LPCWSTR v111; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpRootPathName; // [rsp+70h] [rbp-90h] BYREF
  __int64 v113; // [rsp+78h] [rbp-88h]
  void *Srca; // [rsp+80h] [rbp-80h]
  void *v115; // [rsp+88h] [rbp-78h]
  void *v116; // [rsp+90h] [rbp-70h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Buffer[520]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v115 = a4;
  Srca = a3;
  v116 = a5;
  v110 = a6;
  v9 = 0;
  lpFileName = 0;
  v10 = 0;
  v106 = 0;
  v109 = 0;
  v11 = 0;
  lpRootPathName = 0;
  v111 = 0;
  FirstFileW = -1;
  v113 = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v108 = 0;
  if ( a7 )
  {
    memset_0(Buffer, 0, sizeof(Buffer));
    if ( !GetSystemWindowsDirectoryW(Buffer, 0x208u) )
    {
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
        v14 = 0;
        if ( v11 < 0 )
        {
          LODWORD(lpFileSystemFlags) = v11;
          LODWORD(lpMaximumComponentLength) = 2185;
LABEL_10:
          v15 = *((_QWORD *)this + 11);
          goto LABEL_212;
        }
        goto LABEL_214;
      }
      goto LABEL_215;
    }
    v16 = CMiscHelpersT<CEmptyType>::CombinePath(Buffer, L"system32\\recovery\\reagent.xml", 0, &lpFileName);
    v11 = v16;
    if ( v16 < 0 )
    {
      v17 = *((_QWORD *)this + 11);
      if ( v17 )
      {
        LODWORD(lpFileSystemFlags) = v16;
        LODWORD(lpMaximumComponentLength) = 2186;
LABEL_14:
        v18 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v17,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionLayoutUsb::PopulateOemPaths",
                lpMaximumComponentLength,
                lpFileSystemFlags);
        v19 = (unsigned int)v18;
        if ( v18 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v18);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v19);
        goto LABEL_17;
      }
      goto LABEL_17;
    }
    v108 = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(L"reagent.xml", &v108);
    v11 = StringCch;
    if ( StringCch >= 0 )
    {
      Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(L"reagent.xml");
      v11 = Internal;
      if ( Internal < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
      v10 = v106;
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
    if ( v11 < 0 )
    {
      v17 = *((_QWORD *)this + 11);
      if ( v17 )
      {
        LODWORD(lpFileSystemFlags) = v11;
        LODWORD(lpMaximumComponentLength) = 2187;
        goto LABEL_14;
      }
LABEL_17:
      v9 = lpFileName;
      goto LABEL_215;
    }
    v9 = lpFileName;
    v22 = CDlpActionLayoutUsb::PopulateOemPath(this, lpFileName, v10);
    v11 = v22;
    if ( v22 < 0 )
    {
      v15 = *((_QWORD *)this + 11);
      if ( !v15 )
        goto LABEL_215;
      LODWORD(lpFileSystemFlags) = v22;
      LODWORD(lpMaximumComponentLength) = 2188;
      goto LABEL_212;
    }
    if ( v9 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)(v9 - 2));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      lpFileName = 0;
    }
    if ( v10 )
    {
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v10 - 2);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v10 = 0;
      v106 = 0;
    }
    v25 = CMiscHelpersT<CEmptyType>::CombinePath(Buffer, L"system32\\recovery\\$PBR_ResetConfig.xml", 0, &lpFileName);
    v11 = v25;
    if ( v25 < 0 )
    {
      v17 = *((_QWORD *)this + 11);
      if ( v17 )
      {
        LODWORD(lpFileSystemFlags) = v25;
        LODWORD(lpMaximumComponentLength) = 2195;
        goto LABEL_14;
      }
      goto LABEL_17;
    }
    v9 = lpFileName;
    FileAttributesW = GetFileAttributesW(lpFileName);
    v27 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( v27 )
    {
      v108 = 0;
      v28 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(L"sources\\$PBR_ResetConfig.xml", &v108);
      v11 = v28;
      if ( v28 >= 0 )
      {
        v29 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(L"sources\\$PBR_ResetConfig.xml");
        v11 = v29;
        if ( v29 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v29);
        v10 = v106;
      }
      else
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v28);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
      if ( v11 < 0 )
      {
        v15 = *((_QWORD *)this + 11);
        if ( !v15 )
          goto LABEL_215;
        LODWORD(lpFileSystemFlags) = v11;
        LODWORD(lpMaximumComponentLength) = 2199;
        goto LABEL_212;
      }
      v30 = CDlpActionLayoutUsb::PopulateOemPath(this, v9, v10);
      v11 = v30;
      if ( v30 < 0 )
      {
        v15 = *((_QWORD *)this + 11);
        if ( !v15 )
          goto LABEL_215;
        LODWORD(lpFileSystemFlags) = v30;
        LODWORD(lpMaximumComponentLength) = 2200;
        goto LABEL_212;
      }
    }
    if ( v9 )
    {
      v31 = GetProcessHeap();
      HeapFree(v31, 0, (LPVOID)(v9 - 2));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      lpFileName = 0;
    }
    if ( v10 )
    {
      v32 = GetProcessHeap();
      HeapFree(v32, 0, v10 - 2);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v10 = 0;
      v106 = 0;
    }
    v33 = CMiscHelpersT<CEmptyType>::CombinePath(Buffer, L"system32\\recovery\\$PBR_Diskpart.txt", 0, &lpFileName);
    v11 = v33;
    if ( v33 < 0 )
    {
      v17 = *((_QWORD *)this + 11);
      if ( v17 )
      {
        LODWORD(lpFileSystemFlags) = v33;
        LODWORD(lpMaximumComponentLength) = 2205;
        goto LABEL_14;
      }
      goto LABEL_17;
    }
    v9 = lpFileName;
    v34 = GetFileAttributesW(lpFileName);
    v35 = v34 != -1 && (v34 & 0x10) == 0;
    v108 = v35;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v11 = 0;
    if ( v35 )
    {
      v107 = 0;
      v36 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(L"sources\\$PBR_Diskpart.txt", &v107);
      v11 = v36;
      if ( v36 >= 0 )
      {
        v37 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(L"sources\\$PBR_Diskpart.txt");
        v11 = v37;
        if ( v37 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v37);
        v10 = v106;
      }
      else
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v36);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
      if ( v11 < 0 )
      {
        v15 = *((_QWORD *)this + 11);
        if ( !v15 )
          goto LABEL_215;
        LODWORD(lpFileSystemFlags) = v11;
        LODWORD(lpMaximumComponentLength) = 2209;
        goto LABEL_212;
      }
      v38 = CDlpActionLayoutUsb::PopulateOemPath(this, v9, v10);
      v11 = v38;
      if ( v38 < 0 )
      {
        v15 = *((_QWORD *)this + 11);
        if ( !v15 )
          goto LABEL_215;
        LODWORD(lpFileSystemFlags) = v38;
        LODWORD(lpMaximumComponentLength) = 2210;
        goto LABEL_212;
      }
    }
    if ( v9 )
    {
      v39 = GetProcessHeap();
      HeapFree(v39, 0, (LPVOID)(v9 - 2));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v9 = 0;
      lpFileName = 0;
    }
    if ( v10 )
    {
      v40 = GetProcessHeap();
      HeapFree(v40, 0, v10 - 2);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v10 = 0;
      v106 = 0;
    }
  }
  if ( !Src )
  {
LABEL_139:
    v62 = Srca;
    if ( !Srca )
      goto LABEL_165;
    if ( v9 )
    {
      v63 = GetProcessHeap();
      HeapFree(v63, 0, (LPVOID)(v9 - 2));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v9 = 0;
      lpFileName = 0;
    }
    v107 = 0;
    v64 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v62, &v107);
    v11 = v64;
    if ( v64 >= 0 )
    {
      v65 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v62);
      v11 = v65;
      if ( v65 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v65);
      v9 = lpFileName;
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v64);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
    if ( v11 < 0 )
    {
      v15 = *((_QWORD *)this + 11);
      if ( !v15 )
        goto LABEL_215;
      LODWORD(lpFileSystemFlags) = v11;
      LODWORD(lpMaximumComponentLength) = 2296;
      goto LABEL_212;
    }
    v66 = GetFileAttributesW(v9);
    v67 = v66 != -1 && (v66 >> 4) & 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v11 = 0;
    if ( v67 )
    {
      if ( v10 )
      {
        v68 = GetProcessHeap();
        HeapFree(v68, 0, v10 - 2);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v106 = 0;
      }
      v69 = v110;
      v70 = CDlpHelpersT<CEmptyType>::CombinePath(v110, L"Customizations", &v106);
      v11 = v70;
      if ( v70 < 0 )
      {
        v71 = *((_QWORD *)this + 11);
        if ( v71 )
        {
          LODWORD(lpFileSystemFlags) = v70;
          LODWORD(lpMaximumComponentLength) = 2302;
LABEL_159:
          v72 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v71,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDlpActionLayoutUsb::PopulateOemPaths",
                  lpMaximumComponentLength,
                  lpFileSystemFlags);
          v73 = (unsigned int)v72;
          if ( v72 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v72);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v73);
          goto LABEL_124;
        }
        goto LABEL_124;
      }
      v10 = v106;
      v74 = CDlpActionLayoutUsb::PopulateSplitOemPath(this, v9, v106);
      v11 = v74;
      if ( v74 < 0 )
      {
        v15 = *((_QWORD *)this + 11);
        if ( !v15 )
          goto LABEL_215;
        LODWORD(lpFileSystemFlags) = v74;
        LODWORD(lpMaximumComponentLength) = 2303;
        goto LABEL_212;
      }
    }
    else
    {
LABEL_165:
      v69 = v110;
    }
    v75 = v115;
    if ( v115 )
    {
      if ( v9 )
      {
        v76 = GetProcessHeap();
        HeapFree(v76, 0, (LPVOID)(v9 - 2));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v9 = 0;
        lpFileName = 0;
      }
      v107 = 0;
      v77 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v75, &v107);
      v11 = v77;
      if ( v77 >= 0 )
      {
        v78 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v75);
        v11 = v78;
        if ( v78 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v78);
        v9 = lpFileName;
      }
      else
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v77);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
      if ( v11 < 0 )
      {
        v15 = *((_QWORD *)this + 11);
        if ( !v15 )
          goto LABEL_215;
        LODWORD(lpFileSystemFlags) = v11;
        LODWORD(lpMaximumComponentLength) = 2310;
        goto LABEL_212;
      }
      v79 = GetFileAttributesW(v9);
      v80 = v79 != -1 && (v79 >> 4) & 1;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v11 = 0;
      if ( v80 )
      {
        if ( v10 )
        {
          v81 = GetProcessHeap();
          HeapFree(v81, 0, v10 - 2);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v106 = 0;
        }
        v82 = CDlpHelpersT<CEmptyType>::CombinePath(v69, L"OEM", &v106);
        v11 = v82;
        if ( v82 < 0 )
        {
          v71 = *((_QWORD *)this + 11);
          if ( v71 )
          {
            LODWORD(lpFileSystemFlags) = v82;
            LODWORD(lpMaximumComponentLength) = 2316;
            goto LABEL_159;
          }
LABEL_124:
          v10 = v106;
          goto LABEL_215;
        }
        v10 = v106;
        v83 = CDlpActionLayoutUsb::PopulateOemPath(this, v9, v106);
        v11 = v83;
        if ( v83 < 0 )
        {
          v15 = *((_QWORD *)this + 11);
          if ( !v15 )
            goto LABEL_215;
          LODWORD(lpFileSystemFlags) = v83;
          LODWORD(lpMaximumComponentLength) = 2317;
          goto LABEL_212;
        }
      }
    }
    v84 = v116;
    if ( !v116 )
      goto LABEL_215;
    if ( v9 )
    {
      v85 = GetProcessHeap();
      HeapFree(v85, 0, (LPVOID)(v9 - 2));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v9 = 0;
      lpFileName = 0;
    }
    v107 = 0;
    v86 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v84, &v107);
    v11 = v86;
    if ( v86 >= 0 )
    {
      v87 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v84);
      v11 = v87;
      if ( v87 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v87);
      v9 = lpFileName;
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v86);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
    if ( v11 < 0 )
    {
      v15 = *((_QWORD *)this + 11);
      if ( !v15 )
        goto LABEL_215;
      LODWORD(lpFileSystemFlags) = v11;
      LODWORD(lpMaximumComponentLength) = 2324;
      goto LABEL_212;
    }
    v88 = GetFileAttributesW(v9);
    if ( v88 == -1 )
      v89 = 0;
    else
      v89 = (v88 >> 4) & 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v11 = 0;
    if ( !v89 )
      goto LABEL_215;
    if ( v10 )
    {
      v90 = GetProcessHeap();
      HeapFree(v90, 0, v10 - 2);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v106 = 0;
    }
    v91 = CDlpHelpersT<CEmptyType>::CombinePath(v69, L"AutoApply", &v106);
    v11 = v91;
    if ( v91 >= 0 )
    {
      v10 = v106;
      v92 = CDlpActionLayoutUsb::PopulateOemPath(this, v9, v106);
      v11 = v92;
      if ( v92 < 0 )
      {
        v15 = *((_QWORD *)this + 11);
        if ( v15 )
        {
          LODWORD(lpFileSystemFlags) = v92;
          LODWORD(lpMaximumComponentLength) = 2331;
LABEL_212:
          v93 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v15,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDlpActionLayoutUsb::PopulateOemPaths",
                  lpMaximumComponentLength,
                  lpFileSystemFlags);
          v14 = (unsigned int)v93;
          if ( v93 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v93);
          goto LABEL_214;
        }
      }
      goto LABEL_215;
    }
    v71 = *((_QWORD *)this + 11);
    if ( v71 )
    {
      LODWORD(lpFileSystemFlags) = v91;
      LODWORD(lpMaximumComponentLength) = 2330;
      goto LABEL_159;
    }
    goto LABEL_124;
  }
  v41 = CMiscHelpersT<CEmptyType>::ParseFileName(Src, 0);
  v11 = v41;
  if ( v41 < 0 )
  {
    v15 = *((_QWORD *)this + 11);
    if ( !v15 )
      goto LABEL_215;
    LODWORD(lpFileSystemFlags) = v41;
    LODWORD(lpMaximumComponentLength) = 2224;
    goto LABEL_212;
  }
  v42 = v109;
  v43 = CMiscHelpersT<CEmptyType>::CombinePath(v109, &dword_180084C74, 0, &lpRootPathName);
  v11 = v43;
  if ( v43 < 0 )
  {
    v15 = *((_QWORD *)this + 11);
    if ( !v15 )
      goto LABEL_215;
    LODWORD(lpFileSystemFlags) = v43;
    LODWORD(lpMaximumComponentLength) = 2228;
    goto LABEL_212;
  }
  v44 = lpRootPathName;
  VolumeInformationW = GetVolumeInformationW(lpRootPathName, 0, 0, 0, 0, 0, 0, 0);
  v46 = *((_QWORD *)this + 11);
  if ( v46 )
  {
    v47 = L"Yes";
    if ( !VolumeInformationW )
      v47 = L"No";
    CDlpLogT<CEmptyType>::DlpLogFormat(v46, 2, L"LayoutUsb: OEM Folder: [%s], Volume Root: [%s]", v44, v47);
  }
  v48 = CDlpHelpersT<CEmptyType>::CombinePath(v42, L"*", &v111);
  v11 = v48;
  if ( v48 < 0 )
  {
    v15 = *((_QWORD *)this + 11);
    if ( !v15 )
      goto LABEL_215;
    LODWORD(lpFileSystemFlags) = v48;
    LODWORD(lpMaximumComponentLength) = 2234;
    goto LABEL_212;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (__int64)FindFirstFileW(v111, &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v113 = FirstFileW;
    do
    {
      if ( CompareStringW(0x409u, 1u, FindFileData.cFileName, -1, L".", -1) != 2
        && CompareStringW(0x409u, 1u, FindFileData.cFileName, -1, L"..", -1) != 2 )
      {
        if ( v9 )
        {
          v49 = GetProcessHeap();
          HeapFree(v49, 0, (LPVOID)(v9 - 2));
          v42 = v109;
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          lpFileName = 0;
        }
        v50 = CDlpHelpersT<CEmptyType>::CombinePath(v42, FindFileData.cFileName, &lpFileName);
        v11 = v50;
        if ( v50 < 0 )
        {
          v17 = *((_QWORD *)this + 11);
          if ( !v17 )
            goto LABEL_17;
          LODWORD(lpFileSystemFlags) = v50;
          LODWORD(lpMaximumComponentLength) = 2253;
          goto LABEL_14;
        }
        if ( v10 )
        {
          v51 = GetProcessHeap();
          HeapFree(v51, 0, v10 - 2);
          v42 = v109;
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v106 = 0;
        }
        v52 = CDlpHelpersT<CEmptyType>::CombinePath(v110, FindFileData.cFileName, &v106);
        v11 = v52;
        if ( v52 < 0 )
        {
          v58 = *((_QWORD *)this + 11);
          if ( v58 )
          {
            LODWORD(lpFileSystemFlags) = v52;
            LODWORD(lpMaximumComponentLength) = 2258;
            v59 = CDlpLogT<CEmptyType>::DlpLogFormat(
                    v58,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDlpActionLayoutUsb::PopulateOemPaths",
                    lpMaximumComponentLength,
                    lpFileSystemFlags);
            v60 = (unsigned int)v59;
            if ( v59 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v59);
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v60);
          }
          v9 = lpFileName;
          goto LABEL_124;
        }
        v10 = v106;
        v9 = lpFileName;
        OemFilePath = CDlpActionLayoutUsb::FindOemFilePath(this, lpFileName, v106, &v108);
        v11 = OemFilePath;
        if ( OemFilePath < 0 )
        {
          v15 = *((_QWORD *)this + 11);
          if ( !v15 )
            goto LABEL_215;
          LODWORD(lpFileSystemFlags) = OemFilePath;
          LODWORD(lpMaximumComponentLength) = 2262;
          goto LABEL_212;
        }
        if ( v108 )
        {
          v56 = *((_QWORD *)this + 11);
          if ( v56 )
            CDlpLogT<CEmptyType>::DlpLogFormat(v56, 2, L"LayoutUsb: Skipping duplicate file path: [%s]", v9);
        }
        else
        {
          v54 = CDlpActionLayoutUsb::PopulateOemPath(this, v9, v10);
          v11 = v54;
          if ( v54 == -2147024891 )
          {
            if ( !VolumeInformationW )
              goto LABEL_109;
            v55 = *((_QWORD *)this + 11);
            if ( v55 )
              CDlpLogT<CEmptyType>::DlpLogFormat(v55, 3, L"LayoutUsb: Skipping OEM Path: [%s]", v42);
            v11 = 0;
          }
          else if ( v54 < 0 )
          {
LABEL_109:
            v15 = *((_QWORD *)this + 11);
            if ( !v15 )
              goto LABEL_215;
            LODWORD(lpFileSystemFlags) = v54;
            LODWORD(lpMaximumComponentLength) = 2274;
            goto LABEL_212;
          }
        }
      }
    }
    while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
    if ( GetLastError() == 18 )
      goto LABEL_139;
    v57 = GetLastError();
    v11 = v57;
    if ( v57 )
    {
      if ( v57 > 0 )
        v11 = (unsigned __int16)v57 | 0x80070000;
    }
    else
    {
      v11 = -2147467259;
    }
    if ( !*((_QWORD *)this + 11) )
      goto LABEL_215;
    v14 = 0;
    if ( v11 >= 0 )
      goto LABEL_214;
    LODWORD(lpFileSystemFlags) = v11;
    LODWORD(lpMaximumComponentLength) = 2287;
    goto LABEL_10;
  }
  FirstFileW = -1;
  v113 = -1;
  v61 = GetLastError();
  v11 = v61;
  if ( v61 )
  {
    if ( v61 > 0 )
      v11 = (unsigned __int16)v61 | 0x80070000;
  }
  else
  {
    v11 = -2147467259;
  }
  if ( *((_QWORD *)this + 11) )
  {
    v14 = 0;
    if ( v11 < 0 )
    {
      LODWORD(lpFileSystemFlags) = v11;
      LODWORD(lpMaximumComponentLength) = 2240;
      goto LABEL_10;
    }
LABEL_214:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v14);
  }
LABEL_215:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose((HANDLE)FirstFileW);
  if ( v111 )
  {
    v94 = (WCHAR *)(v111 - 2);
    v95 = GetProcessHeap();
    HeapFree(v95, 0, v94);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( lpRootPathName )
  {
    v96 = (WCHAR *)(lpRootPathName - 2);
    v97 = GetProcessHeap();
    HeapFree(v97, 0, v96);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v109 )
  {
    v98 = (void *)(v109 - 4);
    v99 = GetProcessHeap();
    HeapFree(v99, 0, v98);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v10 )
  {
    v100 = GetProcessHeap();
    HeapFree(v100, 0, v10 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v9 )
  {
    v101 = GetProcessHeap();
    HeapFree(v101, 0, (LPVOID)(v9 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180021988  push    rbp
0x18002198a  push    rbx
0x18002198b  push    rsi
0x18002198c  push    rdi
0x18002198d  push    r12
0x18002198f  push    r13
0x180021991  push    r14
0x180021993  push    r15
0x180021995  lea     rbp, [rsp-618h]
0x18002199d  sub     rsp, 718h
0x1800219a4  mov     rax, cs:__security_cookie
0x1800219ab  xor     rax, rsp
0x1800219ae  mov     [rbp+650h+var_50], rax
0x1800219b5  mov     [rbp+650h+var_6C8], r9
0x1800219b9  mov     [rbp+650h+Src], r8
0x1800219bd  mov     r12, rdx
0x1800219c0  mov     r13, rcx
0x1800219c3  mov     rax, [rbp+650h+arg_20]
0x1800219ca  mov     [rbp+650h+var_6C0], rax
0x1800219ce  mov     rax, [rbp+650h+arg_28]
0x1800219d5  mov     [rsp+750h+var_6F0], rax
0x1800219da  xor     r14d, r14d
0x1800219dd  mov     [rsp+750h+lpFileName], r14
0x1800219e2  xor     r15d, r15d
0x1800219e5  mov     [rsp+750h+var_708], r15
0x1800219ea  mov     [rsp+750h+var_6F8], r15
0x1800219ef  xor     esi, esi
0x1800219f1  mov     [rsp+750h+lpRootPathName], rsi
0x1800219f6  xor     ecx, ecx
0x1800219f8  mov     [rsp+750h+var_6E8], rcx
0x1800219fd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180021a01  mov     [rsp+750h+var_6D8], rbx
0x180021a06  xor     edx, edx; Val
0x180021a08  mov     r8d, 250h; Size
0x180021a0e  lea     rcx, [rbp+650h+FindFileData]; void *
0x180021a12  call    memset_0
0x180021a17  mov     [rsp+750h+var_6FC], esi
0x180021a1b  cmp     [rbp+650h+arg_30], esi
0x180021a21  jz      loc_180021EE6
0x180021a27  xor     edx, edx; Val
0x180021a29  mov     r8d, 410h; Size
0x180021a2f  lea     rcx, [rbp+650h+Buffer]; void *
0x180021a36  call    memset_0
0x180021a3b  mov     edx, 208h; uSize
0x180021a40  lea     rcx, [rbp+650h+Buffer]; lpBuffer
0x180021a47  call    cs:__imp_GetSystemWindowsDirectoryW
0x180021a4d  test    eax, eax
0x180021a4f  jnz     short loc_180021A99
0x180021a51  call    cs:__imp_GetLastError
0x180021a57  mov     esi, eax
0x180021a59  test    eax, eax
0x180021a5b  jnz     short loc_180021A64
0x180021a5d  mov     esi, 80004005h
0x180021a62  jmp     short loc_180021A6F
0x180021a64  jle     short loc_180021A6F
0x180021a66  movzx   esi, ax
0x180021a69  or      esi, 80070000h
0x180021a6f  cmp     qword ptr [r13+58h], 0
0x180021a74  jz      loc_1800227D5
0x180021a7a  xor     ecx, ecx
0x180021a7c  test    esi, esi
0x180021a7e  jns     loc_1800227D0
0x180021a84  mov     dword ptr [rsp+750h+lpFileSystemFlags], esi
0x180021a88  mov     dword ptr [rsp+750h+lpMaximumComponentLength], 889h
0x180021a90  mov     rcx, [r13+58h]
0x180021a94  jmp     loc_1800227AD
0x180021a99  lea     r9, [rsp+750h+lpFileName]
0x180021a9e  xor     r8d, r8d
0x180021aa1  lea     rdx, aSystem32Recove; "system32\\recovery\\reagent.xml"
0x180021aa8  lea     rcx, [rbp+650h+Buffer]
0x180021aaf  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180021ab4  mov     esi, eax
0x180021ab6  test    eax, eax
0x180021ab8  jns     short loc_180021B01
0x180021aba  mov     rcx, [r13+58h]
0x180021abe  test    rcx, rcx
0x180021ac1  jz      short loc_180021AF7
0x180021ac3  mov     dword ptr [rsp+750h+lpFileSystemFlags], eax
0x180021ac7  mov     dword ptr [rsp+750h+lpMaximumComponentLength], 88Ah
0x180021acf  lea     r9, aCdlpactionlayo_40; "CDlpActionLayoutUsb::PopulateOemPaths"
0x180021ad6  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180021add  mov     edx, 4
0x180021ae2  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180021ae7  test    eax, eax
0x180021ae9  mov     ecx, eax
0x180021aeb  jns     short loc_180021AF2
0x180021aed  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180021af2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021af7  mov     r14, [rsp+750h+lpFileName]
0x180021afc  jmp     loc_1800227D5
0x180021b01  mov     [rsp+750h+var_6FC], 0
0x180021b09  lea     rdx, [rsp+750h+var_6FC]
0x180021b0e  lea     rcx, aReagentXml; "reagent.xml"
0x180021b15  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180021b1a  mov     esi, eax
0x180021b1c  test    eax, eax
0x180021b1e  jns     short loc_180021B29
0x180021b20  mov     ecx, eax
0x180021b22  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180021b27  jmp     short loc_180021B50
0x180021b29  lea     r8, [rsp+750h+var_708]
0x180021b2e  mov     edx, [rsp+750h+var_6FC]
0x180021b32  lea     rcx, aReagentXml; "reagent.xml"
0x180021b39  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180021b3e  mov     esi, eax
0x180021b40  test    eax, eax
0x180021b42  jns     short loc_180021B4B
0x180021b44  mov     ecx, eax
0x180021b46  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180021b4b  mov     r15, [rsp+750h+var_708]
0x180021b50  mov     ecx, esi
0x180021b52  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021b57  test    esi, esi
0x180021b59  jns     short loc_180021B75
0x180021b5b  mov     rcx, [r13+58h]
0x180021b5f  test    rcx, rcx
0x180021b62  jz      short loc_180021AF7
0x180021b64  mov     dword ptr [rsp+750h+lpFileSystemFlags], esi
0x180021b68  mov     dword ptr [rsp+750h+lpMaximumComponentLength], 88Bh
0x180021b70  jmp     loc_180021ACF
0x180021b75  mov     r14, [rsp+750h+lpFileName]
0x180021b7a  mov     r8, r15; unsigned __int16 *
0x180021b7d  mov     rdx, r14; unsigned __int16 *
0x180021b80  mov     rcx, r13; this
0x180021b83  call    ?PopulateOemPath@CDlpActionLayoutUsb@@AEAAJPEBG0@Z; CDlpActionLayoutUsb::PopulateOemPath(ushort const *,ushort const *)
0x180021b88  mov     esi, eax
0x180021b8a  test    eax, eax
0x180021b8c  jns     short loc_180021BAC
0x180021b8e  mov     rcx, [r13+58h]
0x180021b92  test    rcx, rcx
0x180021b95  jz      loc_1800227D5
0x180021b9b  mov     dword ptr [rsp+750h+lpFileSystemFlags], eax
0x180021b9f  mov     dword ptr [rsp+750h+lpMaximumComponentLength], 88Ch
0x180021ba7  jmp     loc_1800227AD
0x180021bac  test    r14, r14
0x180021baf  jz      short loc_180021BD6
0x180021bb1  call    cs:__imp_GetProcessHeap
0x180021bb7  mov     rcx, rax; hHeap
0x180021bba  lea     r8, [r14-4]; lpMem
0x180021bbe  xor     edx, edx; dwFlags
0x180021bc0  call    cs:__imp_HeapFree
0x180021bc6  xor     ecx, ecx
0x180021bc8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021bcd  mov     [rsp+750h+lpFileName], 0
0x180021bd6  test    r15, r15
0x180021bd9  jz      short loc_180021BFF
0x180021bdb  call    cs:__imp_GetProcessHeap
0x180021be1  mov     rcx, rax; hHeap
0x180021be4  lea     r8, [r15-4]; lpMem
0x180021be8  xor     edx, edx; dwFlags
0x180021bea  call    cs:__imp_HeapFree
0x180021bf0  xor     ecx, ecx
0x180021bf2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021bf7  xor     r15d, r15d
0x180021bfa  mov     [rsp+750h+var_708], r15
0x180021bff  lea     r9, [rsp+750h+lpFileName]
0x180021c04  xor     r8d, r8d
0x180021c07  lea     rdx, aSystem32Recove_1; "system32\\recovery\\$PBR_ResetConfig.xm"...
0x180021c0e  lea     rcx, [rbp+650h+Buffer]
0x180021c15  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180021c1a  mov     esi, eax
0x180021c1c  test    eax, eax
0x180021c1e  jns     short loc_180021C3E
0x180021c20  mov     rcx, [r13+58h]
0x180021c24  test    rcx, rcx
0x180021c27  jz      loc_180021AF7
0x180021c2d  mov     dword ptr [rsp+750h+lpFileSystemFlags], eax
0x180021c31  mov     dword ptr [rsp+750h+lpMaximumComponentLength], 893h
0x180021c39  jmp     loc_180021ACF
0x180021c3e  mov     r14, [rsp+750h+lpFileName]
0x180021c43  mov     rcx, r14; lpFileName
0x180021c46  call    cs:__imp_GetFileAttributesW
0x180021c4c  mov     edi, eax
0x180021c4e  cmp     eax, 0FFFFFFFFh
0x180021c51  jz      short loc_180021C5D
0x180021c53  shr     edi, 4
0x180021c56  not     edi
0x180021c58  and     edi, 1
0x180021c5b  jmp     short loc_180021C5F
0x180021c5d  xor     edi, edi
0x180021c5f  xor     ecx, ecx
0x180021c61  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021c66  xor     ecx, ecx
0x180021c68  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021c6d  test    edi, edi
0x180021c6f  jz      loc_180021D1F
0x180021c75  mov     [rsp+750h+var_6FC], 0
0x180021c7d  lea     rdx, [rsp+750h+var_6FC]
0x180021c82  lea     rcx, aSourcesPbrRese; "sources\\$PBR_ResetConfig.xml"
0x180021c89  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180021c8e  mov     esi, eax
0x180021c90  test    eax, eax
0x180021c92  jns     short loc_180021C9D
0x180021c94  mov     ecx, eax
0x180021c96  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180021c9b  jmp     short loc_180021CC4
0x180021c9d  lea     r8, [rsp+750h+var_708]
0x180021ca2  mov     edx, [rsp+750h+var_6FC]
0x180021ca6  lea     rcx, aSourcesPbrRese; "sources\\$PBR_ResetConfig.xml"
0x180021cad  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180021cb2  mov     esi, eax
0x180021cb4  test    eax, eax
0x180021cb6  jns     short loc_180021CBF
0x180021cb8  mov     ecx, eax
0x180021cba  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180021cbf  mov     r15, [rsp+750h+var_708]
0x180021cc4  mov     ecx, esi
0x180021cc6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021ccb  test    esi, esi
0x180021ccd  jns     short loc_180021CED
0x180021ccf  mov     rcx, [r13+58h]
0x180021cd3  test    rcx, rcx
0x180021cd6  jz      loc_1800227D5
0x180021cdc  mov     dword ptr [rsp+750h+lpFileSystemFlags], esi
0x180021ce0  mov     dword ptr [rsp+750h+lpMaximumComponentLength], 897h
0x180021ce8  jmp     loc_1800227AD
0x180021ced  mov     r8, r15; unsigned __int16 *
0x180021cf0  mov     rdx, r14; unsigned __int16 *
0x180021cf3  mov     rcx, r13; this
0x180021cf6  call    ?PopulateOemPath@CDlpActionLayoutUsb@@AEAAJPEBG0@Z; CDlpActionLayoutUsb::PopulateOemPath(ushort const *,ushort const *)
0x180021cfb  mov     esi, eax
0x180021cfd  test    eax, eax
0x180021cff  jns     short loc_180021D1F
0x180021d01  mov     rcx, [r13+58h]
0x180021d05  test    rcx, rcx
0x180021d08  jz      loc_1800227D5
0x180021d0e  mov     dword ptr [rsp+750h+lpFileSystemFlags], eax
0x180021d12  mov     dword ptr [rsp+750h+lpMaximumComponentLength], 898h
0x180021d1a  jmp     loc_1800227AD
0x180021d1f  test    r14, r14
0x180021d22  jz      short loc_180021D49
0x180021d24  call    cs:__imp_GetProcessHeap
0x180021d2a  mov     rcx, rax; hHeap
0x180021d2d  lea     r8, [r14-4]; lpMem
0x180021d31  xor     edx, edx; dwFlags
0x180021d33  call    cs:__imp_HeapFree
0x180021d39  xor     ecx, ecx
0x180021d3b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021d40  mov     [rsp+750h+lpFileName], 0
0x180021d49  test    r15, r15
0x180021d4c  jz      short loc_180021D72
0x180021d4e  call    cs:__imp_GetProcessHeap
0x180021d54  mov     rcx, rax; hHeap
0x180021d57  lea     r8, [r15-4]; lpMem
0x180021d5b  xor     edx, edx; dwFlags
0x180021d5d  call    cs:__imp_HeapFree
0x180021d63  xor     ecx, ecx
0x180021d65  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021d6a  xor     r15d, r15d
0x180021d6d  mov     [rsp+750h+var_708], r15
0x180021d72  lea     r9, [rsp+750h+lpFileName]
0x180021d77  xor     r8d, r8d
0x180021d7a  lea     rdx, aSystem32Recove_0; "system32\\recovery\\$PBR_Diskpart.txt"
0x180021d81  lea     rcx, [rbp+650h+Buffer]
0x180021d88  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180021d8d  mov     esi, eax
0x180021d8f  test    eax, eax
0x180021d91  jns     short loc_180021DB1
0x180021d93  mov     rcx, [r13+58h]
0x180021d97  test    rcx, rcx
0x180021d9a  jz      loc_180021AF7
0x180021da0  mov     dword ptr [rsp+750h+lpFileSystemFlags], eax
0x180021da4  mov     dword ptr [rsp+750h+lpMaximumComponentLength], 89Dh
0x180021dac  jmp     loc_180021ACF
0x180021db1  mov     r14, [rsp+750h+lpFileName]
0x180021db6  mov     rcx, r14; lpFileName
0x180021db9  call    cs:__imp_GetFileAttributesW
0x180021dbf  mov     edi, eax
0x180021dc1  cmp     eax, 0FFFFFFFFh
0x180021dc4  jz      short loc_180021DD0
0x180021dc6  shr     edi, 4
0x180021dc9  not     edi
0x180021dcb  and     edi, 1
0x180021dce  jmp     short loc_180021DD2
0x180021dd0  xor     edi, edi
0x180021dd2  mov     [rsp+750h+var_6FC], edi
0x180021dd6  xor     ecx, ecx
0x180021dd8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021ddd  xor     ecx, ecx
0x180021ddf  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021de4  xor     esi, esi
0x180021de6  test    edi, edi
0x180021de8  jz      loc_180021E94
0x180021dee  mov     [rsp+750h+var_700], esi
0x180021df2  lea     rdx, [rsp+750h+var_700]
0x180021df7  lea     rcx, aSourcesPbrDisk; "sources\\$PBR_Diskpart.txt"
0x180021dfe  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180021e03  mov     esi, eax
0x180021e05  test    eax, eax
0x180021e07  jns     short loc_180021E12
0x180021e09  mov     ecx, eax
0x180021e0b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180021e10  jmp     short loc_180021E39
0x180021e12  lea     r8, [rsp+750h+var_708]
0x180021e17  mov     edx, [rsp+750h+var_700]
0x180021e1b  lea     rcx, aSourcesPbrDisk; "sources\\$PBR_Diskpart.txt"
0x180021e22  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180021e27  mov     esi, eax
0x180021e29  test    eax, eax
0x180021e2b  jns     short loc_180021E34
  ... truncated ...
```
