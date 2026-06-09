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
  const WCHAR *v9; // r14
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
  int v21; // eax
  int v22; // eax
  HANDLE ProcessHeap; // rax
  int v24; // eax
  DWORD FileAttributesW; // eax
  BOOL v26; // edi
  int v27; // eax
  int v28; // eax
  int v29; // eax
  HANDLE v30; // rax
  int v31; // eax
  DWORD v32; // eax
  int v33; // edi
  int v34; // eax
  int v35; // eax
  int v36; // eax
  HANDLE v37; // rax
  int v38; // eax
  __int64 v39; // rdi
  int v40; // eax
  LPCWSTR v41; // rsi
  BOOL VolumeInformationW; // r12d
  __int64 v43; // rcx
  const wchar_t *v44; // rdx
  int v45; // eax
  HANDLE v46; // rax
  int v47; // eax
  HANDLE v48; // rax
  int v49; // eax
  int OemFilePath; // eax
  int v51; // eax
  __int64 v52; // rcx
  __int64 v53; // rcx
  signed int v54; // eax
  __int64 v55; // rcx
  int v56; // eax
  __int64 v57; // rcx
  signed int v58; // eax
  _WORD *v59; // rdi
  HANDLE v60; // rax
  int v61; // eax
  int v62; // eax
  DWORD v63; // edi
  BOOL v64; // edi
  HANDLE v65; // rax
  const unsigned __int16 *v66; // r12
  int v67; // eax
  __int64 v68; // rcx
  int v69; // eax
  __int64 v70; // rcx
  int v71; // eax
  _WORD *v72; // rdi
  HANDLE v73; // rax
  int v74; // eax
  int v75; // eax
  DWORD v76; // edi
  BOOL v77; // edi
  HANDLE v78; // rax
  int v79; // eax
  int v80; // eax
  _WORD *v81; // rdi
  HANDLE v82; // rax
  int v83; // eax
  int v84; // eax
  DWORD v85; // edi
  int v86; // edi
  HANDLE v87; // rax
  int v88; // eax
  int v89; // eax
  int v90; // eax
  WCHAR *v91; // rbx
  HANDLE v92; // rax
  WCHAR *v93; // rbx
  HANDLE v94; // rax
  void *v95; // rbx
  HANDLE v96; // rax
  HANDLE v97; // rax
  HANDLE v98; // rax
  LPDWORD lpMaximumComponentLength; // [rsp+20h] [rbp-E0h]
  LPDWORD lpFileSystemFlags; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v103; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v104; // [rsp+50h] [rbp-B0h] BYREF
  int v105; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v106; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v107; // [rsp+60h] [rbp-A0h]
  LPCWSTR v108; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpRootPathName; // [rsp+70h] [rbp-90h]
  __int64 v110; // [rsp+78h] [rbp-88h]
  void *Srca; // [rsp+80h] [rbp-80h]
  void *v112; // [rsp+88h] [rbp-78h]
  void *v113; // [rsp+90h] [rbp-70h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Buffer[520]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v112 = a4;
  Srca = a3;
  v113 = a5;
  v107 = a6;
  v9 = 0;
  lpFileName = 0;
  v10 = 0;
  v103 = 0;
  v106 = 0;
  v11 = 0;
  lpRootPathName = 0;
  v108 = 0;
  FirstFileW = -1;
  v110 = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v105 = 0;
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
          goto LABEL_206;
        }
        goto LABEL_208;
      }
      goto LABEL_209;
    }
    v16 = CMiscHelpersT<CEmptyType>::CombinePath((__int64)Buffer, (__int64)L"system32\\recovery\\reagent.xml", 0);
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
                4u,
                (__int64)L"%s(%d): Result = 0x%X",
                L"CDlpActionLayoutUsb::PopulateOemPaths",
                lpMaximumComponentLength,
                lpFileSystemFlags);
        v19 = (unsigned int)v18;
        if ( v18 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v18);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v19);
        goto LABEL_17;
      }
      goto LABEL_17;
    }
    v105 = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(L"reagent.xml", &v105);
    v11 = StringCch;
    if ( StringCch >= 0 )
    {
      v21 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
              L"reagent.xml",
              v105,
              &v103);
      v11 = v21;
      if ( v21 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v21);
      v10 = v103;
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
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
      goto LABEL_209;
    }
    v9 = lpFileName;
    v22 = CDlpActionLayoutUsb::PopulateOemPath(this, lpFileName, v10);
    v11 = v22;
    if ( v22 < 0 )
    {
      v15 = *((_QWORD *)this + 11);
      if ( !v15 )
        goto LABEL_209;
      LODWORD(lpFileSystemFlags) = v22;
      LODWORD(lpMaximumComponentLength) = 2188;
      goto LABEL_206;
    }
    if ( v10 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v10 - 2);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v10 = 0;
      v103 = 0;
    }
    v24 = CMiscHelpersT<CEmptyType>::CombinePath(
            (__int64)Buffer,
            (__int64)L"system32\\recovery\\$PBR_ResetConfig.xml",
            0);
    v11 = v24;
    if ( v24 < 0 )
    {
      v17 = *((_QWORD *)this + 11);
      if ( v17 )
      {
        LODWORD(lpFileSystemFlags) = v24;
        LODWORD(lpMaximumComponentLength) = 2195;
        goto LABEL_14;
      }
      goto LABEL_17;
    }
    v9 = lpFileName;
    FileAttributesW = GetFileAttributesW(lpFileName);
    v26 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( v26 )
    {
      v105 = 0;
      v27 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(L"sources\\$PBR_ResetConfig.xml", &v105);
      v11 = v27;
      if ( v27 >= 0 )
      {
        v28 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                L"sources\\$PBR_ResetConfig.xml",
                v105,
                &v103);
        v11 = v28;
        if ( v28 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v28);
        v10 = v103;
      }
      else
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v27);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
      if ( v11 < 0 )
      {
        v15 = *((_QWORD *)this + 11);
        if ( !v15 )
          goto LABEL_209;
        LODWORD(lpFileSystemFlags) = v11;
        LODWORD(lpMaximumComponentLength) = 2199;
        goto LABEL_206;
      }
      v29 = CDlpActionLayoutUsb::PopulateOemPath(this, lpFileName, v10);
      v11 = v29;
      if ( v29 < 0 )
      {
        v15 = *((_QWORD *)this + 11);
        if ( !v15 )
          goto LABEL_209;
        LODWORD(lpFileSystemFlags) = v29;
        LODWORD(lpMaximumComponentLength) = 2200;
        goto LABEL_206;
      }
    }
    if ( v10 )
    {
      v30 = GetProcessHeap();
      HeapFree(v30, 0, v10 - 2);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v10 = 0;
      v103 = 0;
    }
    v31 = CMiscHelpersT<CEmptyType>::CombinePath((__int64)Buffer, (__int64)L"system32\\recovery\\$PBR_Diskpart.txt", 0);
    v11 = v31;
    if ( v31 < 0 )
    {
      v17 = *((_QWORD *)this + 11);
      if ( v17 )
      {
        LODWORD(lpFileSystemFlags) = v31;
        LODWORD(lpMaximumComponentLength) = 2205;
        goto LABEL_14;
      }
      goto LABEL_17;
    }
    v9 = lpFileName;
    v32 = GetFileAttributesW(lpFileName);
    v33 = v32 != -1 && (v32 & 0x10) == 0;
    v105 = v33;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v11 = 0;
    if ( v33 )
    {
      v104 = 0;
      v34 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(L"sources\\$PBR_Diskpart.txt", &v104);
      v11 = v34;
      if ( v34 >= 0 )
      {
        v35 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                L"sources\\$PBR_Diskpart.txt",
                v104,
                &v103);
        v11 = v35;
        if ( v35 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v35);
        v10 = v103;
      }
      else
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v34);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
      if ( v11 < 0 )
      {
        v15 = *((_QWORD *)this + 11);
        if ( !v15 )
          goto LABEL_209;
        LODWORD(lpFileSystemFlags) = v11;
        LODWORD(lpMaximumComponentLength) = 2209;
        goto LABEL_206;
      }
      v36 = CDlpActionLayoutUsb::PopulateOemPath(this, lpFileName, v10);
      v11 = v36;
      if ( v36 < 0 )
      {
        v15 = *((_QWORD *)this + 11);
        if ( !v15 )
          goto LABEL_209;
        LODWORD(lpFileSystemFlags) = v36;
        LODWORD(lpMaximumComponentLength) = 2210;
        goto LABEL_206;
      }
    }
    if ( v10 )
    {
      v37 = GetProcessHeap();
      HeapFree(v37, 0, v10 - 2);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v10 = 0;
      v103 = 0;
    }
  }
  if ( !Src )
  {
LABEL_133:
    v59 = Srca;
    if ( !Srca )
      goto LABEL_159;
    if ( v9 )
    {
      v60 = GetProcessHeap();
      HeapFree(v60, 0, (LPVOID)(v9 - 2));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v9 = 0;
      lpFileName = 0;
    }
    v104 = 0;
    v61 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v59, &v104);
    v11 = v61;
    if ( v61 >= 0 )
    {
      v62 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v59, v104, &lpFileName);
      v11 = v62;
      if ( v62 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v62);
      v9 = lpFileName;
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v61);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
    if ( v11 < 0 )
    {
      v15 = *((_QWORD *)this + 11);
      if ( !v15 )
        goto LABEL_209;
      LODWORD(lpFileSystemFlags) = v11;
      LODWORD(lpMaximumComponentLength) = 2296;
      goto LABEL_206;
    }
    v63 = GetFileAttributesW(v9);
    v64 = v63 != -1 && (v63 >> 4) & 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v11 = 0;
    if ( v64 )
    {
      if ( v10 )
      {
        v65 = GetProcessHeap();
        HeapFree(v65, 0, v10 - 2);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v103 = 0;
      }
      v66 = v107;
      v67 = CDlpHelpersT<CEmptyType>::CombinePath((__int64)v107, (__int64)L"Customizations", (__int64)&v103);
      v11 = v67;
      if ( v67 < 0 )
      {
        v68 = *((_QWORD *)this + 11);
        if ( v68 )
        {
          LODWORD(lpFileSystemFlags) = v67;
          LODWORD(lpMaximumComponentLength) = 2302;
LABEL_153:
          v69 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v68,
                  4u,
                  (__int64)L"%s(%d): Result = 0x%X",
                  L"CDlpActionLayoutUsb::PopulateOemPaths",
                  lpMaximumComponentLength,
                  lpFileSystemFlags);
          v70 = (unsigned int)v69;
          if ( v69 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v69);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v70);
          goto LABEL_118;
        }
        goto LABEL_118;
      }
      v10 = v103;
      v71 = CDlpActionLayoutUsb::PopulateSplitOemPath(this, v9, v103);
      v11 = v71;
      if ( v71 < 0 )
      {
        v15 = *((_QWORD *)this + 11);
        if ( !v15 )
          goto LABEL_209;
        LODWORD(lpFileSystemFlags) = v71;
        LODWORD(lpMaximumComponentLength) = 2303;
        goto LABEL_206;
      }
    }
    else
    {
LABEL_159:
      v66 = v107;
    }
    v72 = v112;
    if ( v112 )
    {
      if ( v9 )
      {
        v73 = GetProcessHeap();
        HeapFree(v73, 0, (LPVOID)(v9 - 2));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v9 = 0;
        lpFileName = 0;
      }
      v104 = 0;
      v74 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v72, &v104);
      v11 = v74;
      if ( v74 >= 0 )
      {
        v75 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v72, v104, &lpFileName);
        v11 = v75;
        if ( v75 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v75);
        v9 = lpFileName;
      }
      else
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v74);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
      if ( v11 < 0 )
      {
        v15 = *((_QWORD *)this + 11);
        if ( !v15 )
          goto LABEL_209;
        LODWORD(lpFileSystemFlags) = v11;
        LODWORD(lpMaximumComponentLength) = 2310;
        goto LABEL_206;
      }
      v76 = GetFileAttributesW(v9);
      v77 = v76 != -1 && (v76 >> 4) & 1;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v11 = 0;
      if ( v77 )
      {
        if ( v10 )
        {
          v78 = GetProcessHeap();
          HeapFree(v78, 0, v10 - 2);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v103 = 0;
        }
        v79 = CDlpHelpersT<CEmptyType>::CombinePath((__int64)v66, (__int64)L"OEM", (__int64)&v103);
        v11 = v79;
        if ( v79 < 0 )
        {
          v68 = *((_QWORD *)this + 11);
          if ( v68 )
          {
            LODWORD(lpFileSystemFlags) = v79;
            LODWORD(lpMaximumComponentLength) = 2316;
            goto LABEL_153;
          }
LABEL_118:
          v10 = v103;
          goto LABEL_209;
        }
        v10 = v103;
        v80 = CDlpActionLayoutUsb::PopulateOemPath(this, v9, v103);
        v11 = v80;
        if ( v80 < 0 )
        {
          v15 = *((_QWORD *)this + 11);
          if ( !v15 )
            goto LABEL_209;
          LODWORD(lpFileSystemFlags) = v80;
          LODWORD(lpMaximumComponentLength) = 2317;
          goto LABEL_206;
        }
      }
    }
    v81 = v113;
    if ( !v113 )
      goto LABEL_209;
    if ( v9 )
    {
      v82 = GetProcessHeap();
      HeapFree(v82, 0, (LPVOID)(v9 - 2));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v9 = 0;
      lpFileName = 0;
    }
    v104 = 0;
    v83 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v81, &v104);
    v11 = v83;
    if ( v83 >= 0 )
    {
      v84 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v81, v104, &lpFileName);
      v11 = v84;
      if ( v84 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v84);
      v9 = lpFileName;
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v83);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
    if ( v11 < 0 )
    {
      v15 = *((_QWORD *)this + 11);
      if ( !v15 )
        goto LABEL_209;
      LODWORD(lpFileSystemFlags) = v11;
      LODWORD(lpMaximumComponentLength) = 2324;
      goto LABEL_206;
    }
    v85 = GetFileAttributesW(v9);
    if ( v85 == -1 )
      v86 = 0;
    else
      v86 = (v85 >> 4) & 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v11 = 0;
    if ( !v86 )
      goto LABEL_209;
    if ( v10 )
    {
      v87 = GetProcessHeap();
      HeapFree(v87, 0, v10 - 2);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v103 = 0;
    }
    v88 = CDlpHelpersT<CEmptyType>::CombinePath((__int64)v66, (__int64)L"AutoApply", (__int64)&v103);
    v11 = v88;
    if ( v88 >= 0 )
    {
      v10 = v103;
      v89 = CDlpActionLayoutUsb::PopulateOemPath(this, v9, v103);
      v11 = v89;
      if ( v89 < 0 )
      {
        v15 = *((_QWORD *)this + 11);
        if ( v15 )
        {
          LODWORD(lpFileSystemFlags) = v89;
          LODWORD(lpMaximumComponentLength) = 2331;
LABEL_206:
          v90 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v15,
                  4u,
                  (__int64)L"%s(%d): Result = 0x%X",
                  L"CDlpActionLayoutUsb::PopulateOemPaths",
                  lpMaximumComponentLength,
                  lpFileSystemFlags);
          v14 = (unsigned int)v90;
          if ( v90 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v90);
          goto LABEL_208;
        }
      }
      goto LABEL_209;
    }
    v68 = *((_QWORD *)this + 11);
    if ( v68 )
    {
      LODWORD(lpFileSystemFlags) = v88;
      LODWORD(lpMaximumComponentLength) = 2330;
      goto LABEL_153;
    }
    goto LABEL_118;
  }
  v38 = CMiscHelpersT<CEmptyType>::ParseFileName(Src, 0);
  v11 = v38;
  if ( v38 < 0 )
  {
    v15 = *((_QWORD *)this + 11);
    if ( !v15 )
      goto LABEL_209;
    LODWORD(lpFileSystemFlags) = v38;
    LODWORD(lpMaximumComponentLength) = 2224;
    goto LABEL_206;
  }
  v39 = v106;
  v40 = CMiscHelpersT<CEmptyType>::CombinePath(v106, (__int64)&dword_180084C74, 0);
  v11 = v40;
  if ( v40 < 0 )
  {
    v15 = *((_QWORD *)this + 11);
    if ( !v15 )
      goto LABEL_209;
    LODWORD(lpFileSystemFlags) = v40;
    LODWORD(lpMaximumComponentLength) = 2228;
    goto LABEL_206;
  }
  v41 = lpRootPathName;
  VolumeInformationW = GetVolumeInformationW(lpRootPathName, 0, 0, 0, 0, 0, 0, 0);
  v43 = *((_QWORD *)this + 11);
  if ( v43 )
  {
    v44 = L"Yes";
    if ( !VolumeInformationW )
      v44 = L"No";
    CDlpLogT<CEmptyType>::DlpLogFormat(v43, 2u, (__int64)L"LayoutUsb: OEM Folder: [%s], Volume Root: [%s]", v41, v44);
  }
  v45 = CDlpHelpersT<CEmptyType>::CombinePath(v39, (__int64)L"*", (__int64)&v108);
  v11 = v45;
  if ( v45 < 0 )
  {
    v15 = *((_QWORD *)this + 11);
    if ( !v15 )
      goto LABEL_209;
    LODWORD(lpFileSystemFlags) = v45;
    LODWORD(lpMaximumComponentLength) = 2234;
    goto LABEL_206;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (__int64)FindFirstFileW(v108, &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v110 = FirstFileW;
    do
    {
      if ( CompareStringW(0x409u, 1u, FindFileData.cFileName, -1, L".", -1) != 2
        && CompareStringW(0x409u, 1u, FindFileData.cFileName, -1, L"..", -1) != 2 )
      {
        if ( v9 )
        {
          v46 = GetProcessHeap();
          HeapFree(v46, 0, (LPVOID)(v9 - 2));
          v39 = v106;
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          lpFileName = 0;
        }
        v47 = CDlpHelpersT<CEmptyType>::CombinePath(v39, (__int64)FindFileData.cFileName, (__int64)&lpFileName);
        v11 = v47;
        if ( v47 < 0 )
        {
          v17 = *((_QWORD *)this + 11);
          if ( !v17 )
            goto LABEL_17;
          LODWORD(lpFileSystemFlags) = v47;
          LODWORD(lpMaximumComponentLength) = 2253;
          goto LABEL_14;
        }
        if ( v10 )
        {
          v48 = GetProcessHeap();
          HeapFree(v48, 0, v10 - 2);
          v39 = v106;
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v103 = 0;
        }
        v49 = CDlpHelpersT<CEmptyType>::CombinePath((__int64)v107, (__int64)FindFileData.cFileName, (__int64)&v103);
        v11 = v49;
        if ( v49 < 0 )
        {
          v55 = *((_QWORD *)this + 11);
          if ( v55 )
          {
            LODWORD(lpFileSystemFlags) = v49;
            LODWORD(lpMaximumComponentLength) = 2258;
            v56 = CDlpLogT<CEmptyType>::DlpLogFormat(
                    v55,
                    4u,
                    (__int64)L"%s(%d): Result = 0x%X",
                    L"CDlpActionLayoutUsb::PopulateOemPaths",
                    lpMaximumComponentLength,
                    lpFileSystemFlags);
            v57 = (unsigned int)v56;
            if ( v56 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v56);
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v57);
          }
          v9 = lpFileName;
          goto LABEL_118;
        }
        v10 = v103;
        v9 = lpFileName;
        OemFilePath = CDlpActionLayoutUsb::FindOemFilePath(this, lpFileName, v103, &v105);
        v11 = OemFilePath;
        if ( OemFilePath < 0 )
        {
          v15 = *((_QWORD *)this + 11);
          if ( !v15 )
            goto LABEL_209;
          LODWORD(lpFileSystemFlags) = OemFilePath;
          LODWORD(lpMaximumComponentLength) = 2262;
          goto LABEL_206;
        }
        if ( v105 )
        {
          v53 = *((_QWORD *)this + 11);
          if ( v53 )
            CDlpLogT<CEmptyType>::DlpLogFormat(v53, 2u, (__int64)L"LayoutUsb: Skipping duplicate file path: [%s]", v9);
        }
        else
        {
          v51 = CDlpActionLayoutUsb::PopulateOemPath(this, v9, v10);
          v11 = v51;
          if ( v51 == -2147024891 )
          {
            if ( !VolumeInformationW )
              goto LABEL_103;
            v52 = *((_QWORD *)this + 11);
            if ( v52 )
              CDlpLogT<CEmptyType>::DlpLogFormat(v52, 3u, (__int64)L"LayoutUsb: Skipping OEM Path: [%s]", v39);
            v11 = 0;
          }
          else if ( v51 < 0 )
          {
LABEL_103:
            v15 = *((_QWORD *)this + 11);
            if ( !v15 )
              goto LABEL_209;
            LODWORD(lpFileSystemFlags) = v51;
            LODWORD(lpMaximumComponentLength) = 2274;
            goto LABEL_206;
          }
        }
      }
    }
    while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
    if ( GetLastError() == 18 )
      goto LABEL_133;
    v54 = GetLastError();
    v11 = v54;
    if ( v54 )
    {
      if ( v54 > 0 )
        v11 = (unsigned __int16)v54 | 0x80070000;
    }
    else
    {
      v11 = -2147467259;
    }
    if ( !*((_QWORD *)this + 11) )
      goto LABEL_209;
    v14 = 0;
    if ( v11 >= 0 )
      goto LABEL_208;
    LODWORD(lpFileSystemFlags) = v11;
    LODWORD(lpMaximumComponentLength) = 2287;
    goto LABEL_10;
  }
  FirstFileW = -1;
  v110 = -1;
  v58 = GetLastError();
  v11 = v58;
  if ( v58 )
  {
    if ( v58 > 0 )
      v11 = (unsigned __int16)v58 | 0x80070000;
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
LABEL_208:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v14);
  }
LABEL_209:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose((HANDLE)FirstFileW);
  if ( v108 )
  {
    v91 = (WCHAR *)(v108 - 2);
    v92 = GetProcessHeap();
    HeapFree(v92, 0, v91);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( lpRootPathName )
  {
    v93 = (WCHAR *)(lpRootPathName - 2);
    v94 = GetProcessHeap();
    HeapFree(v94, 0, v93);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v106 )
  {
    v95 = (void *)(v106 - 4);
    v96 = GetProcessHeap();
    HeapFree(v96, 0, v95);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v10 )
  {
    v97 = GetProcessHeap();
    HeapFree(v97, 0, v10 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v9 )
  {
    v98 = GetProcessHeap();
    HeapFree(v98, 0, (LPVOID)(v9 - 2));
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
