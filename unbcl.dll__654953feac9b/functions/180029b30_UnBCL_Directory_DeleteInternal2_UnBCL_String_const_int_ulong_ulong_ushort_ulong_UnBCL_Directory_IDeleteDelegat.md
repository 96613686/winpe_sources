# UnBCL::Directory::DeleteInternal2(UnBCL::String const *,int,ulong,ulong,ushort *,ulong &,UnBCL::Directory::IDeleteDelegate *)

- ea: `0x180029b30`
- end: `0x18002a85b`
- name: `?DeleteInternal2@Directory@UnBCL@@CAKPEBVString@2@HKKPEAGAEAKPEAUIDeleteDelegate@12@@Z`
- size: `3371`
- prototype: `unsigned int __fastcall(const struct UnBCL::String *, int, unsigned int, unsigned int, unsigned __int16 *, unsigned int *, struct UnBCL::Directory::IDeleteDelegate *)`
- caller_count: `2`
- callee_count: `27`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180029ad0`
- `0x180029b30`

## callees

- `0x1800015ac`
- `0x180002f50`
- `0x180002f90`
- `0x180008160`
- `0x180011570`
- `0x180029b30`
- `0x18002b400`
- `0x180031dd0`
- `0x180031e40`
- `0x18003b740`
- `0x180048fb0`
- `0x180049140`
- `0x180049500`
- `0x180049aa0`
- `0x18004a440`
- `0x18005b6d0`
- `0x18005b790`
- `0x18005b9f0`
- `0x18005bda0`
- `0x18005be50`
- `0x18005c010`
- `0x18005c060`
- `0x18005de90`
- `0x180060150`
- `0x180068fe6`
- `0x180069020`
- `0x18006f010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180029c80`
- `msvcrt!_wcsicmp` at `0x180029fc8`
- `msvcrt!_wcsicmp` at `0x180029c80`
- `msvcrt!_wcsicmp` at `0x180029fc8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180029e47`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180029e5b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002a734`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180029e47`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180029e5b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002a734`
- `KERNEL32!CloseHandle` at `0x180029dd9`
- `KERNEL32!CloseHandle` at `0x180029e39`
- `KERNEL32!CloseHandle` at `0x180029e52`
- `KERNEL32!CloseHandle` at `0x180029fe1`
- `KERNEL32!CloseHandle` at `0x180029dd9`
- `KERNEL32!CloseHandle` at `0x180029e39`
- `KERNEL32!CloseHandle` at `0x180029e52`
- `KERNEL32!CloseHandle` at `0x180029fe1`
- `KERNEL32!GetLastError` at `0x180029d2d`
- `KERNEL32!GetLastError` at `0x180029e22`
- `KERNEL32!GetLastError` at `0x18002a137`
- `KERNEL32!GetLastError` at `0x18002a182`
- `KERNEL32!GetLastError` at `0x18002a5ba`
- `KERNEL32!GetLastError` at `0x180029d2d`
- `KERNEL32!GetLastError` at `0x180029e22`
- `KERNEL32!GetLastError` at `0x18002a137`
- `KERNEL32!GetLastError` at `0x18002a182`
- `KERNEL32!GetLastError` at `0x18002a5ba`
- `KERNEL32!FindFirstFileW` at `0x180029d21`
- `KERNEL32!FindFirstFileW` at `0x18002a123`
- `KERNEL32!FindFirstFileW` at `0x18002a16e`
- `KERNEL32!FindFirstFileW` at `0x180029d21`
- `KERNEL32!FindFirstFileW` at `0x18002a123`
- `KERNEL32!FindFirstFileW` at `0x18002a16e`
- `KERNEL32!FindNextFileW` at `0x18002a59a`
- `KERNEL32!FindNextFileW` at `0x18002a59a`
- `KERNEL32!DeviceIoControl` at `0x180029e12`
- `KERNEL32!DeviceIoControl` at `0x180029e12`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180029fb2`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180029fb2`
- `KERNEL32!FindClose` at `0x180029d5d`
- `KERNEL32!FindClose` at `0x18002a5b0`
- `KERNEL32!FindClose` at `0x180029d5d`
- `KERNEL32!FindClose` at `0x18002a5b0`
- `KERNEL32!GetFileAttributesW` at `0x180029d89`
- `KERNEL32!GetFileAttributesW` at `0x180029d89`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall UnBCL::Directory::DeleteInternal2(
        const wchar_t **a1,
        int a2,
        DWORD a3,
        signed int a4,
        unsigned __int16 *a5,
        unsigned int *a6,
        struct UnBCL::Directory::IDeleteDelegate *a7)
{
  unsigned int *v10; // r15
  struct UnBCL::Directory::IDeleteDelegate *v11; // r14
  int v12; // edi
  struct UnBCL::String *FullPath; // rax
  struct UnBCL::String *v14; // rax
  struct UnBCL::String *PathRoot; // rax
  struct UnBCL::String *v16; // rax
  HANDLE FirstFileW; // rax
  DWORD LastError; // eax
  DWORD FileAttributesW; // eax
  HANDLE v21; // rdi
  _DWORD *lpOutBuffer; // r12
  int v23; // eax
  int v24; // eax
  unsigned int v25; // r12d
  unsigned int v26; // edi
  HANDLE v27; // rax
  const wchar_t *v28; // r12
  int v29; // eax
  int v30; // eax
  const unsigned __int16 *v31; // rcx
  struct UnBCL::String *v32; // rax
  DWORD v33; // r12d
  const struct UnBCL::String *v34; // rax
  struct UnBCL::String *v35; // rax
  unsigned int v36; // eax
  int v37; // eax
  int v38; // eax
  __int64 v39; // r9
  __int64 v40; // r8
  int v41; // eax
  int v42; // eax
  int v43; // eax
  int v44; // eax
  DWORD v45; // eax
  unsigned int v46; // ecx
  __int64 v47; // r8
  int v48; // eax
  int v49; // eax
  int v50; // eax
  int v51; // eax
  _DWORD *v52; // rbx
  int v53; // eax
  UnBCL::String *v54; // rax
  UnBCL::String *v55; // rdi
  const struct UnBCL::String *v56; // rax
  _DWORD *v57; // rbx
  int v58; // eax
  UnBCL::String *v59; // rax
  UnBCL::String *v60; // rdi
  const struct UnBCL::String *v61; // rax
  unsigned int v62; // [rsp+40h] [rbp-628h]
  int v63; // [rsp+40h] [rbp-628h]
  unsigned int v64; // [rsp+44h] [rbp-624h]
  DWORD BytesReturned; // [rsp+48h] [rbp-620h] BYREF
  DWORD v66; // [rsp+4Ch] [rbp-61Ch]
  void **v67; // [rsp+50h] [rbp-618h] BYREF
  __int64 v68; // [rsp+58h] [rbp-610h]
  int v69; // [rsp+60h] [rbp-608h]
  DWORD dwFileAttributes; // [rsp+64h] [rbp-604h]
  BOOL v71; // [rsp+68h] [rbp-600h]
  unsigned int *v72; // [rsp+70h] [rbp-5F8h]
  const wchar_t **v73; // [rsp+78h] [rbp-5F0h]
  void **v74; // [rsp+80h] [rbp-5E8h] BYREF
  struct UnBCL::String *v75; // [rsp+88h] [rbp-5E0h]
  int v76; // [rsp+90h] [rbp-5D8h]
  LPWSTR lpszFilePath; // [rsp+98h] [rbp-5D0h]
  int v78; // [rsp+A0h] [rbp-5C8h]
  struct UnBCL::Directory::IDeleteDelegate *v79; // [rsp+A8h] [rbp-5C0h]
  HANDLE hObject; // [rsp+B0h] [rbp-5B8h]
  int v81; // [rsp+B8h] [rbp-5B0h]
  _BYTE v82[8]; // [rsp+C0h] [rbp-5A8h] BYREF
  __int64 v83; // [rsp+C8h] [rbp-5A0h]
  struct UnBCL::String *v84[2]; // [rsp+D0h] [rbp-598h] BYREF
  HANDLE hFindFile; // [rsp+E0h] [rbp-588h]
  WCHAR *v86; // [rsp+E8h] [rbp-580h]
  void **v87; // [rsp+F0h] [rbp-578h] BYREF
  __int64 v88; // [rsp+F8h] [rbp-570h]
  void **v89; // [rsp+100h] [rbp-568h] BYREF
  __int64 v90; // [rsp+108h] [rbp-560h]
  _QWORD v91[2]; // [rsp+110h] [rbp-558h] BYREF
  _BYTE v92[16]; // [rsp+120h] [rbp-548h] BYREF
  unsigned __int16 *v93; // [rsp+130h] [rbp-538h]
  __int64 v94; // [rsp+138h] [rbp-530h]
  _DWORD *v95; // [rsp+140h] [rbp-528h] BYREF
  __int64 v96; // [rsp+148h] [rbp-520h] BYREF
  _DWORD *v97; // [rsp+150h] [rbp-518h] BYREF
  __int64 v98; // [rsp+158h] [rbp-510h] BYREF
  _BYTE v99[32]; // [rsp+160h] [rbp-508h] BYREF
  struct _WIN32_FIND_DATAW v100; // [rsp+180h] [rbp-4E8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+3D0h] [rbp-298h] BYREF

  v94 = -2;
  v81 = a2;
  v86 = a5;
  v10 = a6;
  v72 = a6;
  v11 = a7;
  v79 = a7;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v74, 0);
  if ( a3 == -1 )
  {
    v12 = 1;
    FullPath = UnBCL::Path::GetFullPath((const struct UnBCL::String *)a1);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v67, FullPath);
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v74, v68);
    v67 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v67);
    v14 = UnBCL::Path::WithLongPrefix(v75, 1);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v67, v14);
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v74, v68);
    v67 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v67);
    a1 = (const wchar_t **)v75;
    if ( (unsigned int)UnBCL::String::EndsWith(v75, 0x5Cu) )
    {
      PathRoot = UnBCL::Path::GetPathRoot((const struct UnBCL::String *)a1);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v91, PathRoot);
      if ( _wcsicmp(*(const wchar_t **)(v91[1] + 16LL), a1[2]) )
      {
        v16 = UnBCL::String::Substring((UnBCL::String *)a1, 0, *((_DWORD *)a1[2] - 4) - 1);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v67, v16);
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v74, v68);
        v67 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v67);
        a1 = (const wchar_t **)v75;
      }
      else
      {
        v12 = 0;
      }
      v91[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v91);
    }
    UnBCL::Path::CheckPathTooLong((const struct UnBCL::String *)a1);
    if ( v12 )
    {
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      FirstFileW = FindFirstFileW(a1[2], &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
        goto LABEL_9;
      FindClose(FirstFileW);
      dwFileAttributes = FindFileData.dwFileAttributes;
      a4 = (FindFileData.dwFileAttributes & 0x400) != 0 ? FindFileData.dwReserved0 : 0;
    }
    else
    {
      FileAttributesW = GetFileAttributesW(a1[2]);
      dwFileAttributes = FileAttributesW;
      if ( FileAttributesW == -1 )
        goto LABEL_9;
      if ( (FileAttributesW & 0x400) == 0 )
        goto LABEL_25;
      v21 = pOpenFile(a1[2]);
      if ( v21 == (HANDLE)-1LL )
      {
LABEL_9:
        LastError = GetLastError();
        if ( LastError - 2 <= 1 )
        {
LABEL_11:
          v74 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
          UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v74);
          return 0;
        }
LABEL_10:
        *a6 = LastError;
        goto LABEL_11;
      }
      BytesReturned = 0;
      lpOutBuffer = operator new[](0x4000u);
      hObject = lpOutBuffer;
      if ( !lpOutBuffer )
      {
        CloseHandle(v21);
        *a6 = 8;
        goto LABEL_11;
      }
      if ( DeviceIoControl(v21, 0x900A8u, 0, 0, lpOutBuffer, 0x4000u, &BytesReturned, 0) )
      {
        a4 = *lpOutBuffer;
      }
      else
      {
        v66 = GetLastError();
        if ( v66 != 4390 )
        {
          CloseHandle(v21);
          operator delete[](lpOutBuffer);
          LastError = v66;
          goto LABEL_10;
        }
        a4 = 0;
      }
      CloseHandle(v21);
      operator delete[](hObject);
    }
  }
  else
  {
    dwFileAttributes = a3;
  }
LABEL_25:
  v73 = a1;
  if ( a7 )
  {
    v23 = (*(__int64 (__fastcall **)(struct UnBCL::Directory::IDeleteDelegate *, const wchar_t *, _QWORD))(*(_QWORD *)a7 + 80LL))(
            a7,
            a1[2],
            dwFileAttributes)
        - 1;
    if ( !v23 )
      goto LABEL_11;
    v24 = v23 - 1;
    if ( !v24 )
    {
      *a6 = 774;
      v25 = 0;
      goto LABEL_31;
    }
    if ( v24 == 1 )
    {
      v25 = 995;
LABEL_31:
      v74 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v74);
      return v25;
    }
  }
  v26 = 0;
  v64 = 0;
  lpszFilePath = v86;
  if ( !v81 )
    goto LABEL_119;
  BytesReturned = dwFileAttributes & 0x400;
  if ( (dwFileAttributes & 0x400) != 0 && (a4 >= 0 || a4 == -1610612733 || a4 == -1610612724) )
    goto LABEL_119;
  v78 = 0;
  if ( a7 && (*(unsigned int (__fastcall **)(struct UnBCL::Directory::IDeleteDelegate *))(*(_QWORD *)a7 + 64LL))(a7) )
  {
    if ( !v86 )
    {
      lpszFilePath = (LPWSTR)operator new[](0x10000u);
      if ( !lpszFilePath )
        UnBCL::Allocator::MemAllocFailed();
    }
    v27 = pOpenFile(a1[2]);
    hObject = v27;
    if ( v27 != (HANDLE)-1LL )
    {
      v71 = 0;
      v28 = lpszFilePath;
      if ( GetFinalPathNameByHandleW(v27, lpszFilePath, 0x7FFFu, 0) - 1 <= 0x7FFE )
        v71 = _wcsicmp(a1[2], v28) != 0;
      CloseHandle(hObject);
      if ( v71 )
      {
        v29 = (*(__int64 (__fastcall **)(struct UnBCL::Directory::IDeleteDelegate *, const wchar_t *, const wchar_t *))(*(_QWORD *)a7 + 72LL))(
                a7,
                a1[2],
                v28);
        v78 = v29;
        if ( v29 )
        {
          if ( v29 == 3 )
          {
            v26 = 681;
          }
          else if ( v29 == 2 )
          {
            *a6 = 681;
          }
          goto LABEL_136;
        }
      }
    }
  }
  hObject = lpszFilePath;
  memset_0(&v100, 0, sizeof(v100));
  UnBCL::String::String((UnBCL::String *)v92, 0x5Cu, 1);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v89, 0);
  v30 = UnBCL::String::EndsWith((UnBCL::String *)a1, v93, 1);
  v31 = a1[2];
  if ( v30 )
    v32 = UnBCL::String::Concat(v31, L"*");
  else
    v32 = UnBCL::String::Concat(v31, v93, L"*");
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v67, v32);
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v89, v68);
  v67 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v67);
  hFindFile = FindFirstFileW(*(LPCWSTR *)(v90 + 16), &v100);
  if ( hFindFile == (HANDLE)-1LL )
  {
    v33 = GetLastError();
    if ( v33 == 1920 )
    {
      if ( !BytesReturned
        || !(unsigned int)pRemoveReparsePointData(a1[2])
        || (hFindFile = FindFirstFileW(*(LPCWSTR *)(v90 + 16), &v100), hFindFile != (HANDLE)-1LL) )
      {
LABEL_61:
        *a6 = v33;
        if ( hFindFile != (HANDLE)-1LL )
          goto LABEL_62;
        goto LABEL_117;
      }
      v33 = GetLastError();
    }
    if ( v33 - 2 <= 1 || !v33 )
      goto LABEL_117;
    goto LABEL_61;
  }
LABEL_62:
  while ( 1 )
  {
    v34 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v99, v100.cFileName);
    v35 = UnBCL::Path::Combine((const struct UnBCL::String *)a1, v34);
    UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v82, v35);
    UnBCL::String::~String((UnBCL::String *)v99);
    if ( (v100.dwFileAttributes & 0x10) == 0 )
      break;
    if ( v100.cFileName[0] != 46 || v100.cFileName[1] && (v100.cFileName[1] != 46 || v100.cFileName[2]) )
    {
      v36 = UnBCL::Directory::DeleteInternal2(
              *(struct UnBCL::String **)((char *)v84 + *(int *)(v83 + 4)),
              v81,
              v100.dwFileAttributes,
              (v100.dwFileAttributes & 0x400) != 0 ? v100.dwReserved0 : 0,
              lpszFilePath,
              v10,
              v11);
      if ( v36 )
      {
        v26 = v36;
        goto LABEL_69;
      }
    }
LABEL_112:
    v84[0] = (struct UnBCL::String *)&UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v84);
    if ( !FindNextFileW(hFindFile, &v100) )
      goto LABEL_113;
  }
  if ( v11 )
  {
    v37 = (*(__int64 (__fastcall **)(struct UnBCL::Directory::IDeleteDelegate *, _QWORD, _QWORD))(*(_QWORD *)v11 + 80LL))(
            v11,
            (*(_QWORD **)((char *)v84 + *(int *)(v83 + 4)))[2],
            v100.dwFileAttributes)
        - 1;
    if ( v37 )
    {
      v38 = v37 - 1;
      if ( v38 )
      {
        if ( v38 == 1 )
        {
          v26 = 995;
          goto LABEL_69;
        }
        goto LABEL_77;
      }
      *v10 = 774;
    }
    LODWORD(v39) = 0;
LABEL_109:
    if ( !v26 && (_DWORD)v39 )
      *v10 = v39;
    goto LABEL_112;
  }
LABEL_77:
  v71 = 1;
  v69 = 1;
  v76 = 1;
  BytesReturned = 0;
  v62 = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v67, 0);
  if ( !v11 )
    goto LABEL_94;
  v66 = 0;
  if ( !(*(unsigned int (__fastcall **)(struct UnBCL::Directory::IDeleteDelegate *))(*(_QWORD *)v11 + 64LL))(v11) )
    goto LABEL_94;
  try
  {
    UnBCL::File::DeleteInternal(*(LPCWSTR **)((char *)v84 + *(int *)(v83 + 4)), 1);
  }
  catch ( UnBCL::Win32Exception *v95 )
  {
    v52 = v95;
    if ( v95[14] )
      v53 = v95[14];
    else
      v53 = 31;
    v62 = v53;
    if ( v53 == 681 )
    {
      v66 = 1;
      v54 = (UnBCL::String *)(*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v95 + 72LL))(v95);
      if ( v54 )
      {
        v54 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v55 = v54;
        v91[0] = v54;
        if ( v54 )
        {
          v56 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v52 + 72LL))(v52);
          v54 = (UnBCL::String *)UnBCL::String::String(v55, v56);
        }
      }
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v87, v54);
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v67, v88);
      v87 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v87);
    }
    else
    {
      v76 = 0;
    }
    (**(void (__fastcall ***)(_DWORD *, __int64))v52)(v52, 1);
    v11 = v79;
    if ( v66 )
    {
      v40 = 0;
      if ( v68 )
        v40 = *(_QWORD *)(v68 + 16);
      v41 = (*(__int64 (__fastcall **)(struct UnBCL::Directory::IDeleteDelegate *, _QWORD, __int64))(*(_QWORD *)v79 + 72LL))(
              v79,
              (*(_QWORD **)((char *)v84 + *(int *)(v83 + 4)))[2],
              v40)
          - 1;
      a1 = v73;
      v10 = v72;
      if ( v41 )
      {
        v42 = v41 - 1;
        if ( v42 )
        {
          if ( v42 == 1 )
          {
            v26 = 995;
            if ( v62 )
              v26 = v62;
            v64 = v26;
            BytesReturned = 1;
            v69 = v76;
            goto LABEL_94;
          }
          goto LABEL_92;
        }
        v71 = 0;
        v69 = 0;
        *v72 = 774;
      }
      else
      {
        v71 = 0;
        v69 = 0;
        v62 = 0;
      }
LABEL_93:
      v26 = v64;
      goto LABEL_94;
    }
    a1 = v73;
    v10 = v72;
LABEL_92:
    v69 = v76;
    goto LABEL_93;
  }
LABEL_94:
  v67 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v67);
  if ( BytesReturned )
    goto LABEL_69;
  if ( v69 )
  {
    try
    {
      UnBCL::File::DeleteInternal(*(LPCWSTR **)((char *)v84 + *(int *)(v83 + 4)), 0);
    }
    catch ( UnBCL::Win32Exception *v96 )
    {
      if ( *(_DWORD *)(v96 + 56) )
        v62 = *(_DWORD *)(v96 + 56);
      else
        v62 = 31;
      (**(void (__fastcall ***)(__int64, __int64))v96)(v96, 1);
      v26 = v64;
      a1 = v73;
      v39 = v62;
      v10 = v72;
      v11 = v79;
      goto LABEL_97;
    }
  }
  v39 = v62;
LABEL_97:
  if ( !v11 )
    goto LABEL_109;
  if ( !v71 )
    goto LABEL_108;
  v43 = (*(__int64 (__fastcall **)(struct UnBCL::Directory::IDeleteDelegate *, _QWORD, _QWORD, __int64))(*(_QWORD *)v11 + 88LL))(
          v11,
          (*(_QWORD **)((char *)v84 + *(int *)(v83 + 4)))[2],
          v100.dwFileAttributes,
          v39);
  if ( !v43 )
  {
    LODWORD(v39) = 0;
    goto LABEL_108;
  }
  v44 = v43 - 2;
  if ( !v44 )
  {
    LODWORD(v39) = v62;
    v64 = v26;
    if ( !v62 )
      LODWORD(v39) = 774;
    goto LABEL_109;
  }
  if ( v44 != 1 )
  {
    LODWORD(v39) = v62;
LABEL_108:
    v64 = v26;
    goto LABEL_109;
  }
  v26 = 995;
  if ( v62 )
    v26 = v62;
LABEL_69:
  v84[0] = (struct UnBCL::String *)&UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v84);
LABEL_113:
  FindClose(hFindFile);
  if ( !v26 )
  {
    v45 = GetLastError();
    if ( v45 )
    {
      if ( v45 != 18 )
        *v10 = v45;
    }
  }
LABEL_117:
  v89 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v89);
  UnBCL::String::~String((UnBCL::String *)v92);
  lpszFilePath = (LPWSTR)hObject;
  if ( v26 || v78 )
    goto LABEL_136;
LABEL_119:
  v63 = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v67, 0);
  if ( v11 )
  {
    v66 = 1;
    BytesReturned = 0;
    if ( (*(unsigned int (__fastcall **)(struct UnBCL::Directory::IDeleteDelegate *))(*(_QWORD *)v11 + 64LL))(v11) )
    {
      try
      {
        UnBCL::Directory::DeleteSegment(a1, 1);
      }
      catch ( UnBCL::Win32Exception *v97 )
      {
        v57 = v97;
        if ( v97[14] )
          v58 = v97[14];
        else
          v58 = 31;
        v63 = v58;
        if ( v58 == 681 )
        {
          BytesReturned = 1;
          v59 = (UnBCL::String *)(*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v97 + 72LL))(v97);
          if ( v59 )
          {
            v59 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
            v60 = v59;
            v91[0] = v59;
            if ( v59 )
            {
              v61 = (const struct UnBCL::String *)(*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v57 + 72LL))(v57);
              v59 = (UnBCL::String *)UnBCL::String::String(v60, v61);
            }
          }
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v87, v59);
          UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v67, v88);
          v87 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
          UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v87);
        }
        else
        {
          v66 = 0;
        }
        (**(void (__fastcall ***)(_DWORD *, __int64))v57)(v57, 1);
        v11 = v79;
        if ( !BytesReturned )
        {
          a1 = v73;
          goto LABEL_142;
        }
        v47 = 0;
        if ( v68 )
          v47 = *(_QWORD *)(v68 + 16);
        a1 = v73;
        v48 = (*(__int64 (__fastcall **)(struct UnBCL::Directory::IDeleteDelegate *, const wchar_t *, __int64))(*(_QWORD *)v79 + 72LL))(
                v79,
                v73[2],
                v47)
            - 1;
        if ( !v48 )
        {
          v46 = 0;
          v26 = 0;
          v10 = v72;
          goto LABEL_133;
        }
        v49 = v48 - 1;
        if ( !v49 )
        {
          v10 = v72;
          *v72 = 774;
          v26 = 0;
LABEL_132:
          v46 = v63;
          goto LABEL_133;
        }
        if ( v49 == 1 )
        {
          v26 = 995;
          if ( v63 )
            v26 = v63;
          goto LABEL_135;
        }
LABEL_142:
        v26 = 0;
        v10 = v72;
        if ( !v66 )
        {
          v46 = v63;
          goto LABEL_145;
        }
      }
    }
  }
  try
  {
    UnBCL::Directory::DeleteSegment(a1, 0);
  }
  catch ( UnBCL::Win32Exception *v98 )
  {
    if ( *(_DWORD *)(v98 + 56) )
      v63 = *(_DWORD *)(v98 + 56);
    else
      v63 = 31;
    (**(void (__fastcall ***)(__int64, __int64))v98)(v98, 1);
    v26 = 0;
    a1 = v73;
    v46 = v63;
    v10 = v72;
    v11 = v79;
    goto LABEL_144;
  }
  v46 = v63;
LABEL_144:
  if ( !v11 )
    goto LABEL_133;
LABEL_145:
  v50 = (*(__int64 (__fastcall **)(struct UnBCL::Directory::IDeleteDelegate *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v11 + 88LL))(
          v11,
          a1[2],
          dwFileAttributes,
          v46);
  if ( !v50 )
  {
    v46 = 0;
LABEL_133:
    if ( v46 )
      *v10 = v46;
    goto LABEL_135;
  }
  v51 = v50 - 2;
  if ( !v51 )
  {
    v46 = v63;
    if ( !v63 )
      v46 = 774;
    goto LABEL_133;
  }
  if ( v51 != 1 )
    goto LABEL_132;
  v26 = 995;
  if ( v63 )
    v26 = v63;
LABEL_135:
  v67 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v67);
LABEL_136:
  if ( !v86 )
  {
    if ( lpszFilePath )
      operator delete[](lpszFilePath);
  }
  v74 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v74);
  return v26;
}

```

## disassembly

```asm
0x180029b30  push    rbx
0x180029b32  push    rsi
0x180029b33  push    rdi
0x180029b34  push    r12
0x180029b36  push    r13
0x180029b38  push    r14
0x180029b3a  push    r15
0x180029b3c  sub     rsp, 630h
0x180029b43  mov     [rsp+668h+var_530], 0FFFFFFFFFFFFFFFEh
0x180029b4f  mov     rax, cs:__security_cookie
0x180029b56  xor     rax, rsp
0x180029b59  mov     [rsp+668h+var_48], rax
0x180029b61  mov     r12d, r9d
0x180029b64  mov     ebx, r8d
0x180029b67  mov     r13, rcx
0x180029b6a  mov     [rsp+668h+var_5B0], edx
0x180029b71  mov     rax, [rsp+668h+arg_20]
0x180029b79  mov     [rsp+668h+var_580], rax
0x180029b81  mov     r15, [rsp+668h+arg_28]
0x180029b89  mov     [rsp+668h+var_5F8], r15
0x180029b8e  mov     r14, [rsp+668h+arg_30]
0x180029b96  mov     [rsp+668h+var_5C0], r14
0x180029b9e  xor     edx, edx
0x180029ba0  lea     rcx, [rsp+668h+var_5E8]
0x180029ba8  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180029bad  nop
0x180029bae  cmp     ebx, 0FFFFFFFFh
0x180029bb1  jnz     loc_180029E6A
0x180029bb7  mov     edi, 1
0x180029bbc  mov     rcx, r13; struct UnBCL::String *
0x180029bbf  call    ?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x180029bc4  mov     rdx, rax
0x180029bc7  lea     rcx, [rsp+668h+var_618]
0x180029bcc  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180029bd1  nop
0x180029bd2  mov     rdx, [rsp+668h+var_610]
0x180029bd7  lea     rcx, [rsp+668h+var_5E8]
0x180029bdf  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x180029be4  nop
0x180029be5  lea     rsi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x180029bec  mov     [rsp+668h+var_618], rsi
0x180029bf1  lea     rcx, [rsp+668h+var_618]
0x180029bf6  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180029bfb  mov     edx, edi; int
0x180029bfd  mov     rcx, [rsp+668h+var_5E0]; struct UnBCL::String *
0x180029c05  call    ?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x180029c0a  mov     rdx, rax
0x180029c0d  lea     rcx, [rsp+668h+var_618]
0x180029c12  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180029c17  nop
0x180029c18  mov     rdx, [rsp+668h+var_610]
0x180029c1d  lea     rcx, [rsp+668h+var_5E8]
0x180029c25  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x180029c2a  nop
0x180029c2b  mov     [rsp+668h+var_618], rsi
0x180029c30  lea     rcx, [rsp+668h+var_618]
0x180029c35  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180029c3a  mov     r13, [rsp+668h+var_5E0]
0x180029c42  lea     edx, [rdi+5Bh]; unsigned __int16
0x180029c45  mov     rcx, r13; this
0x180029c48  call    ?EndsWith@String@UnBCL@@QEBAHG@Z; UnBCL::String::EndsWith(ushort)
0x180029c4d  xor     ebx, ebx
0x180029c4f  test    eax, eax
0x180029c51  jz      loc_180029CF0
0x180029c57  mov     rcx, r13; struct UnBCL::String *
0x180029c5a  call    ?GetPathRoot@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetPathRoot(UnBCL::String const *)
0x180029c5f  mov     rdx, rax
0x180029c62  lea     rcx, [rsp+668h+var_558]
0x180029c6a  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180029c6f  nop
0x180029c70  mov     rdx, [r13+10h]; String2
0x180029c74  mov     rcx, [rsp+668h+var_550]
0x180029c7c  mov     rcx, [rcx+10h]; String1
0x180029c80  call    cs:__imp__wcsicmp
0x180029c86  test    eax, eax
0x180029c88  jnz     short loc_180029C8E
0x180029c8a  mov     edi, ebx
0x180029c8c  jmp     short loc_180029CDB
0x180029c8e  mov     rax, [r13+10h]
0x180029c92  mov     r8d, [rax-10h]
0x180029c96  dec     r8d; int
0x180029c99  xor     edx, edx; int
0x180029c9b  mov     rcx, r13; this
0x180029c9e  call    ?Substring@String@UnBCL@@QEBAPEAV12@HH@Z; UnBCL::String::Substring(int,int)
0x180029ca3  mov     rdx, rax
0x180029ca6  lea     rcx, [rsp+668h+var_618]
0x180029cab  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180029cb0  nop
0x180029cb1  mov     rdx, [rsp+668h+var_610]
0x180029cb6  lea     rcx, [rsp+668h+var_5E8]
0x180029cbe  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x180029cc3  nop
0x180029cc4  mov     [rsp+668h+var_618], rsi
0x180029cc9  lea     rcx, [rsp+668h+var_618]
0x180029cce  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180029cd3  mov     r13, [rsp+668h+var_5E0]
0x180029cdb  mov     [rsp+668h+var_558], rsi
0x180029ce3  lea     rcx, [rsp+668h+var_558]
0x180029ceb  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180029cf0  mov     rcx, r13; struct UnBCL::String *
0x180029cf3  call    ?CheckPathTooLong@Path@UnBCL@@KAXPEBVString@2@@Z; UnBCL::Path::CheckPathTooLong(UnBCL::String const *)
0x180029cf8  test    edi, edi
0x180029cfa  jz      loc_180029D85
0x180029d00  xor     edx, edx; Val
0x180029d02  mov     r8d, 250h; Size
0x180029d08  lea     rcx, [rsp+668h+FindFileData]; void *
0x180029d10  call    memset_0
0x180029d15  lea     rdx, [rsp+668h+FindFileData]; lpFindFileData
0x180029d1d  mov     rcx, [r13+10h]; lpFileName
0x180029d21  call    cs:__imp_FindFirstFileW
0x180029d27  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029d2b  jnz     short loc_180029D5A
0x180029d2d  call    cs:__imp_GetLastError
0x180029d33  lea     ecx, [rax-2]
0x180029d36  cmp     ecx, 1
0x180029d39  jbe     short loc_180029D3E
0x180029d3b  mov     [r15], eax
0x180029d3e  mov     [rsp+668h+var_5E8], rsi
0x180029d46  lea     rcx, [rsp+668h+var_5E8]
0x180029d4e  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180029d53  xor     eax, eax
0x180029d55  jmp     loc_18002A752
0x180029d5a  mov     rcx, rax; hFindFile
0x180029d5d  call    cs:__imp_FindClose
0x180029d63  mov     eax, [rsp+668h+FindFileData.dwFileAttributes]
0x180029d6a  mov     [rsp+668h+var_604], eax
0x180029d6e  and     eax, 400h
0x180029d73  neg     eax
0x180029d75  sbb     r12d, r12d
0x180029d78  and     r12d, [rsp+668h+FindFileData.dwReserved0]
0x180029d80  jmp     loc_180029E77
0x180029d85  mov     rcx, [r13+10h]; lpFileName
0x180029d89  call    cs:__imp_GetFileAttributesW
0x180029d8f  mov     [rsp+668h+var_604], eax
0x180029d93  cmp     eax, 0FFFFFFFFh
0x180029d96  jz      short loc_180029D2D
0x180029d98  bt      eax, 0Ah
0x180029d9c  jnb     loc_180029E77
0x180029da2  mov     rcx, [r13+10h]; lpFileName
0x180029da6  call    ?pOpenFile@@YAPEAXPEBG@Z; pOpenFile(ushort const *)
0x180029dab  mov     rdi, rax
0x180029dae  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029db2  jz      loc_180029D2D
0x180029db8  mov     [rsp+668h+BytesReturned], ebx
0x180029dbc  mov     ecx, 4000h; unsigned __int64
0x180029dc1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180029dc6  mov     r12, rax
0x180029dc9  mov     [rsp+668h+hObject], rax
0x180029dd1  mov     rcx, rdi; hDevice
0x180029dd4  test    rax, rax
0x180029dd7  jnz     short loc_180029DEB
0x180029dd9  call    cs:__imp_CloseHandle
0x180029ddf  mov     dword ptr [r15], 8
0x180029de6  jmp     loc_180029D3E
0x180029deb  mov     [rsp+668h+lpOverlapped], rbx; lpOverlapped
0x180029df0  lea     rax, [rsp+668h+BytesReturned]
0x180029df5  mov     [rsp+668h+lpBytesReturned], rax; lpBytesReturned
0x180029dfa  mov     [rsp+668h+nOutBufferSize], 4000h; nOutBufferSize
0x180029e02  mov     [rsp+668h+lpOutBuffer], r12; lpOutBuffer
0x180029e07  xor     r9d, r9d; nInBufferSize
0x180029e0a  xor     r8d, r8d; lpInBuffer
0x180029e0d  mov     edx, 900A8h; dwIoControlCode
0x180029e12  call    cs:__imp_DeviceIoControl
0x180029e18  test    eax, eax
0x180029e1a  jz      short loc_180029E22
0x180029e1c  mov     r12d, [r12]
0x180029e20  jmp     short loc_180029E36
0x180029e22  call    cs:__imp_GetLastError
0x180029e28  mov     [rsp+668h+var_61C], eax
0x180029e2c  cmp     eax, 1126h
0x180029e31  jnz     short loc_180029E4F
0x180029e33  mov     r12d, ebx
0x180029e36  mov     rcx, rdi; hObject
0x180029e39  call    cs:__imp_CloseHandle
0x180029e3f  mov     rcx, [rsp+668h+hObject]
0x180029e47  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180029e4d  jmp     short loc_180029E77
0x180029e4f  mov     rcx, rdi; hObject
0x180029e52  call    cs:__imp_CloseHandle
0x180029e58  mov     rcx, r12
0x180029e5b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180029e61  mov     eax, [rsp+668h+var_61C]
0x180029e65  jmp     loc_180029D3B
0x180029e6a  mov     [rsp+668h+var_604], ebx
0x180029e6e  lea     rsi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x180029e75  xor     ebx, ebx
0x180029e77  mov     [rsp+668h+var_5F0], r13
0x180029e7c  test    r14, r14
0x180029e7f  jz      short loc_180029EDB
0x180029e81  mov     rax, [r14]
0x180029e84  mov     r8d, [rsp+668h+var_604]
0x180029e89  mov     rdx, [r13+10h]
0x180029e8d  mov     rcx, r14
0x180029e90  mov     rax, [rax+50h]
0x180029e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e99  sub     eax, 1
0x180029e9c  jz      loc_180029D3E
0x180029ea2  sub     eax, 1
0x180029ea5  jz      short loc_180029EB4
0x180029ea7  cmp     eax, 1
0x180029eaa  jnz     short loc_180029EDB
0x180029eac  mov     r12d, 3E3h
0x180029eb2  jmp     short loc_180029EBE
0x180029eb4  mov     dword ptr [r15], 306h
0x180029ebb  mov     r12d, ebx
0x180029ebe  mov     [rsp+668h+var_5E8], rsi
0x180029ec6  lea     rcx, [rsp+668h+var_5E8]
0x180029ece  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180029ed3  mov     eax, r12d
0x180029ed6  jmp     loc_18002A752
0x180029edb  mov     edi, ebx
0x180029edd  mov     [rsp+668h+var_624], ebx
0x180029ee1  mov     rax, [rsp+668h+var_580]
0x180029ee9  mov     [rsp+668h+lpszFilePath], rax
0x180029ef1  cmp     [rsp+668h+var_5B0], ebx
0x180029ef8  jz      loc_18002A61A
0x180029efe  mov     eax, [rsp+668h+var_604]
0x180029f02  and     eax, 400h
0x180029f07  mov     [rsp+668h+BytesReturned], eax
0x180029f0b  jz      short loc_180029F30
0x180029f0d  test    r12d, r12d
0x180029f10  jns     loc_18002A61A
0x180029f16  cmp     r12d, 0A0000003h
0x180029f1d  jz      loc_18002A61A
0x180029f23  cmp     r12d, 0A000000Ch
0x180029f2a  jz      loc_18002A61A
0x180029f30  mov     [rsp+668h+var_5C8], ebx
0x180029f37  test    r14, r14
0x180029f3a  jz      loc_18002A032
0x180029f40  mov     rax, [r14]
0x180029f43  mov     rcx, r14
0x180029f46  mov     rax, [rax+40h]
0x180029f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f4f  test    eax, eax
0x180029f51  jz      loc_18002A032
0x180029f57  cmp     [rsp+668h+var_580], rbx
0x180029f5f  jnz     short loc_180029F7C
0x180029f61  mov     ecx, 10000h; unsigned __int64
0x180029f66  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180029f6b  mov     [rsp+668h+lpszFilePath], rax
0x180029f73  test    rax, rax
0x180029f76  jz      loc_18002A855
0x180029f7c  mov     rcx, [r13+10h]; lpFileName
0x180029f80  call    ?pOpenFile@@YAPEAXPEBG@Z; pOpenFile(ushort const *)
0x180029f85  mov     [rsp+668h+hObject], rax
0x180029f8d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029f91  jz      loc_18002A032
0x180029f97  mov     [rsp+668h+var_600], ebx
0x180029f9b  xor     r9d, r9d; dwFlags
0x180029f9e  mov     r8d, 7FFFh; cchFilePath
0x180029fa4  mov     r12, [rsp+668h+lpszFilePath]
0x180029fac  mov     rdx, r12; lpszFilePath
0x180029faf  mov     rcx, rax; hFile
0x180029fb2  call    cs:__imp_GetFinalPathNameByHandleW
0x180029fb8  dec     eax
0x180029fba  cmp     eax, 7FFEh
0x180029fbf  ja      short loc_180029FD9
0x180029fc1  mov     rdx, r12; String2
0x180029fc4  mov     rcx, [r13+10h]; String1
0x180029fc8  call    cs:__imp__wcsicmp
0x180029fce  mov     ecx, ebx
0x180029fd0  test    eax, eax
0x180029fd2  setnz   cl
0x180029fd5  mov     [rsp+668h+var_600], ecx
0x180029fd9  mov     rcx, [rsp+668h+hObject]; hObject
0x180029fe1  call    cs:__imp_CloseHandle
0x180029fe7  cmp     [rsp+668h+var_600], ebx
0x180029feb  jz      short loc_18002A032
0x180029fed  mov     rax, [r14]
0x180029ff0  mov     r8, r12
0x180029ff3  mov     rdx, [r13+10h]
0x180029ff7  mov     rcx, r14
0x180029ffa  mov     rax, [rax+48h]
0x180029ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a003  mov     [rsp+668h+var_5C8], eax
0x18002a00a  test    eax, eax
0x18002a00c  jz      short loc_18002A032
0x18002a00e  cmp     eax, 3
0x18002a011  jnz     short loc_18002A01D
0x18002a013  mov     edi, 2A9h
0x18002a018  jmp     loc_18002A71A
0x18002a01d  cmp     eax, 2
0x18002a020  jnz     loc_18002A71A
0x18002a026  mov     dword ptr [r15], 2A9h
0x18002a02d  jmp     loc_18002A71A
0x18002a032  mov     rax, [rsp+668h+lpszFilePath]
0x18002a03a  mov     [rsp+668h+hObject], rax
0x18002a042  xor     edx, edx; Val
0x18002a044  mov     r8d, 250h; Size
0x18002a04a  lea     rcx, [rsp+668h+var_4E8]; void *
0x18002a052  call    memset_0
0x18002a057  mov     edx, 5Ch ; '\'; unsigned __int16
0x18002a05c  lea     r8d, [rdx-5Bh]; int
0x18002a060  lea     rcx, [rsp+668h+var_548]; this
0x18002a068  call    ??0String@UnBCL@@QEAA@GH@Z; UnBCL::String::String(ushort,int)
0x18002a06d  nop
0x18002a06e  xor     edx, edx
0x18002a070  lea     rcx, [rsp+668h+var_568]
0x18002a078  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002a07d  nop
  ... truncated ...
```
