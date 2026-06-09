# UnBCL::Directory::Copy(UnBCL::String const *,UnBCL::String const *,int,UnBCL::Directory::ICopyDelegate *)

- ea: `0x180028470`
- end: `0x180029043`
- name: `?Copy@Directory@UnBCL@@SAXPEBVString@2@0HPEAUICopyDelegate@12@@Z`
- size: `3027`
- prototype: `void __fastcall(const struct UnBCL::String *, const struct UnBCL::String *, int, struct UnBCL::Directory::ICopyDelegate *)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180028470`

## callees

- `0x18000225c`
- `0x180002ca0`
- `0x180002f50`
- `0x180002f90`
- `0x180009e7c`
- `0x180011570`
- `0x180025720`
- `0x180028470`
- `0x180029280`
- `0x18002bca0`
- `0x1800477d0`
- `0x180048fb0`
- `0x180049140`
- `0x180049500`
- `0x18004a440`
- `0x18005b6d0`
- `0x18005b790`
- `0x18005b9f0`
- `0x18005bcd0`
- `0x18005bda0`
- `0x18005be50`
- `0x18005c060`
- `0x180060150`
- `0x1800602f0`
- `0x180064340`
- `0x180068fe6`
- `0x180069020`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetFileTime` at `0x180028dd0`
- `KERNEL32!GetFileTime` at `0x180028dd0`
- `KERNEL32!CopyFileExW` at `0x180028aa0`
- `KERNEL32!CopyFileExW` at `0x180028aa0`
- `KERNEL32!CloseHandle` at `0x180028b33`
- `KERNEL32!CloseHandle` at `0x180028e40`
- `KERNEL32!CloseHandle` at `0x180028e49`
- `KERNEL32!CloseHandle` at `0x180028b33`
- `KERNEL32!CloseHandle` at `0x180028e40`
- `KERNEL32!CloseHandle` at `0x180028e49`
- `KERNEL32!GetLastError` at `0x180028aaa`
- `KERNEL32!GetLastError` at `0x180028d16`
- `KERNEL32!GetLastError` at `0x180028ef0`
- `KERNEL32!GetLastError` at `0x180028aaa`
- `KERNEL32!GetLastError` at `0x180028d16`
- `KERNEL32!GetLastError` at `0x180028ef0`
- `KERNEL32!FindFirstFileW` at `0x18002869f`
- `KERNEL32!FindFirstFileW` at `0x18002869f`
- `KERNEL32!FindNextFileW` at `0x180028d08`
- `KERNEL32!FindNextFileW` at `0x180028d08`
- `KERNEL32!SetFileTime` at `0x180028b25`
- `KERNEL32!SetFileTime` at `0x180028e37`
- `KERNEL32!SetFileTime` at `0x180028b25`
- `KERNEL32!SetFileTime` at `0x180028e37`
- `KERNEL32!FindClose` at `0x180028d27`
- `KERNEL32!FindClose` at `0x180028d27`
- `KERNEL32!CreateFileW` at `0x180028af6`
- `KERNEL32!CreateFileW` at `0x180028d96`
- `KERNEL32!CreateFileW` at `0x180028e13`
- `KERNEL32!CreateFileW` at `0x180028af6`
- `KERNEL32!CreateFileW` at `0x180028d96`
- `KERNEL32!CreateFileW` at `0x180028e13`
- `KERNEL32!GetFileAttributesW` at `0x180028a68`
- `KERNEL32!GetFileAttributesW` at `0x180028a68`
- `KERNEL32!SetFileAttributesW` at `0x180028a83`
- `KERNEL32!SetFileAttributesW` at `0x180028ac3`
- `KERNEL32!SetFileAttributesW` at `0x180028a83`
- `KERNEL32!SetFileAttributesW` at `0x180028ac3`

## string_xrefs

- `0x180028f15`: `void __cdecl UnBCL::Directory::Copy(const class UnBCL::String *,const class UnBCL::String *,int,struct UnBCL::Directory::ICopyDelegate *)`
- `0x180028f41`: `void __cdecl UnBCL::Directory::Copy(const class UnBCL::String *,const class UnBCL::String *,int,struct UnBCL::Directory::ICopyDelegate *)`
- `0x180028fb3`: `void __cdecl UnBCL::Directory::Copy(const class UnBCL::String *,const class UnBCL::String *,int,struct UnBCL::Directory::ICopyDelegate *)`
- `0x180029017`: `void __cdecl UnBCL::Directory::Copy(const class UnBCL::String *,const class UnBCL::String *,int,struct UnBCL::Directory::ICopyDelegate *)`
- `0x180028980`: ` dir copy to `
- `0x180028b79`: ` dir copy to `
- `0x180028c3f`: ` dir copy to `

## pseudocode

```c
// Hidden C++ exception states: #wind=27
void __fastcall UnBCL::Directory::Copy(
        const struct UnBCL::String *a1,
        const struct UnBCL::String *a2,
        int a3,
        struct UnBCL::Directory::ICopyDelegate *a4)
{
  struct UnBCL::Directory::ICopyDelegate *v4; // r14
  int v5; // r15d
  struct UnBCL::String *FullPath; // rax
  __int64 v8; // rax
  struct UnBCL::String *v9; // rax
  struct UnBCL::String *v10; // rax
  __int64 v11; // rax
  struct UnBCL::String *v12; // rax
  int v13; // eax
  __int64 v14; // rbx
  const unsigned __int16 *v15; // rcx
  struct UnBCL::String *v16; // rax
  DWORD v17; // esi
  struct UnBCL::DirectoryInfo *Dir; // rax
  struct UnBCL::DirectoryInfo *v19; // r14
  const struct UnBCL::String *v20; // rax
  struct UnBCL::String *v21; // rax
  const struct UnBCL::String *v22; // rax
  struct UnBCL::String *v23; // rax
  struct UnBCL::String *v24; // rax
  struct UnBCL::String *v25; // rax
  __int64 v26; // r15
  struct UnBCL::DirectoryInfo *v27; // r13
  int v28; // eax
  struct UnBCL::String *v29; // rax
  signed int v30; // r14d
  BOOL v31; // edx
  HANDLE FileW; // rax
  unsigned int v33; // eax
  int v34; // eax
  struct UnBCL::String *v35; // rax
  struct UnBCL::String *v36; // rax
  DWORD v37; // r14d
  HANDLE v38; // rax
  void *v39; // rsi
  HANDLE v40; // rax
  void *v41; // rbx
  UnBCL::Win32Exception *v42; // rdi
  DWORD LastError; // ebx
  const struct UnBCL::String *v44; // rax
  UnBCL::Win32Exception *v45; // rdi
  const struct UnBCL::String *v46; // rax
  UnBCL::Win32Exception *v47; // rdi
  const struct UnBCL::String *v48; // rax
  struct _FILETIME v49; // rax
  void **v50; // [rsp+40h] [rbp-458h] BYREF
  struct UnBCL::DirectoryInfo *v51; // [rsp+48h] [rbp-450h]
  BOOL v52; // [rsp+50h] [rbp-448h]
  int v53; // [rsp+54h] [rbp-444h]
  struct _FILETIME CreationTime; // [rsp+58h] [rbp-440h] BYREF
  struct _FILETIME LastAccessTime; // [rsp+60h] [rbp-438h] BYREF
  void **v56; // [rsp+68h] [rbp-430h] BYREF
  __int64 v57; // [rsp+70h] [rbp-428h]
  DWORD v58; // [rsp+78h] [rbp-420h]
  int v59; // [rsp+7Ch] [rbp-41Ch]
  HANDLE hFindFile; // [rsp+80h] [rbp-418h] BYREF
  struct UnBCL::Directory::ICopyDelegate *v61; // [rsp+88h] [rbp-410h]
  char v62[8]; // [rsp+90h] [rbp-408h] BYREF
  __int64 v63; // [rsp+98h] [rbp-400h]
  struct UnBCL::String *v64[2]; // [rsp+A0h] [rbp-3F8h] BYREF
  int v65; // [rsp+B0h] [rbp-3E8h]
  DWORD dwFileAttributes[2]; // [rsp+B8h] [rbp-3E0h]
  _QWORD v67[2]; // [rsp+C0h] [rbp-3D8h] BYREF
  char v68[8]; // [rsp+D0h] [rbp-3C8h] BYREF
  __int64 v69; // [rsp+D8h] [rbp-3C0h]
  struct UnBCL::String *v70[2]; // [rsp+E0h] [rbp-3B8h] BYREF
  char v71[8]; // [rsp+F0h] [rbp-3A8h] BYREF
  __int64 v72; // [rsp+F8h] [rbp-3A0h]
  struct UnBCL::String *v73[2]; // [rsp+100h] [rbp-398h] BYREF
  char v74[8]; // [rsp+110h] [rbp-388h] BYREF
  __int64 v75; // [rsp+118h] [rbp-380h] BYREF
  _QWORD v76[2]; // [rsp+120h] [rbp-378h] BYREF
  _BYTE v77[24]; // [rsp+130h] [rbp-368h] BYREF
  __int64 pExceptionObject; // [rsp+148h] [rbp-350h] BYREF
  __int64 v79; // [rsp+150h] [rbp-348h] BYREF
  __int64 v80; // [rsp+158h] [rbp-340h] BYREF
  __int64 v81; // [rsp+160h] [rbp-338h] BYREF
  _BYTE v82[16]; // [rsp+168h] [rbp-330h] BYREF
  unsigned __int16 *v83; // [rsp+178h] [rbp-320h]
  char v84[8]; // [rsp+180h] [rbp-318h] BYREF
  __int64 v85; // [rsp+188h] [rbp-310h]
  struct UnBCL::String *v86[2]; // [rsp+190h] [rbp-308h] BYREF
  char v87[8]; // [rsp+1A0h] [rbp-2F8h] BYREF
  __int64 v88; // [rsp+1A8h] [rbp-2F0h]
  _QWORD v89[3]; // [rsp+1B0h] [rbp-2E8h] BYREF
  struct _FILETIME v90; // [rsp+1C8h] [rbp-2D0h] BYREF
  _BYTE v91[24]; // [rsp+1D0h] [rbp-2C8h] BYREF
  _BYTE v92[24]; // [rsp+1E8h] [rbp-2B0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+200h] [rbp-298h] BYREF

  v89[2] = -2;
  v4 = a4;
  CreationTime = (struct _FILETIME)a4;
  v5 = a3;
  v53 = a3;
  v65 = a3;
  v61 = a4;
  FullPath = UnBCL::Path::GetFullPath(a1);
  v8 = UnBCL::_::MakeSmartPtr<UnBCL::String>(&v50, FullPath);
  v9 = UnBCL::Path::WithLongPrefix(*(const struct UnBCL::String **)(v8 + 8), 1);
  UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v62, v9);
  v50 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v50);
  v10 = UnBCL::Path::GetFullPath(a2);
  v11 = UnBCL::_::MakeSmartPtr<UnBCL::String>(&v50, v10);
  v12 = UnBCL::Path::WithLongPrefix(*(const struct UnBCL::String **)(v11 + 8), 1);
  UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v68, v12);
  v50 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v50);
  UnBCL::Path::CheckPathTooLong(*(struct UnBCL::String **)((char *)v64 + *(int *)(v63 + 4)));
  UnBCL::Path::CheckPathTooLong(*(struct UnBCL::String **)((char *)v70 + *(int *)(v69 + 4)));
  UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v74);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  UnBCL::String::String((UnBCL::String *)v82, 0x5Cu, 1);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v67, 0);
  v13 = UnBCL::String::EndsWith(*(struct UnBCL::String **)((char *)v64 + *(int *)(v63 + 4)), v83, 1);
  v14 = 0;
  v15 = (const unsigned __int16 *)(*(_QWORD **)((char *)v64 + *(int *)(v63 + 4)))[2];
  if ( v13 )
    v16 = UnBCL::String::Concat(v15, L"*");
  else
    v16 = UnBCL::String::Concat(v15, v83, L"*");
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v50, v16);
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(v67, v51);
  v50 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v50);
  hFindFile = FindFirstFileW(*(LPCWSTR *)(v67[1] + 16LL), &FindFileData);
  if ( hFindFile == (HANDLE)-1LL )
  {
    v42 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v61 = v42;
    if ( v42 )
    {
      LastError = GetLastError();
      v44 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->(v67);
      v14 = UnBCL::Win32Exception::Win32Exception(v42, LastError, v44);
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v14,
                         "void __cdecl UnBCL::Directory::Copy(const class UnBCL::String *,const class UnBCL::String *,int"
                         ",struct UnBCL::Directory::ICopyDelegate *)");
    throw (UnBCL::Win32Exception **)&pExceptionObject;
  }
  v17 = 0;
  v58 = 0;
  LastAccessTime = 0;
  v59 = 0;
  if ( !(unsigned int)UnBCL::Directory::Exists(*(struct UnBCL::String **)((char *)v70 + *(int *)(v69 + 4))) )
  {
    Dir = UnBCL::Directory::CreateDir(*(struct UnBCL::String **)((char *)v70 + *(int *)(v69 + 4)));
    v19 = Dir;
    v50 = &UnBCL::SmartPtr<UnBCL::DirectoryInfo>::`vftable';
    v51 = 0;
    if ( Dir )
      _InterlockedAdd((volatile signed __int32 *)Dir + 2, 1u);
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v50);
    v51 = v19;
    v59 = 1;
    v50 = &UnBCL::SmartPtr<UnBCL::DirectoryInfo>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v50);
    v4 = (struct UnBCL::Directory::ICopyDelegate *)CreationTime;
  }
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      if ( (FindFileData.cFileName[0] != 46
         || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]))
        && v5 )
      {
        try
        {
          v20 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v91, FindFileData.cFileName);
          v21 = UnBCL::Path::Combine(*(struct UnBCL::String **)((char *)v64 + *(int *)(v63 + 4)), v20);
          UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v71, v21);
          UnBCL::String::~String((UnBCL::String *)v91);
          v22 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v92, FindFileData.cFileName);
          v23 = UnBCL::Path::Combine(*(struct UnBCL::String **)((char *)v70 + *(int *)(v69 + 4)), v22);
          UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v84, v23);
          UnBCL::String::~String((UnBCL::String *)v92);
          UnBCL::Directory::Copy(
            *(struct UnBCL::String **)((char *)v73 + *(int *)(v72 + 4)),
            *(struct UnBCL::String **)((char *)v86 + *(int *)(v85 + 4)),
            v5,
            v4);
          v86[0] = (struct UnBCL::String *)&UnBCL::SmartPtr<UnBCL::String>::`vftable';
          UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v86);
          v73[0] = (struct UnBCL::String *)&UnBCL::SmartPtr<UnBCL::String>::`vftable';
          UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v73);
        }
        catch ( UnBCL::Exception *v90 )
        {
          v49 = LastAccessTime;
          if ( !*(_QWORD *)&LastAccessTime )
            v49 = v90;
          LastAccessTime = v49;
          v14 = 0;
          v17 = v58;
          v5 = v65;
          v53 = v65;
          v4 = v61;
          CreationTime = (struct _FILETIME)v61;
          goto LABEL_50;
        }
      }
      goto LABEL_50;
    }
    UnBCL::String::String((UnBCL::String *)v77, FindFileData.cFileName);
    v24 = UnBCL::Path::Combine(
            *(struct UnBCL::String **)((char *)v64 + *(int *)(v63 + 4)),
            (const struct UnBCL::String *)v77);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v50, v24);
    v25 = UnBCL::Path::Combine(
            *(struct UnBCL::String **)((char *)v70 + *(int *)(v69 + 4)),
            (const struct UnBCL::String *)v77);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v56, v25);
    v26 = v57;
    v27 = v51;
    if ( !v4 )
      break;
    v28 = (*(__int64 (__fastcall **)(struct UnBCL::Directory::ICopyDelegate *, _QWORD, _QWORD))(*(_QWORD *)v4 + 64LL))(
            v4,
            *((_QWORD *)v51 + 2),
            *(_QWORD *)(v57 + 16));
    if ( !v28 )
    {
      v29 = UnBCL::String::Concat(4, L"Canceled: ", *((_QWORD *)v27 + 2), L" dir copy to ", *(_QWORD *)(v26 + 16));
      UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v71, v29);
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(
        (char *)&v76[-1] + *(int *)(v75 + 4),
        *(struct UnBCL::String **)((char *)v73 + *(int *)(v72 + 4)));
      v73[0] = (struct UnBCL::String *)&UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v73);
      v17 = -2147023673;
      goto LABEL_19;
    }
    if ( v28 != 1 )
      break;
    v56 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v56);
    v50 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v50);
    UnBCL::String::~String((UnBCL::String *)v77);
LABEL_49:
    v5 = v53;
LABEL_50:
    if ( !FindNextFileW(hFindFile, &FindFileData) )
      goto LABEL_51;
  }
  dwFileAttributes[0] = GetFileAttributesW(*(LPCWSTR *)(v26 + 16));
  if ( dwFileAttributes[0] != -1 )
    SetFileAttributesW(*(LPCWSTR *)(v26 + 16), 0x80u);
  v52 = CopyFileExW(*((LPCWSTR *)v27 + 2), *(LPCWSTR *)(v26 + 16), 0, 0, 0, 0);
  v30 = GetLastError();
  if ( dwFileAttributes[0] != -1 )
    SetFileAttributesW(*(LPCWSTR *)(v26 + 16), dwFileAttributes[0]);
  v31 = v52;
  if ( v52 )
  {
    FileW = CreateFileW(*(LPCWSTR *)(v26 + 16), 0x100u, 7u, 0, 3u, 0x2000000u, 0);
    *(_QWORD *)dwFileAttributes = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      SetFileTime(FileW, &FindFileData.ftCreationTime, &FindFileData.ftLastAccessTime, &FindFileData.ftLastWriteTime);
      CloseHandle(*(HANDLE *)dwFileAttributes);
    }
    v31 = v52;
  }
  if ( !*(_QWORD *)&CreationTime )
    goto LABEL_40;
  v33 = 0;
  if ( !v31 )
    v33 = v30;
  v30 = v33;
  v34 = (*(__int64 (__fastcall **)(struct _FILETIME, _QWORD, _QWORD, _QWORD))(**(_QWORD **)&CreationTime + 72LL))(
          CreationTime,
          *((_QWORD *)v27 + 2),
          *(_QWORD *)(v26 + 16),
          v33);
  if ( v34 )
  {
    if ( v34 == 1 )
    {
LABEL_48:
      v56 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v56);
      v50 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v50);
      UnBCL::String::~String((UnBCL::String *)v77);
      v4 = (struct UnBCL::Directory::ICopyDelegate *)CreationTime;
      goto LABEL_49;
    }
LABEL_40:
    if ( !v52 && !*(_QWORD *)&LastAccessTime )
    {
      if ( !*(_QWORD *)((char *)v76 + *(int *)(v75 + 4)) )
      {
        v36 = UnBCL::String::Concat(
                *((const unsigned __int16 **)v27 + 2),
                L" dir copy to ",
                *(const unsigned __int16 **)(v26 + 16));
        UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v87, v36);
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(
          (char *)&v76[-1] + *(int *)(v75 + 4),
          *(_QWORD *)((char *)v89 + *(int *)(v88 + 4)));
        v89[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v89);
      }
      if ( v30 > 0 )
        v17 = (unsigned __int16)v30 | 0x80070000;
      else
        v17 = v30;
      v58 = v17;
    }
    goto LABEL_48;
  }
  v35 = UnBCL::String::Concat(
          *((const unsigned __int16 **)v27 + 2),
          L" dir copy to ",
          *(const unsigned __int16 **)(v26 + 16));
  UnBCL::StringPtr::StringPtr((UnBCL::StringPtr *)v71, v35);
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(
    (char *)&v76[-1] + *(int *)(v75 + 4),
    *(struct UnBCL::String **)((char *)v73 + *(int *)(v72 + 4)));
  v73[0] = (struct UnBCL::String *)&UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v73);
  if ( !v30 )
  {
    LOWORD(v30) = 1223;
    goto LABEL_36;
  }
  if ( v30 > 0 )
LABEL_36:
    v17 = (unsigned __int16)v30 | 0x80070000;
  else
    v17 = v30;
LABEL_19:
  v56 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v56);
  v50 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v50);
  UnBCL::String::~String((UnBCL::String *)v77);
LABEL_51:
  v37 = GetLastError();
  FindClose(hFindFile);
  if ( LastAccessTime )
  {
    v79 = ((__int64 (__fastcall *)(_QWORD, _QWORD))AddStackTraceToException<UnBCL::InvalidOperationException>)(
            LastAccessTime,
            "void __cdecl UnBCL::Directory::Copy(const class UnBCL::String *,const class UnBCL::String *,int,struct UnBCL"
            "::Directory::ICopyDelegate *)");
    throw (UnBCL::Exception **)&v79;
  }
  if ( v17 )
  {
    v45 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v61 = v45;
    if ( v45 )
    {
      v46 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->((char *)&v76[-1] + *(int *)(v75 + 4));
      v14 = UnBCL::Win32Exception::Win32Exception(v45, v17, v46);
    }
    v80 = AddStackTraceToException<UnBCL::InvalidOperationException>(
            v14,
            "void __cdecl UnBCL::Directory::Copy(const class UnBCL::String *,const class UnBCL::String *,int,struct UnBCL"
            "::Directory::ICopyDelegate *)");
    throw (UnBCL::Win32Exception **)&v80;
  }
  if ( v37 && v37 != 18 )
  {
    v47 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
    v61 = v47;
    if ( v47 )
    {
      v48 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::Decoder>::operator->(v67);
      v14 = UnBCL::Win32Exception::Win32Exception(v47, v37, v48);
    }
    v81 = AddStackTraceToException<UnBCL::InvalidOperationException>(
            v14,
            "void __cdecl UnBCL::Directory::Copy(const class UnBCL::String *,const class UnBCL::String *,int,struct UnBCL"
            "::Directory::ICopyDelegate *)");
    throw (UnBCL::Win32Exception **)&v81;
  }
  if ( v59 )
  {
    v38 = CreateFileW((*(LPCWSTR **)((char *)v64 + *(int *)(v63 + 4)))[2], 0x80u, 7u, 0, 3u, 0x2000000u, 0);
    v39 = v38;
    if ( v38 != (HANDLE)-1LL )
    {
      CreationTime = 0;
      LastAccessTime = 0;
      hFindFile = 0;
      if ( GetFileTime(v38, &CreationTime, &LastAccessTime, (LPFILETIME)&hFindFile) )
      {
        v40 = CreateFileW((*(LPCWSTR **)((char *)v70 + *(int *)(v69 + 4)))[2], 0x100u, 7u, 0, 3u, 0x2000000u, 0);
        v41 = v40;
        if ( v40 != (HANDLE)-1LL )
        {
          SetFileTime(v40, &CreationTime, &LastAccessTime, (const FILETIME *)&hFindFile);
          CloseHandle(v41);
        }
      }
      CloseHandle(v39);
    }
  }
  v67[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v67);
  UnBCL::String::~String((UnBCL::String *)v82);
  v76[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v76);
  v70[0] = (struct UnBCL::String *)&UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v70);
  v64[0] = (struct UnBCL::String *)&UnBCL::SmartPtr<UnBCL::String>::`vftable';
  UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v64);
}

```

## disassembly

```asm
0x180028470  push    rbx
0x180028472  push    rsi
0x180028473  push    rdi
0x180028474  push    r12
0x180028476  push    r13
0x180028478  push    r14
0x18002847a  push    r15
0x18002847c  sub     rsp, 460h
0x180028483  mov     [rsp+498h+var_2D8], 0FFFFFFFFFFFFFFFEh
0x18002848f  mov     rax, cs:__security_cookie
0x180028496  xor     rax, rsp
0x180028499  mov     [rsp+498h+var_48], rax
0x1800284a1  mov     r14, r9
0x1800284a4  mov     qword ptr [rsp+498h+CreationTime.dwLowDateTime], r9
0x1800284a9  mov     r15d, r8d
0x1800284ac  mov     [rsp+498h+var_444], r8d
0x1800284b1  mov     rbx, rdx
0x1800284b4  mov     [rsp+498h+var_3E8], r8d
0x1800284bc  mov     [rsp+498h+var_410], r9
0x1800284c4  call    ?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x1800284c9  mov     rdx, rax
0x1800284cc  lea     rcx, [rsp+498h+var_458]
0x1800284d1  call    ??$MakeSmartPtr@VString@UnBCL@@@_@UnBCL@@YA?AV?$SmartPtr@VString@UnBCL@@@1@PEAVString@1@@Z; UnBCL::_::MakeSmartPtr<UnBCL::String>(UnBCL::String *)
0x1800284d6  nop
0x1800284d7  mov     r12d, 1
0x1800284dd  mov     edx, r12d; int
0x1800284e0  mov     rcx, [rax+8]; struct UnBCL::String *
0x1800284e4  call    ?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x1800284e9  mov     rdx, rax; struct UnBCL::String *
0x1800284ec  mov     r8d, r12d
0x1800284ef  lea     rcx, [rsp+498h+var_408]; this
0x1800284f7  call    ??0StringPtr@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::StringPtr::StringPtr(UnBCL::String *)
0x1800284fc  nop
0x1800284fd  lea     rdi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x180028504  mov     [rsp+498h+var_458], rdi
0x180028509  lea     rcx, [rsp+498h+var_458]
0x18002850e  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180028513  mov     rcx, rbx; struct UnBCL::String *
0x180028516  call    ?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x18002851b  mov     rdx, rax
0x18002851e  lea     rcx, [rsp+498h+var_458]
0x180028523  call    ??$MakeSmartPtr@VString@UnBCL@@@_@UnBCL@@YA?AV?$SmartPtr@VString@UnBCL@@@1@PEAVString@1@@Z; UnBCL::_::MakeSmartPtr<UnBCL::String>(UnBCL::String *)
0x180028528  nop
0x180028529  mov     edx, r12d; int
0x18002852c  mov     rcx, [rax+8]; struct UnBCL::String *
0x180028530  call    ?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x180028535  mov     rdx, rax; struct UnBCL::String *
0x180028538  mov     r8d, r12d
0x18002853b  lea     rcx, [rsp+498h+var_3C8]; this
0x180028543  call    ??0StringPtr@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::StringPtr::StringPtr(UnBCL::String *)
0x180028548  nop
0x180028549  mov     [rsp+498h+var_458], rdi
0x18002854e  lea     rcx, [rsp+498h+var_458]
0x180028553  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180028558  mov     rax, [rsp+498h+var_400]
0x180028560  movsxd  rcx, dword ptr [rax+4]
0x180028564  mov     rcx, [rsp+rcx+498h+var_3F8]; struct UnBCL::String *
0x18002856c  call    ?CheckPathTooLong@Path@UnBCL@@KAXPEBVString@2@@Z; UnBCL::Path::CheckPathTooLong(UnBCL::String const *)
0x180028571  mov     rax, [rsp+498h+var_3C0]
0x180028579  movsxd  rcx, dword ptr [rax+4]
0x18002857d  mov     rcx, [rsp+rcx+498h+var_3B8]; struct UnBCL::String *
0x180028585  call    ?CheckPathTooLong@Path@UnBCL@@KAXPEBVString@2@@Z; UnBCL::Path::CheckPathTooLong(UnBCL::String const *)
0x18002858a  mov     edx, r12d
0x18002858d  lea     rcx, [rsp+498h+var_388]; this
0x180028595  call    ??0StringPtr@UnBCL@@QEAA@XZ; UnBCL::StringPtr::StringPtr(void)
0x18002859a  nop
0x18002859b  xor     edx, edx; Val
0x18002859d  mov     r8d, 250h; Size
0x1800285a3  lea     rcx, [rsp+498h+FindFileData]; void *
0x1800285ab  call    memset_0
0x1800285b0  lea     edx, [r12+5Bh]; unsigned __int16
0x1800285b5  mov     r8d, r12d; int
0x1800285b8  lea     rcx, [rsp+498h+var_330]; this
0x1800285c0  call    ??0String@UnBCL@@QEAA@GH@Z; UnBCL::String::String(ushort,int)
0x1800285c5  nop
0x1800285c6  xor     edx, edx
0x1800285c8  lea     rcx, [rsp+498h+var_3D8]
0x1800285d0  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800285d5  nop
0x1800285d6  mov     rax, [rsp+498h+var_400]
0x1800285de  movsxd  rcx, dword ptr [rax+4]
0x1800285e2  mov     r8d, r12d; int
0x1800285e5  mov     rdx, [rsp+498h+var_320]; unsigned __int16 *
0x1800285ed  mov     rcx, [rsp+rcx+498h+var_3F8]; this
0x1800285f5  call    ?EndsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::EndsWith(ushort const *,int)
0x1800285fa  xor     ebx, ebx
0x1800285fc  test    eax, eax
0x1800285fe  mov     rax, [rsp+498h+var_400]
0x180028606  movsxd  rcx, dword ptr [rax+4]
0x18002860a  mov     rcx, [rsp+rcx+498h+var_3F8]
0x180028612  mov     rcx, [rcx+10h]; unsigned __int16 *
0x180028616  jz      short loc_180028647
0x180028618  lea     rdx, asc_180080E7C; "*"
0x18002861f  call    ?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z; UnBCL::String::Concat(ushort const *,ushort const *)
0x180028624  mov     rdx, rax
0x180028627  lea     rcx, [rsp+498h+var_458]
0x18002862c  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180028631  nop
0x180028632  mov     rdx, [rsp+498h+var_450]
0x180028637  lea     rcx, [rsp+498h+var_3D8]
0x18002863f  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x180028644  nop
0x180028645  jmp     short loc_18002867C
0x180028647  lea     r8, asc_180080E7C; "*"
0x18002864e  mov     rdx, [rsp+498h+var_320]; unsigned __int16 *
0x180028656  call    ?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z; UnBCL::String::Concat(ushort const *,ushort const *,ushort const *)
0x18002865b  mov     rdx, rax
0x18002865e  lea     rcx, [rsp+498h+var_458]
0x180028663  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180028668  nop
0x180028669  mov     rdx, [rsp+498h+var_450]
0x18002866e  lea     rcx, [rsp+498h+var_3D8]
0x180028676  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18002867b  nop
0x18002867c  mov     [rsp+498h+var_458], rdi
0x180028681  lea     rcx, [rsp+498h+var_458]
0x180028686  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002868b  lea     rdx, [rsp+498h+FindFileData]; lpFindFileData
0x180028693  mov     rcx, [rsp+498h+var_3D0]
0x18002869b  mov     rcx, [rcx+10h]; lpFileName
0x18002869f  call    cs:__imp_FindFirstFileW
0x1800286a5  mov     [rsp+498h+hFindFile], rax
0x1800286ad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800286b1  jz      loc_180028ED8
0x1800286b7  mov     esi, ebx
0x1800286b9  mov     [rsp+498h+var_420], ebx
0x1800286bd  mov     qword ptr [rsp+498h+LastAccessTime.dwLowDateTime], rbx
0x1800286c2  mov     [rsp+498h+var_41C], ebx
0x1800286c6  mov     rax, [rsp+498h+var_3C0]
0x1800286ce  movsxd  rcx, dword ptr [rax+4]
0x1800286d2  mov     rcx, [rsp+rcx+498h+var_3B8]; struct UnBCL::String *
0x1800286da  call    ?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x1800286df  test    eax, eax
0x1800286e1  jnz     short loc_180028742
0x1800286e3  mov     rax, [rsp+498h+var_3C0]
0x1800286eb  movsxd  rcx, dword ptr [rax+4]
0x1800286ef  mov     rcx, [rsp+rcx+498h+var_3B8]; struct UnBCL::String *
0x1800286f7  call    ?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z; UnBCL::Directory::CreateDir(UnBCL::String const *)
0x1800286fc  mov     r14, rax
0x1800286ff  lea     r13, ??_7?$SmartPtr@VDirectoryInfo@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::DirectoryInfo>::`vftable'
0x180028706  mov     [rsp+498h+var_458], r13
0x18002870b  mov     [rsp+498h+var_450], rbx
0x180028710  test    rax, rax
0x180028713  jz      short loc_18002871A
0x180028715  lock add [rax+8], r12d
0x18002871a  lea     rcx, [rsp+498h+var_458]
0x18002871f  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180028724  mov     [rsp+498h+var_450], r14
0x180028729  mov     [rsp+498h+var_41C], r12d
0x18002872e  mov     [rsp+498h+var_458], r13
0x180028733  lea     rcx, [rsp+498h+var_458]
0x180028738  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18002873d  mov     r14, qword ptr [rsp+498h+CreationTime.dwLowDateTime]
0x180028742  test    byte ptr [rsp+498h+FindFileData.dwFileAttributes], 10h
0x18002874a  jz      loc_1800288D1
0x180028750  movzx   eax, [rsp+498h+FindFileData.cFileName+2]
0x180028758  cmp     [rsp+498h+FindFileData.cFileName], 2Eh ; '.'
0x180028761  jnz     short loc_18002878B
0x180028763  test    ax, ax
0x180028766  jz      loc_180028CF8
0x18002876c  cmp     [rsp+498h+FindFileData.cFileName], 2Eh ; '.'
0x180028775  jnz     short loc_18002878B
0x180028777  cmp     ax, 2Eh ; '.'
0x18002877b  jnz     short loc_18002878B
0x18002877d  cmp     [rsp+498h+FindFileData.cFileName+4], bx
0x180028785  jz      loc_180028CF8
0x18002878b  test    r15d, r15d
0x18002878e  jz      loc_180028CF8
0x180028794  lea     rdx, [rsp+498h+FindFileData.cFileName]; unsigned __int16 *
0x18002879c  lea     rcx, [rsp+498h+var_2C8]; this
0x1800287a4  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800287a9  nop
0x1800287aa  mov     rcx, [rsp+498h+var_400]
0x1800287b2  movsxd  rcx, dword ptr [rcx+4]
0x1800287b6  mov     rdx, rax; struct UnBCL::String *
0x1800287b9  mov     rcx, [rsp+rcx+498h+var_3F8]; struct UnBCL::String *
0x1800287c1  call    ?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1800287c6  mov     rdx, rax; struct UnBCL::String *
0x1800287c9  mov     r8d, r12d
0x1800287cc  lea     rcx, [rsp+498h+var_3A8]; this
0x1800287d4  call    ??0StringPtr@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::StringPtr::StringPtr(UnBCL::String *)
0x1800287d9  nop
0x1800287da  lea     rcx, [rsp+498h+var_2C8]; this
0x1800287e2  call    ??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800287e7  lea     rdx, [rsp+498h+FindFileData.cFileName]; unsigned __int16 *
0x1800287ef  lea     rcx, [rsp+498h+var_2B0]; this
0x1800287f7  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800287fc  nop
0x1800287fd  mov     rcx, [rsp+498h+var_3C0]
0x180028805  movsxd  rcx, dword ptr [rcx+4]
0x180028809  mov     rdx, rax; struct UnBCL::String *
0x18002880c  mov     rcx, [rsp+rcx+498h+var_3B8]; struct UnBCL::String *
0x180028814  call    ?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180028819  mov     rdx, rax; struct UnBCL::String *
0x18002881c  mov     r8d, r12d
0x18002881f  lea     rcx, [rsp+498h+var_318]; this
0x180028827  call    ??0StringPtr@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::StringPtr::StringPtr(UnBCL::String *)
0x18002882c  nop
0x18002882d  lea     rcx, [rsp+498h+var_2B0]; this
0x180028835  call    ??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18002883a  mov     rax, [rsp+498h+var_310]
0x180028842  movsxd  rdx, dword ptr [rax+4]
0x180028846  mov     rax, [rsp+498h+var_3A0]
0x18002884e  movsxd  rcx, dword ptr [rax+4]
0x180028852  mov     r9, r14; struct UnBCL::Directory::ICopyDelegate *
0x180028855  mov     r8d, r15d; int
0x180028858  mov     rdx, [rsp+rdx+498h+var_308]; struct UnBCL::String *
0x180028860  mov     rcx, [rsp+rcx+498h+var_398]; struct UnBCL::String *
0x180028868  call    ?Copy@Directory@UnBCL@@SAXPEBVString@2@0HPEAUICopyDelegate@12@@Z; UnBCL::Directory::Copy(UnBCL::String const *,UnBCL::String const *,int,UnBCL::Directory::ICopyDelegate *)
0x18002886d  nop
0x18002886e  mov     [rsp+498h+var_308], rdi
0x180028876  lea     rcx, [rsp+498h+var_308]
0x18002887e  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180028883  nop
0x180028884  mov     [rsp+498h+var_398], rdi
0x18002888c  lea     rcx, [rsp+498h+var_398]
0x180028894  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180028899  nop
0x18002889a  jmp     loc_180028CF8
0x18002889f  mov     r12d, 1
0x1800288a5  lea     rdi, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x1800288ac  xor     ebx, ebx
0x1800288ae  mov     esi, [rsp+498h+var_420]
0x1800288b2  mov     r15d, [rsp+498h+var_3E8]
0x1800288ba  mov     [rsp+498h+var_444], r15d
0x1800288bf  mov     r14, [rsp+498h+var_410]
0x1800288c7  mov     qword ptr [rsp+498h+CreationTime.dwLowDateTime], r14
0x1800288cc  jmp     loc_180028CF8
0x1800288d1  lea     rdx, [rsp+498h+FindFileData.cFileName]; unsigned __int16 *
0x1800288d9  lea     rcx, [rsp+498h+var_368]; this
0x1800288e1  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800288e6  nop
0x1800288e7  mov     rax, [rsp+498h+var_400]
0x1800288ef  movsxd  rcx, dword ptr [rax+4]
0x1800288f3  lea     rdx, [rsp+498h+var_368]; struct UnBCL::String *
0x1800288fb  mov     rcx, [rsp+rcx+498h+var_3F8]; struct UnBCL::String *
0x180028903  call    ?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180028908  mov     rdx, rax
0x18002890b  lea     rcx, [rsp+498h+var_458]
0x180028910  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180028915  nop
0x180028916  mov     rax, [rsp+498h+var_3C0]
0x18002891e  movsxd  rcx, dword ptr [rax+4]
0x180028922  lea     rdx, [rsp+498h+var_368]; struct UnBCL::String *
0x18002892a  mov     rcx, [rsp+rcx+498h+var_3B8]; struct UnBCL::String *
0x180028932  call    ?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180028937  mov     rdx, rax
0x18002893a  lea     rcx, [rsp+498h+var_430]
0x18002893f  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180028944  nop
0x180028945  mov     r15, [rsp+498h+var_428]
0x18002894a  mov     r13, [rsp+498h+var_450]
0x18002894f  test    r14, r14
0x180028952  jz      loc_180028A64
0x180028958  mov     rax, [r14]
0x18002895b  mov     r8, [r15+10h]
0x18002895f  mov     rdx, [r13+10h]
0x180028963  mov     rcx, r14
0x180028966  mov     rax, [rax+40h]
0x18002896a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002896f  test    eax, eax
0x180028971  jnz     loc_180028A2D
0x180028977  mov     rax, [r15+10h]
0x18002897b  mov     [rsp+498h+pbCancel], rax
0x180028980  lea     r9, aDirCopyTo; " dir copy to "
0x180028987  mov     r8, [r13+10h]
0x18002898b  lea     rdx, aCanceled; "Canceled: "
0x180028992  mov     ecx, 4; int
0x180028997  call    ?Concat@String@UnBCL@@SAPEAV12@HZZ; UnBCL::String::Concat(int,...)
0x18002899c  mov     r8d, r12d
0x18002899f  mov     rdx, rax; struct UnBCL::String *
0x1800289a2  lea     rcx, [rsp+498h+var_3A8]; this
0x1800289aa  call    ??0StringPtr@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::StringPtr::StringPtr(UnBCL::String *)
0x1800289af  nop
0x1800289b0  mov     rax, [rsp+498h+var_3A0]
0x1800289b8  movsxd  rdx, dword ptr [rax+4]
0x1800289bc  mov     rax, [rsp+498h+var_380]
0x1800289c4  movsxd  rcx, dword ptr [rax+4]
0x1800289c8  lea     rax, [rsp+498h+var_380]
0x1800289d0  add     rcx, rax
0x1800289d3  mov     rdx, [rsp+rdx+498h+var_398]
0x1800289db  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x1800289e0  nop
0x1800289e1  mov     [rsp+498h+var_398], rdi
0x1800289e9  lea     rcx, [rsp+498h+var_398]
0x1800289f1  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x1800289f6  mov     esi, 800704C7h
0x1800289fb  mov     [rsp+498h+var_430], rdi
0x180028a00  lea     rcx, [rsp+498h+var_430]
0x180028a05  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180028a0a  nop
0x180028a0b  mov     [rsp+498h+var_458], rdi
0x180028a10  lea     rcx, [rsp+498h+var_458]
0x180028a15  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x180028a1a  nop
0x180028a1b  lea     rcx, [rsp+498h+var_368]; this
0x180028a23  call    ??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180028a28  jmp     loc_180028D16
0x180028a2d  cmp     eax, r12d
0x180028a30  jnz     short loc_180028A64
  ... truncated ...
```
