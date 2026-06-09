# BLBIMGI_BACKUP_FILE::InitializeForWrite(ushort const *,_GUID *,uchar,__int64,uchar,__int64,_RTL_BITMAP *,_RTL_BITMAP *,uchar,_BLBIMG_FS_TYPE_,void * *,ulong * *,ulong *,ulong * *,ulong *,ulong *)

- ea: `0x1400c7594`
- end: `0x1400c82ef`
- name: `?InitializeForWrite@BLBIMGI_BACKUP_FILE@@QEAA?AW4_BLBIMG_RESULT_CODE@@PEBGPEAU_GUID@@E_JE2PEAU_RTL_BITMAP@@3EW4_BLBIMG_FS_TYPE_@@PEAPEAXPEAPEAKPEAK677@Z`
- size: `3419`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400c1f5c`

## callees

- `0x1400063b4`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x14003c434`
- `0x14003c9cc`
- `0x14003cb70`
- `0x14008a8b0`
- `0x1400c3d08`
- `0x1400c5394`
- `0x1400c5ebc`
- `0x1400c64b0`
- `0x1400c7594`
- `0x1400ca348`
- `0x1400ccee4`
- `0x1400cda84`
- `0x1400cf258`
- `0x1400cfbcc`
- `0x1400cfc30`
- `0x1400d1178`
- `0x140134d20`

## import_xrefs

- `KERNEL32!SetFileValidData` at `0x1400c819c`
- `KERNEL32!SetFileValidData` at `0x1400c819c`
- `KERNEL32!LocalAlloc` at `0x1400c788b`
- `KERNEL32!LocalAlloc` at `0x1400c789e`
- `KERNEL32!LocalAlloc` at `0x1400c78ac`
- `KERNEL32!LocalAlloc` at `0x1400c79ae`
- `KERNEL32!LocalAlloc` at `0x1400c7a53`
- `KERNEL32!LocalAlloc` at `0x1400c7b33`
- `KERNEL32!LocalAlloc` at `0x1400c788b`
- `KERNEL32!LocalAlloc` at `0x1400c789e`
- `KERNEL32!LocalAlloc` at `0x1400c78ac`
- `KERNEL32!LocalAlloc` at `0x1400c79ae`
- `KERNEL32!LocalAlloc` at `0x1400c7a53`
- `KERNEL32!LocalAlloc` at `0x1400c7b33`
- `KERNEL32!LocalFree` at `0x1400c7cc1`
- `KERNEL32!LocalFree` at `0x1400c7d73`
- `KERNEL32!LocalFree` at `0x1400c7e31`
- `KERNEL32!LocalFree` at `0x1400c7fdf`
- `KERNEL32!LocalFree` at `0x1400c8213`
- `KERNEL32!LocalFree` at `0x1400c8228`
- `KERNEL32!LocalFree` at `0x1400c7cc1`
- `KERNEL32!LocalFree` at `0x1400c7d73`
- `KERNEL32!LocalFree` at `0x1400c7e31`
- `KERNEL32!LocalFree` at `0x1400c7fdf`
- `KERNEL32!LocalFree` at `0x1400c8213`
- `KERNEL32!LocalFree` at `0x1400c8228`
- `KERNEL32!CreateFileW` at `0x1400c7ba3`
- `KERNEL32!CreateFileW` at `0x1400c7ba3`
- `KERNEL32!CreateEventW` at `0x1400c79da`
- `KERNEL32!CreateEventW` at `0x1400c79da`
- `KERNEL32!GetLastError` at `0x1400c79ec`
- `KERNEL32!GetLastError` at `0x1400c7ac5`
- `KERNEL32!GetLastError` at `0x1400c7bb2`
- `KERNEL32!GetLastError` at `0x1400c8124`
- `KERNEL32!GetLastError` at `0x1400c81a6`
- `KERNEL32!GetLastError` at `0x1400c82ae`
- `KERNEL32!GetLastError` at `0x1400c79ec`
- `KERNEL32!GetLastError` at `0x1400c7ac5`
- `KERNEL32!GetLastError` at `0x1400c7bb2`
- `KERNEL32!GetLastError` at `0x1400c8124`
- `KERNEL32!GetLastError` at `0x1400c81a6`
- `KERNEL32!GetLastError` at `0x1400c82ae`
- `ntdll!RtlNtStatusToDosError` at `0x1400c7d7b`
- `ntdll!RtlNtStatusToDosError` at `0x1400c7de9`
- `ntdll!RtlNtStatusToDosError` at `0x1400c7d7b`
- `ntdll!RtlNtStatusToDosError` at `0x1400c7de9`
- `ntdll!NtCreateFile` at `0x1400c7d41`
- `ntdll!NtCreateFile` at `0x1400c7d41`
- `ntdll!RtlFreeHeap` at `0x1400c7d5c`
- `ntdll!RtlFreeHeap` at `0x1400c7d5c`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1400c7ca1`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1400c7ca1`
- `ntdll!NtQueryInformationFile` at `0x1400c7dd9`
- `ntdll!NtQueryInformationFile` at `0x1400c7dd9`

## pseudocode

```c
__int64 __fastcall BLBIMGI_BACKUP_FILE::InitializeForWrite(
        __int64 *a1,
        __int64 a2,
        _DWORD *a3,
        char a4,
        __int64 a5,
        char a6,
        __int64 a7,
        __int128 *a8,
        _DWORD *a9,
        unsigned __int8 a10,
        int a11,
        _QWORD *a12,
        _QWORD *a13,
        _DWORD *a14,
        _QWORD *a15,
        _DWORD *a16,
        DWORD *a17)
{
  _DWORD *v17; // r14
  unsigned __int16 *v18; // rsi
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rdi
  char v24; // cl
  char v25; // r8
  char v26; // r9
  char v27; // al
  char v28; // r10
  char v29; // r11
  char v30; // bl
  char v31; // di
  __int16 v32; // si
  __int64 *v33; // r13
  unsigned int v34; // ebx
  int v35; // ebx
  __int64 v36; // r8
  __int128 v37; // xmm0
  bool v38; // zf
  unsigned int v39; // r8d
  __int64 v40; // rax
  HLOCAL v41; // rax
  HANDLE EventW; // rax
  unsigned __int64 v43; // rax
  __int64 v44; // rdx
  unsigned __int64 v45; // rbx
  unsigned __int64 v46; // rcx
  __int64 v47; // rax
  unsigned __int64 v48; // rbx
  unsigned __int16 *v49; // rax
  int v50; // eax
  HANDLE FileW; // rax
  __int64 v52; // rdx
  __int64 v53; // r9
  DWORD LastError; // eax
  unsigned int started; // edi
  _QWORD *v56; // rcx
  __int64 v57; // rdx
  int v58; // edi
  _QWORD *v59; // rcx
  __int64 v60; // rdx
  int v61; // eax
  BLBIMGI_BACKUP_FILE *v62; // rcx
  unsigned int v63; // eax
  _QWORD *v64; // rcx
  __int64 v65; // rdx
  PVOID *v66; // rcx
  __int64 v67; // rcx
  __int64 v68; // r8
  HLOCAL v69; // rsi
  int v70; // edx
  _QWORD *v71; // r9
  __int64 v72; // rdi
  __int64 v73; // rax
  __int64 v74; // rdi
  __int64 v75; // r14
  char dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  char v77; // [rsp+80h] [rbp-80h] BYREF
  char v78; // [rsp+81h] [rbp-7Fh]
  unsigned int v79; // [rsp+84h] [rbp-7Ch]
  HLOCAL hMem; // [rsp+88h] [rbp-78h] BYREF
  int v81; // [rsp+90h] [rbp-70h]
  unsigned int v82; // [rsp+94h] [rbp-6Ch]
  int v83; // [rsp+98h] [rbp-68h]
  __int64 v84; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v85; // [rsp+A8h] [rbp-58h]
  __int64 v86; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD *v87; // [rsp+B8h] [rbp-48h]
  __int64 v88; // [rsp+C0h] [rbp-40h]
  HLOCAL v89; // [rsp+C8h] [rbp-38h]
  __int64 v90; // [rsp+D0h] [rbp-30h]
  HLOCAL v91; // [rsp+D8h] [rbp-28h]
  _DWORD *v92; // [rsp+E0h] [rbp-20h]
  _QWORD *v93; // [rsp+E8h] [rbp-18h]
  _QWORD *v94; // [rsp+F0h] [rbp-10h]
  _DWORD *v95; // [rsp+F8h] [rbp-8h]
  _QWORD *v96; // [rsp+100h] [rbp+0h]
  _DWORD *v97; // [rsp+108h] [rbp+8h]
  struct _UNICODE_STRING NtPathName; // [rsp+110h] [rbp+10h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+120h] [rbp+20h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+130h] [rbp+30h] BYREF
  __int128 FileInformation; // [rsp+160h] [rbp+60h] BYREF
  __int128 v102; // [rsp+170h] [rbp+70h]
  __int64 v103; // [rsp+180h] [rbp+80h]

  v87 = a9;
  v17 = a3;
  v93 = a12;
  v18 = (unsigned __int16 *)a2;
  v94 = a13;
  v95 = a14;
  v96 = a15;
  v97 = a16;
  v103 = 0;
  v78 = a4;
  v92 = a3;
  v85 = (unsigned __int16 *)a2;
  v90 = 0;
  v91 = 0;
  v79 = 0;
  v88 = 0;
  v89 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v77 = 0;
  v84 = 0;
  hMem = 0;
  NtPathName = 0;
  v86 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  FileInformation = 0;
  v102 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids);
  }
  IoStatusBlock = 0;
  v103 = 0;
  FileInformation = 0;
  v102 = 0;
  BLBIMGI_BACKUP_FILE::Destroy((BLBIMGI_BACKUP_FILE *)a1);
  v22 = a7;
  v84 = 0;
  if ( a7 > 0x1FDFFE00000LL )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids);
    }
    return 25;
  }
  a1[3] = a5;
  if ( !a5 || !a6 )
    a1[3] = 0x7FFFFFFFFFFFFFFFLL;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v24 = *((_BYTE *)v17 + 14);
    v25 = *((_BYTE *)v17 + 13);
    v26 = *((_BYTE *)v17 + 12);
    v27 = *((_BYTE *)v17 + 15);
    v28 = *((_BYTE *)v17 + 11);
    v29 = *((_BYTE *)v17 + 10);
    v30 = *((_BYTE *)v17 + 9);
    v31 = *((_BYTE *)v17 + 8);
    v32 = *((_WORD *)v17 + 3);
    dwCreationDisposition = *((_WORD *)v17 + 2);
    v17 = v92;
    WPP_SF_DDDDDDDDDDDS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      (unsigned int)WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids,
      *v92,
      dwCreationDisposition,
      v32,
      v31,
      v30,
      v29,
      v28,
      v26,
      v25,
      v24,
      v27,
      (__int64)v85);
    v18 = v85;
    v22 = a7;
  }
  v33 = a1 + 5;
  *((_DWORD *)a1 + 94) = a11;
  LOBYTE(v21) = 1;
  a1[45] = 0;
  a1[4] = v22;
  *((_BYTE *)a1 + 48) = 1;
  v34 = BLBIMGI_BACKUP_FILE::ComputeDiskSize(v20, v22, v21, a1 + 5, a17);
  if ( v34 )
  {
LABEL_141:
    BLBIMGI_BACKUP_FILE::Destroy((BLBIMGI_BACKUP_FILE *)a1);
    return v34;
  }
  if ( *v33 > 0x1FE00000000LL )
  {
    v34 = 25;
    goto LABEL_141;
  }
  *((_BYTE *)a1 + 72) = a6;
  a1[7] = 0;
  a1[8] = 0;
  *((_BYTE *)a1 + 73) = 0;
  v35 = 0x10000;
  a1[10] = (__int64)LocalAlloc(0, 0x10024u);
  a1[11] = (__int64)LocalAlloc(0, 0x10000u);
  a1[12] = (__int64)LocalAlloc(0, 0x10000u);
  *((_DWORD *)a1 + 26) = 0;
  v37 = *a8;
  *((_DWORD *)a1 + 42) = 0;
  *((_OWORD *)a1 + 7) = v37;
  *((_DWORD *)a1 + 43) = v22 % 0x10000;
  if ( (unsigned int)(v22 % 0x10000) )
    v35 = v22 % 0x10000;
  else
    *((_DWORD *)a1 + 43) = 0x10000;
  *((_BYTE *)a1 + 336) = a10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_idL(*((_QWORD *)WPP_GLOBAL_Control + 2), &WPP_GLOBAL_Control, v36, a1[3], a10, v35);
  }
  v38 = *((_BYTE *)a1 + 72) == 0;
  v39 = 1536;
  *((_DWORD *)a1 + 45) = 1536;
  if ( !v38 )
  {
    v39 = (((unsigned int)(*v87 + 4223) >> 12) + 3) << 9;
    *((_DWORD *)a1 + 45) = v39;
  }
  v40 = (*v33 + 0x1FFFFF) / 0x200000;
  *((_BYTE *)a1 + 192) = 0;
  *((_DWORD *)a1 + 47) = v40;
  *((_DWORD *)a1 + 46) = (v39 >> 9) + ((unsigned int)(4 * v40 + 511) >> 9) + 1;
  v41 = LocalAlloc(0, 0x10200u);
  a1[25] = (__int64)v41;
  a1[26] = ((unsigned __int64)v41 + 0xFFFF) & 0xFFFFFFFFFFFF0000uLL;
  EventW = CreateEventW(0, 1, 0, 0);
  a1[30] = (__int64)EventW;
  if ( !EventW )
  {
    *a17 = GetLastError();
LABEL_140:
    v34 = 7;
    goto LABEL_141;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_LLL(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids);
  }
  v43 = (unsigned __int64)LocalAlloc(0, 0x1FEE8u);
  if ( v43 )
  {
    v45 = (v43 & 0xFFFFFFFFFFFFFF00uLL) + 256;
    v38 = dword_140160788 == 0;
    *(_QWORD *)(v45 + 8) = v43;
    v46 = (v43 & 0xFFFFFFFFFFFFFF00uLL) + 512;
    *(_QWORD *)(v45 + 32) = 0xFFFF;
    *(_QWORD *)(v45 + 48) = qword_14015EB00;
    *(_QWORD *)(v45 + 16) = (v43 & 0xFFFFFFFFFFFFFF00uLL) + 108288;
    *(_DWORD *)(v45 + 40) = 0;
    *(_DWORD *)v45 = 1407697118;
    *(_QWORD *)(v45 + 24) = v46;
    if ( v38 )
      bitno_init(v46, v44);
  }
  else
  {
    v45 = 0;
  }
  a1[38] = v45;
  if ( !v45 )
  {
    *a17 = GetLastError();
    v34 = 3;
    goto LABEL_141;
  }
  a1[39] = 0;
  *((_OWORD *)a1 + 20) = *(_OWORD *)v17;
  if ( !a1[10] || !a1[11] || !a1[12] || !a1[25] )
  {
    *a17 = GetLastError();
    BLBIMGI_BACKUP_FILE::Destroy((BLBIMGI_BACKUP_FILE *)a1);
    return 3;
  }
  v47 = -1;
  do
    ++v47;
  while ( v18[v47] );
  v48 = v47 + 1;
  v49 = (unsigned __int16 *)LocalAlloc(0, 2 * (v47 + 1));
  a1[1] = (__int64)v49;
  if ( !v49 )
    return 8;
  v50 = StringCchCopyW(v49, v48, v18);
  if ( v50 < 0 )
  {
    v34 = 8;
    *a17 = (unsigned __int16)v50;
    goto LABEL_141;
  }
  v34 = 2;
  if ( a6 )
  {
    FileW = CreateFileW(v18, 0xC0000000, 0, 0, 2u, 0x60000080u, 0);
    *a1 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      *a17 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_SLd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          57,
          (unsigned int)WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids,
          (_DWORD)v18,
          0,
          LastError);
      }
      goto LABEL_140;
    }
    v77 = 0;
    goto LABEL_101;
  }
  started = BLBIMGI_BACKUP_FILE::QueryBatBlockListFromExistingBackupFile(a1, v18, v22, &v77, &hMem, &v84, a17);
  if ( started )
  {
    BLBIMGI_BACKUP_FILE::Destroy((BLBIMGI_BACKUP_FILE *)a1);
    v56 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return started;
    }
    v57 = 58;
    goto LABEL_64;
  }
  if ( !RtlDosPathNameToNtPathName_U(v18, &NtPathName, 0, 0) )
  {
    *a17 = 123;
    if ( v77 )
      LocalFree(hMem);
    goto LABEL_141;
  }
  ObjectAttributes.ObjectName = &NtPathName;
  v86 = v84;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v58 = NtCreateFile(
          (PHANDLE)a1,
          0xC0100080,
          &ObjectAttributes,
          &IoStatusBlock,
          (PLARGE_INTEGER)((unsigned __int64)&v86 & -(__int64)(v77 != 0)),
          0x80u,
          0,
          3u,
          0x48u,
          0,
          0);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  if ( v58 < 0 )
  {
    *a1 = 0;
    if ( v77 )
      LocalFree(hMem);
    *a17 = RtlNtStatusToDosError(v58);
    BLBIMGI_BACKUP_FILE::Destroy((BLBIMGI_BACKUP_FILE *)a1);
    v59 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 7;
    }
    v60 = 59;
    goto LABEL_127;
  }
  v61 = NtQueryInformationFile((HANDLE)*a1, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
  if ( v61 < 0 )
  {
    *a17 = RtlNtStatusToDosError(v61);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids);
    }
    if ( v77 )
      LocalFree(hMem);
    BLBIMGI_BACKUP_FILE::Destroy((BLBIMGI_BACKUP_FILE *)a1);
    v59 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 7;
    }
    v60 = 61;
    goto LABEL_127;
  }
  if ( (v103 & 0x800) == 0 )
    goto LABEL_101;
  v62 = (BLBIMGI_BACKUP_FILE *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids, v18);
  }
  v63 = BLBIMGI_BACKUP_FILE::UncompressBackupFile(v62, (void *)*a1);
  *a17 = v63;
  if ( v63 )
  {
    v64 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_140;
    }
    v65 = 63;
LABEL_139:
    WPP_SF_d(v64[2], v65, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids);
    goto LABEL_140;
  }
  v66 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
LABEL_102:
      if ( v66 != &WPP_GLOBAL_Control && (*((_BYTE *)v66 + 28) & 4) != 0 && *((_BYTE *)v66 + 25) >= 4u )
        WPP_SF_Sq(
          (unsigned int)v66[2],
          65,
          (unsigned int)WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids,
          (_DWORD)v18,
          *a1);
      goto LABEL_106;
    }
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids, v18);
LABEL_101:
    v66 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_102;
  }
LABEL_106:
  LOBYTE(v53) = v77;
  started = BLBIMGI_BACKUP_FILE::BuildStartBlock(a1, v52, v87, v53, hMem);
  if ( v77 )
    LocalFree(hMem);
  if ( started )
  {
    BLBIMGI_BACKUP_FILE::Destroy((BLBIMGI_BACKUP_FILE *)a1);
    v56 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return started;
    }
    v57 = 66;
LABEL_64:
    WPP_SF_dd(v56[2], v57, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids);
    return started;
  }
  v67 = v82;
  v68 = v88;
  v69 = v89;
  v70 = v81;
  v71 = v93;
  v72 = v79;
  *((_DWORD *)a1 + 41) = v83;
  v73 = *a1;
  *((_DWORD *)a1 + 36) = v67;
  a1[19] = v68;
  *((_DWORD *)a1 + 40) = v70;
  a1[17] = (__int64)v69;
  *v71 = v73;
  *v94 = v68;
  *v95 = v70;
  *v96 = v69;
  *v97 = v67;
  v74 = 2097664 * v67 + v72 + 512;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
  {
    v75 = a5;
  }
  else
  {
    v75 = a5;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_iii(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids, v74, a5, v84);
  }
  if ( a6 )
  {
    if ( v74 > v75 )
      v74 = v75;
  }
  else if ( v77 && v74 < v84 )
  {
    v74 = v84;
  }
  a1[44] = v84;
  a1[43] = v74;
  if ( !a6 )
  {
    if ( !(unsigned int)BLBIMGI_BACKUP_FILE::SetFileSize((BLBIMGI_BACKUP_FILE *)a1, v74) )
    {
      *a17 = GetLastError();
      BLBIMGI_BACKUP_FILE::Destroy((BLBIMGI_BACKUP_FILE *)a1);
      v59 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 7;
      }
      v60 = 68;
LABEL_127:
      WPP_SF_d(v59[2], v60, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids);
      return 7;
    }
    if ( !v78 && !SetFileValidData((HANDLE)*a1, v74) )
    {
      *a17 = GetLastError();
      v64 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_140;
      }
      v65 = 69;
      goto LABEL_139;
    }
  }
  started = BLBIMGI_BACKUP_FILE::WriteStartBlock(a1, v90, v79, a17);
  LocalFree(v91);
  if ( started )
  {
    BLBIMGI_BACKUP_FILE::Destroy((BLBIMGI_BACKUP_FILE *)a1);
    LocalFree(v69);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids);
    }
    return started;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x1400c7594  mov     [rsp-8+arg_18], rbx
0x1400c7599  push    rbp
0x1400c759a  push    rsi
0x1400c759b  push    rdi
0x1400c759c  push    r12
0x1400c759e  push    r13
0x1400c75a0  push    r14
0x1400c75a2  push    r15
0x1400c75a4  lea     rbp, [rsp-90h]
0x1400c75ac  sub     rsp, 190h
0x1400c75b3  mov     rax, cs:__security_cookie
0x1400c75ba  xor     rax, rsp
0x1400c75bd  mov     [rbp+0C0h+var_38], rax
0x1400c75c4  mov     rax, [rbp+0C0h+arg_40]
0x1400c75cb  xor     ebx, ebx
0x1400c75cd  mov     r12, [rbp+0C0h+arg_80]
0x1400c75d4  xorps   xmm1, xmm1
0x1400c75d7  mov     [rbp+0C0h+var_108], rax
0x1400c75db  xorps   xmm0, xmm0
0x1400c75de  mov     rax, [rbp+0C0h+arg_58]
0x1400c75e5  mov     r14, r8
0x1400c75e8  mov     [rbp+0C0h+var_D8], rax
0x1400c75ec  mov     rsi, rdx
0x1400c75ef  mov     rax, [rbp+0C0h+arg_60]
0x1400c75f6  mov     r15, rcx
0x1400c75f9  mov     [rbp+0C0h+var_D0], rax
0x1400c75fd  mov     rax, [rbp+0C0h+arg_68]
0x1400c7604  mov     [rbp+0C0h+var_C8], rax
0x1400c7608  mov     rax, [rbp+0C0h+arg_70]
0x1400c760f  mov     [rbp+0C0h+var_C0], rax
0x1400c7613  mov     rax, [rbp+0C0h+arg_78]
0x1400c761a  mov     [rbp+0C0h+var_B8], rax
0x1400c761e  xor     eax, eax
0x1400c7620  mov     [rbp+0C0h+var_40], rax
0x1400c7627  mov     [rbp+0C0h+var_13F], r9b
0x1400c762b  mov     [rbp+0C0h+var_E0], r8
0x1400c762f  mov     [rbp+0C0h+var_118], rdx
0x1400c7633  mov     [rbp+0C0h+var_F0], rbx
0x1400c7637  mov     [rbp+0C0h+var_E8], rbx
0x1400c763b  mov     [rbp+0C0h+var_13C], ebx
0x1400c763e  mov     [rbp+0C0h+var_100], rbx
0x1400c7642  mov     [rbp+0C0h+var_F8], rbx
0x1400c7646  mov     [rbp+0C0h+var_130], ebx
0x1400c7649  mov     [rbp+0C0h+var_12C], ebx
0x1400c764c  mov     [rbp+0C0h+var_128], ebx
0x1400c764f  mov     [rbp+0C0h+var_140], bl
0x1400c7652  mov     [rbp+0C0h+var_120], rbx
0x1400c7656  mov     [rbp+0C0h+hMem], rbx
0x1400c765a  movups  xmmword ptr [rbp+0C0h+NtPathName.Length], xmm0
0x1400c765e  mov     [rbp+0C0h+var_110], rbx
0x1400c7662  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.Length], xmm1
0x1400c7666  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.ObjectName], xmm1
0x1400c766a  movups  xmmword ptr [rbp+0C0h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400c766e  movups  xmmword ptr [rbp+0C0h+IoStatusBlock], xmm0
0x1400c7672  movups  [rbp+0C0h+FileInformation], xmm1
0x1400c7676  movups  [rbp+0C0h+var_50], xmm1
0x1400c767a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c7681  lea     r13, WPP_GLOBAL_Control
0x1400c7688  cmp     rcx, r13
0x1400c768b  jz      short loc_1400C76AC
0x1400c768d  test    byte ptr [rcx+1Ch], 4
0x1400c7691  jz      short loc_1400C76AC
0x1400c7693  cmp     byte ptr [rcx+19h], 4
0x1400c7697  jb      short loc_1400C76AC
0x1400c7699  mov     rcx, [rcx+10h]
0x1400c769d  lea     edx, [rbx+34h]
0x1400c76a0  lea     r8, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids
0x1400c76a7  call    WPP_SF_
0x1400c76ac  xorps   xmm1, xmm1
0x1400c76af  xorps   xmm0, xmm0
0x1400c76b2  xor     eax, eax
0x1400c76b4  mov     rcx, r15; this
0x1400c76b7  movups  xmmword ptr [rbp+0C0h+IoStatusBlock], xmm0
0x1400c76bb  mov     [rbp+0C0h+var_40], rax
0x1400c76c2  movups  [rbp+0C0h+FileInformation], xmm1
0x1400c76c6  movups  [rbp+0C0h+var_50], xmm1
0x1400c76ca  call    ?Destroy@BLBIMGI_BACKUP_FILE@@QEAAXXZ; BLBIMGI_BACKUP_FILE::Destroy(void)
0x1400c76cf  mov     rdi, [rbp+0C0h+arg_30]
0x1400c76d6  mov     rax, 1FDFFE00000h
0x1400c76e0  mov     [rbp+0C0h+var_120], rbx
0x1400c76e4  cmp     rdi, rax
0x1400c76e7  jle     short loc_1400C772D
0x1400c76e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c76f0  cmp     rcx, r13
0x1400c76f3  jz      short loc_1400C7723
0x1400c76f5  test    byte ptr [rcx+1Ch], 4
0x1400c76f9  jz      short loc_1400C7723
0x1400c76fb  mov     ebx, 2
0x1400c7700  cmp     [rcx+19h], bl
0x1400c7703  jb      short loc_1400C7723
0x1400c7705  mov     rcx, [rcx+10h]
0x1400c7709  lea     edx, [rbx+33h]
0x1400c770c  mov     r9, rdi
0x1400c770f  mov     [rsp+1C0h+dwCreationDisposition], edi
0x1400c7713  shr     r9, 20h
0x1400c7717  lea     r8, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids
0x1400c771e  call    WPP_SF_dd
0x1400c7723  mov     eax, 19h
0x1400c7728  jmp     loc_1400C82C5
0x1400c772d  mov     rax, [rbp+0C0h+arg_20]
0x1400c7734  mov     [r15+18h], rax
0x1400c7738  test    rax, rax
0x1400c773b  jz      short loc_1400C7745
0x1400c773d  cmp     [rbp+0C0h+arg_28], bl
0x1400c7743  jnz     short loc_1400C7753
0x1400c7745  mov     rax, 7FFFFFFFFFFFFFFFh
0x1400c774f  mov     [r15+18h], rax
0x1400c7753  mov     r13, cs:WPP_GLOBAL_Control
0x1400c775a  lea     rax, WPP_GLOBAL_Control
0x1400c7761  cmp     r13, rax
0x1400c7764  jz      loc_1400C7818
0x1400c776a  test    byte ptr [r13+1Ch], 4
0x1400c776f  jz      loc_1400C7818
0x1400c7775  cmp     byte ptr [r13+19h], 4
0x1400c777a  jb      loc_1400C7818
0x1400c7780  movzx   ecx, byte ptr [r14+0Eh]
0x1400c7785  mov     edx, 36h ; '6'
0x1400c778a  movzx   r8d, byte ptr [r14+0Dh]
0x1400c778f  movzx   r9d, byte ptr [r14+0Ch]
0x1400c7794  movzx   eax, byte ptr [r14+0Fh]
0x1400c7799  movzx   r10d, byte ptr [r14+0Bh]
0x1400c779e  movzx   r11d, byte ptr [r14+0Ah]
0x1400c77a3  movzx   ebx, byte ptr [r14+9]
0x1400c77a8  movzx   edi, byte ptr [r14+8]
0x1400c77ad  movzx   esi, word ptr [r14+6]
0x1400c77b2  movzx   r14d, word ptr [r14+4]
0x1400c77b7  mov     r13, [rbp+0C0h+var_118]
0x1400c77bb  mov     [rsp+1C0h+var_150], r13
0x1400c77c0  mov     r13, cs:WPP_GLOBAL_Control
0x1400c77c7  mov     dword ptr [rsp+1C0h+var_158], eax
0x1400c77cb  mov     dword ptr [rsp+1C0h+var_160], ecx
0x1400c77cf  mov     dword ptr [rsp+1C0h+var_168], r8d
0x1400c77d4  lea     r8, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids
0x1400c77db  mov     rcx, [r13+10h]
0x1400c77df  mov     [rsp+1C0h+EaLength], r9d
0x1400c77e4  mov     dword ptr [rsp+1C0h+EaBuffer], r10d
0x1400c77e9  mov     [rsp+1C0h+CreateOptions], r11d
0x1400c77ee  mov     [rsp+1C0h+CreateDisposition], ebx
0x1400c77f2  mov     dword ptr [rsp+1C0h+hTemplateFile], edi
0x1400c77f6  mov     [rsp+1C0h+dwFlagsAndAttributes], esi
0x1400c77fa  mov     [rsp+1C0h+dwCreationDisposition], r14d
0x1400c77ff  mov     r14, [rbp+0C0h+var_E0]
0x1400c7803  mov     r9d, [r14]
0x1400c7806  call    WPP_SF_DDDDDDDDDDDS
0x1400c780b  mov     rsi, [rbp+0C0h+var_118]
0x1400c780f  xor     ebx, ebx
0x1400c7811  mov     rdi, [rbp+0C0h+arg_30]
0x1400c7818  mov     eax, [rbp+0C0h+arg_50]
0x1400c781e  lea     r13, [r15+28h]
0x1400c7822  mov     r9, r13
0x1400c7825  mov     [r15+178h], eax
0x1400c782c  mov     r8b, 1
0x1400c782f  mov     [r15+168h], rbx
0x1400c7836  mov     rdx, rdi
0x1400c7839  mov     [r15+20h], rdi
0x1400c783d  mov     byte ptr [r15+30h], 1
0x1400c7842  mov     qword ptr [rsp+1C0h+dwCreationDisposition], r12
0x1400c7847  call    ?ComputeDiskSize@BLBIMGI_BACKUP_FILE@@AEAA?AW4_BLBIMG_RESULT_CODE@@_JEPEA_JPEAK@Z; BLBIMGI_BACKUP_FILE::ComputeDiskSize(__int64,uchar,__int64 *,ulong *)
0x1400c784c  xor     ecx, ecx; uFlags
0x1400c784e  mov     ebx, eax
0x1400c7850  test    eax, eax
0x1400c7852  jnz     loc_1400C81EB
0x1400c7858  mov     rax, 1FE00000000h
0x1400c7862  cmp     [r13+0], rax
0x1400c7866  jle     short loc_1400C7870
0x1400c7868  lea     ebx, [rcx+19h]
0x1400c786b  jmp     loc_1400C81EB
0x1400c7870  mov     al, [rbp+0C0h+arg_28]
0x1400c7876  mov     edx, 10024h; uBytes
0x1400c787b  mov     [r15+48h], al
0x1400c787f  mov     [r15+38h], rcx
0x1400c7883  mov     [r15+40h], rcx
0x1400c7887  mov     [r15+49h], cl
0x1400c788b  call    cs:__imp_LocalAlloc
0x1400c7891  mov     ebx, 10000h
0x1400c7896  xor     ecx, ecx; uFlags
0x1400c7898  mov     edx, ebx; uBytes
0x1400c789a  mov     [r15+50h], rax
0x1400c789e  call    cs:__imp_LocalAlloc
0x1400c78a4  mov     edx, ebx; uBytes
0x1400c78a6  xor     ecx, ecx; uFlags
0x1400c78a8  mov     [r15+58h], rax
0x1400c78ac  call    cs:__imp_LocalAlloc
0x1400c78b2  mov     [r15+60h], rax
0x1400c78b6  xor     ecx, ecx
0x1400c78b8  mov     rax, [rbp+0C0h+arg_38]
0x1400c78bf  mov     [r15+68h], ecx
0x1400c78c3  movups  xmm0, xmmword ptr [rax]
0x1400c78c6  mov     rax, rdi
0x1400c78c9  mov     [r15+0A8h], ecx
0x1400c78d0  cqo
0x1400c78d2  idiv    rbx
0x1400c78d5  movdqu  xmmword ptr [r15+70h], xmm0
0x1400c78db  mov     [r15+0ACh], edx
0x1400c78e2  test    edx, edx
0x1400c78e4  jnz     short loc_1400C78EF
0x1400c78e6  mov     [r15+0ACh], ebx
0x1400c78ed  jmp     short loc_1400C78F1
0x1400c78ef  mov     ebx, edx
0x1400c78f1  movzx   eax, [rbp+0C0h+arg_48]
0x1400c78f8  mov     [r15+150h], al
0x1400c78ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c7906  lea     rdx, WPP_GLOBAL_Control
0x1400c790d  cmp     rcx, rdx
0x1400c7910  jz      short loc_1400C7933
0x1400c7912  test    byte ptr [rcx+1Ch], 4
0x1400c7916  jz      short loc_1400C7933
0x1400c7918  cmp     byte ptr [rcx+19h], 4
0x1400c791c  jb      short loc_1400C7933
0x1400c791e  mov     r9, [r15+18h]
0x1400c7922  mov     rcx, [rcx+10h]
0x1400c7926  mov     [rsp+1C0h+dwFlagsAndAttributes], ebx
0x1400c792a  mov     [rsp+1C0h+dwCreationDisposition], eax
0x1400c792e  call    WPP_SF_idL
0x1400c7933  cmp     byte ptr [r15+48h], 0
0x1400c7938  mov     r8d, 600h
0x1400c793e  mov     [r15+0B4h], r8d
0x1400c7945  jz      short loc_1400C7968
0x1400c7947  mov     r8, [rbp+0C0h+var_108]
0x1400c794b  mov     r8d, [r8]
0x1400c794e  add     r8d, 107Fh
0x1400c7955  shr     r8d, 0Ch
0x1400c7959  add     r8d, 3
0x1400c795d  shl     r8d, 9
0x1400c7961  mov     [r15+0B4h], r8d
0x1400c7968  mov     rax, [r13+0]
0x1400c796c  mov     ecx, 200000h
0x1400c7971  add     rax, 1FFFFFh
0x1400c7977  shr     r8d, 9
0x1400c797b  cqo
0x1400c797d  xor     r13d, r13d
0x1400c7980  idiv    rcx
0x1400c7983  mov     edx, 10200h; uBytes
0x1400c7988  mov     [r15+0C0h], r13b
0x1400c798f  mov     [r15+0BCh], eax
0x1400c7996  lea     ecx, ds:1FFh[rax*4]
0x1400c799d  shr     ecx, 9
0x1400c79a0  inc     ecx
0x1400c79a2  add     ecx, r8d
0x1400c79a5  mov     [r15+0B8h], ecx
0x1400c79ac  xor     ecx, ecx; uFlags
0x1400c79ae  call    cs:__imp_LocalAlloc
0x1400c79b4  mov     [r15+0C8h], rax
0x1400c79bb  xor     r9d, r9d; lpName
0x1400c79be  add     rax, 0FFFFh
0x1400c79c4  lea     edx, [r13+1]; bManualReset
0x1400c79c8  and     rax, 0FFFFFFFFFFFF0000h
0x1400c79ce  xor     r8d, r8d; bInitialState
0x1400c79d1  xor     ecx, ecx; lpEventAttributes
0x1400c79d3  mov     [r15+0D0h], rax
0x1400c79da  call    cs:__imp_CreateEventW
0x1400c79e0  mov     [r15+0F0h], rax
0x1400c79e7  test    rax, rax
0x1400c79ea  jnz     short loc_1400C79FB
0x1400c79ec  call    cs:__imp_GetLastError
0x1400c79f2  mov     [r12], eax
0x1400c79f6  jmp     loc_1400C81E6
0x1400c79fb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c7a02  lea     rax, WPP_GLOBAL_Control
0x1400c7a09  cmp     rcx, rax
0x1400c7a0c  jz      short loc_1400C7A4C
0x1400c7a0e  test    byte ptr [rcx+1Ch], 4
0x1400c7a12  jz      short loc_1400C7A4C
0x1400c7a14  cmp     byte ptr [rcx+19h], 4
0x1400c7a18  jb      short loc_1400C7A4C
0x1400c7a1a  mov     eax, [r15+0B8h]
0x1400c7a21  lea     r8, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids
0x1400c7a28  mov     r9d, [r15+0B4h]
0x1400c7a2f  mov     edx, 38h ; '8'
0x1400c7a34  mov     rcx, [rcx+10h]
0x1400c7a38  mov     [rsp+1C0h+dwFlagsAndAttributes], eax
0x1400c7a3c  mov     eax, [r15+0BCh]
0x1400c7a43  mov     [rsp+1C0h+dwCreationDisposition], eax
0x1400c7a47  call    WPP_SF_LLL
0x1400c7a4c  mov     edx, 1FEE8h; uBytes
0x1400c7a51  xor     ecx, ecx; uFlags
0x1400c7a53  call    cs:__imp_LocalAlloc
0x1400c7a59  test    rax, rax
0x1400c7a5c  jnz     short loc_1400C7A63
0x1400c7a5e  mov     rbx, r13
0x1400c7a61  jmp     short loc_1400C7AB9
0x1400c7a63  mov     rbx, rax
0x1400c7a66  and     rbx, 0FFFFFFFFFFFFFF00h
0x1400c7a6d  add     rbx, 100h
0x1400c7a74  cmp     cs:dword_140160788, r13d
0x1400c7a7b  mov     [rbx+8], rax
0x1400c7a7f  lea     rcx, [rbx+100h]
0x1400c7a86  lea     rax, qword_14015EB00
0x1400c7a8d  mov     qword ptr [rbx+20h], 0FFFFh
0x1400c7a95  mov     [rbx+30h], rax
0x1400c7a99  lea     rax, [rcx+1A500h]
0x1400c7aa0  mov     [rbx+10h], rax
0x1400c7aa4  mov     [rbx+28h], r13d
0x1400c7aa8  mov     dword ptr [rbx], 53E7C0DEh
0x1400c7aae  mov     [rbx+18h], rcx
0x1400c7ab2  jnz     short loc_1400C7AB9
0x1400c7ab4  call    bitno_init
0x1400c7ab9  mov     [r15+130h], rbx
0x1400c7ac0  test    rbx, rbx
0x1400c7ac3  jnz     short loc_1400C7AD9
  ... truncated ...
```
