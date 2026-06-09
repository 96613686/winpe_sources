# CSdRestoreImpl::_RestoreAskUIWhatToDo(ISdAsyncPriv *,long,ISdCallback2 *,ushort const *,ushort const *,ISdFileRecord *,ulong,CBsString *,ulong *)

- ea: `0x18002d6c4`
- end: `0x18002e04d`
- name: `?_RestoreAskUIWhatToDo@CSdRestoreImpl@@AEAAJPEAUISdAsyncPriv@@JPEAUISdCallback2@@PEBG2PEAUISdFileRecord@@KPEAVCBsString@@PEAK@Z`
- size: `2441`
- prototype: `__int64 __fastcall(CSdRestoreImpl *__hidden this, struct ISdAsyncPriv *, int, struct ISdCallback2 *, const unsigned __int16 *, const unsigned __int16 *, struct ISdFileRecord *, unsigned int, struct CBsString *, unsigned int *)`
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, service_task`

## callers

- `0x18002e620`
- `0x180030494`
- `0x180030ef4`
- `0x180031558`

## callees

- `0x180008370`
- `0x1800083a0`
- `0x180009d0c`
- `0x180014c30`
- `0x18002d6c4`
- `0x180072e08`
- `0x180072f14`
- `0x18008a4dc`
- `0x18009da98`
- `0x18009e234`
- `0x18009e718`
- `0x18009e8e4`
- `0x18009e904`
- `0x18009f560`
- `0x1800cf55e`
- `0x1800cf56a`
- `0x1800cf5c0`
- `0x1800d1010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18002db3d`
- `KERNEL32!CreateFileW` at `0x18002db3d`
- `KERNEL32!GetLastError` at `0x18002dcd7`
- `KERNEL32!GetLastError` at `0x18002dcd7`
- `KERNEL32!CloseHandle` at `0x18002dc0a`
- `KERNEL32!CloseHandle` at `0x18002e00a`
- `KERNEL32!CloseHandle` at `0x18002dc0a`
- `KERNEL32!CloseHandle` at `0x18002e00a`
- `KERNEL32!FindFirstFileW` at `0x18002dc54`
- `KERNEL32!FindFirstFileW` at `0x18002dc54`
- `KERNEL32!FindClose` at `0x18002dff1`
- `KERNEL32!FindClose` at `0x18002dff1`
- `KERNEL32!GetFileType` at `0x18002db63`
- `KERNEL32!GetFileType` at `0x18002db63`
- `KERNEL32!GetFileInformationByHandle` at `0x18002db82`
- `KERNEL32!GetFileInformationByHandle` at `0x18002db82`
- `ole32!CoTaskMemFree` at `0x18002dfac`
- `ole32!CoTaskMemFree` at `0x18002dfac`

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
  __int64 v22; // r9
  int v23; // esi
  DWORD LastError; // eax
  __int64 v25; // r9
  PVOID *v26; // rcx
  int v27; // r14d
  const unsigned __int16 *v28; // rsi
  unsigned int v29; // r15d
  struct ISdCallback2 *v30; // r12
  const unsigned __int16 *v31; // r13
  int v32; // eax
  unsigned int v33; // r8d
  int valid; // eax
  unsigned int v35; // esi
  int v37; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v38; // [rsp+54h] [rbp-ACh]
  __int16 v39; // [rsp+56h] [rbp-AAh]
  int v40; // [rsp+88h] [rbp-78h]
  unsigned int v41; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v42; // [rsp+90h] [rbp-70h]
  LPVOID pv; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v44; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-58h]
  LPCWSTR lpFileName[2]; // [rsp+B0h] [rbp-50h] BYREF
  void *v47; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v48; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v49[2]; // [rsp+D0h] [rbp-30h] BYREF
  const unsigned __int16 *v50; // [rsp+E0h] [rbp-20h]
  struct ISdAsyncPriv *v51; // [rsp+E8h] [rbp-18h]
  CSdRestoreImpl *v52; // [rsp+F0h] [rbp-10h]
  struct ISdCallback2 *v53; // [rsp+F8h] [rbp-8h]
  CBsString *v54; // [rsp+100h] [rbp+0h]
  unsigned int *v55; // [rsp+108h] [rbp+8h]
  unsigned __int16 *v56; // [rsp+110h] [rbp+10h] BYREF
  _WORD *v57; // [rsp+118h] [rbp+18h]
  __int16 v58; // [rsp+120h] [rbp+20h]
  __int64 v59; // [rsp+140h] [rbp+40h]
  int v60; // [rsp+148h] [rbp+48h]
  FILETIME ftCreationTime; // [rsp+150h] [rbp+50h]
  FILETIME ftLastWriteTime; // [rsp+158h] [rbp+58h]
  FILETIME ftLastAccessTime; // [rsp+160h] [rbp+60h]
  __int64 v64; // [rsp+168h] [rbp+68h]
  unsigned __int64 v65; // [rsp+170h] [rbp+70h]
  unsigned __int64 v66; // [rsp+178h] [rbp+78h]
  DWORD dwFileAttributes; // [rsp+180h] [rbp+80h]
  __int64 v68; // [rsp+184h] [rbp+84h]
  unsigned __int16 *v69; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 *v70; // [rsp+198h] [rbp+98h] BYREF
  __int16 v71; // [rsp+1A0h] [rbp+A0h]
  __int64 v72; // [rsp+1C0h] [rbp+C0h]
  int v73; // [rsp+1C8h] [rbp+C8h]
  char v74[8]; // [rsp+1D0h] [rbp+D0h] BYREF
  char v75[8]; // [rsp+1D8h] [rbp+D8h] BYREF
  char v76[8]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v77; // [rsp+1E8h] [rbp+E8h]
  char v78[8]; // [rsp+1F0h] [rbp+F0h] BYREF
  char v79[8]; // [rsp+1F8h] [rbp+F8h] BYREF
  char v80[4]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v81; // [rsp+204h] [rbp+104h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+210h] [rbp+110h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+250h] [rbp+150h] BYREF

  v53 = a4;
  v40 = a3;
  v51 = a2;
  v52 = this;
  v50 = a6;
  v42 = a8;
  v54 = a9;
  v55 = a10;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v37, "CSdRestoreImpl::_RestoreAskUIWhatToDo", 0x770u, 1u);
  v41 = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  memset_0(&v56, 0, 0x80u);
  memset_0(&v69, 0, 0x80u);
  v11 = -1;
  pv = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = -1;
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
  lpFileName[1] = 0;
  v49[0] = (unsigned __int16 *)qword_1800EE510;
  v49[1] = 0;
  v44 = (unsigned __int16 *)qword_1800EE510;
  v45 = 0;
  v47 = qword_1800EE510;
  v48 = 0;
  v13 = 1925;
  if ( !v51 )
    goto LABEL_83;
  v38 = 1925;
  v13 = 1926;
  if ( !a4 )
    goto LABEL_83;
  v38 = 1926;
  v13 = 1927;
  if ( !a5 || (v38 = 1927, v13 = 1928, !v50) || (v38 = 1928, v13 = 1929, !a7) || (v38 = 1929, v13 = 1930, !a9) )
  {
LABEL_83:
    v37 = -2147024809;
    goto LABEL_84;
  }
  v38 = 1930;
  v13 = 1931;
  if ( !a10 )
  {
    v37 = -2147024809;
    goto LABEL_84;
  }
  v37 = 0;
  v38 = 1931;
  v37 = CBsString::Set((CBsString *)lpFileName, a5);
  v13 = 1936;
  if ( v37 < 0 )
    goto LABEL_84;
  v38 = 1936;
  v37 = CBsString::Set((CBsString *)&v44, a5);
  v13 = 1937;
  if ( v37 < 0 )
    goto LABEL_84;
  v38 = 1937;
  v14 = CBsString::ReverseFind((CBsString *)&v44, 0x5Cu);
  v15 = v14;
  v16 = (unsigned int)(v14 + 1);
  if ( (unsigned int)v16 < (unsigned int)v45 )
  {
    LODWORD(v45) = v14 + 1;
    v44[v16] = 0;
  }
  v37 = CBsString::Set((CBsString *)&v47, a5);
  v13 = 1947;
  if ( v37 < 0 )
    goto LABEL_84;
  v38 = 1947;
  v17 = -1;
  do
    ++v17;
  while ( a5[v17] );
  v18 = (unsigned int)(v17 - v15 - 1);
  v19 = v47;
  if ( (unsigned int)v18 < (unsigned int)v17 && (unsigned int)v18 < (unsigned int)v48 )
  {
    memmove_0(v47, (char *)v47 + 2 * ((unsigned int)v48 - (unsigned __int64)(unsigned int)v18), 2 * v18);
    LODWORD(v48) = v18;
    v19[v18] = 0;
  }
  v37 = (*(__int64 (__fastcall **)(struct ISdFileRecord *, unsigned __int16 **))(*(_QWORD *)a7 + 24LL))(a7, &v69);
  v13 = 1955;
  if ( v37 < 0 )
    goto LABEL_84;
  v38 = 1955;
  v37 = (*(__int64 (__fastcall **)(struct ISdFileRecord *, unsigned __int16 **))(*(_QWORD *)a7 + 32LL))(a7, &v70);
  v13 = 1956;
  if ( v37 < 0 )
    goto LABEL_84;
  v38 = 1956;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v37 = (*(__int64 (__fastcall **)(struct ISdFileRecord *, char *))(*(_QWORD *)a7 + 64LL))(a7, v74);
  v13 = 1960;
  if ( v37 < 0 )
    goto LABEL_84;
  v38 = 1960;
  v37 = (*(__int64 (__fastcall **)(struct ISdFileRecord *, char *))(*(_QWORD *)a7 + 72LL))(a7, v75);
  v13 = 1961;
  if ( v37 < 0 )
    goto LABEL_84;
  v38 = 1961;
  v37 = (*(__int64 (__fastcall **)(struct ISdFileRecord *, char *))(*(_QWORD *)a7 + 120LL))(a7, v76);
  v13 = 1962;
  if ( v37 < 0 )
    goto LABEL_84;
  v38 = 1962;
  v77 = 0;
  v37 = (*(__int64 (__fastcall **)(struct ISdFileRecord *, char *))(*(_QWORD *)a7 + 144LL))(a7, v78);
  v13 = 1964;
  if ( v37 < 0 )
    goto LABEL_84;
  v38 = 1964;
  v37 = (*(__int64 (__fastcall **)(struct ISdFileRecord *, char *))(*(_QWORD *)a7 + 152LL))(a7, v79);
  v13 = 1965;
  if ( v37 < 0 )
    goto LABEL_84;
  v38 = 1965;
  v37 = (*(__int64 (__fastcall **)(struct ISdFileRecord *, char *))(*(_QWORD *)a7 + 128LL))(a7, v80);
  v13 = 1966;
  if ( v37 < 0 )
    goto LABEL_84;
  v38 = 1966;
  v81 = 0;
  dwFlagsAndAttributes = 128;
  if ( *((_DWORD *)v52 + 14) != 11 )
    dwFlagsAndAttributes = 33554560;
  v37 = CBsString::AntiCanonicalize((CBsString *)lpFileName);
  v13 = 1981;
  if ( v37 < 0 )
    goto LABEL_84;
  v38 = 1981;
  FileW = CreateFileW(lpFileName[0], 0x80000000, 1u, 0, 3u, dwFlagsAndAttributes, 0);
  v11 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_37;
  v23 = 0;
  if ( GetFileType(FileW) == 1 && GetFileInformationByHandle((HANDLE)v11, &FileInformation) )
  {
    v56 = v44;
    v57 = v19;
    v58 = 0;
    v59 = 0;
    v60 = 0;
    ftCreationTime = FileInformation.ftCreationTime;
    ftLastWriteTime = FileInformation.ftLastWriteTime;
    ftLastAccessTime = FileInformation.ftLastAccessTime;
    v64 = 0;
    v65 = FileInformation.nFileSizeLow + ((unsigned __int64)FileInformation.nFileSizeHigh << 32);
    v66 = v65;
    dwFileAttributes = FileInformation.dwFileAttributes;
    v68 = 0;
    v23 = 1;
  }
  if ( v11 )
  {
    CloseHandle((HANDLE)v11);
    v11 = -1;
  }
  if ( !v23 )
  {
LABEL_37:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, v22);
    FirstFileW = (__int64)FindFirstFileW(lpFileName[0], &FindFileData);
    if ( FirstFileW == -1 )
    {
      LastError = GetLastError();
      if ( LastError == 18 || LastError - 2 <= 1 || LastError == 267 )
        v42 &= ~2u;
      v26 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_52;
      if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_49;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, v25);
    }
    else
    {
      v56 = v44;
      v57 = v19;
      v58 = 0;
      v59 = 0;
      v60 = 0;
      ftCreationTime = FindFileData.ftCreationTime;
      ftLastWriteTime = FindFileData.ftLastWriteTime;
      ftLastAccessTime = FindFileData.ftLastAccessTime;
      v64 = 0;
      v65 = FindFileData.nFileSizeLow + ((unsigned __int64)FindFileData.nFileSizeHigh << 32);
      v66 = v65;
      dwFileAttributes = FindFileData.dwFileAttributes;
      v68 = 0;
    }
  }
  v26 = (PVOID *)WPP_GLOBAL_Control;
LABEL_49:
  if ( v26 == &WPP_GLOBAL_Control )
  {
LABEL_52:
    v27 = v40;
    goto LABEL_53;
  }
  v27 = v40;
  if ( *((char *)v26 + 28) < 0 )
    WPP_SF_Sd((unsigned int)v26[2], 51, (unsigned int)&WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, (_DWORD)a5, v40);
LABEL_53:
  v37 = CBsString::Set((CBsString *)lpFileName, a5);
  v13 = 2058;
  if ( v37 < 0 )
  {
LABEL_84:
    v39 = v13;
    goto LABEL_85;
  }
  v38 = 2058;
  v28 = lpFileName[0];
  v29 = v42;
  v30 = v53;
  v31 = v50;
  while ( 1 )
  {
    while ( 1 )
    {
      SdFreeString((unsigned __int16 **)&pv);
      v32 = (*(__int64 (__fastcall **)(struct ISdCallback2 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned int, int, LPVOID *, unsigned int *))(*(_QWORD *)v30 + 32LL))(
              v30,
              v28,
              v31,
              &v56,
              &v69,
              v29,
              v27,
              &pv,
              &v41);
      v37 = v32;
      if ( v32 < 0 )
      {
        v13 = 2063;
        goto LABEL_84;
      }
      v38 = 2063;
      if ( v32 == 1 )
      {
        v37 = (*(__int64 (__fastcall **)(struct ISdAsyncPriv *))(*(_QWORD *)v51 + 128LL))(v51);
        v13 = 2067;
        if ( v37 < 0 )
          goto LABEL_84;
        v38 = 2067;
      }
      v33 = v41;
      if ( (v29 & v41) != 0 )
        break;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, v41);
      v27 = -2147024809;
    }
    if ( (v41 & 4) == 0 )
      break;
    if ( pv )
    {
      v37 = CBsString::Set((CBsString *)v49, (const unsigned __int16 *)pv);
      v13 = 2089;
      if ( v37 < 0 )
        goto LABEL_84;
      v38 = 2089;
    }
    else
    {
      CBsString::Empty((CBsString *)v49);
    }
    valid = IsValidFileName(v49[0]);
    v27 = valid;
    v37 = valid;
    if ( valid == 1 )
    {
      v27 = -2147024773;
    }
    else if ( valid >= 0 )
    {
      v37 = CBsString::Set((CBsString *)lpFileName, v44, v49[0]);
      v13 = 2111;
      if ( v37 < 0 )
        goto LABEL_84;
      v38 = 2111;
      v33 = v41;
      v28 = lpFileName[0];
      break;
    }
  }
  if ( !v33 || ((v33 - 1) & v33) != 0 )
  {
    v37 = -2130706431;
    v13 = 2121;
    goto LABEL_84;
  }
  v37 = 0;
  v38 = 2121;
  if ( v33 == 4 )
  {
    v37 = CBsString::Set(v54, v28);
    v13 = 2125;
    if ( v37 < 0 )
      goto LABEL_84;
    v38 = 2125;
    v33 = v41;
  }
  *v55 = v33;
LABEL_85:
  SdFreeString(&v69);
  SdFreeString(&v70);
  memset_0(&v69, 0, 0x80u);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v35 = v37;
  CBsString::_Release((CBsString *)&v47);
  CBsString::_Release((CBsString *)&v44);
  CBsString::_Release((CBsString *)v49);
  CBsString::_Release((CBsString *)lpFileName);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose((HANDLE)FirstFileW);
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v11);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v37);
  return v35;
}

```

## disassembly

```asm
0x18002d6c4  mov     [rsp-8+arg_0], rbx
0x18002d6c9  push    rbp
0x18002d6ca  push    rsi
0x18002d6cb  push    rdi
0x18002d6cc  push    r12
0x18002d6ce  push    r13
0x18002d6d0  push    r14
0x18002d6d2  push    r15
0x18002d6d4  lea     rbp, [rsp-3B0h]
0x18002d6dc  sub     rsp, 4B0h
0x18002d6e3  mov     rax, cs:__security_cookie
0x18002d6ea  xor     rax, rsp
0x18002d6ed  mov     [rbp+3E0h+var_40], rax
0x18002d6f4  mov     r13, r9
0x18002d6f7  mov     [rbp+3E0h+var_3E8], r9
0x18002d6fb  mov     [rbp+3E0h+var_458], r8d
0x18002d6ff  mov     [rbp+3E0h+var_3F8], rdx
0x18002d703  mov     [rbp+3E0h+var_3F0], rcx
0x18002d707  mov     r12, [rbp+3E0h+arg_20]
0x18002d70e  mov     rax, [rbp+3E0h+arg_28]
0x18002d715  mov     [rbp+3E0h+var_400], rax
0x18002d719  mov     r14, [rbp+3E0h+arg_30]
0x18002d720  mov     eax, [rbp+3E0h+arg_38]
0x18002d726  mov     [rbp+3E0h+var_450], eax
0x18002d729  mov     r15, [rbp+3E0h+arg_40]
0x18002d730  mov     [rbp+3E0h+var_3E0], r15
0x18002d734  mov     rsi, [rbp+3E0h+arg_48]
0x18002d73b  mov     [rbp+3E0h+var_3D8], rsi
0x18002d73f  mov     r9d, 1; unsigned __int16
0x18002d745  mov     r8d, 770h; unsigned __int16
0x18002d74b  lea     rdx, aCsdrestoreimpl_28; "CSdRestoreImpl::_RestoreAskUIWhatToDo"
0x18002d752  lea     rcx, [rsp+4E0h+var_490]; this
0x18002d757  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002d75c  xor     edi, edi
0x18002d75e  mov     [rbp+3E0h+var_454], edi
0x18002d761  xorps   xmm0, xmm0
0x18002d764  xor     eax, eax
0x18002d766  movups  xmmword ptr [rbp+3E0h+FileInformation.dwFileAttributes], xmm0
0x18002d76d  movups  xmmword ptr [rbp+3E0h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18002d774  movups  xmmword ptr [rbp+3E0h+FileInformation.nFileSizeHigh], xmm0
0x18002d77b  mov     [rbp+3E0h+FileInformation.nFileIndexLow], eax
0x18002d781  mov     ebx, 80h
0x18002d786  mov     r8d, ebx; Size
0x18002d789  xor     edx, edx; Val
0x18002d78b  lea     rcx, [rbp+3E0h+var_3D0]; void *
0x18002d78f  call    memset_0
0x18002d794  mov     r8d, ebx; Size
0x18002d797  xor     edx, edx; Val
0x18002d799  lea     rcx, [rbp+3E0h+var_350]; void *
0x18002d7a0  call    memset_0
0x18002d7a5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002d7a9  mov     [rbp+3E0h+pv], rdi
0x18002d7ad  xor     edx, edx; Val
0x18002d7af  mov     r8d, 250h; Size
0x18002d7b5  lea     rcx, [rbp+3E0h+FindFileData]; void *
0x18002d7bc  call    memset_0
0x18002d7c1  or      rdi, rbx
0x18002d7c4  lea     rax, qword_1800EE510
0x18002d7cb  mov     [rbp+3E0h+lpFileName], rax
0x18002d7cf  xor     ecx, ecx
0x18002d7d1  mov     [rbp+3E0h+var_428], rcx
0x18002d7d5  mov     [rbp+3E0h+var_410], rax
0x18002d7d9  mov     [rbp+3E0h+var_408], rcx
0x18002d7dd  mov     [rbp+3E0h+var_440], rax
0x18002d7e1  mov     [rbp+3E0h+var_438], rcx
0x18002d7e5  mov     [rbp+3E0h+var_420], rax
0x18002d7e9  mov     [rbp+3E0h+var_418], rcx
0x18002d7ed  mov     eax, 785h
0x18002d7f2  cmp     [rbp+3E0h+var_3F8], rcx
0x18002d7f6  jz      loc_18002DF67
0x18002d7fc  mov     [rsp+4E0h+var_48C], ax
0x18002d801  mov     eax, 786h
0x18002d806  test    r13, r13
0x18002d809  jz      loc_18002DF67
0x18002d80f  mov     [rsp+4E0h+var_48C], ax
0x18002d814  mov     eax, 787h
0x18002d819  test    r12, r12
0x18002d81c  jz      loc_18002DF67
0x18002d822  mov     [rsp+4E0h+var_48C], ax
0x18002d827  mov     eax, 788h
0x18002d82c  cmp     [rbp+3E0h+var_400], rcx
0x18002d830  jz      loc_18002DF67
0x18002d836  mov     [rsp+4E0h+var_48C], ax
0x18002d83b  mov     eax, 789h
0x18002d840  test    r14, r14
0x18002d843  jz      loc_18002DF67
0x18002d849  mov     [rsp+4E0h+var_48C], ax
0x18002d84e  mov     eax, 78Ah
0x18002d853  test    r15, r15
0x18002d856  jz      loc_18002DF67
0x18002d85c  mov     [rsp+4E0h+var_48C], ax
0x18002d861  xor     r15d, r15d
0x18002d864  mov     eax, 78Bh
0x18002d869  test    rsi, rsi
0x18002d86c  jz      loc_18002DF5D
0x18002d872  mov     [rsp+4E0h+var_490], r15d
0x18002d877  mov     [rsp+4E0h+var_48C], ax
0x18002d87c  mov     rdx, r12; unsigned __int16 *
0x18002d87f  lea     rcx, [rbp+3E0h+lpFileName]; this
0x18002d883  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18002d888  mov     [rsp+4E0h+var_490], eax
0x18002d88c  test    eax, eax
0x18002d88e  mov     eax, 790h
0x18002d893  js      loc_18002DF72
0x18002d899  mov     [rsp+4E0h+var_48C], ax
0x18002d89e  mov     rdx, r12; unsigned __int16 *
0x18002d8a1  lea     rcx, [rbp+3E0h+var_440]; this
0x18002d8a5  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18002d8aa  mov     [rsp+4E0h+var_490], eax
0x18002d8ae  test    eax, eax
0x18002d8b0  mov     eax, 791h
0x18002d8b5  js      loc_18002DF72
0x18002d8bb  mov     [rsp+4E0h+var_48C], ax
0x18002d8c0  lea     edx, [rbx+5Dh]; unsigned __int16
0x18002d8c3  lea     rcx, [rbp+3E0h+var_440]; this
0x18002d8c7  call    ?ReverseFind@CBsString@@QEBAJG@Z; CBsString::ReverseFind(ushort)
0x18002d8cc  mov     esi, eax
0x18002d8ce  lea     ecx, [rax+1]
0x18002d8d1  cmp     ecx, dword ptr [rbp+3E0h+var_438]
0x18002d8d4  jnb     short loc_18002D8E2
0x18002d8d6  mov     dword ptr [rbp+3E0h+var_438], ecx
0x18002d8d9  mov     rax, [rbp+3E0h+var_440]
0x18002d8dd  mov     [rax+rcx*2], r15w
0x18002d8e2  mov     rdx, r12; unsigned __int16 *
0x18002d8e5  lea     rcx, [rbp+3E0h+var_420]; this
0x18002d8e9  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18002d8ee  mov     [rsp+4E0h+var_490], eax
0x18002d8f2  test    eax, eax
0x18002d8f4  mov     eax, 79Bh
0x18002d8f9  js      loc_18002DF72
0x18002d8ff  mov     [rsp+4E0h+var_48C], ax
0x18002d904  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002d908  inc     rcx
0x18002d90b  cmp     [r12+rcx*2], r15w
0x18002d910  jnz     short loc_18002D908
0x18002d912  mov     r15d, ecx
0x18002d915  sub     r15d, esi
0x18002d918  dec     r15d
0x18002d91b  mov     r13, [rbp+3E0h+var_420]
0x18002d91f  cmp     r15d, ecx
0x18002d922  jnb     short loc_18002D958
0x18002d924  cmp     r15d, dword ptr [rbp+3E0h+var_418]
0x18002d928  jnb     short loc_18002D958
0x18002d92a  mov     ecx, r15d
0x18002d92d  lea     rsi, [r15+r15]
0x18002d931  mov     eax, dword ptr [rbp+3E0h+var_418]
0x18002d934  sub     rax, rcx
0x18002d937  lea     rdx, ds:0[rax*2]
0x18002d93f  add     rdx, r13; Src
0x18002d942  mov     r8, rsi; Size
0x18002d945  mov     rcx, r13; void *
0x18002d948  call    memmove_0
0x18002d94d  mov     dword ptr [rbp+3E0h+var_418], r15d
0x18002d951  xor     eax, eax
0x18002d953  mov     [rsi+r13], ax
0x18002d958  mov     rax, [r14]
0x18002d95b  lea     rdx, [rbp+3E0h+var_350]
0x18002d962  mov     rcx, r14
0x18002d965  mov     rax, [rax+18h]
0x18002d969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d96e  mov     [rsp+4E0h+var_490], eax
0x18002d972  xor     r15d, r15d
0x18002d975  test    eax, eax
0x18002d977  mov     eax, 7A3h
0x18002d97c  js      loc_18002DF72
0x18002d982  mov     [rsp+4E0h+var_48C], ax
0x18002d987  mov     rax, [r14]
0x18002d98a  lea     rdx, [rbp+3E0h+var_348]
0x18002d991  mov     rcx, r14
0x18002d994  mov     rax, [rax+20h]
0x18002d998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d99d  mov     [rsp+4E0h+var_490], eax
0x18002d9a1  test    eax, eax
0x18002d9a3  mov     eax, 7A4h
0x18002d9a8  js      loc_18002DF72
0x18002d9ae  mov     [rsp+4E0h+var_48C], ax
0x18002d9b3  mov     [rbp+3E0h+var_340], r15w
0x18002d9bb  mov     [rbp+3E0h+var_320], r15
0x18002d9c2  mov     [rbp+3E0h+var_318], r15d
0x18002d9c9  mov     rax, [r14]
0x18002d9cc  lea     rdx, [rbp+3E0h+var_310]
0x18002d9d3  mov     rcx, r14
0x18002d9d6  mov     rax, [rax+40h]
0x18002d9da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9df  mov     [rsp+4E0h+var_490], eax
0x18002d9e3  test    eax, eax
0x18002d9e5  mov     eax, 7A8h
0x18002d9ea  js      loc_18002DF72
0x18002d9f0  mov     [rsp+4E0h+var_48C], ax
0x18002d9f5  mov     rax, [r14]
0x18002d9f8  lea     rdx, [rbp+3E0h+var_308]
0x18002d9ff  mov     rcx, r14
0x18002da02  mov     rax, [rax+48h]
0x18002da06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da0b  mov     [rsp+4E0h+var_490], eax
0x18002da0f  test    eax, eax
0x18002da11  mov     eax, 7A9h
0x18002da16  js      loc_18002DF72
0x18002da1c  mov     [rsp+4E0h+var_48C], ax
0x18002da21  mov     rax, [r14]
0x18002da24  lea     rdx, [rbp+3E0h+var_300]
0x18002da2b  mov     rcx, r14
0x18002da2e  mov     rax, [rax+78h]
0x18002da32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da37  mov     [rsp+4E0h+var_490], eax
0x18002da3b  test    eax, eax
0x18002da3d  mov     eax, 7AAh
0x18002da42  js      loc_18002DF72
0x18002da48  mov     [rsp+4E0h+var_48C], ax
0x18002da4d  mov     [rbp+3E0h+var_2F8], r15
0x18002da54  mov     rax, [r14]
0x18002da57  lea     rdx, [rbp+3E0h+var_2F0]
0x18002da5e  mov     rcx, r14
0x18002da61  mov     rax, [rax+90h]
0x18002da68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da6d  mov     [rsp+4E0h+var_490], eax
0x18002da71  test    eax, eax
0x18002da73  mov     eax, 7ACh
0x18002da78  js      loc_18002DF72
0x18002da7e  mov     [rsp+4E0h+var_48C], ax
0x18002da83  mov     rax, [r14]
0x18002da86  lea     rdx, [rbp+3E0h+var_2E8]
0x18002da8d  mov     rcx, r14
0x18002da90  mov     rax, [rax+98h]
0x18002da97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da9c  mov     [rsp+4E0h+var_490], eax
0x18002daa0  test    eax, eax
0x18002daa2  mov     eax, 7ADh
0x18002daa7  js      loc_18002DF72
0x18002daad  mov     [rsp+4E0h+var_48C], ax
0x18002dab2  mov     rax, [r14]
0x18002dab5  lea     rdx, [rbp+3E0h+var_2E0]
0x18002dabc  mov     rcx, r14
0x18002dabf  mov     rax, [rax+80h]
0x18002dac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dacb  mov     [rsp+4E0h+var_490], eax
0x18002dacf  test    eax, eax
0x18002dad1  mov     eax, 7AEh
0x18002dad6  js      loc_18002DF72
0x18002dadc  mov     [rsp+4E0h+var_48C], ax
0x18002dae1  mov     [rbp+3E0h+var_2DC], r15
0x18002dae8  mov     esi, 80h
0x18002daed  mov     ecx, 2000080h
0x18002daf2  mov     rax, [rbp+3E0h+var_3F0]
0x18002daf6  cmp     dword ptr [rax+38h], 0Bh
0x18002dafa  cmovnz  esi, ecx
0x18002dafd  lea     rcx, [rbp+3E0h+lpFileName]; this
0x18002db01  call    ?AntiCanonicalize@CBsString@@QEAAJXZ; CBsString::AntiCanonicalize(void)
0x18002db06  mov     [rsp+4E0h+var_490], eax
0x18002db0a  test    eax, eax
0x18002db0c  mov     eax, 7BDh
0x18002db11  js      loc_18002DF72
0x18002db17  mov     [rsp+4E0h+var_48C], ax
0x18002db1c  mov     [rsp+4E0h+hTemplateFile], r15; hTemplateFile
0x18002db21  mov     [rsp+4E0h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18002db25  mov     [rsp+4E0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002db2d  xor     r9d, r9d; lpSecurityAttributes
0x18002db30  mov     edx, 80000000h; dwDesiredAccess
0x18002db35  lea     r8d, [r15+1]; dwShareMode
0x18002db39  mov     rcx, [rbp+3E0h+lpFileName]; lpFileName
0x18002db3d  call    cs:__imp_CreateFileW
0x18002db44  nop     dword ptr [rax+rax+00h]
0x18002db49  mov     rbx, rax
0x18002db4c  lea     r14, WPP_GLOBAL_Control
0x18002db53  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002db57  jz      loc_18002DC22
0x18002db5d  mov     esi, r15d
0x18002db60  mov     rcx, rax; hFile
0x18002db63  call    cs:__imp_GetFileType
0x18002db6a  nop     dword ptr [rax+rax+00h]
0x18002db6f  cmp     eax, 1
0x18002db72  jnz     loc_18002DC02
0x18002db78  lea     rdx, [rbp+3E0h+FileInformation]; lpFileInformation
0x18002db7f  mov     rcx, rbx; hFile
0x18002db82  call    cs:__imp_GetFileInformationByHandle
0x18002db89  nop     dword ptr [rax+rax+00h]
0x18002db8e  test    eax, eax
0x18002db90  jz      short loc_18002DC02
0x18002db92  mov     rax, [rbp+3E0h+var_440]
0x18002db96  mov     [rbp+3E0h+var_3D0], rax
0x18002db9a  mov     [rbp+3E0h+var_3C8], r13
0x18002db9e  mov     [rbp+3E0h+var_3C0], r15w
0x18002dba3  mov     [rbp+3E0h+var_3A0], r15
0x18002dba7  mov     [rbp+3E0h+var_398], r15d
0x18002dbab  mov     rax, qword ptr [rbp+3E0h+FileInformation.ftCreationTime.dwLowDateTime]
0x18002dbb2  mov     [rbp+3E0h+var_390], rax
0x18002dbb6  mov     rax, qword ptr [rbp+3E0h+FileInformation.ftLastWriteTime.dwLowDateTime]
0x18002dbbd  mov     [rbp+3E0h+var_388], rax
0x18002dbc1  mov     rax, qword ptr [rbp+3E0h+FileInformation.ftLastAccessTime.dwLowDateTime]
0x18002dbc8  mov     [rbp+3E0h+var_380], rax
0x18002dbcc  mov     [rbp+3E0h+var_378], r15
0x18002dbd0  mov     ecx, [rbp+3E0h+FileInformation.nFileSizeHigh]
0x18002dbd6  shl     rcx, 20h
0x18002dbda  mov     eax, [rbp+3E0h+FileInformation.nFileSizeLow]
0x18002dbe0  add     rcx, rax
0x18002dbe3  mov     [rbp+3E0h+var_370], rcx
0x18002dbe7  mov     [rbp+3E0h+var_368], rcx
0x18002dbeb  mov     eax, [rbp+3E0h+FileInformation.dwFileAttributes]
0x18002dbf1  mov     [rbp+3E0h+var_360], eax
0x18002dbf7  mov     [rbp+3E0h+var_35C], r15
  ... truncated ...
```
