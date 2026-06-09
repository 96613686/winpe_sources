# CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::EnumUniqueIds(ulong *,_GUID * *)

- ea: `0x180002e9c`
- end: `0x180003357`
- name: `?EnumUniqueIds@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@QEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `1211`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000b3b0`

## callees

- `0x1800012d4`
- `0x1800012f8`
- `0x180002028`
- `0x180002574`
- `0x180002e9c`
- `0x180003b24`
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

- `KERNEL32!FindFirstFileW` at `0x180003063`
- `KERNEL32!FindFirstFileW` at `0x180003063`
- `KERNEL32!GetLastError` at `0x180003169`
- `KERNEL32!GetLastError` at `0x180003226`
- `KERNEL32!GetLastError` at `0x180003231`
- `KERNEL32!GetLastError` at `0x180003169`
- `KERNEL32!GetLastError` at `0x180003226`
- `KERNEL32!GetLastError` at `0x180003231`
- `KERNEL32!FindNextFileW` at `0x18000315d`
- `KERNEL32!FindNextFileW` at `0x18000315d`
- `KERNEL32!FindClose` at `0x18000331b`
- `KERNEL32!FindClose` at `0x18000331b`
- `ole32!CLSIDFromString` at `0x18000311b`
- `ole32!CLSIDFromString` at `0x18000311b`

## string_xrefs

- `0x18000326f`: `( (GetLastError() == ERROR_FILE_NOT_FOUND) || (GetLastError() == ERROR_PATH_NOT_FOUND) )`
- `0x180002f10`: `CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::EnumUniqueIds`

## pseudocode

```c
__int64 __fastcall CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::EnumUniqueIds(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v6; // rsi
  __int64 FirstFileW; // rdi
  __int64 v8; // rbx
  __int16 v9; // ax
  struct _WIN32_FIND_DATAW *p_FindFileData; // rax
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
  unsigned int v21; // esi
  __int64 v22; // rdx
  __int64 v23; // r8
  const unsigned __int16 *v25; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v26; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v27; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v28; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v29; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v30; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v31; // [rsp+50h] [rbp-B0h]
  int CacheFileName; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v33; // [rsp+64h] [rbp-9Ch]
  __int16 v34; // [rsp+66h] [rbp-9Ah]
  LPCOLESTR lpsz; // [rsp+98h] [rbp-68h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-60h]
  const unsigned __int16 **v37; // [rsp+A8h] [rbp-58h]
  __int64 *v38; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-48h]
  __int64 *v40; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v41; // [rsp+C8h] [rbp-38h]
  LPCWSTR lpFileName[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v43; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v44; // [rsp+E8h] [rbp-18h]
  GUID v45; // [rsp+F0h] [rbp-10h] BYREF
  GUID pclsid; // [rsp+100h] [rbp+0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+110h] [rbp+10h] BYREF

  v37 = (const unsigned __int16 **)a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&CacheFileName,
    "CSxOnDiskCache<struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long __cdecl Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_"
    "INFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long __cdecl Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_I"
    "NFO(void *,struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::EnumUniqueIds",
    265);
  v6 = 592;
  v43 = qword_18001A620;
  lpFileName[0] = (LPCWSTR)qword_18001A620;
  v44 = 0;
  lpFileName[1] = 0;
  FirstFileW = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v41 = 0;
  v40 = qword_18001A620;
  v8 = 0;
  v38 = qword_18001A620;
  v9 = 276;
  v39 = 0;
  if ( !a2 || (v33 = 276, v9 = 277, !a3) )
  {
    CacheFileName = -2147024809;
    goto LABEL_41;
  }
  v33 = 277;
  p_FindFileData = &FindFileData;
  CacheFileName = 0;
  *a2 = 0;
  *a3 = 0;
  do
  {
    LOBYTE(p_FindFileData->dwFileAttributes) = 0;
    p_FindFileData = (struct _WIN32_FIND_DATAW *)((char *)p_FindFileData + 1);
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
    v34 = v9;
    goto LABEL_42;
  }
  *(_DWORD *)v11 = 1;
  v11[1] = 0;
  v11[2] = 0;
  CacheFileName = 0;
  v33 = 283;
  CacheFileName = CBsString::Set((CBsString *)&v40, &GUID_NULL);
  v9 = 285;
  if ( CacheFileName < 0 )
    goto LABEL_41;
  v33 = 285;
  CacheFileName = CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::_CreateCacheFileName(
                    a1,
                    &GUID_NULL,
                    0,
                    (CBsString *)&v38);
  v9 = 286;
  if ( CacheFileName < 0 )
    goto LABEL_41;
  v33 = 286;
  CacheFileName = CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::_CreateCacheFileName(
                    a1,
                    0,
                    0,
                    (CBsString *)lpFileName);
  v9 = 287;
  if ( CacheFileName < 0 )
    goto LABEL_41;
  v12 = lpFileName[0];
  v33 = 287;
  FirstFileW = (__int64)FindFirstFileW(lpFileName[0], &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( GetLastError() == 2 || GetLastError() == 3 )
    {
      CacheFileName = 0;
      v33 = 295;
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
      v34 = 295;
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
  v13 = v41;
  while ( 1 )
  {
    lpsz = (LPCOLESTR)qword_18001A620;
    pclsid = GUID_NULL;
    v36 = 0;
    CacheFileName = CBsString::Append((CBsString *)&lpsz, FindFileData.cFileName);
    v15 = 304;
    if ( CacheFileName < 0 )
      goto LABEL_28;
    v33 = 304;
    CacheFileName = CBsString::SetPath(
                      (CBsString *)&v43,
                      *v37,
                      FindFileData.cFileName,
                      v14,
                      v25,
                      v26,
                      v27,
                      v28,
                      v29,
                      v30,
                      v31);
    v15 = 305;
    if ( CacheFileName < 0 )
      goto LABEL_28;
    v33 = 305;
    if ( (_DWORD)v44 == (_DWORD)v39 )
    {
      v15 = 312;
      if ( v13 > HIDWORD(v36) )
      {
        CacheFileName = -2147024809;
LABEL_28:
        v34 = v15;
        goto LABEL_29;
      }
      v16 = lpsz;
      LODWORD(v36) = v13;
      lpsz[v13] = 0;
      CacheFileName = 0;
      v33 = 312;
      CacheFileName = CLSIDFromString(v16, &pclsid);
      if ( CacheFileName )
      {
        CacheFileName = 0;
      }
      else
      {
        v45 = pclsid;
        CacheFileName = CSxSimpleArray<_GUID>::Append(v8, &v45);
        v15 = 320;
        if ( CacheFileName < 0 )
          goto LABEL_28;
        v33 = 320;
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
    v33 = 327;
    goto LABEL_25;
  }
  v19 = GetLastFailureAsHRESULT();
  CacheFileName = v19;
  v34 = 327;
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
  v21 = CacheFileName;
  CBsString::_Release((LPVOID *)&v38);
  CBsString::_Release((LPVOID *)&v40);
  if ( v8 && _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
  {
    CSxSimpleArray<_GUID>::~CSxSimpleArray<_GUID>(v8);
    operator delete((void *)v8);
  }
  CBsString::_Release((LPVOID *)lpFileName);
  CBsString::_Release((LPVOID *)&v43);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose((HANDLE)FirstFileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&CacheFileName, v22, v23);
  return v21;
}

```

## disassembly

```asm
0x180002e9c  mov     [rsp-8+arg_18], rbx
0x180002ea1  push    rbp
0x180002ea2  push    rsi
0x180002ea3  push    rdi
0x180002ea4  push    r12
0x180002ea6  push    r13
0x180002ea8  push    r14
0x180002eaa  push    r15
0x180002eac  lea     rbp, [rsp-270h]
0x180002eb4  sub     rsp, 370h
0x180002ebb  mov     rax, cs:__security_cookie
0x180002ec2  xor     rax, rsp
0x180002ec5  mov     [rbp+2A0h+var_40], rax
0x180002ecc  mov     r15, r8
0x180002ecf  mov     [rbp+2A0h+var_2F8], rcx
0x180002ed3  mov     r12, rdx
0x180002ed6  mov     r14, rcx
0x180002ed9  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ee0  lea     rax, WPP_GLOBAL_Control
0x180002ee7  cmp     rcx, rax
0x180002eea  jz      short loc_180002F0A
0x180002eec  test    dword ptr [rcx+1Ch], 20000000h
0x180002ef3  jz      short loc_180002F0A
0x180002ef5  mov     rcx, [rcx+10h]
0x180002ef9  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x180002f00  mov     edx, 14h
0x180002f05  call    WPP_SF_
0x180002f0a  mov     r8d, 109h; unsigned __int16
0x180002f10  lea     rdx, aCsxondiskcache
0x180002f17  lea     rcx, [rsp+3A0h+var_340]; this
0x180002f1c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z
0x180002f21  lea     rax, qword_18001A620
0x180002f28  xor     r13d, r13d
0x180002f2b  mov     esi, 250h
0x180002f30  mov     [rbp+2A0h+var_2C0], rax
0x180002f34  mov     r8d, esi; Size
0x180002f37  mov     [rbp+2A0h+lpFileName], rax
0x180002f3b  xor     edx, edx; Val
0x180002f3d  mov     [rbp+2A0h+var_2B8], r13
0x180002f41  lea     rcx, [rbp+2A0h+FindFileData]; void *
0x180002f45  mov     [rbp+2A0h+var_2C8], r13
0x180002f49  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180002f4d  call    memset_0
0x180002f52  mov     [rbp+2A0h+var_2D8], r13
0x180002f56  lea     rax, qword_18001A620
0x180002f5d  mov     [rbp+2A0h+var_2E0], rax
0x180002f61  mov     ebx, r13d
0x180002f64  mov     [rbp+2A0h+var_2F0], rax
0x180002f68  mov     eax, 114h
0x180002f6d  mov     [rbp+2A0h+var_2E8], r13
0x180002f71  test    r12, r12
0x180002f74  jz      loc_1800032B8
0x180002f7a  mov     [rsp+3A0h+var_33C], ax
0x180002f7f  mov     eax, 115h
0x180002f84  test    r15, r15
0x180002f87  jz      loc_1800032B8
0x180002f8d  mov     [rsp+3A0h+var_33C], ax
0x180002f92  lea     rax, [rbp+2A0h+FindFileData]
0x180002f96  mov     [rsp+3A0h+var_340], r13d
0x180002f9b  mov     [r12], r13d
0x180002f9f  mov     [r15], r13
0x180002fa2  mov     [rax], r13b
0x180002fa5  inc     rax
0x180002fa8  sub     rsi, 1
0x180002fac  jnz     short loc_180002FA2
0x180002fae  lea     ecx, [rsi+18h]; Size
0x180002fb1  call    ??2@YAPEAX_K@Z
0x180002fb6  mov     rbx, rax
0x180002fb9  test    rax, rax
0x180002fbc  jz      loc_1800032A6
0x180002fc2  mov     dword ptr [rax], 1
0x180002fc8  mov     [rax+8], r13
0x180002fcc  mov     [rax+10h], r13
0x180002fd0  mov     eax, 11Bh
0x180002fd5  mov     [rsp+3A0h+var_340], r13d
0x180002fda  lea     rdx, GUID_NULL; struct _GUID *
0x180002fe1  mov     [rsp+3A0h+var_33C], ax
0x180002fe6  lea     rcx, [rbp+2A0h+var_2E0]; this
0x180002fea  call    ?Set@CBsString@@QEAAJAEBU_GUID@@@Z
0x180002fef  mov     [rsp+3A0h+var_340], eax
0x180002ff3  test    eax, eax
0x180002ff5  mov     eax, 11Dh
0x180002ffa  js      loc_1800032C0
0x180003000  lea     r9, [rbp+2A0h+var_2F0]
0x180003004  mov     [rsp+3A0h+var_33C], ax
0x180003009  xor     r8d, r8d
0x18000300c  lea     rdx, GUID_NULL
0x180003013  mov     rcx, r14
0x180003016  call    ?_CreateCacheFileName@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@AEAAJPEBU_GUID@@HPEAVCBsString@@@Z
0x18000301b  mov     [rsp+3A0h+var_340], eax
0x18000301f  test    eax, eax
0x180003021  mov     eax, 11Eh
0x180003026  js      loc_1800032C0
0x18000302c  lea     r9, [rbp+2A0h+lpFileName]
0x180003030  mov     [rsp+3A0h+var_33C], ax
0x180003035  xor     r8d, r8d
0x180003038  xor     edx, edx
0x18000303a  mov     rcx, r14
0x18000303d  call    ?_CreateCacheFileName@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@AEAAJPEBU_GUID@@HPEAVCBsString@@@Z
0x180003042  mov     [rsp+3A0h+var_340], eax
0x180003046  test    eax, eax
0x180003048  mov     eax, 11Fh
0x18000304d  js      loc_1800032C0
0x180003053  mov     r14, [rbp+2A0h+lpFileName]
0x180003057  lea     rdx, [rbp+2A0h+FindFileData]; lpFindFileData
0x18000305b  mov     rcx, r14; lpFileName
0x18000305e  mov     [rsp+3A0h+var_33C], ax
0x180003063  call    cs:__imp_FindFirstFileW
0x180003069  mov     rdi, rax
0x18000306c  dec     rax
0x18000306f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003073  ja      loc_180003226
0x180003079  mov     r13, [rbp+2A0h+var_2D8]
0x18000307d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180003084  lea     rax, qword_18001A620
0x18000308b  xor     esi, esi
0x18000308d  mov     [rbp+2A0h+lpsz], rax
0x180003091  movdqu  xmmword ptr [rbp+2A0h+pclsid.Data1], xmm0
0x180003096  mov     [rbp+2A0h+var_300], rsi
0x18000309a  lea     rdx, [rbp+2A0h+FindFileData.cFileName]; unsigned __int16 *
0x18000309e  lea     rcx, [rbp+2A0h+lpsz]; this
0x1800030a2  call    ?Append@CBsString@@QEAAJPEBG@Z
0x1800030a7  mov     [rsp+3A0h+var_340], eax
0x1800030ab  test    eax, eax
0x1800030ad  mov     eax, 130h
0x1800030b2  js      loc_1800031BD
0x1800030b8  mov     [rsp+3A0h+var_33C], ax
0x1800030bd  lea     r8, [rbp+2A0h+FindFileData.cFileName]; unsigned __int16 *
0x1800030c1  mov     rax, [rbp+2A0h+var_2F8]
0x1800030c5  lea     rcx, [rbp+2A0h+var_2C0]; this
0x1800030c9  mov     rdx, [rax]; unsigned __int16 *
0x1800030cc  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z
0x1800030d1  mov     [rsp+3A0h+var_340], eax
0x1800030d5  test    eax, eax
0x1800030d7  mov     eax, 131h
0x1800030dc  js      loc_1800031BD
0x1800030e2  mov     [rsp+3A0h+var_33C], ax
0x1800030e7  mov     rax, [rbp+2A0h+var_2E8]
0x1800030eb  cmp     dword ptr [rbp+2A0h+var_2B8], eax
0x1800030ee  jnz     short loc_180003156
0x1800030f0  mov     eax, 138h
0x1800030f5  cmp     r13d, dword ptr [rbp+2A0h+var_300+4]
0x1800030f9  ja      loc_1800031B5
0x1800030ff  mov     rcx, [rbp+2A0h+lpsz]; lpsz
0x180003103  mov     edx, r13d
0x180003106  mov     dword ptr [rbp+2A0h+var_300], r13d
0x18000310a  mov     [rcx+rdx*2], si
0x18000310e  lea     rdx, [rbp+2A0h+pclsid]; pclsid
0x180003112  mov     [rsp+3A0h+var_340], esi
0x180003116  mov     [rsp+3A0h+var_33C], ax
0x18000311b  call    cs:__imp_CLSIDFromString
0x180003121  mov     [rsp+3A0h+var_340], eax
0x180003125  test    eax, eax
0x180003127  jz      short loc_18000312F
0x180003129  mov     [rsp+3A0h+var_340], esi
0x18000312d  jmp     short loc_180003156
0x18000312f  movaps  xmm0, xmmword ptr [rbp+2A0h+pclsid.Data1]
0x180003133  lea     rdx, [rbp+2A0h+var_2B0]
0x180003137  mov     rcx, rbx
0x18000313a  movdqa  [rbp+2A0h+var_2B0], xmm0
0x18000313f  call    ?Append@?$CSxSimpleArray@U_GUID@@@@QEAAJU_GUID@@@Z
0x180003144  mov     [rsp+3A0h+var_340], eax
0x180003148  test    eax, eax
0x18000314a  mov     eax, 140h
0x18000314f  js      short loc_1800031BD
0x180003151  mov     [rsp+3A0h+var_33C], ax
0x180003156  lea     rdx, [rbp+2A0h+FindFileData]; lpFindFileData
0x18000315a  mov     rcx, rdi; hFindFile
0x18000315d  call    cs:__imp_FindNextFileW
0x180003163  mov     esi, eax
0x180003165  test    eax, eax
0x180003167  jnz     short loc_180003182
0x180003169  call    cs:__imp_GetLastError
0x18000316f  cmp     eax, 12h
0x180003172  jnz     short loc_1800031D0
0x180003174  mov     eax, 147h
0x180003179  mov     [rsp+3A0h+var_340], esi
0x18000317d  mov     [rsp+3A0h+var_33C], ax
0x180003182  lea     rcx, [rbp+2A0h+lpsz]; this
0x180003186  call    ?_Release@CBsString@@AEAAXXZ
0x18000318b  test    esi, esi
0x18000318d  jnz     loc_18000307D
0x180003193  xor     r13d, r13d
0x180003196  mov     eax, [rbx+10h]
0x180003199  mov     [r12], eax
0x18000319d  mov     rax, [rbx+8]
0x1800031a1  mov     [rbx+8], r13
0x1800031a5  mov     qword ptr [rbx+10h], 0
0x1800031ad  mov     [r15], rax
0x1800031b0  jmp     loc_1800032C5
0x1800031b5  mov     [rsp+3A0h+var_340], 80070057h
0x1800031bd  mov     [rsp+3A0h+var_33A], ax
0x1800031c2  lea     rcx, [rbp+2A0h+lpsz]; this
0x1800031c6  call    ?_Release@CBsString@@AEAAXXZ
0x1800031cb  jmp     loc_1800032C5
0x1800031d0  call    GetLastFailureAsHRESULT
0x1800031d5  mov     ecx, 147h
0x1800031da  mov     [rsp+3A0h+var_340], eax
0x1800031de  mov     [rsp+3A0h+var_33A], cx
0x1800031e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031ea  lea     rdx, WPP_GLOBAL_Control
0x1800031f1  cmp     rcx, rdx
0x1800031f4  jz      short loc_1800031C2
0x1800031f6  test    dword ptr [rcx+1Ch], 2000000h
0x1800031fd  jz      short loc_1800031C2
0x1800031ff  mov     rcx, [rcx+10h]
0x180003203  lea     r9, aGetlasterrorEr
0x18000320a  mov     dword ptr [rsp+3A0h+var_378], eax
0x18000320e  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x180003215  mov     edx, 16h
0x18000321a  mov     [rsp+3A0h+var_380], r14
0x18000321f  call    WPP_SF_sSd
0x180003224  jmp     short loc_1800031C2
0x180003226  call    cs:__imp_GetLastError
0x18000322c  cmp     eax, 2
0x18000322f  jz      short loc_180003292
0x180003231  call    cs:__imp_GetLastError
0x180003237  cmp     eax, 3
0x18000323a  jz      short loc_180003292
0x18000323c  call    GetLastFailureAsHRESULT
0x180003241  mov     ecx, 127h
0x180003246  mov     [rsp+3A0h+var_340], eax
0x18000324a  mov     [rsp+3A0h+var_33A], cx
0x18000324f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003256  lea     rdx, WPP_GLOBAL_Control
0x18000325d  cmp     rcx, rdx
0x180003260  jz      short loc_1800032C5
0x180003262  test    dword ptr [rcx+1Ch], 2000000h
0x180003269  jz      short loc_1800032C5
0x18000326b  mov     rcx, [rcx+10h]
0x18000326f  lea     r9, aGetlasterrorEr_0
0x180003276  mov     dword ptr [rsp+3A0h+var_378], eax
0x18000327a  lea     r8, WPP_e3138bf60ab3339e968ece0eb19ed757_Traceguids
0x180003281  mov     edx, 15h
0x180003286  mov     [rsp+3A0h+var_380], r14
0x18000328b  call    WPP_SF_sSd
0x180003290  jmp     short loc_1800032C5
0x180003292  mov     ecx, 127h
0x180003297  mov     [rsp+3A0h+var_340], r13d
0x18000329c  mov     [rsp+3A0h+var_33C], cx
0x1800032a1  jmp     loc_180003196
0x1800032a6  mov     rbx, r13
0x1800032a9  mov     [rsp+3A0h+var_340], 8007000Eh
0x1800032b1  mov     eax, 11Bh
0x1800032b6  jmp     short loc_1800032C0
0x1800032b8  mov     [rsp+3A0h+var_340], 80070057h
0x1800032c0  mov     [rsp+3A0h+var_33A], ax
0x1800032c5  mov     esi, [rsp+3A0h+var_340]
0x1800032c9  lea     rcx, [rbp+2A0h+var_2F0]; this
0x1800032cd  call    ?_Release@CBsString@@AEAAXXZ
0x1800032d2  lea     rcx, [rbp+2A0h+var_2E0]; this
0x1800032d6  call    ?_Release@CBsString@@AEAAXXZ
0x1800032db  test    rbx, rbx
0x1800032de  jz      short loc_1800032FC
0x1800032e0  or      eax, 0FFFFFFFFh
0x1800032e3  lock xadd [rbx], eax
0x1800032e7  cmp     eax, 1
0x1800032ea  jnz     short loc_1800032FC
0x1800032ec  mov     rcx, rbx
0x1800032ef  call    ??1?$CSxSimpleArray@U_GUID@@@@AEAA@XZ
0x1800032f4  mov     rcx, rbx; Block
0x1800032f7  call    ??3@YAXPEAX@Z
0x1800032fc  lea     rcx, [rbp+2A0h+lpFileName]; this
0x180003300  call    ?_Release@CBsString@@AEAAXXZ
0x180003305  lea     rcx, [rbp+2A0h+var_2C0]; this
0x180003309  call    ?_Release@CBsString@@AEAAXXZ
0x18000330e  lea     rcx, [rdi-1]
0x180003312  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180003316  ja      short loc_180003321
0x180003318  mov     rcx, rdi; hFindFile
0x18000331b  call    cs:__imp_FindClose
0x180003321  lea     rcx, [rsp+3A0h+var_340]; this
0x180003326  call    ??1CSxFunctionTracer@@QEAA@XZ
0x18000332b  mov     eax, esi
0x18000332d  mov     rcx, [rbp+2A0h+var_40]
0x180003334  xor     rcx, rsp; StackCookie
0x180003337  call    __security_check_cookie
0x18000333c  mov     rbx, [rsp+3A0h+arg_18]
0x180003344  add     rsp, 370h
0x18000334b  pop     r15
0x18000334d  pop     r14
0x18000334f  pop     r13
0x180003351  pop     r12
0x180003353  pop     rdi
0x180003354  pop     rsi
0x180003355  pop     rbp
0x180003356  retn
```
