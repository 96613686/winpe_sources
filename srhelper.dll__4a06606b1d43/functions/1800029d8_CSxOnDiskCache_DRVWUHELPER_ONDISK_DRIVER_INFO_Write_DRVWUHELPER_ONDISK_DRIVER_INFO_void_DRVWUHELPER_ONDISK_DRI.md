# CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::EnumUniqueIds(ulong *,_GUID * *)

- ea: `0x1800029d8`
- end: `0x180002e93`
- name: `?EnumUniqueIds@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@QEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `1211`
- prototype: `void __fastcall __noreturn(__int64, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000b3b0`

## callees

- `0x1800012d4`
- `0x1800012f8`
- `0x180002028`
- `0x180002574`
- `0x1800029d8`
- `0x180003968`
- `0x180003ce0`
- `0x180003e5c`
- `0x18000d348`
- `0x18000d43c`
- `0x18000f154`
- `0x180014f38`
- `0x18001528c`
- `0x180015390`
- `0x180015760`
- `0x1800157be`
- `0x1800157f0`

## import_xrefs

- `KERNEL32!FindFirstFileW` at `0x180002b9f`
- `KERNEL32!FindFirstFileW` at `0x180002b9f`
- `KERNEL32!GetLastError` at `0x180002ca5`
- `KERNEL32!GetLastError` at `0x180002d62`
- `KERNEL32!GetLastError` at `0x180002d6d`
- `KERNEL32!GetLastError` at `0x180002ca5`
- `KERNEL32!GetLastError` at `0x180002d62`
- `KERNEL32!GetLastError` at `0x180002d6d`
- `KERNEL32!FindNextFileW` at `0x180002c99`
- `KERNEL32!FindNextFileW` at `0x180002c99`
- `KERNEL32!FindClose` at `0x180002e57`
- `KERNEL32!FindClose` at `0x180002e57`
- `ole32!CLSIDFromString` at `0x180002c57`
- `ole32!CLSIDFromString` at `0x180002c57`

## string_xrefs

- `0x180002a4c`: `CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_DRIVER_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,struct _DRVWUHELPER_ONDISK_DRIVER_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,struct _DRVWUHELPER_ONDISK_DRIVER_INFO *)>::EnumUniqueIds`
- `0x180002dab`: `( (GetLastError() == ERROR_FILE_NOT_FOUND) || (GetLastError() == ERROR_PATH_NOT_FOUND) )`

## pseudocode

```c
void __fastcall __noreturn CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::EnumUniqueIds(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v6; // rsi
  __int64 FirstFileW; // rdi
  __int64 v8; // rbx
  __int16 v9; // ax
  _WIN32_FIND_DATAW *p_FindFileData; // rax
  _QWORD *v11; // rax
  LPCWSTR v12; // r14
  unsigned int v13; // r13d
  const unsigned __int16 *v14; // r9
  __int16 v15; // ax
  const OLECHAR *v16; // rcx
  BOOL NextFileW; // esi
  __int64 v18; // rax
  int v19; // eax
  int LastFailureAsHRESULT; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  const unsigned __int16 *v23; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v24; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v25; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v26; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v27; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v28; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v29; // [rsp+50h] [rbp-B0h]
  int CacheFileName; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v31; // [rsp+64h] [rbp-9Ch]
  __int16 v32; // [rsp+66h] [rbp-9Ah]
  LPCOLESTR lpsz; // [rsp+98h] [rbp-68h] BYREF
  __int64 v34; // [rsp+A0h] [rbp-60h]
  const unsigned __int16 **v35; // [rsp+A8h] [rbp-58h]
  __int64 *v36; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v37; // [rsp+B8h] [rbp-48h]
  __int64 *v38; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v39; // [rsp+C8h] [rbp-38h]
  LPCWSTR lpFileName[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v41; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v42; // [rsp+E8h] [rbp-18h]
  GUID v43; // [rsp+F0h] [rbp-10h] BYREF
  GUID pclsid; // [rsp+100h] [rbp+0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+110h] [rbp+10h] BYREF

  v35 = (const unsigned __int16 **)a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&CacheFileName,
    "CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_DRIVER_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,stru"
    "ct _DRVWUHELPER_ONDISK_DRIVER_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,struct _DRVWUHELPER_O"
    "NDISK_DRIVER_INFO *)>::EnumUniqueIds",
    265);
  v6 = 592;
  v41 = qword_18001A620;
  lpFileName[0] = (LPCWSTR)qword_18001A620;
  v42 = 0;
  lpFileName[1] = 0;
  FirstFileW = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v39 = 0;
  v38 = qword_18001A620;
  v8 = 0;
  v36 = qword_18001A620;
  v9 = 276;
  v37 = 0;
  if ( !a2 || (v31 = 276, v9 = 277, !a3) )
  {
    CacheFileName = -2147024809;
    goto LABEL_41;
  }
  v31 = 277;
  p_FindFileData = &FindFileData;
  CacheFileName = 0;
  *a2 = 0;
  *a3 = 0;
  do
  {
    LOBYTE(p_FindFileData->dwFileAttributes) = 0;
    p_FindFileData = (_WIN32_FIND_DATAW *)((char *)p_FindFileData + 1);
    --v6;
  }
  while ( v6 );
  v11 = operator new(0x18u);
  v8 = (__int64)v11;
  if ( !v11 )
  {
    v8 = 0;
    CacheFileName = -2147024882;
    v9 = 283;
LABEL_41:
    v32 = v9;
    goto LABEL_42;
  }
  *(_DWORD *)v11 = 1;
  v11[1] = 0;
  v11[2] = 0;
  CacheFileName = 0;
  v31 = 283;
  CacheFileName = CBsString::Set((CBsString *)&v38, &GUID_NULL);
  v9 = 285;
  if ( CacheFileName < 0 )
    goto LABEL_41;
  v31 = 285;
  CacheFileName = CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::_CreateCacheFileName(
                    a1,
                    &GUID_NULL,
                    0,
                    (CBsString *)&v36);
  v9 = 286;
  if ( CacheFileName < 0 )
    goto LABEL_41;
  v31 = 286;
  CacheFileName = CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::_CreateCacheFileName(
                    a1,
                    0,
                    0,
                    (CBsString *)lpFileName);
  v9 = 287;
  if ( CacheFileName < 0 )
    goto LABEL_41;
  v12 = lpFileName[0];
  v31 = 287;
  FirstFileW = (__int64)FindFirstFileW(lpFileName[0], &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( GetLastError() == 2 || GetLastError() == 3 )
    {
      CacheFileName = 0;
      v31 = 295;
LABEL_26:
      *a2 = *(_DWORD *)(v8 + 16);
      v18 = *(_QWORD *)(v8 + 8);
      *(_QWORD *)(v8 + 8) = 0;
      *(_QWORD *)(v8 + 16) = 0;
      *a3 = v18;
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT();
      CacheFileName = LastFailureAsHRESULT;
      v32 = 295;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_sSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          (unsigned int)WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids,
          (unsigned int)"( (GetLastError() == ERROR_FILE_NOT_FOUND) || (GetLastError() == ERROR_PATH_NOT_FOUND) )",
          (__int64)v12,
          LastFailureAsHRESULT);
      }
    }
    goto LABEL_42;
  }
  v13 = v39;
  while ( 1 )
  {
    lpsz = (LPCOLESTR)qword_18001A620;
    pclsid = GUID_NULL;
    v34 = 0;
    CacheFileName = CBsString::Append((CBsString *)&lpsz, FindFileData.cFileName);
    v15 = 304;
    if ( CacheFileName < 0 )
      goto LABEL_28;
    v31 = 304;
    CacheFileName = CBsString::SetPath(
                      (CBsString *)&v41,
                      *v35,
                      FindFileData.cFileName,
                      v14,
                      v23,
                      v24,
                      v25,
                      v26,
                      v27,
                      v28,
                      v29);
    v15 = 305;
    if ( CacheFileName < 0 )
      goto LABEL_28;
    v31 = 305;
    if ( (_DWORD)v42 == (_DWORD)v37 )
    {
      v15 = 312;
      if ( v13 > HIDWORD(v34) )
      {
        CacheFileName = -2147024809;
LABEL_28:
        v32 = v15;
        goto LABEL_29;
      }
      v16 = lpsz;
      LODWORD(v34) = v13;
      lpsz[v13] = 0;
      CacheFileName = 0;
      v31 = 312;
      CacheFileName = CLSIDFromString(v16, &pclsid);
      if ( CacheFileName )
      {
        CacheFileName = 0;
      }
      else
      {
        v43 = pclsid;
        CacheFileName = CSxSimpleArray<_GUID>::Append(v8, &v43);
        v15 = 320;
        if ( CacheFileName < 0 )
          goto LABEL_28;
        v31 = 320;
      }
    }
    NextFileW = FindNextFileW((HANDLE)FirstFileW, &FindFileData);
    if ( !NextFileW )
      break;
LABEL_25:
    CBsString::_Release((LPVOID *)&lpsz);
    if ( !NextFileW )
      goto LABEL_26;
  }
  if ( GetLastError() == 18 )
  {
    CacheFileName = NextFileW;
    v31 = 327;
    goto LABEL_25;
  }
  v19 = GetLastFailureAsHRESULT();
  CacheFileName = v19;
  v32 = 327;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    WPP_SF_sSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids,
      (unsigned int)"( GetLastError() == ERROR_NO_MORE_FILES )",
      (__int64)v12,
      v19);
LABEL_29:
  CBsString::_Release((LPVOID *)&lpsz);
LABEL_42:
  CBsString::_Release((LPVOID *)&v36);
  CBsString::_Release((LPVOID *)&v38);
  if ( v8 && _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
  {
    CSxSimpleArray<_GUID>::~CSxSimpleArray<_GUID>(v8);
    operator delete((void *)v8);
  }
  CBsString::_Release((LPVOID *)lpFileName);
  CBsString::_Release((LPVOID *)&v41);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose((HANDLE)FirstFileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&CacheFileName, v21, v22);
}

```

## disassembly

```asm
0x1800029d8  mov     [rsp-8+arg_18], rbx
0x1800029dd  push    rbp
0x1800029de  push    rsi
0x1800029df  push    rdi
0x1800029e0  push    r12
0x1800029e2  push    r13
0x1800029e4  push    r14
0x1800029e6  push    r15
0x1800029e8  lea     rbp, [rsp-270h]
0x1800029f0  sub     rsp, 370h
0x1800029f7  mov     rax, cs:__security_cookie
0x1800029fe  xor     rax, rsp
0x180002a01  mov     [rbp+2A0h+var_40], rax
0x180002a08  mov     r15, r8
0x180002a0b  mov     [rbp+2A0h+var_2F8], rcx
0x180002a0f  mov     r12, rdx
0x180002a12  mov     r14, rcx
0x180002a15  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a1c  lea     rax, WPP_GLOBAL_Control
0x180002a23  cmp     rcx, rax
0x180002a26  jz      short loc_180002A46
0x180002a28  test    dword ptr [rcx+1Ch], 20000000h
0x180002a2f  jz      short loc_180002A46
0x180002a31  mov     rcx, [rcx+10h]
0x180002a35  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x180002a3c  mov     edx, 14h
0x180002a41  call    WPP_SF_
0x180002a46  mov     r8d, 109h; unsigned __int16
0x180002a4c  lea     rdx, aCsxondiskcache_8
0x180002a53  lea     rcx, [rsp+3A0h+var_340]; this
0x180002a58  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z
0x180002a5d  lea     rax, qword_18001A620
0x180002a64  xor     r13d, r13d
0x180002a67  mov     esi, 250h
0x180002a6c  mov     [rbp+2A0h+var_2C0], rax
0x180002a70  mov     r8d, esi; Size
0x180002a73  mov     [rbp+2A0h+lpFileName], rax
0x180002a77  xor     edx, edx; Val
0x180002a79  mov     [rbp+2A0h+var_2B8], r13
0x180002a7d  lea     rcx, [rbp+2A0h+FindFileData]; void *
0x180002a81  mov     [rbp+2A0h+var_2C8], r13
0x180002a85  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180002a89  call    memset_0
0x180002a8e  mov     [rbp+2A0h+var_2D8], r13
0x180002a92  lea     rax, qword_18001A620
0x180002a99  mov     [rbp+2A0h+var_2E0], rax
0x180002a9d  mov     ebx, r13d
0x180002aa0  mov     [rbp+2A0h+var_2F0], rax
0x180002aa4  mov     eax, 114h
0x180002aa9  mov     [rbp+2A0h+var_2E8], r13
0x180002aad  test    r12, r12
0x180002ab0  jz      loc_180002DF4
0x180002ab6  mov     [rsp+3A0h+var_33C], ax
0x180002abb  mov     eax, 115h
0x180002ac0  test    r15, r15
0x180002ac3  jz      loc_180002DF4
0x180002ac9  mov     [rsp+3A0h+var_33C], ax
0x180002ace  lea     rax, [rbp+2A0h+FindFileData]
0x180002ad2  mov     [rsp+3A0h+var_340], r13d
0x180002ad7  mov     [r12], r13d
0x180002adb  mov     [r15], r13
0x180002ade  mov     [rax], r13b
0x180002ae1  inc     rax
0x180002ae4  sub     rsi, 1
0x180002ae8  jnz     short loc_180002ADE
0x180002aea  lea     ecx, [rsi+18h]; Size
0x180002aed  call    ??2@YAPEAX_K@Z
0x180002af2  mov     rbx, rax
0x180002af5  test    rax, rax
0x180002af8  jz      loc_180002DE2
0x180002afe  mov     dword ptr [rax], 1
0x180002b04  mov     [rax+8], r13
0x180002b08  mov     [rax+10h], r13
0x180002b0c  mov     eax, 11Bh
0x180002b11  mov     [rsp+3A0h+var_340], r13d
0x180002b16  lea     rdx, GUID_NULL; struct _GUID *
0x180002b1d  mov     [rsp+3A0h+var_33C], ax
0x180002b22  lea     rcx, [rbp+2A0h+var_2E0]; this
0x180002b26  call    ?Set@CBsString@@QEAAJAEBU_GUID@@@Z
0x180002b2b  mov     [rsp+3A0h+var_340], eax
0x180002b2f  test    eax, eax
0x180002b31  mov     eax, 11Dh
0x180002b36  js      loc_180002DFC
0x180002b3c  lea     r9, [rbp+2A0h+var_2F0]
0x180002b40  mov     [rsp+3A0h+var_33C], ax
0x180002b45  xor     r8d, r8d
0x180002b48  lea     rdx, GUID_NULL
0x180002b4f  mov     rcx, r14
0x180002b52  call    ?_CreateCacheFileName@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@AEAAJPEBU_GUID@@HPEAVCBsString@@@Z
0x180002b57  mov     [rsp+3A0h+var_340], eax
0x180002b5b  test    eax, eax
0x180002b5d  mov     eax, 11Eh
0x180002b62  js      loc_180002DFC
0x180002b68  lea     r9, [rbp+2A0h+lpFileName]
0x180002b6c  mov     [rsp+3A0h+var_33C], ax
0x180002b71  xor     r8d, r8d
0x180002b74  xor     edx, edx
0x180002b76  mov     rcx, r14
0x180002b79  call    ?_CreateCacheFileName@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@AEAAJPEBU_GUID@@HPEAVCBsString@@@Z
0x180002b7e  mov     [rsp+3A0h+var_340], eax
0x180002b82  test    eax, eax
0x180002b84  mov     eax, 11Fh
0x180002b89  js      loc_180002DFC
0x180002b8f  mov     r14, [rbp+2A0h+lpFileName]
0x180002b93  lea     rdx, [rbp+2A0h+FindFileData]; lpFindFileData
0x180002b97  mov     rcx, r14; lpFileName
0x180002b9a  mov     [rsp+3A0h+var_33C], ax
0x180002b9f  call    cs:__imp_FindFirstFileW
0x180002ba5  mov     rdi, rax
0x180002ba8  dec     rax
0x180002bab  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002baf  ja      loc_180002D62
0x180002bb5  mov     r13, [rbp+2A0h+var_2D8]
0x180002bb9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180002bc0  lea     rax, qword_18001A620
0x180002bc7  xor     esi, esi
0x180002bc9  mov     [rbp+2A0h+lpsz], rax
0x180002bcd  movdqu  xmmword ptr [rbp+2A0h+pclsid.Data1], xmm0
0x180002bd2  mov     [rbp+2A0h+var_300], rsi
0x180002bd6  lea     rdx, [rbp+2A0h+FindFileData.cFileName]; unsigned __int16 *
0x180002bda  lea     rcx, [rbp+2A0h+lpsz]; this
0x180002bde  call    ?Append@CBsString@@QEAAJPEBG@Z
0x180002be3  mov     [rsp+3A0h+var_340], eax
0x180002be7  test    eax, eax
0x180002be9  mov     eax, 130h
0x180002bee  js      loc_180002CF9
0x180002bf4  mov     [rsp+3A0h+var_33C], ax
0x180002bf9  lea     r8, [rbp+2A0h+FindFileData.cFileName]; unsigned __int16 *
0x180002bfd  mov     rax, [rbp+2A0h+var_2F8]
0x180002c01  lea     rcx, [rbp+2A0h+var_2C0]; this
0x180002c05  mov     rdx, [rax]; unsigned __int16 *
0x180002c08  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z
0x180002c0d  mov     [rsp+3A0h+var_340], eax
0x180002c11  test    eax, eax
0x180002c13  mov     eax, 131h
0x180002c18  js      loc_180002CF9
0x180002c1e  mov     [rsp+3A0h+var_33C], ax
0x180002c23  mov     rax, [rbp+2A0h+var_2E8]
0x180002c27  cmp     dword ptr [rbp+2A0h+var_2B8], eax
0x180002c2a  jnz     short loc_180002C92
0x180002c2c  mov     eax, 138h
0x180002c31  cmp     r13d, dword ptr [rbp+2A0h+var_300+4]
0x180002c35  ja      loc_180002CF1
0x180002c3b  mov     rcx, [rbp+2A0h+lpsz]; lpsz
0x180002c3f  mov     edx, r13d
0x180002c42  mov     dword ptr [rbp+2A0h+var_300], r13d
0x180002c46  mov     [rcx+rdx*2], si
0x180002c4a  lea     rdx, [rbp+2A0h+pclsid]; pclsid
0x180002c4e  mov     [rsp+3A0h+var_340], esi
0x180002c52  mov     [rsp+3A0h+var_33C], ax
0x180002c57  call    cs:__imp_CLSIDFromString
0x180002c5d  mov     [rsp+3A0h+var_340], eax
0x180002c61  test    eax, eax
0x180002c63  jz      short loc_180002C6B
0x180002c65  mov     [rsp+3A0h+var_340], esi
0x180002c69  jmp     short loc_180002C92
0x180002c6b  movaps  xmm0, xmmword ptr [rbp+2A0h+pclsid.Data1]
0x180002c6f  lea     rdx, [rbp+2A0h+var_2B0]
0x180002c73  mov     rcx, rbx
0x180002c76  movdqa  [rbp+2A0h+var_2B0], xmm0
0x180002c7b  call    ?Append@?$CSxSimpleArray@U_GUID@@@@QEAAJU_GUID@@@Z
0x180002c80  mov     [rsp+3A0h+var_340], eax
0x180002c84  test    eax, eax
0x180002c86  mov     eax, 140h
0x180002c8b  js      short loc_180002CF9
0x180002c8d  mov     [rsp+3A0h+var_33C], ax
0x180002c92  lea     rdx, [rbp+2A0h+FindFileData]; lpFindFileData
0x180002c96  mov     rcx, rdi; hFindFile
0x180002c99  call    cs:__imp_FindNextFileW
0x180002c9f  mov     esi, eax
0x180002ca1  test    eax, eax
0x180002ca3  jnz     short loc_180002CBE
0x180002ca5  call    cs:__imp_GetLastError
0x180002cab  cmp     eax, 12h
0x180002cae  jnz     short loc_180002D0C
0x180002cb0  mov     eax, 147h
0x180002cb5  mov     [rsp+3A0h+var_340], esi
0x180002cb9  mov     [rsp+3A0h+var_33C], ax
0x180002cbe  lea     rcx, [rbp+2A0h+lpsz]; this
0x180002cc2  call    ?_Release@CBsString@@AEAAXXZ
0x180002cc7  test    esi, esi
0x180002cc9  jnz     loc_180002BB9
0x180002ccf  xor     r13d, r13d
0x180002cd2  mov     eax, [rbx+10h]
0x180002cd5  mov     [r12], eax
0x180002cd9  mov     rax, [rbx+8]
0x180002cdd  mov     [rbx+8], r13
0x180002ce1  mov     qword ptr [rbx+10h], 0
0x180002ce9  mov     [r15], rax
0x180002cec  jmp     loc_180002E01
0x180002cf1  mov     [rsp+3A0h+var_340], 80070057h
0x180002cf9  mov     [rsp+3A0h+var_33A], ax
0x180002cfe  lea     rcx, [rbp+2A0h+lpsz]; this
0x180002d02  call    ?_Release@CBsString@@AEAAXXZ
0x180002d07  jmp     loc_180002E01
0x180002d0c  call    GetLastFailureAsHRESULT
0x180002d11  mov     ecx, 147h
0x180002d16  mov     [rsp+3A0h+var_340], eax
0x180002d1a  mov     [rsp+3A0h+var_33A], cx
0x180002d1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d26  lea     rdx, WPP_GLOBAL_Control
0x180002d2d  cmp     rcx, rdx
0x180002d30  jz      short loc_180002CFE
0x180002d32  test    dword ptr [rcx+1Ch], 2000000h
0x180002d39  jz      short loc_180002CFE
0x180002d3b  mov     rcx, [rcx+10h]
0x180002d3f  lea     r9, aGetlasterrorEr
0x180002d46  mov     dword ptr [rsp+3A0h+var_378], eax
0x180002d4a  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x180002d51  mov     edx, 16h
0x180002d56  mov     [rsp+3A0h+var_380], r14
0x180002d5b  call    WPP_SF_sSd
0x180002d60  jmp     short loc_180002CFE
0x180002d62  call    cs:__imp_GetLastError
0x180002d68  cmp     eax, 2
0x180002d6b  jz      short loc_180002DCE
0x180002d6d  call    cs:__imp_GetLastError
0x180002d73  cmp     eax, 3
0x180002d76  jz      short loc_180002DCE
0x180002d78  call    GetLastFailureAsHRESULT
0x180002d7d  mov     ecx, 127h
0x180002d82  mov     [rsp+3A0h+var_340], eax
0x180002d86  mov     [rsp+3A0h+var_33A], cx
0x180002d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d92  lea     rdx, WPP_GLOBAL_Control
0x180002d99  cmp     rcx, rdx
0x180002d9c  jz      short loc_180002E01
0x180002d9e  test    dword ptr [rcx+1Ch], 2000000h
0x180002da5  jz      short loc_180002E01
0x180002da7  mov     rcx, [rcx+10h]
0x180002dab  lea     r9, aGetlasterrorEr_0
0x180002db2  mov     dword ptr [rsp+3A0h+var_378], eax
0x180002db6  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x180002dbd  mov     edx, 15h
0x180002dc2  mov     [rsp+3A0h+var_380], r14
0x180002dc7  call    WPP_SF_sSd
0x180002dcc  jmp     short loc_180002E01
0x180002dce  mov     ecx, 127h
0x180002dd3  mov     [rsp+3A0h+var_340], r13d
0x180002dd8  mov     [rsp+3A0h+var_33C], cx
0x180002ddd  jmp     loc_180002CD2
0x180002de2  mov     rbx, r13
0x180002de5  mov     [rsp+3A0h+var_340], 8007000Eh
0x180002ded  mov     eax, 11Bh
0x180002df2  jmp     short loc_180002DFC
0x180002df4  mov     [rsp+3A0h+var_340], 80070057h
0x180002dfc  mov     [rsp+3A0h+var_33A], ax
0x180002e01  mov     esi, [rsp+3A0h+var_340]
0x180002e05  lea     rcx, [rbp+2A0h+var_2F0]; this
0x180002e09  call    ?_Release@CBsString@@AEAAXXZ
0x180002e0e  lea     rcx, [rbp+2A0h+var_2E0]; this
0x180002e12  call    ?_Release@CBsString@@AEAAXXZ
0x180002e17  test    rbx, rbx
0x180002e1a  jz      short loc_180002E38
0x180002e1c  or      eax, 0FFFFFFFFh
0x180002e1f  lock xadd [rbx], eax
0x180002e23  cmp     eax, 1
0x180002e26  jnz     short loc_180002E38
0x180002e28  mov     rcx, rbx
0x180002e2b  call    ??1?$CSxSimpleArray@U_GUID@@@@AEAA@XZ
0x180002e30  mov     rcx, rbx; Block
0x180002e33  call    ??3@YAXPEAX@Z
0x180002e38  lea     rcx, [rbp+2A0h+lpFileName]; this
0x180002e3c  call    ?_Release@CBsString@@AEAAXXZ
0x180002e41  lea     rcx, [rbp+2A0h+var_2C0]; this
0x180002e45  call    ?_Release@CBsString@@AEAAXXZ
0x180002e4a  lea     rcx, [rdi-1]
0x180002e4e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180002e52  ja      short loc_180002E5D
0x180002e54  mov     rcx, rdi; hFindFile
0x180002e57  call    cs:__imp_FindClose
0x180002e5d  lea     rcx, [rsp+3A0h+var_340]; this
0x180002e62  call    ??1CSxFunctionTracer@@QEAA@XZ
0x180002e67  mov     eax, esi
0x180002e69  mov     rcx, [rbp+2A0h+var_40]
0x180002e70  xor     rcx, rsp; StackCookie
0x180002e73  call    __security_check_cookie
0x180002e78  mov     rbx, [rsp+3A0h+arg_18]
0x180002e80  add     rsp, 370h
0x180002e87  pop     r15
0x180002e89  pop     r14
0x180002e8b  pop     r13
0x180002e8d  pop     r12
0x180002e8f  pop     rdi
0x180002e90  pop     rsi
0x180002e91  pop     rbp
0x180002e92  retn
```
