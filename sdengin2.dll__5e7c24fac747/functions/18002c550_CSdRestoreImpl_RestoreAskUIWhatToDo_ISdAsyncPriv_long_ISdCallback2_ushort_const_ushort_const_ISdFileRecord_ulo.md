# CSdRestoreImpl::_RestoreAskUIWhatToDo(ISdAsyncPriv *,long,ISdCallback2 *,ushort const *,ushort const *,ISdFileRecord *,ulong,CBsString *,ulong *)

- ea: `0x18002c550`
- end: `0x18002cea2`
- name: `?_RestoreAskUIWhatToDo@CSdRestoreImpl@@AEAAJPEAUISdAsyncPriv@@JPEAUISdCallback2@@PEBG2PEAUISdFileRecord@@KPEAVCBsString@@PEAK@Z`
- size: `2386`
- prototype: `__int64 __fastcall(CSdRestoreImpl *__hidden this, struct ISdAsyncPriv *, int, struct ISdCallback2 *, const unsigned __int16 *, const unsigned __int16 *, struct ISdFileRecord *, unsigned int, struct CBsString *, unsigned int *)`
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, service_task`

## callers

- `0x18002d470`
- `0x18002f208`
- `0x18002fc60`
- `0x1800302bc`

## callees

- `0x1800081d8`
- `0x180008200`
- `0x180009a98`
- `0x180014394`
- `0x18002c550`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180086b74`
- `0x180099484`
- `0x180099bdc`
- `0x18009a08c`
- `0x18009a22c`
- `0x18009a24c`
- `0x18009ae34`
- `0x1800c97ce`
- `0x1800c97da`
- `0x1800c9830`
- `0x1800cb010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18002c9c9`
- `KERNEL32!CreateFileW` at `0x18002c9c9`
- `KERNEL32!GetLastError` at `0x18002cb45`
- `KERNEL32!GetLastError` at `0x18002cb45`
- `KERNEL32!CloseHandle` at `0x18002ca84`
- `KERNEL32!CloseHandle` at `0x18002ce66`
- `KERNEL32!CloseHandle` at `0x18002ca84`
- `KERNEL32!CloseHandle` at `0x18002ce66`
- `KERNEL32!FindFirstFileW` at `0x18002cac8`
- `KERNEL32!FindFirstFileW` at `0x18002cac8`
- `KERNEL32!FindClose` at `0x18002ce53`
- `KERNEL32!FindClose` at `0x18002ce53`
- `KERNEL32!GetFileType` at `0x18002c9e9`
- `KERNEL32!GetFileType` at `0x18002c9e9`
- `KERNEL32!GetFileInformationByHandle` at `0x18002ca02`
- `KERNEL32!GetFileInformationByHandle` at `0x18002ca02`
- `ole32!CoTaskMemFree` at `0x18002ce14`
- `ole32!CoTaskMemFree` at `0x18002ce14`

## pseudocode

```c
__int64 __fastcall CSdRestoreImpl::_RestoreAskUIWhatToDo(
        CSdRestoreImpl *this,
        struct ISdAsyncPriv *a2,
        int a3,
        struct ISdCallback2 *a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6,
        struct ISdFileRecord *a7,
        unsigned int a8,
        struct CBsString *a9,
        unsigned int *a10)
{
  __int64 v11; // rbx
  __int64 FirstFileW; // rdi
  __int16 v13; // ax
  int v14; // eax
  int v15; // esi
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // r15
  _WORD *v19; // r13
  DWORD dwFlagsAndAttributes; // esi
  HANDLE FileW; // rax
  int v22; // esi
  DWORD LastError; // eax
  PVOID *v24; // rcx
  int v25; // r14d
  const unsigned __int16 *v26; // rsi
  unsigned int v27; // r15d
  struct ISdCallback2 *v28; // r12
  const unsigned __int16 *v29; // r13
  int v30; // eax
  unsigned int v31; // r8d
  int valid; // eax
  unsigned int v33; // esi
  int v35; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v36; // [rsp+54h] [rbp-ACh]
  __int16 v37; // [rsp+56h] [rbp-AAh]
  int v38; // [rsp+88h] [rbp-78h]
  unsigned int v39; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v40; // [rsp+90h] [rbp-70h]
  LPVOID pv; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v42; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-58h]
  LPCWSTR lpFileName[2]; // [rsp+B0h] [rbp-50h] BYREF
  void *v45; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v46; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v47[2]; // [rsp+D0h] [rbp-30h] BYREF
  const unsigned __int16 *v48; // [rsp+E0h] [rbp-20h]
  struct ISdAsyncPriv *v49; // [rsp+E8h] [rbp-18h]
  CSdRestoreImpl *v50; // [rsp+F0h] [rbp-10h]
  struct ISdCallback2 *v51; // [rsp+F8h] [rbp-8h]
  CBsString *v52; // [rsp+100h] [rbp+0h]
  unsigned int *v53; // [rsp+108h] [rbp+8h]
  unsigned __int16 *v54; // [rsp+110h] [rbp+10h] BYREF
  _WORD *v55; // [rsp+118h] [rbp+18h]
  __int16 v56; // [rsp+120h] [rbp+20h]
  __int64 v57; // [rsp+140h] [rbp+40h]
  int v58; // [rsp+148h] [rbp+48h]
  FILETIME ftCreationTime; // [rsp+150h] [rbp+50h]
  FILETIME ftLastWriteTime; // [rsp+158h] [rbp+58h]
  FILETIME ftLastAccessTime; // [rsp+160h] [rbp+60h]
  __int64 v62; // [rsp+168h] [rbp+68h]
  unsigned __int64 v63; // [rsp+170h] [rbp+70h]
  unsigned __int64 v64; // [rsp+178h] [rbp+78h]
  DWORD dwFileAttributes; // [rsp+180h] [rbp+80h]
  __int64 v66; // [rsp+184h] [rbp+84h]
  unsigned __int16 *v67; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 *v68; // [rsp+198h] [rbp+98h] BYREF
  __int16 v69; // [rsp+1A0h] [rbp+A0h]
  __int64 v70; // [rsp+1C0h] [rbp+C0h]
  int v71; // [rsp+1C8h] [rbp+C8h]
  char v72[8]; // [rsp+1D0h] [rbp+D0h] BYREF
  char v73[8]; // [rsp+1D8h] [rbp+D8h] BYREF
  char v74[8]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v75; // [rsp+1E8h] [rbp+E8h]
  char v76[8]; // [rsp+1F0h] [rbp+F0h] BYREF
  char v77[8]; // [rsp+1F8h] [rbp+F8h] BYREF
  char v78[4]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v79; // [rsp+204h] [rbp+104h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+210h] [rbp+110h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+250h] [rbp+150h] BYREF

  v51 = a4;
  v38 = a3;
  v49 = a2;
  v50 = this;
  v48 = a6;
  v40 = a8;
  v52 = a9;
  v53 = a10;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v35, "CSdRestoreImpl::_RestoreAskUIWhatToDo", 1904, 1);
  v39 = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  memset_0(&v54, 0, 0x80u);
  memset_0(&v67, 0, 0x80u);
  v11 = -1;
  pv = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = -1;
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  lpFileName[1] = 0;
  v47[0] = (unsigned __int16 *)qword_1800E8530;
  v47[1] = 0;
  v42 = (unsigned __int16 *)qword_1800E8530;
  v43 = 0;
  v45 = qword_1800E8530;
  v46 = 0;
  v13 = 1925;
  if ( !v49 )
    goto LABEL_83;
  v36 = 1925;
  v13 = 1926;
  if ( !a4 )
    goto LABEL_83;
  v36 = 1926;
  v13 = 1927;
  if ( !a5 || (v36 = 1927, v13 = 1928, !v48) || (v36 = 1928, v13 = 1929, !a7) || (v36 = 1929, v13 = 1930, !a9) )
  {
LABEL_83:
    v35 = -2147024809;
    goto LABEL_84;
  }
  v36 = 1930;
  v13 = 1931;
  if ( !a10 )
  {
    v35 = -2147024809;
    goto LABEL_84;
  }
  v35 = 0;
  v36 = 1931;
  v35 = CBsString::Set((CBsString *)lpFileName, a5);
  v13 = 1936;
  if ( v35 < 0 )
    goto LABEL_84;
  v36 = 1936;
  v35 = CBsString::Set((CBsString *)&v42, a5);
  v13 = 1937;
  if ( v35 < 0 )
    goto LABEL_84;
  v36 = 1937;
  v14 = CBsString::ReverseFind((CBsString *)&v42, 0x5Cu);
  v15 = v14;
  v16 = (unsigned int)(v14 + 1);
  if ( (unsigned int)v16 < (unsigned int)v43 )
  {
    LODWORD(v43) = v14 + 1;
    v42[v16] = 0;
  }
  v35 = CBsString::Set((CBsString *)&v45, a5);
  v13 = 1947;
  if ( v35 < 0 )
    goto LABEL_84;
  v36 = 1947;
  v17 = -1;
  do
    ++v17;
  while ( a5[v17] );
  v18 = (unsigned int)(v17 - v15 - 1);
  v19 = v45;
  if ( (unsigned int)v18 < (unsigned int)v17 && (unsigned int)v18 < (unsigned int)v46 )
  {
    memmove_0(v45, (char *)v45 + 2 * ((unsigned int)v46 - (unsigned __int64)(unsigned int)v18), 2 * v18);
    LODWORD(v46) = v18;
    v19[v18] = 0;
  }
  v35 = (*(__int64 (__fastcall **)(struct ISdFileRecord *, unsigned __int16 **))(*(_QWORD *)a7 + 24LL))(a7, &v67);
  v13 = 1955;
  if ( v35 < 0 )
    goto LABEL_84;
  v36 = 1955;
  v35 = (*(__int64 (__fastcall **)(struct ISdFileRecord *, unsigned __int16 **))(*(_QWORD *)a7 + 32LL))(a7, &v68);
  v13 = 1956;
  if ( v35 < 0 )
    goto LABEL_84;
  v36 = 1956;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v35 = (*(__int64 (__fastcall **)(struct ISdFileRecord *, char *))(*(_QWORD *)a7 + 64LL))(a7, v72);
  v13 = 1960;
  if ( v35 < 0 )
    goto LABEL_84;
  v36 = 1960;
  v35 = (*(__int64 (__fastcall **)(struct ISdFileRecord *, char *))(*(_QWORD *)a7 + 72LL))(a7, v73);
  v13 = 1961;
  if ( v35 < 0 )
    goto LABEL_84;
  v36 = 1961;
  v35 = (*(__int64 (__fastcall **)(struct ISdFileRecord *, char *))(*(_QWORD *)a7 + 120LL))(a7, v74);
  v13 = 1962;
  if ( v35 < 0 )
    goto LABEL_84;
  v36 = 1962;
  v75 = 0;
  v35 = (*(__int64 (__fastcall **)(struct ISdFileRecord *, char *))(*(_QWORD *)a7 + 144LL))(a7, v76);
  v13 = 1964;
  if ( v35 < 0 )
    goto LABEL_84;
  v36 = 1964;
  v35 = (*(__int64 (__fastcall **)(struct ISdFileRecord *, char *))(*(_QWORD *)a7 + 152LL))(a7, v77);
  v13 = 1965;
  if ( v35 < 0 )
    goto LABEL_84;
  v36 = 1965;
  v35 = (*(__int64 (__fastcall **)(struct ISdFileRecord *, char *))(*(_QWORD *)a7 + 128LL))(a7, v78);
  v13 = 1966;
  if ( v35 < 0 )
    goto LABEL_84;
  v36 = 1966;
  v79 = 0;
  dwFlagsAndAttributes = 128;
  if ( *((_DWORD *)v50 + 14) != 11 )
    dwFlagsAndAttributes = 33554560;
  v35 = CBsString::AntiCanonicalize((CBsString *)lpFileName);
  v13 = 1981;
  if ( v35 < 0 )
    goto LABEL_84;
  v36 = 1981;
  FileW = CreateFileW(lpFileName[0], 0x80000000, 1u, 0, 3u, dwFlagsAndAttributes, 0);
  v11 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_37;
  v22 = 0;
  if ( GetFileType(FileW) == 1 && GetFileInformationByHandle((HANDLE)v11, &FileInformation) )
  {
    v54 = v42;
    v55 = v19;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    ftCreationTime = FileInformation.ftCreationTime;
    ftLastWriteTime = FileInformation.ftLastWriteTime;
    ftLastAccessTime = FileInformation.ftLastAccessTime;
    v62 = 0;
    v63 = FileInformation.nFileSizeLow + ((unsigned __int64)FileInformation.nFileSizeHigh << 32);
    v64 = v63;
    dwFileAttributes = FileInformation.dwFileAttributes;
    v66 = 0;
    v22 = 1;
  }
  if ( v11 )
  {
    CloseHandle((HANDLE)v11);
    v11 = -1;
  }
  if ( !v22 )
  {
LABEL_37:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids);
    FirstFileW = (__int64)FindFirstFileW(lpFileName[0], &FindFileData);
    if ( FirstFileW == -1 )
    {
      LastError = GetLastError();
      if ( LastError == 18 || LastError - 2 <= 1 || LastError == 267 )
        v40 &= ~2u;
      v24 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_52;
      if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_49;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids);
    }
    else
    {
      v54 = v42;
      v55 = v19;
      v56 = 0;
      v57 = 0;
      v58 = 0;
      ftCreationTime = FindFileData.ftCreationTime;
      ftLastWriteTime = FindFileData.ftLastWriteTime;
      ftLastAccessTime = FindFileData.ftLastAccessTime;
      v62 = 0;
      v63 = FindFileData.nFileSizeLow + ((unsigned __int64)FindFileData.nFileSizeHigh << 32);
      v64 = v63;
      dwFileAttributes = FindFileData.dwFileAttributes;
      v66 = 0;
    }
  }
  v24 = (PVOID *)WPP_GLOBAL_Control;
LABEL_49:
  if ( v24 == &WPP_GLOBAL_Control )
  {
LABEL_52:
    v25 = v38;
    goto LABEL_53;
  }
  v25 = v38;
  if ( *((char *)v24 + 28) < 0 )
    WPP_SF_Sd((unsigned int)v24[2], 51, (unsigned int)&WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, (_DWORD)a5, v38);
LABEL_53:
  v35 = CBsString::Set((CBsString *)lpFileName, a5);
  v13 = 2058;
  if ( v35 < 0 )
  {
LABEL_84:
    v37 = v13;
    goto LABEL_85;
  }
  v36 = 2058;
  v26 = lpFileName[0];
  v27 = v40;
  v28 = v51;
  v29 = v48;
  while ( 1 )
  {
    while ( 1 )
    {
      SdFreeString((unsigned __int16 **)&pv);
      v30 = (*(__int64 (__fastcall **)(struct ISdCallback2 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned int, int, LPVOID *, unsigned int *))(*(_QWORD *)v28 + 32LL))(
              v28,
              v26,
              v29,
              &v54,
              &v67,
              v27,
              v25,
              &pv,
              &v39);
      v35 = v30;
      if ( v30 < 0 )
      {
        v13 = 2063;
        goto LABEL_84;
      }
      v36 = 2063;
      if ( v30 == 1 )
      {
        v35 = (*(__int64 (__fastcall **)(struct ISdAsyncPriv *))(*(_QWORD *)v49 + 128LL))(v49);
        v13 = 2067;
        if ( v35 < 0 )
          goto LABEL_84;
        v36 = 2067;
      }
      v31 = v39;
      if ( (v27 & v39) != 0 )
        break;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, v39);
      v25 = -2147024809;
    }
    if ( (v39 & 4) == 0 )
      break;
    if ( pv )
    {
      v35 = CBsString::Set((CBsString *)v47, (const unsigned __int16 *)pv);
      v13 = 2089;
      if ( v35 < 0 )
        goto LABEL_84;
      v36 = 2089;
    }
    else
    {
      CBsString::Empty((CBsString *)v47);
    }
    valid = IsValidFileName(v47[0]);
    v25 = valid;
    v35 = valid;
    if ( valid == 1 )
    {
      v25 = -2147024773;
    }
    else if ( valid >= 0 )
    {
      v35 = CBsString::Set((CBsString *)lpFileName, v42, v47[0]);
      v13 = 2111;
      if ( v35 < 0 )
        goto LABEL_84;
      v36 = 2111;
      v31 = v39;
      v26 = lpFileName[0];
      break;
    }
  }
  if ( !v31 || ((v31 - 1) & v31) != 0 )
  {
    v35 = -2130706431;
    v13 = 2121;
    goto LABEL_84;
  }
  v35 = 0;
  v36 = 2121;
  if ( v31 == 4 )
  {
    v35 = CBsString::Set(v52, v26);
    v13 = 2125;
    if ( v35 < 0 )
      goto LABEL_84;
    v36 = 2125;
    v31 = v39;
  }
  *v53 = v31;
LABEL_85:
  SdFreeString(&v67);
  SdFreeString(&v68);
  memset_0(&v67, 0, 0x80u);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v33 = v35;
  CBsString::_Release((CBsString *)&v45);
  CBsString::_Release((CBsString *)&v42);
  CBsString::_Release((CBsString *)v47);
  CBsString::_Release((CBsString *)lpFileName);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose((HANDLE)FirstFileW);
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v11);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v35);
  return v33;
}

```

## disassembly

```asm
0x18002c550  mov     [rsp-8+arg_0], rbx
0x18002c555  push    rbp
0x18002c556  push    rsi
0x18002c557  push    rdi
0x18002c558  push    r12
0x18002c55a  push    r13
0x18002c55c  push    r14
0x18002c55e  push    r15
0x18002c560  lea     rbp, [rsp-3B0h]
0x18002c568  sub     rsp, 4B0h
0x18002c56f  mov     rax, cs:__security_cookie
0x18002c576  xor     rax, rsp
0x18002c579  mov     [rbp+3E0h+var_40], rax
0x18002c580  mov     r13, r9
0x18002c583  mov     [rbp+3E0h+var_3E8], r9
0x18002c587  mov     [rbp+3E0h+var_458], r8d
0x18002c58b  mov     [rbp+3E0h+var_3F8], rdx
0x18002c58f  mov     [rbp+3E0h+var_3F0], rcx
0x18002c593  mov     r12, [rbp+3E0h+arg_20]
0x18002c59a  mov     rax, [rbp+3E0h+arg_28]
0x18002c5a1  mov     [rbp+3E0h+var_400], rax
0x18002c5a5  mov     r14, [rbp+3E0h+arg_30]
0x18002c5ac  mov     eax, [rbp+3E0h+arg_38]
0x18002c5b2  mov     [rbp+3E0h+var_450], eax
0x18002c5b5  mov     r15, [rbp+3E0h+arg_40]
0x18002c5bc  mov     [rbp+3E0h+var_3E0], r15
0x18002c5c0  mov     rsi, [rbp+3E0h+arg_48]
0x18002c5c7  mov     [rbp+3E0h+var_3D8], rsi
0x18002c5cb  mov     r9d, 1; unsigned __int16
0x18002c5d1  mov     r8d, 770h; unsigned __int16
0x18002c5d7  lea     rdx, aCsdrestoreimpl_28; "CSdRestoreImpl::_RestoreAskUIWhatToDo"
0x18002c5de  lea     rcx, [rsp+4E0h+var_490]; this
0x18002c5e3  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002c5e8  xor     edi, edi
0x18002c5ea  mov     [rbp+3E0h+var_454], edi
0x18002c5ed  xorps   xmm0, xmm0
0x18002c5f0  xor     eax, eax
0x18002c5f2  movups  xmmword ptr [rbp+3E0h+FileInformation.dwFileAttributes], xmm0
0x18002c5f9  movups  xmmword ptr [rbp+3E0h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18002c600  movups  xmmword ptr [rbp+3E0h+FileInformation.nFileSizeHigh], xmm0
0x18002c607  mov     [rbp+3E0h+FileInformation.nFileIndexLow], eax
0x18002c60d  mov     ebx, 80h
0x18002c612  mov     r8d, ebx; Size
0x18002c615  xor     edx, edx; Val
0x18002c617  lea     rcx, [rbp+3E0h+var_3D0]; void *
0x18002c61b  call    memset_0
0x18002c620  mov     r8d, ebx; Size
0x18002c623  xor     edx, edx; Val
0x18002c625  lea     rcx, [rbp+3E0h+var_350]; void *
0x18002c62c  call    memset_0
0x18002c631  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002c635  mov     [rbp+3E0h+pv], rdi
0x18002c639  xor     edx, edx; Val
0x18002c63b  mov     r8d, 250h; Size
0x18002c641  lea     rcx, [rbp+3E0h+FindFileData]; void *
0x18002c648  call    memset_0
0x18002c64d  or      rdi, rbx
0x18002c650  lea     rax, qword_1800E8530
0x18002c657  mov     [rbp+3E0h+lpFileName], rax
0x18002c65b  xor     ecx, ecx
0x18002c65d  mov     [rbp+3E0h+var_428], rcx
0x18002c661  mov     [rbp+3E0h+var_410], rax
0x18002c665  mov     [rbp+3E0h+var_408], rcx
0x18002c669  mov     [rbp+3E0h+var_440], rax
0x18002c66d  mov     [rbp+3E0h+var_438], rcx
0x18002c671  mov     [rbp+3E0h+var_420], rax
0x18002c675  mov     [rbp+3E0h+var_418], rcx
0x18002c679  mov     eax, 785h
0x18002c67e  cmp     [rbp+3E0h+var_3F8], rcx
0x18002c682  jz      loc_18002CDCF
0x18002c688  mov     [rsp+4E0h+var_48C], ax
0x18002c68d  mov     eax, 786h
0x18002c692  test    r13, r13
0x18002c695  jz      loc_18002CDCF
0x18002c69b  mov     [rsp+4E0h+var_48C], ax
0x18002c6a0  mov     eax, 787h
0x18002c6a5  test    r12, r12
0x18002c6a8  jz      loc_18002CDCF
0x18002c6ae  mov     [rsp+4E0h+var_48C], ax
0x18002c6b3  mov     eax, 788h
0x18002c6b8  cmp     [rbp+3E0h+var_400], rcx
0x18002c6bc  jz      loc_18002CDCF
0x18002c6c2  mov     [rsp+4E0h+var_48C], ax
0x18002c6c7  mov     eax, 789h
0x18002c6cc  test    r14, r14
0x18002c6cf  jz      loc_18002CDCF
0x18002c6d5  mov     [rsp+4E0h+var_48C], ax
0x18002c6da  mov     eax, 78Ah
0x18002c6df  test    r15, r15
0x18002c6e2  jz      loc_18002CDCF
0x18002c6e8  mov     [rsp+4E0h+var_48C], ax
0x18002c6ed  xor     r15d, r15d
0x18002c6f0  mov     eax, 78Bh
0x18002c6f5  test    rsi, rsi
0x18002c6f8  jz      loc_18002CDC5
0x18002c6fe  mov     [rsp+4E0h+var_490], r15d
0x18002c703  mov     [rsp+4E0h+var_48C], ax
0x18002c708  mov     rdx, r12; unsigned __int16 *
0x18002c70b  lea     rcx, [rbp+3E0h+lpFileName]; this
0x18002c70f  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18002c714  mov     [rsp+4E0h+var_490], eax
0x18002c718  test    eax, eax
0x18002c71a  mov     eax, 790h
0x18002c71f  js      loc_18002CDDA
0x18002c725  mov     [rsp+4E0h+var_48C], ax
0x18002c72a  mov     rdx, r12; unsigned __int16 *
0x18002c72d  lea     rcx, [rbp+3E0h+var_440]; this
0x18002c731  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18002c736  mov     [rsp+4E0h+var_490], eax
0x18002c73a  test    eax, eax
0x18002c73c  mov     eax, 791h
0x18002c741  js      loc_18002CDDA
0x18002c747  mov     [rsp+4E0h+var_48C], ax
0x18002c74c  lea     edx, [rbx+5Dh]; unsigned __int16
0x18002c74f  lea     rcx, [rbp+3E0h+var_440]; this
0x18002c753  call    ?ReverseFind@CBsString@@QEBAJG@Z; CBsString::ReverseFind(ushort)
0x18002c758  mov     esi, eax
0x18002c75a  lea     ecx, [rax+1]
0x18002c75d  cmp     ecx, dword ptr [rbp+3E0h+var_438]
0x18002c760  jnb     short loc_18002C76E
0x18002c762  mov     dword ptr [rbp+3E0h+var_438], ecx
0x18002c765  mov     rax, [rbp+3E0h+var_440]
0x18002c769  mov     [rax+rcx*2], r15w
0x18002c76e  mov     rdx, r12; unsigned __int16 *
0x18002c771  lea     rcx, [rbp+3E0h+var_420]; this
0x18002c775  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18002c77a  mov     [rsp+4E0h+var_490], eax
0x18002c77e  test    eax, eax
0x18002c780  mov     eax, 79Bh
0x18002c785  js      loc_18002CDDA
0x18002c78b  mov     [rsp+4E0h+var_48C], ax
0x18002c790  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002c794  inc     rcx
0x18002c797  cmp     [r12+rcx*2], r15w
0x18002c79c  jnz     short loc_18002C794
0x18002c79e  mov     r15d, ecx
0x18002c7a1  sub     r15d, esi
0x18002c7a4  dec     r15d
0x18002c7a7  mov     r13, [rbp+3E0h+var_420]
0x18002c7ab  cmp     r15d, ecx
0x18002c7ae  jnb     short loc_18002C7E4
0x18002c7b0  cmp     r15d, dword ptr [rbp+3E0h+var_418]
0x18002c7b4  jnb     short loc_18002C7E4
0x18002c7b6  mov     ecx, r15d
0x18002c7b9  lea     rsi, [r15+r15]
0x18002c7bd  mov     eax, dword ptr [rbp+3E0h+var_418]
0x18002c7c0  sub     rax, rcx
0x18002c7c3  lea     rdx, ds:0[rax*2]
0x18002c7cb  add     rdx, r13; Src
0x18002c7ce  mov     r8, rsi; Size
0x18002c7d1  mov     rcx, r13; void *
0x18002c7d4  call    memmove_0
0x18002c7d9  mov     dword ptr [rbp+3E0h+var_418], r15d
0x18002c7dd  xor     eax, eax
0x18002c7df  mov     [rsi+r13], ax
0x18002c7e4  mov     rax, [r14]
0x18002c7e7  lea     rdx, [rbp+3E0h+var_350]
0x18002c7ee  mov     rcx, r14
0x18002c7f1  mov     rax, [rax+18h]
0x18002c7f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7fa  mov     [rsp+4E0h+var_490], eax
0x18002c7fe  xor     r15d, r15d
0x18002c801  test    eax, eax
0x18002c803  mov     eax, 7A3h
0x18002c808  js      loc_18002CDDA
0x18002c80e  mov     [rsp+4E0h+var_48C], ax
0x18002c813  mov     rax, [r14]
0x18002c816  lea     rdx, [rbp+3E0h+var_348]
0x18002c81d  mov     rcx, r14
0x18002c820  mov     rax, [rax+20h]
0x18002c824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c829  mov     [rsp+4E0h+var_490], eax
0x18002c82d  test    eax, eax
0x18002c82f  mov     eax, 7A4h
0x18002c834  js      loc_18002CDDA
0x18002c83a  mov     [rsp+4E0h+var_48C], ax
0x18002c83f  mov     [rbp+3E0h+var_340], r15w
0x18002c847  mov     [rbp+3E0h+var_320], r15
0x18002c84e  mov     [rbp+3E0h+var_318], r15d
0x18002c855  mov     rax, [r14]
0x18002c858  lea     rdx, [rbp+3E0h+var_310]
0x18002c85f  mov     rcx, r14
0x18002c862  mov     rax, [rax+40h]
0x18002c866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c86b  mov     [rsp+4E0h+var_490], eax
0x18002c86f  test    eax, eax
0x18002c871  mov     eax, 7A8h
0x18002c876  js      loc_18002CDDA
0x18002c87c  mov     [rsp+4E0h+var_48C], ax
0x18002c881  mov     rax, [r14]
0x18002c884  lea     rdx, [rbp+3E0h+var_308]
0x18002c88b  mov     rcx, r14
0x18002c88e  mov     rax, [rax+48h]
0x18002c892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c897  mov     [rsp+4E0h+var_490], eax
0x18002c89b  test    eax, eax
0x18002c89d  mov     eax, 7A9h
0x18002c8a2  js      loc_18002CDDA
0x18002c8a8  mov     [rsp+4E0h+var_48C], ax
0x18002c8ad  mov     rax, [r14]
0x18002c8b0  lea     rdx, [rbp+3E0h+var_300]
0x18002c8b7  mov     rcx, r14
0x18002c8ba  mov     rax, [rax+78h]
0x18002c8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8c3  mov     [rsp+4E0h+var_490], eax
0x18002c8c7  test    eax, eax
0x18002c8c9  mov     eax, 7AAh
0x18002c8ce  js      loc_18002CDDA
0x18002c8d4  mov     [rsp+4E0h+var_48C], ax
0x18002c8d9  mov     [rbp+3E0h+var_2F8], r15
0x18002c8e0  mov     rax, [r14]
0x18002c8e3  lea     rdx, [rbp+3E0h+var_2F0]
0x18002c8ea  mov     rcx, r14
0x18002c8ed  mov     rax, [rax+90h]
0x18002c8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8f9  mov     [rsp+4E0h+var_490], eax
0x18002c8fd  test    eax, eax
0x18002c8ff  mov     eax, 7ACh
0x18002c904  js      loc_18002CDDA
0x18002c90a  mov     [rsp+4E0h+var_48C], ax
0x18002c90f  mov     rax, [r14]
0x18002c912  lea     rdx, [rbp+3E0h+var_2E8]
0x18002c919  mov     rcx, r14
0x18002c91c  mov     rax, [rax+98h]
0x18002c923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c928  mov     [rsp+4E0h+var_490], eax
0x18002c92c  test    eax, eax
0x18002c92e  mov     eax, 7ADh
0x18002c933  js      loc_18002CDDA
0x18002c939  mov     [rsp+4E0h+var_48C], ax
0x18002c93e  mov     rax, [r14]
0x18002c941  lea     rdx, [rbp+3E0h+var_2E0]
0x18002c948  mov     rcx, r14
0x18002c94b  mov     rax, [rax+80h]
0x18002c952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c957  mov     [rsp+4E0h+var_490], eax
0x18002c95b  test    eax, eax
0x18002c95d  mov     eax, 7AEh
0x18002c962  js      loc_18002CDDA
0x18002c968  mov     [rsp+4E0h+var_48C], ax
0x18002c96d  mov     [rbp+3E0h+var_2DC], r15
0x18002c974  mov     esi, 80h
0x18002c979  mov     ecx, 2000080h
0x18002c97e  mov     rax, [rbp+3E0h+var_3F0]
0x18002c982  cmp     dword ptr [rax+38h], 0Bh
0x18002c986  cmovnz  esi, ecx
0x18002c989  lea     rcx, [rbp+3E0h+lpFileName]; this
0x18002c98d  call    ?AntiCanonicalize@CBsString@@QEAAJXZ; CBsString::AntiCanonicalize(void)
0x18002c992  mov     [rsp+4E0h+var_490], eax
0x18002c996  test    eax, eax
0x18002c998  mov     eax, 7BDh
0x18002c99d  js      loc_18002CDDA
0x18002c9a3  mov     [rsp+4E0h+var_48C], ax
0x18002c9a8  mov     [rsp+4E0h+hTemplateFile], r15; hTemplateFile
0x18002c9ad  mov     [rsp+4E0h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18002c9b1  mov     [rsp+4E0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002c9b9  xor     r9d, r9d; lpSecurityAttributes
0x18002c9bc  mov     edx, 80000000h; dwDesiredAccess
0x18002c9c1  lea     r8d, [r15+1]; dwShareMode
0x18002c9c5  mov     rcx, [rbp+3E0h+lpFileName]; lpFileName
0x18002c9c9  call    cs:__imp_CreateFileW
0x18002c9cf  mov     rbx, rax
0x18002c9d2  lea     r14, WPP_GLOBAL_Control
0x18002c9d9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c9dd  jz      loc_18002CA96
0x18002c9e3  mov     esi, r15d
0x18002c9e6  mov     rcx, rax; hFile
0x18002c9e9  call    cs:__imp_GetFileType
0x18002c9ef  cmp     eax, 1
0x18002c9f2  jnz     loc_18002CA7C
0x18002c9f8  lea     rdx, [rbp+3E0h+FileInformation]; lpFileInformation
0x18002c9ff  mov     rcx, rbx; hFile
0x18002ca02  call    cs:__imp_GetFileInformationByHandle
0x18002ca08  test    eax, eax
0x18002ca0a  jz      short loc_18002CA7C
0x18002ca0c  mov     rax, [rbp+3E0h+var_440]
0x18002ca10  mov     [rbp+3E0h+var_3D0], rax
0x18002ca14  mov     [rbp+3E0h+var_3C8], r13
0x18002ca18  mov     [rbp+3E0h+var_3C0], r15w
0x18002ca1d  mov     [rbp+3E0h+var_3A0], r15
0x18002ca21  mov     [rbp+3E0h+var_398], r15d
0x18002ca25  mov     rax, qword ptr [rbp+3E0h+FileInformation.ftCreationTime.dwLowDateTime]
0x18002ca2c  mov     [rbp+3E0h+var_390], rax
0x18002ca30  mov     rax, qword ptr [rbp+3E0h+FileInformation.ftLastWriteTime.dwLowDateTime]
0x18002ca37  mov     [rbp+3E0h+var_388], rax
0x18002ca3b  mov     rax, qword ptr [rbp+3E0h+FileInformation.ftLastAccessTime.dwLowDateTime]
0x18002ca42  mov     [rbp+3E0h+var_380], rax
0x18002ca46  mov     [rbp+3E0h+var_378], r15
0x18002ca4a  mov     ecx, [rbp+3E0h+FileInformation.nFileSizeHigh]
0x18002ca50  shl     rcx, 20h
0x18002ca54  mov     eax, [rbp+3E0h+FileInformation.nFileSizeLow]
0x18002ca5a  add     rcx, rax
0x18002ca5d  mov     [rbp+3E0h+var_370], rcx
0x18002ca61  mov     [rbp+3E0h+var_368], rcx
0x18002ca65  mov     eax, [rbp+3E0h+FileInformation.dwFileAttributes]
0x18002ca6b  mov     [rbp+3E0h+var_360], eax
0x18002ca71  mov     [rbp+3E0h+var_35C], r15
0x18002ca78  lea     esi, [r15+1]
0x18002ca7c  test    rbx, rbx
0x18002ca7f  jz      short loc_18002CA8E
  ... truncated ...
```
