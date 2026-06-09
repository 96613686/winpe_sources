# UnBCL::Directory::DeleteInternal(UnBCL::String const *,int,ulong,ulong)

- ea: `0x18002a870`
- end: `0x18002b2df`
- name: `?DeleteInternal@Directory@UnBCL@@CAXPEBVString@2@HKK@Z`
- size: `2671`
- prototype: `void __fastcall(const struct UnBCL::String *, int, DWORD dwFileAttributes, signed int)`
- caller_count: `3`
- callee_count: `29`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180029ab0`
- `0x18002a870`
- `0x18002b2f0`

## callees

- `0x1800015ac`
- `0x18000225c`
- `0x180002ca0`
- `0x180002f50`
- `0x180002f90`
- `0x180009e7c`
- `0x180011570`
- `0x18002a870`
- `0x180031dd0`
- `0x180031e40`
- `0x18003b740`
- `0x1800477d0`
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
- `0x180064340`
- `0x180068fe6`
- `0x180069020`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002a987`
- `msvcrt!_wcsicmp` at `0x18002a987`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ab6b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002b199`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ab6b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002b199`
- `KERNEL32!CloseHandle` at `0x18002ab62`
- `KERNEL32!CloseHandle` at `0x18002b12f`
- `KERNEL32!CloseHandle` at `0x18002b18b`
- `KERNEL32!CloseHandle` at `0x18002ab62`
- `KERNEL32!CloseHandle` at `0x18002b12f`
- `KERNEL32!CloseHandle` at `0x18002b18b`
- `KERNEL32!GetLastError` at `0x18002aa2a`
- `KERNEL32!GetLastError` at `0x18002aa8d`
- `KERNEL32!GetLastError` at `0x18002aac3`
- `KERNEL32!GetLastError` at `0x18002ab3d`
- `KERNEL32!GetLastError` at `0x18002acc1`
- `KERNEL32!GetLastError` at `0x18002af62`
- `KERNEL32!GetLastError` at `0x18002afdc`
- `KERNEL32!GetLastError` at `0x18002aa2a`
- `KERNEL32!GetLastError` at `0x18002aa8d`
- `KERNEL32!GetLastError` at `0x18002aac3`
- `KERNEL32!GetLastError` at `0x18002ab3d`
- `KERNEL32!GetLastError` at `0x18002acc1`
- `KERNEL32!GetLastError` at `0x18002af62`
- `KERNEL32!GetLastError` at `0x18002afdc`
- `KERNEL32!FindFirstFileW` at `0x18002aa1e`
- `KERNEL32!FindFirstFileW` at `0x18002aca9`
- `KERNEL32!FindFirstFileW` at `0x18002ad0c`
- `KERNEL32!FindFirstFileW` at `0x18002aa1e`
- `KERNEL32!FindFirstFileW` at `0x18002aca9`
- `KERNEL32!FindFirstFileW` at `0x18002ad0c`
- `KERNEL32!FindNextFileW` at `0x18002af54`
- `KERNEL32!FindNextFileW` at `0x18002af54`
- `KERNEL32!DeviceIoControl` at `0x18002ab25`
- `KERNEL32!DeviceIoControl` at `0x18002ab25`
- `KERNEL32!RemoveDirectoryW` at `0x18002afce`
- `KERNEL32!RemoveDirectoryW` at `0x18002afce`
- `KERNEL32!FindClose` at `0x18002aa46`
- `KERNEL32!FindClose` at `0x18002af6f`
- `KERNEL32!FindClose` at `0x18002aa46`
- `KERNEL32!FindClose` at `0x18002af6f`
- `KERNEL32!GetFileAttributesW` at `0x18002aa7c`
- `KERNEL32!GetFileAttributesW` at `0x18002aed6`
- `KERNEL32!GetFileAttributesW` at `0x18002aa7c`
- `KERNEL32!GetFileAttributesW` at `0x18002aed6`
- `KERNEL32!SetFileAttributesW` at `0x18002aeef`
- `KERNEL32!SetFileAttributesW` at `0x18002afc4`
- `KERNEL32!SetFileAttributesW` at `0x18002aeef`
- `KERNEL32!SetFileAttributesW` at `0x18002afc4`

## string_xrefs

- `0x18002b011`: `void __cdecl UnBCL::Directory::DeleteInternal(const class UnBCL::String *,int,unsigned long,unsigned long)`
- `0x18002b061`: `void __cdecl UnBCL::Directory::DeleteInternal(const class UnBCL::String *,int,unsigned long,unsigned long)`
- `0x18002b0b1`: `void __cdecl UnBCL::Directory::DeleteInternal(const class UnBCL::String *,int,unsigned long,unsigned long)`
- `0x18002b100`: `void __cdecl UnBCL::Directory::DeleteInternal(const class UnBCL::String *,int,unsigned long,unsigned long)`
- `0x18002b15c`: `void __cdecl UnBCL::Directory::DeleteInternal(const class UnBCL::String *,int,unsigned long,unsigned long)`
- `0x18002b1c5`: `void __cdecl UnBCL::Directory::DeleteInternal(const class UnBCL::String *,int,unsigned long,unsigned long)`
- `0x18002b226`: `void __cdecl UnBCL::Directory::DeleteInternal(const class UnBCL::String *,int,unsigned long,unsigned long)`
- `0x18002b252`: `void __cdecl UnBCL::Directory::DeleteInternal(const class UnBCL::String *,int,unsigned long,unsigned long)`
- `0x18002b2b3`: `void __cdecl UnBCL::Directory::DeleteInternal(const class UnBCL::String *,int,unsigned long,unsigned long)`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
void __fastcall UnBCL::Directory::DeleteInternal(
        const struct UnBCL::String *a1,
        int a2,
        DWORD dwFileAttributes,
        signed int a4)
{
  int v7; // esi
  struct UnBCL::String *FullPath; // rax
  struct UnBCL::String *v9; // rax
  const wchar_t **v10; // rdi
  __int64 v11; // rbx
  struct UnBCL::String *PathRoot; // rax
  struct UnBCL::String *v13; // rax
  HANDLE FirstFileW; // rax
  DWORD LastError; // edi
  DWORD FileAttributesW; // eax
  DWORD v17; // edi
  HANDLE v18; // r15
  DWORD v19; // edi
  void *lpOutBuffer; // rax
  void *v21; // r13
  int v22; // eax
  const unsigned __int16 *v23; // rcx
  struct UnBCL::String *v24; // rax
  HANDLE v25; // r15
  DWORD v26; // eax
  DWORD v27; // r13d
  __int64 v28; // r13
  const struct UnBCL::String *v29; // rax
  struct UnBCL::String *v30; // rax
  struct UnBCL::String *v31; // rax
  DWORD v32; // eax
  DWORD v33; // r15d
  DWORD v34; // esi
  void *v35; // rax
  void *v36; // rax
  void *v37; // rax
  void *v38; // rax
  void *v39; // rax
  void *v40; // rax
  void *v41; // rdi
  const struct UnBCL::String *v42; // rax
  void *v43; // rdi
  const struct UnBCL::String *v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  HANDLE hObject; // [rsp+40h] [rbp-608h] BYREF
  struct UnBCL::String *v48; // [rsp+48h] [rbp-600h]
  DWORD dwMessageId[2]; // [rsp+50h] [rbp-5F8h]
  DWORD v50; // [rsp+58h] [rbp-5F0h]
  int v51; // [rsp+5Ch] [rbp-5ECh]
  void **v52; // [rsp+60h] [rbp-5E8h] BYREF
  struct UnBCL::String *v53; // [rsp+68h] [rbp-5E0h]
  int v54; // [rsp+70h] [rbp-5D8h]
  DWORD BytesReturned[2]; // [rsp+78h] [rbp-5D0h] BYREF
  void *v56[2]; // [rsp+80h] [rbp-5C8h] BYREF
  void **v57; // [rsp+90h] [rbp-5B8h] BYREF
  __int64 v58; // [rsp+98h] [rbp-5B0h]
  __int64 v59; // [rsp+A0h] [rbp-5A8h] BYREF
  __int64 v60; // [rsp+A8h] [rbp-5A0h] BYREF
  __int64 v61; // [rsp+B0h] [rbp-598h] BYREF
  __int64 v62; // [rsp+B8h] [rbp-590h] BYREF
  __int64 v63; // [rsp+C0h] [rbp-588h] BYREF
  __int64 v64; // [rsp+C8h] [rbp-580h] BYREF
  __int64 v65; // [rsp+D0h] [rbp-578h] BYREF
  __int64 v66; // [rsp+D8h] [rbp-570h] BYREF
  __int64 pExceptionObject; // [rsp+E0h] [rbp-568h] BYREF
  _BYTE v68[16]; // [rsp+E8h] [rbp-560h] BYREF
  unsigned __int16 *v69; // [rsp+F8h] [rbp-550h]
  _BYTE v70[8]; // [rsp+100h] [rbp-548h] BYREF
  __int64 v71; // [rsp+108h] [rbp-540h]
  struct UnBCL::String *v72[3]; // [rsp+110h] [rbp-538h] BYREF
  __int64 v73; // [rsp+128h] [rbp-520h] BYREF
  __int64 v74; // [rsp+130h] [rbp-518h] BYREF
  _BYTE v75[24]; // [rsp+138h] [rbp-510h] BYREF
  _BYTE v76[32]; // [rsp+150h] [rbp-4F8h] BYREF
  struct _WIN32_FIND_DATAW v77; // [rsp+170h] [rbp-4D8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+3C0h] [rbp-288h] BYREF

  v72[2] = (struct UnBCL::String *)-2LL;
  v51 = a2;
  v54 = a2;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v52, 0);
  if ( dwFileAttributes == -1 )
  {
    v7 = 1;
    FullPath = UnBCL::Path::GetFullPath(a1);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&hObject, FullPath);
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v52, v48);
    hObject = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&hObject);
    v9 = UnBCL::Path::WithLongPrefix(v53, 1);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&hObject, v9);
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v52, v48);
    hObject = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&hObject);
    v10 = (const wchar_t **)v53;
    v11 = 0;
    if ( (unsigned int)UnBCL::String::EndsWith(v53, 0x5Cu) )
    {
      PathRoot = UnBCL::Path::GetPathRoot((const struct UnBCL::String *)v10);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v56, PathRoot);
      if ( _wcsicmp(*((const wchar_t **)v56[1] + 2), v10[2]) )
      {
        v13 = UnBCL::String::Substring((UnBCL::String *)v10, 0, *((_DWORD *)v10[2] - 4) - 1);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&hObject, v13);
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v52, v48);
        hObject = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&hObject);
        v10 = (const wchar_t **)v53;
      }
      else
      {
        v7 = 0;
      }
      v56[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v56);
    }
    UnBCL::Path::CheckPathTooLong((const struct UnBCL::String *)v10);
    if ( v7 )
    {
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      FirstFileW = FindFirstFileW(v10[2], &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        if ( LastError - 2 > 1 )
        {
          v36 = UnBCL::Object::operator new(0x40u);
          hObject = v36;
          if ( v36 )
            v11 = UnBCL::Win32Exception::Win32Exception((UnBCL::Win32Exception *)v36, LastError, a1);
          v59 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                  v11,
                  "void __cdecl UnBCL::Directory::DeleteInternal(const class UnBCL::String *,int,unsigned long,unsigned long)");
          throw (UnBCL::Win32Exception **)&v59;
        }
        goto LABEL_43;
      }
      FindClose(FirstFileW);
      dwFileAttributes = FindFileData.dwFileAttributes;
      v50 = FindFileData.dwFileAttributes;
      a4 = (FindFileData.dwFileAttributes & 0x400) != 0 ? FindFileData.dwReserved0 : 0;
    }
    else
    {
      FileAttributesW = GetFileAttributesW(v10[2]);
      dwFileAttributes = FileAttributesW;
      v50 = FileAttributesW;
      if ( FileAttributesW == -1 )
      {
        v17 = GetLastError();
        if ( v17 - 2 > 1 )
        {
          v37 = UnBCL::Object::operator new(0x40u);
          hObject = v37;
          if ( v37 )
            v11 = UnBCL::Win32Exception::Win32Exception((UnBCL::Win32Exception *)v37, v17, a1);
          v60 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                  v11,
                  "void __cdecl UnBCL::Directory::DeleteInternal(const class UnBCL::String *,int,unsigned long,unsigned long)");
          throw (UnBCL::Win32Exception **)&v60;
        }
        goto LABEL_43;
      }
      if ( (FileAttributesW & 0x400) != 0 )
      {
        v18 = pOpenFile(v10[2]);
        hObject = v18;
        if ( v18 == (HANDLE)-1LL )
        {
          v19 = GetLastError();
          if ( v19 - 2 > 1 )
          {
            v38 = UnBCL::Object::operator new(0x40u);
            hObject = v38;
            if ( v38 )
              v11 = UnBCL::Win32Exception::Win32Exception((UnBCL::Win32Exception *)v38, v19, a1);
            v61 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                    v11,
                    "void __cdecl UnBCL::Directory::DeleteInternal(const class UnBCL::String *,int,unsigned long,unsigned long)");
            throw (UnBCL::Win32Exception **)&v61;
          }
          goto LABEL_43;
        }
        BytesReturned[0] = 0;
        lpOutBuffer = operator new[](0x4000u);
        v56[0] = lpOutBuffer;
        if ( !lpOutBuffer )
        {
          CloseHandle(v18);
          v39 = UnBCL::Object::operator new(0x40u);
          hObject = v39;
          if ( v39 )
            v11 = UnBCL::Win32Exception::Win32Exception((UnBCL::Win32Exception *)v39, 8u, a1);
          v62 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                  v11,
                  "void __cdecl UnBCL::Directory::DeleteInternal(const class UnBCL::String *,int,unsigned long,unsigned long)");
          throw (UnBCL::Win32Exception **)&v62;
        }
        if ( DeviceIoControl(v18, 0x900A8u, 0, 0, lpOutBuffer, 0x4000u, BytesReturned, 0) )
        {
          v21 = v56[0];
          a4 = *(_DWORD *)v56[0];
        }
        else
        {
          dwMessageId[0] = GetLastError();
          if ( dwMessageId[0] != 4390 )
          {
            CloseHandle(v18);
            operator delete[](v56[0]);
            v40 = UnBCL::Object::operator new(0x40u);
            hObject = v40;
            if ( v40 )
              v11 = UnBCL::Win32Exception::Win32Exception((UnBCL::Win32Exception *)v40, dwMessageId[0], a1);
            v63 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                    v11,
                    "void __cdecl UnBCL::Directory::DeleteInternal(const class UnBCL::String *,int,unsigned long,unsigned long)");
            throw (UnBCL::Win32Exception **)&v63;
          }
          a4 = 0;
          v21 = v56[0];
        }
        CloseHandle(hObject);
        operator delete[](v21);
      }
    }
    v56[0] = v10;
  }
  else
  {
    v50 = dwFileAttributes;
    v10 = (const wchar_t **)a1;
    v56[0] = a1;
    v11 = 0;
  }
  if ( v51 )
  {
    dwMessageId[0] = dwFileAttributes & 0x400;
    if ( (dwFileAttributes & 0x400) == 0 || a4 < 0 && a4 != -1610612733 && a4 != -1610612724 )
    {
      memset_0(&v77, 0, sizeof(v77));
      UnBCL::String::String((UnBCL::String *)v68, 0x5Cu, 1);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v57, 0);
      v22 = UnBCL::String::EndsWith((UnBCL::String *)v10, v69, 1);
      v23 = v10[2];
      if ( v22 )
        v24 = UnBCL::String::Concat(v23, L"*");
      else
        v24 = UnBCL::String::Concat(v23, v69, L"*");
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&hObject, v24);
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(&v57, v48);
      hObject = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&hObject);
      v25 = FindFirstFileW(*(LPCWSTR *)(v58 + 16), &v77);
      *(_QWORD *)BytesReturned = v25;
      if ( v25 == (HANDLE)-1LL )
      {
        v26 = GetLastError();
        v27 = v26;
        if ( v26 - 2 <= 1 )
        {
          v57 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
          UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v57);
          UnBCL::String::~String((UnBCL::String *)v68);
          goto LABEL_43;
        }
        if ( v26 != 1920
          || !dwMessageId[0]
          || !(unsigned int)pRemoveReparsePointData(v10[2])
          || (v25 = FindFirstFileW(*(LPCWSTR *)(v58 + 16), &v77), *(_QWORD *)BytesReturned = v25, v25 == (HANDLE)-1LL) )
        {
          v41 = UnBCL::Object::operator new(0x40u);
          hObject = v41;
          if ( v41 )
          {
            v42 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->(&v57);
            v11 = UnBCL::Win32Exception::Win32Exception((UnBCL::Win32Exception *)v41, v27, v42);
          }
          v64 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                  v11,
                  "void __cdecl UnBCL::Directory::DeleteInternal(const class UnBCL::String *,int,unsigned long,unsigned long)");
          throw (UnBCL::Win32Exception **)&v64;
        }
      }
      v28 = 0;
      *(_QWORD *)dwMessageId = 0;
      do
      {
        if ( (v77.dwFileAttributes & 0x10) != 0 )
        {
          if ( v77.cFileName[0] != 46 || v77.cFileName[1] && (v77.cFileName[1] != 46 || v77.cFileName[2]) )
          {
            try
            {
              v29 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v76, v77.cFileName);
              v30 = UnBCL::Path::Combine((const struct UnBCL::String *)v10, v29);
              UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v70, v30);
              UnBCL::String::~String((UnBCL::String *)v76);
              UnBCL::Directory::DeleteInternal(
                *(struct UnBCL::String **)((char *)v72 + *(int *)(v71 + 4)),
                v51,
                v77.dwFileAttributes,
                (v77.dwFileAttributes & 0x400) != 0 ? v77.dwReserved0 : 0);
              v72[0] = (struct UnBCL::String *)&UnBCL::SmartPtr<UnBCL::String>::`vftable';
              UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v72);
            }
            catch ( UnBCL::Exception *v73 )
            {
              v45 = *(_QWORD *)dwMessageId;
              if ( !*(_QWORD *)dwMessageId )
                v45 = v73;
              *(_QWORD *)dwMessageId = v45;
              v11 = 0;
              dwFileAttributes = v50;
              v10 = (const wchar_t **)v56[0];
              v28 = v45;
              v25 = *(HANDLE *)BytesReturned;
              v51 = v54;
            }
          }
        }
        else
        {
          UnBCL::String::String((UnBCL::String *)v75, v77.cFileName);
          v31 = UnBCL::Path::Combine((const struct UnBCL::String *)v10, (const struct UnBCL::String *)v75);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&hObject, v31);
          v32 = GetFileAttributesW(*((LPCWSTR *)v48 + 2));
          if ( v32 != -1 )
          {
            SetFileAttributesW(*((LPCWSTR *)v48 + 2), v32 & 0xFFFFFFFE);
            try
            {
              UnBCL::File::DeleteInternal((LPCWSTR *)v48, 0);
            }
            catch ( UnBCL::Win32Exception *v74 )
            {
              v46 = *(_QWORD *)dwMessageId;
              if ( !*(_QWORD *)dwMessageId )
                v46 = v74;
              *(_QWORD *)dwMessageId = v46;
              v11 = 0;
              dwFileAttributes = v50;
              v10 = (const wchar_t **)v56[0];
              v28 = v46;
              v25 = *(HANDLE *)BytesReturned;
              v51 = v54;
            }
          }
          hObject = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
          UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&hObject);
          UnBCL::String::~String((UnBCL::String *)v75);
        }
      }
      while ( FindNextFileW(v25, &v77) );
      dwMessageId[0] = GetLastError();
      FindClose(v25);
      if ( v28 )
      {
        v65 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                v28,
                "void __cdecl UnBCL::Directory::DeleteInternal(const class UnBCL::String *,int,unsigned long,unsigned long)");
        throw (UnBCL::Exception **)&v65;
      }
      v33 = dwMessageId[0];
      if ( dwMessageId[0] && dwMessageId[0] != 18 )
      {
        v43 = UnBCL::Object::operator new(0x40u);
        hObject = v43;
        if ( v43 )
        {
          v44 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->(&v57);
          v11 = UnBCL::Win32Exception::Win32Exception((UnBCL::Win32Exception *)v43, v33, v44);
        }
        v66 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                v11,
                "void __cdecl UnBCL::Directory::DeleteInternal(const class UnBCL::String *,int,unsigned long,unsigned long)");
        throw (UnBCL::Win32Exception **)&v66;
      }
      v57 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v57);
      UnBCL::String::~String((UnBCL::String *)v68);
    }
  }
  if ( (dwFileAttributes & 1) != 0 )
    SetFileAttributesW(v10[2], dwFileAttributes & 0xFFFFFFFE);
  if ( !RemoveDirectoryW(v10[2]) )
  {
    v34 = GetLastError();
    if ( v34 == 2 )
      v34 = 3;
    v35 = UnBCL::Object::operator new(0x40u);
    hObject = v35;
    if ( v35 )
      v11 = UnBCL::Win32Exception::Win32Exception((UnBCL::Win32Exception *)v35, v34, (const struct UnBCL::String *)v10);
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v11,
                         "void __cdecl UnBCL::Directory::DeleteInternal(const class UnBCL::String *,int,unsigned long,unsigned long)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
LABEL_43:
  v52 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v52);
}

```

## disassembly

```asm
0x18002a870  mov     rax, rsp
0x18002a873  push    rsi
0x18002a874  push    rdi
0x18002a875  push    r13
0x18002a877  push    r14
0x18002a879  push    r15
0x18002a87b  sub     rsp, 620h
0x18002a882  mov     qword ptr [rax-528h], 0FFFFFFFFFFFFFFFEh
0x18002a88d  mov     [rax+20h], rbx
0x18002a891  mov     rax, cs:__security_cookie
0x18002a898  xor     rax, rsp
0x18002a89b  mov     [rsp+648h+var_38], rax
0x18002a8a3  mov     r15d, r9d
0x18002a8a6  mov     esi, r8d
0x18002a8a9  mov     [rsp+648h+var_5EC], edx
0x18002a8ad  mov     r13, rcx
0x18002a8b0  mov     [rsp+648h+var_5D8], edx
0x18002a8b4  xor     edx, edx
0x18002a8b6  lea     rcx, [rsp+648h+var_5E8]
0x18002a8bb  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002a8c0  nop
0x18002a8c1  cmp     esi, 0FFFFFFFFh
0x18002a8c4  jnz     loc_18002AB76
0x18002a8ca  mov     esi, 1
0x18002a8cf  mov     rcx, r13; struct UnBCL::String *
0x18002a8d2  call    ?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x18002a8d7  mov     rdx, rax
0x18002a8da  lea     rcx, [rsp+648h+hObject]
0x18002a8df  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002a8e4  nop
0x18002a8e5  mov     rdx, [rsp+648h+var_600]
0x18002a8ea  lea     rcx, [rsp+648h+var_5E8]
0x18002a8ef  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18002a8f4  nop
0x18002a8f5  lea     r14, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18002a8fc  mov     [rsp+648h+hObject], r14
0x18002a901  lea     rcx, [rsp+648h+hObject]
0x18002a906  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002a90b  mov     edx, esi; int
0x18002a90d  mov     rcx, [rsp+648h+var_5E0]; struct UnBCL::String *
0x18002a912  call    ?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x18002a917  mov     rdx, rax
0x18002a91a  lea     rcx, [rsp+648h+hObject]
0x18002a91f  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002a924  nop
0x18002a925  mov     rdx, [rsp+648h+var_600]
0x18002a92a  lea     rcx, [rsp+648h+var_5E8]
0x18002a92f  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18002a934  nop
0x18002a935  mov     [rsp+648h+hObject], r14
0x18002a93a  lea     rcx, [rsp+648h+hObject]
0x18002a93f  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002a944  mov     rdi, [rsp+648h+var_5E0]
0x18002a949  lea     edx, [rsi+5Bh]; unsigned __int16
0x18002a94c  mov     rcx, rdi; this
0x18002a94f  call    ?EndsWith@String@UnBCL@@QEBAHG@Z; UnBCL::String::EndsWith(ushort)
0x18002a954  xor     ebx, ebx
0x18002a956  test    eax, eax
0x18002a958  jz      loc_18002A9F1
0x18002a95e  mov     rcx, rdi; struct UnBCL::String *
0x18002a961  call    ?GetPathRoot@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetPathRoot(UnBCL::String const *)
0x18002a966  mov     rdx, rax
0x18002a969  lea     rcx, [rsp+648h+var_5C8]
0x18002a971  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002a976  nop
0x18002a977  mov     rdx, [rdi+10h]; String2
0x18002a97b  mov     rcx, [rsp+648h+var_5C0]
0x18002a983  mov     rcx, [rcx+10h]; String1
0x18002a987  call    cs:__imp__wcsicmp
0x18002a98d  test    eax, eax
0x18002a98f  jnz     short loc_18002A995
0x18002a991  mov     esi, ebx
0x18002a993  jmp     short loc_18002A9DC
0x18002a995  mov     rax, [rdi+10h]
0x18002a999  mov     r8d, [rax-10h]
0x18002a99d  dec     r8d; int
0x18002a9a0  xor     edx, edx; int
0x18002a9a2  mov     rcx, rdi; this
0x18002a9a5  call    ?Substring@String@UnBCL@@QEBAPEAV12@HH@Z; UnBCL::String::Substring(int,int)
0x18002a9aa  mov     rdx, rax
0x18002a9ad  lea     rcx, [rsp+648h+hObject]
0x18002a9b2  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002a9b7  nop
0x18002a9b8  mov     rdx, [rsp+648h+var_600]
0x18002a9bd  lea     rcx, [rsp+648h+var_5E8]
0x18002a9c2  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18002a9c7  nop
0x18002a9c8  mov     [rsp+648h+hObject], r14
0x18002a9cd  lea     rcx, [rsp+648h+hObject]
0x18002a9d2  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002a9d7  mov     rdi, [rsp+648h+var_5E0]
0x18002a9dc  mov     [rsp+648h+var_5C8], r14
0x18002a9e4  lea     rcx, [rsp+648h+var_5C8]
0x18002a9ec  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002a9f1  mov     rcx, rdi; struct UnBCL::String *
0x18002a9f4  call    ?CheckPathTooLong@Path@UnBCL@@KAXPEBVString@2@@Z; UnBCL::Path::CheckPathTooLong(UnBCL::String const *)
0x18002a9f9  test    esi, esi
0x18002a9fb  jz      short loc_18002AA78
0x18002a9fd  xor     edx, edx; Val
0x18002a9ff  mov     r8d, 250h; Size
0x18002aa05  lea     rcx, [rsp+648h+FindFileData]; void *
0x18002aa0d  call    memset_0
0x18002aa12  lea     rdx, [rsp+648h+FindFileData]; lpFindFileData
0x18002aa1a  mov     rcx, [rdi+10h]; lpFileName
0x18002aa1e  call    cs:__imp_FindFirstFileW
0x18002aa24  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002aa28  jnz     short loc_18002AA43
0x18002aa2a  call    cs:__imp_GetLastError
0x18002aa30  mov     edi, eax
0x18002aa32  lea     ecx, [rax-2]
0x18002aa35  cmp     ecx, 1
0x18002aa38  ja      loc_18002B03D
0x18002aa3e  jmp     loc_18002AD4A
0x18002aa43  mov     rcx, rax; hFindFile
0x18002aa46  call    cs:__imp_FindClose
0x18002aa4c  mov     esi, [rsp+648h+FindFileData.dwFileAttributes]
0x18002aa53  mov     [rsp+648h+var_5F0], esi
0x18002aa57  mov     eax, esi
0x18002aa59  and     eax, 400h
0x18002aa5e  neg     eax
0x18002aa60  sbb     r15d, r15d
0x18002aa63  and     r15d, [rsp+648h+FindFileData.dwReserved0]
0x18002aa6b  mov     [rsp+648h+var_5C8], rdi
0x18002aa73  jmp     loc_18002AB8E
0x18002aa78  mov     rcx, [rdi+10h]; lpFileName
0x18002aa7c  call    cs:__imp_GetFileAttributesW
0x18002aa82  mov     esi, eax
0x18002aa84  mov     [rsp+648h+var_5F0], eax
0x18002aa88  cmp     eax, 0FFFFFFFFh
0x18002aa8b  jnz     short loc_18002AAA6
0x18002aa8d  call    cs:__imp_GetLastError
0x18002aa93  mov     edi, eax
0x18002aa95  lea     ecx, [rax-2]
0x18002aa98  cmp     ecx, 1
0x18002aa9b  ja      loc_18002B08D
0x18002aaa1  jmp     loc_18002AD4A
0x18002aaa6  bt      eax, 0Ah
0x18002aaaa  jnb     short loc_18002AA6B
0x18002aaac  mov     rcx, [rdi+10h]; lpFileName
0x18002aab0  call    ?pOpenFile@@YAPEAXPEBG@Z; pOpenFile(ushort const *)
0x18002aab5  mov     r15, rax
0x18002aab8  mov     [rsp+648h+hObject], rax
0x18002aabd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002aac1  jnz     short loc_18002AADC
0x18002aac3  call    cs:__imp_GetLastError
0x18002aac9  mov     edi, eax
0x18002aacb  lea     ecx, [rax-2]
0x18002aace  cmp     ecx, 1
0x18002aad1  ja      loc_18002B0DD
0x18002aad7  jmp     loc_18002AD4A
0x18002aadc  mov     [rsp+648h+BytesReturned], ebx
0x18002aae0  mov     ecx, 4000h; unsigned __int64
0x18002aae5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002aaea  mov     [rsp+648h+var_5C8], rax
0x18002aaf2  test    rax, rax
0x18002aaf5  jz      loc_18002B12C
0x18002aafb  mov     [rsp+648h+lpOverlapped], rbx; lpOverlapped
0x18002ab00  lea     rcx, [rsp+648h+BytesReturned]
0x18002ab05  mov     [rsp+648h+lpBytesReturned], rcx; lpBytesReturned
0x18002ab0a  mov     [rsp+648h+nOutBufferSize], 4000h; nOutBufferSize
0x18002ab12  mov     [rsp+648h+lpOutBuffer], rax; lpOutBuffer
0x18002ab17  xor     r9d, r9d; nInBufferSize
0x18002ab1a  xor     r8d, r8d; lpInBuffer
0x18002ab1d  mov     edx, 900A8h; dwIoControlCode
0x18002ab22  mov     rcx, r15; hDevice
0x18002ab25  call    cs:__imp_DeviceIoControl
0x18002ab2b  test    eax, eax
0x18002ab2d  jz      short loc_18002AB3D
0x18002ab2f  mov     r13, [rsp+648h+var_5C8]
0x18002ab37  mov     r15d, [r13+0]
0x18002ab3b  jmp     short loc_18002AB5D
0x18002ab3d  call    cs:__imp_GetLastError
0x18002ab43  mov     [rsp+648h+dwMessageId], eax
0x18002ab47  cmp     eax, 1126h
0x18002ab4c  jnz     loc_18002B188
0x18002ab52  mov     r15d, ebx
0x18002ab55  mov     r13, [rsp+648h+var_5C8]
0x18002ab5d  mov     rcx, [rsp+648h+hObject]; hObject
0x18002ab62  call    cs:__imp_CloseHandle
0x18002ab68  mov     rcx, r13
0x18002ab6b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002ab71  jmp     loc_18002AA6B
0x18002ab76  mov     [rsp+648h+var_5F0], esi
0x18002ab7a  mov     rdi, r13
0x18002ab7d  mov     [rsp+648h+var_5C8], r13
0x18002ab85  lea     r14, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x18002ab8c  xor     ebx, ebx
0x18002ab8e  cmp     [rsp+648h+var_5EC], ebx
0x18002ab92  jz      loc_18002AFB5
0x18002ab98  mov     eax, esi
0x18002ab9a  and     eax, 400h
0x18002ab9f  mov     [rsp+648h+dwMessageId], eax
0x18002aba3  jz      short loc_18002ABC8
0x18002aba5  test    r15d, r15d
0x18002aba8  jns     loc_18002AFB5
0x18002abae  cmp     r15d, 0A0000003h
0x18002abb5  jz      loc_18002AFB5
0x18002abbb  cmp     r15d, 0A000000Ch
0x18002abc2  jz      loc_18002AFB5
0x18002abc8  xor     edx, edx; Val
0x18002abca  mov     r8d, 250h; Size
0x18002abd0  lea     rcx, [rsp+648h+var_4D8]; void *
0x18002abd8  call    memset_0
0x18002abdd  mov     edx, 5Ch ; '\'; unsigned __int16
0x18002abe2  lea     r8d, [rdx-5Bh]; int
0x18002abe6  lea     rcx, [rsp+648h+var_560]; this
0x18002abee  call    ??0String@UnBCL@@QEAA@GH@Z; UnBCL::String::String(ushort,int)
0x18002abf3  nop
0x18002abf4  xor     edx, edx
0x18002abf6  lea     rcx, [rsp+648h+var_5B8]
0x18002abfe  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002ac03  nop
0x18002ac04  mov     r8d, 1; int
0x18002ac0a  mov     rdx, [rsp+648h+var_550]; unsigned __int16 *
0x18002ac12  mov     rcx, rdi; this
0x18002ac15  call    ?EndsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::EndsWith(ushort const *,int)
0x18002ac1a  mov     rcx, [rdi+10h]; unsigned __int16 *
0x18002ac1e  test    eax, eax
0x18002ac20  jz      short loc_18002AC51
0x18002ac22  lea     rdx, asc_180080E7C; "*"
0x18002ac29  call    ?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z; UnBCL::String::Concat(ushort const *,ushort const *)
0x18002ac2e  mov     rdx, rax
0x18002ac31  lea     rcx, [rsp+648h+hObject]
0x18002ac36  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002ac3b  nop
0x18002ac3c  mov     rdx, [rsp+648h+var_600]
0x18002ac41  lea     rcx, [rsp+648h+var_5B8]
0x18002ac49  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18002ac4e  nop
0x18002ac4f  jmp     short loc_18002AC86
0x18002ac51  lea     r8, asc_180080E7C; "*"
0x18002ac58  mov     rdx, [rsp+648h+var_550]; unsigned __int16 *
0x18002ac60  call    ?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z; UnBCL::String::Concat(ushort const *,ushort const *,ushort const *)
0x18002ac65  mov     rdx, rax
0x18002ac68  lea     rcx, [rsp+648h+hObject]
0x18002ac6d  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18002ac72  nop
0x18002ac73  mov     rdx, [rsp+648h+var_600]
0x18002ac78  lea     rcx, [rsp+648h+var_5B8]
0x18002ac80  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18002ac85  nop
0x18002ac86  mov     [rsp+648h+hObject], r14
0x18002ac8b  lea     rcx, [rsp+648h+hObject]
0x18002ac90  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002ac95  lea     rdx, [rsp+648h+var_4D8]; lpFindFileData
0x18002ac9d  mov     rcx, [rsp+648h+var_5B0]
0x18002aca5  mov     rcx, [rcx+10h]; lpFileName
0x18002aca9  call    cs:__imp_FindFirstFileW
0x18002acaf  mov     r15, rax
0x18002acb2  mov     qword ptr [rsp+648h+BytesReturned], rax
0x18002acb7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002acbb  jnz     loc_18002AD81
0x18002acc1  call    cs:__imp_GetLastError
0x18002acc7  mov     r13d, eax
0x18002acca  lea     ecx, [rax-2]
0x18002accd  cmp     ecx, 1
0x18002acd0  jbe     short loc_18002AD26
0x18002acd2  cmp     eax, 780h
0x18002acd7  jnz     loc_18002B1F1
0x18002acdd  cmp     [rsp+648h+dwMessageId], ebx
0x18002ace1  jz      loc_18002B1F1
0x18002ace7  mov     rcx, [rdi+10h]; lpFileName
0x18002aceb  call    ?pRemoveReparsePointData@@YAHPEBG@Z; pRemoveReparsePointData(ushort const *)
0x18002acf0  test    eax, eax
0x18002acf2  jz      loc_18002B1F1
0x18002acf8  lea     rdx, [rsp+648h+var_4D8]; lpFindFileData
0x18002ad00  mov     rax, [rsp+648h+var_5B0]
0x18002ad08  mov     rcx, [rax+10h]; lpFileName
0x18002ad0c  call    cs:__imp_FindFirstFileW
0x18002ad12  mov     r15, rax
0x18002ad15  mov     qword ptr [rsp+648h+BytesReturned], rax
0x18002ad1a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002ad1e  jz      loc_18002B1F1
0x18002ad24  jmp     short loc_18002AD81
0x18002ad26  mov     [rsp+648h+var_5B8], r14
0x18002ad2e  lea     rcx, [rsp+648h+var_5B8]
0x18002ad36  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002ad3b  nop
0x18002ad3c  lea     rcx, [rsp+648h+var_560]; this
0x18002ad44  call    ??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18002ad49  nop
0x18002ad4a  mov     [rsp+648h+var_5E8], r14
0x18002ad4f  lea     rcx, [rsp+648h+var_5E8]
0x18002ad54  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002ad59  mov     rcx, [rsp+648h+var_38]
0x18002ad61  xor     rcx, rsp; StackCookie
0x18002ad64  call    __security_check_cookie
0x18002ad69  mov     rbx, [rsp+648h+arg_18]
0x18002ad71  add     rsp, 620h
0x18002ad78  pop     r15
0x18002ad7a  pop     r14
0x18002ad7c  pop     r13
0x18002ad7e  pop     rdi
0x18002ad7f  pop     rsi
0x18002ad80  retn
0x18002ad81  mov     r13, rbx
0x18002ad84  mov     qword ptr [rsp+648h+dwMessageId], rbx
0x18002ad89  test    byte ptr [rsp+648h+var_4D8.dwFileAttributes], 10h
0x18002ad91  jz      loc_18002AE99
0x18002ad97  movzx   eax, [rsp+648h+var_4D8.cFileName+2]
  ... truncated ...
```
