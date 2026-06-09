# kfapi::CFixedFolderLoader::GetPath(_GUID const &,void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180075790`
- end: `0x180075e85`
- name: `?GetPath@CFixedFolderLoader@kfapi@@SAJAEBU_GUID@@PEAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1781`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180073c50`

## callees

- `0x180074868`
- `0x180074958`
- `0x180075548`
- `0x180075790`
- `0x180075e8c`
- `0x180132350`
- `0x180133f50`
- `0x1801f4760`
- `0x1802eeaec`
- `0x180346a50`
- `0x1803b1f60`
- `0x180649650`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800757fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075b2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075c02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800757fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075b2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075c02`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800759a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180075c2f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800759a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180075c2f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180075b1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180075b1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800757ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800757ea`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180075b63`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180075b63`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x180075be5`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x180075be5`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800758e7`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18007591e`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800759e0`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800758e7`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18007591e`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800759e0`

## string_xrefs

- `0x180075bc7`: `CommonFilesDir`
- `0x180075bae`: `CommonFilesDir (x86)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall kfapi::CFixedFolderLoader::GetPath(_QWORD *a1, kfapi *a2, unsigned __int16 *a3, unsigned int a4)
{
  __int64 v5; // rax
  UINT WindowsDirectoryW; // eax
  signed int LastError; // eax
  int v8; // ebx
  __int64 v9; // rax
  signed int UserProfileDir; // eax
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
  const WCHAR *v32; // r8
  UINT SystemWow64DirectoryW; // ecx
  UINT v34; // eax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rdx
  const unsigned __int16 *v42; // r8
  __int64 v43; // rdx
  unsigned __int16 *v44[3]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v45; // [rsp+38h] [rbp-C8h]
  WCHAR Buffer[4096]; // [rsp+40h] [rbp-C0h] BYREF

  v5 = *a1 - *(_QWORD *)&FOLDERID_Windows.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_Windows.Data1 )
    v5 = a1[1] - *(_QWORD *)FOLDERID_Windows.Data4;
  if ( !v5 )
  {
    WindowsDirectoryW = GetWindowsDirectoryW(Buffer, 0x1000u);
    if ( WindowsDirectoryW )
    {
      v8 = 0;
      if ( WindowsDirectoryW >= 0x1000 )
        v8 = -2147024774;
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
    v8 = UserProfileDir;
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
      v8 = 0;
      if ( SystemDirectoryW >= 0x1000 )
        v8 = -2147024774;
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
    UserProfileDir = kfapi::_GetProgramFiles(v19, Buffer, a3, v18, (unsigned int)v44[0]);
    goto LABEL_11;
  }
  v21 = *a1 - *(_QWORD *)&FOLDERID_ProgramFiles.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_ProgramFiles.Data1 )
    v21 = a1[1] - *(_QWORD *)FOLDERID_ProgramFiles.Data4;
  if ( !v21 )
  {
    UserProfileDir = kfapi::_GetProgramFiles(L"ProgramFilesDir", Buffer, a3, 0, (unsigned int)v44[0]);
    goto LABEL_11;
  }
  v22 = *a1 - *(_QWORD *)&FOLDERID_ProgramFilesX64.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_ProgramFilesX64.Data1 )
    v22 = a1[1] - *(_QWORD *)FOLDERID_ProgramFilesX64.Data4;
  if ( !v22 )
  {
    UserProfileDir = kfapi::_GetProgramFiles(L"ProgramFilesDir", Buffer, a3, 0x100u, (unsigned int)v44[0]);
    goto LABEL_11;
  }
  v23 = *a1 - *(_QWORD *)&FOLDERID_ProgramFilesCommonX86.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_ProgramFilesCommonX86.Data1 )
    v23 = a1[1] - *(_QWORD *)FOLDERID_ProgramFilesCommonX86.Data4;
  if ( !v23 )
  {
    UserProfileDir = kfapi::_GetProgramFiles(L"CommonFilesDir (x86)", Buffer, a3, 0, (unsigned int)v44[0]);
    goto LABEL_11;
  }
  v24 = *a1 - *(_QWORD *)&FOLDERID_ProgramFilesCommon.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_ProgramFilesCommon.Data1 )
    v24 = a1[1] - *(_QWORD *)FOLDERID_ProgramFilesCommon.Data4;
  if ( !v24 )
  {
    v18 = 0;
LABEL_81:
    v19 = L"CommonFilesDir";
    goto LABEL_38;
  }
  v25 = *a1 - *(_QWORD *)&FOLDERID_ProgramFilesCommonX64.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_ProgramFilesCommonX64.Data1 )
    v25 = a1[1] - *(_QWORD *)FOLDERID_ProgramFilesCommonX64.Data4;
  if ( !v25 )
  {
    v18 = 256;
    goto LABEL_81;
  }
  v26 = *a1 - *(_QWORD *)&FOLDERID_SystemX86.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_SystemX86.Data1 )
    v26 = a1[1] - *(_QWORD *)FOLDERID_SystemX86.Data4;
  if ( !v26 )
  {
    SystemWow64DirectoryW = GetSystemWow64DirectoryW(Buffer, 0x1000u);
    v8 = 0;
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
    v34 = GetSystemDirectoryW(Buffer, 0x1000u);
    if ( v34 )
    {
      if ( v34 >= 0x1000 )
        v8 = -2147024774;
      goto LABEL_12;
    }
LABEL_5:
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_12;
  }
  v27 = *a1 - *(_QWORD *)&FOLDERID_ResourceDir.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_ResourceDir.Data1 )
    v27 = a1[1] - *(_QWORD *)FOLDERID_ResourceDir.Data4;
  if ( !v27 )
  {
    UserProfileDir = kfapi::_GetResourcesDir(0, (int)Buffer, a3, a4);
    goto LABEL_11;
  }
  v28 = *a1 - *(_QWORD *)&FOLDERID_LocalizedResourcesDir.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_LocalizedResourcesDir.Data1 )
    v28 = a1[1] - *(_QWORD *)FOLDERID_LocalizedResourcesDir.Data4;
  if ( !v28 )
  {
    UserProfileDir = kfapi::_GetResourcesDir((kfapi *)1, (int)Buffer, a3, a4);
    goto LABEL_11;
  }
  v29 = *a1 - *(_QWORD *)&FOLDERID_Fonts.Data1;
  if ( *a1 == *(_QWORD *)&FOLDERID_Fonts.Data1 )
    v29 = a1[1] - *(_QWORD *)FOLDERID_Fonts.Data4;
  if ( !v29 )
  {
    SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x1000u);
    if ( SystemWindowsDirectoryW )
    {
      v8 = 0;
      if ( SystemWindowsDirectoryW >= 0x1000 )
        v8 = -2147024774;
    }
    else
    {
      v31 = GetLastError();
      v8 = v31;
      if ( v31 > 0 )
        v8 = (unsigned __int16)v31 | 0x80070000;
    }
    if ( v8 < 0 )
      return (unsigned int)v8;
    v32 = L"Fonts";
    goto LABEL_76;
  }
  v35 = *a1 - 0x4BDA9EFE915221FBLL;
  if ( *a1 == 0x4BDA9EFE915221FBLL )
    v35 = a1[1] + 0x78B0883572082871LL;
  if ( !v35 )
  {
    v8 = kfapi::GetUserProfileDir(a2, Buffer, (unsigned __int16 *)0x1000, a4);
    if ( v8 >= 0 )
    {
      v32 = L"AppData\\Roaming\\Microsoft\\Credentials";
      goto LABEL_76;
    }
LABEL_12:
    if ( v8 >= 0 )
    {
      v11 = -1;
      do
        ++v11;
      while ( Buffer[v11] );
      std::wstring::_Assign<unsigned short>(a3, Buffer);
    }
    return (unsigned int)v8;
  }
  v36 = *a1 - 0x49A9E7BDB88F4DAALL;
  if ( *a1 == 0x49A9E7BDB88F4DAALL )
    v36 = a1[1] - 0x65C75D5A88024DB7LL;
  if ( !v36 )
  {
    v8 = kfapi::GetUserProfileDir(a2, Buffer, (unsigned __int16 *)0x1000, a4);
    if ( v8 >= 0 )
    {
      v32 = L"AppData\\Roaming\\Microsoft\\Crypto";
      goto LABEL_76;
    }
    goto LABEL_12;
  }
  v37 = *a1 - 0x4567EF9110C07CD0LL;
  if ( *a1 == 0x4567EF9110C07CD0LL )
    v37 = a1[1] + 0x6C8348874BBAF48LL;
  if ( !v37 )
  {
    v8 = kfapi::GetUserProfileDir(a2, Buffer, (unsigned __int16 *)0x1000, a4);
    if ( v8 >= 0 )
    {
      v32 = L"AppData\\Roaming\\Microsoft\\Protect";
LABEL_76:
      v8 = PathCchAppend(Buffer, 0x1000u, v32);
      goto LABEL_12;
    }
    goto LABEL_12;
  }
  v38 = *a1 - 0x4FDBE7CA54EED2E0LL;
  if ( *a1 == 0x4FDBE7CA54EED2E0LL )
    v38 = a1[1] + 0x5E3D6B8BDF0B76FLL;
  if ( !v38 )
  {
    UserProfileDir = kfapi::GetProfileRelativeDirectory(
                       a2,
                       Buffer,
                       a3,
                       (unsigned int)L"AppData\\Roaming\\Microsoft\\SystemCertificates",
                       v44[0]);
    goto LABEL_11;
  }
  v39 = *a1 - 0x4C9D71852856B913LL;
  if ( *a1 == 0x4C9D71852856B913LL )
    v39 = a1[1] - 0x143CA8691298CC9ALL;
  if ( !v39 )
  {
    std::wstring::wstring(v44);
    v8 = kfapi::ExpandString(L"%SystemDrive%\\Data\\SharedData", v41, v44);
    if ( v8 >= 0 )
    {
      v42 = (const unsigned __int16 *)v44;
      if ( v45 > 7 )
        v42 = v44[0];
      goto LABEL_132;
    }
LABEL_133:
    std::pair<std::wstring,int>::~pair<std::wstring,int>(v44);
    goto LABEL_12;
  }
  v40 = *a1 - 0x48E0CFD58C19F0BCLL;
  if ( *a1 == 0x48E0CFD58C19F0BCLL )
    v40 = a1[1] - 0x68E351F082067B80LL;
  if ( !v40 )
  {
    std::wstring::wstring(v44);
    v8 = kfapi::ExpandString(L"%SystemDrive%\\Data\\SystemData", v43, v44);
    if ( v8 >= 0 )
    {
      v42 = (const unsigned __int16 *)v44;
      if ( v45 > 7 )
        v42 = v44[0];
LABEL_132:
      v8 = StringCchCopyW(Buffer, 0x1000u, v42);
      goto LABEL_133;
    }
    goto LABEL_133;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180075790  mov     [rsp-8+arg_0], rbx
0x180075795  push    rbp
0x180075796  push    rsi
0x180075797  push    rdi
0x180075798  lea     rbp, [rsp-1F50h]
0x1800757a0  mov     eax, 2050h
0x1800757a5  call    _alloca_probe
0x1800757aa  sub     rsp, rax
0x1800757ad  mov     rax, cs:__security_cookie
0x1800757b4  xor     rax, rsp
0x1800757b7  mov     [rbp+1F60h+var_20], rax
0x1800757be  mov     rsi, r8
0x1800757c1  mov     r10, rdx
0x1800757c4  mov     rax, [rcx]
0x1800757c7  sub     rax, qword ptr cs:FOLDERID_Windows.Data1
0x1800757ce  jnz     short loc_1800757DB
0x1800757d0  mov     rax, [rcx+8]
0x1800757d4  sub     rax, qword ptr cs:FOLDERID_Windows.Data4
0x1800757db  test    rax, rax
0x1800757de  jnz     short loc_18007581B
0x1800757e0  mov     edx, 1000h; uSize
0x1800757e5  lea     rcx, [rsp+2060h+Buffer]; lpBuffer
0x1800757ea  call    cs:__imp_GetWindowsDirectoryW
0x1800757f1  nop     dword ptr [rax+rax+00h]
0x1800757f6  test    eax, eax
0x1800757f8  jnz     loc_1800758F8
0x1800757fe  call    cs:__imp_GetLastError
0x180075805  nop     dword ptr [rax+rax+00h]
0x18007580a  mov     ebx, eax
0x18007580c  test    eax, eax
0x18007580e  jle     short loc_18007584C
0x180075810  movzx   ebx, ax
0x180075813  or      ebx, 80070000h
0x180075819  jmp     short loc_18007584C
0x18007581b  mov     rax, [rcx]
0x18007581e  sub     rax, qword ptr cs:FOLDERID_Profile.Data1
0x180075825  jnz     short loc_180075832
0x180075827  mov     rax, [rcx+8]
0x18007582b  sub     rax, qword ptr cs:FOLDERID_Profile.Data4
0x180075832  test    rax, rax
0x180075835  jnz     short loc_18007589D
0x180075837  mov     r8d, 1000h; unsigned __int16 *
0x18007583d  lea     rdx, [rsp+2060h+Buffer]; void *
0x180075842  mov     rcx, r10; this
0x180075845  call    ?GetUserProfileDir@kfapi@@YAJPEAXPEAGI@Z; kfapi::GetUserProfileDir(void *,ushort *,uint)
0x18007584a  mov     ebx, eax
0x18007584c  test    ebx, ebx
0x18007584e  js      short loc_180075878
0x180075850  lea     rax, [rsp+2060h+Buffer]
0x180075855  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18007585c  nop     dword ptr [rax+00h]
0x180075860  inc     r8
0x180075863  cmp     word ptr [rax+r8*2], 0
0x180075869  jnz     short loc_180075860
0x18007586b  lea     rdx, [rsp+2060h+Buffer]
0x180075870  mov     rcx, rsi
0x180075873  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180075878  mov     eax, ebx
0x18007587a  mov     rcx, [rbp+1F60h+var_20]
0x180075881  xor     rcx, rsp; StackCookie
0x180075884  call    __security_check_cookie
0x180075889  mov     rbx, [rsp+2060h+arg_0]
0x180075891  add     rsp, 2050h
0x180075898  pop     rdi
0x180075899  pop     rsi
0x18007589a  pop     rbp
0x18007589b  retn
0x18007589d  mov     rax, [rcx]
0x1800758a0  sub     rax, qword ptr cs:FOLDERID_UserProfiles.Data1
0x1800758a7  jnz     short loc_1800758B4
0x1800758a9  mov     rax, [rcx+8]
0x1800758ad  sub     rax, qword ptr cs:FOLDERID_UserProfiles.Data4
0x1800758b4  test    rax, rax
0x1800758b7  jz      short loc_18007590C
0x1800758b9  mov     rax, [rcx]
0x1800758bc  sub     rax, qword ptr cs:FOLDERID_ProgramData.Data1
0x1800758c3  jnz     short loc_1800758D0
0x1800758c5  mov     rax, [rcx+8]
0x1800758c9  sub     rax, qword ptr cs:FOLDERID_ProgramData.Data4
0x1800758d0  test    rax, rax
0x1800758d3  jnz     short loc_18007592F
0x1800758d5  mov     r9d, 1000h
0x1800758db  lea     r8, [rsp+2060h+Buffer]
0x1800758e0  xor     edx, edx
0x1800758e2  mov     ecx, 4
0x1800758e7  call    cs:__imp_GetBasicProfileFolderPath
0x1800758ee  nop     dword ptr [rax+rax+00h]
0x1800758f3  jmp     loc_18007584A
0x1800758f8  xor     ebx, ebx
0x1800758fa  mov     edi, 8007007Ah
0x1800758ff  cmp     eax, 1000h
0x180075904  cmovnb  ebx, edi
0x180075907  jmp     loc_18007584C
0x18007590c  mov     r9d, 1000h
0x180075912  lea     r8, [rsp+2060h+Buffer]
0x180075917  xor     edx, edx
0x180075919  mov     ecx, 1
0x18007591e  call    cs:__imp_GetBasicProfileFolderPath
0x180075925  nop     dword ptr [rax+rax+00h]
0x18007592a  jmp     loc_18007584A
0x18007592f  mov     rax, [rcx]
0x180075932  sub     rax, qword ptr cs:FOLDERID_System.Data1
0x180075939  jnz     short loc_180075946
0x18007593b  mov     rax, [rcx+8]
0x18007593f  sub     rax, qword ptr cs:FOLDERID_System.Data4
0x180075946  test    rax, rax
0x180075949  jz      short loc_18007599C
0x18007594b  mov     rax, [rcx]
0x18007594e  sub     rax, qword ptr cs:FOLDERID_Public.Data1
0x180075955  jnz     short loc_180075962
0x180075957  mov     rax, [rcx+8]
0x18007595b  sub     rax, qword ptr cs:FOLDERID_Public.Data4
0x180075962  test    rax, rax
0x180075965  jz      short loc_1800759CE
0x180075967  mov     rax, [rcx]
0x18007596a  sub     rax, qword ptr cs:FOLDERID_ProgramFilesX86.Data1
0x180075971  jnz     short loc_18007597E
0x180075973  mov     rax, [rcx+8]
0x180075977  sub     rax, qword ptr cs:FOLDERID_ProgramFilesX86.Data4
0x18007597e  test    rax, rax
0x180075981  jnz     short loc_1800759F1
0x180075983  xor     r9d, r9d; unsigned int
0x180075986  lea     rcx, aProgramfilesdi_1; "ProgramFilesDir (x86)"
0x18007598d  lea     rdx, [rsp+2060h+Buffer]; pvData
0x180075992  call    ?_GetProgramFiles@kfapi@@YAJPEBGPEAGIK@Z; kfapi::_GetProgramFiles(ushort const *,ushort *,uint,ulong)
0x180075997  jmp     loc_18007584A
0x18007599c  mov     edx, 1000h; uSize
0x1800759a1  lea     rcx, [rsp+2060h+Buffer]; lpBuffer
0x1800759a6  call    cs:__imp_GetSystemDirectoryW
0x1800759ad  nop     dword ptr [rax+rax+00h]
0x1800759b2  test    eax, eax
0x1800759b4  jz      loc_1800757FE
0x1800759ba  xor     ebx, ebx
0x1800759bc  mov     edi, 8007007Ah
0x1800759c1  cmp     eax, 1000h
0x1800759c6  cmovnb  ebx, edi
0x1800759c9  jmp     loc_18007584C
0x1800759ce  mov     r9d, 1000h
0x1800759d4  lea     r8, [rsp+2060h+Buffer]
0x1800759d9  xor     edx, edx
0x1800759db  mov     ecx, 3
0x1800759e0  call    cs:__imp_GetBasicProfileFolderPath
0x1800759e7  nop     dword ptr [rax+rax+00h]
0x1800759ec  jmp     loc_18007584A
0x1800759f1  mov     rax, [rcx]
0x1800759f4  sub     rax, qword ptr cs:FOLDERID_ProgramFiles.Data1
0x1800759fb  jnz     short loc_180075A08
0x1800759fd  mov     rax, [rcx+8]
0x180075a01  sub     rax, qword ptr cs:FOLDERID_ProgramFiles.Data4
0x180075a08  test    rax, rax
0x180075a0b  jz      loc_180075B76
0x180075a11  mov     rax, [rcx]
0x180075a14  sub     rax, qword ptr cs:FOLDERID_ProgramFilesX64.Data1
0x180075a1b  jnz     short loc_180075A28
0x180075a1d  mov     rax, [rcx+8]
0x180075a21  sub     rax, qword ptr cs:FOLDERID_ProgramFilesX64.Data4
0x180075a28  test    rax, rax
0x180075a2b  jz      loc_180075B8F
0x180075a31  mov     rax, [rcx]
0x180075a34  sub     rax, qword ptr cs:FOLDERID_ProgramFilesCommonX86.Data1
0x180075a3b  jnz     short loc_180075A48
0x180075a3d  mov     rax, [rcx+8]
0x180075a41  sub     rax, qword ptr cs:FOLDERID_ProgramFilesCommonX86.Data4
0x180075a48  test    rax, rax
0x180075a4b  jz      loc_180075BAB
0x180075a51  mov     rax, [rcx]
0x180075a54  sub     rax, qword ptr cs:FOLDERID_ProgramFilesCommon.Data1
0x180075a5b  jnz     short loc_180075A68
0x180075a5d  mov     rax, [rcx+8]
0x180075a61  sub     rax, qword ptr cs:FOLDERID_ProgramFilesCommon.Data4
0x180075a68  test    rax, rax
0x180075a6b  jz      loc_180075BC4
0x180075a71  mov     rax, [rcx]
0x180075a74  sub     rax, qword ptr cs:FOLDERID_ProgramFilesCommonX64.Data1
0x180075a7b  jnz     short loc_180075A88
0x180075a7d  mov     rax, [rcx+8]
0x180075a81  sub     rax, qword ptr cs:FOLDERID_ProgramFilesCommonX64.Data4
0x180075a88  test    rax, rax
0x180075a8b  jz      loc_180075BD3
0x180075a91  mov     rax, [rcx]
0x180075a94  sub     rax, qword ptr cs:FOLDERID_SystemX86.Data1
0x180075a9b  jnz     short loc_180075AA8
0x180075a9d  mov     rax, [rcx+8]
0x180075aa1  sub     rax, qword ptr cs:FOLDERID_SystemX86.Data4
0x180075aa8  test    rax, rax
0x180075aab  jz      loc_180075BDB
0x180075ab1  mov     rax, [rcx]
0x180075ab4  sub     rax, qword ptr cs:FOLDERID_ResourceDir.Data1
0x180075abb  jnz     short loc_180075AC8
0x180075abd  mov     rax, [rcx+8]
0x180075ac1  sub     rax, qword ptr cs:FOLDERID_ResourceDir.Data4
0x180075ac8  test    rax, rax
0x180075acb  jz      loc_180075C50
0x180075ad1  mov     rax, [rcx]
0x180075ad4  sub     rax, qword ptr cs:FOLDERID_LocalizedResourcesDir.Data1
0x180075adb  jnz     short loc_180075AE8
0x180075add  mov     rax, [rcx+8]
0x180075ae1  sub     rax, qword ptr cs:FOLDERID_LocalizedResourcesDir.Data4
0x180075ae8  test    rax, rax
0x180075aeb  jz      loc_180075C61
0x180075af1  mov     rax, [rcx]
0x180075af4  sub     rax, qword ptr cs:FOLDERID_Fonts.Data1
0x180075afb  jnz     short loc_180075B08
0x180075afd  mov     rax, [rcx+8]
0x180075b01  sub     rax, qword ptr cs:FOLDERID_Fonts.Data4
0x180075b08  test    rax, rax
0x180075b0b  jnz     loc_180075C75
0x180075b11  mov     edx, 1000h; uSize
0x180075b16  lea     rcx, [rsp+2060h+Buffer]; lpBuffer
0x180075b1b  call    cs:__imp_GetSystemWindowsDirectoryW
0x180075b22  nop     dword ptr [rax+rax+00h]
0x180075b27  test    eax, eax
0x180075b29  jnz     loc_180075CFE
0x180075b2f  call    cs:__imp_GetLastError
0x180075b36  nop     dword ptr [rax+rax+00h]
0x180075b3b  mov     ebx, eax
0x180075b3d  test    eax, eax
0x180075b3f  jle     short loc_180075B4A
0x180075b41  movzx   ebx, ax
0x180075b44  or      ebx, 80070000h
0x180075b4a  test    ebx, ebx
0x180075b4c  js      loc_180075878
0x180075b52  lea     r8, aFonts; "Fonts"
0x180075b59  mov     edx, 1000h; cchPath
0x180075b5e  lea     rcx, [rsp+2060h+Buffer]; pszPath
0x180075b63  call    cs:__imp_PathCchAppend
0x180075b6a  nop     dword ptr [rax+rax+00h]
0x180075b6f  mov     ebx, eax
0x180075b71  jmp     loc_18007584C
0x180075b76  xor     r9d, r9d; unsigned int
0x180075b79  lea     rcx, aProgramfilesdi_2; "ProgramFilesDir"
0x180075b80  lea     rdx, [rsp+2060h+Buffer]; pvData
0x180075b85  call    ?_GetProgramFiles@kfapi@@YAJPEBGPEAGIK@Z; kfapi::_GetProgramFiles(ushort const *,ushort *,uint,ulong)
0x180075b8a  jmp     loc_18007584A
0x180075b8f  mov     r9d, 100h; unsigned int
0x180075b95  lea     rcx, aProgramfilesdi_2; "ProgramFilesDir"
0x180075b9c  lea     rdx, [rsp+2060h+Buffer]; pvData
0x180075ba1  call    ?_GetProgramFiles@kfapi@@YAJPEBGPEAGIK@Z; kfapi::_GetProgramFiles(ushort const *,ushort *,uint,ulong)
0x180075ba6  jmp     loc_18007584A
0x180075bab  xor     r9d, r9d; unsigned int
0x180075bae  lea     rcx, aCommonfilesdir_1; "CommonFilesDir (x86)"
0x180075bb5  lea     rdx, [rsp+2060h+Buffer]; pvData
0x180075bba  call    ?_GetProgramFiles@kfapi@@YAJPEBGPEAGIK@Z; kfapi::_GetProgramFiles(ushort const *,ushort *,uint,ulong)
0x180075bbf  jmp     loc_18007584A
0x180075bc4  xor     r9d, r9d
0x180075bc7  lea     rcx, aCommonfilesdir_2; "CommonFilesDir"
0x180075bce  jmp     loc_18007598D
0x180075bd3  mov     r9d, 100h
0x180075bd9  jmp     short loc_180075BC7
0x180075bdb  mov     edx, 1000h; uSize
0x180075be0  lea     rcx, [rsp+2060h+Buffer]; lpBuffer
0x180075be5  call    cs:__imp_GetSystemWow64DirectoryW
0x180075bec  nop     dword ptr [rax+rax+00h]
0x180075bf1  mov     ecx, eax
0x180075bf3  xor     ebx, ebx
0x180075bf5  mov     edi, 8007007Ah
0x180075bfa  test    eax, eax
0x180075bfc  jnz     loc_180075D12
0x180075c02  call    cs:__imp_GetLastError
0x180075c09  nop     dword ptr [rax+rax+00h]
0x180075c0e  test    eax, eax
0x180075c10  jle     short loc_180075C1A
0x180075c12  movzx   eax, ax
0x180075c15  or      eax, 80070000h
0x180075c1a  cmp     eax, 80070078h
0x180075c1f  jnz     loc_18007584A
0x180075c25  mov     edx, 1000h; uSize
0x180075c2a  lea     rcx, [rsp+2060h+Buffer]; lpBuffer
0x180075c2f  call    cs:__imp_GetSystemDirectoryW
0x180075c36  nop     dword ptr [rax+rax+00h]
0x180075c3b  test    eax, eax
0x180075c3d  jz      loc_1800757FE
0x180075c43  cmp     eax, 1000h
0x180075c48  cmovnb  ebx, edi
0x180075c4b  jmp     loc_18007584C
0x180075c50  lea     rdx, [rsp+2060h+Buffer]; int
0x180075c55  xor     ecx, ecx; this
0x180075c57  call    ?_GetResourcesDir@kfapi@@YAJHPEAGK@Z; kfapi::_GetResourcesDir(int,ushort *,ulong)
0x180075c5c  jmp     loc_18007584A
0x180075c61  lea     rdx, [rsp+2060h+Buffer]; int
0x180075c66  mov     ecx, 1; this
0x180075c6b  call    ?_GetResourcesDir@kfapi@@YAJHPEAGK@Z; kfapi::_GetResourcesDir(int,ushort *,ulong)
0x180075c70  jmp     loc_18007584A
0x180075c75  mov     rax, [rcx]
0x180075c78  sub     rax, cs:qword_180718DE8
0x180075c7f  jnz     short loc_180075C8C
0x180075c81  mov     rax, [rcx+8]
0x180075c85  sub     rax, cs:qword_180718DF0
0x180075c8c  test    rax, rax
0x180075c8f  jz      loc_180075D22
0x180075c95  mov     rax, [rcx]
0x180075c98  sub     rax, cs:qword_180718E50
0x180075c9f  jnz     short loc_180075CAC
0x180075ca1  mov     rax, [rcx+8]
0x180075ca5  sub     rax, cs:qword_180718E58
0x180075cac  test    rax, rax
0x180075caf  jz      loc_180075D4B
0x180075cb5  mov     rax, [rcx]
0x180075cb8  sub     rax, cs:qword_180718E60
0x180075cbf  jnz     short loc_180075CCC
  ... truncated ...
```
