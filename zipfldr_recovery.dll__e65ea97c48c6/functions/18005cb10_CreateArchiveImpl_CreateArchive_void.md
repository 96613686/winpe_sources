# CreateArchiveImpl::CreateArchive(void)

- ea: `0x18005cb10`
- end: `0x18005d9dd`
- name: `?CreateArchive@CreateArchiveImpl@@QEAAJXZ`
- size: `3789`
- prototype: `__int64 __fastcall(CreateArchiveImpl *__hidden this)`
- caller_count: `2`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005ca84`
- `0x18005e420`

## callees

- `0x18000c2e4`
- `0x18002abd0`
- `0x180030a3c`
- `0x180031e94`
- `0x180033aa8`
- `0x180033e78`
- `0x18003534c`
- `0x18003547c`
- `0x180035508`
- `0x180036f50`
- `0x180037350`
- `0x1800390fd`
- `0x1800398bc`
- `0x180039a18`
- `0x180040e04`
- `0x180048cdc`
- `0x180057d74`
- `0x18005af50`
- `0x18005afe8`
- `0x18005b1b4`
- `0x18005b23c`
- `0x18005b3b8`
- `0x18005b414`
- `0x18005b470`
- `0x18005b734`
- `0x18005bab0`
- `0x18005cb10`
- `0x18005de40`
- `0x18005df28`
- `0x18005e138`
- `0x18005e604`
- `0x18005ea4c`
- `0x18005f8fc`
- `0x18005f950`
- `0x180071010`

## import_xrefs

- `SHELL32!SHFileOperationW` at `0x18005d7bf`
- `SHELL32!SHFileOperationW` at `0x18005d7bf`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18005d7e5`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18005d7e5`
- `archiveint!archive_write_set_bytes_per_block` at `0x18005cec8`
- `archiveint!archive_write_set_bytes_per_block` at `0x18005cec8`
- `archiveint!archive_error_string` at `0x18005cc02`
- `archiveint!archive_error_string` at `0x18005ccbe`
- `archiveint!archive_error_string` at `0x18005cd80`
- `archiveint!archive_error_string` at `0x18005ce42`
- `archiveint!archive_error_string` at `0x18005cf2b`
- `archiveint!archive_error_string` at `0x18005cc02`
- `archiveint!archive_error_string` at `0x18005ccbe`
- `archiveint!archive_error_string` at `0x18005cd80`
- `archiveint!archive_error_string` at `0x18005ce42`
- `archiveint!archive_error_string` at `0x18005cf2b`
- `archiveint!archive_errno` at `0x18005cbe8`
- `archiveint!archive_errno` at `0x18005cca4`
- `archiveint!archive_errno` at `0x18005cd66`
- `archiveint!archive_errno` at `0x18005ce28`
- `archiveint!archive_errno` at `0x18005cf11`
- `archiveint!archive_errno` at `0x18005cbe8`
- `archiveint!archive_errno` at `0x18005cca4`
- `archiveint!archive_errno` at `0x18005cd66`
- `archiveint!archive_errno` at `0x18005ce28`
- `archiveint!archive_errno` at `0x18005cf11`
- `archiveint!archive_entry_linkresolver_free` at `0x18005d019`
- `archiveint!archive_entry_linkresolver_free` at `0x18005d019`
- `archiveint!archive_entry_sourcepath_w` at `0x18005d85e`
- `archiveint!archive_entry_sourcepath_w` at `0x18005d85e`
- `archiveint!archive_entry_linkify` at `0x18005d5f4`
- `archiveint!archive_entry_linkify` at `0x18005d5f4`
- `archiveint!archive_entry_linkresolver_set_strategy` at `0x18005d07a`
- `archiveint!archive_entry_linkresolver_set_strategy` at `0x18005d07a`
- `archiveint!archive_entry_linkresolver_new` at `0x18005cffa`
- `archiveint!archive_entry_linkresolver_new` at `0x18005cffa`
- `archiveint!archive_entry_new2` at `0x18005cfad`
- `archiveint!archive_entry_new2` at `0x18005cfad`
- `archiveint!archive_write_open` at `0x18005cf00`
- `archiveint!archive_write_open` at `0x18005cf00`
- `archiveint!archive_write_set_bytes_in_last_block` at `0x18005ceda`
- `archiveint!archive_write_set_bytes_in_last_block` at `0x18005ceda`
- `archiveint!archive_write_set_option` at `0x18005cd55`
- `archiveint!archive_write_set_option` at `0x18005ce17`
- `archiveint!archive_write_set_option` at `0x18005cd55`
- `archiveint!archive_write_set_option` at `0x18005ce17`
- `archiveint!archive_write_add_filter` at `0x18005cc93`
- `archiveint!archive_write_add_filter` at `0x18005cc93`
- `archiveint!archive_write_set_options` at `0x18005cc87`
- `archiveint!archive_write_set_options` at `0x18005cc87`
- `archiveint!archive_write_set_format` at `0x18005cbd7`
- `archiveint!archive_write_set_format` at `0x18005cbd7`
- `archiveint!archive_write_new` at `0x18005cb84`
- `archiveint!archive_write_new` at `0x18005cb84`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005d1ed`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005d758`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005d1ed`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005d758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d762`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005d134`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005d134`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005d888`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005d888`

## string_xrefs

- `0x18005cbb0`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005cc24`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005cc5a`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005cce0`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005cd16`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005cda2`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005cdd8`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005ce64`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005ce9a`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005cf4d`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005cf83`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005cfd4`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005d042`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005d0e5`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005d14b`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005d1a3`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005d328`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005d415`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005d4d0`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005d623`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005d8c1`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005d942`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005ce0b`: `compression-level`
- `0x18005cd49`: `compression`
- `0x18005cb4c`: `CompressTo`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
CreateArchive *__fastcall CreateArchiveImpl::CreateArchive(CreateArchive *this)
{
  const unsigned __int16 *v2; // rbx
  _QWORD *v3; // rbx
  __int64 v4; // rax
  const char *v5; // r9
  CreateArchive *result; // rax
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  int v10; // edi
  const char *v11; // rax
  int v12; // eax
  const char *v13; // rax
  int v14; // eax
  const char *v15; // rax
  int v16; // eax
  const char *v17; // rax
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  const char *v21; // rax
  struct archive_entry **v22; // r13
  __int64 v23; // rax
  __int64 v24; // rsi
  __int64 v25; // r14
  __int64 v26; // rdx
  unsigned int v27; // eax
  void *v28; // rax
  void *v29; // rcx
  _QWORD *v30; // r14
  HRESULT Instance; // eax
  unsigned int v32; // esi
  int v33; // eax
  unsigned int v34; // esi
  _QWORD *v35; // rax
  const WCHAR ***v36; // rax
  const WCHAR **v37; // r15
  const WCHAR **v38; // r12
  __int64 v39; // rax
  int ExtendedLengthPath; // eax
  unsigned int v41; // esi
  int v42; // eax
  unsigned int v43; // esi
  const WCHAR ***v44; // rax
  const WCHAR **v45; // r14
  const WCHAR **v46; // r15
  __int64 v47; // rax
  int v48; // eax
  unsigned int v49; // esi
  int v50; // ebx
  __int64 v51; // r9
  _QWORD **v52; // rax
  _QWORD *v53; // rcx
  __int64 v54; // rbx
  __int64 v55; // r8
  unsigned __int64 v56; // rax
  const WCHAR *v57; // r15
  const void ***v58; // rax
  const void **v59; // r12
  const void **v60; // r14
  WCHAR *v61; // rsi
  _WORD *v62; // rdx
  size_t v63; // rbx
  signed int v64; // eax
  bool v65; // sf
  const WCHAR *v66; // rax
  char *FileW; // rax
  const char *v68; // r9
  int v69; // eax
  unsigned int v70; // esi
  unsigned int LastError; // ebx
  CreateArchive *v72; // [rsp+40h] [rbp-6F8h] BYREF
  char v73; // [rsp+48h] [rbp-6F0h]
  char *v74; // [rsp+58h] [rbp-6E0h] BYREF
  struct _SHFILEOPSTRUCTW FileOp; // [rsp+60h] [rbp-6D8h] BYREF
  const WCHAR *v76; // [rsp+A0h] [rbp-698h] BYREF
  __int64 v77; // [rsp+A8h] [rbp-690h]
  _OWORD v78[2]; // [rsp+B0h] [rbp-688h] BYREF
  int v79; // [rsp+D0h] [rbp-668h] BYREF
  _QWORD *v80; // [rsp+D8h] [rbp-660h]
  __int64 v81; // [rsp+E0h] [rbp-658h]
  __int64 v82; // [rsp+E8h] [rbp-650h] BYREF
  __int128 v83; // [rsp+F0h] [rbp-648h]
  __int64 v84; // [rsp+100h] [rbp-638h]
  __int64 v85; // [rsp+108h] [rbp-630h]
  _BYTE v86[64]; // [rsp+110h] [rbp-628h] BYREF
  _BYTE v87[64]; // [rsp+150h] [rbp-5E8h] BYREF
  _QWORD v88[42]; // [rsp+190h] [rbp-5A8h] BYREF
  WCHAR Buffer[264]; // [rsp+2E0h] [rbp-458h] BYREF
  WCHAR v90[264]; // [rsp+4F0h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+738h] [rbp+0h]

  v2 = (const unsigned __int16 *)CreateArchiveOptions::PreferredExtension(this, &v72);
  wil::ActivityBase<ArchiveFolderTelemetry,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ArchiveFolderTelemetry,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>(
    v88,
    "CompressTo");
  try
  {
    v88[0] = &ArchiveFolderTelemetry::CompressTo::`vftable';
    ArchiveFolderTelemetry::CompressTo::StartActivity((ArchiveFolderTelemetry::CompressTo *)v88, v2);
    v3 = (_QWORD *)((char *)this + 64);
    v4 = archive_write_new();
    wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_write_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::reset(
      (char *)this + 64,
      v4);
    if ( !*((_QWORD *)this + 8) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
        (const char *)0x8007000ELL);
      ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
      return (CreateArchive *)2147942414LL;
    }
    v7 = archive_write_set_format(*((_QWORD *)this + 8), *(unsigned int *)this);
    v8 = *v3;
    if ( v7 )
    {
      v9 = archive_errno(v8);
      if ( !v9 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x53,
          (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
          (const char *)0x80004005LL);
        ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
        return (CreateArchive *)2147500037LL;
      }
      v10 = HRESULT_FROM_ERRNO(v9);
      if ( v10 < 0 )
      {
        v11 = (const char *)archive_error_string(*v3);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x53,
          (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
          (const char *)(unsigned int)v10,
          (int)"archive error: %hs",
          v11);
      }
      goto LABEL_34;
    }
    archive_write_set_options(v8, "hdrcharset=UTF-8");
    if ( (unsigned int)archive_write_add_filter(*v3, *((unsigned int *)this + 1)) )
    {
      v12 = archive_errno(*v3);
      if ( !v12 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x58,
          (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
          (const char *)0x80004005LL);
        ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
        return (CreateArchive *)2147500037LL;
      }
      v10 = HRESULT_FROM_ERRNO(v12);
      if ( v10 < 0 )
      {
        v13 = (const char *)archive_error_string(*v3);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x58,
          (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
          (const char *)(unsigned int)v10,
          (int)"archive error: %hs",
          v13);
      }
      goto LABEL_34;
    }
    if ( *((_QWORD *)this + 2) && (unsigned int)archive_write_set_option(*v3, 0, "compression") )
    {
      v14 = archive_errno(*v3);
      if ( !v14 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5C,
          (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
          (const char *)0x80004005LL);
        ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
        return (CreateArchive *)2147500037LL;
      }
      v10 = HRESULT_FROM_ERRNO(v14);
      if ( v10 < 0 )
      {
        v15 = (const char *)archive_error_string(*v3);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x5C,
          (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
          (const char *)(unsigned int)v10,
          (int)"archive error: %hs",
          v15);
      }
      goto LABEL_34;
    }
    if ( *((_QWORD *)this + 3) && (unsigned int)archive_write_set_option(*v3, 0, "compression-level") )
    {
      v16 = archive_errno(*v3);
      if ( !v16 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x62,
          (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
          (const char *)0x80004005LL);
        ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
        return (CreateArchive *)2147500037LL;
      }
      v10 = HRESULT_FROM_ERRNO(v16);
      if ( v10 < 0 )
      {
        v17 = (const char *)archive_error_string(*v3);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x62,
          (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
          (const char *)(unsigned int)v10,
          (int)"archive error: %hs",
          v17);
      }
      goto LABEL_34;
    }
    archive_write_set_bytes_per_block(*v3, 10240);
    archive_write_set_bytes_in_last_block(*v3, 1);
    v18 = archive_write_open(
            *v3,
            this,
            winrt::implements<ArchiveFolder,IShellFolder2,IPersistFolder2,IFolderType,IExplorerPaneVisibility,IShellIconOverlay>::find_inspectable,
            lambda_36b85dbb2352314519a4da0def15ca0c_::_lambda_invoker_cdecl_,
            winrt::implements<ArchiveFolder,IShellFolder2,IPersistFolder2,IFolderType,IExplorerPaneVisibility,IShellIconOverlay>::find_inspectable);
    v19 = *v3;
    if ( v18 )
    {
      v20 = archive_errno(v19);
      if ( !v20 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x87,
          (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
          (const char *)0x80004005LL);
        ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
        return (CreateArchive *)2147500037LL;
      }
      v10 = HRESULT_FROM_ERRNO(v20);
      if ( v10 < 0 )
      {
        v21 = (const char *)archive_error_string(*v3);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x87,
          (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
          (const char *)(unsigned int)v10,
          (int)"archive error: %hs",
          v21);
      }
LABEL_34:
      ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
      return (CreateArchive *)(unsigned int)v10;
    }
    v22 = (struct archive_entry **)((char *)this + 72);
    v23 = archive_entry_new2(v19);
    wil::details::unique_storage<wil::details::resource_policy<archive_entry *,void (*)(archive_entry *),&void archive_entry_free(archive_entry *),wistd::integral_constant<unsigned __int64,0>,archive_entry *,archive_entry *,0,std::nullptr_t>>::reset(
      (char *)this + 72,
      v23);
    if ( !*((_QWORD *)this + 9) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
        (const char *)0x8007000ELL);
      ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
      return (CreateArchive *)2147942414LL;
    }
    v24 = archive_entry_linkresolver_new();
    v25 = *((_QWORD *)this + 10);
    if ( v25 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v74);
      archive_entry_linkresolver_free(v25);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v74);
    }
    *((_QWORD *)this + 10) = v24;
    if ( !v24 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
        (const char *)0x8007000ELL);
      ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
      return (CreateArchive *)2147942414LL;
    }
    if ( *((_BYTE *)this + 9) )
      v26 = *(unsigned int *)this;
    else
      v26 = 589824;
    archive_entry_linkresolver_set_strategy(v24, v26);
    v27 = 0x20000;
    *((_DWORD *)this + 50) = 0x20000;
    while ( 1 )
    {
      v28 = operator new[](v27, (const struct std::nothrow_t *)&std::nothrow);
      v29 = (void *)*((_QWORD *)this + 24);
      *((_QWORD *)this + 24) = v28;
      if ( v29 )
        operator delete(v29);
      if ( *((_QWORD *)this + 24) )
        break;
      *((_DWORD *)this + 50) >>= 1;
      v27 = *((_DWORD *)this + 50);
      if ( v27 < 0x400 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9C,
          (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
          (const char *)0x8007000ELL);
        ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
        return (CreateArchive *)2147942414LL;
      }
    }
    v30 = (_QWORD *)((char *)this + 88);
    if ( *((_QWORD *)this + 11) )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref((char *)this + 88);
    Instance = CoCreateInstance(
                 &CLSID_ProgressDialog,
                 0,
                 1u,
                 &GUID_ebbc7c04_315e_11d2_b62f_006097df5bd4,
                 (LPVOID *)this + 11);
    v32 = Instance;
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9F,
        (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
        (const char *)(unsigned int)Instance);
      ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
      return (CreateArchive *)v32;
    }
    v33 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _QWORD))(*(_QWORD *)*v30 + 24LL))(
            *v30,
            *((_QWORD *)this + 6),
            0,
            2,
            0);
    v34 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
        (const char *)(unsigned int)v33);
      ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
      return (CreateArchive *)v34;
    }
    v72 = this;
    v73 = 1;
    LoadStringW(&_ImageBase, 0x276Bu, Buffer, 260);
    (*(void (__fastcall **)(_QWORD, WCHAR *))(*(_QWORD *)*v30 + 40LL))(*v30, Buffer);
    v78[0] = 0;
    v78[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v78[0]) = 0;
    std::unordered_set<long>::unordered_set<long>(v87);
    std::unordered_set<std::wstring>::unordered_set<std::wstring>(v86);
    v79 = 0;
    v80 = 0;
    v81 = 0;
    v35 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(32);
    *v35 = v35;
    v35[1] = v35;
    v80 = v35;
    v82 = 0;
    v83 = 0;
    v84 = 7;
    v85 = 8;
    v79 = 1065353216;
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
      &v82,
      16,
      v35);
    v36 = (const WCHAR ***)*((_QWORD *)this + 5);
    v37 = *v36;
    v38 = v36[1];
    while ( 1 )
    {
      v39 = -1;
      if ( v37 == v38 )
        break;
      do
        ++v39;
      while ( (*v37)[v39] );
      v76 = *v37;
      v77 = v39;
      ExtendedLengthPath = MakeExtendedLengthPath(&v76, v78);
      v41 = ExtendedLengthPath;
      if ( ExtendedLengthPath < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB5,
          (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
          (const char *)(unsigned int)ExtendedLengthPath);
        std::_Hash<std::_Uset_traits<std::pair<unsigned __int64,unsigned __int64>,std::_Uhash_compare<std::pair<unsigned __int64,unsigned __int64>,tuple_hash,std::equal_to<std::pair<unsigned __int64,unsigned __int64>>>,std::allocator<std::pair<unsigned __int64,unsigned __int64>>,0>>::~_Hash<std::_Uset_traits<std::pair<unsigned __int64,unsigned __int64>,std::_Uhash_compare<std::pair<unsigned __int64,unsigned __int64>,tuple_hash,std::equal_to<std::pair<unsigned __int64,unsigned __int64>>>,std::allocator<std::pair<unsigned __int64,unsigned __int64>>,0>>(&v79);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v86);
        std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::~_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>(v87);
        std::wstring::_Tidy_deallocate(v78);
        v73 = 0;
        lambda_52c38641fa72ba168eaf783a9810bda8_::operator()(&v72);
        ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
        return (CreateArchive *)v41;
      }
      FileOp.hwnd = (HWND)v87;
      *(_QWORD *)&FileOp.wFunc = this;
      FileOp.pFrom = (PCZZWSTR)v86;
      FileOp.pTo = (PCZZWSTR)&v79;
      enumerate_path__lambda_c85309403f21122c925928639243c58a_(v78, &FileOp);
      ++v37;
    }
    std::_Hash<std::_Uset_traits<std::pair<unsigned __int64,unsigned __int64>,std::_Uhash_compare<std::pair<unsigned __int64,unsigned __int64>,tuple_hash,std::equal_to<std::pair<unsigned __int64,unsigned __int64>>>,std::allocator<std::pair<unsigned __int64,unsigned __int64>>,0>>::~_Hash<std::_Uset_traits<std::pair<unsigned __int64,unsigned __int64>,std::_Uhash_compare<std::pair<unsigned __int64,unsigned __int64>,tuple_hash,std::equal_to<std::pair<unsigned __int64,unsigned __int64>>>,std::allocator<std::pair<unsigned __int64,unsigned __int64>>,0>>(&v79);
    v42 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v30 + 72LL))(
            *v30,
            *((_QWORD *)this + 13),
            *((_QWORD *)this + 12));
    v43 = v42;
    if ( v42 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF7,
        (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
        (const char *)(unsigned int)v42);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v86);
      std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::~_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>(v87);
      std::wstring::_Tidy_deallocate(v78);
      v73 = 0;
      lambda_52c38641fa72ba168eaf783a9810bda8_::operator()(&v72);
      ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
      return (CreateArchive *)v43;
    }
    v44 = (const WCHAR ***)*((_QWORD *)this + 5);
    v45 = *v44;
    v46 = v44[1];
    while ( v45 != v46 )
    {
      v47 = -1;
      do
        ++v47;
      while ( (*v45)[v47] );
      v76 = *v45;
      v77 = v47;
      v48 = MakeExtendedLengthPath(&v76, v78);
      v49 = v48;
      if ( v48 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFB,
          (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
          (const char *)(unsigned int)v48);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v86);
        std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::~_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>(v87);
        std::wstring::_Tidy_deallocate(v78);
        v73 = 0;
        lambda_52c38641fa72ba168eaf783a9810bda8_::operator()(&v72);
        ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
        return (CreateArchive *)v49;
      }
      FileOp.hwnd = (HWND)v86;
      *(_QWORD *)&FileOp.wFunc = v87;
      FileOp.pFrom = (PCZZWSTR)this;
      enumerate_path__lambda_94ba8ce0435b1f69c01c8b0462c8682c_(v78, &FileOp);
      if ( *((_BYTE *)this + 120) )
      {
        wil::ActivityBase<ArchiveFolderTelemetry,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(
          v88,
          2147943623LL);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v86);
        std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::~_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>(v87);
        std::wstring::_Tidy_deallocate(v78);
        v73 = 0;
        lambda_52c38641fa72ba168eaf783a9810bda8_::operator()(&v72);
        ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
        return (CreateArchive *)2147943623LL;
      }
      ++v45;
    }
    while ( 1 )
    {
      v76 = 0;
      wil::details::unique_storage<wil::details::resource_policy<archive_entry *,void (*)(archive_entry *),&void archive_entry_free(archive_entry *),wistd::integral_constant<unsigned __int64,0>,archive_entry *,archive_entry *,0,std::nullptr_t>>::reset(
        (char *)this + 72,
        0);
      archive_entry_linkify(*((_QWORD *)this + 10), (char *)this + 72, &v76);
      if ( !*v22 )
        break;
      v66 = (const WCHAR *)archive_entry_sourcepath_w();
      FileW = (char *)CreateFileW(v66, 0x80000000, 1u, 0, 3u, 0x2200000u, 0);
      v74 = FileW;
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x165,
                      (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
                      v68);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v74);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v86);
        std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::~_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>(v87);
        std::wstring::_Tidy_deallocate(v78);
        v73 = 0;
        lambda_52c38641fa72ba168eaf783a9810bda8_::operator()(&v72);
        ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
        return (CreateArchive *)LastError;
      }
      v69 = CreateArchiveImpl::WriteEntryToArchive(this, *v22, FileW);
      v70 = v69;
      if ( v69 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x166,
          (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
          (const char *)(unsigned int)v69);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v74);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v86);
        std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::~_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>(v87);
        std::wstring::_Tidy_deallocate(v78);
        v73 = 0;
        lambda_52c38641fa72ba168eaf783a9810bda8_::operator()(&v72);
        ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
        return (CreateArchive *)v70;
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v74);
    }
    wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&int archive_write_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::reset(
      (char *)this + 64,
      0);
    v50 = *((_DWORD *)this + 31);
    if ( v50 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x172,
        (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
        (const char *)(unsigned int)v50);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v86);
      std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::~_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>(v87);
      std::wstring::_Tidy_deallocate(v78);
      v73 = 0;
      lambda_52c38641fa72ba168eaf783a9810bda8_::operator()(&v72);
      ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
      return (CreateArchive *)(unsigned int)v50;
    }
    if ( !*((_BYTE *)this + 56) )
    {
LABEL_99:
      wil::ActivityBase<ArchiveFolderTelemetry,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(
        v88,
        0);
      *((_QWORD *)this + 4) = -1;
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v86);
      std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::~_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>(v87);
      std::wstring::_Tidy_deallocate(v78);
      v73 = 0;
      lambda_52c38641fa72ba168eaf783a9810bda8_::operator()(&v72);
      ArchiveFolderTelemetry::CompressTo::~CompressTo((ArchiveFolderTelemetry::CompressTo *)v88);
      return 0;
    }
    v51 = 0;
    v52 = (_QWORD **)*((_QWORD *)this + 5);
    v53 = *v52;
    v54 = -1;
    while ( v53 != v52[1] )
    {
      v55 = -1;
      do
        ++v55;
      while ( *(_WORD *)(*v53 + 2 * v55) );
      v51 += v55 + 1;
      ++v53;
    }
    v56 = 2 * (v51 + 1);
    if ( !is_mul_ok(v51 + 1, 2u) )
      v56 = -1;
    v57 = (const WCHAR *)operator new[](v56, (const struct std::nothrow_t *)&std::nothrow);
    v76 = v57;
    if ( v57 )
    {
      v58 = (const void ***)*((_QWORD *)this + 5);
      v59 = v58[1];
      v60 = *v58;
      v61 = (WCHAR *)v57;
      while ( v60 != v59 )
      {
        v62 = *v60;
        do
          ++v54;
        while ( v62[v54] );
        v63 = 2 * v54 + 2;
        memcpy_0(v61, v62, v63);
        v61 = (WCHAR *)((char *)v61 + v63);
        ++v60;
        v54 = -1;
      }
      *v61 = 0;
      if ( LoadStringW(&_ImageBase, 0x276Du, v90, 260) )
      {
        FileOp.hwnd = (HWND)*((_QWORD *)this + 6);
        *(_QWORD *)&FileOp.wFunc = 3;
        FileOp.pFrom = v57;
        FileOp.pTo = 0;
        *(_QWORD *)&FileOp.fFlags = 272;
        FileOp.hNameMappings = 0;
        FileOp.lpszProgressTitle = v90;
        if ( !SHFileOperationW(&FileOp) )
        {
LABEL_98:
          Microsoft::WRL::Details::MakeAllocator<CLocalCopyDownloadSink>::~MakeAllocator<CLocalCopyDownloadSink>(&v76);
          goto LABEL_99;
        }
      }
      else
      {
        v64 = GetLastError();
        v65 = v64 < 0;
        if ( v64 > 0 )
          v65 = 1;
        if ( !v65 )
          goto LABEL_98;
      }
    }
    ShellMessageBoxW(&_ImageBase, *((HWND *)this + 6), (LPCWSTR)0x2772, (LPCWSTR)0x2941, 0);
    goto LABEL_98;
  }
  catch ( ... )
  {
    return (CreateArchive *)(unsigned int)wil::details::in1diag3::Return_CaughtException(
                                            retaddr,
                                            (void *)0x1B4,
                                            (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
                                            v5);
  }
  return result;
}

```

## disassembly

```asm
0x18005cb10  mov     [rsp+arg_8], rbx
0x18005cb15  mov     [rsp+arg_10], rsi
0x18005cb1a  push    rdi
0x18005cb1b  push    r12
0x18005cb1d  push    r13
0x18005cb1f  push    r14
0x18005cb21  push    r15
0x18005cb23  sub     rsp, 710h
0x18005cb2a  mov     rax, cs:__security_cookie
0x18005cb31  xor     rax, rsp
0x18005cb34  mov     [rsp+738h+var_38], rax
0x18005cb3c  mov     rdi, rcx
0x18005cb3f  lea     rdx, [rsp+738h+var_6F8]
0x18005cb44  call    ?PreferredExtension@CreateArchiveOptions@@QEAA?AV?$array@G$08@std@@XZ; CreateArchiveOptions::PreferredExtension(void)
0x18005cb49  mov     rbx, rax
0x18005cb4c  lea     rdx, aCompressto; "CompressTo"
0x18005cb53  lea     rcx, [rsp+738h+var_5A8]
0x18005cb5b  call    ??0?$ActivityBase@VArchiveFolderTelemetry@@$00$0CAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ArchiveFolderTelemetry,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ArchiveFolderTelemetry,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18005cb60  lea     rax, ??_7CompressTo@ArchiveFolderTelemetry@@6B@; const ArchiveFolderTelemetry::CompressTo::`vftable'
0x18005cb67  mov     [rsp+738h+var_5A8], rax
0x18005cb6f  mov     rdx, rbx; unsigned __int16 *
0x18005cb72  lea     rcx, [rsp+738h+var_5A8]; this
0x18005cb7a  call    ?StartActivity@CompressTo@ArchiveFolderTelemetry@@QEAAXPEBG@Z; ArchiveFolderTelemetry::CompressTo::StartActivity(ushort const *)
0x18005cb7f  nop
0x18005cb80  lea     rbx, [rdi+40h]
0x18005cb84  call    cs:__imp_archive_write_new
0x18005cb8a  mov     rdx, rax
0x18005cb8d  mov     rcx, rbx
0x18005cb90  call    ?reset@?$unique_storage@U?$resource_policy@PEAUarchive@@P6AHPEAU1@@Z$1?archive_write_free@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUarchive@@@Z; wil::details::unique_storage<wil::details::resource_policy<archive *,int (*)(archive *),&archive_write_free(archive *),wistd::integral_constant<unsigned __int64,0>,archive *,archive *,0,std::nullptr_t>>::reset(archive *)
0x18005cb95  mov     rcx, [rbx]
0x18005cb98  xor     r15d, r15d
0x18005cb9b  test    rcx, rcx
0x18005cb9e  jnz     short loc_18005CBD5
0x18005cba0  mov     rcx, [rsp+738h]
0x18005cba8  mov     ebx, 8007000Eh
0x18005cbad  mov     r9d, ebx
0x18005cbb0  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005cbb7  lea     edx, [r15+52h]
0x18005cbbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cbc0  nop
0x18005cbc1  lea     rcx, [rsp+738h+var_5A8]; this
0x18005cbc9  call    ??1CompressTo@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::CompressTo::~CompressTo(void)
0x18005cbce  mov     eax, ebx
0x18005cbd0  jmp     loc_18005D9AF
0x18005cbd5  mov     edx, [rdi]
0x18005cbd7  call    cs:__imp_archive_write_set_format
0x18005cbdd  mov     rcx, [rbx]
0x18005cbe0  test    eax, eax
0x18005cbe2  jz      loc_18005CC80
0x18005cbe8  call    cs:__imp_archive_errno
0x18005cbee  test    eax, eax
0x18005cbf0  jz      short loc_18005CC4A
0x18005cbf2  mov     ecx, eax; int
0x18005cbf4  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x18005cbf9  mov     edi, eax
0x18005cbfb  test    eax, eax
0x18005cbfd  jns     short loc_18005CC36
0x18005cbff  mov     rcx, [rbx]
0x18005cc02  call    cs:__imp_archive_error_string
0x18005cc08  mov     rcx, [rsp+738h]; this
0x18005cc10  mov     qword ptr [rsp+738h+dwFlagsAndAttributes], rax; char *
0x18005cc15  lea     rdx, aArchiveErrorHs; "archive error: %hs"
0x18005cc1c  mov     [rsp+738h+ppv], rdx; int
0x18005cc21  mov     r9d, edi; char *
0x18005cc24  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005cc2b  mov     edx, 53h ; 'S'; void *
0x18005cc30  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005cc35  nop
0x18005cc36  lea     rcx, [rsp+738h+var_5A8]; this
0x18005cc3e  call    ??1CompressTo@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::CompressTo::~CompressTo(void)
0x18005cc43  mov     eax, edi
0x18005cc45  jmp     loc_18005D9AF
0x18005cc4a  mov     rcx, [rsp+738h]
0x18005cc52  mov     ebx, 80004005h
0x18005cc57  mov     r9d, ebx
0x18005cc5a  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005cc61  mov     edx, 53h ; 'S'
0x18005cc66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cc6b  nop
0x18005cc6c  lea     rcx, [rsp+738h+var_5A8]; this
0x18005cc74  call    ??1CompressTo@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::CompressTo::~CompressTo(void)
0x18005cc79  mov     eax, ebx
0x18005cc7b  jmp     loc_18005D9AF
0x18005cc80  lea     rdx, aHdrcharsetUtf8; "hdrcharset=UTF-8"
0x18005cc87  call    cs:__imp_archive_write_set_options
0x18005cc8d  mov     edx, [rdi+4]
0x18005cc90  mov     rcx, [rbx]
0x18005cc93  call    cs:__imp_archive_write_add_filter
0x18005cc99  test    eax, eax
0x18005cc9b  jz      loc_18005CD3C
0x18005cca1  mov     rcx, [rbx]
0x18005cca4  call    cs:__imp_archive_errno
0x18005ccaa  test    eax, eax
0x18005ccac  jz      short loc_18005CD06
0x18005ccae  mov     ecx, eax; int
0x18005ccb0  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x18005ccb5  mov     edi, eax
0x18005ccb7  test    eax, eax
0x18005ccb9  jns     short loc_18005CCF2
0x18005ccbb  mov     rcx, [rbx]
0x18005ccbe  call    cs:__imp_archive_error_string
0x18005ccc4  mov     rcx, [rsp+738h]; this
0x18005cccc  mov     qword ptr [rsp+738h+dwFlagsAndAttributes], rax; char *
0x18005ccd1  lea     rdx, aArchiveErrorHs; "archive error: %hs"
0x18005ccd8  mov     [rsp+738h+ppv], rdx; int
0x18005ccdd  mov     r9d, edi; char *
0x18005cce0  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005cce7  mov     edx, 58h ; 'X'; void *
0x18005ccec  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005ccf1  nop
0x18005ccf2  lea     rcx, [rsp+738h+var_5A8]; this
0x18005ccfa  call    ??1CompressTo@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::CompressTo::~CompressTo(void)
0x18005ccff  mov     eax, edi
0x18005cd01  jmp     loc_18005D9AF
0x18005cd06  mov     rcx, [rsp+738h]
0x18005cd0e  mov     ebx, 80004005h
0x18005cd13  mov     r9d, ebx
0x18005cd16  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005cd1d  mov     edx, 58h ; 'X'
0x18005cd22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cd27  nop
0x18005cd28  lea     rcx, [rsp+738h+var_5A8]; this
0x18005cd30  call    ??1CompressTo@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::CompressTo::~CompressTo(void)
0x18005cd35  mov     eax, ebx
0x18005cd37  jmp     loc_18005D9AF
0x18005cd3c  mov     r9, [rdi+10h]
0x18005cd40  test    r9, r9
0x18005cd43  jz      loc_18005CDFE
0x18005cd49  lea     r8, aCompression; "compression"
0x18005cd50  xor     edx, edx
0x18005cd52  mov     rcx, [rbx]
0x18005cd55  call    cs:__imp_archive_write_set_option
0x18005cd5b  test    eax, eax
0x18005cd5d  jz      loc_18005CDFE
0x18005cd63  mov     rcx, [rbx]
0x18005cd66  call    cs:__imp_archive_errno
0x18005cd6c  test    eax, eax
0x18005cd6e  jz      short loc_18005CDC8
0x18005cd70  mov     ecx, eax; int
0x18005cd72  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x18005cd77  mov     edi, eax
0x18005cd79  test    eax, eax
0x18005cd7b  jns     short loc_18005CDB4
0x18005cd7d  mov     rcx, [rbx]
0x18005cd80  call    cs:__imp_archive_error_string
0x18005cd86  mov     rcx, [rsp+738h]; this
0x18005cd8e  mov     qword ptr [rsp+738h+dwFlagsAndAttributes], rax; char *
0x18005cd93  lea     rdx, aArchiveErrorHs; "archive error: %hs"
0x18005cd9a  mov     [rsp+738h+ppv], rdx; int
0x18005cd9f  mov     r9d, edi; char *
0x18005cda2  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005cda9  mov     edx, 5Ch ; '\'; void *
0x18005cdae  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005cdb3  nop
0x18005cdb4  lea     rcx, [rsp+738h+var_5A8]; this
0x18005cdbc  call    ??1CompressTo@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::CompressTo::~CompressTo(void)
0x18005cdc1  mov     eax, edi
0x18005cdc3  jmp     loc_18005D9AF
0x18005cdc8  mov     rcx, [rsp+738h]
0x18005cdd0  mov     ebx, 80004005h
0x18005cdd5  mov     r9d, ebx
0x18005cdd8  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005cddf  mov     edx, 5Ch ; '\'
0x18005cde4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cde9  nop
0x18005cdea  lea     rcx, [rsp+738h+var_5A8]; this
0x18005cdf2  call    ??1CompressTo@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::CompressTo::~CompressTo(void)
0x18005cdf7  mov     eax, ebx
0x18005cdf9  jmp     loc_18005D9AF
0x18005cdfe  mov     r9, [rdi+18h]
0x18005ce02  test    r9, r9
0x18005ce05  jz      loc_18005CEC0
0x18005ce0b  lea     r8, aCompressionLev; "compression-level"
0x18005ce12  xor     edx, edx
0x18005ce14  mov     rcx, [rbx]
0x18005ce17  call    cs:__imp_archive_write_set_option
0x18005ce1d  test    eax, eax
0x18005ce1f  jz      loc_18005CEC0
0x18005ce25  mov     rcx, [rbx]
0x18005ce28  call    cs:__imp_archive_errno
0x18005ce2e  test    eax, eax
0x18005ce30  jz      short loc_18005CE8A
0x18005ce32  mov     ecx, eax; int
0x18005ce34  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x18005ce39  mov     edi, eax
0x18005ce3b  test    eax, eax
0x18005ce3d  jns     short loc_18005CE76
0x18005ce3f  mov     rcx, [rbx]
0x18005ce42  call    cs:__imp_archive_error_string
0x18005ce48  mov     rcx, [rsp+738h]; this
0x18005ce50  mov     qword ptr [rsp+738h+dwFlagsAndAttributes], rax; char *
0x18005ce55  lea     rdx, aArchiveErrorHs; "archive error: %hs"
0x18005ce5c  mov     [rsp+738h+ppv], rdx; int
0x18005ce61  mov     r9d, edi; char *
0x18005ce64  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005ce6b  mov     edx, 62h ; 'b'; void *
0x18005ce70  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005ce75  nop
0x18005ce76  lea     rcx, [rsp+738h+var_5A8]; this
0x18005ce7e  call    ??1CompressTo@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::CompressTo::~CompressTo(void)
0x18005ce83  mov     eax, edi
0x18005ce85  jmp     loc_18005D9AF
0x18005ce8a  mov     rcx, [rsp+738h]
0x18005ce92  mov     ebx, 80004005h
0x18005ce97  mov     r9d, ebx
0x18005ce9a  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005cea1  mov     edx, 62h ; 'b'
0x18005cea6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ceab  nop
0x18005ceac  lea     rcx, [rsp+738h+var_5A8]; this
0x18005ceb4  call    ??1CompressTo@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::CompressTo::~CompressTo(void)
0x18005ceb9  mov     eax, ebx
0x18005cebb  jmp     loc_18005D9AF
0x18005cec0  mov     edx, 2800h
0x18005cec5  mov     rcx, [rbx]
0x18005cec8  call    cs:__imp_archive_write_set_bytes_per_block
0x18005cece  mov     r12d, 1
0x18005ced4  mov     edx, r12d
0x18005ced7  mov     rcx, [rbx]
0x18005ceda  call    cs:__imp_archive_write_set_bytes_in_last_block
0x18005cee0  lea     rax, ?find_inspectable@?$implements@VArchiveFolder@@UIShellFolder2@@UIPersistFolder2@@UIFolderType@@UIExplorerPaneVisibility@@UIShellIconOverlay@@@winrt@@UEBAPEAUtype@?$abi@UIInspectable@Foundation@Windows@winrt@@X@impl@2@XZ; winrt::implements<ArchiveFolder,IShellFolder2,IPersistFolder2,IFolderType,IExplorerPaneVisibility,IShellIconOverlay>::find_inspectable(void)
0x18005cee7  mov     [rsp+738h+ppv], rax
0x18005ceec  lea     r9, _lambda_36b85dbb2352314519a4da0def15ca0c____lambda_invoker_cdecl_
0x18005cef3  lea     r8, ?find_inspectable@?$implements@VArchiveFolder@@UIShellFolder2@@UIPersistFolder2@@UIFolderType@@UIExplorerPaneVisibility@@UIShellIconOverlay@@@winrt@@UEBAPEAUtype@?$abi@UIInspectable@Foundation@Windows@winrt@@X@impl@2@XZ; winrt::implements<ArchiveFolder,IShellFolder2,IPersistFolder2,IFolderType,IExplorerPaneVisibility,IShellIconOverlay>::find_inspectable(void)
0x18005cefa  mov     rdx, rdi
0x18005cefd  mov     rcx, [rbx]
0x18005cf00  call    cs:__imp_archive_write_open
0x18005cf06  mov     rcx, [rbx]
0x18005cf09  test    eax, eax
0x18005cf0b  jz      loc_18005CFA9
0x18005cf11  call    cs:__imp_archive_errno
0x18005cf17  test    eax, eax
0x18005cf19  jz      short loc_18005CF73
0x18005cf1b  mov     ecx, eax; int
0x18005cf1d  call    ?HRESULT_FROM_ERRNO@@YAJH@Z; HRESULT_FROM_ERRNO(int)
0x18005cf22  mov     edi, eax
0x18005cf24  test    eax, eax
0x18005cf26  jns     short loc_18005CF5F
0x18005cf28  mov     rcx, [rbx]
0x18005cf2b  call    cs:__imp_archive_error_string
0x18005cf31  mov     rcx, [rsp+738h]; this
0x18005cf39  mov     qword ptr [rsp+738h+dwFlagsAndAttributes], rax; char *
0x18005cf3e  lea     rdx, aArchiveErrorHs; "archive error: %hs"
0x18005cf45  mov     [rsp+738h+ppv], rdx; int
0x18005cf4a  mov     r9d, edi; char *
0x18005cf4d  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005cf54  mov     edx, 87h; void *
0x18005cf59  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005cf5e  nop
0x18005cf5f  lea     rcx, [rsp+738h+var_5A8]; this
0x18005cf67  call    ??1CompressTo@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::CompressTo::~CompressTo(void)
0x18005cf6c  mov     eax, edi
0x18005cf6e  jmp     loc_18005D9AF
0x18005cf73  mov     rcx, [rsp+738h]
0x18005cf7b  mov     ebx, 80004005h
0x18005cf80  mov     r9d, ebx
0x18005cf83  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005cf8a  mov     edx, 87h
0x18005cf8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cf94  nop
0x18005cf95  lea     rcx, [rsp+738h+var_5A8]; this
0x18005cf9d  call    ??1CompressTo@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::CompressTo::~CompressTo(void)
0x18005cfa2  mov     eax, ebx
0x18005cfa4  jmp     loc_18005D9AF
0x18005cfa9  lea     r13, [rdi+48h]
0x18005cfad  call    cs:__imp_archive_entry_new2
0x18005cfb3  mov     rdx, rax
0x18005cfb6  mov     rcx, r13
0x18005cfb9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUarchive_entry@@P6AXPEAU1@@Z$1?archive_entry_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUarchive_entry@@@Z; wil::details::unique_storage<wil::details::resource_policy<archive_entry *,void (*)(archive_entry *),&archive_entry_free(archive_entry *),wistd::integral_constant<unsigned __int64,0>,archive_entry *,archive_entry *,0,std::nullptr_t>>::reset(archive_entry *)
0x18005cfbe  cmp     [r13+0], r15
0x18005cfc2  jnz     short loc_18005CFFA
0x18005cfc4  mov     rcx, [rsp+738h]
0x18005cfcc  mov     ebx, 8007000Eh
0x18005cfd1  mov     r9d, ebx
0x18005cfd4  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005cfdb  mov     edx, 8Bh
0x18005cfe0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cfe5  nop
0x18005cfe6  lea     rcx, [rsp+738h+var_5A8]; this
0x18005cfee  call    ??1CompressTo@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::CompressTo::~CompressTo(void)
0x18005cff3  mov     eax, ebx
0x18005cff5  jmp     loc_18005D9AF
0x18005cffa  call    cs:__imp_archive_entry_linkresolver_new
0x18005d000  mov     rsi, rax
0x18005d003  mov     r14, [rdi+50h]
0x18005d007  test    r14, r14
0x18005d00a  jz      short loc_18005D029
0x18005d00c  lea     rcx, [rsp+738h+var_6E0]; this
0x18005d011  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005d016  mov     rcx, r14
0x18005d019  call    cs:__imp_archive_entry_linkresolver_free
0x18005d01f  lea     rcx, [rsp+738h+var_6E0]; this
0x18005d024  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005d029  mov     [rdi+50h], rsi
0x18005d02d  test    rsi, rsi
0x18005d030  jnz     short loc_18005D068
0x18005d032  mov     rcx, [rsp+738h]
0x18005d03a  mov     ebx, 8007000Eh
0x18005d03f  mov     r9d, ebx
0x18005d042  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
  ... truncated ...
```
