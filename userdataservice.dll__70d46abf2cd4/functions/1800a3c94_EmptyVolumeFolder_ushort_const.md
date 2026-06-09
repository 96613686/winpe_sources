# _EmptyVolumeFolder(ushort const *)

- ea: `0x1800a3c94`
- end: `0x1800a41ad`
- name: `?_EmptyVolumeFolder@@YAJPEBG@Z`
- size: `1305`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180030180`

## callees

- `0x180008f0c`
- `0x180018c20`
- `0x18001b340`
- `0x180035040`
- `0x180035c40`
- `0x18003e698`
- `0x18007ba48`
- `0x18007be90`
- `0x18009e71c`
- `0x1800a3c94`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4086`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a40d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4135`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a418d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4086`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a40d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4135`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a418d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800a412a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800a4143`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800a412a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800a4143`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a40b9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a40b9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800a3fcb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800a3fcb`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800a40ca`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800a40ca`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800a407c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800a407c`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1800a3f3e`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1800a3f3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a3dbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a4153`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a3dbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a4153`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800a3de1`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800a3de1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800a3e07`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800a3e07`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800a3d90`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800a3d90`

## string_xrefs

- `0x1800a3d0f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800a3da9`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800a40a2`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800a411b`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800a3e47`: `Comms`

## pseudocode

```c
__int64 __fastcall _EmptyVolumeFolder(const unsigned __int16 *a1)
{
  __int64 v2; // r9
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rcx
  int SystemDataStorePath; // eax
  PWSTR *v7; // rax
  HRESULT v8; // eax
  __int64 v9; // r9
  __int64 v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  HANDLE FirstFileW; // rdi
  BOOL i; // eax
  int v15; // eax
  signed int LastError; // eax
  bool v17; // sf
  signed int v18; // eax
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // rcx
  signed int v23; // eax
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR pszPath[4]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v26; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v27; // [rsp+60h] [rbp-A0h]
  GUID pguid; // [rsp+78h] [rbp-88h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR sz[40]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+330h] [rbp+230h] BYREF
  WCHAR FileName[264]; // [rsp+540h] [rbp+440h] BYREF
  WCHAR NewFileName[264]; // [rsp+750h] [rbp+650h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&v26);
  if ( a1 )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             &v26,
                             a1) )
    {
      v2 = 2420;
LABEL_4:
      v3 = -2147024882;
LABEL_7:
      v4 = 0;
      v5 = v3;
LABEL_8:
      Log_HREvent(
        v5,
        v4,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        v2);
      goto LABEL_83;
    }
    if ( v26 == v27 )
    {
      v2 = 2422;
      v3 = -2147024809;
      goto LABEL_7;
    }
    if ( v26[v27 - v26 - 1] != 92
      && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v26,
                             L"\\") )
    {
      v2 = 2426;
      goto LABEL_4;
    }
  }
  else
  {
    SystemDataStorePath = GetSystemDataStorePath(&v26);
    v3 = SystemDataStorePath;
    if ( SystemDataStorePath < 0 )
    {
      v2 = 2431;
      v4 = 1;
      v5 = (unsigned int)SystemDataStorePath;
      goto LABEL_8;
    }
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(pszPath);
  pv = 0;
  v7 = (PWSTR *)tlx::replace<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),0>(&pv);
  v8 = SHGetKnownFolderPath(&rfid, 0x4000u, 0, v7);
  v3 = v8;
  if ( v8 < 0 )
  {
    v9 = 2436;
LABEL_16:
    v10 = (unsigned int)v8;
    v11 = 1;
    goto LABEL_17;
  }
  pguid = 0;
  v8 = CoCreateGuid(&pguid);
  v3 = v8;
  if ( v8 < 0 )
  {
    v9 = 2440;
    goto LABEL_16;
  }
  StringFromGUID2(&pguid, sz, 39);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           pszPath,
                           pv) )
  {
    v9 = 2445;
LABEL_43:
    v3 = -2147024882;
LABEL_44:
    v11 = 0;
    v10 = v3;
LABEL_17:
    Log_HREvent(
      v10,
      v11,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      v9);
LABEL_18:
    if ( pv )
      CoTaskMemFree(pv);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(pszPath);
    goto LABEL_83;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           pszPath,
                           L"\\") )
  {
    v9 = 2446;
    goto LABEL_43;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           pszPath,
                           L"Comms") )
  {
    v9 = 2447;
    goto LABEL_43;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           pszPath,
                           L"\\") )
  {
    v9 = 2448;
    goto LABEL_43;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           pszPath,
                           L"CorruptVols") )
  {
    v9 = 2449;
    goto LABEL_43;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           pszPath,
                           L"\\") )
  {
    v9 = 2450;
    goto LABEL_43;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           pszPath,
                           L"UDM") )
  {
    v9 = 2451;
    goto LABEL_43;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           pszPath,
                           L"\\") )
  {
    v9 = 2452;
    goto LABEL_43;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           pszPath,
                           sz) )
  {
    v9 = 2453;
    goto LABEL_43;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           pszPath,
                           L"\\") )
  {
    v9 = 2454;
    goto LABEL_43;
  }
  v12 = SHCreateDirectoryExW(0, pszPath[0], 0);
  v3 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v3 = (unsigned __int16)v12 | 0x80070000;
    v9 = 2456;
    goto LABEL_44;
  }
  v8 = StringCchCopyW(FileName, 0x104u, v26);
  v3 = v8;
  if ( v8 < 0 )
  {
    v9 = 2460;
    goto LABEL_16;
  }
  v8 = StringCchCatW(FileName, 0x104u, L"*");
  v3 = v8;
  if ( v8 < 0 )
  {
    v9 = 2461;
    goto LABEL_16;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    for ( i = 1; i; i = FindNextFileW(FirstFileW, &FindFileData) )
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        v15 = StringCchCopyW(ExistingFileName, 0x104u, v26);
        v3 = v15;
        if ( v15 < 0 )
        {
          v19 = 2478;
LABEL_76:
          v20 = 1;
          v21 = (unsigned int)v15;
LABEL_77:
          Log_HREvent(
            v21,
            v20,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
            v19);
          FindClose(FirstFileW);
          goto LABEL_18;
        }
        v15 = StringCchCatW(ExistingFileName, 0x104u, FindFileData.cFileName);
        v3 = v15;
        if ( v15 < 0 )
        {
          v19 = 2479;
          goto LABEL_76;
        }
        v15 = StringCchCopyW(NewFileName, 0x104u, pszPath[0]);
        v3 = v15;
        if ( v15 < 0 )
        {
          v19 = 2482;
          goto LABEL_76;
        }
        v15 = StringCchCatW(NewFileName, 0x104u, FindFileData.cFileName);
        v3 = v15;
        if ( v15 < 0 )
        {
          v19 = 2483;
          goto LABEL_76;
        }
        if ( !MoveFileExW(ExistingFileName, NewFileName, 0) )
        {
          LastError = GetLastError();
          v17 = LastError < 0;
          if ( LastError > 0 )
          {
            LastError = (unsigned __int16)LastError | 0x80070000;
            v17 = LastError < 0;
          }
          if ( v17 )
            Log_HREvent(
              (unsigned int)LastError,
              0,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
              2487);
          if ( !DeleteFileW(ExistingFileName) )
          {
            v18 = GetLastError();
            v3 = v18;
            if ( v18 > 0 )
              v3 = (unsigned __int16)v18 | 0x80070000;
            v19 = 2489;
            goto LABEL_71;
          }
        }
      }
    }
    if ( GetLastError() != 18 )
    {
      v23 = GetLastError();
      v3 = v23;
      if ( v23 > 0 )
        v3 = (unsigned __int16)v23 | 0x80070000;
      v19 = 2495;
LABEL_71:
      v20 = 0;
      v21 = v3;
      goto LABEL_77;
    }
    FindClose(FirstFileW);
  }
  if ( pv )
    CoTaskMemFree(pv);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(pszPath);
  v3 = 0;
LABEL_83:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v26);
  return v3;
}

```

## disassembly

```asm
0x1800a3c94  push    rbp
0x1800a3c96  push    rbx
0x1800a3c97  push    rdi
0x1800a3c98  push    r14
0x1800a3c9a  lea     rbp, [rsp-878h]
0x1800a3ca2  sub     rsp, 978h
0x1800a3ca9  mov     rax, cs:__security_cookie
0x1800a3cb0  xor     rax, rsp
0x1800a3cb3  mov     [rbp+890h+var_30], rax
0x1800a3cba  mov     rbx, rcx
0x1800a3cbd  lea     rcx, [rsp+990h+var_938]; void *
0x1800a3cc2  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800a3cc7  lea     rdi, asc_18013D0B8; "\\"
0x1800a3cce  lea     rcx, [rsp+990h+var_938]
0x1800a3cd3  test    rbx, rbx
0x1800a3cd6  jz      short loc_1800A3D47
0x1800a3cd8  mov     rdx, rbx
0x1800a3cdb  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800a3ce0  test    al, al
0x1800a3ce2  jnz     short loc_1800A3CF1
0x1800a3ce4  mov     r9d, 974h
0x1800a3cea  mov     ebx, 8007000Eh
0x1800a3cef  jmp     short loc_1800A3D0B
0x1800a3cf1  mov     rcx, [rsp+990h+var_938]
0x1800a3cf6  mov     rax, [rsp+990h+var_930]
0x1800a3cfb  cmp     rcx, rax
0x1800a3cfe  jnz     short loc_1800A3D20
0x1800a3d00  mov     r9d, 976h
0x1800a3d06  mov     ebx, 80070057h
0x1800a3d0b  xor     edx, edx
0x1800a3d0d  mov     ecx, ebx
0x1800a3d0f  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800a3d16  call    Log_HREvent
0x1800a3d1b  jmp     loc_1800A4165
0x1800a3d20  sub     rax, rcx
0x1800a3d23  sar     rax, 1
0x1800a3d26  cmp     word ptr [rcx+rax*2-2], 5Ch ; '\'
0x1800a3d2c  jz      short loc_1800A3D61
0x1800a3d2e  mov     rdx, rdi
0x1800a3d31  lea     rcx, [rsp+990h+var_938]
0x1800a3d36  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800a3d3b  test    al, al
0x1800a3d3d  jnz     short loc_1800A3D61
0x1800a3d3f  mov     r9d, 97Ah
0x1800a3d45  jmp     short loc_1800A3CEA
0x1800a3d47  call    ?GetSystemDataStorePath@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetSystemDataStorePath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800a3d4c  mov     ebx, eax
0x1800a3d4e  test    eax, eax
0x1800a3d50  jns     short loc_1800A3D61
0x1800a3d52  mov     r9d, 97Fh
0x1800a3d58  mov     edx, 1
0x1800a3d5d  mov     ecx, eax
0x1800a3d5f  jmp     short loc_1800A3D0F
0x1800a3d61  lea     rcx, [rsp+990h+pszPath]; void *
0x1800a3d66  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800a3d6b  lea     rcx, [rsp+990h+pv]
0x1800a3d70  mov     [rsp+990h+pv], 0
0x1800a3d79  call    ??$replace@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(void *),&CoTaskMemFree(void *),0>(tlx::auto_xxx<ushort *,void (*)(void *),&CoTaskMemFree(void *),0> &)
0x1800a3d7e  mov     r9, rax; ppszPath
0x1800a3d81  lea     rcx, rfid; rfid
0x1800a3d88  xor     r8d, r8d; hToken
0x1800a3d8b  mov     edx, 4000h; dwFlags
0x1800a3d90  call    cs:__imp_SHGetKnownFolderPath
0x1800a3d96  mov     ebx, eax
0x1800a3d98  test    eax, eax
0x1800a3d9a  jns     short loc_1800A3DD4
0x1800a3d9c  mov     r9d, 984h
0x1800a3da2  mov     ecx, eax
0x1800a3da4  mov     edx, 1
0x1800a3da9  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800a3db0  call    Log_HREvent
0x1800a3db5  mov     rcx, [rsp+990h+pv]; pv
0x1800a3dba  test    rcx, rcx
0x1800a3dbd  jz      short loc_1800A3DC5
0x1800a3dbf  call    cs:__imp_CoTaskMemFree
0x1800a3dc5  lea     rcx, [rsp+990h+pszPath]; void *
0x1800a3dca  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800a3dcf  jmp     loc_1800A4165
0x1800a3dd4  xorps   xmm0, xmm0
0x1800a3dd7  lea     rcx, [rsp+990h+pguid]; pguid
0x1800a3ddc  movups  xmmword ptr [rsp+990h+pguid.Data1], xmm0
0x1800a3de1  call    cs:__imp_CoCreateGuid
0x1800a3de7  mov     ebx, eax
0x1800a3de9  test    eax, eax
0x1800a3deb  jns     short loc_1800A3DF5
0x1800a3ded  mov     r9d, 988h
0x1800a3df3  jmp     short loc_1800A3DA2
0x1800a3df5  mov     r8d, 27h ; '''; cchMax
0x1800a3dfb  lea     rdx, [rbp+890h+sz]; lpsz
0x1800a3e02  lea     rcx, [rsp+990h+pguid]; rguid
0x1800a3e07  call    cs:__imp_StringFromGUID2
0x1800a3e0d  mov     rdx, [rsp+990h+pv]
0x1800a3e12  lea     rcx, [rsp+990h+pszPath]
0x1800a3e17  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800a3e1c  test    al, al
0x1800a3e1e  jnz     short loc_1800A3E2B
0x1800a3e20  mov     r9d, 98Dh
0x1800a3e26  jmp     loc_1800A3F26
0x1800a3e2b  mov     rdx, rdi
0x1800a3e2e  lea     rcx, [rsp+990h+pszPath]
0x1800a3e33  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800a3e38  test    al, al
0x1800a3e3a  jnz     short loc_1800A3E47
0x1800a3e3c  mov     r9d, 98Eh
0x1800a3e42  jmp     loc_1800A3F26
0x1800a3e47  lea     rdx, ?gc_szCommsFolderName@@3QBGB; "Comms"
0x1800a3e4e  lea     rcx, [rsp+990h+pszPath]
0x1800a3e53  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800a3e58  test    al, al
0x1800a3e5a  jnz     short loc_1800A3E67
0x1800a3e5c  mov     r9d, 98Fh
0x1800a3e62  jmp     loc_1800A3F26
0x1800a3e67  mov     rdx, rdi
0x1800a3e6a  lea     rcx, [rsp+990h+pszPath]
0x1800a3e6f  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800a3e74  test    al, al
0x1800a3e76  jnz     short loc_1800A3E83
0x1800a3e78  mov     r9d, 990h
0x1800a3e7e  jmp     loc_1800A3F26
0x1800a3e83  lea     rdx, ?gc_szCorruptDataFolderName@@3QBGB; "CorruptVols"
0x1800a3e8a  lea     rcx, [rsp+990h+pszPath]
0x1800a3e8f  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800a3e94  test    al, al
0x1800a3e96  jnz     short loc_1800A3EA3
0x1800a3e98  mov     r9d, 991h
0x1800a3e9e  jmp     loc_1800A3F26
0x1800a3ea3  mov     rdx, rdi
0x1800a3ea6  lea     rcx, [rsp+990h+pszPath]
0x1800a3eab  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800a3eb0  test    al, al
0x1800a3eb2  jnz     short loc_1800A3EBC
0x1800a3eb4  mov     r9d, 992h
0x1800a3eba  jmp     short loc_1800A3F26
0x1800a3ebc  lea     rdx, ?gc_szUserDataBaseName@@3QBGB; "UDM"
0x1800a3ec3  lea     rcx, [rsp+990h+pszPath]
0x1800a3ec8  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800a3ecd  test    al, al
0x1800a3ecf  jnz     short loc_1800A3ED9
0x1800a3ed1  mov     r9d, 993h
0x1800a3ed7  jmp     short loc_1800A3F26
0x1800a3ed9  mov     rdx, rdi
0x1800a3edc  lea     rcx, [rsp+990h+pszPath]
0x1800a3ee1  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800a3ee6  test    al, al
0x1800a3ee8  jnz     short loc_1800A3EF2
0x1800a3eea  mov     r9d, 994h
0x1800a3ef0  jmp     short loc_1800A3F26
0x1800a3ef2  lea     rdx, [rbp+890h+sz]
0x1800a3ef9  lea     rcx, [rsp+990h+pszPath]
0x1800a3efe  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800a3f03  test    al, al
0x1800a3f05  jnz     short loc_1800A3F0F
0x1800a3f07  mov     r9d, 995h
0x1800a3f0d  jmp     short loc_1800A3F26
0x1800a3f0f  mov     rdx, rdi
0x1800a3f12  lea     rcx, [rsp+990h+pszPath]
0x1800a3f17  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800a3f1c  test    al, al
0x1800a3f1e  jnz     short loc_1800A3F34
0x1800a3f20  mov     r9d, 996h
0x1800a3f26  mov     ebx, 8007000Eh
0x1800a3f2b  xor     edx, edx
0x1800a3f2d  mov     ecx, ebx
0x1800a3f2f  jmp     loc_1800A3DA9
0x1800a3f34  mov     rdx, [rsp+990h+pszPath]; pszPath
0x1800a3f39  xor     r8d, r8d; psa
0x1800a3f3c  xor     ecx, ecx; hwnd
0x1800a3f3e  call    cs:__imp_SHCreateDirectoryExW
0x1800a3f44  mov     ebx, eax
0x1800a3f46  test    eax, eax
0x1800a3f48  jz      short loc_1800A3F5D
0x1800a3f4a  jle     short loc_1800A3F55
0x1800a3f4c  movzx   ebx, ax
0x1800a3f4f  or      ebx, 80070000h
0x1800a3f55  mov     r9d, 998h
0x1800a3f5b  jmp     short loc_1800A3F2B
0x1800a3f5d  mov     r8, [rsp+990h+var_938]; unsigned __int16 *
0x1800a3f62  lea     rcx, [rbp+890h+FileName]; unsigned __int16 *
0x1800a3f69  mov     r14d, 104h
0x1800a3f6f  mov     edx, r14d; unsigned __int64
0x1800a3f72  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a3f77  mov     ebx, eax
0x1800a3f79  test    eax, eax
0x1800a3f7b  jns     short loc_1800A3F88
0x1800a3f7d  mov     r9d, 99Ch
0x1800a3f83  jmp     loc_1800A3DA2
0x1800a3f88  lea     r8, pszMore; "*"
0x1800a3f8f  mov     rdx, r14; unsigned __int64
0x1800a3f92  lea     rcx, [rbp+890h+FileName]; unsigned __int16 *
0x1800a3f99  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a3f9e  mov     ebx, eax
0x1800a3fa0  test    eax, eax
0x1800a3fa2  jns     short loc_1800A3FAF
0x1800a3fa4  mov     r9d, 99Dh
0x1800a3faa  jmp     loc_1800A3DA2
0x1800a3faf  xor     edx, edx; Val
0x1800a3fb1  lea     rcx, [rbp+890h+FindFileData]; void *
0x1800a3fb5  mov     r8d, 250h; Size
0x1800a3fbb  call    memset_0
0x1800a3fc0  lea     rdx, [rbp+890h+FindFileData]; lpFindFileData
0x1800a3fc4  lea     rcx, [rbp+890h+FileName]; lpFileName
0x1800a3fcb  call    cs:__imp_FindFirstFileW
0x1800a3fd1  mov     rdi, rax
0x1800a3fd4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a3fd8  jz      loc_1800A4149
0x1800a3fde  mov     eax, 1
0x1800a3fe3  test    eax, eax
0x1800a3fe5  jz      loc_1800A4135
0x1800a3feb  test    byte ptr [rbp+890h+FindFileData.dwFileAttributes], 10h
0x1800a3fef  jnz     loc_1800A40C3
0x1800a3ff5  mov     r8, [rsp+990h+var_938]; unsigned __int16 *
0x1800a3ffa  lea     rcx, [rbp+890h+ExistingFileName]; unsigned __int16 *
0x1800a4001  mov     rdx, r14; unsigned __int64
0x1800a4004  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a4009  mov     ebx, eax
0x1800a400b  test    eax, eax
0x1800a400d  js      loc_1800A410E
0x1800a4013  lea     r8, [rbp+890h+FindFileData.cFileName]; unsigned __int16 *
0x1800a4017  mov     rdx, r14; unsigned __int64
0x1800a401a  lea     rcx, [rbp+890h+ExistingFileName]; unsigned __int16 *
0x1800a4021  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a4026  mov     ebx, eax
0x1800a4028  test    eax, eax
0x1800a402a  js      loc_1800A4106
0x1800a4030  mov     r8, [rsp+990h+pszPath]; unsigned __int16 *
0x1800a4035  lea     rcx, [rbp+890h+NewFileName]; unsigned __int16 *
0x1800a403c  mov     rdx, r14; unsigned __int64
0x1800a403f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a4044  mov     ebx, eax
0x1800a4046  test    eax, eax
0x1800a4048  js      loc_1800A40FE
0x1800a404e  lea     r8, [rbp+890h+FindFileData.cFileName]; unsigned __int16 *
0x1800a4052  mov     rdx, r14; unsigned __int64
0x1800a4055  lea     rcx, [rbp+890h+NewFileName]; unsigned __int16 *
0x1800a405c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a4061  mov     ebx, eax
0x1800a4063  test    eax, eax
0x1800a4065  js      loc_1800A40F6
0x1800a406b  xor     r8d, r8d; dwFlags
0x1800a406e  lea     rdx, [rbp+890h+NewFileName]; lpNewFileName
0x1800a4075  lea     rcx, [rbp+890h+ExistingFileName]; lpExistingFileName
0x1800a407c  call    cs:__imp_MoveFileExW
0x1800a4082  test    eax, eax
0x1800a4084  jnz     short loc_1800A40C3
0x1800a4086  call    cs:__imp_GetLastError
0x1800a408c  test    eax, eax
0x1800a408e  jle     short loc_1800A409A
0x1800a4090  movzx   eax, ax
0x1800a4093  or      eax, 80070000h
0x1800a4098  test    eax, eax
0x1800a409a  jns     short loc_1800A40B2
0x1800a409c  mov     r9d, 9B7h
0x1800a40a2  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800a40a9  xor     edx, edx
0x1800a40ab  mov     ecx, eax
0x1800a40ad  call    Log_HREvent
0x1800a40b2  lea     rcx, [rbp+890h+ExistingFileName]; lpFileName
0x1800a40b9  call    cs:__imp_DeleteFileW
0x1800a40bf  test    eax, eax
0x1800a40c1  jz      short loc_1800A40D5
0x1800a40c3  lea     rdx, [rbp+890h+FindFileData]; lpFindFileData
0x1800a40c7  mov     rcx, rdi; hFindFile
0x1800a40ca  call    cs:__imp_FindNextFileW
0x1800a40d0  jmp     loc_1800A3FE3
0x1800a40d5  call    cs:__imp_GetLastError
0x1800a40db  mov     ebx, eax
0x1800a40dd  test    eax, eax
0x1800a40df  jle     short loc_1800A40EA
0x1800a40e1  movzx   ebx, ax
0x1800a40e4  or      ebx, 80070000h
0x1800a40ea  mov     r9d, 9B9h
0x1800a40f0  xor     edx, edx
0x1800a40f2  mov     ecx, ebx
0x1800a40f4  jmp     short loc_1800A411B
0x1800a40f6  mov     r9d, 9B3h
0x1800a40fc  jmp     short loc_1800A4114
0x1800a40fe  mov     r9d, 9B2h
0x1800a4104  jmp     short loc_1800A4114
0x1800a4106  mov     r9d, 9AFh
0x1800a410c  jmp     short loc_1800A4114
0x1800a410e  mov     r9d, 9AEh
0x1800a4114  mov     edx, 1
0x1800a4119  mov     ecx, eax
0x1800a411b  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800a4122  call    Log_HREvent
0x1800a4127  mov     rcx, rdi; hFindFile
0x1800a412a  call    cs:__imp_FindClose
0x1800a4130  jmp     loc_1800A3DB5
0x1800a4135  call    cs:__imp_GetLastError
0x1800a413b  cmp     eax, 12h
0x1800a413e  jnz     short loc_1800A418D
0x1800a4140  mov     rcx, rdi; hFindFile
0x1800a4143  call    cs:__imp_FindClose
0x1800a4149  mov     rcx, [rsp+990h+pv]; pv
0x1800a414e  test    rcx, rcx
0x1800a4151  jz      short loc_1800A4159
0x1800a4153  call    cs:__imp_CoTaskMemFree
0x1800a4159  lea     rcx, [rsp+990h+pszPath]; void *
0x1800a415e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800a4163  xor     ebx, ebx
  ... truncated ...
```
