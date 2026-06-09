# _RecursiveDeleteOldFiles(ushort const *,unsigned __int64)

- ea: `0x180034760`
- end: `0x180034b6c`
- name: `?_RecursiveDeleteOldFiles@@YAJPEBG_K@Z`
- size: `1036`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x180034760`
- `0x1800acc34`

## callees

- `0x180008f0c`
- `0x180018c20`
- `0x18001b340`
- `0x180033f70`
- `0x180034760`
- `0x180035040`
- `0x180035670`
- `0x180035c40`
- `0x180075f98`
- `0x1800977ac`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800349cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034a62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034aab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034adb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800349cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034a62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034aab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034adb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180034997`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180034997`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180034a57`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180034a70`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180034a57`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180034a70`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800349c2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800349c2`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003489a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003489a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800349ff`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800349ff`

## string_xrefs

- `0x1800347b7`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180034849`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x1800349e8`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180034a3a`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180034ac6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180034b01`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`
- `0x180034b1f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`

## pseudocode

```c
__int64 __fastcall _RecursiveDeleteOldFiles(const unsigned __int16 *a1)
{
  __int64 v2; // r9
  DWORD LastError; // ebx
  void *v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // r9
  HANDLE FirstFileW; // rsi
  BOOL NextFileW; // edi
  int v10; // edx
  int v11; // edx
  signed int v12; // eax
  __int64 v13; // r9
  bool v14; // sf
  __int64 v15; // r9
  signed int v16; // eax
  __int64 v17; // rcx
  FILETIME FileTime1; // [rsp+30h] [rbp-D0h] BYREF
  void *Block; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h]
  char v21; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v24; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+80h] [rbp-80h] BYREF
  char v26; // [rsp+90h] [rbp-70h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&Block);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &Block,
                           a1) )
  {
    v2 = 859;
LABEL_3:
    LastError = -2147024882;
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      v2);
LABEL_4:
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&Block);
    return LastError;
  }
  v5 = Block;
  v6 = v20;
  if ( *((_WORD *)Block + ((v20 - (__int64)Block) >> 1) - 1) != 92 )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &Block,
                             L"\\") )
    {
      v2 = 862;
      goto LABEL_3;
    }
    v6 = v20;
    v5 = Block;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpFileName);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           lpFileName,
                           v5,
                           (v6 - (__int64)v5) >> 1) )
  {
    v7 = 866;
LABEL_11:
    LastError = -2147024882;
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      v7);
LABEL_12:
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
    goto LABEL_4;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           lpFileName,
                           L"*") )
  {
    v7 = 867;
    goto LABEL_11;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(lpFileName[0], &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError - 2 <= 1 )
    {
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&Block);
      return 0;
    }
    if ( (int)LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Log_HREvent(
      LastError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      883);
    if ( !LastError )
      Log_AssertionEvent_2(
        v17,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
        883);
    goto LABEL_12;
  }
  NextFileW = 1;
  while ( NextFileW )
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v23);
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v23,
                             Block,
                             (v20 - (__int64)Block) >> 1) )
    {
      v15 = 892;
LABEL_43:
      LastError = -2147024882;
      Log_HREvent(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
        v15);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v23);
LABEL_44:
      FindClose(FirstFileW);
      goto LABEL_12;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v23,
                             FindFileData.cFileName) )
    {
      v15 = 893;
      goto LABEL_43;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      v10 = FindFileData.cFileName[0] - 46;
      if ( FindFileData.cFileName[0] == 46 )
        v10 = FindFileData.cFileName[1];
      if ( v10 )
      {
        v11 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
        {
          v11 = FindFileData.cFileName[1] - 46;
          if ( FindFileData.cFileName[1] == 46 )
            v11 = FindFileData.cFileName[2];
        }
        if ( v11 )
        {
          v12 = _RecursiveDeleteOldFiles(v23[0], 0x134FD9000uLL);
          if ( v12 < 0 )
          {
            v13 = 900;
LABEL_38:
            Log_HREvent(
              (unsigned int)v12,
              0,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
              v13);
          }
        }
      }
    }
    else
    {
      FileTime1 = FindFileData.ftLastWriteTime;
      if ( !(unsigned int)IsFileTimeValid(&FileTime1)
        || (SystemTimeAsFileTime = 0,
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime),
            *(_QWORD *)&SystemTimeAsFileTime < *(unsigned __int64 *)&FileTime1)
        || *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&FileTime1 >= 0x2F25F0C90000uLL )
      {
        if ( !DeleteFileW(v23[0]) )
        {
          v12 = GetLastError();
          v14 = v12 < 0;
          if ( v12 > 0 )
          {
            v12 = (unsigned __int16)v12 | 0x80070000;
            v14 = v12 < 0;
          }
          if ( v14 )
          {
            v13 = 910;
            goto LABEL_38;
          }
        }
      }
    }
    NextFileW = FindNextFileW(FirstFileW, &FindFileData);
    if ( (char *)v23[0] != &v24 )
      operator delete((void *)v23[0]);
  }
  if ( GetLastError() != 18 )
  {
    v16 = GetLastError();
    LastError = v16;
    if ( v16 > 0 )
      LastError = (unsigned __int16)v16 | 0x80070000;
    Log_HREvent(
      LastError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
      917);
    goto LABEL_44;
  }
  FindClose(FirstFileW);
  if ( (char *)lpFileName[0] != &v26 )
    operator delete((void *)lpFileName[0]);
  if ( Block != &v21 )
    operator delete(Block);
  return 0;
}

```

## disassembly

```asm
0x180034760  mov     [rsp-8+arg_8], rbx
0x180034765  mov     [rsp-8+arg_10], rsi
0x18003476a  push    rbp
0x18003476b  push    rdi
0x18003476c  push    r15
0x18003476e  lea     rbp, [rsp-200h]
0x180034776  sub     rsp, 300h
0x18003477d  mov     rax, cs:__security_cookie
0x180034784  xor     rax, rsp
0x180034787  mov     [rbp+210h+var_20], rax
0x18003478e  mov     rbx, rcx
0x180034791  lea     rcx, [rsp+310h+Block]; void *
0x180034796  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18003479b  mov     rdx, rbx
0x18003479e  lea     rcx, [rsp+310h+Block]
0x1800347a3  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800347a8  test    al, al
0x1800347aa  jnz     short loc_1800347D8
0x1800347ac  mov     r9d, 35Bh
0x1800347b2  mov     ebx, 8007000Eh
0x1800347b7  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800347be  mov     ecx, ebx
0x1800347c0  xor     edx, edx
0x1800347c2  call    Log_HREvent
0x1800347c7  lea     rcx, [rsp+310h+Block]; void *
0x1800347cc  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800347d1  mov     eax, ebx
0x1800347d3  jmp     loc_180034B45
0x1800347d8  mov     rdi, [rsp+310h+Block]
0x1800347dd  mov     rbx, [rsp+310h+var_2D0]
0x1800347e2  mov     rax, rbx
0x1800347e5  sub     rax, rdi
0x1800347e8  sar     rax, 1
0x1800347eb  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x1800347f1  jz      short loc_18003481A
0x1800347f3  lea     rdx, asc_18013D0B8; "\\"
0x1800347fa  lea     rcx, [rsp+310h+Block]
0x1800347ff  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180034804  test    al, al
0x180034806  jnz     short loc_180034810
0x180034808  mov     r9d, 35Eh
0x18003480e  jmp     short loc_1800347B2
0x180034810  mov     rbx, [rsp+310h+var_2D0]
0x180034815  mov     rdi, [rsp+310h+Block]
0x18003481a  lea     rcx, [rbp+210h+lpFileName]; void *
0x18003481e  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180034823  sub     rbx, rdi
0x180034826  lea     rcx, [rbp+210h+lpFileName]
0x18003482a  sar     rbx, 1
0x18003482d  mov     rdx, rdi
0x180034830  mov     r8, rbx
0x180034833  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180034838  test    al, al
0x18003483a  jnz     short loc_180034865
0x18003483c  mov     r9d, 362h
0x180034842  xor     edx, edx
0x180034844  mov     ebx, 8007000Eh
0x180034849  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180034850  mov     ecx, ebx
0x180034852  call    Log_HREvent
0x180034857  lea     rcx, [rbp+210h+lpFileName]; void *
0x18003485b  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180034860  jmp     loc_1800347C7
0x180034865  lea     rdx, pszMore; "*"
0x18003486c  lea     rcx, [rbp+210h+lpFileName]
0x180034870  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180034875  xor     edx, edx; Val
0x180034877  test    al, al
0x180034879  jnz     short loc_180034883
0x18003487b  mov     r9d, 363h
0x180034881  jmp     short loc_180034844
0x180034883  mov     r8d, 250h; Size
0x180034889  lea     rcx, [rbp+210h+FindFileData]; void *
0x18003488d  call    memset_0
0x180034892  mov     rcx, [rbp+210h+lpFileName]; lpFileName
0x180034896  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x18003489a  call    cs:__imp_FindFirstFileW
0x1800348a0  mov     rsi, rax
0x1800348a3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800348a7  jz      loc_180034ADB
0x1800348ad  mov     edi, 1
0x1800348b2  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800348b9  lea     r15d, [rdi+2Dh]
0x1800348bd  test    edi, edi
0x1800348bf  jz      loc_180034A62
0x1800348c5  lea     rcx, [rsp+310h+var_2B0]; void *
0x1800348ca  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800348cf  mov     r8, [rsp+310h+var_2D0]
0x1800348d4  lea     rcx, [rsp+310h+var_2B0]
0x1800348d9  mov     rdx, [rsp+310h+Block]
0x1800348de  sub     r8, rdx
0x1800348e1  sar     r8, 1
0x1800348e4  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800348e9  test    al, al
0x1800348eb  jz      loc_180034A2F
0x1800348f1  lea     rdx, [rbp+210h+FindFileData.cFileName]
0x1800348f5  lea     rcx, [rsp+310h+var_2B0]
0x1800348fa  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800348ff  test    al, al
0x180034901  jz      loc_180034A27
0x180034907  test    byte ptr [rbp+210h+FindFileData.dwFileAttributes], 10h
0x18003490b  jz      short loc_180034972
0x18003490d  movzx   edx, [rbp+210h+FindFileData.cFileName]
0x180034911  sub     edx, r15d
0x180034914  jnz     short loc_180034921
0x180034916  movzx   edx, [rbp+210h+FindFileData.cFileName+2]
0x18003491a  xor     eax, eax
0x18003491c  movzx   ecx, ax
0x18003491f  sub     edx, ecx
0x180034921  test    edx, edx
0x180034923  jz      loc_1800349F8
0x180034929  movzx   edx, [rbp+210h+FindFileData.cFileName]
0x18003492d  sub     edx, r15d
0x180034930  jnz     short loc_180034946
0x180034932  movzx   edx, [rbp+210h+FindFileData.cFileName+2]
0x180034936  sub     edx, r15d
0x180034939  jnz     short loc_180034946
0x18003493b  movzx   edx, [rbp+210h+FindFileData.cFileName+4]
0x18003493f  xor     eax, eax
0x180034941  movzx   ecx, ax
0x180034944  sub     edx, ecx
0x180034946  test    edx, edx
0x180034948  jz      loc_1800349F8
0x18003494e  mov     rcx, [rsp+310h+var_2B0]; unsigned __int16 *
0x180034953  mov     rdx, 134FD9000h; unsigned __int64
0x18003495d  call    ?_RecursiveDeleteOldFiles@@YAJPEBG_K@Z; _RecursiveDeleteOldFiles(ushort const *,unsigned __int64)
0x180034962  test    eax, eax
0x180034964  jns     loc_1800349F8
0x18003496a  mov     r9d, 384h
0x180034970  jmp     short loc_1800349E8
0x180034972  mov     rax, qword ptr [rbp+210h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x180034976  lea     rcx, [rsp+310h+FileTime1]; lpFileTime1
0x18003497b  mov     qword ptr [rsp+310h+FileTime1.dwLowDateTime], rax
0x180034980  call    ?IsFileTimeValid@@YAHAEBU_FILETIME@@@Z; IsFileTimeValid(_FILETIME const &)
0x180034985  test    eax, eax
0x180034987  jz      short loc_1800349BD
0x180034989  lea     rcx, [rsp+310h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003498e  mov     qword ptr [rsp+310h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180034997  call    cs:__imp_GetSystemTimeAsFileTime
0x18003499d  mov     rax, qword ptr [rsp+310h+SystemTimeAsFileTime.dwLowDateTime]
0x1800349a2  cmp     rax, qword ptr [rsp+310h+FileTime1.dwLowDateTime]
0x1800349a7  jb      short loc_1800349BD
0x1800349a9  sub     rax, qword ptr [rsp+310h+FileTime1.dwLowDateTime]
0x1800349ae  mov     rcx, 2F25F0C90000h
0x1800349b8  cmp     rax, rcx
0x1800349bb  jb      short loc_1800349F8
0x1800349bd  mov     rcx, [rsp+310h+var_2B0]; lpFileName
0x1800349c2  call    cs:__imp_DeleteFileW
0x1800349c8  test    eax, eax
0x1800349ca  jnz     short loc_1800349F8
0x1800349cc  call    cs:__imp_GetLastError
0x1800349d2  test    eax, eax
0x1800349d4  jle     short loc_1800349E0
0x1800349d6  movzx   eax, ax
0x1800349d9  or      eax, 80070000h
0x1800349de  test    eax, eax
0x1800349e0  jns     short loc_1800349F8
0x1800349e2  mov     r9d, 38Eh
0x1800349e8  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800349ef  xor     edx, edx
0x1800349f1  mov     ecx, eax
0x1800349f3  call    Log_HREvent
0x1800349f8  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x1800349fc  mov     rcx, rsi; hFindFile
0x1800349ff  call    cs:__imp_FindNextFileW
0x180034a05  mov     rcx, [rsp+310h+var_2B0]; Block
0x180034a0a  mov     edi, eax
0x180034a0c  lea     rax, [rsp+310h+var_2A0]
0x180034a11  cmp     rcx, rax
0x180034a14  jz      loc_1800348BD
0x180034a1a  mov     rdx, rbx
0x180034a1d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180034a22  jmp     loc_1800348BD
0x180034a27  mov     r9d, 37Dh
0x180034a2d  jmp     short loc_180034A35
0x180034a2f  mov     r9d, 37Ch
0x180034a35  mov     ebx, 8007000Eh
0x180034a3a  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180034a41  mov     ecx, ebx
0x180034a43  xor     edx, edx
0x180034a45  call    Log_HREvent
0x180034a4a  lea     rcx, [rsp+310h+var_2B0]; void *
0x180034a4f  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180034a54  mov     rcx, rsi; hFindFile
0x180034a57  call    cs:__imp_FindClose
0x180034a5d  jmp     loc_180034857
0x180034a62  call    cs:__imp_GetLastError
0x180034a68  cmp     eax, 12h
0x180034a6b  jnz     short loc_180034AAB
0x180034a6d  mov     rcx, rsi; hFindFile
0x180034a70  call    cs:__imp_FindClose
0x180034a76  mov     rcx, [rbp+210h+lpFileName]; Block
0x180034a7a  lea     rax, [rbp+210h+var_280]
0x180034a7e  cmp     rcx, rax
0x180034a81  jz      short loc_180034A8B
0x180034a83  mov     rdx, rbx
0x180034a86  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180034a8b  mov     rcx, [rsp+310h+Block]; Block
0x180034a90  lea     rax, [rsp+310h+var_2C8]
0x180034a95  cmp     rcx, rax
0x180034a98  jz      loc_180034B43
0x180034a9e  mov     rdx, rbx
0x180034aa1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180034aa6  jmp     loc_180034B43
0x180034aab  call    cs:__imp_GetLastError
0x180034ab1  mov     ebx, eax
0x180034ab3  test    eax, eax
0x180034ab5  jle     short loc_180034AC0
0x180034ab7  movzx   ebx, ax
0x180034aba  or      ebx, 80070000h
0x180034ac0  mov     r9d, 395h
0x180034ac6  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180034acd  xor     edx, edx
0x180034acf  mov     ecx, ebx
0x180034ad1  call    Log_HREvent
0x180034ad6  jmp     loc_180034A54
0x180034adb  call    cs:__imp_GetLastError
0x180034ae1  mov     ebx, eax
0x180034ae3  mov     edi, 1
0x180034ae8  add     eax, 0FFFFFFFEh
0x180034aeb  cmp     eax, edi
0x180034aed  jbe     short loc_180034B30
0x180034aef  test    ebx, ebx
0x180034af1  jle     short loc_180034AFC
0x180034af3  movzx   ebx, bx
0x180034af6  or      ebx, 80070000h
0x180034afc  mov     edi, 373h
0x180034b01  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180034b08  mov     r9d, edi
0x180034b0b  xor     edx, edx
0x180034b0d  mov     ecx, ebx
0x180034b0f  call    Log_HREvent
0x180034b14  test    ebx, ebx
0x180034b16  jnz     loc_180034857
0x180034b1c  mov     r8d, edi
0x180034b1f  lea     rdx, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180034b26  call    Log_AssertionEvent_2
0x180034b2b  jmp     loc_180034857
0x180034b30  lea     rcx, [rbp+210h+lpFileName]; void *
0x180034b34  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180034b39  lea     rcx, [rsp+310h+Block]; void *
0x180034b3e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180034b43  xor     eax, eax
0x180034b45  mov     rcx, [rbp+210h+var_20]
0x180034b4c  xor     rcx, rsp; StackCookie
0x180034b4f  call    __security_check_cookie
0x180034b54  lea     r11, [rsp+310h+var_10]
0x180034b5c  mov     rbx, [r11+28h]
0x180034b60  mov     rsi, [r11+30h]
0x180034b64  mov     rsp, r11
0x180034b67  pop     r15
0x180034b69  pop     rdi
0x180034b6a  pop     rbp
0x180034b6b  retn
```
