# ExtractRegularFile

- ea: `0x180065a94`
- end: `0x180066209`
- name: `ExtractRegularFile`
- size: `1909`
- prototype: `__int64 __fastcall(int, int, int, int, char, LPCVOID, __int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180064cec`

## callees

- `0x180020cbc`
- `0x1800264c8`
- `0x18002abd0`
- `0x180034fbc`
- `0x18003519c`
- `0x18003534c`
- `0x18003547c`
- `0x180036f50`
- `0x1800390f1`
- `0x18003edd4`
- `0x18005fa8c`
- `0x180062684`
- `0x180065a94`
- `0x180067bd0`
- `0x180067bfc`
- `0x180067c5c`
- `0x180068e80`
- `0x180068f88`
- `0x180069114`
- `0x180071010`

## import_xrefs

- `archiveint!archive_read_has_encrypted_entries` at `0x180065fcc`
- `archiveint!archive_read_has_encrypted_entries` at `0x180065fcc`
- `archiveint!archive_error_string` at `0x180065fd9`
- `archiveint!archive_error_string` at `0x180066024`
- `archiveint!archive_error_string` at `0x180065fd9`
- `archiveint!archive_error_string` at `0x180066024`
- `archiveint!archive_errno` at `0x180065f3d`
- `archiveint!archive_errno` at `0x180065fba`
- `archiveint!archive_errno` at `0x180066014`
- `archiveint!archive_errno` at `0x180065f3d`
- `archiveint!archive_errno` at `0x180065fba`
- `archiveint!archive_errno` at `0x180066014`
- `archiveint!archive_read_data_block` at `0x180065d1a`
- `archiveint!archive_read_data_block` at `0x180065d1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065b3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065b3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066158`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180065b97`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180065def`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180065e6b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180065ee5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180065f71`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180066091`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800661c2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180065b97`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180065def`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180065e6b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180065ee5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180065f71`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180066091`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800661c2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180065b15`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180065d6c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180065b15`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180065d6c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180065b4d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180065b4d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180065b86`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180065b86`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ExtractRegularFile(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char a5,
        _QWORD *a6,
        ArchiveExtractProgress *a7)
{
  _QWORD *v10; // r14
  char i; // r12
  const WCHAR *v12; // rax
  HANDLE FileW; // rax
  signed int LastError; // ebx
  const WCHAR *v15; // rax
  DWORD FileAttributesW; // eax
  const WCHAR *v17; // rax
  int v18; // edx
  const WCHAR *v19; // rax
  void *v20; // rdx
  unsigned int v21; // r8d
  const char *v22; // r9
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // rdx
  unsigned __int64 v26; // rbx
  int v27; // r12d
  int v28; // eax
  int v29; // eax
  const WCHAR *v30; // rax
  char *v31; // rax
  int v32; // ebx
  __int64 v33; // rax
  __int64 v34; // r8
  const WCHAR *v35; // rax
  int v36; // eax
  __int64 v37; // rax
  __int64 v38; // r8
  const WCHAR *v39; // rax
  int v40; // eax
  __int64 v41; // rax
  __int64 v42; // r8
  const WCHAR *v43; // rax
  int v44; // eax
  __int64 v45; // rbx
  int v46; // eax
  unsigned int v47; // eax
  __int64 v48; // r8
  const WCHAR *v49; // rax
  int v50; // eax
  int v51; // eax
  unsigned int v52; // ebx
  _BYTE *v53; // rax
  __int64 v54; // r8
  int v55; // r14d
  unsigned int v56; // eax
  const char *v57; // rdx
  __int64 v58; // rax
  __int64 v59; // r8
  const WCHAR *v60; // rax
  int v61; // eax
  const WCHAR *v62; // rax
  const char *v64; // rbx
  void *v65; // rdx
  unsigned int v66; // r8d
  __int64 v67; // rax
  __int64 v68; // r8
  const WCHAR *v69; // rax
  int v70; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  _BYTE v74[32]; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE *p_hFile; // [rsp+70h] [rbp-90h]
  __int64 v76; // [rsp+78h] [rbp-88h]
  ArchiveExtractProgress **v77; // [rsp+80h] [rbp-80h]
  __int64 *v78; // [rsp+88h] [rbp-78h]
  char v79; // [rsp+90h] [rbp-70h]
  ArchiveExtractProgress *v80; // [rsp+98h] [rbp-68h] BYREF
  LPCVOID lpBuffer; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE hFile; // [rsp+A8h] [rbp-58h] BYREF
  char *v83; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v84; // [rsp+B8h] [rbp-48h] BYREF
  DWORD nNumberOfBytesToWrite[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v86[32]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v87; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v10 = a6;
  v87 = a1;
  v80 = a7;
  hFile = 0;
  for ( i = 0; ; i = 1 )
  {
    v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
    FileW = CreateFileW(v12, 0xC0000100, 1u, 0, 1u, 0x200080u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      FileW);
    if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      break;
    LastError = GetLastError();
    v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
    FileAttributesW = GetFileAttributesW(v15);
    if ( FileAttributesW == -1 || i )
      goto LABEL_12;
    if ( (FileAttributesW & 0x410) == 0x10 )
    {
      v23 = std::wstring::wstring(v86, a4);
      LOBYTE(v24) = 5;
      v25 = 2150039564LL;
      goto LABEL_19;
    }
    if ( (a5 & 1) == 0 )
    {
      v23 = std::wstring::wstring(v86, a4);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LOBYTE(v24) = 4;
LABEL_18:
      v25 = (unsigned int)LastError;
LABEL_19:
      ExtractResult::ExtractResult(a1, v25, v24, v23);
      goto LABEL_70;
    }
    if ( (FileAttributesW & 1) != 0 )
    {
      v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
      SetFileAttributesW(v17, v18 & 0xFFFFFFFE);
    }
    v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
    if ( !DeleteFileW(v19) )
    {
      LastError = wil::details::in1diag3::Log_GetLastError(retaddr, v20, v21, v22);
LABEL_12:
      v23 = std::wstring::wstring(v86, a4);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LOBYTE(v24) = 2;
      goto LABEL_18;
    }
  }
  v84 = 0;
  if ( v80 )
    v84 = *(_QWORD *)(*((_QWORD *)v80 + 2) + 8LL);
  p_hFile = &hFile;
  v76 = a4;
  v77 = &v80;
  v78 = &v84;
  v79 = 1;
  lpBuffer = 0;
  *(_QWORD *)nNumberOfBytesToWrite = 0;
  v87 = 0;
  v26 = 0;
  while ( 1 )
  {
    v29 = archive_read_data_block(a2, &lpBuffer, nNumberOfBytesToWrite, &v87);
    if ( v29 == 1 )
    {
      if ( a6[2] )
      {
        std::operator+<unsigned short>(v86, a4);
        v30 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v86);
        v31 = (char *)CreateFileW(v30, 0xC0000000, 0, 0, 2u, 0x80u, 0);
        v83 = v31;
        if ( (unsigned __int64)(v31 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        {
          v64 = (const char *)GetLastError();
          wil::details::in1diag3::Log_Win32(retaddr, v65, v66, v64, dwCreationDispositiona);
          v67 = std::wstring::wstring(v74, a4);
          if ( (int)v64 > 0 )
            LODWORD(v64) = (unsigned __int16)v64 | 0x80070000;
          LOBYTE(v68) = 2;
          ExtractResult::ExtractResult(a1, (unsigned int)v64, v68, v67);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v83);
          std::wstring::_Tidy_deallocate(v86);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &hFile,
            0);
          v69 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
          DeleteFileW(v69);
          if ( v80 )
          {
            *(_QWORD *)(*((_QWORD *)v80 + 2) + 8LL) = v84;
            v70 = ArchiveExtractProgress::Update(v80);
            if ( v70 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x204,
                (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
                (const char *)(unsigned int)v70,
                dwCreationDispositionb);
          }
          goto LABEL_70;
        }
        if ( a6[3] > 0xFu )
          v10 = (_QWORD *)*a6;
        v32 = WriteAllBytesToFile(v31, v10, a6[2]);
        if ( v32 < 0 )
        {
          v33 = std::wstring::wstring(v74, a4);
          LOBYTE(v34) = 2;
          ExtractResult::ExtractResult(a1, (unsigned int)v32, v34, v33);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v83);
          std::wstring::_Tidy_deallocate(v86);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &hFile,
            0);
          v35 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
          DeleteFileW(v35);
          if ( v80 )
          {
            *(_QWORD *)(*((_QWORD *)v80 + 2) + 8LL) = v84;
            v36 = ArchiveExtractProgress::Update(v80);
            if ( v36 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x204,
                (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
                (const char *)(unsigned int)v36,
                dwCreationDispositiona);
          }
          goto LABEL_70;
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v83);
        std::wstring::_Tidy_deallocate(v86);
      }
      TryRestoreFileTimes_0(hFile);
      v62 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
      TryRestoreAttributes_0(v62);
      *(_OWORD *)a1 = 0;
      *(_OWORD *)(a1 + 16) = 0;
      *(_DWORD *)a1 = 0;
      *(_BYTE *)(a1 + 4) = 0;
      *(_OWORD *)(a1 + 8) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      *(_QWORD *)(a1 + 32) = 7;
      *(_WORD *)(a1 + 8) = 0;
      goto LABEL_70;
    }
    if ( v29 == -30 )
      break;
    if ( v29 )
    {
      v45 = std::wstring::wstring(v86, a4);
      v46 = archive_errno(a2);
      v47 = HRESULT_FROM_ERRNO(v46);
      LOBYTE(v48) = 2;
      ExtractResult::ExtractResult(a1, v47, v48, v45);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hFile,
        0);
      v49 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
      DeleteFileW(v49);
      if ( v80 )
      {
        *(_QWORD *)(*((_QWORD *)v80 + 2) + 8LL) = v84;
        v50 = ArchiveExtractProgress::Update(v80);
        if ( v50 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x204,
            (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
            (const char *)(unsigned int)v50,
            dwCreationDisposition);
      }
      goto LABEL_70;
    }
    v27 = WriteAllBytesToFile(hFile, lpBuffer, nNumberOfBytesToWrite[0]);
    if ( v27 < 0 )
    {
      v41 = std::wstring::wstring(v86, a4);
      LOBYTE(v42) = 2;
      ExtractResult::ExtractResult(a1, (unsigned int)v27, v42, v41);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hFile,
        0);
      v43 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
      DeleteFileW(v43);
      if ( v80 )
      {
        *(_QWORD *)(*((_QWORD *)v80 + 2) + 8LL) = v84;
        v44 = ArchiveExtractProgress::Update(v80);
        if ( v44 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x204,
            (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
            (const char *)(unsigned int)v44,
            dwCreationDisposition);
      }
      goto LABEL_70;
    }
    if ( v80 )
    {
      *(_QWORD *)(*((_QWORD *)v80 + 2) + 8LL) += *(_QWORD *)nNumberOfBytesToWrite;
      v26 += *(_QWORD *)nNumberOfBytesToWrite;
      if ( v26 >= 0xF4240 )
      {
        LODWORD(v83) = 0;
        if ( (*(int (__fastcall **)(_QWORD, char **))(**(_QWORD **)v80 + 104LL))(*(_QWORD *)v80, &v83) >= 0
          && (_DWORD)v83 == 3 )
        {
          v37 = std::wstring::wstring(v86, a4);
          LOBYTE(v38) = 1;
          ExtractResult::ExtractResult(a1, 2147943623LL, v38, v37);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &hFile,
            0);
          v39 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
          DeleteFileW(v39);
          if ( v80 )
          {
            *(_QWORD *)(*((_QWORD *)v80 + 2) + 8LL) = v84;
            v40 = ArchiveExtractProgress::Update(v80);
            if ( v40 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x204,
                (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
                (const char *)(unsigned int)v40,
                dwCreationDisposition);
          }
          goto LABEL_70;
        }
        v26 = 0;
        v28 = ArchiveExtractProgress::Update(v80);
        if ( v28 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x24F,
            (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
            (const char *)(unsigned int)v28,
            dwCreationDisposition);
      }
    }
  }
  v51 = archive_errno(a2);
  v52 = HRESULT_FROM_ERRNO(v51);
  if ( (int)archive_read_has_encrypted_entries(a2) > 0 )
    goto LABEL_61;
  v53 = (_BYTE *)archive_error_string(a2);
  if ( !v53 )
    goto LABEL_62;
  v54 = -1;
  do
    ++v54;
  while ( v53[v54] );
  if ( v54 == 27 && !memcmp_0(v53, KnownArchiveErrors::EncryptedRAR, 0x1Bu) )
  {
LABEL_61:
    v52 = -2147018894;
  }
  else
  {
LABEL_62:
    v55 = archive_errno(a2);
    if ( v55 )
    {
      archive_error_string(a2);
      v56 = HRESULT_FROM_ERRNO(v55);
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x22E,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)v56,
        (int)"archive error: %hs",
        v57);
    }
  }
  v58 = std::wstring::wstring(v86, a4);
  LOBYTE(v59) = 3;
  ExtractResult::ExtractResult(a1, v52, v59, v58);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hFile,
    0);
  v60 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
  DeleteFileW(v60);
  if ( v80 )
  {
    *(_QWORD *)(*((_QWORD *)v80 + 2) + 8LL) = v84;
    v61 = ArchiveExtractProgress::Update(v80);
    if ( v61 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x204,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v61,
        dwCreationDisposition);
  }
LABEL_70:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
  return a1;
}

```

## disassembly

```asm
0x180065a94  push    rbp
0x180065a96  push    rbx
0x180065a97  push    rsi
0x180065a98  push    rdi
0x180065a99  push    r12
0x180065a9b  push    r13
0x180065a9d  push    r14
0x180065a9f  push    r15
0x180065aa1  lea     rbp, [rsp-8]
0x180065aa6  sub     rsp, 108h
0x180065aad  mov     rax, cs:__security_cookie
0x180065ab4  xor     rax, rsp
0x180065ab7  mov     [rbp+40h+var_50], rax
0x180065abb  mov     rsi, r9
0x180065abe  mov     r13, r8
0x180065ac1  mov     r15, rdx
0x180065ac4  mov     rdi, rcx
0x180065ac7  mov     r14, [rbp+40h+arg_28]
0x180065acb  mov     [rbp+40h+var_58], rcx
0x180065acf  mov     rax, [rbp+40h+arg_30]
0x180065ad6  mov     [rbp+40h+var_A8], rax
0x180065ada  mov     [rbp+40h+hFile], 0
0x180065ae2  xor     r12b, r12b
0x180065ae5  mov     rcx, rsi
0x180065ae8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180065aed  mov     [rsp+140h+hTemplateFile], 0; hTemplateFile
0x180065af6  mov     [rsp+140h+dwFlagsAndAttributes], 200080h; dwFlagsAndAttributes
0x180065afe  mov     [rsp+140h+dwCreationDisposition], 1; dwCreationDisposition
0x180065b06  xor     r9d, r9d; lpSecurityAttributes
0x180065b09  mov     edx, 0C0000100h; dwDesiredAccess
0x180065b0e  lea     r8d, [r9+1]; dwShareMode
0x180065b12  mov     rcx, rax; lpFileName
0x180065b15  call    cs:__imp_CreateFileW
0x180065b1b  mov     rdx, rax
0x180065b1e  lea     rcx, [rbp+40h+hFile]
0x180065b22  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180065b27  mov     rax, [rbp+40h+hFile]
0x180065b2b  inc     rax
0x180065b2e  test    rax, 0FFFFFFFFFFFFFFFEh
0x180065b34  jnz     loc_180065C16
0x180065b3a  call    cs:__imp_GetLastError
0x180065b40  mov     ebx, eax
0x180065b42  mov     rcx, rsi
0x180065b45  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180065b4a  mov     rcx, rax; lpFileName
0x180065b4d  call    cs:__imp_GetFileAttributesW
0x180065b53  mov     edx, eax
0x180065b55  cmp     eax, 0FFFFFFFFh
0x180065b58  jz      short loc_180065BB4
0x180065b5a  test    r12b, r12b
0x180065b5d  jnz     short loc_180065BB4
0x180065b5f  and     eax, 410h
0x180065b64  cmp     eax, 10h
0x180065b67  jz      loc_180065C00
0x180065b6d  test    [rbp+40h+arg_20], 1
0x180065b71  jz      short loc_180065BD2
0x180065b73  test    dl, 1
0x180065b76  jz      short loc_180065B8C
0x180065b78  mov     rcx, rsi
0x180065b7b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180065b80  and     edx, 0FFFFFFFEh; dwFileAttributes
0x180065b83  mov     rcx, rax; lpFileName
0x180065b86  call    cs:__imp_SetFileAttributesW
0x180065b8c  mov     rcx, rsi
0x180065b8f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180065b94  mov     rcx, rax; lpFileName
0x180065b97  call    cs:__imp_DeleteFileW
0x180065b9d  test    eax, eax
0x180065b9f  jz      short loc_180065BA9
0x180065ba1  mov     r12b, 1
0x180065ba4  jmp     loc_180065AE5
0x180065ba9  mov     rcx, [rbp+48h]; this
0x180065bad  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180065bb2  mov     ebx, eax
0x180065bb4  mov     rdx, rsi
0x180065bb7  lea     rcx, [rbp+40h+var_78]
0x180065bbb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180065bc0  test    ebx, ebx
0x180065bc2  jle     short loc_180065BCD
0x180065bc4  movzx   ebx, bx
0x180065bc7  or      ebx, 80070000h
0x180065bcd  mov     r8b, 2
0x180065bd0  jmp     short loc_180065BEE
0x180065bd2  mov     rdx, rsi
0x180065bd5  lea     rcx, [rbp+40h+var_78]
0x180065bd9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180065bde  test    ebx, ebx
0x180065be0  jle     short loc_180065BEB
0x180065be2  movzx   ebx, bx
0x180065be5  or      ebx, 80070000h
0x180065beb  mov     r8b, 4
0x180065bee  mov     edx, ebx
0x180065bf0  mov     r9, rax
0x180065bf3  mov     rcx, rdi
0x180065bf6  call    ??0ExtractResult@@QEAA@JW4ExtractFailureReason@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ExtractResult::ExtractResult(long,ExtractFailureReason,std::wstring)
0x180065bfb  jmp     loc_18006612C
0x180065c00  mov     rdx, rsi
0x180065c03  lea     rcx, [rbp+40h+var_78]
0x180065c07  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180065c0c  mov     r8b, 5
0x180065c0f  mov     edx, 8027000Ch
0x180065c14  jmp     short loc_180065BF0
0x180065c16  xor     r12d, r12d
0x180065c19  mov     [rbp+40h+var_88], r12
0x180065c1d  mov     rax, [rbp+40h+var_A8]
0x180065c21  test    rax, rax
0x180065c24  jz      short loc_180065C32
0x180065c26  mov     rax, [rax+10h]
0x180065c2a  mov     rcx, [rax+8]
0x180065c2e  mov     [rbp+40h+var_88], rcx
0x180065c32  lea     rax, [rbp+40h+hFile]
0x180065c36  mov     [rsp+140h+var_D0], rax
0x180065c3b  mov     [rsp+140h+var_C8], rsi
0x180065c40  lea     rax, [rbp+40h+var_A8]
0x180065c44  mov     [rbp+40h+var_C0], rax
0x180065c48  lea     rax, [rbp+40h+var_88]
0x180065c4c  mov     [rbp+40h+var_B8], rax
0x180065c50  mov     [rbp+40h+var_B0], 1
0x180065c54  mov     [rbp+40h+lpBuffer], r12
0x180065c58  mov     qword ptr [rbp+40h+nNumberOfBytesToWrite], r12
0x180065c5c  mov     [rbp+40h+var_58], r12
0x180065c60  mov     rbx, r12
0x180065c63  jmp     loc_180065D0B
0x180065c68  cmp     eax, 0FFFFFFE2h
0x180065c6b  jz      loc_180065FB7
0x180065c71  test    eax, eax
0x180065c73  jnz     loc_180065F2B
0x180065c79  mov     r8, qword ptr [rbp+40h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180065c7d  mov     rdx, [rbp+40h+lpBuffer]; lpBuffer
0x180065c81  mov     rcx, [rbp+40h+hFile]; hFile
0x180065c85  call    WriteAllBytesToFile
0x180065c8a  mov     r12d, eax
0x180065c8d  test    eax, eax
0x180065c8f  js      loc_180065EB1
0x180065c95  mov     rcx, [rbp+40h+var_A8]
0x180065c99  xor     r12d, r12d
0x180065c9c  test    rcx, rcx
0x180065c9f  jz      short loc_180065D0B
0x180065ca1  mov     rcx, [rcx+10h]
0x180065ca5  mov     rax, qword ptr [rbp+40h+nNumberOfBytesToWrite]
0x180065ca9  add     [rcx+8], rax
0x180065cad  add     rbx, qword ptr [rbp+40h+nNumberOfBytesToWrite]
0x180065cb1  cmp     rbx, 0F4240h
0x180065cb8  jb      short loc_180065D0B
0x180065cba  mov     dword ptr [rbp+40h+var_90], r12d
0x180065cbe  mov     rax, [rbp+40h+var_A8]
0x180065cc2  mov     rcx, [rax]
0x180065cc5  mov     rax, [rcx]
0x180065cc8  lea     rdx, [rbp+40h+var_90]
0x180065ccc  mov     rax, [rax+68h]
0x180065cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065cd5  test    eax, eax
0x180065cd7  js      short loc_180065CE3
0x180065cd9  cmp     dword ptr [rbp+40h+var_90], 3
0x180065cdd  jz      loc_180065E35
0x180065ce3  mov     rbx, r12
0x180065ce6  mov     rcx, [rbp+40h+var_A8]; this
0x180065cea  call    ?Update@ArchiveExtractProgress@@QEAAJXZ; ArchiveExtractProgress::Update(void)
0x180065cef  mov     rcx, [rbp+48h]; this
0x180065cf3  test    eax, eax
0x180065cf5  jns     short loc_180065D0B
0x180065cf7  mov     r9d, eax; char *
0x180065cfa  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x180065d01  mov     edx, 24Fh; void *
0x180065d06  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180065d0b  lea     r9, [rbp+40h+var_58]
0x180065d0f  lea     r8, [rbp+40h+nNumberOfBytesToWrite]
0x180065d13  lea     rdx, [rbp+40h+lpBuffer]
0x180065d17  mov     rcx, r15
0x180065d1a  call    cs:__imp_archive_read_data_block
0x180065d20  cmp     eax, 1
0x180065d23  jnz     loc_180065C68
0x180065d29  cmp     [r14+10h], r12
0x180065d2d  jz      loc_1800660E7
0x180065d33  mov     rdx, rsi
0x180065d36  lea     rcx, [rbp+40h+var_78]
0x180065d3a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180065d3f  nop
0x180065d40  lea     rcx, [rbp+40h+var_78]
0x180065d44  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180065d49  mov     rcx, rax; lpFileName
0x180065d4c  mov     [rsp+140h+hTemplateFile], r12; hTemplateFile
0x180065d51  mov     [rsp+140h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180065d59  mov     [rsp+140h+dwCreationDisposition], 2; int
0x180065d61  xor     r9d, r9d; lpSecurityAttributes
0x180065d64  xor     r8d, r8d; dwShareMode
0x180065d67  mov     edx, 0C0000000h; dwDesiredAccess
0x180065d6c  call    cs:__imp_CreateFileW
0x180065d72  mov     [rbp+40h+var_90], rax
0x180065d76  lea     rcx, [rax-1]
0x180065d7a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180065d7e  ja      loc_180066158
0x180065d84  mov     r8, [r14+10h]; nNumberOfBytesToWrite
0x180065d88  cmp     qword ptr [r14+18h], 0Fh
0x180065d8d  jbe     short loc_180065D92
0x180065d8f  mov     r14, [r14]
0x180065d92  mov     rdx, r14; lpBuffer
0x180065d95  mov     rcx, rax; hFile
0x180065d98  call    WriteAllBytesToFile
0x180065d9d  mov     ebx, eax
0x180065d9f  test    eax, eax
0x180065da1  jns     loc_1800660D4
0x180065da7  mov     rdx, rsi
0x180065daa  lea     rcx, [rsp+140h+var_F0]
0x180065daf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180065db4  mov     r9, rax
0x180065db7  mov     r8b, 2
0x180065dba  mov     edx, ebx
0x180065dbc  mov     rcx, rdi
0x180065dbf  call    ??0ExtractResult@@QEAA@JW4ExtractFailureReason@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ExtractResult::ExtractResult(long,ExtractFailureReason,std::wstring)
0x180065dc4  nop
0x180065dc5  lea     rcx, [rbp+40h+var_90]
0x180065dc9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180065dce  nop
0x180065dcf  lea     rcx, [rbp+40h+var_78]
0x180065dd3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180065dd8  nop
0x180065dd9  xor     edx, edx
0x180065ddb  lea     rcx, [rbp+40h+hFile]
0x180065ddf  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180065de4  mov     rcx, rsi
0x180065de7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180065dec  mov     rcx, rax; lpFileName
0x180065def  call    cs:__imp_DeleteFileW
0x180065df5  mov     rcx, [rbp+40h+var_A8]
0x180065df9  test    rcx, rcx
0x180065dfc  jz      short loc_180065E30
0x180065dfe  mov     rcx, [rcx+10h]
0x180065e02  mov     rax, [rbp+40h+var_88]
0x180065e06  mov     [rcx+8], rax
0x180065e0a  mov     rcx, [rbp+40h+var_A8]; this
0x180065e0e  call    ?Update@ArchiveExtractProgress@@QEAAJXZ; ArchiveExtractProgress::Update(void)
0x180065e13  mov     rcx, [rbp+48h]; this
0x180065e17  test    eax, eax
0x180065e19  jns     short loc_180065E30
0x180065e1b  mov     r9d, eax; char *
0x180065e1e  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x180065e25  mov     edx, 204h; void *
0x180065e2a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180065e2f  nop
0x180065e30  jmp     loc_18006612C
0x180065e35  mov     rdx, rsi
0x180065e38  lea     rcx, [rbp+40h+var_78]
0x180065e3c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180065e41  mov     r9, rax
0x180065e44  mov     r8b, 1
0x180065e47  mov     edx, 800704C7h
0x180065e4c  mov     rcx, rdi
0x180065e4f  call    ??0ExtractResult@@QEAA@JW4ExtractFailureReason@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ExtractResult::ExtractResult(long,ExtractFailureReason,std::wstring)
0x180065e54  nop
0x180065e55  xor     edx, edx
0x180065e57  lea     rcx, [rbp+40h+hFile]
0x180065e5b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180065e60  mov     rcx, rsi
0x180065e63  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180065e68  mov     rcx, rax; lpFileName
0x180065e6b  call    cs:__imp_DeleteFileW
0x180065e71  mov     rcx, [rbp+40h+var_A8]
0x180065e75  test    rcx, rcx
0x180065e78  jz      short loc_180065EAC
0x180065e7a  mov     rcx, [rcx+10h]
0x180065e7e  mov     rax, [rbp+40h+var_88]
0x180065e82  mov     [rcx+8], rax
0x180065e86  mov     rcx, [rbp+40h+var_A8]; this
0x180065e8a  call    ?Update@ArchiveExtractProgress@@QEAAJXZ; ArchiveExtractProgress::Update(void)
0x180065e8f  mov     rcx, [rbp+48h]; this
0x180065e93  test    eax, eax
0x180065e95  jns     short loc_180065EAC
0x180065e97  mov     r9d, eax; char *
0x180065e9a  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x180065ea1  mov     edx, 204h; void *
0x180065ea6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180065eab  nop
0x180065eac  jmp     loc_18006612C
0x180065eb1  mov     rdx, rsi
0x180065eb4  lea     rcx, [rbp+40h+var_78]
0x180065eb8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180065ebd  mov     r9, rax
0x180065ec0  mov     r8b, 2
0x180065ec3  mov     edx, r12d
0x180065ec6  mov     rcx, rdi
0x180065ec9  call    ??0ExtractResult@@QEAA@JW4ExtractFailureReason@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ExtractResult::ExtractResult(long,ExtractFailureReason,std::wstring)
0x180065ece  nop
0x180065ecf  xor     edx, edx
0x180065ed1  lea     rcx, [rbp+40h+hFile]
0x180065ed5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180065eda  mov     rcx, rsi
0x180065edd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180065ee2  mov     rcx, rax; lpFileName
0x180065ee5  call    cs:__imp_DeleteFileW
0x180065eeb  mov     rcx, [rbp+40h+var_A8]
0x180065eef  test    rcx, rcx
0x180065ef2  jz      short loc_180065F26
0x180065ef4  mov     rcx, [rcx+10h]
0x180065ef8  mov     rax, [rbp+40h+var_88]
0x180065efc  mov     [rcx+8], rax
0x180065f00  mov     rcx, [rbp+40h+var_A8]; this
0x180065f04  call    ?Update@ArchiveExtractProgress@@QEAAJXZ; ArchiveExtractProgress::Update(void)
0x180065f09  mov     rcx, [rbp+48h]; this
0x180065f0d  test    eax, eax
  ... truncated ...
```
