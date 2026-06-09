# MoveAllFiles(ushort const *,ushort const *)

- ea: `0x18007f368`
- end: `0x18007f76d`
- name: `?MoveAllFiles@@YAJPEBG0@Z`
- size: `1029`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task`

## callers

- `0x18007dec0`

## callees

- `0x1800068f0`
- `0x180019108`
- `0x18001bd48`
- `0x18001c080`
- `0x18001c1a0`
- `0x18001c2e0`
- `0x18007f368`
- `0x1800c50aa`
- `0x1800c50f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f6bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f740`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f6bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f740`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18007f653`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18007f653`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18007f561`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18007f561`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18007f673`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18007f735`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18007f673`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18007f735`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18007f62c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18007f62c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18007f396`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18007f3c7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18007f396`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18007f3c7`

## string_xrefs

- `0x18007f3ad`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18007f3ff`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18007f47e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18007f50a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18007f6ed`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18007f719`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18007f75b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall MoveAllFiles(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  __int64 v4; // r9
  unsigned int v5; // ebx
  __int64 v7; // r9
  __int64 v8; // r9
  __int64 v9; // r9
  HANDLE FirstFileW; // rdi
  __int64 v11; // r8
  __int64 v12; // r8
  signed int LastError; // eax
  __int64 v14; // r9
  __int64 v15; // r9
  signed int v16; // eax
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h]
  __int64 v19; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h]
  LPCWSTR lpFileName[4]; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpExistingFileName[4]; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpNewFileName[4]; // [rsp+B0h] [rbp-50h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+D0h] [rbp-30h] BYREF

  if ( !PathFileExistsW(a1) )
  {
    v4 = 700;
LABEL_3:
    v5 = -2147024809;
    Log_UnistoreHREvent_0(
      2147942487LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v4);
    return v5;
  }
  if ( !PathFileExistsW(a2) )
  {
    v4 = 701;
    goto LABEL_3;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&v17);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &v17,
                           a1) )
  {
    v7 = 704;
LABEL_9:
    v5 = -2147024882;
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v7);
LABEL_10:
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v17);
    return v5;
  }
  if ( *(_WORD *)(v17 + 2 * ((v18 - v17) >> 1) - 2) != 92
    && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &v17,
                           L"\\",
                           1) )
  {
    v7 = 708;
    goto LABEL_9;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&v19);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &v19,
                           a2) )
  {
    v8 = 712;
LABEL_16:
    v5 = -2147024882;
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v8);
LABEL_17:
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v19);
    goto LABEL_10;
  }
  if ( *(_WORD *)(v19 + 2 * ((v20 - v19) >> 1) - 2) != 92
    && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           &v19,
                           L"\\",
                           1) )
  {
    v8 = 716;
    goto LABEL_16;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpFileName);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           lpFileName,
                           v17,
                           (v18 - v17) >> 1) )
  {
    v9 = 720;
LABEL_23:
    v5 = -2147024882;
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v9);
LABEL_24:
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
    goto LABEL_17;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           lpFileName,
                           L"*",
                           1) )
  {
    v9 = 721;
    goto LABEL_23;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(lpFileName[0], &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpExistingFileName);
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                 lpExistingFileName,
                                 v17,
                                 (v18 - v17) >> 1) )
        {
          v15 = 737;
LABEL_52:
          v5 = -2147024882;
          Log_UnistoreHREvent_0(
            2147942414LL,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
            v15);
          goto LABEL_53;
        }
        v11 = -1;
        do
          ++v11;
        while ( FindFileData.cFileName[v11] );
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 lpExistingFileName,
                                 FindFileData.cFileName,
                                 v11) )
        {
          v15 = 738;
          goto LABEL_52;
        }
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpNewFileName);
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                 lpNewFileName,
                                 v19,
                                 (v20 - v19) >> 1) )
        {
          v14 = 741;
LABEL_48:
          v5 = -2147024882;
LABEL_49:
          Log_UnistoreHREvent_0(
            v5,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
            v14);
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpNewFileName);
LABEL_53:
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpExistingFileName);
          goto LABEL_54;
        }
        v12 = -1;
        do
          ++v12;
        while ( FindFileData.cFileName[v12] );
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 lpNewFileName,
                                 FindFileData.cFileName,
                                 v12) )
        {
          v14 = 742;
          goto LABEL_48;
        }
        if ( !MoveFileExW(lpExistingFileName[0], lpNewFileName[0], 0) )
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
          v14 = 744;
          goto LABEL_49;
        }
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpNewFileName);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpExistingFileName);
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    if ( GetLastError() == 18 )
    {
      FindClose(FirstFileW);
      goto LABEL_42;
    }
    v16 = GetLastError();
    v5 = v16;
    if ( v16 > 0 )
      v5 = (unsigned __int16)v16 | 0x80070000;
    Log_UnistoreHREvent_0(
      v5,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      748);
LABEL_54:
    FindClose(FirstFileW);
    goto LABEL_24;
  }
LABEL_42:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v19);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v17);
  return 0;
}

```

## disassembly

```asm
0x18007f368  mov     [rsp-8+arg_10], rbx
0x18007f36d  push    rbp
0x18007f36e  push    rsi
0x18007f36f  push    rdi
0x18007f370  lea     rbp, [rsp-230h]
0x18007f378  sub     rsp, 330h
0x18007f37f  mov     rax, cs:__security_cookie
0x18007f386  xor     rax, rsp
0x18007f389  mov     [rbp+240h+var_20], rax
0x18007f390  mov     rdi, rdx
0x18007f393  mov     rbx, rcx
0x18007f396  call    cs:__imp_PathFileExistsW
0x18007f39c  xor     esi, esi
0x18007f39e  test    eax, eax
0x18007f3a0  jnz     short loc_18007F3C4
0x18007f3a2  mov     r9d, 2BCh
0x18007f3a8  mov     ebx, 80070057h
0x18007f3ad  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007f3b4  mov     ecx, ebx
0x18007f3b6  xor     edx, edx
0x18007f3b8  call    Log_UnistoreHREvent_0
0x18007f3bd  mov     eax, ebx
0x18007f3bf  jmp     loc_18007F699
0x18007f3c4  mov     rcx, rdi; pszPath
0x18007f3c7  call    cs:__imp_PathFileExistsW
0x18007f3cd  test    eax, eax
0x18007f3cf  jnz     short loc_18007F3D9
0x18007f3d1  mov     r9d, 2BDh
0x18007f3d7  jmp     short loc_18007F3A8
0x18007f3d9  lea     rcx, [rsp+340h+var_310]
0x18007f3de  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18007f3e3  mov     rdx, rbx
0x18007f3e6  lea     rcx, [rsp+340h+var_310]
0x18007f3eb  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18007f3f0  test    al, al
0x18007f3f2  jnz     short loc_18007F41B
0x18007f3f4  mov     r9d, 2C0h
0x18007f3fa  mov     ebx, 8007000Eh
0x18007f3ff  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007f406  mov     ecx, ebx
0x18007f408  xor     edx, edx
0x18007f40a  call    Log_UnistoreHREvent_0
0x18007f40f  lea     rcx, [rsp+340h+var_310]
0x18007f414  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007f419  jmp     short loc_18007F3BD
0x18007f41b  mov     rax, [rsp+340h+var_310]
0x18007f420  mov     ebx, 1
0x18007f425  mov     rcx, [rsp+340h+var_308]
0x18007f42a  sub     rcx, rax
0x18007f42d  sar     rcx, 1
0x18007f430  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18007f436  jz      short loc_18007F458
0x18007f438  mov     r8d, ebx
0x18007f43b  lea     rdx, asc_1800DB900; "\\"
0x18007f442  lea     rcx, [rsp+340h+var_310]
0x18007f447  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18007f44c  test    al, al
0x18007f44e  jnz     short loc_18007F458
0x18007f450  mov     r9d, 2C4h
0x18007f456  jmp     short loc_18007F3FA
0x18007f458  lea     rcx, [rsp+340h+var_2F0]
0x18007f45d  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18007f462  mov     rdx, rdi
0x18007f465  lea     rcx, [rsp+340h+var_2F0]
0x18007f46a  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18007f46f  test    al, al
0x18007f471  jnz     short loc_18007F49D
0x18007f473  mov     r9d, 2C8h
0x18007f479  mov     ebx, 8007000Eh
0x18007f47e  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007f485  mov     ecx, ebx
0x18007f487  xor     edx, edx
0x18007f489  call    Log_UnistoreHREvent_0
0x18007f48e  lea     rcx, [rsp+340h+var_2F0]
0x18007f493  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007f498  jmp     loc_18007F40F
0x18007f49d  mov     rax, [rsp+340h+var_2F0]
0x18007f4a2  mov     rcx, [rsp+340h+var_2E8]
0x18007f4a7  sub     rcx, rax
0x18007f4aa  sar     rcx, 1
0x18007f4ad  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18007f4b3  jz      short loc_18007F4D5
0x18007f4b5  mov     r8, rbx
0x18007f4b8  lea     rdx, asc_1800DB900; "\\"
0x18007f4bf  lea     rcx, [rsp+340h+var_2F0]
0x18007f4c4  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18007f4c9  test    al, al
0x18007f4cb  jnz     short loc_18007F4D5
0x18007f4cd  mov     r9d, 2CCh
0x18007f4d3  jmp     short loc_18007F479
0x18007f4d5  lea     rcx, [rsp+340h+lpFileName]
0x18007f4da  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18007f4df  mov     rdx, [rsp+340h+var_310]
0x18007f4e4  lea     rcx, [rsp+340h+lpFileName]
0x18007f4e9  mov     r8, [rsp+340h+var_308]
0x18007f4ee  sub     r8, rdx
0x18007f4f1  sar     r8, 1
0x18007f4f4  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18007f4f9  test    al, al
0x18007f4fb  jnz     short loc_18007F527
0x18007f4fd  mov     r9d, 2D0h
0x18007f503  xor     edx, edx
0x18007f505  mov     ebx, 8007000Eh
0x18007f50a  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007f511  mov     ecx, ebx
0x18007f513  call    Log_UnistoreHREvent_0
0x18007f518  lea     rcx, [rsp+340h+lpFileName]
0x18007f51d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007f522  jmp     loc_18007F48E
0x18007f527  mov     r8, rbx
0x18007f52a  lea     rdx, pszMore; "*"
0x18007f531  lea     rcx, [rsp+340h+lpFileName]
0x18007f536  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18007f53b  xor     edx, edx; Val
0x18007f53d  test    al, al
0x18007f53f  jnz     short loc_18007F549
0x18007f541  mov     r9d, 2D1h
0x18007f547  jmp     short loc_18007F505
0x18007f549  mov     r8d, 250h; Size
0x18007f54f  lea     rcx, [rbp+240h+FindFileData]; void *
0x18007f553  call    memset_0
0x18007f558  mov     rcx, [rsp+340h+lpFileName]; lpFileName
0x18007f55d  lea     rdx, [rbp+240h+FindFileData]; lpFindFileData
0x18007f561  call    cs:__imp_FindFirstFileW
0x18007f567  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007f56b  mov     rdi, rax
0x18007f56e  cmp     rax, rbx
0x18007f571  jz      loc_18007F679
0x18007f577  test    byte ptr [rbp+240h+FindFileData.dwFileAttributes], 10h
0x18007f57b  jnz     loc_18007F64C
0x18007f581  lea     rcx, [rbp+240h+lpExistingFileName]
0x18007f585  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18007f58a  mov     rdx, [rsp+340h+var_310]
0x18007f58f  lea     rcx, [rbp+240h+lpExistingFileName]
0x18007f593  mov     r8, [rsp+340h+var_308]
0x18007f598  sub     r8, rdx
0x18007f59b  sar     r8, 1
0x18007f59e  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18007f5a3  test    al, al
0x18007f5a5  jz      loc_18007F70E
0x18007f5ab  lea     rax, [rbp+240h+FindFileData.cFileName]
0x18007f5af  mov     r8, rbx
0x18007f5b2  inc     r8
0x18007f5b5  cmp     [rax+r8*2], si
0x18007f5ba  jnz     short loc_18007F5B2
0x18007f5bc  lea     rdx, [rbp+240h+FindFileData.cFileName]
0x18007f5c0  lea     rcx, [rbp+240h+lpExistingFileName]
0x18007f5c4  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18007f5c9  test    al, al
0x18007f5cb  jz      loc_18007F706
0x18007f5d1  lea     rcx, [rbp+240h+lpNewFileName]
0x18007f5d5  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18007f5da  mov     rdx, [rsp+340h+var_2F0]
0x18007f5df  lea     rcx, [rbp+240h+lpNewFileName]
0x18007f5e3  mov     r8, [rsp+340h+var_2E8]
0x18007f5e8  sub     r8, rdx
0x18007f5eb  sar     r8, 1
0x18007f5ee  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18007f5f3  test    al, al
0x18007f5f5  jz      loc_18007F6E0
0x18007f5fb  lea     rax, [rbp+240h+FindFileData.cFileName]
0x18007f5ff  mov     r8, rbx
0x18007f602  inc     r8
0x18007f605  cmp     [rax+r8*2], si
0x18007f60a  jnz     short loc_18007F602
0x18007f60c  lea     rdx, [rbp+240h+FindFileData.cFileName]
0x18007f610  lea     rcx, [rbp+240h+lpNewFileName]
0x18007f614  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18007f619  test    al, al
0x18007f61b  jz      loc_18007F6D8
0x18007f621  mov     rdx, [rbp+240h+lpNewFileName]; lpNewFileName
0x18007f625  xor     r8d, r8d; dwFlags
0x18007f628  mov     rcx, [rbp+240h+lpExistingFileName]; lpExistingFileName
0x18007f62c  call    cs:__imp_MoveFileExW
0x18007f632  test    eax, eax
0x18007f634  jz      loc_18007F6BB
0x18007f63a  lea     rcx, [rbp+240h+lpNewFileName]
0x18007f63e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007f643  lea     rcx, [rbp+240h+lpExistingFileName]
0x18007f647  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007f64c  lea     rdx, [rbp+240h+FindFileData]; lpFindFileData
0x18007f650  mov     rcx, rdi; hFindFile
0x18007f653  call    cs:__imp_FindNextFileW
0x18007f659  test    eax, eax
0x18007f65b  jnz     loc_18007F577
0x18007f661  call    cs:__imp_GetLastError
0x18007f667  cmp     eax, 12h
0x18007f66a  jnz     loc_18007F740
0x18007f670  mov     rcx, rdi; hFindFile
0x18007f673  call    cs:__imp_FindClose
0x18007f679  lea     rcx, [rsp+340h+lpFileName]
0x18007f67e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007f683  lea     rcx, [rsp+340h+var_2F0]
0x18007f688  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007f68d  lea     rcx, [rsp+340h+var_310]
0x18007f692  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007f697  xor     eax, eax
0x18007f699  mov     rcx, [rbp+240h+var_20]
0x18007f6a0  xor     rcx, rsp; StackCookie
0x18007f6a3  call    __security_check_cookie
0x18007f6a8  mov     rbx, [rsp+340h+arg_10]
0x18007f6b0  add     rsp, 330h
0x18007f6b7  pop     rdi
0x18007f6b8  pop     rsi
0x18007f6b9  pop     rbp
0x18007f6ba  retn
0x18007f6bb  call    cs:__imp_GetLastError
0x18007f6c1  mov     ebx, eax
0x18007f6c3  test    eax, eax
0x18007f6c5  jle     short loc_18007F6D0
0x18007f6c7  movzx   ebx, ax
0x18007f6ca  or      ebx, 80070000h
0x18007f6d0  mov     r9d, 2E8h
0x18007f6d6  jmp     short loc_18007F6EB
0x18007f6d8  mov     r9d, 2E6h
0x18007f6de  jmp     short loc_18007F6E6
0x18007f6e0  mov     r9d, 2E5h
0x18007f6e6  mov     ebx, 8007000Eh
0x18007f6eb  xor     edx, edx
0x18007f6ed  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007f6f4  mov     ecx, ebx
0x18007f6f6  call    Log_UnistoreHREvent_0
0x18007f6fb  lea     rcx, [rbp+240h+lpNewFileName]
0x18007f6ff  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007f704  jmp     short loc_18007F729
0x18007f706  mov     r9d, 2E2h
0x18007f70c  jmp     short loc_18007F714
0x18007f70e  mov     r9d, 2E1h
0x18007f714  mov     ebx, 8007000Eh
0x18007f719  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007f720  mov     ecx, ebx
0x18007f722  xor     edx, edx
0x18007f724  call    Log_UnistoreHREvent_0
0x18007f729  lea     rcx, [rbp+240h+lpExistingFileName]
0x18007f72d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007f732  mov     rcx, rdi; hFindFile
0x18007f735  call    cs:__imp_FindClose
0x18007f73b  jmp     loc_18007F518
0x18007f740  call    cs:__imp_GetLastError
0x18007f746  mov     ebx, eax
0x18007f748  test    eax, eax
0x18007f74a  jle     short loc_18007F755
0x18007f74c  movzx   ebx, ax
0x18007f74f  or      ebx, 80070000h
0x18007f755  mov     r9d, 2ECh
0x18007f75b  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007f762  xor     edx, edx
0x18007f764  mov     ecx, ebx
0x18007f766  call    Log_UnistoreHREvent_0
0x18007f76b  jmp     short loc_18007F732
```
