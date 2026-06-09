# UnBCL::File::DeleteInternal(UnBCL::String const *,int)

- ea: `0x18003b740`
- end: `0x18003c096`
- name: `?DeleteInternal@File@UnBCL@@CAXPEBVString@2@H@Z`
- size: `2390`
- prototype: `void __fastcall(LPCWSTR *, int)`
- caller_count: `3`
- callee_count: `19`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180029b30`
- `0x18002a870`
- `0x18003b5f0`

## callees

- `0x1800015ac`
- `0x18000225c`
- `0x180002f90`
- `0x180006b70`
- `0x180009e7c`
- `0x18000afd0`
- `0x180011570`
- `0x18003b740`
- `0x1800477d0`
- `0x180048980`
- `0x180049fc0`
- `0x18004a440`
- `0x18004a8b0`
- `0x18005b790`
- `0x18005b9f0`
- `0x18005bb40`
- `0x180064090`
- `0x180069020`
- `0x18006f010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003b8d6`
- `msvcrt!_wcsicmp` at `0x18003b8d6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003b8e7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003bf69`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003bf98`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003b8e7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003bf69`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003bf98`
- `ntdll!NtSetInformationFile` at `0x18003bb92`
- `ntdll!NtSetInformationFile` at `0x18003bbbc`
- `ntdll!NtSetInformationFile` at `0x18003bb92`
- `ntdll!NtSetInformationFile` at `0x18003bbbc`
- `ntdll!RtlNtStatusToDosError` at `0x18003bd0f`
- `ntdll!RtlNtStatusToDosError` at `0x18003bd0f`
- `KERNEL32!FindNextFileNameW` at `0x18003bb55`
- `KERNEL32!FindNextFileNameW` at `0x18003bb55`
- `KERNEL32!DeleteFileW` at `0x18003b808`
- `KERNEL32!DeleteFileW` at `0x18003b808`
- `KERNEL32!CloseHandle` at `0x18003b7d0`
- `KERNEL32!CloseHandle` at `0x18003bbd2`
- `KERNEL32!CloseHandle` at `0x18003bc90`
- `KERNEL32!CloseHandle` at `0x18003bcda`
- `KERNEL32!CloseHandle` at `0x18003b7d0`
- `KERNEL32!CloseHandle` at `0x18003bbd2`
- `KERNEL32!CloseHandle` at `0x18003bc90`
- `KERNEL32!CloseHandle` at `0x18003bcda`
- `KERNEL32!SetFileInformationByHandle` at `0x18003b957`
- `KERNEL32!SetFileInformationByHandle` at `0x18003bc82`
- `KERNEL32!SetFileInformationByHandle` at `0x18003b957`
- `KERNEL32!SetFileInformationByHandle` at `0x18003bc82`
- `KERNEL32!GetLastError` at `0x18003b7c0`
- `KERNEL32!GetLastError` at `0x18003bd63`
- `KERNEL32!GetLastError` at `0x18003bdbe`
- `KERNEL32!GetLastError` at `0x18003be6b`
- `KERNEL32!GetLastError` at `0x18003c008`
- `KERNEL32!GetLastError` at `0x18003b7c0`
- `KERNEL32!GetLastError` at `0x18003bd63`
- `KERNEL32!GetLastError` at `0x18003bdbe`
- `KERNEL32!GetLastError` at `0x18003be6b`
- `KERNEL32!GetLastError` at `0x18003c008`
- `KERNEL32!FindFirstFileNameW` at `0x18003baf4`
- `KERNEL32!FindFirstFileNameW` at `0x18003baf4`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18003b936`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18003b936`
- `KERNEL32!GetFileInformationByHandle` at `0x18003b917`
- `KERNEL32!GetFileInformationByHandle` at `0x18003b917`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18003b82e`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18003b86a`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18003b82e`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18003b86a`
- `KERNEL32!FindClose` at `0x18003bb69`
- `KERNEL32!FindClose` at `0x18003bb69`
- `KERNEL32!CreateFileW` at `0x18003b7a9`
- `KERNEL32!CreateFileW` at `0x18003bc59`
- `KERNEL32!CreateFileW` at `0x18003b7a9`
- `KERNEL32!CreateFileW` at `0x18003bc59`

## string_xrefs

- `0x18003bd26`: `void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)`
- `0x18003bd81`: `void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)`
- `0x18003bddc`: `void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)`
- `0x18003be2e`: `void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)`
- `0x18003be89`: `void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)`
- `0x18003bedc`: `void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)`
- `0x18003bf6f`: `void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)`
- `0x18003bfcb`: `void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)`
- `0x18003c026`: `void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)`
- `0x18003c070`: `void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)`
- `0x18003c060`: `Failed to allocate hard link file path`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
void __fastcall UnBCL::File::DeleteInternal(LPCWSTR *a1, int a2)
{
  int v4; // r14d
  HANDLE FileW; // rax
  HANDLE v6; // rbx
  DWORD LastError; // edi
  DWORD FinalPathNameByHandleW; // eax
  DWORD v9; // esi
  WCHAR *v10; // rax
  WCHAR *v11; // rdi
  DWORD v12; // eax
  const wchar_t *v13; // rcx
  LPCWSTR v14; // rdx
  int v15; // r12d
  __int64 v16; // r14
  struct UnBCL::String *v17; // rax
  struct UnBCL::String *v18; // r13
  void *v19; // rax
  __int64 v20; // rdi
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  WCHAR *v24; // rax
  const unsigned __int16 *v25; // rdi
  const unsigned __int16 *v26; // rax
  WCHAR *v27; // rax
  int v28; // edi
  NTSTATUS v29; // eax
  const unsigned __int16 *v30; // rax
  const struct UnBCL::String *v31; // rax
  struct UnBCL::String *v32; // rax
  UnBCL::Win32Exception *v33; // rax
  UnBCL::Win32Exception *v34; // rbx
  ULONG v35; // eax
  UnBCL::Win32Exception *v36; // rbx
  DWORD v37; // eax
  __int64 v38; // rax
  UnBCL::Win32Exception *v39; // rbx
  DWORD v40; // eax
  __int64 v41; // rax
  UnBCL::Win32Exception *v42; // rax
  __int64 v43; // rax
  UnBCL::Win32Exception *v44; // rbx
  DWORD v45; // eax
  __int64 v46; // rax
  UnBCL::Win32Exception *v47; // rax
  __int64 v48; // rax
  void *v49; // rbx
  const struct UnBCL::String *v50; // rax
  __int64 v51; // rbx
  UnBCL::Win32Exception *v52; // rax
  __int64 v53; // rax
  UnBCL::Win32Exception *v54; // rbx
  DWORD v55; // eax
  __int64 v56; // rax
  UnBCL::OutOfMemoryException *v57; // rax
  HANDLE hFindStream; // [rsp+40h] [rbp-C0h] BYREF
  char v59[8]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD StringLength[2]; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v61; // [rsp+58h] [rbp-A8h]
  unsigned int v62; // [rsp+60h] [rbp-A0h]
  void **v63; // [rsp+68h] [rbp-98h] BYREF
  __int64 v64; // [rsp+70h] [rbp-90h]
  void **v65; // [rsp+80h] [rbp-80h] BYREF
  __int64 v66; // [rsp+88h] [rbp-78h]
  _QWORD v67[2]; // [rsp+90h] [rbp-70h] BYREF
  void **v68; // [rsp+A0h] [rbp-60h] BYREF
  struct UnBCL::String *v69; // [rsp+A8h] [rbp-58h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v71; // [rsp+C0h] [rbp-40h]
  _BYTE v72[24]; // [rsp+C8h] [rbp-38h] BYREF
  int v73; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v74; // [rsp+E4h] [rbp-1Ch]
  __int128 v75; // [rsp+F4h] [rbp-Ch]
  int v76; // [rsp+104h] [rbp+4h]
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+108h] [rbp+8h] BYREF

  v71 = -2;
  v4 = 0;
  v62 = 0;
  v61 = 0;
  FileW = CreateFileW(a1[2], 0x10180u, 7u, 0, 3u, 0x2200000u, 0);
  v6 = FileW;
  v61 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError != 2 )
    {
      if ( LastError != 5 )
      {
        v42 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
        *(_QWORD *)StringLength = v42;
        if ( v42 )
          v43 = UnBCL::Win32Exception::Win32Exception(v42, LastError, 1, (const struct UnBCL::String *)a1);
        else
          v43 = 0;
        hFindStream = (HANDLE)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                v43,
                                "void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)");
        throw (UnBCL::Win32Exception **)&hFindStream;
      }
      if ( !DeleteFileW(a1[2]) )
      {
        v39 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
        *(_QWORD *)StringLength = v39;
        if ( v39 )
        {
          v40 = GetLastError();
          v41 = UnBCL::Win32Exception::Win32Exception(v39, v40, 1, (const struct UnBCL::String *)a1);
        }
        else
        {
          v41 = 0;
        }
        hFindStream = (HANDLE)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                v41,
                                "void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)");
        throw (UnBCL::Win32Exception **)&hFindStream;
      }
    }
    CloseHandle((HANDLE)0xFFFFFFFFFFFFFFFFLL);
    v61 = 0;
  }
  else
  {
    if ( a2 )
    {
      FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 0);
      v9 = FinalPathNameByHandleW;
      if ( !FinalPathNameByHandleW )
      {
        v44 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
        *(_QWORD *)StringLength = v44;
        if ( v44 )
        {
          v45 = GetLastError();
          v46 = UnBCL::Win32Exception::Win32Exception(v44, v45, 1, (const struct UnBCL::String *)a1);
        }
        else
        {
          v46 = 0;
        }
        hFindStream = (HANDLE)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                v46,
                                "void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)");
        throw (UnBCL::Win32Exception **)&hFindStream;
      }
      v10 = (WCHAR *)operator new[](saturated_mul(FinalPathNameByHandleW, 2u));
      v11 = v10;
      if ( !v10 )
      {
        v47 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
        *(_QWORD *)StringLength = v47;
        if ( v47 )
          v48 = UnBCL::Win32Exception::Win32Exception(v47, 8u, 1, (const struct UnBCL::String *)a1);
        else
          v48 = 0;
        hFindStream = (HANDLE)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                v48,
                                "void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)");
        throw (UnBCL::Win32Exception **)&hFindStream;
      }
      v12 = GetFinalPathNameByHandleW(v6, v10, v9, 0);
      if ( !v12 || v12 >= v9 )
      {
        operator delete[](v11);
        v52 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
        *(_QWORD *)StringLength = v52;
        if ( v52 )
          v53 = UnBCL::Win32Exception::Win32Exception(v52, 0x7Au, 1, (const struct UnBCL::String *)a1);
        else
          v53 = 0;
        hFindStream = (HANDLE)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                v53,
                                "void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)");
        throw (UnBCL::Win32Exception **)&hFindStream;
      }
      v13 = v11;
      if ( *v11 == 92 && (v11[1] == 92 || v11[1] == 63) && v11[2] == 63 && v11[3] == 92 )
        v13 = v11 + 4;
      v14 = a1[2];
      if ( *v14 == 92 && (v14[1] == 92 || v14[1] == 63) && v14[2] == 63 && v14[3] == 92 )
        v14 += 4;
      if ( _wcsicmp(v13, v14) )
      {
        v49 = UnBCL::Object::operator new(0x40u);
        hFindStream = v49;
        if ( v49 )
        {
          v50 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v63, v11);
          v4 = 1;
          v62 = 1;
          v51 = UnBCL::Win32Exception::Win32Exception((UnBCL::Win32Exception *)v49, 0x2A9u, 1, v50);
        }
        else
        {
          v51 = 0;
        }
        if ( (v4 & 1) != 0 )
        {
          v62 = v4 & 0xFFFFFFFE;
          UnBCL::String::~String((UnBCL::String *)&v63);
        }
        operator delete[](v11);
        hFindStream = (HANDLE)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                v51,
                                "void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)");
        throw (UnBCL::Win32Exception **)&hFindStream;
      }
      operator delete[](v11);
    }
    memset(&FileInformation, 0, sizeof(FileInformation));
    v73 = 0;
    v74 = 0;
    v75 = 0;
    v76 = 0;
    if ( !GetFileInformationByHandle(v6, &FileInformation)
      || !GetFileInformationByHandleEx(v6, FileBasicInfo, &v73, 0x28u) )
    {
      v36 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
      v63 = (void **)v36;
      if ( v36 )
      {
        v37 = GetLastError();
        v38 = UnBCL::Win32Exception::Win32Exception(v36, v37, 1, (const struct UnBCL::String *)a1);
      }
      else
      {
        v38 = 0;
      }
      hFindStream = (HANDLE)AddStackTraceToException<UnBCL::InvalidOperationException>(
                              v38,
                              "void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)");
      throw (UnBCL::Win32Exception **)&hFindStream;
    }
    HIDWORD(v75) = 0x2000;
    if ( !SetFileInformationByHandle(v6, FileBasicInfo, &v73, 0x28u) )
    {
      v54 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
      *(_QWORD *)StringLength = v54;
      if ( v54 )
      {
        v55 = GetLastError();
        v56 = UnBCL::Win32Exception::Win32Exception(v54, v55, 1, (const struct UnBCL::String *)a1);
      }
      else
      {
        v56 = 0;
      }
      hFindStream = (HANDLE)AddStackTraceToException<UnBCL::InvalidOperationException>(
                              v56,
                              "void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)");
      throw (UnBCL::Win32Exception **)&hFindStream;
    }
    v15 = 0;
    v65 = &UnBCL::SmartPtr<UnBCL::Array<unsigned short>>::`vftable';
    v16 = 0;
    v66 = 0;
    StringLength[0] = 0;
    v17 = UnBCL::Path::WithoutLongPrefix((const struct UnBCL::String *)a1, (int *)StringLength);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v68, v17);
    v18 = v69;
    if ( (unsigned int)UnBCL::Path::IsDriveLetterPrefix(v69) && FileInformation.nNumberOfLinks > 1 )
    {
      v19 = UnBCL::Object::operator new(0xB0u);
      hFindStream = v19;
      if ( v19 )
        v16 = UnBCL::Array<unsigned short>::Array<unsigned short>(v19, 0x8000, 0, 1);
      else
        v16 = 0;
      v63 = &UnBCL::SmartPtr<UnBCL::Array<unsigned short>>::`vftable';
      v64 = 0;
      v20 = v16 + 8;
      if ( v16 )
        _InterlockedAdd((volatile signed __int32 *)(*(int *)(*(_QWORD *)v20 + 4LL) + v16 + 16), 1u);
      UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(&v63);
      v64 = v16;
      if ( v16 )
        _InterlockedAdd((volatile signed __int32 *)(*(int *)(*(_QWORD *)v20 + 4LL) + v16 + 16), 1u);
      UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(&v65);
      v66 = v16;
      v63 = &UnBCL::SmartPtr<UnBCL::Array<unsigned short>>::`vftable';
      UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(&v63);
      if ( !v16 )
      {
        v57 = (UnBCL::OutOfMemoryException *)UnBCL::Object::operator new(0x38u);
        v63 = (void **)v57;
        if ( v57 )
          v57 = (UnBCL::OutOfMemoryException *)UnBCL::OutOfMemoryException::OutOfMemoryException(
                                                 v57,
                                                 L"Failed to allocate hard link file path");
        hFindStream = (HANDLE)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                v57,
                                "void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)");
        throw (UnBCL::OutOfMemoryException **)&hFindStream;
      }
      StringLength[0] = 0;
      v21 = v16 + *(int *)(*(_QWORD *)v20 + 16LL) + 8LL;
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v21 + 32LL))(
        v21,
        0,
        **((unsigned __int16 **)v18 + 2));
      v22 = v16 + *(int *)(*(_QWORD *)v20 + 16LL) + 8LL;
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v22 + 32LL))(v22, 1, 58);
      v23 = v16 + *(int *)(*(_QWORD *)v20 + 16LL) + 8LL;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 32LL))(v23, 2);
      StringLength[0] = 32764;
      v24 = (WCHAR *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 56LL))(v16, 2);
      hFindStream = FindFirstFileNameW(a1[2], 0, StringLength, v24);
      if ( hFindStream != (HANDLE)-1LL )
      {
        while ( 1 )
        {
          v25 = (const unsigned __int16 *)*((_QWORD *)v18 + 2);
          v26 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v16 + 56LL))(v16, 0);
          if ( (unsigned int)UnBCL::String::Compare(v26, v25, 1) )
            break;
          StringLength[0] = 32764;
          v27 = (WCHAR *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 56LL))(v16, 2);
          if ( !FindNextFileNameW(hFindStream, StringLength, v27) )
            goto LABEL_45;
        }
        v15 = 1;
LABEL_45:
        FindClose(hFindStream);
      }
    }
    v59[0] = 1;
    IoStatusBlock = 0;
    v28 = NtSetInformationFile(v6, &IoStatusBlock, v59, 1u, FileDispositionInformation);
    if ( v28 < 0 )
    {
      StringLength[0] = 1;
      v29 = NtSetInformationFile(v6, &IoStatusBlock, StringLength, 4u, (FILE_INFORMATION_CLASS)64);
      if ( v29 < 0 )
      {
        if ( v29 != -1073741821 )
          v28 = v29;
        v33 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
        v34 = v33;
        v63 = (void **)v33;
        if ( v33 )
        {
          v35 = RtlNtStatusToDosError(v28);
          v33 = (UnBCL::Win32Exception *)UnBCL::Win32Exception::Win32Exception(
                                           v34,
                                           v35,
                                           1,
                                           (const struct UnBCL::String *)a1);
        }
        hFindStream = (HANDLE)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                v33,
                                "void __cdecl UnBCL::File::DeleteInternal(const class UnBCL::String *,int)");
        throw (UnBCL::Win32Exception **)&hFindStream;
      }
    }
    if ( v6 )
    {
      CloseHandle(v6);
      v6 = 0;
      v61 = 0;
    }
    if ( v15 )
    {
      v30 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v16 + 56LL))(v16, 0);
      v31 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v72, v30);
      v32 = UnBCL::Path::WithLongPrefix(v31, 1);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v67, v32);
      UnBCL::String::~String((UnBCL::String *)v72);
      v6 = CreateFileW(*(LPCWSTR *)(v67[1] + 16LL), 0x100u, 0, 0, 3u, 0x2200000u, 0);
      v61 = v6;
      if ( v6 != (HANDLE)-1LL )
      {
        HIDWORD(v75) = FileInformation.dwFileAttributes;
        SetFileInformationByHandle(v6, FileBasicInfo, &v73, 0x28u);
        if ( v6 )
        {
          CloseHandle(v6);
          v6 = 0;
          v61 = 0;
        }
      }
      v67[0] = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(v67);
    }
    v68 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
    UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v68);
    v65 = &UnBCL::SmartPtr<UnBCL::Array<unsigned short>>::`vftable';
    UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(&v65);
    if ( v6 )
    {
      CloseHandle(v6);
      v61 = 0;
    }
  }
}

```

## disassembly

```asm
0x18003b740  push    rbp
0x18003b742  push    rbx
0x18003b743  push    rsi
0x18003b744  push    rdi
0x18003b745  push    r12
0x18003b747  push    r13
0x18003b749  push    r14
0x18003b74b  push    r15
0x18003b74d  lea     rbp, [rsp-58h]
0x18003b752  sub     rsp, 158h
0x18003b759  mov     [rbp+90h+var_D0], 0FFFFFFFFFFFFFFFEh
0x18003b761  mov     rax, cs:__security_cookie
0x18003b768  xor     rax, rsp
0x18003b76b  mov     [rbp+90h+var_50], rax
0x18003b76f  mov     edi, edx
0x18003b771  mov     r15, rcx
0x18003b774  xor     r13d, r13d
0x18003b777  mov     r14d, r13d
0x18003b77a  mov     [rsp+190h+var_130], r13d
0x18003b77f  mov     [rsp+190h+var_138], r13
0x18003b784  mov     [rsp+190h+hTemplateFile], r13; hTemplateFile
0x18003b789  mov     [rsp+190h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18003b791  mov     [rsp+190h+dwCreationDisposition], 3; dwCreationDisposition
0x18003b799  xor     r9d, r9d; lpSecurityAttributes
0x18003b79c  mov     edx, 10180h; dwDesiredAccess
0x18003b7a1  lea     r8d, [r13+7]; dwShareMode
0x18003b7a5  mov     rcx, [rcx+10h]; lpFileName
0x18003b7a9  call    cs:__imp_CreateFileW
0x18003b7af  mov     rbx, rax
0x18003b7b2  mov     [rsp+190h+var_138], rax
0x18003b7b7  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003b7bb  cmp     rax, r12
0x18003b7be  jnz     short loc_18003B81B
0x18003b7c0  call    cs:__imp_GetLastError
0x18003b7c6  mov     edi, eax
0x18003b7c8  cmp     eax, 2
0x18003b7cb  jnz     short loc_18003B7FB
0x18003b7cd  mov     rcx, r12; hObject
0x18003b7d0  call    cs:__imp_CloseHandle
0x18003b7d6  mov     [rsp+190h+var_138], r13
0x18003b7db  mov     rcx, [rbp+90h+var_50]
0x18003b7df  xor     rcx, rsp; StackCookie
0x18003b7e2  call    __security_check_cookie
0x18003b7e7  add     rsp, 158h
0x18003b7ee  pop     r15
0x18003b7f0  pop     r14
0x18003b7f2  pop     r13
0x18003b7f4  pop     r12
0x18003b7f6  pop     rdi
0x18003b7f7  pop     rsi
0x18003b7f8  pop     rbx
0x18003b7f9  pop     rbp
0x18003b7fa  retn
0x18003b7fb  cmp     edi, 5
0x18003b7fe  jnz     loc_18003BE02
0x18003b804  mov     rcx, [r15+10h]; lpFileName
0x18003b808  call    cs:__imp_DeleteFileW
0x18003b80e  test    eax, eax
0x18003b810  jz      loc_18003BDA7
0x18003b816  mov     rcx, rbx
0x18003b819  jmp     short loc_18003B7D0
0x18003b81b  test    edi, edi
0x18003b81d  jz      loc_18003B8ED
0x18003b823  xor     r9d, r9d; dwFlags
0x18003b826  xor     r8d, r8d; cchFilePath
0x18003b829  xor     edx, edx; lpszFilePath
0x18003b82b  mov     rcx, rbx; hFile
0x18003b82e  call    cs:__imp_GetFinalPathNameByHandleW
0x18003b834  mov     esi, eax
0x18003b836  test    eax, eax
0x18003b838  jz      loc_18003BE54
0x18003b83e  mov     eax, 2
0x18003b843  mul     rsi
0x18003b846  cmovb   rax, r12
0x18003b84a  mov     rcx, rax; unsigned __int64
0x18003b84d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003b852  mov     rdi, rax
0x18003b855  test    rax, rax
0x18003b858  jz      loc_18003BEAF
0x18003b85e  xor     r9d, r9d; dwFlags
0x18003b861  mov     r8d, esi; cchFilePath
0x18003b864  mov     rdx, rax; lpszFilePath
0x18003b867  mov     rcx, rbx; hFile
0x18003b86a  call    cs:__imp_GetFinalPathNameByHandleW
0x18003b870  test    eax, eax
0x18003b872  jz      loc_18003BF95
0x18003b878  cmp     eax, esi
0x18003b87a  jnb     loc_18003BF95
0x18003b880  mov     rcx, rdi
0x18003b883  mov     r8w, 3Fh ; '?'
0x18003b888  mov     ax, 5Ch ; '\'
0x18003b88c  cmp     [rdi], ax
0x18003b88f  jnz     short loc_18003B8AF
0x18003b891  cmp     [rdi+2], ax
0x18003b895  jz      short loc_18003B89E
0x18003b897  cmp     [rdi+2], r8w
0x18003b89c  jnz     short loc_18003B8AF
0x18003b89e  cmp     [rdi+4], r8w
0x18003b8a3  jnz     short loc_18003B8AF
0x18003b8a5  cmp     [rdi+6], ax
0x18003b8a9  jnz     short loc_18003B8AF
0x18003b8ab  lea     rcx, [rdi+8]; String1
0x18003b8af  mov     rdx, [r15+10h]
0x18003b8b3  cmp     [rdx], ax
0x18003b8b6  jnz     short loc_18003B8D6
0x18003b8b8  cmp     [rdx+2], ax
0x18003b8bc  jz      short loc_18003B8C5
0x18003b8be  cmp     [rdx+2], r8w
0x18003b8c3  jnz     short loc_18003B8D6
0x18003b8c5  cmp     [rdx+4], r8w
0x18003b8ca  jnz     short loc_18003B8D6
0x18003b8cc  cmp     [rdx+6], ax
0x18003b8d0  jnz     short loc_18003B8D6
0x18003b8d2  add     rdx, 8; String2
0x18003b8d6  call    cs:__imp__wcsicmp
0x18003b8dc  test    eax, eax
0x18003b8de  jnz     loc_18003BF02
0x18003b8e4  mov     rcx, rdi
0x18003b8e7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18003b8ed  xorps   xmm0, xmm0
0x18003b8f0  xor     eax, eax
0x18003b8f2  movups  xmmword ptr [rbp+90h+FileInformation.dwFileAttributes], xmm0
0x18003b8f6  movups  xmmword ptr [rbp+90h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18003b8fa  movups  xmmword ptr [rbp+90h+FileInformation.nFileSizeHigh], xmm0
0x18003b8fe  mov     [rbp+90h+FileInformation.nFileIndexLow], eax
0x18003b901  mov     [rbp+90h+var_B0], r13d
0x18003b905  movups  [rbp+90h+var_AC], xmm0
0x18003b909  movups  [rbp+90h+var_9C], xmm0
0x18003b90d  mov     [rbp+90h+var_8C], eax
0x18003b910  lea     rdx, [rbp+90h+FileInformation]; lpFileInformation
0x18003b914  mov     rcx, rbx; hFile
0x18003b917  call    cs:__imp_GetFileInformationByHandle
0x18003b91d  test    eax, eax
0x18003b91f  jz      loc_18003BD4C
0x18003b925  mov     edi, 28h ; '('
0x18003b92a  mov     r9d, edi; dwBufferSize
0x18003b92d  lea     r8, [rbp+90h+var_B0]; lpFileInformation
0x18003b931  xor     edx, edx; FileInformationClass
0x18003b933  mov     rcx, rbx; hFile
0x18003b936  call    cs:__imp_GetFileInformationByHandleEx
0x18003b93c  test    eax, eax
0x18003b93e  jz      loc_18003BD4C
0x18003b944  mov     dword ptr [rbp+90h+var_9C+0Ch], 2000h
0x18003b94b  mov     r9d, edi; dwBufferSize
0x18003b94e  lea     r8, [rbp+90h+var_B0]; lpFileInformation
0x18003b952  xor     edx, edx; FileInformationClass
0x18003b954  mov     rcx, rbx; hFile
0x18003b957  call    cs:__imp_SetFileInformationByHandle
0x18003b95d  test    eax, eax
0x18003b95f  jz      loc_18003BFF1
0x18003b965  mov     r12d, r13d
0x18003b968  lea     rdi, ??_7?$SmartPtr@V?$Array@G@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::Array<ushort>>::`vftable'
0x18003b96f  mov     [rbp+90h+var_110], rdi
0x18003b973  mov     r14, r13
0x18003b976  mov     [rbp+90h+var_108], r13
0x18003b97a  mov     [rsp+190h+StringLength], r13d
0x18003b97f  lea     rdx, [rsp+190h+StringLength]; int *
0x18003b984  mov     rcx, r15; struct UnBCL::String *
0x18003b987  call    ?WithoutLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@AEAH@Z; UnBCL::Path::WithoutLongPrefix(UnBCL::String const *,int &)
0x18003b98c  mov     rdx, rax
0x18003b98f  lea     rcx, [rbp+90h+var_F0]
0x18003b993  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003b998  nop
0x18003b999  mov     r13, [rbp+90h+var_E8]
0x18003b99d  mov     rcx, r13; struct UnBCL::String *
0x18003b9a0  call    ?IsDriveLetterPrefix@Path@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Path::IsDriveLetterPrefix(UnBCL::String const *)
0x18003b9a5  mov     esi, 1
0x18003b9aa  test    eax, eax
0x18003b9ac  jz      loc_18003BB6F
0x18003b9b2  cmp     [rbp+90h+FileInformation.nNumberOfLinks], esi
0x18003b9b5  jbe     loc_18003BB6F
0x18003b9bb  mov     ecx, 0B0h; unsigned __int64
0x18003b9c0  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003b9c5  mov     [rsp+190h+hFindStream], rax
0x18003b9ca  test    rax, rax
0x18003b9cd  jz      short loc_18003B9E7
0x18003b9cf  mov     r9d, esi
0x18003b9d2  xor     r8d, r8d
0x18003b9d5  mov     edx, 8000h
0x18003b9da  mov     rcx, rax
0x18003b9dd  call    ??0?$Array@G@UnBCL@@QEAA@HH@Z; UnBCL::Array<ushort>::Array<ushort>(int,int)
0x18003b9e2  mov     r14, rax
0x18003b9e5  jmp     short loc_18003B9EA
0x18003b9e7  xor     r14d, r14d
0x18003b9ea  mov     [rsp+190h+var_128], rdi
0x18003b9ef  mov     [rsp+190h+var_120], 0
0x18003b9f8  lea     rdi, [r14+8]
0x18003b9fc  test    r14, r14
0x18003b9ff  jz      short loc_18003BA0E
0x18003ba01  mov     rax, [rdi]
0x18003ba04  movsxd  rcx, dword ptr [rax+4]
0x18003ba08  lock add [rcx+r14+10h], esi
0x18003ba0e  lea     rcx, [rsp+190h+var_128]
0x18003ba13  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@PEAVTypeFactoryList@SerializationStream@UnBCL@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(void)
0x18003ba18  mov     [rsp+190h+var_120], r14
0x18003ba1d  test    r14, r14
0x18003ba20  jz      short loc_18003BA2F
0x18003ba22  mov     rax, [rdi]
0x18003ba25  movsxd  rcx, dword ptr [rax+4]
0x18003ba29  lock add [rcx+r14+10h], esi
0x18003ba2f  lea     rcx, [rbp+90h+var_110]
0x18003ba33  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@PEAVTypeFactoryList@SerializationStream@UnBCL@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(void)
0x18003ba38  mov     [rbp+90h+var_108], r14
0x18003ba3c  lea     rax, ??_7?$SmartPtr@V?$Array@G@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::Array<ushort>>::`vftable'
0x18003ba43  mov     [rsp+190h+var_128], rax
0x18003ba48  lea     rcx, [rsp+190h+var_128]
0x18003ba4d  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@PEAVTypeFactoryList@SerializationStream@UnBCL@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::SerializationStream::TypeFactoryList *>>::DeAssign(void)
0x18003ba52  test    r14, r14
0x18003ba55  jz      loc_18003C04C
0x18003ba5b  mov     [rsp+190h+StringLength], 0
0x18003ba63  mov     rax, [rdi]
0x18003ba66  movsxd  rcx, dword ptr [rax+10h]
0x18003ba6a  add     rcx, 8
0x18003ba6e  add     rcx, r14
0x18003ba71  mov     rax, [rcx]
0x18003ba74  mov     r8, [r13+10h]
0x18003ba78  movzx   r8d, word ptr [r8]
0x18003ba7c  xor     edx, edx
0x18003ba7e  mov     rax, [rax+20h]
0x18003ba82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba87  mov     rax, [rdi]
0x18003ba8a  movsxd  rcx, dword ptr [rax+10h]
0x18003ba8e  add     rcx, 8
0x18003ba92  add     rcx, r14
0x18003ba95  mov     rax, [rcx]
0x18003ba98  mov     r8d, 3Ah ; ':'
0x18003ba9e  mov     edx, esi
0x18003baa0  mov     rax, [rax+20h]
0x18003baa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003baa9  mov     rax, [rdi]
0x18003baac  movsxd  rcx, dword ptr [rax+10h]
0x18003bab0  add     rcx, 8
0x18003bab4  add     rcx, r14
0x18003bab7  mov     rax, [rcx]
0x18003baba  xor     r8d, r8d
0x18003babd  lea     edx, [r8+2]
0x18003bac1  mov     rax, [rax+20h]
0x18003bac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003baca  mov     [rsp+190h+StringLength], 7FFCh
0x18003bad2  mov     rax, [r14]
0x18003bad5  mov     edx, 2
0x18003bada  mov     rcx, r14
0x18003badd  mov     rax, [rax+38h]
0x18003bae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bae6  mov     r9, rax; LinkName
0x18003bae9  lea     r8, [rsp+190h+StringLength]; StringLength
0x18003baee  xor     edx, edx; dwFlags
0x18003baf0  mov     rcx, [r15+10h]; lpFileName
0x18003baf4  call    cs:__imp_FindFirstFileNameW
0x18003bafa  mov     [rsp+190h+hFindStream], rax
0x18003baff  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003bb03  jz      short loc_18003BB6F
0x18003bb05  mov     rdi, [r13+10h]
0x18003bb09  mov     rcx, [r14]
0x18003bb0c  mov     rax, [rcx+38h]
0x18003bb10  xor     edx, edx
0x18003bb12  mov     rcx, r14
0x18003bb15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb1a  mov     r8d, esi; int
0x18003bb1d  mov     rdx, rdi; unsigned __int16 *
0x18003bb20  mov     rcx, rax; unsigned __int16 *
0x18003bb23  call    ?Compare@String@UnBCL@@SAHPEBG0H@Z; UnBCL::String::Compare(ushort const *,ushort const *,int)
0x18003bb28  test    eax, eax
0x18003bb2a  jnz     short loc_18003BB61
0x18003bb2c  mov     [rsp+190h+StringLength], 7FFCh
0x18003bb34  mov     rax, [r14]
0x18003bb37  mov     edx, 2
0x18003bb3c  mov     rcx, r14
0x18003bb3f  mov     rax, [rax+38h]
0x18003bb43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb48  mov     r8, rax; LinkName
0x18003bb4b  lea     rdx, [rsp+190h+StringLength]; StringLength
0x18003bb50  mov     rcx, [rsp+190h+hFindStream]; hFindStream
0x18003bb55  call    cs:__imp_FindNextFileNameW
0x18003bb5b  test    eax, eax
0x18003bb5d  jnz     short loc_18003BB05
0x18003bb5f  jmp     short loc_18003BB64
0x18003bb61  mov     r12d, esi
0x18003bb64  mov     rcx, [rsp+190h+hFindStream]; hFindFile
0x18003bb69  call    cs:__imp_FindClose
0x18003bb6f  mov     [rsp+190h+var_148], sil
0x18003bb74  xorps   xmm0, xmm0
0x18003bb77  movups  xmmword ptr [rbp+90h+IoStatusBlock], xmm0
0x18003bb7b  mov     [rsp+190h+dwCreationDisposition], 0Dh; FileInformationClass
0x18003bb83  mov     r9d, esi; Length
0x18003bb86  lea     r8, [rsp+190h+var_148]; FileInformation
0x18003bb8b  lea     rdx, [rbp+90h+IoStatusBlock]; IoStatusBlock
0x18003bb8f  mov     rcx, rbx; FileHandle
0x18003bb92  call    cs:__imp_NtSetInformationFile
0x18003bb98  mov     edi, eax
0x18003bb9a  test    eax, eax
0x18003bb9c  jns     short loc_18003BBCA
0x18003bb9e  mov     [rsp+190h+StringLength], esi
0x18003bba2  mov     [rsp+190h+dwCreationDisposition], 40h ; '@'; FileInformationClass
0x18003bbaa  mov     r9d, 4; Length
0x18003bbb0  lea     r8, [rsp+190h+StringLength]; FileInformation
0x18003bbb5  lea     rdx, [rbp+90h+IoStatusBlock]; IoStatusBlock
0x18003bbb9  mov     rcx, rbx; FileHandle
0x18003bbbc  call    cs:__imp_NtSetInformationFile
0x18003bbc2  test    eax, eax
  ... truncated ...
```
