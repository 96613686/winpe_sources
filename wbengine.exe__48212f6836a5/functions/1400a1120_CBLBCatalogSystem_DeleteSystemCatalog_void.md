# CBLBCatalogSystem::DeleteSystemCatalog(void)

- ea: `0x1400a1120`
- end: `0x1400a15fa`
- name: `?DeleteSystemCatalog@CBLBCatalogSystem@@UEAAJXZ`
- size: `1242`
- prototype: `__int64 __fastcall(CBLBCatalogSystem *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x1400063b4`
- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014260`
- `0x140051e98`
- `0x1400a0914`
- `0x1400a1120`
- `0x1400a2e90`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x1400a11c4`
- `KERNEL32!GetSystemDirectoryW` at `0x1400a11c4`
- `KERNEL32!DeleteFileW` at `0x1400a143d`
- `KERNEL32!DeleteFileW` at `0x1400a1517`
- `KERNEL32!DeleteFileW` at `0x1400a143d`
- `KERNEL32!DeleteFileW` at `0x1400a1517`
- `KERNEL32!GetFileAttributesW` at `0x1400a1381`
- `KERNEL32!GetFileAttributesW` at `0x1400a1381`
- `KERNEL32!GetLastError` at `0x1400a11ce`
- `KERNEL32!GetLastError` at `0x1400a123a`
- `KERNEL32!GetLastError` at `0x1400a138c`
- `KERNEL32!GetLastError` at `0x1400a1447`
- `KERNEL32!GetLastError` at `0x1400a1495`
- `KERNEL32!GetLastError` at `0x1400a1521`
- `KERNEL32!GetLastError` at `0x1400a11ce`
- `KERNEL32!GetLastError` at `0x1400a123a`
- `KERNEL32!GetLastError` at `0x1400a138c`
- `KERNEL32!GetLastError` at `0x1400a1447`
- `KERNEL32!GetLastError` at `0x1400a1495`
- `KERNEL32!GetLastError` at `0x1400a1521`
- `KERNEL32!EnterCriticalSection` at `0x1400a142b`
- `KERNEL32!EnterCriticalSection` at `0x1400a142b`
- `KERNEL32!GetVolumePathNameW` at `0x1400a1230`
- `KERNEL32!GetVolumePathNameW` at `0x1400a1230`

## string_xrefs

- `0x1400a12a8`: `wcslen(wszCatalogDir) + wcslen(x_wszSVIDirectoryName) < MAX_PATH`
- `0x1400a12ea`: `wcslen(wszCatalogDir) + wcslen(x_wszApplicationName) + 1 < MAX_PATH`
- `0x1400a1340`: `wcslen(wszCatalogDir) + wcslen(x_wszBLB_CATALOG) + 1 < MAX_PATH`
- `0x1400a13e1`: `wcslen(wszPathBackupCatalog) + wcslen(x_wszBackupGlobalCatalogName) + 1 < MAX_PATH`
- `0x1400a14d0`: `wcslen(wszPathOrgCatalog) + wcslen(x_wszGlobalCatalogName) + 1 < MAX_PATH`

## pseudocode

```c
__int64 __fastcall CBLBCatalogSystem::DeleteSystemCatalog(CBLBCatalogSystem *this)
{
  signed int LastError; // ebx
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  signed int v7; // eax
  __int64 v8; // rax
  DWORD v9; // eax
  __int64 v10; // r8
  _QWORD *v11; // rcx
  int v12; // edx
  WCHAR *v13; // r9
  __int64 v14; // rdx
  DWORD v15; // eax
  _QWORD v17[2]; // [rsp+30h] [rbp-D0h] BYREF
  char v18; // [rsp+40h] [rbp-C0h]
  WCHAR szVolumePathName[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR v21[264]; // [rsp+470h] [rbp+370h] BYREF
  WCHAR Buffer[264]; // [rsp+680h] [rbp+580h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(szVolumePathName, 0, 0x208u);
  memset_0(v21, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  v17[1] = this;
  v17[0] = &CBlbObjectLock<CBLBCatalogSystem>::`vftable';
  v18 = 0;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_d041e7adef8233277ea9793acb2161c7_Traceguids);
    }
    goto LABEL_6;
  }
  if ( GetVolumePathNameW(Buffer, szVolumePathName, 0x104u) )
  {
    v3 = -1;
    v4 = -1;
    do
      ++v4;
    while ( szVolumePathName[v4] );
    if ( (unsigned __int64)(v4 + 25) >= 0x104 )
      BlbAssert(
        "base\\stor\\blb\\catalog\\catsys.cpp",
        0x6D0u,
        "wcslen(wszCatalogDir) + wcslen(x_wszSVIDirectoryName) < MAX_PATH");
    StringCchCatW(szVolumePathName, 260, L"System Volume Information");
    v5 = -1;
    do
      ++v5;
    while ( szVolumePathName[v5] );
    if ( (unsigned __int64)(v5 + 19) >= 0x104 )
      BlbAssert(
        "base\\stor\\blb\\catalog\\catsys.cpp",
        0x6D7u,
        "wcslen(wszCatalogDir) + wcslen(x_wszApplicationName) + 1 < MAX_PATH");
    StringCchCatW(szVolumePathName, 260, L"\\");
    StringCchCatW(szVolumePathName, 260, L"WindowsImageBackup");
    v6 = -1;
    do
      ++v6;
    while ( szVolumePathName[v6] );
    if ( (unsigned __int64)(v6 + 8) >= 0x104 )
      BlbAssert(
        "base\\stor\\blb\\catalog\\catsys.cpp",
        0x6DBu,
        "wcslen(wszCatalogDir) + wcslen(x_wszBLB_CATALOG) + 1 < MAX_PATH");
    StringCchCatW(szVolumePathName, 260, L"\\");
    StringCchCatW(szVolumePathName, 260, L"Catalog");
    if ( GetFileAttributesW(szVolumePathName) == -1 )
    {
      v7 = GetLastError();
      LastError = v7;
      if ( v7 == 2 )
      {
        LastError = 0;
        goto LABEL_59;
      }
      goto LABEL_29;
    }
    StringCchCopyW(FileName, 0x104u, szVolumePathName);
    v8 = -1;
    do
      ++v8;
    while ( FileName[v8] );
    if ( (unsigned __int64)(v8 + 20) >= 0x104 )
      BlbAssert(
        "base\\stor\\blb\\catalog\\catsys.cpp",
        0x6F2u,
        "wcslen(wszPathBackupCatalog) + wcslen(x_wszBackupGlobalCatalogName) + 1 < MAX_PATH");
    StringCchCatW(FileName, 259, L"\\");
    StringCchCatW(FileName, 259, L"BackupGlobalCatalog");
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v18 = 1;
    if ( DeleteFileW(FileName) || (v9 = GetLastError(), LOBYTE(v10) = v9, v9 == 2) )
    {
      StringCchCopyW(v21, 0x104u, szVolumePathName);
      do
        ++v3;
      while ( v21[v3] );
      if ( (unsigned __int64)(v3 + 14) >= 0x104 )
        BlbAssert(
          "base\\stor\\blb\\catalog\\catsys.cpp",
          0x70Au,
          "wcslen(wszPathOrgCatalog) + wcslen(x_wszGlobalCatalogName) + 1 < MAX_PATH");
      StringCchCatW(v21, 259, L"\\");
      StringCchCatW(v21, 259, L"GlobalCatalog");
      if ( DeleteFileW(v21) || (v15 = GetLastError(), v10 = v15, v15 == 2) )
      {
        LastError = (*(__int64 (__fastcall **)(CBLBCatalogSystem *, __int64, __int64))(*(_QWORD *)this + 152LL))(
                      this,
                      v14,
                      v10);
        if ( LastError >= 0 )
        {
          CBlbObjectLock<CBLBCatalogSystem>::ReleaseLock(v17);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_d041e7adef8233277ea9793acb2161c7_Traceguids);
        }
        goto LABEL_59;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_42;
      }
      v12 = 68;
      v13 = v21;
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_42;
      }
      v12 = 67;
      v13 = FileName;
    }
    WPP_SF_Sd(v11[2], v12, (unsigned int)&WPP_d041e7adef8233277ea9793acb2161c7_Traceguids, (_DWORD)v13, v10);
LABEL_42:
    v7 = GetLastError();
    LastError = v7;
LABEL_29:
    if ( v7 <= 0 )
      goto LABEL_59;
    LastError = (unsigned __int16)v7;
    goto LABEL_8;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      66,
      (unsigned int)&WPP_d041e7adef8233277ea9793acb2161c7_Traceguids,
      (unsigned int)Buffer,
      LastError);
  }
LABEL_6:
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError;
LABEL_8:
    LastError |= 0x80070000;
  }
LABEL_59:
  CBlbObjectLock<CBLBCatalogSystem>::~CBlbObjectLock<CBLBCatalogSystem>(v17);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1400a1120  mov     [rsp-8+arg_8], rbx
0x1400a1125  mov     [rsp-8+arg_10], rsi
0x1400a112a  push    rbp
0x1400a112b  push    rdi
0x1400a112c  push    r12
0x1400a112e  push    r14
0x1400a1130  push    r15
0x1400a1132  lea     rbp, [rsp-7A0h]
0x1400a113a  sub     rsp, 8A0h
0x1400a1141  mov     rax, cs:__security_cookie
0x1400a1148  xor     rax, rsp
0x1400a114b  mov     [rbp+7C0h+var_30], rax
0x1400a1152  mov     rdi, rcx
0x1400a1155  mov     ebx, 208h
0x1400a115a  mov     r8d, ebx; Size
0x1400a115d  lea     rcx, [rbp+7C0h+Buffer]; void *
0x1400a1164  xor     edx, edx; Val
0x1400a1166  call    memset_0
0x1400a116b  mov     r8d, ebx; Size
0x1400a116e  lea     rcx, [rsp+8C0h+szVolumePathName]; void *
0x1400a1173  xor     edx, edx; Val
0x1400a1175  call    memset_0
0x1400a117a  mov     r8d, ebx; Size
0x1400a117d  lea     rcx, [rbp+7C0h+var_450]; void *
0x1400a1184  xor     edx, edx; Val
0x1400a1186  call    memset_0
0x1400a118b  mov     r8d, ebx; Size
0x1400a118e  lea     rcx, [rbp+7C0h+FileName]; void *
0x1400a1195  xor     edx, edx; Val
0x1400a1197  call    memset_0
0x1400a119c  lea     rax, ??_7?$CBlbObjectLock@VCBLBCatalogSystem@@@@6B@; const CBlbObjectLock<CBLBCatalogSystem>::`vftable'
0x1400a11a3  mov     [rsp+8C0h+var_888], rdi
0x1400a11a8  mov     r14d, 104h
0x1400a11ae  mov     [rsp+8C0h+var_890], rax
0x1400a11b3  xor     esi, esi
0x1400a11b5  lea     rcx, [rbp+7C0h+Buffer]; lpBuffer
0x1400a11bc  mov     edx, r14d; uSize
0x1400a11bf  mov     [rsp+8C0h+var_880], sil
0x1400a11c4  call    cs:__imp_GetSystemDirectoryW
0x1400a11ca  test    eax, eax
0x1400a11cc  jnz     short loc_1400A1221
0x1400a11ce  call    cs:__imp_GetLastError
0x1400a11d4  mov     ebx, eax
0x1400a11d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a11dd  lea     rax, WPP_GLOBAL_Control
0x1400a11e4  cmp     rcx, rax
0x1400a11e7  jz      short loc_1400A120B
0x1400a11e9  test    byte ptr [rcx+1Ch], 2
0x1400a11ed  jz      short loc_1400A120B
0x1400a11ef  cmp     byte ptr [rcx+19h], 2
0x1400a11f3  jb      short loc_1400A120B
0x1400a11f5  mov     rcx, [rcx+10h]
0x1400a11f9  lea     edx, [rsi+41h]
0x1400a11fc  mov     r9d, ebx
0x1400a11ff  lea     r8, WPP_d041e7adef8233277ea9793acb2161c7_Traceguids
0x1400a1206  call    WPP_SF_d
0x1400a120b  test    ebx, ebx
0x1400a120d  jle     loc_1400A15C3
0x1400a1213  movzx   ebx, bx
0x1400a1216  or      ebx, 80070000h
0x1400a121c  jmp     loc_1400A15C3
0x1400a1221  mov     r8d, r14d; cchBufferLength
0x1400a1224  lea     rdx, [rsp+8C0h+szVolumePathName]; lpszVolumePathName
0x1400a1229  lea     rcx, [rbp+7C0h+Buffer]; lpszFileName
0x1400a1230  call    cs:__imp_GetVolumePathNameW
0x1400a1236  test    eax, eax
0x1400a1238  jnz     short loc_1400A1283
0x1400a123a  call    cs:__imp_GetLastError
0x1400a1240  mov     ebx, eax
0x1400a1242  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1249  lea     rax, WPP_GLOBAL_Control
0x1400a1250  cmp     rcx, rax
0x1400a1253  jz      short loc_1400A120B
0x1400a1255  test    byte ptr [rcx+1Ch], 2
0x1400a1259  jz      short loc_1400A120B
0x1400a125b  cmp     byte ptr [rcx+19h], 2
0x1400a125f  jb      short loc_1400A120B
0x1400a1261  mov     rcx, [rcx+10h]
0x1400a1265  lea     r9, [rbp+7C0h+Buffer]
0x1400a126c  mov     edx, 42h ; 'B'
0x1400a1271  mov     [rsp+8C0h+var_8A0], ebx
0x1400a1275  lea     r8, WPP_d041e7adef8233277ea9793acb2161c7_Traceguids
0x1400a127c  call    WPP_SF_Sd
0x1400a1281  jmp     short loc_1400A120B
0x1400a1283  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400a1287  lea     rcx, [rsp+8C0h+szVolumePathName]
0x1400a128c  mov     rax, rbx
0x1400a128f  inc     rax
0x1400a1292  cmp     [rcx+rax*2], si
0x1400a1296  jnz     short loc_1400A128F
0x1400a1298  add     rax, 19h
0x1400a129c  lea     r15, aBaseStorBlbCat_10; "base\\stor\\blb\\catalog\\catsys.cpp"
0x1400a12a3  cmp     rax, r14
0x1400a12a6  jb      short loc_1400A12BC
0x1400a12a8  lea     r8, aWcslenWszcatal; "wcslen(wszCatalogDir) + wcslen(x_wszSVI"...
0x1400a12af  mov     edx, 6D0h; unsigned int
0x1400a12b4  mov     rcx, r15; char *
0x1400a12b7  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400a12bc  lea     r8, aSystemVolumeIn_0; "System Volume Information"
0x1400a12c3  mov     rdx, r14; unsigned __int64
0x1400a12c6  lea     rcx, [rsp+8C0h+szVolumePathName]; unsigned __int16 *
0x1400a12cb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400a12d0  lea     rcx, [rsp+8C0h+szVolumePathName]
0x1400a12d5  mov     rax, rbx
0x1400a12d8  inc     rax
0x1400a12db  cmp     [rcx+rax*2], si
0x1400a12df  jnz     short loc_1400A12D8
0x1400a12e1  add     rax, 13h
0x1400a12e5  cmp     rax, r14
0x1400a12e8  jb      short loc_1400A12FE
0x1400a12ea  lea     r8, aWcslenWszcatal_1; "wcslen(wszCatalogDir) + wcslen(x_wszApp"...
0x1400a12f1  mov     edx, 6D7h; unsigned int
0x1400a12f6  mov     rcx, r15; char *
0x1400a12f9  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400a12fe  lea     r8, asc_14013C090; "\\"
0x1400a1305  mov     rdx, r14; unsigned __int64
0x1400a1308  lea     rcx, [rsp+8C0h+szVolumePathName]; unsigned __int16 *
0x1400a130d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400a1312  lea     r8, aWindowsimageba_0; "WindowsImageBackup"
0x1400a1319  mov     rdx, r14; unsigned __int64
0x1400a131c  lea     rcx, [rsp+8C0h+szVolumePathName]; unsigned __int16 *
0x1400a1321  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400a1326  lea     rcx, [rsp+8C0h+szVolumePathName]
0x1400a132b  mov     rax, rbx
0x1400a132e  inc     rax
0x1400a1331  cmp     [rcx+rax*2], si
0x1400a1335  jnz     short loc_1400A132E
0x1400a1337  add     rax, 8
0x1400a133b  cmp     rax, r14
0x1400a133e  jb      short loc_1400A1354
0x1400a1340  lea     r8, aWcslenWszcatal_0; "wcslen(wszCatalogDir) + wcslen(x_wszBLB"...
0x1400a1347  mov     edx, 6DBh; unsigned int
0x1400a134c  mov     rcx, r15; char *
0x1400a134f  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400a1354  lea     r8, asc_14013C090; "\\"
0x1400a135b  mov     rdx, r14; unsigned __int64
0x1400a135e  lea     rcx, [rsp+8C0h+szVolumePathName]; unsigned __int16 *
0x1400a1363  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400a1368  lea     r8, aCatalog; "Catalog"
0x1400a136f  mov     rdx, r14; unsigned __int64
0x1400a1372  lea     rcx, [rsp+8C0h+szVolumePathName]; unsigned __int16 *
0x1400a1377  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400a137c  lea     rcx, [rsp+8C0h+szVolumePathName]; lpFileName
0x1400a1381  call    cs:__imp_GetFileAttributesW
0x1400a1387  cmp     eax, 0FFFFFFFFh
0x1400a138a  jnz     short loc_1400A13B0
0x1400a138c  call    cs:__imp_GetLastError
0x1400a1392  mov     ebx, eax
0x1400a1394  cmp     eax, 2
0x1400a1397  jnz     short loc_1400A13A0
0x1400a1399  mov     ebx, esi
0x1400a139b  jmp     loc_1400A15C3
0x1400a13a0  test    eax, eax
0x1400a13a2  jle     loc_1400A15C3
0x1400a13a8  movzx   ebx, ax
0x1400a13ab  jmp     loc_1400A1216
0x1400a13b0  lea     r8, [rsp+8C0h+szVolumePathName]; unsigned __int16 *
0x1400a13b5  mov     rdx, r14; unsigned __int64
0x1400a13b8  lea     rcx, [rbp+7C0h+FileName]; unsigned __int16 *
0x1400a13bf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400a13c4  mov     rax, rbx
0x1400a13c7  lea     r11, [rbp+7C0h+FileName]
0x1400a13ce  inc     rax
0x1400a13d1  cmp     [r11+rax*2], si
0x1400a13d6  jnz     short loc_1400A13CE
0x1400a13d8  add     rax, 14h
0x1400a13dc  cmp     rax, r14
0x1400a13df  jb      short loc_1400A13F5
0x1400a13e1  lea     r8, aWcslenWszpathb_0; "wcslen(wszPathBackupCatalog) + wcslen(x"...
0x1400a13e8  mov     edx, 6F2h; unsigned int
0x1400a13ed  mov     rcx, r15; char *
0x1400a13f0  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400a13f5  mov     r12d, 103h
0x1400a13fb  lea     r8, asc_14013C090; "\\"
0x1400a1402  mov     edx, r12d; unsigned __int64
0x1400a1405  lea     rcx, [rbp+7C0h+FileName]; unsigned __int16 *
0x1400a140c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400a1411  lea     r8, aBackupglobalca; "BackupGlobalCatalog"
0x1400a1418  mov     edx, r12d; unsigned __int64
0x1400a141b  lea     rcx, [rbp+7C0h+FileName]; unsigned __int16 *
0x1400a1422  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400a1427  lea     rcx, [rdi+10h]; lpCriticalSection
0x1400a142b  call    cs:__imp_EnterCriticalSection
0x1400a1431  lea     rcx, [rbp+7C0h+FileName]; lpFileName
0x1400a1438  mov     [rsp+8C0h+var_880], 1
0x1400a143d  call    cs:__imp_DeleteFileW
0x1400a1443  test    eax, eax
0x1400a1445  jnz     short loc_1400A14A2
0x1400a1447  call    cs:__imp_GetLastError
0x1400a144d  mov     r8d, eax
0x1400a1450  cmp     eax, 2
0x1400a1453  jz      short loc_1400A14A2
0x1400a1455  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a145c  lea     rax, WPP_GLOBAL_Control
0x1400a1463  cmp     rcx, rax
0x1400a1466  jz      short loc_1400A1495
0x1400a1468  test    byte ptr [rcx+1Ch], 2
0x1400a146c  jz      short loc_1400A1495
0x1400a146e  cmp     byte ptr [rcx+19h], 2
0x1400a1472  jb      short loc_1400A1495
0x1400a1474  mov     edx, 43h ; 'C'
0x1400a1479  lea     r9, [rbp+7C0h+FileName]
0x1400a1480  mov     rcx, [rcx+10h]
0x1400a1484  mov     [rsp+8C0h+var_8A0], r8d
0x1400a1489  lea     r8, WPP_d041e7adef8233277ea9793acb2161c7_Traceguids
0x1400a1490  call    WPP_SF_Sd
0x1400a1495  call    cs:__imp_GetLastError
0x1400a149b  mov     ebx, eax
0x1400a149d  jmp     loc_1400A13A0
0x1400a14a2  lea     r8, [rsp+8C0h+szVolumePathName]; unsigned __int16 *
0x1400a14a7  mov     rdx, r14; unsigned __int64
0x1400a14aa  lea     rcx, [rbp+7C0h+var_450]; unsigned __int16 *
0x1400a14b1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400a14b6  lea     r11, [rbp+7C0h+var_450]
0x1400a14bd  inc     rbx
0x1400a14c0  cmp     [r11+rbx*2], si
0x1400a14c5  jnz     short loc_1400A14BD
0x1400a14c7  lea     rax, [rbx+0Eh]
0x1400a14cb  cmp     rax, r14
0x1400a14ce  jb      short loc_1400A14E4
0x1400a14d0  lea     r8, aWcslenWszpatho_0; "wcslen(wszPathOrgCatalog) + wcslen(x_ws"...
0x1400a14d7  mov     edx, 70Ah; unsigned int
0x1400a14dc  mov     rcx, r15; char *
0x1400a14df  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400a14e4  lea     r8, asc_14013C090; "\\"
0x1400a14eb  mov     rdx, r12; unsigned __int64
0x1400a14ee  lea     rcx, [rbp+7C0h+var_450]; unsigned __int16 *
0x1400a14f5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400a14fa  lea     r8, aGlobalcatalog; "GlobalCatalog"
0x1400a1501  mov     rdx, r12; unsigned __int64
0x1400a1504  lea     rcx, [rbp+7C0h+var_450]; unsigned __int16 *
0x1400a150b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400a1510  lea     rcx, [rbp+7C0h+var_450]; lpFileName
0x1400a1517  call    cs:__imp_DeleteFileW
0x1400a151d  test    eax, eax
0x1400a151f  jnz     short loc_1400A156B
0x1400a1521  call    cs:__imp_GetLastError
0x1400a1527  mov     r8d, eax
0x1400a152a  cmp     eax, 2
0x1400a152d  jz      short loc_1400A156B
0x1400a152f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1536  lea     rax, WPP_GLOBAL_Control
0x1400a153d  cmp     rcx, rax
0x1400a1540  jz      loc_1400A1495
0x1400a1546  test    byte ptr [rcx+1Ch], 2
0x1400a154a  jz      loc_1400A1495
0x1400a1550  cmp     byte ptr [rcx+19h], 2
0x1400a1554  jb      loc_1400A1495
0x1400a155a  mov     edx, 44h ; 'D'
0x1400a155f  lea     r9, [rbp+7C0h+var_450]
0x1400a1566  jmp     loc_1400A1480
0x1400a156b  mov     rax, [rdi]
0x1400a156e  mov     rcx, rdi
0x1400a1571  mov     rax, [rax+98h]
0x1400a1578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a157d  mov     ebx, eax
0x1400a157f  test    eax, eax
0x1400a1581  jns     short loc_1400A15B9
0x1400a1583  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a158a  lea     rax, WPP_GLOBAL_Control
0x1400a1591  cmp     rcx, rax
0x1400a1594  jz      short loc_1400A15C3
0x1400a1596  test    byte ptr [rcx+1Ch], 2
0x1400a159a  jz      short loc_1400A15C3
0x1400a159c  cmp     byte ptr [rcx+19h], 2
0x1400a15a0  jb      short loc_1400A15C3
0x1400a15a2  mov     rcx, [rcx+10h]
0x1400a15a6  lea     r8, WPP_d041e7adef8233277ea9793acb2161c7_Traceguids
0x1400a15ad  mov     edx, 45h ; 'E'
0x1400a15b2  call    WPP_SF_
0x1400a15b7  jmp     short loc_1400A15C3
0x1400a15b9  lea     rcx, [rsp+8C0h+var_890]
0x1400a15be  call    ?ReleaseLock@?$CBlbObjectLock@VCBLBCatalogSystem@@@@UEAAXXZ; CBlbObjectLock<CBLBCatalogSystem>::ReleaseLock(void)
0x1400a15c3  lea     rcx, [rsp+8C0h+var_890]
0x1400a15c8  call    ??1?$CBlbObjectLock@VCBLBCatalogSystem@@@@UEAA@XZ; CBlbObjectLock<CBLBCatalogSystem>::~CBlbObjectLock<CBLBCatalogSystem>(void)
0x1400a15cd  mov     eax, ebx
0x1400a15cf  mov     rcx, [rbp+7C0h+var_30]
0x1400a15d6  xor     rcx, rsp; StackCookie
0x1400a15d9  call    __security_check_cookie
0x1400a15de  lea     r11, [rsp+8C0h+var_20]
0x1400a15e6  mov     rbx, [r11+38h]
0x1400a15ea  mov     rsi, [r11+40h]
0x1400a15ee  mov     rsp, r11
0x1400a15f1  pop     r15
0x1400a15f3  pop     r14
0x1400a15f5  pop     r12
0x1400a15f7  pop     rdi
0x1400a15f8  pop     rbp
0x1400a15f9  retn
```
