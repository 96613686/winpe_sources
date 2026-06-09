# Pca::MergeSdb::Utils::SdbFileData::GetTimeAndTargetFromSdb(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,_GUID &,_GUID &,ulong &,Pca::MergeSdb::Utils::TimeValue &,ulong &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,std::list<Pca::MergeSdb::PreviousMergeDbInfo,std::allocator<Pca::MergeSdb::PreviousMergeDbInfo>> &,int &,ushort const *,ushort const *)

- ea: `0x14002b138`
- end: `0x14002be3a`
- name: `?GetTimeAndTargetFromSdb@SdbFileData@Utils@MergeSdb@Pca@@QEAAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAU_GUID@@1AEAKAEAVTimeValue@234@20200AEAV?$list@VPreviousMergeDbInfo@MergeSdb@Pca@@V?$allocator@VPreviousMergeDbInfo@MergeSdb@Pca@@@std@@@std@@AEAHPEBG6@Z`
- size: `3330`
- prototype: `__int64 __fastcall(__int64, void **, _OWORD *, _OWORD *, _DWORD *, _QWORD *, int *, void **, _DWORD *, void **, void **, void **, int *, PCWSTR FileName, void *)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14002c36c`

## callees

- `0x1400018b0`
- `0x14000d8ac`
- `0x14001008c`
- `0x140010d44`
- `0x140013898`
- `0x140013cb8`
- `0x140013d54`
- `0x140013dc0`
- `0x140014380`
- `0x1400143d8`
- `0x14001443c`
- `0x140014574`
- `0x140016070`
- `0x140016148`
- `0x140016198`
- `0x14001a24c`
- `0x14001a834`
- `0x140020d74`
- `0x140020f9c`
- `0x140024564`
- `0x14002469c`
- `0x1400248cc`
- `0x140029c80`
- `0x140029d98`
- `0x14002b138`
- `0x14002e3e2`
- `0x14002e3ee`
- `0x14002e420`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002b1fc`
- `KERNEL32!GetLastError` at `0x14002b25d`
- `KERNEL32!GetLastError` at `0x14002b299`
- `KERNEL32!GetLastError` at `0x14002b2c9`
- `KERNEL32!GetLastError` at `0x14002bb87`
- `KERNEL32!GetLastError` at `0x14002b1fc`
- `KERNEL32!GetLastError` at `0x14002b25d`
- `KERNEL32!GetLastError` at `0x14002b299`
- `KERNEL32!GetLastError` at `0x14002b2c9`
- `KERNEL32!GetLastError` at `0x14002bb87`
- `KERNEL32!GetProcessHeap` at `0x14002b204`
- `KERNEL32!GetProcessHeap` at `0x14002b265`
- `KERNEL32!GetProcessHeap` at `0x14002b2a1`
- `KERNEL32!GetProcessHeap` at `0x14002b2d1`
- `KERNEL32!GetProcessHeap` at `0x14002b5ed`
- `KERNEL32!GetProcessHeap` at `0x14002b641`
- `KERNEL32!GetProcessHeap` at `0x14002b684`
- `KERNEL32!GetProcessHeap` at `0x14002b86e`
- `KERNEL32!GetProcessHeap` at `0x14002b88b`
- `KERNEL32!GetProcessHeap` at `0x14002b934`
- `KERNEL32!GetProcessHeap` at `0x14002b94e`
- `KERNEL32!GetProcessHeap` at `0x14002b9ae`
- `KERNEL32!GetProcessHeap` at `0x14002b9c8`
- `KERNEL32!GetProcessHeap` at `0x14002bc41`
- `KERNEL32!GetProcessHeap` at `0x14002bc5b`
- `KERNEL32!GetProcessHeap` at `0x14002bc86`
- `KERNEL32!GetProcessHeap` at `0x14002bca0`
- `KERNEL32!GetProcessHeap` at `0x14002bd74`
- `KERNEL32!GetProcessHeap` at `0x14002bd93`
- `KERNEL32!GetProcessHeap` at `0x14002bdc8`
- `KERNEL32!GetProcessHeap` at `0x14002bde7`
- `KERNEL32!GetProcessHeap` at `0x14002b204`
- `KERNEL32!GetProcessHeap` at `0x14002b265`
- `KERNEL32!GetProcessHeap` at `0x14002b2a1`
- `KERNEL32!GetProcessHeap` at `0x14002b2d1`
- `KERNEL32!GetProcessHeap` at `0x14002b5ed`
- `KERNEL32!GetProcessHeap` at `0x14002b641`
- `KERNEL32!GetProcessHeap` at `0x14002b684`
- `KERNEL32!GetProcessHeap` at `0x14002b86e`
- `KERNEL32!GetProcessHeap` at `0x14002b88b`
- `KERNEL32!GetProcessHeap` at `0x14002b934`
- `KERNEL32!GetProcessHeap` at `0x14002b94e`
- `KERNEL32!GetProcessHeap` at `0x14002b9ae`
- `KERNEL32!GetProcessHeap` at `0x14002b9c8`
- `KERNEL32!GetProcessHeap` at `0x14002bc41`
- `KERNEL32!GetProcessHeap` at `0x14002bc5b`
- `KERNEL32!GetProcessHeap` at `0x14002bc86`
- `KERNEL32!GetProcessHeap` at `0x14002bca0`
- `KERNEL32!GetProcessHeap` at `0x14002bd74`
- `KERNEL32!GetProcessHeap` at `0x14002bd93`
- `KERNEL32!GetProcessHeap` at `0x14002bdc8`
- `KERNEL32!GetProcessHeap` at `0x14002bde7`
- `KERNEL32!SetLastError` at `0x14002b21a`
- `KERNEL32!SetLastError` at `0x14002b27b`
- `KERNEL32!SetLastError` at `0x14002b2b7`
- `KERNEL32!SetLastError` at `0x14002b2e7`
- `KERNEL32!SetLastError` at `0x14002bb99`
- `KERNEL32!SetLastError` at `0x14002b21a`
- `KERNEL32!SetLastError` at `0x14002b27b`
- `KERNEL32!SetLastError` at `0x14002b2b7`
- `KERNEL32!SetLastError` at `0x14002b2e7`
- `KERNEL32!SetLastError` at `0x14002bb99`
- `KERNEL32!HeapFree` at `0x14002b212`
- `KERNEL32!HeapFree` at `0x14002b273`
- `KERNEL32!HeapFree` at `0x14002b2af`
- `KERNEL32!HeapFree` at `0x14002b2df`
- `KERNEL32!HeapFree` at `0x14002b5fb`
- `KERNEL32!HeapFree` at `0x14002b64f`
- `KERNEL32!HeapFree` at `0x14002b692`
- `KERNEL32!HeapFree` at `0x14002b87c`
- `KERNEL32!HeapFree` at `0x14002b899`
- `KERNEL32!HeapFree` at `0x14002b942`
- `KERNEL32!HeapFree` at `0x14002b95c`
- `KERNEL32!HeapFree` at `0x14002b9bc`
- `KERNEL32!HeapFree` at `0x14002b9d6`
- `KERNEL32!HeapFree` at `0x14002bc4f`
- `KERNEL32!HeapFree` at `0x14002bc69`
- `KERNEL32!HeapFree` at `0x14002bc94`
- `KERNEL32!HeapFree` at `0x14002bcae`
- `KERNEL32!HeapFree` at `0x14002bd82`
- `KERNEL32!HeapFree` at `0x14002bda1`
- `KERNEL32!HeapFree` at `0x14002bdd6`
- `KERNEL32!HeapFree` at `0x14002bdf5`
- `KERNEL32!HeapFree` at `0x14002b212`
- `KERNEL32!HeapFree` at `0x14002b273`
- `KERNEL32!HeapFree` at `0x14002b2af`
- `KERNEL32!HeapFree` at `0x14002b2df`
- `KERNEL32!HeapFree` at `0x14002b5fb`
- `KERNEL32!HeapFree` at `0x14002b64f`
- `KERNEL32!HeapFree` at `0x14002b692`
- `KERNEL32!HeapFree` at `0x14002b87c`
- `KERNEL32!HeapFree` at `0x14002b899`
- `KERNEL32!HeapFree` at `0x14002b942`
- `KERNEL32!HeapFree` at `0x14002b95c`
- `KERNEL32!HeapFree` at `0x14002b9bc`
- `KERNEL32!HeapFree` at `0x14002b9d6`
- `KERNEL32!HeapFree` at `0x14002bc4f`
- `KERNEL32!HeapFree` at `0x14002bc69`
- `KERNEL32!HeapFree` at `0x14002bc94`
- `KERNEL32!HeapFree` at `0x14002bcae`
- `KERNEL32!HeapFree` at `0x14002bd82`
- `KERNEL32!HeapFree` at `0x14002bda1`
- `KERNEL32!HeapFree` at `0x14002bdd6`
- `KERNEL32!HeapFree` at `0x14002bdf5`
- `msvcrt!??3@YAXPEAX@Z` at `0x14002b92d`
- `msvcrt!??3@YAXPEAX@Z` at `0x14002b9a7`
- `msvcrt!??3@YAXPEAX@Z` at `0x14002bc7f`
- `msvcrt!??3@YAXPEAX@Z` at `0x14002bdb7`
- `msvcrt!??3@YAXPEAX@Z` at `0x14002b92d`
- `msvcrt!??3@YAXPEAX@Z` at `0x14002b9a7`
- `msvcrt!??3@YAXPEAX@Z` at `0x14002bc7f`
- `msvcrt!??3@YAXPEAX@Z` at `0x14002bdb7`
- `ntdll!RtlDoesFileExists_U` at `0x14002b31d`
- `ntdll!RtlDoesFileExists_U` at `0x14002b31d`
- `ntdll!RtlNtStatusToDosError` at `0x14002b712`
- `ntdll!RtlNtStatusToDosError` at `0x14002b75f`
- `ntdll!RtlNtStatusToDosError` at `0x14002b792`
- `ntdll!RtlNtStatusToDosError` at `0x14002b712`
- `ntdll!RtlNtStatusToDosError` at `0x14002b75f`
- `ntdll!RtlNtStatusToDosError` at `0x14002b792`

## string_xrefs

- `0x14002b4c8`: `Failed to read TAG_TIME or invalid time in sdb`
- `0x14002b556`: `Failed to read compiler version string from sdb`
- `0x14002b61f`: `Failed to read database name string from sdb`
- `0x14002bc18`: `Failed to compute the registered sdb file name (%d)`
- `0x14002bbc8`: `Failed to compute the sdb merge target (%d)`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::SdbFileData::GetTimeAndTargetFromSdb(
        __int64 a1,
        void **a2,
        _OWORD *a3,
        _OWORD *a4,
        _DWORD *a5,
        _QWORD *a6,
        int *a7,
        void **a8,
        _DWORD *a9,
        void **a10,
        void **a11,
        void **a12,
        int *a13,
        PCWSTR FileName,
        void *a15)
{
  void **v15; // rax
  void *v16; // rsi
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  void *v19; // rsi
  DWORD v20; // ebx
  HANDLE v21; // rax
  void *v22; // rsi
  DWORD v23; // ebx
  HANDLE v24; // rax
  void *v25; // rsi
  DWORD v26; // ebx
  HANDLE v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rbx
  unsigned int v31; // r15d
  unsigned int FirstTag; // eax
  unsigned int v33; // r15d
  unsigned int FirstTagBefore; // eax
  __int128 v36; // xmm6
  unsigned int v37; // eax
  unsigned int v38; // eax
  __int128 v39; // xmm0
  unsigned int v40; // eax
  unsigned int v41; // eax
  unsigned int v42; // eax
  void *v43; // rdi
  LPVOID v44; // rsi
  __int64 StringTagPtr; // rax
  unsigned int v46; // eax
  HANDLE v47; // rax
  __int64 v48; // rax
  HANDLE v49; // rax
  __int64 v50; // rcx
  void *v51; // r14
  HANDLE v52; // rax
  char *v53; // r12
  unsigned int v54; // eax
  unsigned int i; // eax
  NTSTATUS v56; // esi
  ULONG v57; // eax
  NTSTATUS v58; // esi
  ULONG v59; // eax
  ULONG v60; // r12d
  __int64 v61; // rsi
  NTSTATUS v62; // esi
  ULONG v63; // eax
  __int64 v64; // rcx
  __int64 v65; // rax
  void *v66; // rsi
  HANDLE v67; // rax
  void *v68; // rsi
  HANDLE v69; // rax
  unsigned int v70; // r13d
  __int64 v71; // rdx
  unsigned int v72; // eax
  __int64 v73; // r8
  HANDLE v74; // rax
  HANDLE v75; // rax
  HANDLE v76; // rax
  HANDLE v77; // rax
  int v78; // r12d
  unsigned int v79; // esi
  unsigned int v80; // r13d
  unsigned int v81; // eax
  unsigned int v82; // r12d
  const wchar_t *v83; // r13
  int v84; // r12d
  unsigned int v85; // eax
  const wchar_t *v86; // rax
  __int16 TagFromTagID; // r13
  unsigned int v88; // r12d
  __int16 v89; // ax
  unsigned int NextChild; // eax
  DWORD v91; // esi
  unsigned int v92; // eax
  void *v93; // rbx
  unsigned int v94; // eax
  void *v95; // rsi
  HANDLE v96; // rax
  HANDLE v97; // rax
  HANDLE v98; // rax
  HANDLE v99; // rax
  void **v100; // rcx
  void *v101; // rax
  char *v102; // rax
  void *v103; // rbx
  HANDLE v104; // rax
  void *v105; // rbx
  HANDLE v106; // rax
  void *v107; // rbx
  HANDLE v108; // rax
  void *v109; // rbx
  HANDLE v110; // rax
  void *v111; // [rsp+38h] [rbp-D0h] BYREF
  char *v112; // [rsp+40h] [rbp-C8h]
  __int64 v113; // [rsp+48h] [rbp-C0h]
  LPVOID v114; // [rsp+50h] [rbp-B8h] BYREF
  LPVOID v115; // [rsp+58h] [rbp-B0h] BYREF
  int DWORDTag; // [rsp+60h] [rbp-A8h]
  int v117; // [rsp+64h] [rbp-A4h]
  LPVOID v118; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v119[3]; // [rsp+70h] [rbp-98h] BYREF
  void **v120; // [rsp+88h] [rbp-80h]
  _OWORD *v121; // [rsp+90h] [rbp-78h]
  _OWORD *v122; // [rsp+98h] [rbp-70h]
  _DWORD *v123; // [rsp+A0h] [rbp-68h]
  _QWORD *v124; // [rsp+A8h] [rbp-60h]
  int *v125; // [rsp+B0h] [rbp-58h]
  _DWORD *v126; // [rsp+B8h] [rbp-50h]
  int *v127; // [rsp+C0h] [rbp-48h]
  _QWORD v128[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v129; // [rsp+D8h] [rbp-30h]
  void **v130; // [rsp+E0h] [rbp-28h]
  void **v131; // [rsp+E8h] [rbp-20h]
  void **v132; // [rsp+F0h] [rbp-18h]
  void **v133; // [rsp+F8h] [rbp-10h]
  _QWORD v134[3]; // [rsp+108h] [rbp+0h] BYREF
  __int128 v135; // [rsp+120h] [rbp+18h]
  __int128 v136; // [rsp+130h] [rbp+28h]
  int v137; // [rsp+140h] [rbp+38h]
  __int64 v138; // [rsp+148h] [rbp+40h] BYREF
  int v139; // [rsp+150h] [rbp+48h]
  int v140; // [rsp+154h] [rbp+4Ch]
  LPVOID v141[3]; // [rsp+158h] [rbp+50h] BYREF
  __int128 v142; // [rsp+170h] [rbp+68h]
  __int128 v143; // [rsp+180h] [rbp+78h]
  int v144; // [rsp+190h] [rbp+88h]
  LPVOID lpMem; // [rsp+198h] [rbp+90h] BYREF
  int v146; // [rsp+1A0h] [rbp+98h]
  bool v147; // [rsp+1A4h] [rbp+9Ch]

  v122 = a4;
  v121 = a3;
  v15 = a2;
  v120 = a2;
  v132 = a11;
  v131 = a10;
  v130 = a8;
  v124 = a6;
  v123 = a5;
  v125 = a7;
  v126 = a9;
  v133 = a12;
  v127 = a13;
  v115 = a15;
  v16 = *a2;
  if ( *a2 )
  {
    LastError = GetLastError();
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v16);
    SetLastError(LastError);
    v15 = v120;
  }
  *v15 = 0;
  *v121 = 0;
  *v122 = 0;
  *v123 = 0;
  *v124 = 0;
  *v125 = 0;
  v19 = *a8;
  if ( *a8 )
  {
    v20 = GetLastError();
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v19);
    SetLastError(v20);
  }
  *a8 = 0;
  *v126 = 0;
  v22 = *a10;
  if ( *a10 )
  {
    v23 = GetLastError();
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v22);
    SetLastError(v23);
  }
  *a10 = 0;
  v25 = *a11;
  if ( *a11 )
  {
    v26 = GetLastError();
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v25);
    SetLastError(v26);
  }
  *a11 = 0;
  std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(a12);
  *v127 = 0;
  v29 = SdbOpenDatabaseEx(FileName, v28, 16);
  v30 = v29;
  v129 = v29;
  if ( !v29 )
  {
    if ( RtlDoesFileExists_U(FileName) )
    {
      return 1392;
    }
    else
    {
      v31 = 2;
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::SdbFileData::GetTimeAndTargetFromSdb",
        2082,
        "Failed to find sdb file '%S' (%d)",
        FileName,
        2);
    }
    return v31;
  }
  FirstTag = SdbFindFirstTag(v29, 0, 28673);
  v33 = FirstTag;
  if ( !FirstTag )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::SdbFileData::GetTimeAndTargetFromSdb",
      2091,
      "Failed to find TAG_DATABASE in sdb");
    SdbCloseDatabase(v30);
    return 4313;
  }
  FirstTagBefore = SdbFindFirstTagBefore(v30, FirstTag, 36871);
  if ( !FirstTagBefore )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::SdbFileData::GetTimeAndTargetFromSdb",
      2097,
      "Failed to find TAG_DATABASE_ID in sdb");
    SdbCloseDatabase(v30);
    return 4313;
  }
  *(_OWORD *)&v119[1] = 0;
  v36 = *(_OWORD *)SdbReadGUIDTag(v128, v30, FirstTagBefore, &v119[1]);
  v37 = SdbFindFirstTagBefore(v30, v33, 16478);
  if ( v37 )
    DWORDTag = SdbReadDWORDTag(v30, v37, 0);
  else
    DWORDTag = 0;
  v38 = SdbFindFirstTagBefore(v30, v33, 36878);
  if ( v38 )
  {
    *(_OWORD *)&v119[1] = 0;
    v39 = *(_OWORD *)SdbReadGUIDTag(v128, v30, v38, &v119[1]);
  }
  else
  {
    v39 = v36;
  }
  *(_OWORD *)&v119[1] = v39;
  v40 = SdbFindFirstTagBefore(v30, v33, 20481);
  if ( !v40 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::SdbFileData::GetTimeAndTargetFromSdb",
      2119,
      "Failed to find TAG_TIME under TAG_DATABASE in sdb");
    SdbCloseDatabase(v30);
    return 4313;
  }
  v128[0] = SdbReadQWORDTag(v30, v40, 0);
  if ( !v128[0] )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::SdbFileData::GetTimeAndTargetFromSdb",
      2125,
      "Failed to read TAG_TIME or invalid time in sdb");
    SdbCloseDatabase(v30);
    return 4313;
  }
  v41 = SdbFindFirstTagBefore(v30, v33, 16417);
  if ( v41 )
    v117 = SdbReadDWORDTag(v30, v41, 0);
  else
    v117 = 255;
  v42 = SdbFindFirstTagBefore(v30, v33, 24610);
  v43 = 0;
  v118 = 0;
  v44 = 0;
  if ( v42 )
  {
    StringTagPtr = SdbGetStringTagPtr(v30, v42);
    if ( !StringTagPtr )
    {
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::SdbFileData::GetTimeAndTargetFromSdb",
        2149,
        "Failed to read compiler version string from sdb");
      SdbCloseDatabase(v30);
      return 4313;
    }
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v118,
      StringTagPtr,
      -1);
    v43 = v118;
    if ( !v118 )
    {
LABEL_35:
      SdbCloseDatabase(v30);
      return 14;
    }
    v44 = v118;
  }
  v46 = SdbFindFirstTagBefore(v30, v33, 24577);
  if ( !v46 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::SdbFileData::GetTimeAndTargetFromSdb",
      2161,
      "Failed to find TAG_NAME in sdb");
    if ( v44 )
    {
      v47 = GetProcessHeap();
      HeapFree(v47, 0, v43);
    }
LABEL_40:
    SdbCloseDatabase(v30);
    return 4313;
  }
  v48 = SdbGetStringTagPtr(v30, v46);
  if ( !v48 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::SdbFileData::GetTimeAndTargetFromSdb",
      2167,
      "Failed to read database name string from sdb");
    if ( v44 )
    {
      v49 = GetProcessHeap();
      HeapFree(v49, 0, v43);
    }
    goto LABEL_40;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    v119,
    v48,
    -1);
  v51 = (void *)v119[0];
  if ( !v119[0] )
  {
    if ( v44 )
    {
      v52 = GetProcessHeap();
      HeapFree(v52, 0, v43);
    }
    goto LABEL_35;
  }
  v53 = 0;
  v112 = 0;
  v111 = (void *)std::_List_alloc<0,std::_List_base_types<Pca::MergeSdb::PreviousMergeDbInfo>>::_Buynode0(v50, 0, 0);
  v54 = SdbFindFirstTagBefore(v30, v33, 28748);
  LODWORD(v113) = v54;
  if ( v54 )
  {
    for ( i = SdbFindFirstTag(v30, v54, 28749); ; i = SdbFindNextTag(v30, (unsigned int)v113, v70) )
    {
      v70 = i;
      if ( !i )
        goto LABEL_66;
      memset_0(v134, 0, 0x50u);
      v56 = SdbMergeCollectPreviousMergeInfoFromDb(v30, v70, v134);
      v57 = RtlNtStatusToDosError(v56);
      if ( v56 >= 0 )
      {
        if ( !v134[0] )
        {
          v58 = AslStringDuplicate(v134, &Format);
          v59 = RtlNtStatusToDosError(v58);
          v60 = v59;
          if ( v58 < 0 )
          {
            AslLogCallPrintf(
              1,
              "Pca::MergeSdb::Utils::SdbFileData::GetTimeAndTargetFromSdb",
              2189,
              "Failed to duplicate string (%d)",
              v59);
            std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(&v111);
            operator delete(v111);
            v74 = GetProcessHeap();
            HeapFree(v74, 0, v51);
            if ( v43 )
            {
              v75 = GetProcessHeap();
              HeapFree(v75, 0, v43);
            }
            goto LABEL_73;
          }
          v53 = v112;
        }
        v61 = v138;
        if ( !v138 )
        {
          v62 = AslStringDuplicate(&v138, &Format);
          v63 = RtlNtStatusToDosError(v62);
          v60 = v63;
          if ( v62 < 0 )
          {
            AslLogCallPrintf(
              1,
              "Pca::MergeSdb::Utils::SdbFileData::GetTimeAndTargetFromSdb",
              2195,
              "Failed to duplicate string (%d)",
              v63);
            std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(&v111);
            operator delete(v111);
            v76 = GetProcessHeap();
            HeapFree(v76, 0, v51);
            if ( v43 )
            {
              v77 = GetProcessHeap();
              HeapFree(v77, 0, v43);
            }
LABEL_73:
            SdbCloseDatabase(v30);
            return v60;
          }
          v61 = v138;
          v53 = v112;
        }
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          v141,
          v134[0],
          -1);
        v141[1] = (LPVOID)v134[1];
        v141[2] = (LPVOID)v134[2];
        v142 = v135;
        v143 = v136;
        v144 = v137;
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &lpMem,
          v61,
          -1);
        v146 = v139;
        v147 = v140 != 0;
        v65 = std::_List_buy<Pca::MergeSdb::PreviousMergeDbInfo>::_Buynode<Pca::MergeSdb::PreviousMergeDbInfo>(
                v64,
                v111,
                *((_QWORD *)v111 + 1),
                v141);
        if ( v53 == (char *)0x2AAAAAAAAAAAAA9LL )
          std::_Xlength_error("list<T> too long");
        v112 = ++v53;
        *((_QWORD *)v111 + 1) = v65;
        **(_QWORD **)(v65 + 8) = v65;
        v66 = lpMem;
        if ( lpMem )
        {
          v67 = GetProcessHeap();
          HeapFree(v67, 0, v66);
        }
        v68 = v141[0];
        if ( v141[0] )
        {
          v69 = GetProcessHeap();
          HeapFree(v69, 0, v68);
        }
      }
      else
      {
        AslLogCallPrintf(
          1,
          "Pca::MergeSdb::Utils::SdbFileData::GetTimeAndTargetFromSdb",
          2185,
          "Failed to get previous merge info from sdb (%d)",
          v57);
      }
      SdbMergeFreePdbInformation(v134);
    }
  }
  AslLogCallPrintf(
    3,
    "Pca::MergeSdb::Utils::SdbFileData::GetTimeAndTargetFromSdb",
    2206,
    "SDB file contains no previous merge information.");
LABEL_66:
  v71 = *(_QWORD *)(v30 + 8);
  if ( v71 && (v72 = *(_DWORD *)(v30 + 20)) != 0 )
  {
    v73 = 4096;
    if ( v72 < 0x1000 )
      v73 = v72;
    LODWORD(v113) = AslComputeCrc32(0, v71, v73);
  }
  else
  {
    LODWORD(v113) = 0;
  }
  v78 = 0;
  LODWORD(v114) = 0;
  v79 = SdbFindFirstTagBefore(v30, v33, 28687);
  if ( v79 )
  {
    while ( 1 )
    {
      v80 = SdbFindFirstTag(v30, v79, 24577);
      v81 = SdbFindFirstTag(v30, v79, 16408);
      v82 = v81;
      if ( v80 )
      {
        if ( v81 )
        {
          v83 = (const wchar_t *)SdbGetStringTagPtr(v30, v80);
          v84 = SdbReadDWORDTag(v30, v82, 0);
          if ( v83 )
          {
            if ( !wcscmp_0(v83, L"TagDatabaseWhenAllEntriesQualify") && v84 == 1 )
            {
              v85 = SdbFindFirstTag(v30, v79, 24606);
              if ( v85 )
              {
                v86 = (const wchar_t *)SdbGetStringTagPtr(v30, v85);
                if ( v86 )
                {
                  if ( !wcscmp_0(v86, L"TestMergeOnlyDontMergeAggressively") )
                  {
                    v78 = 1;
                    AslLogCallPrintf(
                      3,
                      "Pca::MergeSdb::Utils::SdbFileData::GetTimeAndTargetFromSdb",
                      2242,
                      "SDB file contains only test content.");
                    goto LABEL_100;
                  }
                }
              }
            }
          }
        }
      }
      TagFromTagID = SdbGetTagFromTagID(v30, v79);
      if ( !TagFromTagID )
        break;
      v88 = 0;
      do
      {
        NextChild = SdbGetNextChild(v30, v33, v79);
        v79 = NextChild;
        if ( !NextChild )
          break;
        v89 = SdbGetTagFromTagID(v30, NextChild);
        if ( v89 == TagFromTagID )
        {
          v88 = v79;
          break;
        }
      }
      while ( v89 != 28674 );
      v79 = v88;
      if ( !v88 )
        goto LABEL_99;
    }
    AslLogCallPrintf(1, "SdbFindNextTagBefore", 170, "Invalid tagid 0x%lx", v79);
LABEL_99:
    v78 = (int)v114;
  }
LABEL_100:
  v91 = GetLastError();
  SdbCloseDatabase(v30);
  SetLastError(v91);
  v129 = 0;
  v114 = 0;
  v92 = Pca::MergeSdb::Utils::SdbFileData::ComputeSdbMergeTarget(&v114, &v119[1], v115);
  v31 = v92;
  if ( v92 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::SdbFileData::GetTimeAndTargetFromSdb",
      2254,
      "Failed to compute the sdb merge target (%d)",
      v92);
    v93 = v114;
LABEL_105:
    if ( v93 )
    {
      v97 = GetProcessHeap();
      HeapFree(v97, 0, v93);
    }
    std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(&v111);
    operator delete(v111);
    v98 = GetProcessHeap();
    HeapFree(v98, 0, v51);
    if ( v43 )
    {
      v99 = GetProcessHeap();
      HeapFree(v99, 0, v43);
    }
    return v31;
  }
  v115 = 0;
  v93 = v114;
  v94 = Pca::MergeSdb::Utils::SdbFileData::ComputeRegisteredFileName(&v115, v114, v128);
  v31 = v94;
  if ( v94 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::SdbFileData::GetTimeAndTargetFromSdb",
      2263,
      "Failed to compute the registered sdb file name (%d)",
      v94);
    v95 = v115;
    if ( v115 )
    {
      v96 = GetProcessHeap();
      HeapFree(v96, 0, v95);
    }
    goto LABEL_105;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
    v120,
    &v114);
  *v121 = v36;
  *v122 = *(_OWORD *)&v119[1];
  *v123 = DWORDTag;
  *v124 = v128[0];
  *v125 = v117;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
    v130,
    &v118);
  *v126 = v113;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
    v131,
    &v115);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::swap(
    v132,
    v119);
  v100 = v133;
  if ( v133 != &v111 )
  {
    v101 = *v133;
    *v133 = v111;
    v111 = v101;
    v102 = (char *)v100[1];
    v100[1] = v112;
    v112 = v102;
  }
  *v127 = v78;
  v103 = v115;
  if ( v115 )
  {
    v104 = GetProcessHeap();
    HeapFree(v104, 0, v103);
  }
  v105 = v114;
  if ( v114 )
  {
    v106 = GetProcessHeap();
    HeapFree(v106, 0, v105);
  }
  std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(&v111);
  operator delete(v111);
  v107 = (void *)v119[0];
  if ( v119[0] )
  {
    v108 = GetProcessHeap();
    HeapFree(v108, 0, v107);
  }
  v109 = v118;
  if ( v118 )
  {
    v110 = GetProcessHeap();
    HeapFree(v110, 0, v109);
  }
  return 0;
}

```

## disassembly

```asm
0x14002b138  mov     rax, rsp
0x14002b13b  mov     [rax+8], rbx
0x14002b13f  push    rbp
0x14002b140  push    rsi
0x14002b141  push    rdi
0x14002b142  push    r12
0x14002b144  push    r13
0x14002b146  push    r14
0x14002b148  push    r15
0x14002b14a  lea     rbp, [rax-0F8h]
0x14002b151  sub     rsp, 1C0h
0x14002b158  movaps  xmmword ptr [rax-48h], xmm6
0x14002b15c  mov     rax, cs:__security_cookie
0x14002b163  xor     rax, rsp
0x14002b166  mov     [rbp+0F0h+var_50], rax
0x14002b16d  mov     [rbp+0F0h+var_160], r9
0x14002b171  mov     [rbp+0F0h+var_168], r8
0x14002b175  mov     rax, rdx
0x14002b178  mov     [rbp+0F0h+var_170], rdx
0x14002b17c  mov     r12, [rbp+0F0h+arg_50]
0x14002b183  mov     [rbp+0F0h+var_108], r12
0x14002b187  mov     r15, [rbp+0F0h+arg_48]
0x14002b18e  mov     [rbp+0F0h+var_110], r15
0x14002b192  mov     r13, [rbp+0F0h+arg_38]
0x14002b199  mov     [rbp+0F0h+var_118], r13
0x14002b19d  mov     rcx, [rbp+0F0h+arg_28]
0x14002b1a4  mov     [rbp+0F0h+var_150], rcx
0x14002b1a8  mov     rcx, [rbp+0F0h+arg_20]
0x14002b1af  mov     [rbp+0F0h+var_158], rcx
0x14002b1b3  mov     rcx, [rbp+0F0h+arg_30]
0x14002b1ba  mov     [rbp+0F0h+var_148], rcx
0x14002b1be  mov     rcx, [rbp+0F0h+arg_40]
0x14002b1c5  mov     [rbp+0F0h+var_140], rcx
0x14002b1c9  mov     r14, [rbp+0F0h+arg_58]
0x14002b1d0  mov     [rbp+0F0h+var_100], r14
0x14002b1d4  mov     rcx, [rbp+0F0h+arg_60]
0x14002b1db  mov     [rbp+0F0h+var_138], rcx
0x14002b1df  mov     rdi, [rbp+0F0h+FileName]
0x14002b1e6  mov     rcx, [rbp+0F0h+arg_70]
0x14002b1ed  mov     [rsp+1F0h+var_1A0], rcx
0x14002b1f2  mov     rsi, [rdx]
0x14002b1f5  xor     edx, edx
0x14002b1f7  test    rsi, rsi
0x14002b1fa  jz      short loc_14002B226
0x14002b1fc  call    cs:__imp_GetLastError
0x14002b202  mov     ebx, eax
0x14002b204  call    cs:__imp_GetProcessHeap
0x14002b20a  mov     rcx, rax; hHeap
0x14002b20d  mov     r8, rsi; lpMem
0x14002b210  xor     edx, edx; dwFlags
0x14002b212  call    cs:__imp_HeapFree
0x14002b218  mov     ecx, ebx; dwErrCode
0x14002b21a  call    cs:__imp_SetLastError
0x14002b220  mov     rax, [rbp+0F0h+var_170]
0x14002b224  xor     edx, edx
0x14002b226  mov     [rax], rdx
0x14002b229  xorps   xmm0, xmm0
0x14002b22c  mov     rax, [rbp+0F0h+var_168]
0x14002b230  movdqu  xmmword ptr [rax], xmm0
0x14002b234  xorps   xmm1, xmm1
0x14002b237  mov     rax, [rbp+0F0h+var_160]
0x14002b23b  movdqu  xmmword ptr [rax], xmm1
0x14002b23f  mov     rax, [rbp+0F0h+var_158]
0x14002b243  mov     [rax], edx
0x14002b245  xor     eax, eax
0x14002b247  mov     rcx, [rbp+0F0h+var_150]
0x14002b24b  mov     [rcx], rax
0x14002b24e  mov     rax, [rbp+0F0h+var_148]
0x14002b252  mov     [rax], edx
0x14002b254  mov     rsi, [r13+0]
0x14002b258  test    rsi, rsi
0x14002b25b  jz      short loc_14002B283
0x14002b25d  call    cs:__imp_GetLastError
0x14002b263  mov     ebx, eax
0x14002b265  call    cs:__imp_GetProcessHeap
0x14002b26b  mov     rcx, rax; hHeap
0x14002b26e  mov     r8, rsi; lpMem
0x14002b271  xor     edx, edx; dwFlags
0x14002b273  call    cs:__imp_HeapFree
0x14002b279  mov     ecx, ebx; dwErrCode
0x14002b27b  call    cs:__imp_SetLastError
0x14002b281  xor     edx, edx
0x14002b283  mov     [r13+0], rdx
0x14002b287  mov     rax, [rbp+0F0h+var_140]
0x14002b28b  xor     r13d, r13d
0x14002b28e  mov     [rax], r13d
0x14002b291  mov     rsi, [r15]
0x14002b294  test    rsi, rsi
0x14002b297  jz      short loc_14002B2BD
0x14002b299  call    cs:__imp_GetLastError
0x14002b29f  mov     ebx, eax
0x14002b2a1  call    cs:__imp_GetProcessHeap
0x14002b2a7  mov     rcx, rax; hHeap
0x14002b2aa  mov     r8, rsi; lpMem
0x14002b2ad  xor     edx, edx; dwFlags
0x14002b2af  call    cs:__imp_HeapFree
0x14002b2b5  mov     ecx, ebx; dwErrCode
0x14002b2b7  call    cs:__imp_SetLastError
0x14002b2bd  mov     [r15], r13
0x14002b2c0  mov     rsi, [r12]
0x14002b2c4  test    rsi, rsi
0x14002b2c7  jz      short loc_14002B2ED
0x14002b2c9  call    cs:__imp_GetLastError
0x14002b2cf  mov     ebx, eax
0x14002b2d1  call    cs:__imp_GetProcessHeap
0x14002b2d7  mov     rcx, rax; hHeap
0x14002b2da  mov     r8, rsi; lpMem
0x14002b2dd  xor     edx, edx; dwFlags
0x14002b2df  call    cs:__imp_HeapFree
0x14002b2e5  mov     ecx, ebx; dwErrCode
0x14002b2e7  call    cs:__imp_SetLastError
0x14002b2ed  mov     [r12], r13
0x14002b2f1  mov     rcx, r14
0x14002b2f4  call    ?clear@?$list@VPreviousMergeDbInfo@MergeSdb@Pca@@V?$allocator@VPreviousMergeDbInfo@MergeSdb@Pca@@@std@@@std@@QEAAXXZ; std::list<Pca::MergeSdb::PreviousMergeDbInfo>::clear(void)
0x14002b2f9  mov     rax, [rbp+0F0h+var_138]
0x14002b2fd  mov     [rax], r13d
0x14002b300  mov     r8d, 10h
0x14002b306  mov     rcx, rdi
0x14002b309  call    SdbOpenDatabaseEx
0x14002b30e  mov     rbx, rax
0x14002b311  mov     [rbp+0F0h+var_120], rax
0x14002b315  test    rax, rax
0x14002b318  jnz     short loc_14002B361
0x14002b31a  mov     rcx, rdi; FileName
0x14002b31d  call    cs:__imp_RtlDoesFileExists_U
0x14002b323  test    al, al
0x14002b325  jnz     short loc_14002B356
0x14002b327  lea     r15d, [rbx+2]
0x14002b32b  mov     dword ptr [rsp+1F0h+var_1C8], r15d
0x14002b330  mov     qword ptr [rsp+1F0h+var_1D0], rdi
0x14002b335  lea     r9, aFailedToFindSd; "Failed to find sdb file '%S' (%d)"
0x14002b33c  mov     r8d, 822h
0x14002b342  lea     rdx, aPcaMergesdbUti_21; "Pca::MergeSdb::Utils::SdbFileData::GetT"...
0x14002b349  lea     ecx, [rbx+1]
0x14002b34c  call    AslLogCallPrintf
0x14002b351  jmp     loc_14002BCB5
0x14002b356  mov     r15d, 570h
0x14002b35c  jmp     loc_14002BCB5
0x14002b361  xor     edx, edx
0x14002b363  mov     r8d, 7001h
0x14002b369  mov     rcx, rbx
0x14002b36c  call    SdbFindFirstTag
0x14002b371  mov     r15d, eax
0x14002b374  test    eax, eax
0x14002b376  jnz     short loc_14002B3A8
0x14002b378  lea     r9, aFailedToFindTa; "Failed to find TAG_DATABASE in sdb"
0x14002b37f  mov     r8d, 82Bh
0x14002b385  lea     rdx, aPcaMergesdbUti_21; "Pca::MergeSdb::Utils::SdbFileData::GetT"...
0x14002b38c  lea     ecx, [rax+1]
0x14002b38f  call    AslLogCallPrintf
0x14002b394  nop
0x14002b395  mov     rcx, rbx
0x14002b398  call    SdbCloseDatabase
0x14002b39d  nop
0x14002b39e  mov     eax, 10D9h
0x14002b3a3  jmp     loc_14002BDFE
0x14002b3a8  mov     r8d, 9007h
0x14002b3ae  mov     edx, r15d
0x14002b3b1  mov     rcx, rbx
0x14002b3b4  call    SdbFindFirstTagBefore
0x14002b3b9  test    eax, eax
0x14002b3bb  jnz     short loc_14002B3E5
0x14002b3bd  lea     r9, aFailedToFindTa_8; "Failed to find TAG_DATABASE_ID in sdb"
0x14002b3c4  mov     r8d, 831h
0x14002b3ca  lea     rdx, aPcaMergesdbUti_21; "Pca::MergeSdb::Utils::SdbFileData::GetT"...
0x14002b3d1  lea     ecx, [rax+1]
0x14002b3d4  call    AslLogCallPrintf
0x14002b3d9  nop
0x14002b3da  mov     rcx, rbx
0x14002b3dd  call    SdbCloseDatabase
0x14002b3e2  nop
0x14002b3e3  jmp     short loc_14002B39E
0x14002b3e5  xorps   xmm0, xmm0
0x14002b3e8  movdqa  xmmword ptr [rsp+1F0h+var_188+8], xmm0
0x14002b3ee  lea     r9, [rsp+1F0h+var_188+8]
0x14002b3f3  mov     r8d, eax
0x14002b3f6  mov     rdx, rbx
0x14002b3f9  lea     rcx, [rbp+0F0h+var_130]
0x14002b3fd  call    SdbReadGUIDTag
0x14002b402  movups  xmm6, xmmword ptr [rax]
0x14002b405  mov     r8d, 405Eh
0x14002b40b  mov     edx, r15d
0x14002b40e  mov     rcx, rbx
0x14002b411  call    SdbFindFirstTagBefore
0x14002b416  test    eax, eax
0x14002b418  jz      short loc_14002B42D
0x14002b41a  xor     r8d, r8d
0x14002b41d  mov     edx, eax
0x14002b41f  mov     rcx, rbx
0x14002b422  call    SdbReadDWORDTag
0x14002b427  mov     dword ptr [rsp+1F0h+var_198], eax
0x14002b42b  jmp     short loc_14002B432
0x14002b42d  mov     dword ptr [rsp+1F0h+var_198], r13d
0x14002b432  mov     r8d, 900Eh
0x14002b438  mov     edx, r15d
0x14002b43b  mov     rcx, rbx
0x14002b43e  call    SdbFindFirstTagBefore
0x14002b443  test    eax, eax
0x14002b445  jz      short loc_14002B469
0x14002b447  xorps   xmm0, xmm0
0x14002b44a  movdqa  xmmword ptr [rsp+1F0h+var_188+8], xmm0
0x14002b450  lea     r9, [rsp+1F0h+var_188+8]
0x14002b455  mov     r8d, eax
0x14002b458  mov     rdx, rbx
0x14002b45b  lea     rcx, [rbp+0F0h+var_130]
0x14002b45f  call    SdbReadGUIDTag
0x14002b464  movups  xmm0, xmmword ptr [rax]
0x14002b467  jmp     short loc_14002B46C
0x14002b469  movaps  xmm0, xmm6
0x14002b46c  movdqa  xmmword ptr [rsp+1F0h+var_188+8], xmm0
0x14002b472  mov     r8d, 5001h
0x14002b478  mov     edx, r15d
0x14002b47b  mov     rcx, rbx
0x14002b47e  call    SdbFindFirstTagBefore
0x14002b483  test    eax, eax
0x14002b485  jnz     short loc_14002B4B2
0x14002b487  lea     r9, aFailedToFindTa_7; "Failed to find TAG_TIME under TAG_DATAB"...
0x14002b48e  mov     r8d, 847h
0x14002b494  lea     rdx, aPcaMergesdbUti_21; "Pca::MergeSdb::Utils::SdbFileData::GetT"...
0x14002b49b  lea     ecx, [rax+1]
0x14002b49e  call    AslLogCallPrintf
0x14002b4a3  nop
0x14002b4a4  mov     rcx, rbx
0x14002b4a7  call    SdbCloseDatabase
0x14002b4ac  nop
0x14002b4ad  jmp     loc_14002B39E
0x14002b4b2  xor     r8d, r8d
0x14002b4b5  mov     edx, eax
0x14002b4b7  mov     rcx, rbx
0x14002b4ba  call    SdbReadQWORDTag
0x14002b4bf  mov     [rbp+0F0h+var_130], rax
0x14002b4c3  test    rax, rax
0x14002b4c6  jnz     short loc_14002B4F3
0x14002b4c8  lea     r9, aFailedToReadTa_1; "Failed to read TAG_TIME or invalid time"...
0x14002b4cf  mov     r8d, 84Dh
0x14002b4d5  lea     rdx, aPcaMergesdbUti_21; "Pca::MergeSdb::Utils::SdbFileData::GetT"...
0x14002b4dc  lea     ecx, [rax+1]
0x14002b4df  call    AslLogCallPrintf
0x14002b4e4  nop
0x14002b4e5  mov     rcx, rbx
0x14002b4e8  call    SdbCloseDatabase
0x14002b4ed  nop
0x14002b4ee  jmp     loc_14002B39E
0x14002b4f3  mov     r8d, 4021h
0x14002b4f9  mov     edx, r15d
0x14002b4fc  mov     rcx, rbx
0x14002b4ff  call    SdbFindFirstTagBefore
0x14002b504  test    eax, eax
0x14002b506  jz      short loc_14002B51B
0x14002b508  xor     r8d, r8d
0x14002b50b  mov     edx, eax
0x14002b50d  mov     rcx, rbx
0x14002b510  call    SdbReadDWORDTag
0x14002b515  mov     dword ptr [rsp+1F0h+var_198+4], eax
0x14002b519  jmp     short loc_14002B523
0x14002b51b  mov     dword ptr [rsp+1F0h+var_198+4], 0FFh
0x14002b523  mov     r8d, 6022h
0x14002b529  mov     edx, r15d
0x14002b52c  mov     rcx, rbx
0x14002b52f  call    SdbFindFirstTagBefore
0x14002b534  mov     rdi, r13
0x14002b537  mov     [rsp+1F0h+var_190], r13
0x14002b53c  mov     rsi, r13
0x14002b53f  or      r14, 0FFFFFFFFFFFFFFFFh
0x14002b543  test    eax, eax
0x14002b545  jz      short loc_14002B5B6
0x14002b547  mov     edx, eax
0x14002b549  mov     rcx, rbx
0x14002b54c  call    SdbGetStringTagPtr
0x14002b551  test    rax, rax
0x14002b554  jnz     short loc_14002B581
0x14002b556  lea     r9, aFailedToReadCo; "Failed to read compiler version string "...
0x14002b55d  mov     r8d, 865h
0x14002b563  lea     rdx, aPcaMergesdbUti_21; "Pca::MergeSdb::Utils::SdbFileData::GetT"...
0x14002b56a  lea     ecx, [rax+1]
0x14002b56d  call    AslLogCallPrintf
0x14002b572  nop
0x14002b573  mov     rcx, rbx
0x14002b576  call    SdbCloseDatabase
0x14002b57b  nop
0x14002b57c  jmp     loc_14002B39E
0x14002b581  mov     r8, r14
0x14002b584  mov     rdx, rax
0x14002b587  lea     rcx, [rsp+1F0h+var_190]
0x14002b58c  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x14002b591  mov     rdi, [rsp+1F0h+var_190]
0x14002b596  mov     [rsp+1F0h+var_190], rdi
0x14002b59b  test    rdi, rdi
0x14002b59e  jnz     short loc_14002B5B3
0x14002b5a0  mov     rcx, rbx
0x14002b5a3  call    SdbCloseDatabase
0x14002b5a8  nop
0x14002b5a9  mov     eax, 0Eh
0x14002b5ae  jmp     loc_14002BDFE
0x14002b5b3  mov     rsi, rdi
0x14002b5b6  mov     r8d, 6001h
0x14002b5bc  mov     edx, r15d
0x14002b5bf  mov     rcx, rbx
0x14002b5c2  call    SdbFindFirstTagBefore
0x14002b5c7  test    eax, eax
  ... truncated ...
```
