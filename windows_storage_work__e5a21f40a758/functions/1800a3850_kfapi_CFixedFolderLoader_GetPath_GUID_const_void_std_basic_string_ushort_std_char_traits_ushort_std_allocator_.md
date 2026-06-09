# kfapi::CFixedFolderLoader::GetPath(_GUID const &,void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x1800a3850`
- end: `0x1800a3f38`
- name: `?GetPath@CFixedFolderLoader@kfapi@@SAJAEBU_GUID@@PEAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1768`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180137340`

## callees

- `0x1800a1b50`
- `0x1800a3080`
- `0x1800a3850`
- `0x1800a3f40`
- `0x1800a40cc`
- `0x1801158c0`
- `0x180137f14`
- `0x1802aecb4`
- `0x1802deae4`
- `0x1803340e8`
- `0x1803a4cb0`
- `0x180628830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a38b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3bc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3c87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a38b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3bc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3c87`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800a3a4b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800a3cae`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800a3a4b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800a3cae`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800a3bb4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800a3bb4`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800a38aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800a38aa`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800a3bf0`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800a3d80`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800a3ddf`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800a3e1a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800a3bf0`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800a3d80`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800a3ddf`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800a3e1a`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x1800a3c70`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x1800a3c70`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800a3996`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800a39c7`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800a3a7f`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800a3996`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800a39c7`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800a3a7f`

## string_xrefs

- `0x1800a3c52`: `CommonFilesDir`
- `0x1800a3c37`: `CommonFilesDir (x86)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall kfapi::CFixedFolderLoader::GetPath(_QWORD *a1, kfapi *a2, unsigned __int16 *a3, unsigned int a4)
{
  __int64 v5; // rax
  UINT WindowsDirectoryW; // eax
  signed int LastError; // eax
  int ProgramFiles; // ebx
  __int64 v9; // rax
  int UserProfileDir; // eax
  __int64 v11; // r8
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned int v18; // r9d
  const WCHAR *v19; // rcx
  UINT SystemDirectoryW; // eax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  UINT SystemWindowsDirectoryW; // eax
  signed int v31; // eax
  UINT SystemWow64DirectoryW; // ecx
  UINT v33; // eax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rdx
  const unsigned __int16 *v41; // r8
  __int64 v42; // rdx
  unsigned __int16 *v43[3]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v44; // [rsp+38h] [rbp-C8h]
  WCHAR Buffer[4096]; // [rsp+40h] [rbp-C0h] BYREF

  v5 = *a1 - *(_QWORD *)&FOLDERID_Windows.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_Windows.Data1 )
    v5 = a1[1] - *(_QWORD *)FOLDERID_Windows.Data4;
  if ( !v5 )
  {
    WindowsDirectoryW = GetWindowsDirectoryW(Buffer, 0x1000u);
    if ( WindowsDirectoryW )
    {
      ProgramFiles = 0;
      if ( WindowsDirectoryW >= 0x1000 )
        ProgramFiles = -2147024774;
      goto LABEL_12;
    }
    goto LABEL_5;
  }
  v9 = *a1 - *(_QWORD *)&FOLDERID_Profile.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_Profile.Data1 )
    v9 = a1[1] - *(_QWORD *)FOLDERID_Profile.Data4;
  if ( !v9 )
  {
    UserProfileDir = kfapi::GetUserProfileDir(a2, Buffer, (unsigned __int16 *)0x1000, a4);
LABEL_11:
    ProgramFiles = UserProfileDir;
    goto LABEL_12;
  }
  v13 = *a1 - *(_QWORD *)&FOLDERID_UserProfiles.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_UserProfiles.Data1 )
    v13 = a1[1] - *(_QWORD *)FOLDERID_UserProfiles.Data4;
  if ( !v13 )
  {
    UserProfileDir = GetBasicProfileFolderPath(1, 0, Buffer, 4096);
    goto LABEL_11;
  }
  v14 = *a1 - *(_QWORD *)&FOLDERID_ProgramData.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_ProgramData.Data1 )
    v14 = a1[1] - *(_QWORD *)FOLDERID_ProgramData.Data4;
  if ( !v14 )
  {
    UserProfileDir = GetBasicProfileFolderPath(4, 0, Buffer, 4096);
    goto LABEL_11;
  }
  v15 = *a1 - *(_QWORD *)&FOLDERID_System.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_System.Data1 )
    v15 = a1[1] - *(_QWORD *)FOLDERID_System.Data4;
  if ( !v15 )
  {
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x1000u);
    if ( SystemDirectoryW )
    {
      ProgramFiles = 0;
      if ( SystemDirectoryW >= 0x1000 )
        ProgramFiles = -2147024774;
      goto LABEL_12;
    }
    goto LABEL_5;
  }
  v16 = *a1 - *(_QWORD *)&FOLDERID_Public.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_Public.Data1 )
    v16 = a1[1] - *(_QWORD *)FOLDERID_Public.Data4;
  if ( !v16 )
  {
    UserProfileDir = GetBasicProfileFolderPath(3, 0, Buffer, 4096);
    goto LABEL_11;
  }
  v17 = *a1 - *(_QWORD *)&FOLDERID_ProgramFilesX86.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_ProgramFilesX86.Data1 )
    v17 = a1[1] - *(_QWORD *)FOLDERID_ProgramFilesX86.Data4;
  if ( !v17 )
  {
    v18 = 0;
    v19 = L"ProgramFilesDir (x86)";
LABEL_38:
    ProgramFiles = kfapi::_GetProgramFiles(v19, Buffer, a3, v18, (unsigned int)v43[0]);
    goto LABEL_12;
  }
  v21 = *a1 - *(_QWORD *)&FOLDERID_ProgramFiles.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_ProgramFiles.Data1 )
    v21 = a1[1] - *(_QWORD *)FOLDERID_ProgramFiles.Data4;
  if ( !v21 )
  {
    ProgramFiles = kfapi::_GetProgramFiles(L"ProgramFilesDir", Buffer, a3, 0, (unsigned int)v43[0]);
    goto LABEL_12;
  }
  v22 = *a1 - *(_QWORD *)&FOLDERID_ProgramFilesX64.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_ProgramFilesX64.Data1 )
    v22 = a1[1] - *(_QWORD *)FOLDERID_ProgramFilesX64.Data4;
  if ( !v22 )
  {
    ProgramFiles = kfapi::_GetProgramFiles(L"ProgramFilesDir", Buffer, a3, 0x100u, (unsigned int)v43[0]);
    goto LABEL_12;
  }
  v23 = *a1 - *(_QWORD *)&FOLDERID_ProgramFilesCommonX86.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_ProgramFilesCommonX86.Data1 )
    v23 = a1[1] - *(_QWORD *)FOLDERID_ProgramFilesCommonX86.Data4;
  if ( !v23 )
  {
    ProgramFiles = kfapi::_GetProgramFiles(L"CommonFilesDir (x86)", Buffer, a3, 0, (unsigned int)v43[0]);
    goto LABEL_12;
  }
  v24 = *a1 - *(_QWORD *)&FOLDERID_ProgramFilesCommon.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_ProgramFilesCommon.Data1 )
    v24 = a1[1] - *(_QWORD *)FOLDERID_ProgramFilesCommon.Data4;
  if ( !v24 )
  {
    v18 = 0;
LABEL_80:
    v19 = L"CommonFilesDir";
    goto LABEL_38;
  }
  v25 = *a1 - *(_QWORD *)&FOLDERID_ProgramFilesCommonX64.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_ProgramFilesCommonX64.Data1 )
    v25 = a1[1] - *(_QWORD *)FOLDERID_ProgramFilesCommonX64.Data4;
  if ( !v25 )
  {
    v18 = 256;
    goto LABEL_80;
  }
  v26 = *a1 - *(_QWORD *)&FOLDERID_SystemX86.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_SystemX86.Data1 )
    v26 = a1[1] - *(_QWORD *)FOLDERID_SystemX86.Data4;
  if ( !v26 )
  {
    SystemWow64DirectoryW = GetSystemWow64DirectoryW(Buffer, 0x1000u);
    ProgramFiles = 0;
    if ( SystemWow64DirectoryW )
    {
      UserProfileDir = 0;
      if ( SystemWow64DirectoryW >= 0x1000 )
        UserProfileDir = -2147024774;
    }
    else
    {
      UserProfileDir = GetLastError();
      if ( UserProfileDir > 0 )
        UserProfileDir = (unsigned __int16)UserProfileDir | 0x80070000;
    }
    if ( UserProfileDir != -2147024776 )
      goto LABEL_11;
    v33 = GetSystemDirectoryW(Buffer, 0x1000u);
    if ( v33 )
    {
      if ( v33 >= 0x1000 )
        ProgramFiles = -2147024774;
      goto LABEL_12;
    }
LABEL_5:
    LastError = GetLastError();
    ProgramFiles = LastError;
    if ( LastError > 0 )
      ProgramFiles = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_12;
  }
  v27 = *a1 - *(_QWORD *)&FOLDERID_ResourceDir.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_ResourceDir.Data1 )
    v27 = a1[1] - *(_QWORD *)FOLDERID_ResourceDir.Data4;
  if ( !v27 )
  {
    ProgramFiles = kfapi::_GetResourcesDir(0, (int)Buffer, a3, a4);
    goto LABEL_12;
  }
  v28 = *a1 - *(_QWORD *)&FOLDERID_LocalizedResourcesDir.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_LocalizedResourcesDir.Data1 )
    v28 = a1[1] - *(_QWORD *)FOLDERID_LocalizedResourcesDir.Data4;
  if ( !v28 )
  {
    ProgramFiles = kfapi::_GetResourcesDir((kfapi *)1, (int)Buffer, a3, a4);
    goto LABEL_12;
  }
  v29 = *a1 - *(_QWORD *)&FOLDERID_Fonts.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_Fonts.Data1 )
    v29 = a1[1] - *(_QWORD *)FOLDERID_Fonts.Data4;
  if ( !v29 )
  {
    SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x1000u);
    if ( SystemWindowsDirectoryW )
    {
      ProgramFiles = 0;
      if ( SystemWindowsDirectoryW >= 0x1000 )
        ProgramFiles = -2147024774;
    }
    else
    {
      v31 = GetLastError();
      ProgramFiles = v31;
      if ( v31 > 0 )
        ProgramFiles = (unsigned __int16)v31 | 0x80070000;
    }
    if ( ProgramFiles < 0 )
      return (unsigned int)ProgramFiles;
    UserProfileDir = PathCchAppend(Buffer, 0x1000u, L"Fonts");
    goto LABEL_11;
  }
  v34 = *a1 - 0x4BDA9EFE915221FBLL;
  if ( *a1 == 0x4BDA9EFE915221FBLL )
    v34 = a1[1] + 0x78B0883572082871LL;
  if ( !v34 )
  {
    ProgramFiles = kfapi::GetUserProfileDir(a2, Buffer, (unsigned __int16 *)0x1000, a4);
    if ( ProgramFiles >= 0 )
      ProgramFiles = PathCchAppend(Buffer, 0x1000u, L"AppData\\Roaming\\Microsoft\\Credentials");
    goto LABEL_12;
  }
  v35 = *a1 - 0x49A9E7BDB88F4DAALL;
  if ( *a1 == 0x49A9E7BDB88F4DAALL )
    v35 = a1[1] - 0x65C75D5A88024DB7LL;
  if ( !v35 )
  {
    ProgramFiles = kfapi::GetUserProfileDir(a2, Buffer, (unsigned __int16 *)0x1000, a4);
    if ( ProgramFiles >= 0 )
      ProgramFiles = PathCchAppend(Buffer, 0x1000u, L"AppData\\Roaming\\Microsoft\\Crypto");
    goto LABEL_12;
  }
  v36 = *a1 - 0x4567EF9110C07CD0LL;
  if ( *a1 == 0x4567EF9110C07CD0LL )
    v36 = a1[1] + 0x6C8348874BBAF48LL;
  if ( !v36 )
  {
    ProgramFiles = kfapi::GetUserProfileDir(a2, Buffer, (unsigned __int16 *)0x1000, a4);
    if ( ProgramFiles >= 0 )
      ProgramFiles = PathCchAppend(Buffer, 0x1000u, L"AppData\\Roaming\\Microsoft\\Protect");
    goto LABEL_12;
  }
  v37 = *a1 - 0x4FDBE7CA54EED2E0LL;
  if ( *a1 == 0x4FDBE7CA54EED2E0LL )
    v37 = a1[1] + 0x5E3D6B8BDF0B76FLL;
  if ( !v37 )
  {
    UserProfileDir = kfapi::GetProfileRelativeDirectory(
                       a2,
                       Buffer,
                       a3,
                       (unsigned int)L"AppData\\Roaming\\Microsoft\\SystemCertificates",
                       v43[0]);
    goto LABEL_11;
  }
  v38 = *a1 - 0x4C9D71852856B913LL;
  if ( *a1 == 0x4C9D71852856B913LL )
    v38 = a1[1] - 0x143CA8691298CC9ALL;
  if ( !v38 )
  {
    std::wstring::wstring(v43);
    ProgramFiles = kfapi::ExpandString(L"%SystemDrive%\\Data\\SharedData", v40, v43);
    if ( ProgramFiles >= 0 )
    {
      v41 = (const unsigned __int16 *)v43;
      if ( v44 > 7 )
        v41 = v43[0];
      goto LABEL_131;
    }
LABEL_132:
    std::pair<std::wstring,int>::~pair<std::wstring,int>(v43);
LABEL_12:
    if ( ProgramFiles >= 0 )
    {
      v11 = -1;
      do
        ++v11;
      while ( Buffer[v11] );
      std::wstring::_Assign<unsigned short>(a3, Buffer);
    }
    return (unsigned int)ProgramFiles;
  }
  v39 = *a1 - 0x48E0CFD58C19F0BCLL;
  if ( *a1 == 0x48E0CFD58C19F0BCLL )
    v39 = a1[1] - 0x68E351F082067B80LL;
  if ( !v39 )
  {
    std::wstring::wstring(v43);
    ProgramFiles = kfapi::ExpandString(L"%SystemDrive%\\Data\\SystemData", v42, v43);
    if ( ProgramFiles >= 0 )
    {
      v41 = (const unsigned __int16 *)v43;
      if ( v44 > 7 )
        v41 = v43[0];
LABEL_131:
      ProgramFiles = StringCchCopyW(Buffer, 0x1000u, v41);
      goto LABEL_132;
    }
    goto LABEL_132;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800a3850  mov     [rsp-8+arg_0], rbx
0x1800a3855  push    rbp
0x1800a3856  push    rsi
0x1800a3857  push    rdi
0x1800a3858  lea     rbp, [rsp-1F50h]
0x1800a3860  mov     eax, 2050h
0x1800a3865  call    _alloca_probe
0x1800a386a  sub     rsp, rax
0x1800a386d  mov     rax, cs:__security_cookie
0x1800a3874  xor     rax, rsp
0x1800a3877  mov     [rbp+1F60h+var_20], rax
0x1800a387e  mov     rsi, r8
0x1800a3881  mov     r10, rdx
0x1800a3884  mov     rax, [rcx]
0x1800a3887  sub     rax, qword ptr cs:FOLDERID_Windows.Data1
0x1800a388e  jnz     short loc_1800A389B
0x1800a3890  mov     rax, [rcx+8]
0x1800a3894  sub     rax, qword ptr cs:FOLDERID_Windows.Data4
0x1800a389b  test    rax, rax
0x1800a389e  jnz     short loc_1800A38CF
0x1800a38a0  mov     edx, 1000h; uSize
0x1800a38a5  lea     rcx, [rsp+2060h+Buffer]; lpBuffer
0x1800a38aa  call    cs:__imp_GetWindowsDirectoryW
0x1800a38b0  test    eax, eax
0x1800a38b2  jnz     loc_1800A39A1
0x1800a38b8  call    cs:__imp_GetLastError
0x1800a38be  mov     ebx, eax
0x1800a38c0  test    eax, eax
0x1800a38c2  jle     short loc_1800A3900
0x1800a38c4  movzx   ebx, ax
0x1800a38c7  or      ebx, 80070000h
0x1800a38cd  jmp     short loc_1800A3900
0x1800a38cf  mov     rax, [rcx]
0x1800a38d2  sub     rax, qword ptr cs:FOLDERID_Profile.Data1
0x1800a38d9  jnz     short loc_1800A38E6
0x1800a38db  mov     rax, [rcx+8]
0x1800a38df  sub     rax, qword ptr cs:FOLDERID_Profile.Data4
0x1800a38e6  test    rax, rax
0x1800a38e9  jnz     short loc_1800A394C
0x1800a38eb  mov     r8d, 1000h; unsigned __int16 *
0x1800a38f1  lea     rdx, [rsp+2060h+Buffer]; void *
0x1800a38f6  mov     rcx, r10; this
0x1800a38f9  call    ?GetUserProfileDir@kfapi@@YAJPEAXPEAGI@Z; kfapi::GetUserProfileDir(void *,ushort *,uint)
0x1800a38fe  mov     ebx, eax
0x1800a3900  test    ebx, ebx
0x1800a3902  js      short loc_1800A3928
0x1800a3904  lea     rax, [rsp+2060h+Buffer]
0x1800a3909  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800a3910  inc     r8
0x1800a3913  cmp     word ptr [rax+r8*2], 0
0x1800a3919  jnz     short loc_1800A3910
0x1800a391b  lea     rdx, [rsp+2060h+Buffer]
0x1800a3920  mov     rcx, rsi
0x1800a3923  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800a3928  mov     eax, ebx
0x1800a392a  mov     rcx, [rbp+1F60h+var_20]
0x1800a3931  xor     rcx, rsp; StackCookie
0x1800a3934  call    __security_check_cookie
0x1800a3939  mov     rbx, [rsp+2060h+arg_0]
0x1800a3941  add     rsp, 2050h
0x1800a3948  pop     rdi
0x1800a3949  pop     rsi
0x1800a394a  pop     rbp
0x1800a394b  retn
0x1800a394c  mov     rax, [rcx]
0x1800a394f  sub     rax, qword ptr cs:FOLDERID_UserProfiles.Data1
0x1800a3956  jnz     short loc_1800A3963
0x1800a3958  mov     rax, [rcx+8]
0x1800a395c  sub     rax, qword ptr cs:FOLDERID_UserProfiles.Data4
0x1800a3963  test    rax, rax
0x1800a3966  jz      short loc_1800A39B5
0x1800a3968  mov     rax, [rcx]
0x1800a396b  sub     rax, qword ptr cs:FOLDERID_ProgramData.Data1
0x1800a3972  jnz     short loc_1800A397F
0x1800a3974  mov     rax, [rcx+8]
0x1800a3978  sub     rax, qword ptr cs:FOLDERID_ProgramData.Data4
0x1800a397f  test    rax, rax
0x1800a3982  jnz     short loc_1800A39D2
0x1800a3984  mov     r9d, 1000h
0x1800a398a  lea     r8, [rsp+2060h+Buffer]
0x1800a398f  xor     edx, edx
0x1800a3991  mov     ecx, 4
0x1800a3996  call    cs:__imp_GetBasicProfileFolderPath
0x1800a399c  jmp     loc_1800A38FE
0x1800a39a1  xor     ebx, ebx
0x1800a39a3  mov     edi, 8007007Ah
0x1800a39a8  cmp     eax, 1000h
0x1800a39ad  cmovnb  ebx, edi
0x1800a39b0  jmp     loc_1800A3900
0x1800a39b5  mov     r9d, 1000h
0x1800a39bb  lea     r8, [rsp+2060h+Buffer]
0x1800a39c0  xor     edx, edx
0x1800a39c2  mov     ecx, 1
0x1800a39c7  call    cs:__imp_GetBasicProfileFolderPath
0x1800a39cd  jmp     loc_1800A38FE
0x1800a39d2  mov     rax, [rcx]
0x1800a39d5  sub     rax, qword ptr cs:FOLDERID_System.Data1
0x1800a39dc  jnz     short loc_1800A39E9
0x1800a39de  mov     rax, [rcx+8]
0x1800a39e2  sub     rax, qword ptr cs:FOLDERID_System.Data4
0x1800a39e9  test    rax, rax
0x1800a39ec  jz      short loc_1800A3A41
0x1800a39ee  mov     rax, [rcx]
0x1800a39f1  sub     rax, qword ptr cs:FOLDERID_Public.Data1
0x1800a39f8  jnz     short loc_1800A3A05
0x1800a39fa  mov     rax, [rcx+8]
0x1800a39fe  sub     rax, qword ptr cs:FOLDERID_Public.Data4
0x1800a3a05  test    rax, rax
0x1800a3a08  jz      short loc_1800A3A6D
0x1800a3a0a  mov     rax, [rcx]
0x1800a3a0d  sub     rax, qword ptr cs:FOLDERID_ProgramFilesX86.Data1
0x1800a3a14  jnz     short loc_1800A3A21
0x1800a3a16  mov     rax, [rcx+8]
0x1800a3a1a  sub     rax, qword ptr cs:FOLDERID_ProgramFilesX86.Data4
0x1800a3a21  test    rax, rax
0x1800a3a24  jnz     short loc_1800A3A8A
0x1800a3a26  xor     r9d, r9d; unsigned int
0x1800a3a29  lea     rcx, aProgramfilesdi_1; "ProgramFilesDir (x86)"
0x1800a3a30  lea     rdx, [rsp+2060h+Buffer]; pvData
0x1800a3a35  call    ?_GetProgramFiles@kfapi@@YAJPEBGPEAGIK@Z; kfapi::_GetProgramFiles(ushort const *,ushort *,uint,ulong)
0x1800a3a3a  mov     ebx, eax
0x1800a3a3c  jmp     loc_1800A3900
0x1800a3a41  mov     edx, 1000h; uSize
0x1800a3a46  lea     rcx, [rsp+2060h+Buffer]; lpBuffer
0x1800a3a4b  call    cs:__imp_GetSystemDirectoryW
0x1800a3a51  test    eax, eax
0x1800a3a53  jz      loc_1800A38B8
0x1800a3a59  xor     ebx, ebx
0x1800a3a5b  mov     edi, 8007007Ah
0x1800a3a60  cmp     eax, 1000h
0x1800a3a65  cmovnb  ebx, edi
0x1800a3a68  jmp     loc_1800A3900
0x1800a3a6d  mov     r9d, 1000h
0x1800a3a73  lea     r8, [rsp+2060h+Buffer]
0x1800a3a78  xor     edx, edx
0x1800a3a7a  mov     ecx, 3
0x1800a3a7f  call    cs:__imp_GetBasicProfileFolderPath
0x1800a3a85  jmp     loc_1800A38FE
0x1800a3a8a  mov     rax, [rcx]
0x1800a3a8d  sub     rax, qword ptr cs:FOLDERID_ProgramFiles.Data1
0x1800a3a94  jnz     short loc_1800A3AA1
0x1800a3a96  mov     rax, [rcx+8]
0x1800a3a9a  sub     rax, qword ptr cs:FOLDERID_ProgramFiles.Data4
0x1800a3aa1  test    rax, rax
0x1800a3aa4  jz      loc_1800A3BFB
0x1800a3aaa  mov     rax, [rcx]
0x1800a3aad  sub     rax, qword ptr cs:FOLDERID_ProgramFilesX64.Data1
0x1800a3ab4  jnz     short loc_1800A3AC1
0x1800a3ab6  mov     rax, [rcx+8]
0x1800a3aba  sub     rax, qword ptr cs:FOLDERID_ProgramFilesX64.Data4
0x1800a3ac1  test    rax, rax
0x1800a3ac4  jz      loc_1800A3C16
0x1800a3aca  mov     rax, [rcx]
0x1800a3acd  sub     rax, qword ptr cs:FOLDERID_ProgramFilesCommonX86.Data1
0x1800a3ad4  jnz     short loc_1800A3AE1
0x1800a3ad6  mov     rax, [rcx+8]
0x1800a3ada  sub     rax, qword ptr cs:FOLDERID_ProgramFilesCommonX86.Data4
0x1800a3ae1  test    rax, rax
0x1800a3ae4  jz      loc_1800A3C34
0x1800a3aea  mov     rax, [rcx]
0x1800a3aed  sub     rax, qword ptr cs:FOLDERID_ProgramFilesCommon.Data1
0x1800a3af4  jnz     short loc_1800A3B01
0x1800a3af6  mov     rax, [rcx+8]
0x1800a3afa  sub     rax, qword ptr cs:FOLDERID_ProgramFilesCommon.Data4
0x1800a3b01  test    rax, rax
0x1800a3b04  jz      loc_1800A3C4F
0x1800a3b0a  mov     rax, [rcx]
0x1800a3b0d  sub     rax, qword ptr cs:FOLDERID_ProgramFilesCommonX64.Data1
0x1800a3b14  jnz     short loc_1800A3B21
0x1800a3b16  mov     rax, [rcx+8]
0x1800a3b1a  sub     rax, qword ptr cs:FOLDERID_ProgramFilesCommonX64.Data4
0x1800a3b21  test    rax, rax
0x1800a3b24  jz      loc_1800A3C5E
0x1800a3b2a  mov     rax, [rcx]
0x1800a3b2d  sub     rax, qword ptr cs:FOLDERID_SystemX86.Data1
0x1800a3b34  jnz     short loc_1800A3B41
0x1800a3b36  mov     rax, [rcx+8]
0x1800a3b3a  sub     rax, qword ptr cs:FOLDERID_SystemX86.Data4
0x1800a3b41  test    rax, rax
0x1800a3b44  jz      loc_1800A3C66
0x1800a3b4a  mov     rax, [rcx]
0x1800a3b4d  sub     rax, qword ptr cs:FOLDERID_ResourceDir.Data1
0x1800a3b54  jnz     short loc_1800A3B61
0x1800a3b56  mov     rax, [rcx+8]
0x1800a3b5a  sub     rax, qword ptr cs:FOLDERID_ResourceDir.Data4
0x1800a3b61  test    rax, rax
0x1800a3b64  jz      loc_1800A3CC9
0x1800a3b6a  mov     rax, [rcx]
0x1800a3b6d  sub     rax, qword ptr cs:FOLDERID_LocalizedResourcesDir.Data1
0x1800a3b74  jnz     short loc_1800A3B81
0x1800a3b76  mov     rax, [rcx+8]
0x1800a3b7a  sub     rax, qword ptr cs:FOLDERID_LocalizedResourcesDir.Data4
0x1800a3b81  test    rax, rax
0x1800a3b84  jz      loc_1800A3CDC
0x1800a3b8a  mov     rax, [rcx]
0x1800a3b8d  sub     rax, qword ptr cs:FOLDERID_Fonts.Data1
0x1800a3b94  jnz     short loc_1800A3BA1
0x1800a3b96  mov     rax, [rcx+8]
0x1800a3b9a  sub     rax, qword ptr cs:FOLDERID_Fonts.Data4
0x1800a3ba1  test    rax, rax
0x1800a3ba4  jnz     loc_1800A3CF2
0x1800a3baa  mov     edx, 1000h; uSize
0x1800a3baf  lea     rcx, [rsp+2060h+Buffer]; lpBuffer
0x1800a3bb4  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800a3bba  test    eax, eax
0x1800a3bbc  jnz     loc_1800A3D8D
0x1800a3bc2  call    cs:__imp_GetLastError
0x1800a3bc8  mov     ebx, eax
0x1800a3bca  test    eax, eax
0x1800a3bcc  jle     short loc_1800A3BD7
0x1800a3bce  movzx   ebx, ax
0x1800a3bd1  or      ebx, 80070000h
0x1800a3bd7  test    ebx, ebx
0x1800a3bd9  js      loc_1800A3928
0x1800a3bdf  lea     r8, aFonts; "Fonts"
0x1800a3be6  mov     edx, 1000h; cchPath
0x1800a3beb  lea     rcx, [rsp+2060h+Buffer]; pszPath
0x1800a3bf0  call    cs:__imp_PathCchAppend
0x1800a3bf6  jmp     loc_1800A38FE
0x1800a3bfb  xor     r9d, r9d; unsigned int
0x1800a3bfe  lea     rcx, aProgramfilesdi_2; "ProgramFilesDir"
0x1800a3c05  lea     rdx, [rsp+2060h+Buffer]; pvData
0x1800a3c0a  call    ?_GetProgramFiles@kfapi@@YAJPEBGPEAGIK@Z; kfapi::_GetProgramFiles(ushort const *,ushort *,uint,ulong)
0x1800a3c0f  mov     ebx, eax
0x1800a3c11  jmp     loc_1800A3900
0x1800a3c16  mov     r9d, 100h; unsigned int
0x1800a3c1c  lea     rcx, aProgramfilesdi_2; "ProgramFilesDir"
0x1800a3c23  lea     rdx, [rsp+2060h+Buffer]; pvData
0x1800a3c28  call    ?_GetProgramFiles@kfapi@@YAJPEBGPEAGIK@Z; kfapi::_GetProgramFiles(ushort const *,ushort *,uint,ulong)
0x1800a3c2d  mov     ebx, eax
0x1800a3c2f  jmp     loc_1800A3900
0x1800a3c34  xor     r9d, r9d; unsigned int
0x1800a3c37  lea     rcx, aCommonfilesdir_1; "CommonFilesDir (x86)"
0x1800a3c3e  lea     rdx, [rsp+2060h+Buffer]; pvData
0x1800a3c43  call    ?_GetProgramFiles@kfapi@@YAJPEBGPEAGIK@Z; kfapi::_GetProgramFiles(ushort const *,ushort *,uint,ulong)
0x1800a3c48  mov     ebx, eax
0x1800a3c4a  jmp     loc_1800A3900
0x1800a3c4f  xor     r9d, r9d
0x1800a3c52  lea     rcx, aCommonfilesdir_2; "CommonFilesDir"
0x1800a3c59  jmp     loc_1800A3A30
0x1800a3c5e  mov     r9d, 100h
0x1800a3c64  jmp     short loc_1800A3C52
0x1800a3c66  mov     edx, 1000h; uSize
0x1800a3c6b  lea     rcx, [rsp+2060h+Buffer]; lpBuffer
0x1800a3c70  call    cs:__imp_GetSystemWow64DirectoryW
0x1800a3c76  mov     ecx, eax
0x1800a3c78  xor     ebx, ebx
0x1800a3c7a  mov     edi, 8007007Ah
0x1800a3c7f  test    eax, eax
0x1800a3c81  jnz     loc_1800A3DA1
0x1800a3c87  call    cs:__imp_GetLastError
0x1800a3c8d  test    eax, eax
0x1800a3c8f  jle     short loc_1800A3C99
0x1800a3c91  movzx   eax, ax
0x1800a3c94  or      eax, 80070000h
0x1800a3c99  cmp     eax, 80070078h
0x1800a3c9e  jnz     loc_1800A38FE
0x1800a3ca4  mov     edx, 1000h; uSize
0x1800a3ca9  lea     rcx, [rsp+2060h+Buffer]; lpBuffer
0x1800a3cae  call    cs:__imp_GetSystemDirectoryW
0x1800a3cb4  test    eax, eax
0x1800a3cb6  jz      loc_1800A38B8
0x1800a3cbc  cmp     eax, 1000h
0x1800a3cc1  cmovnb  ebx, edi
0x1800a3cc4  jmp     loc_1800A3900
0x1800a3cc9  lea     rdx, [rsp+2060h+Buffer]; int
0x1800a3cce  xor     ecx, ecx; this
0x1800a3cd0  call    ?_GetResourcesDir@kfapi@@YAJHPEAGK@Z; kfapi::_GetResourcesDir(int,ushort *,ulong)
0x1800a3cd5  mov     ebx, eax
0x1800a3cd7  jmp     loc_1800A3900
0x1800a3cdc  lea     rdx, [rsp+2060h+Buffer]; int
0x1800a3ce1  mov     ecx, 1; this
0x1800a3ce6  call    ?_GetResourcesDir@kfapi@@YAJHPEAGK@Z; kfapi::_GetResourcesDir(int,ushort *,ulong)
0x1800a3ceb  mov     ebx, eax
0x1800a3ced  jmp     loc_1800A3900
0x1800a3cf2  mov     rax, [rcx]
0x1800a3cf5  sub     rax, cs:qword_1806F4D88
0x1800a3cfc  jnz     short loc_1800A3D09
0x1800a3cfe  mov     rax, [rcx+8]
0x1800a3d02  sub     rax, cs:qword_1806F4D90
0x1800a3d09  test    rax, rax
0x1800a3d0c  jz      loc_1800A3DB1
0x1800a3d12  mov     rax, [rcx]
0x1800a3d15  sub     rax, cs:qword_1806F4E18
0x1800a3d1c  jnz     short loc_1800A3D29
0x1800a3d1e  mov     rax, [rcx+8]
0x1800a3d22  sub     rax, cs:qword_1806F4E20
0x1800a3d29  test    rax, rax
0x1800a3d2c  jz      loc_1800A3DEC
0x1800a3d32  mov     rax, [rcx]
0x1800a3d35  sub     rax, cs:qword_1806F4E28
0x1800a3d3c  jnz     short loc_1800A3D49
0x1800a3d3e  mov     rax, [rcx+8]
0x1800a3d42  sub     rax, cs:qword_1806F4E30
0x1800a3d49  test    rax, rax
0x1800a3d4c  jnz     loc_1800A3E27
0x1800a3d52  mov     r8d, 1000h; unsigned __int16 *
0x1800a3d58  lea     rdx, [rsp+2060h+Buffer]; void *
0x1800a3d5d  mov     rcx, r10; this
0x1800a3d60  call    ?GetUserProfileDir@kfapi@@YAJPEAXPEAGI@Z; kfapi::GetUserProfileDir(void *,ushort *,uint)
  ... truncated ...
```
