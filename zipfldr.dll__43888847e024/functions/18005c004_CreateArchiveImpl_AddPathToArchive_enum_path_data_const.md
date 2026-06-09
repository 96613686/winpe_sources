# CreateArchiveImpl::AddPathToArchive(enum_path_data const &)

- ea: `0x18005c004`
- end: `0x18005ca7d`
- name: `?AddPathToArchive@CreateArchiveImpl@@AEAAJAEBUenum_path_data@@@Z`
- size: `2681`
- prototype: `__int64 __fastcall(CreateArchiveImpl *__hidden this, const struct enum_path_data *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005bb2c`

## callees

- `0x1800207f8`
- `0x180020cbc`
- `0x180020f08`
- `0x1800210b0`
- `0x180031e94`
- `0x180033aa8`
- `0x180034760`
- `0x180034e5c`
- `0x18003519c`
- `0x18003534c`
- `0x180036f50`
- `0x180037958`
- `0x180040e04`
- `0x180048dac`
- `0x180055f7c`
- `0x180059e7c`
- `0x18005b6d0`
- `0x18005c004`
- `0x18005dca8`
- `0x18005e604`
- `0x18005f774`
- `0x18005f950`
- `0x180071010`

## import_xrefs

- `archiveint!archive_entry_set_fflags` at `0x18005c77c`
- `archiveint!archive_entry_set_fflags` at `0x18005c77c`
- `archiveint!archive_entry_set_mode` at `0x18005c764`
- `archiveint!archive_entry_set_mode` at `0x18005c764`
- `archiveint!archive_entry_set_rdev` at `0x18005c756`
- `archiveint!archive_entry_set_rdev` at `0x18005c756`
- `archiveint!archive_entry_set_gid` at `0x18005c74a`
- `archiveint!archive_entry_set_gid` at `0x18005c74a`
- `archiveint!archive_entry_set_uid` at `0x18005c73e`
- `archiveint!archive_entry_set_uid` at `0x18005c73e`
- `archiveint!archive_entry_set_size` at `0x18005c732`
- `archiveint!archive_entry_set_size` at `0x18005c732`
- `archiveint!archive_entry_set_nlink` at `0x18005c720`
- `archiveint!archive_entry_set_nlink` at `0x18005c720`
- `archiveint!archive_entry_set_ino64` at `0x18005c712`
- `archiveint!archive_entry_set_ino64` at `0x18005c712`
- `archiveint!archive_entry_set_dev` at `0x18005c703`
- `archiveint!archive_entry_set_dev` at `0x18005c703`
- `archiveint!archive_entry_set_ctime` at `0x18005c6f5`
- `archiveint!archive_entry_set_ctime` at `0x18005c6f5`
- `archiveint!archive_entry_set_birthtime` at `0x18005c6e5`
- `archiveint!archive_entry_set_birthtime` at `0x18005c6e5`
- `archiveint!archive_entry_set_mtime` at `0x18005c6bf`
- `archiveint!archive_entry_set_mtime` at `0x18005c6bf`
- `archiveint!archive_entry_copy_symlink_w` at `0x18005c65f`
- `archiveint!archive_entry_copy_symlink_w` at `0x18005c65f`
- `archiveint!archive_entry_set_symlink_type` at `0x18005c565`
- `archiveint!archive_entry_set_symlink_type` at `0x18005c565`
- `archiveint!archive_entry_copy_sourcepath_w` at `0x18005c3a5`
- `archiveint!archive_entry_copy_sourcepath_w` at `0x18005c3a5`
- `archiveint!archive_entry_copy_pathname_w` at `0x18005c0b0`
- `archiveint!archive_entry_copy_pathname_w` at `0x18005c0b0`
- `archiveint!archive_entry_clear` at `0x18005c046`
- `archiveint!archive_entry_clear` at `0x18005c046`
- `archiveint!archive_entry_linkify` at `0x18005c875`
- `archiveint!archive_entry_linkify` at `0x18005c875`
- `archiveint!archive_entry_new2` at `0x18005c98e`
- `archiveint!archive_entry_new2` at `0x18005c98e`
- `archiveint!archive_entry_set_atime` at `0x18005c69e`
- `archiveint!archive_entry_set_atime` at `0x18005c69e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005c214`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005c214`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18005c2ca`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18005c2ca`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18005c25c`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18005c25c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005c4f5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005c4f5`

## string_xrefs

- `0x18005c26e`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005c2dc`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005c3b5`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005c51d`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005c5a8`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005c829`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005c8d1`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005c95a`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005c9b6`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005ca07`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005ca6a`: `shell\ext\zip\archive\archivecreate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateArchiveImpl::AddPathToArchive(CreateArchiveImpl *this, const struct enum_path_data *a2)
{
  struct archive_entry **v4; // r12
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // r8
  _WORD *v12; // rdx
  __int64 v13; // rax
  __int64 v14; // r8
  __int16 v15; // ax
  __int64 v16; // rdx
  __int64 v17; // rdi
  __int128 v18; // kr10_16
  int FileInfo; // eax
  union _LARGE_INTEGER v20; // r15
  HANDLE FileW; // rax
  const char *v22; // r9
  const char *v23; // r9
  unsigned int v24; // ebx
  const char *v25; // r9
  __int64 result; // rax
  const char *v27; // r9
  unsigned int v28; // ebx
  unsigned int LastError; // ebx
  unsigned __int16 v30; // r15
  union _LARGE_INTEGER *v31; // r13
  _DWORD *v32; // rax
  _DWORD *v33; // r13
  const char *v34; // r9
  char *v35; // rcx
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rax
  __int64 v40; // r8
  _WORD *v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rax
  unsigned int v44; // r9d
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rdi
  unsigned int v49; // ebx
  unsigned __int64 v50; // rbx
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // rdi
  __int64 (__fastcall *v54)(__int64, __int64, __int64); // rbx
  __int64 v55; // r8
  int v56; // eax
  unsigned int v57; // ebx
  HANDLE v58; // rbx
  int v59; // eax
  unsigned int v60; // edi
  int v61; // eax
  unsigned int v62; // edi
  __int64 v63; // rax
  unsigned int v64; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-118h]
  HANDLE hFile; // [rsp+40h] [rbp-F8h] BYREF
  int v67; // [rsp+48h] [rbp-F0h]
  unsigned int v68; // [rsp+4Ch] [rbp-ECh]
  unsigned int v69; // [rsp+50h] [rbp-E8h]
  int v70; // [rsp+54h] [rbp-E4h]
  unsigned __int64 QuadPart; // [rsp+58h] [rbp-E0h]
  unsigned __int64 v72; // [rsp+60h] [rbp-D8h]
  unsigned int v73; // [rsp+68h] [rbp-D0h]
  _BYTE FileInformation[56]; // [rsp+70h] [rbp-C8h] BYREF
  int v75; // [rsp+A8h] [rbp-90h]
  unsigned int v76; // [rsp+B0h] [rbp-88h]
  unsigned int v77; // [rsp+C0h] [rbp-78h]
  DWORD BytesReturned[4]; // [rsp+E0h] [rbp-58h] BYREF
  union _LARGE_INTEGER FileSize[2]; // [rsp+F0h] [rbp-48h] BYREF
  struct archive_entry *v80; // [rsp+100h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  FileSize[0].QuadPart = (LONGLONG)a2;
  v4 = (struct archive_entry **)((char *)this + 72);
  archive_entry_clear(*((_QWORD *)this + 9));
  v5 = *((_QWORD *)a2 + 2);
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(v5 + 2 * v6) );
  try
  {
    std::wstring::_Assign<unsigned short>((char *)this + 128, v5, v6);
    v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 128, v7, v8);
    v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 128, v9, v10)
        + 2LL * *((_QWORD *)this + 18);
    while ( v12 != (_WORD *)v11 )
    {
      if ( *v12 == 92 )
        *v12 = 47;
      ++v12;
    }
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 128, v12, v11);
    archive_entry_copy_pathname_w(*v4, v13);
    v15 = *((_WORD *)a2 + 2);
    LOBYTE(v16) = *((_BYTE *)this + 8);
    if ( (_BYTE)v16 || v15 != -24576 )
    {
      LOWORD(BytesReturned[0]) = *((_WORD *)a2 + 2);
      if ( v15 != 0x4000 && ((_BYTE)v16 || v15 != -24576) )
      {
        v17 = 0;
        v69 = 0;
        v72 = 0;
        QuadPart = 0;
        v68 = 0;
        v67 = 0;
        v18 = 0u;
        goto LABEL_19;
      }
    }
    else if ( (*((_BYTE *)a2 + 24) & 0x10) != 0 )
    {
      LOWORD(BytesReturned[0]) = 0x4000;
    }
    else
    {
      BytesReturned[0] = 0x8000;
    }
    memset_0(FileInformation, 0, 0x68u);
    FileInfo = GetFileInfo(*((LPCWSTR *)a2 + 1), (struct _FILE_STAT_BASIC_INFORMATION *)FileInformation);
    if ( FileInfo < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1DA,
        (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
        (const char *)(unsigned int)FileInfo,
        dwCreationDisposition);
    v69 = v77;
    v72 = *(_QWORD *)FileInformation;
    QuadPart = *(_QWORD *)&FileInformation[48];
    v68 = v76;
    v67 = v75;
    v18 = *(_OWORD *)&FileInformation[16];
    v17 = *(_QWORD *)&FileInformation[8];
LABEL_19:
    hFile = 0;
    if ( LOWORD(BytesReturned[0]) != 0x4000 )
    {
      v20 = FileSize[0];
      FileW = CreateFileW(
                *(LPCWSTR *)(FileSize[0].QuadPart + 8),
                0x80000080,
                1u,
                0,
                3u,
                *((_BYTE *)this + 8) != 0 ? 35651584 : 128,
                0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hFile,
        FileW);
      if ( (char *)hFile - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x1F2,
                      (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
                      v22);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        return LastError;
      }
      if ( *(_WORD *)(v20.QuadPart + 4) == 0x8000 || *((_BYTE *)this + 8) )
      {
        memset(FileInformation, 0, 52);
        if ( !GetFileInformationByHandle(hFile, (LPBY_HANDLE_FILE_INFORMATION)FileInformation) )
        {
          v28 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1FA,
                  (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
                  v27);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          return v28;
        }
        v17 = *(_QWORD *)&FileInformation[4];
        v69 = *(_DWORD *)&FileInformation[28];
        v72 = *(unsigned int *)&FileInformation[48] | ((unsigned __int64)*(unsigned int *)&FileInformation[44] << 32);
        QuadPart = *(unsigned int *)&FileInformation[36]
                 | ((unsigned __int64)*(unsigned int *)&FileInformation[32] << 32);
        v68 = *(_DWORD *)&FileInformation[40];
        v67 = *(_DWORD *)FileInformation;
        v18 = *(_OWORD *)&FileInformation[12];
      }
      else
      {
        FileSize[0].QuadPart = 0;
        if ( !GetFileSizeEx(hFile, FileSize) )
        {
          v24 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x208,
                  (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
                  v23);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          return v24;
        }
        QuadPart = FileSize[0].QuadPart;
      }
      if ( v68 > 1 && *(_WORD *)(v20.QuadPart + 4) == 0x8000 && *((_BYTE *)this + 9) )
        archive_entry_copy_sourcepath_w(*v4, *(_QWORD *)(v20.QuadPart + 8));
    }
    v30 = LOWORD(BytesReturned[0]) | 0x1B6;
    if ( (v67 & 1) != 0 )
      v30 = LOWORD(BytesReturned[0]) | 0x124;
    if ( LOWORD(BytesReturned[0]) == 0x4000 )
    {
      v30 |= 0x49u;
    }
    else
    {
      if ( LOWORD(BytesReturned[0]) == 0x8000 )
      {
        v31 = (union _LARGE_INTEGER *)((char *)this + 128);
        FileSize[0].QuadPart = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                                 (char *)this + 128,
                                 v16,
                                 v14);
        FileSize[1] = *(union _LARGE_INTEGER *)((char *)this + 144);
        *(_OWORD *)&FileSize[0].LowPart = *(_OWORD *)(split_extension((__int64)FileInformation, (__int64 *)FileSize) + 16);
        if ( (unsigned __int8)matches_name<std::basic_string_view<unsigned short> const *>(
                                FileSize,
                                &off_180076210,
                                &off_180076240) )
          v30 |= 0x49u;
LABEL_62:
        filetime_to_archive_time(FileSize, v18);
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))archive_entry_set_atime)(
          *v4,
          (union _LARGE_INTEGER)FileSize[0].QuadPart,
          FileSize[1].LowPart);
        v46 = filetime_to_archive_time(FileSize, *((_QWORD *)&v18 + 1));
        archive_entry_set_mtime(*v4, *(_QWORD *)v46, *(unsigned int *)(v46 + 8));
        v47 = filetime_to_archive_time(FileSize, v17);
        v48 = *(_QWORD *)v47;
        v49 = *(_DWORD *)(v47 + 8);
        archive_entry_set_birthtime(*v4, *(_QWORD *)v47, v49);
        archive_entry_set_ctime(*v4, v48, v49);
        archive_entry_set_dev(*v4, v69);
        archive_entry_set_ino64(*v4, v72);
        archive_entry_set_nlink(*v4, v68);
        v50 = QuadPart;
        archive_entry_set_size(*v4, QuadPart);
        archive_entry_set_uid(*v4, 0);
        archive_entry_set_gid(*v4, 0);
        archive_entry_set_rdev(*v4, 0);
        archive_entry_set_mode(*v4, v30);
        if ( (v67 & 7) != 0 )
          archive_entry_set_fflags(*v4, v67 & 7, 0);
        if ( v50 + *((_QWORD *)this + 13) >= *((_QWORD *)this + 14) )
        {
          if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 56LL))(*((_QWORD *)this + 11)) )
          {
            *((_BYTE *)this + 120) = 1;
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
            return 2147943623LL;
          }
          v53 = *((_QWORD *)this + 11);
          v54 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v53 + 80LL);
          FileSize[0].QuadPart = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31, v51, v52);
          FileSize[1] = v31[2];
          dwCreationDisposition = 0;
          v55 = *(_QWORD *)(split_filename((__int64)FileInformation, (__int64 *)FileSize) + 16);
          v56 = v54(v53, 2, v55);
          v57 = v56;
          if ( v56 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x275,
              (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
              (const char *)(unsigned int)v56,
              0);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
            return v57;
          }
          *((_QWORD *)this + 14) = *((_QWORD *)this + 13) + 1000000LL;
        }
        v80 = 0;
        archive_entry_linkify(*((_QWORD *)this + 10), v4, &v80);
        if ( *v4 )
        {
          v58 = hFile;
          v59 = CreateArchiveImpl::WriteEntryToArchive(this, *v4, hFile);
          v60 = v59;
          if ( v59 < 0 )
          {
            if ( v59 == -2147023673 )
            {
LABEL_73:
              wil::details::unique_storage<wil::details::resource_policy<archive_entry *,void (*)(archive_entry *),&void archive_entry_free(archive_entry *),wistd::integral_constant<unsigned __int64,0>,archive_entry *,archive_entry *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive_entry *,void (*)(archive_entry *),&void archive_entry_free(archive_entry *),wistd::integral_constant<unsigned __int64,0>,archive_entry *,archive_entry *,0,std::nullptr_t>>(&v80);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
              return 2147943623LL;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x286,
              (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
              (const char *)(unsigned int)v59,
              dwCreationDisposition);
            wil::details::unique_storage<wil::details::resource_policy<archive_entry *,void (*)(archive_entry *),&void archive_entry_free(archive_entry *),wistd::integral_constant<unsigned __int64,0>,archive_entry *,archive_entry *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive_entry *,void (*)(archive_entry *),&void archive_entry_free(archive_entry *),wistd::integral_constant<unsigned __int64,0>,archive_entry *,archive_entry *,0,std::nullptr_t>>(&v80);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
            return v60;
          }
          if ( v80 )
          {
            v61 = CreateArchiveImpl::WriteEntryToArchive(this, v80, v58);
            v62 = v61;
            if ( v61 < 0 )
            {
              if ( v61 == -2147023673 )
                goto LABEL_73;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x28B,
                (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
                (const char *)(unsigned int)v61,
                dwCreationDisposition);
              wil::details::unique_storage<wil::details::resource_policy<archive_entry *,void (*)(archive_entry *),&void archive_entry_free(archive_entry *),wistd::integral_constant<unsigned __int64,0>,archive_entry *,archive_entry *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive_entry *,void (*)(archive_entry *),&void archive_entry_free(archive_entry *),wistd::integral_constant<unsigned __int64,0>,archive_entry *,archive_entry *,0,std::nullptr_t>>(&v80);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
              return v62;
            }
          }
        }
        else
        {
          v63 = archive_entry_new2(*((_QWORD *)this + 8));
          wil::details::unique_storage<wil::details::resource_policy<archive_entry *,void (*)(archive_entry *),&void archive_entry_free(archive_entry *),wistd::integral_constant<unsigned __int64,0>,archive_entry *,archive_entry *,0,std::nullptr_t>>::reset(
            v4,
            v63);
          if ( !*v4 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x293,
              (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
              (const char *)0x8007000ELL,
              dwCreationDisposition);
            wil::details::unique_storage<wil::details::resource_policy<archive_entry *,void (*)(archive_entry *),&void archive_entry_free(archive_entry *),wistd::integral_constant<unsigned __int64,0>,archive_entry *,archive_entry *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive_entry *,void (*)(archive_entry *),&void archive_entry_free(archive_entry *),wistd::integral_constant<unsigned __int64,0>,archive_entry *,archive_entry *,0,std::nullptr_t>>(&v80);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
            return 2147942414LL;
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<archive_entry *,void (*)(archive_entry *),&void archive_entry_free(archive_entry *),wistd::integral_constant<unsigned __int64,0>,archive_entry *,archive_entry *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<archive_entry *,void (*)(archive_entry *),&void archive_entry_free(archive_entry *),wistd::integral_constant<unsigned __int64,0>,archive_entry *,archive_entry *,0,std::nullptr_t>>(&v80);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        return 0;
      }
      BytesReturned[0] = 0;
      v32 = wil::details::heap_allocator::allocate(0x4000u);
      v33 = v32;
      if ( v32 )
        memset_0(v32, 0, 0x4000u);
      else
        v33 = 0;
      FileSize[0].QuadPart = (LONGLONG)v33;
      if ( !DeviceIoControl(hFile, 0x900A8u, 0, 0, v33, 0x4000u, BytesReturned, 0) )
      {
        v64 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x232,
                (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
                v34);
        Microsoft::WRL::Details::MakeAllocator<CLocalCopyDownloadSink>::~MakeAllocator<CLocalCopyDownloadSink>(FileSize);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        return v64;
      }
      if ( *v33 != -1610612724 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x235,
          (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
          (const char *)0x8000FFFFLL,
          dwCreationDisposition);
        Microsoft::WRL::Details::MakeAllocator<CLocalCopyDownloadSink>::~MakeAllocator<CLocalCopyDownloadSink>(FileSize);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        return 2147549183LL;
      }
      v70 = v67 & 0x10;
      archive_entry_set_symlink_type(*v4, (unsigned int)(v70 != 0) + 1);
      v35 = (char *)v33 + *((unsigned __int16 *)v33 + 4) + 20;
      if ( (v33[4] & 1) != 0 )
      {
        std::wstring::_Assign<unsigned short>(
          (char *)this + 160,
          v35,
          (unsigned __int64)*((unsigned __int16 *)v33 + 5) >> 1);
      }
      else
      {
        v36 = ConvertNtPathToDosPath<unsigned short>(v35);
        v73 = v36;
        if ( v36 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x242,
            (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
            (const char *)(unsigned int)v36,
            dwCreationDisposition);
          Microsoft::WRL::Details::MakeAllocator<CLocalCopyDownloadSink>::~MakeAllocator<CLocalCopyDownloadSink>(FileSize);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          return v73;
        }
      }
      v39 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 160, v37, v38);
      v42 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 160, v39, v40)
          + 2LL * *((_QWORD *)this + 22);
      while ( v41 != (_WORD *)v42 )
      {
        if ( *v41 == 92 )
          *v41 = 47;
        ++v41;
      }
      if ( v70 )
      {
        v42 = *((_QWORD *)this + 22);
        if ( v42 )
        {
          v43 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 160, v41, v42);
          if ( *(_WORD *)(v43 + 2 * v42 - 2) != (_WORD)v44 )
            std::wstring::push_back((char *)this + 160, v44);
        }
      }
      v45 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 160, v41, v42);
      archive_entry_copy_symlink_w(*v4, v45);
      Microsoft::WRL::Details::MakeAllocator<CLocalCopyDownloadSink>::~MakeAllocator<CLocalCopyDownloadSink>(FileSize);
    }
    v31 = (union _LARGE_INTEGER *)((char *)this + 128);
    goto LABEL_62;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x298,
                           (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
                           v25);
  }
  return result;
}

```

## disassembly

```asm
0x18005c004  mov     [rsp+arg_10], rbx
0x18005c009  mov     [rsp+arg_18], rsi
0x18005c00e  push    rdi
0x18005c00f  push    r12
0x18005c011  push    r13
0x18005c013  push    r14
0x18005c015  push    r15
0x18005c017  sub     rsp, 110h
0x18005c01e  mov     rax, cs:__security_cookie
0x18005c025  xor     rax, rsp
0x18005c028  mov     [rsp+138h+var_30], rax
0x18005c030  mov     rbx, rdx
0x18005c033  mov     qword ptr [rsp+138h+FileSize], rdx
0x18005c03b  mov     r14, rcx
0x18005c03e  lea     r12, [rcx+48h]
0x18005c042  mov     rcx, [r12]
0x18005c046  call    cs:__imp_archive_entry_clear
0x18005c04c  mov     rdx, [rbx+10h]
0x18005c050  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005c054  xor     r13d, r13d
0x18005c057  inc     r8
0x18005c05a  cmp     [rdx+r8*2], r13w
0x18005c05f  jnz     short loc_18005C057
0x18005c061  lea     rdi, [r14+80h]
0x18005c068  mov     rcx, rdi
0x18005c06b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005c070  mov     rcx, rdi
0x18005c073  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005c078  mov     rdx, rax
0x18005c07b  mov     rcx, rdi
0x18005c07e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005c083  mov     rcx, [rdi+10h]
0x18005c087  lea     r8, [rax+rcx*2]
0x18005c08b  jmp     short loc_18005C09C
0x18005c08d  cmp     word ptr [rdx], 5Ch ; '\'
0x18005c091  jnz     short loc_18005C098
0x18005c093  mov     word ptr [rdx], 2Fh ; '/'
0x18005c098  add     rdx, 2
0x18005c09c  cmp     rdx, r8
0x18005c09f  jnz     short loc_18005C08D
0x18005c0a1  mov     rcx, rdi
0x18005c0a4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005c0a9  mov     rdx, rax
0x18005c0ac  mov     rcx, [r12]
0x18005c0b0  call    cs:__imp_archive_entry_copy_pathname_w
0x18005c0b6  movzx   eax, word ptr [rbx+4]
0x18005c0ba  mov     dl, [r14+8]
0x18005c0be  mov     ecx, 0A000h
0x18005c0c3  test    dl, dl
0x18005c0c5  jnz     short loc_18005C0F3
0x18005c0c7  cmp     ax, cx
0x18005c0ca  jnz     short loc_18005C0F3
0x18005c0cc  mov     r15d, 4000h
0x18005c0d2  mov     r13d, 8000h
0x18005c0d8  test    byte ptr [rbx+18h], 10h
0x18005c0dc  jz      short loc_18005C0E9
0x18005c0de  mov     word ptr [rsp+138h+BytesReturned], r15w
0x18005c0e7  jmp     short loc_18005C143
0x18005c0e9  mov     [rsp+138h+BytesReturned], r13d
0x18005c0f1  jmp     short loc_18005C143
0x18005c0f3  mov     r15d, 4000h
0x18005c0f9  mov     word ptr [rsp+138h+BytesReturned], ax
0x18005c101  cmp     ax, r15w
0x18005c105  jz      short loc_18005C13D
0x18005c107  test    dl, dl
0x18005c109  jnz     short loc_18005C110
0x18005c10b  cmp     ax, cx
0x18005c10e  jz      short loc_18005C13D
0x18005c110  mov     rbx, r13
0x18005c113  mov     rsi, r13
0x18005c116  mov     rdi, r13
0x18005c119  mov     [rsp+138h+var_E8], r13d
0x18005c11e  mov     [rsp+138h+var_D8], r13
0x18005c123  mov     [rsp+138h+var_E0], r13
0x18005c128  mov     [rsp+138h+var_EC], r13d
0x18005c12d  mov     [rsp+138h+var_F0], r13d
0x18005c132  mov     r13d, 8000h
0x18005c138  jmp     loc_18005C1BE
0x18005c13d  mov     r13d, 8000h
0x18005c143  xor     edx, edx; Val
0x18005c145  lea     r8d, [rdx+68h]; Size
0x18005c149  lea     rcx, [rsp+138h+FileInformation]; void *
0x18005c14e  call    memset_0
0x18005c153  lea     rdx, [rsp+138h+FileInformation]; struct _FILE_STAT_BASIC_INFORMATION *
0x18005c158  mov     rcx, [rbx+8]; lpFileName
0x18005c15c  call    ?GetFileInfo@@YAJPEBGPEAU_FILE_STAT_BASIC_INFORMATION@@@Z; GetFileInfo(ushort const *,_FILE_STAT_BASIC_INFORMATION *)
0x18005c161  mov     rcx, [rsp+138h]; this
0x18005c169  test    eax, eax
0x18005c16b  js      loc_18005CA67
0x18005c171  mov     eax, [rsp+138h+var_78]
0x18005c178  mov     [rsp+138h+var_E8], eax
0x18005c17c  mov     rax, qword ptr [rsp+138h+FileInformation]
0x18005c181  mov     [rsp+138h+var_D8], rax
0x18005c186  mov     rax, qword ptr [rsp+138h+FileInformation+30h]
0x18005c18e  mov     [rsp+138h+var_E0], rax
0x18005c193  mov     eax, [rsp+138h+var_88]
0x18005c19a  mov     [rsp+138h+var_EC], eax
0x18005c19e  mov     eax, [rsp+138h+var_90]
0x18005c1a5  mov     [rsp+138h+var_F0], eax
0x18005c1a9  mov     rbx, qword ptr [rsp+138h+FileInformation+10h]
0x18005c1b1  mov     rsi, qword ptr [rsp+138h+FileInformation+18h]
0x18005c1b9  mov     rdi, qword ptr [rsp+138h+FileInformation+8]
0x18005c1be  mov     [rsp+138h+hFile], 0
0x18005c1c7  cmp     word ptr [rsp+138h+BytesReturned], r15w
0x18005c1d0  jz      loc_18005C3D9
0x18005c1d6  mov     al, [r14+8]
0x18005c1da  neg     al
0x18005c1dc  sbb     ecx, ecx
0x18005c1de  and     ecx, 21FFF80h
0x18005c1e4  sub     ecx, 0FFFFFF80h
0x18005c1e7  mov     [rsp+138h+hTemplateFile], 0; hTemplateFile
0x18005c1f0  mov     [rsp+138h+dwFlagsAndAttributes], ecx; dwFlagsAndAttributes
0x18005c1f4  mov     [rsp+138h+dwCreationDisposition], 3; dwCreationDisposition
0x18005c1fc  xor     r9d, r9d; lpSecurityAttributes
0x18005c1ff  mov     edx, 80000080h; dwDesiredAccess
0x18005c204  lea     r8d, [r9+1]; dwShareMode
0x18005c208  mov     r15, qword ptr [rsp+138h+FileSize]
0x18005c210  mov     rcx, [r15+8]; lpFileName
0x18005c214  call    cs:__imp_CreateFileW
0x18005c21a  mov     rdx, rax
0x18005c21d  lea     rcx, [rsp+138h+hFile]
0x18005c222  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18005c227  mov     rcx, [rsp+138h+hFile]; hFile
0x18005c22c  lea     rax, [rcx-1]
0x18005c230  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005c234  ja      loc_18005C3AD
0x18005c23a  cmp     [r15+4], r13w
0x18005c23f  jz      short loc_18005C2A4
0x18005c241  cmp     byte ptr [r14+8], 0
0x18005c246  jnz     short loc_18005C2A4
0x18005c248  mov     qword ptr [rsp+138h+FileSize], 0
0x18005c254  lea     rdx, [rsp+138h+FileSize]; lpFileSize
0x18005c25c  call    cs:__imp_GetFileSizeEx
0x18005c262  test    eax, eax
0x18005c264  jnz     short loc_18005C292
0x18005c266  mov     rcx, [rsp+138h]; this
0x18005c26e  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005c275  mov     edx, 208h; void *
0x18005c27a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c27f  mov     ebx, eax
0x18005c281  lea     rcx, [rsp+138h+hFile]
0x18005c286  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005c28b  mov     eax, ebx
0x18005c28d  jmp     loc_18005CA3A
0x18005c292  mov     rax, qword ptr [rsp+138h+FileSize]
0x18005c29a  mov     [rsp+138h+var_E0], rax
0x18005c29f  jmp     loc_18005C388
0x18005c2a4  xorps   xmm0, xmm0
0x18005c2a7  xor     eax, eax
0x18005c2a9  movups  xmmword ptr [rsp+138h+FileInformation], xmm0
0x18005c2ae  movups  xmmword ptr [rsp+138h+FileInformation+10h], xmm0
0x18005c2b6  movups  xmmword ptr [rsp+138h+FileInformation+20h], xmm0
0x18005c2be  mov     dword ptr [rsp+138h+FileInformation+30h], eax
0x18005c2c5  lea     rdx, [rsp+138h+FileInformation]; lpFileInformation
0x18005c2ca  call    cs:__imp_GetFileInformationByHandle
0x18005c2d0  test    eax, eax
0x18005c2d2  jnz     short loc_18005C300
0x18005c2d4  mov     rcx, [rsp+138h]; this
0x18005c2dc  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005c2e3  mov     edx, 1FAh; void *
0x18005c2e8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c2ed  mov     ebx, eax
0x18005c2ef  lea     rcx, [rsp+138h+hFile]
0x18005c2f4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005c2f9  mov     eax, ebx
0x18005c2fb  jmp     loc_18005CA3A
0x18005c300  mov     ebx, dword ptr [rsp+138h+FileInformation+10h]
0x18005c307  shl     rbx, 20h
0x18005c30b  mov     eax, dword ptr [rsp+138h+FileInformation+0Ch]
0x18005c30f  or      rbx, rax
0x18005c312  mov     esi, dword ptr [rsp+138h+FileInformation+18h]
0x18005c319  shl     rsi, 20h
0x18005c31d  mov     eax, dword ptr [rsp+138h+FileInformation+14h]
0x18005c324  or      rsi, rax
0x18005c327  mov     edi, dword ptr [rsp+138h+FileInformation+8]
0x18005c32b  shl     rdi, 20h
0x18005c32f  mov     eax, dword ptr [rsp+138h+FileInformation+4]
0x18005c333  or      rdi, rax
0x18005c336  mov     eax, dword ptr [rsp+138h+FileInformation+1Ch]
0x18005c33d  mov     [rsp+138h+var_E8], eax
0x18005c341  mov     ecx, dword ptr [rsp+138h+FileInformation+2Ch]
0x18005c348  shl     rcx, 20h
0x18005c34c  mov     eax, dword ptr [rsp+138h+FileInformation+30h]
0x18005c353  or      rcx, rax
0x18005c356  mov     [rsp+138h+var_D8], rcx
0x18005c35b  mov     ecx, dword ptr [rsp+138h+FileInformation+20h]
0x18005c362  shl     rcx, 20h
0x18005c366  mov     eax, dword ptr [rsp+138h+FileInformation+24h]
0x18005c36d  or      rcx, rax
0x18005c370  mov     [rsp+138h+var_E0], rcx
0x18005c375  mov     eax, dword ptr [rsp+138h+FileInformation+28h]
0x18005c37c  mov     [rsp+138h+var_EC], eax
0x18005c380  mov     eax, dword ptr [rsp+138h+FileInformation]
0x18005c384  mov     [rsp+138h+var_F0], eax
0x18005c388  cmp     [rsp+138h+var_EC], 1
0x18005c38d  jbe     short loc_18005C3D9
0x18005c38f  cmp     [r15+4], r13w
0x18005c394  jnz     short loc_18005C3D9
0x18005c396  cmp     byte ptr [r14+9], 0
0x18005c39b  jz      short loc_18005C3D9
0x18005c39d  mov     rdx, [r15+8]
0x18005c3a1  mov     rcx, [r12]
0x18005c3a5  call    cs:__imp_archive_entry_copy_sourcepath_w
0x18005c3ab  jmp     short loc_18005C3D9
0x18005c3ad  mov     rcx, [rsp+138h]; this
0x18005c3b5  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005c3bc  mov     edx, 1F2h; void *
0x18005c3c1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c3c6  mov     ebx, eax
0x18005c3c8  lea     rcx, [rsp+138h+hFile]
0x18005c3cd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005c3d2  mov     eax, ebx
0x18005c3d4  jmp     loc_18005CA3A
0x18005c3d9  movzx   ecx, word ptr [rsp+138h+BytesReturned]
0x18005c3e1  or      cx, 124h
0x18005c3e6  movzx   r15d, cx
0x18005c3ea  or      r15w, 92h
0x18005c3f0  test    byte ptr [rsp+138h+var_F0], 1
0x18005c3f5  cmovnz  r15w, cx
0x18005c3fa  mov     eax, 4000h
0x18005c3ff  mov     ecx, [rsp+138h+BytesReturned]
0x18005c406  cmp     cx, ax
0x18005c409  jnz     short loc_18005C415
0x18005c40b  or      r15w, 49h
0x18005c410  jmp     loc_18005C673
0x18005c415  cmp     cx, r13w
0x18005c419  jnz     short loc_18005C48A
0x18005c41b  lea     r13, [r14+80h]
0x18005c422  mov     rcx, r13
0x18005c425  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005c42a  mov     qword ptr [rsp+138h+FileSize], rax
0x18005c432  mov     rax, [r13+10h]
0x18005c436  mov     qword ptr [rsp+138h+FileSize+8], rax
0x18005c43e  lea     rdx, [rsp+138h+FileSize]
0x18005c446  lea     rcx, [rsp+138h+FileInformation]
0x18005c44b  call    ?split_extension@@YA?AU?$pair@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V12@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; split_extension(std::basic_string_view<ushort>)
0x18005c450  movups  xmm0, xmmword ptr [rax+10h]
0x18005c454  movdqu  xmmword ptr [rsp+138h+FileSize], xmm0
0x18005c45d  lea     r8, off_180076240
0x18005c464  lea     rdx, off_180076210; ".exe"
0x18005c46b  lea     rcx, [rsp+138h+FileSize]
0x18005c473  call    ??$matches_name@PEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@@YA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEBV01@1@Z; matches_name<std::basic_string_view<ushort> const *>(std::basic_string_view<ushort>,std::basic_string_view<ushort> const *,std::basic_string_view<ushort> const *)
0x18005c478  test    al, al
0x18005c47a  jz      loc_18005C67A
0x18005c480  or      r15w, 49h
0x18005c485  jmp     loc_18005C67A
0x18005c48a  mov     [rsp+138h+BytesReturned], 0
0x18005c495  mov     rcx, rax; unsigned __int64
0x18005c498  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x18005c49d  mov     r13, rax
0x18005c4a0  test    rax, rax
0x18005c4a3  jz      short loc_18005C4B7
0x18005c4a5  xor     edx, edx; Val
0x18005c4a7  mov     r8d, 4000h; Size
0x18005c4ad  mov     rcx, rax; void *
0x18005c4b0  call    memset_0
0x18005c4b5  jmp     short loc_18005C4BA
0x18005c4b7  xor     r13d, r13d
0x18005c4ba  mov     qword ptr [rsp+138h+FileSize], r13
0x18005c4c2  mov     [rsp+138h+lpOverlapped], 0; lpOverlapped
0x18005c4cb  lea     rax, [rsp+138h+BytesReturned]
0x18005c4d3  mov     [rsp+138h+hTemplateFile], rax; lpBytesReturned
0x18005c4d8  mov     [rsp+138h+dwFlagsAndAttributes], 4000h; nOutBufferSize
0x18005c4e0  mov     qword ptr [rsp+138h+dwCreationDisposition], r13; int
0x18005c4e5  xor     r9d, r9d; nInBufferSize
0x18005c4e8  xor     r8d, r8d; lpInBuffer
0x18005c4eb  mov     edx, 900A8h; dwIoControlCode
0x18005c4f0  mov     rcx, [rsp+138h+hFile]; hDevice
0x18005c4f5  call    cs:__imp_DeviceIoControl
0x18005c4fb  test    eax, eax
0x18005c4fd  jz      loc_18005C9FF
0x18005c503  cmp     dword ptr [r13+0], 0A000000Ch
0x18005c50b  jz      short loc_18005C54E
0x18005c50d  mov     rcx, [rsp+138h]; this
0x18005c515  mov     ebx, 8000FFFFh
0x18005c51a  mov     r9d, ebx; char *
0x18005c51d  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005c524  mov     edx, 235h; void *
0x18005c529  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c52e  nop
0x18005c52f  lea     rcx, [rsp+138h+FileSize]
0x18005c537  call    ??1?$MakeAllocator@VCLocalCopyDownloadSink@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CLocalCopyDownloadSink>::~MakeAllocator<CLocalCopyDownloadSink>(void)
0x18005c53c  nop
0x18005c53d  lea     rcx, [rsp+138h+hFile]
0x18005c542  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005c547  mov     eax, ebx
0x18005c549  jmp     loc_18005CA3A
0x18005c54e  mov     eax, [rsp+138h+var_F0]
0x18005c552  and     eax, 10h
0x18005c555  mov     [rsp+138h+var_E4], eax
0x18005c559  neg     eax
0x18005c55b  sbb     edx, edx
0x18005c55d  neg     edx
0x18005c55f  inc     edx
0x18005c561  mov     rcx, [r12]
0x18005c565  call    cs:__imp_archive_entry_set_symlink_type
0x18005c56b  movzx   ecx, word ptr [r13+8]
0x18005c570  add     rcx, 14h
0x18005c574  add     rcx, r13; Src
0x18005c577  movzx   eax, word ptr [r13+0Ah]
  ... truncated ...
```
