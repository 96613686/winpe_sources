# BootstrapSystemDataDirectories(bool)

- ea: `0x100439330`
- end: `0x100439804`
- name: `?BootstrapSystemDataDirectories@@YAJ_N@Z`
- size: `1236`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x100416770`

## callees

- `0x100401580`
- `0x100402ec0`
- `0x100438200`
- `0x100438ed0`
- `0x100439260`
- `0x100439330`
- `0x1004403d0`
- `0x100452b78`
- `0x100452be0`
- `0x1004534f8`

## import_xrefs

- `KERNEL32!FindFirstFileW` at `0x1004394a7`
- `KERNEL32!FindFirstFileW` at `0x10043961e`
- `KERNEL32!FindFirstFileW` at `0x1004394a7`
- `KERNEL32!FindFirstFileW` at `0x10043961e`
- `KERNEL32!CreateDirectoryW` at `0x10043956d`
- `KERNEL32!CreateDirectoryW` at `0x10043956d`
- `KERNEL32!CopyFileW` at `0x1004396dc`
- `KERNEL32!CopyFileW` at `0x1004396dc`
- `KERNEL32!GetLastError` at `0x100439577`
- `KERNEL32!GetLastError` at `0x100439663`
- `KERNEL32!GetLastError` at `0x100439787`
- `KERNEL32!GetLastError` at `0x100439577`
- `KERNEL32!GetLastError` at `0x100439663`
- `KERNEL32!GetLastError` at `0x100439787`
- `KERNEL32!FindClose` at `0x1004394d7`
- `KERNEL32!FindClose` at `0x10043964d`
- `KERNEL32!FindClose` at `0x10043965b`
- `KERNEL32!FindClose` at `0x1004394d7`
- `KERNEL32!FindClose` at `0x10043964d`
- `KERNEL32!FindClose` at `0x10043965b`
- `sqlmin!GetMasterLogPath` at `0x100439535`
- `sqlmin!GetMasterLogPath` at `0x100439535`
- `sqlmin!GetMasterDataPath` at `0x100439499`
- `sqlmin!GetMasterDataPath` at `0x10043953d`
- `sqlmin!GetMasterDataPath` at `0x100439499`
- `sqlmin!GetMasterDataPath` at `0x10043953d`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043979e`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1004397e2`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x10043979e`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x1004397e2`
- `svl!SvlPathGetDirectory` at `0x100439553`
- `svl!SvlPathGetDirectory` at `0x100439553`
- `svl!SvlPathGetParent` at `0x1004395b6`
- `svl!SvlPathGetParent` at `0x1004395b6`
- `svl!SvlPathReplaceFileName` at `0x100439522`
- `svl!SvlPathReplaceFileName` at `0x100439602`
- `svl!SvlPathReplaceFileName` at `0x100439522`
- `svl!SvlPathReplaceFileName` at `0x100439602`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BootstrapSystemDataDirectories(unsigned __int8 a1)
{
  int v1; // r13d
  unsigned int v2; // r12d
  const WCHAR *MasterDataPath; // rax
  HANDLE v4; // rbx
  __int64 result; // rax
  unsigned int v6; // r15d
  __int64 *v7; // rsi
  char v8; // r14
  __int64 v9; // rax
  int Parent; // ebx
  signed int LastError; // eax
  signed int v12; // ebx
  HANDLE FirstFileW; // rax
  void *v14; // rdi
  signed int v15; // eax
  const wchar_t *v16; // rdx
  signed int v17; // ebx
  wchar_t *v18; // rax
  wchar_t *OSErrString; // rax
  _BYTE v20[8]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+28h] [rbp-D8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v23[4096]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v24[4096]; // [rsp+1280h] [rbp+1180h] BYREF
  WCHAR PathName[264]; // [rsp+2280h] [rbp+2180h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+2490h] [rbp+2390h] BYREF
  _BYTE v27[528]; // [rsp+26A0h] [rbp+25A0h] BYREF

  v21 = -2;
  v1 = a1;
  v2 = 0;
  memset_0(ExistingFileName, 0, 0x20Au);
  memset_0(PathName, 0, 0x20Au);
  if ( dword_1004D48C0 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&dword_1004D48C0);
    if ( dword_1004D48C0 == -1 )
    {
      qword_1004D4810 = (__int64)L"master.mdf";
      qword_1004D4818 = (__int64)L"mastlog.ldf";
      qword_1004D4820 = (__int64)L"model.mdf";
      qword_1004D4828 = (__int64)L"modellog.ldf";
      qword_1004D4830 = (__int64)L"msdbdata.mdf";
      qword_1004D4838 = (__int64)L"msdblog.ldf";
      qword_1004D4840 = (__int64)L"model_replicatedmaster.mdf";
      qword_1004D4848 = (__int64)L"model_replicatedmaster.ldf";
      qword_1004D4850 = (__int64)L"model_msdbdata.mdf";
      qword_1004D4858 = (__int64)L"model_msdblog.ldf";
      Init_thread_footer(&dword_1004D48C0);
    }
  }
  if ( (*((_DWORD *)qword_10049F360 + 12127) & 0x200) != 0
    || (_BYTE)v1
    || (MasterDataPath = (const WCHAR *)GetMasterDataPath(),
        v4 = FindFirstFileW(MasterDataPath, &FindFileData),
        v4 == (HANDLE)-1LL) )
  {
    result = GetBootstrapDataSourcePath(ExistingFileName, 261);
    if ( (int)result < 0 )
    {
LABEL_47:
      _mm_lfence();
      return result;
    }
    v6 = 0;
    v7 = &qword_1004D4810;
    while ( 1 )
    {
      v8 = 0;
      result = SvlPathReplaceFileName(ExistingFileName, 261, *v7);
      if ( (int)result < 0 )
        goto LABEL_47;
      v9 = (wchar_t *)*v7 == L"mastlog.ldf" ? GetMasterLogPath() : GetMasterDataPath();
      result = SvlPathGetDirectory(v9, PathName, 261);
      if ( (int)result < 0 )
        goto LABEL_47;
      Parent = 0;
      if ( !CreateDirectoryW(PathName, 0) )
      {
        LastError = GetLastError();
        Parent = LastError;
        if ( LastError == 3 )
        {
          v20[0] = 0;
          memset_0(v27, 0, 0x20Au);
          Parent = SvlPathGetParent(PathName, v27, 261, v20);
          if ( Parent >= 0 )
            Parent = CreateDirectoryIfNeeded(v27);
        }
        else if ( LastError == 183 )
        {
          Parent = 0;
        }
        else if ( LastError > 0 )
        {
          Parent = (unsigned __int16)LastError | 0x80070000;
        }
      }
      if ( Parent < 0 )
      {
        _mm_lfence();
        OSErrString = GetOSErrString(Parent, (struct ErrorStringHolder *)v24, 0, 0);
        scierrlog(0xC32Cu, PathName, OSErrString);
        return (unsigned int)Parent;
      }
      result = SvlPathReplaceFileName(PathName, 261, *v7);
      v12 = result;
      if ( (int)result < 0 )
        goto LABEL_47;
      FirstFileW = FindFirstFileW(PathName, &FindFileData);
      v14 = FirstFileW;
      if ( FirstFileW != (HANDLE)-1LL )
        break;
      v15 = GetLastError();
      if ( v15 != 2 )
      {
        if ( v15 > 0 )
          v12 = (unsigned __int16)v15 | 0x80070000;
        else
          v12 = v15;
LABEL_35:
        if ( v12 < 0 )
          goto LABEL_46;
        if ( v8 && !(_BYTE)v1 )
          goto LABEL_45;
      }
      CheckEULA();
      v16 = &dword_10045ADE4;
      if ( (_BYTE)v1 )
        v16 = L"FORCE ";
      scierrlog(0xC329u, v16, ExistingFileName, PathName);
      if ( !CopyFileW(ExistingFileName, PathName, v1 != 1) )
      {
        v17 = GetLastError();
        v18 = GetOSErrString(v17, (struct ErrorStringHolder *)v23, 0, 0);
        scierrlog(0xC32Au, ExistingFileName, PathName, v18);
        if ( v17 > 0 )
          return (unsigned __int16)v17 | 0x80070000;
        return (unsigned int)v17;
      }
      if ( (wchar_t *)*v7 == L"master.mdf" )
      {
        *((_DWORD *)qword_10049F360 + 3632) = 1;
        if ( (*((_DWORD *)qword_10049F360 + 12127) & 0x200) == 0 )
          scierrlog(0xC328u, PathName);
      }
      *((_DWORD *)qword_10049F360 + 12127) |= 8u;
LABEL_45:
      ++v6;
      ++v7;
      if ( v6 >= 0xA )
      {
LABEL_46:
        result = (unsigned int)v12;
        goto LABEL_47;
      }
    }
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      scierrlog(0xC32Bu, PathName);
      v12 = -2147024629;
      FindClose(v14);
    }
    else
    {
      v8 = 1;
      FindClose(FirstFileW);
    }
    goto LABEL_35;
  }
  if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
  {
    scierrlog(0xC32Bu, PathName);
    v2 = -2147024629;
  }
  FindClose(v4);
  return v2;
}

```

## disassembly

```asm
0x100439330  push    rbp
0x100439332  push    r12
0x100439334  push    r13
0x100439336  push    r14
0x100439338  push    r15
0x10043933a  lea     rbp, [rsp-27C0h]
0x100439342  mov     eax, 28C0h
0x100439347  call    _alloca_probe
0x10043934c  sub     rsp, rax
0x10043934f  mov     [rsp+28E0h+var_28B8], 0FFFFFFFFFFFFFFFEh
0x100439358  mov     [rsp+28E0h+arg_8], rbx
0x100439360  mov     [rsp+28E0h+arg_10], rsi
0x100439368  mov     [rsp+28E0h+arg_18], rdi
0x100439370  mov     rax, cs:__security_cookie
0x100439377  xor     rax, rsp
0x10043937a  mov     [rbp+27E0h+var_30], rax
0x100439381  movzx   r13d, cl
0x100439385  xor     r12d, r12d
0x100439388  xor     edx, edx; Val
0x10043938a  mov     r8d, 20Ah; Size
0x100439390  lea     rcx, [rbp+27E0h+ExistingFileName]; void *
0x100439397  call    memset_0
0x10043939c  xor     edx, edx; Val
0x10043939e  mov     r8d, 20Ah; Size
0x1004393a4  lea     rcx, [rbp+27E0h+PathName]; void *
0x1004393ab  call    memset_0
0x1004393b0  mov     rax, gs:58h
0x1004393b9  mov     edx, 4
0x1004393be  mov     rcx, [rax]
0x1004393c1  lea     rdi, aMasterMdf; "master.mdf"
0x1004393c8  lea     rbx, aMastlogLdf; "mastlog.ldf"
0x1004393cf  mov     eax, [rdx+rcx]
0x1004393d2  cmp     cs:dword_1004D48C0, eax
0x1004393d8  jle     loc_100439481
0x1004393de  lea     rcx, dword_1004D48C0
0x1004393e5  call    _Init_thread_header
0x1004393ea  cmp     cs:dword_1004D48C0, 0FFFFFFFFh
0x1004393f1  jnz     loc_100439481
0x1004393f7  mov     cs:qword_1004D4810, rdi
0x1004393fe  mov     cs:qword_1004D4818, rbx
0x100439405  lea     rax, aModelMdf; "model.mdf"
0x10043940c  mov     cs:qword_1004D4820, rax
0x100439413  lea     rax, aModellogLdf; "modellog.ldf"
0x10043941a  mov     cs:qword_1004D4828, rax
0x100439421  lea     rax, aMsdbdataMdf; "msdbdata.mdf"
0x100439428  mov     cs:qword_1004D4830, rax
0x10043942f  lea     rax, aMsdblogLdf; "msdblog.ldf"
0x100439436  mov     cs:qword_1004D4838, rax
0x10043943d  lea     rax, aModelReplicate_0; "model_replicatedmaster.mdf"
0x100439444  mov     cs:qword_1004D4840, rax
0x10043944b  lea     rax, aModelReplicate; "model_replicatedmaster.ldf"
0x100439452  mov     cs:qword_1004D4848, rax
0x100439459  lea     rax, aModelMsdbdataM; "model_msdbdata.mdf"
0x100439460  mov     cs:qword_1004D4850, rax
0x100439467  lea     rax, aModelMsdblogLd; "model_msdblog.ldf"
0x10043946e  mov     cs:qword_1004D4858, rax
0x100439475  lea     rcx, dword_1004D48C0
0x10043947c  call    _Init_thread_footer
0x100439481  mov     rax, cs:qword_10049F360
0x100439488  test    dword ptr [rax+0BD7Ch], 200h
0x100439492  jnz     short loc_1004394EC
0x100439494  test    r13b, r13b
0x100439497  jnz     short loc_1004394EC
0x100439499  call    cs:__imp_GetMasterDataPath
0x10043949f  mov     rcx, rax; lpFileName
0x1004394a2  lea     rdx, [rsp+28E0h+FindFileData]; lpFindFileData
0x1004394a7  call    cs:__imp_FindFirstFileW
0x1004394ad  mov     rbx, rax
0x1004394b0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1004394b4  jz      short loc_1004394E5
0x1004394b6  test    byte ptr [rsp+28E0h+FindFileData.dwFileAttributes], 10h
0x1004394bb  jz      short loc_1004394D4
0x1004394bd  lea     rdx, [rbp+27E0h+PathName]
0x1004394c4  mov     ecx, 0C32Bh; unsigned int
0x1004394c9  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x1004394ce  mov     r12d, 8007010Bh
0x1004394d4  mov     rcx, rbx; hFindFile
0x1004394d7  call    cs:__imp_FindClose
0x1004394dd  mov     eax, r12d
0x1004394e0  jmp     loc_100439757
0x1004394e5  lea     rbx, aMastlogLdf; "mastlog.ldf"
0x1004394ec  mov     edx, 105h
0x1004394f1  lea     rcx, [rbp+27E0h+ExistingFileName]
0x1004394f8  call    GetBootstrapDataSourcePath
0x1004394fd  test    eax, eax
0x1004394ff  js      loc_100439754
0x100439505  mov     r15d, r12d
0x100439508  lea     rsi, qword_1004D4810
0x10043950f  nop
0x100439510  xor     r14b, r14b
0x100439513  mov     r8, [rsi]
0x100439516  mov     edx, 105h
0x10043951b  lea     rcx, [rbp+27E0h+ExistingFileName]
0x100439522  call    cs:__imp_SvlPathReplaceFileName
0x100439528  test    eax, eax
0x10043952a  js      loc_100439754
0x100439530  cmp     [rsi], rbx
0x100439533  jnz     short loc_10043953D
0x100439535  call    cs:__imp_GetMasterLogPath
0x10043953b  jmp     short loc_100439543
0x10043953d  call    cs:__imp_GetMasterDataPath
0x100439543  mov     r8d, 105h
0x100439549  lea     rdx, [rbp+27E0h+PathName]
0x100439550  mov     rcx, rax
0x100439553  call    cs:__imp_SvlPathGetDirectory
0x100439559  test    eax, eax
0x10043955b  js      loc_100439754
0x100439561  mov     ebx, r12d
0x100439564  xor     edx, edx; lpSecurityAttributes
0x100439566  lea     rcx, [rbp+27E0h+PathName]; lpPathName
0x10043956d  call    cs:__imp_CreateDirectoryW
0x100439573  test    eax, eax
0x100439575  jnz     short loc_1004395EB
0x100439577  call    cs:__imp_GetLastError
0x10043957d  mov     ebx, eax
0x10043957f  cmp     eax, 3
0x100439582  jnz     short loc_1004395D2
0x100439584  mov     [rsp+28E0h+var_28C0], r14b
0x100439589  xor     edx, edx; Val
0x10043958b  mov     r8d, 20Ah; Size
0x100439591  lea     rcx, [rbp+27E0h+var_240]; void *
0x100439598  call    memset_0
0x10043959d  lea     r9, [rsp+28E0h+var_28C0]
0x1004395a2  mov     r8d, 105h
0x1004395a8  lea     rdx, [rbp+27E0h+var_240]
0x1004395af  lea     rcx, [rbp+27E0h+PathName]
0x1004395b6  call    cs:__imp_SvlPathGetParent
0x1004395bc  mov     ebx, eax
0x1004395be  test    eax, eax
0x1004395c0  js      short loc_1004395EB
0x1004395c2  lea     rcx, [rbp+27E0h+var_240]
0x1004395c9  call    CreateDirectoryIfNeeded
0x1004395ce  mov     ebx, eax
0x1004395d0  jmp     short loc_1004395EB
0x1004395d2  cmp     eax, 0B7h
0x1004395d7  jnz     short loc_1004395DE
0x1004395d9  mov     ebx, r12d
0x1004395dc  jmp     short loc_1004395EB
0x1004395de  test    eax, eax
0x1004395e0  jle     short loc_1004395EB
0x1004395e2  movzx   ebx, ax
0x1004395e5  or      ebx, 80070000h
0x1004395eb  test    ebx, ebx
0x1004395ed  js      loc_1004397D0
0x1004395f3  mov     r8, [rsi]
0x1004395f6  mov     edx, 105h
0x1004395fb  lea     rcx, [rbp+27E0h+PathName]
0x100439602  call    cs:__imp_SvlPathReplaceFileName
0x100439608  mov     ebx, eax
0x10043960a  test    eax, eax
0x10043960c  js      loc_100439754
0x100439612  lea     rdx, [rsp+28E0h+FindFileData]; lpFindFileData
0x100439617  lea     rcx, [rbp+27E0h+PathName]; lpFileName
0x10043961e  call    cs:__imp_FindFirstFileW
0x100439624  mov     rdi, rax
0x100439627  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x10043962b  jz      short loc_100439663
0x10043962d  test    byte ptr [rsp+28E0h+FindFileData.dwFileAttributes], 10h
0x100439632  jz      short loc_100439655
0x100439634  lea     rdx, [rbp+27E0h+PathName]
0x10043963b  mov     ecx, 0C32Bh; unsigned int
0x100439640  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100439645  mov     ebx, 8007010Bh
0x10043964a  mov     rcx, rdi; hFindFile
0x10043964d  call    cs:__imp_FindClose
0x100439653  jmp     short loc_10043967F
0x100439655  mov     r14b, 1
0x100439658  mov     rcx, rdi; hFindFile
0x10043965b  call    cs:__imp_FindClose
0x100439661  jmp     short loc_10043967F
0x100439663  call    cs:__imp_GetLastError
0x100439669  cmp     eax, 2
0x10043966c  jz      short loc_100439695
0x10043966e  test    eax, eax
0x100439670  jg      short loc_100439676
0x100439672  mov     ebx, eax
0x100439674  jmp     short loc_10043967F
0x100439676  movzx   ebx, ax
0x100439679  or      ebx, 80070000h
0x10043967f  test    ebx, ebx
0x100439681  js      loc_100439752
0x100439687  test    r14b, r14b
0x10043968a  jz      short loc_100439695
0x10043968c  test    r13b, r13b
0x10043968f  jz      loc_100439739
0x100439695  call    ?CheckEULA@@YAXXZ; CheckEULA(void)
0x10043969a  lea     rdx, dword_10045ADE4
0x1004396a1  test    r13b, r13b
0x1004396a4  lea     rax, aForce; "FORCE "
0x1004396ab  cmovnz  rdx, rax
0x1004396af  lea     r9, [rbp+27E0h+PathName]
0x1004396b6  lea     r8, [rbp+27E0h+ExistingFileName]
0x1004396bd  mov     ecx, 0C329h; unsigned int
0x1004396c2  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x1004396c7  mov     r8d, r13d
0x1004396ca  xor     r8d, 1; bFailIfExists
0x1004396ce  lea     rdx, [rbp+27E0h+PathName]; lpNewFileName
0x1004396d5  lea     rcx, [rbp+27E0h+ExistingFileName]; lpExistingFileName
0x1004396dc  call    cs:__imp_CopyFileW
0x1004396e2  test    eax, eax
0x1004396e4  jz      loc_100439787
0x1004396ea  lea     rdi, aMasterMdf; "master.mdf"
0x1004396f1  cmp     [rsi], rdi
0x1004396f4  jnz     short loc_10043972B
0x1004396f6  mov     rax, cs:qword_10049F360
0x1004396fd  mov     dword ptr [rax+38C0h], 1
0x100439707  mov     rax, cs:qword_10049F360
0x10043970e  test    dword ptr [rax+0BD7Ch], 200h
0x100439718  jnz     short loc_10043972B
0x10043971a  lea     rdx, [rbp+27E0h+PathName]
0x100439721  mov     ecx, 0C328h; unsigned int
0x100439726  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10043972b  mov     rax, cs:qword_10049F360
0x100439732  or      dword ptr [rax+0BD7Ch], 8
0x100439739  inc     r15d
0x10043973c  add     rsi, 8
0x100439740  cmp     r15d, 0Ah
0x100439744  jnb     short loc_100439752
0x100439746  lea     rbx, aMastlogLdf; "mastlog.ldf"
0x10043974d  jmp     loc_100439510
0x100439752  mov     eax, ebx
0x100439754  lfence
0x100439757  mov     rcx, [rbp+27E0h+var_30]
0x10043975e  xor     rcx, rsp; StackCookie
0x100439761  call    __security_check_cookie
0x100439766  lea     r11, [rsp+28E0h+var_20]
0x10043976e  mov     rbx, [r11+38h]
0x100439772  mov     rsi, [r11+40h]
0x100439776  mov     rdi, [r11+48h]
0x10043977a  mov     rsp, r11
0x10043977d  pop     r15
0x10043977f  pop     r14
0x100439781  pop     r13
0x100439783  pop     r12
0x100439785  pop     rbp
0x100439786  retn
0x100439787  call    cs:__imp_GetLastError
0x10043978d  mov     ebx, eax
0x10043978f  xor     r9d, r9d
0x100439792  xor     r8d, r8d
0x100439795  lea     rdx, [rbp+27E0h+var_2660]
0x10043979c  mov     ecx, eax
0x10043979e  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x1004397a4  mov     r9, rax
0x1004397a7  lea     r8, [rbp+27E0h+PathName]
0x1004397ae  lea     rdx, [rbp+27E0h+ExistingFileName]
0x1004397b5  mov     ecx, 0C32Ah; unsigned int
0x1004397ba  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x1004397bf  test    ebx, ebx
0x1004397c1  jle     short loc_1004397CC
0x1004397c3  movzx   ebx, bx
0x1004397c6  or      ebx, 80070000h
0x1004397cc  mov     eax, ebx
0x1004397ce  jmp     short loc_100439757
0x1004397d0  lfence
0x1004397d3  xor     r9d, r9d
0x1004397d6  xor     r8d, r8d
0x1004397d9  lea     rdx, [rbp+27E0h+var_1660]
0x1004397e0  mov     ecx, ebx
0x1004397e2  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x1004397e8  mov     r8, rax
0x1004397eb  lea     rdx, [rbp+27E0h+PathName]
0x1004397f2  mov     ecx, 0C32Ch; unsigned int
0x1004397f7  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x1004397fc  mov     eax, ebx
0x1004397fe  jmp     loc_100439757
```
