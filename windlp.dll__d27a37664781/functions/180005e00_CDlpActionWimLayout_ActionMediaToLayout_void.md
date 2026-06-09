# CDlpActionWimLayout::ActionMediaToLayout(void)

- ea: `0x180005e00`
- end: `0x1800066fa`
- name: `?ActionMediaToLayout@CDlpActionWimLayout@@AEAAJXZ`
- size: `2298`
- prototype: `__int64 __fastcall(CDlpActionWimLayout *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016870`

## callees

- `0x180005e00`
- `0x180007bbc`
- `0x18000aba4`
- `0x18000abc4`
- `0x18000b9a8`
- `0x18000d888`
- `0x180012f5c`
- `0x18001fd60`
- `0x180027f1c`
- `0x18002b5bc`
- `0x18002baec`
- `0x18003924c`
- `0x1800392f4`
- `0x18003a4c8`
- `0x18003b04c`
- `0x18007ec9a`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005ec5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005f0c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005ec5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005f0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000609c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000628e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006301`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006684`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000609c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000628e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006301`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006684`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000629d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006310`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006693`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000629d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006310`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006693`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006583`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000640d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000640d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006589`

## string_xrefs

- `0x180005eac`: `MediaLayout: Checking source layout path: [%s]`
- `0x180005ef6`: `MediaLayout: Checking target layout path: [%s]`
- `0x180006117`: `MediaLayout: Calculating size of media path: [%s]...`
- `0x1800063a1`: `MediaLayout: Copying layout path: [%s]...`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDlpActionWimLayout::ActionMediaToLayout(CDlpActionWimLayout *this)
{
  LPCWSTR v2; // r14
  wchar_t *v3; // r13
  __int64 v4; // rcx
  LPCWSTR *v5; // rbx
  __int64 v6; // rcx
  int v7; // eax
  signed int v8; // edi
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // r15d
  HANDLE ProcessHeap; // rax
  __int64 v17; // r12
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rbx
  int v22; // eax
  unsigned __int64 v23; // rax
  int v24; // eax
  int v25; // eax
  unsigned int v26; // edi
  HANDLE v27; // rax
  __int64 v28; // r15
  __int64 v29; // r12
  int v30; // eax
  HANDLE v31; // rax
  int v32; // eax
  int FolderPath; // eax
  __int64 v34; // rcx
  __int64 v35; // rcx
  signed int v36; // eax
  int v37; // eax
  int v38; // eax
  __int64 v39; // rcx
  int v40; // eax
  __int64 v41; // rcx
  __int64 v42; // rcx
  signed int LastError; // eax
  __int64 v44; // rcx
  int v45; // eax
  __int64 v46; // rcx
  int v47; // eax
  __int64 v48; // rbx
  HANDLE v49; // rax
  HANDLE v50; // rax
  HANDLE v51; // rax
  __int64 v53; // [rsp+20h] [rbp-E0h]
  int v54; // [rsp+28h] [rbp-D8h]
  int v55; // [rsp+28h] [rbp-D8h]
  _QWORD *v56; // [rsp+30h] [rbp-D0h]
  _QWORD v57[3]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v58; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v59; // [rsp+60h] [rbp-A0h]
  const wchar_t *v60; // [rsp+70h] [rbp-90h]
  _DWORD v61[2]; // [rsp+78h] [rbp-88h]
  const wchar_t *v62; // [rsp+80h] [rbp-80h]
  int v63; // [rsp+88h] [rbp-78h]
  const wchar_t *v64; // [rsp+90h] [rbp-70h]
  int v65; // [rsp+98h] [rbp-68h]
  const wchar_t *v66; // [rsp+A0h] [rbp-60h]
  int v67; // [rsp+A8h] [rbp-58h]
  const wchar_t *v68; // [rsp+B0h] [rbp-50h]
  int v69; // [rsp+B8h] [rbp-48h]
  _QWORD v70[2]; // [rsp+C0h] [rbp-40h] BYREF
  int v71; // [rsp+D0h] [rbp-30h]
  int v72; // [rsp+D4h] [rbp-2Ch]
  __int64 v73; // [rsp+D8h] [rbp-28h]
  __int64 (__fastcall *v74)(const WCHAR *, __int64); // [rsp+E0h] [rbp-20h]
  CDlpActionWimLayout *v75; // [rsp+E8h] [rbp-18h]
  __int64 v76; // [rsp+F0h] [rbp-10h]
  unsigned int (__fastcall *v77)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *); // [rsp+F8h] [rbp-8h]
  CDlpActionWimLayout *v78; // [rsp+100h] [rbp+0h]
  unsigned int v79; // [rsp+160h] [rbp+60h]
  LPCWSTR lpFileName; // [rsp+168h] [rbp+68h] BYREF
  __int64 v81; // [rsp+170h] [rbp+70h] BYREF
  wchar_t *v82; // [rsp+178h] [rbp+78h] BYREF

  v2 = 0;
  lpFileName = 0;
  v3 = 0;
  v82 = 0;
  v81 = 0;
  memset_0(v70, 0, 0x48u);
  v60 = L"Boot";
  v61[0] = 0;
  v62 = L"Efi";
  v63 = 0;
  v64 = L"Sources";
  v65 = 0;
  v66 = L"$OEM$";
  v67 = 1;
  v68 = L"AutoUnattend_Files";
  v69 = 1;
  v4 = *((_QWORD *)this + 11);
  v5 = (LPCWSTR *)((char *)this + 720);
  v56 = (_QWORD *)((char *)this + 720);
  if ( v4 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v4, 2, L"MediaLayout: Checking source layout path: [%s]", *v5);
  else
    v56 = (_QWORD *)((char *)this + 720);
  if ( GetFileAttributesW(*v5) != -1 && !(unsigned int)FileExists(*v5) )
  {
    v6 = *((_QWORD *)this + 11);
    if ( v6 )
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v6,
        2,
        L"MediaLayout: Checking target layout path: [%s]",
        *((_QWORD *)this + 91));
    if ( GetFileAttributesW(*((LPCWSTR *)this + 91)) == -1 || (unsigned int)FileExists(*((_QWORD *)this + 91)) )
    {
      v8 = -2147024735;
      v9 = *((_QWORD *)this + 11);
      if ( v9 )
      {
        v54 = -2147024735;
        LODWORD(v53) = 1720;
        goto LABEL_117;
      }
      goto LABEL_120;
    }
    CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 552, 0);
    v7 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 90), L"sources\\vista", 0, &v81);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = *((_QWORD *)this + 11);
      if ( v9 )
      {
        v54 = v7;
        LODWORD(v53) = 1725;
        goto LABEL_117;
      }
      goto LABEL_120;
    }
    v10 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 552, &v81);
    v8 = v10;
    if ( v10 < 0 )
    {
      v9 = *((_QWORD *)this + 11);
      if ( v9 )
      {
        v54 = v10;
        LODWORD(v53) = 1726;
        goto LABEL_117;
      }
      goto LABEL_120;
    }
    v11 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 90), L"sources\\xp", 0, &v81);
    v8 = v11;
    if ( v11 < 0 )
    {
      v9 = *((_QWORD *)this + 11);
      if ( v9 )
      {
        v54 = v11;
        LODWORD(v53) = 1727;
        goto LABEL_117;
      }
      goto LABEL_120;
    }
    v12 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 552, &v81);
    v8 = v12;
    if ( v12 < 0 )
    {
      v9 = *((_QWORD *)this + 11);
      if ( v9 )
      {
        v54 = v12;
        LODWORD(v53) = 1728;
        goto LABEL_117;
      }
      goto LABEL_120;
    }
    v13 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 90), L"support", 0, &v81);
    v8 = v13;
    if ( v13 < 0 )
    {
      v9 = *((_QWORD *)this + 11);
      if ( v9 )
      {
        v54 = v13;
        LODWORD(v53) = 1729;
        goto LABEL_117;
      }
      goto LABEL_120;
    }
    v14 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 552, &v81);
    v8 = v14;
    if ( v14 < 0 )
    {
      v9 = *((_QWORD *)this + 11);
      if ( v9 )
      {
        v54 = v14;
        LODWORD(v53) = 1730;
        goto LABEL_117;
      }
      goto LABEL_120;
    }
    *((_QWORD *)this + 101) = 0;
    v15 = 0;
    while ( 1 )
    {
      if ( v2 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)(v2 - 2));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        lpFileName = 0;
      }
      v17 = *(_QWORD *)&v61[4 * v15 - 2];
      v18 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 90), v17, 0, &lpFileName);
      v8 = v18;
      if ( v18 < 0 )
        break;
      v2 = lpFileName;
      if ( (unsigned int)DirectoryExists(lpFileName) || !v61[4 * v15] )
      {
        v19 = *((_QWORD *)this + 11);
        if ( v19 )
          CDlpLogT<CEmptyType>::DlpLogFormat(v19, 2, L"MediaLayout: Calculating size of media path: [%s]...", v17);
        v58 = 0;
        v59 = 0;
        if ( !v2 || !*v2 )
        {
          SetLastError(0x57u);
LABEL_100:
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError )
          {
            if ( LastError > 0 )
              v8 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v8 = -2147467259;
          }
          if ( *((_QWORD *)this + 11) )
          {
            v44 = 0;
            if ( v8 >= 0 )
              goto LABEL_119;
            v54 = v8;
            LODWORD(v53) = 1752;
            v9 = *((_QWORD *)this + 11);
LABEL_117:
            v47 = CDlpLogT<CEmptyType>::DlpLogFormat(
                    v9,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDlpActionWimLayout::ActionMediaToLayout",
                    v53,
                    v54);
            v44 = (unsigned int)v47;
            if ( v47 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v47);
LABEL_119:
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v44);
          }
          goto LABEL_120;
        }
        *((_QWORD *)&v58 + 1) = CDlpActionWimLayout::CopyCallbackRoutine;
        *(_QWORD *)&v59 = this;
        v57[0] = 1;
        v57[1] = &v58;
        v57[2] = GetDirectorySizeCallback;
        v20 = EnumeratePathEx(
                v2,
                (__int64 (__fastcall *)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64))EnumeratePathDirCallback,
                (__int64 (__fastcall *)(DWORD *, __int64))EnumeratePathFileCallback,
                (__int64)v57,
                0);
        v21 = 0;
        if ( v20 == 1 )
          v21 = *((_QWORD *)&v59 + 1);
        if ( !v20 )
          goto LABEL_100;
        v22 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(this);
        v8 = v22;
        if ( v22 < 0 )
        {
          v9 = *((_QWORD *)this + 11);
          if ( !v9 )
            goto LABEL_120;
          v54 = v22;
          LODWORD(v53) = 1753;
          goto LABEL_117;
        }
        v23 = *((_QWORD *)this + 101);
        if ( v23 + v21 < v23 )
        {
          v8 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          *((_QWORD *)this + 101) = v23 + v21;
          v8 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
        if ( v8 < 0 )
        {
          v9 = *((_QWORD *)this + 11);
          if ( !v9 )
            goto LABEL_120;
          v54 = v8;
          LODWORD(v53) = 1757;
          goto LABEL_117;
        }
      }
      if ( (unsigned int)++v15 >= 5 )
      {
        *((_QWORD *)this + 100) = 0;
        v24 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::SetProgress(this, 100, 0);
        v8 = v24;
        if ( v24 < 0 )
        {
          v9 = *((_QWORD *)this + 11);
          if ( !v9 )
            goto LABEL_120;
          v54 = v24;
          LODWORD(v53) = 1765;
          goto LABEL_117;
        }
        *((_DWORD *)this + 195) = 0;
        *((_DWORD *)this + 196) = 100;
        v25 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::ResetActionProgress(this);
        v8 = v25;
        if ( v25 < 0 )
        {
          v9 = *((_QWORD *)this + 11);
          if ( !v9 )
            goto LABEL_120;
          v54 = v25;
          LODWORD(v53) = 1774;
          goto LABEL_117;
        }
        v26 = 0;
        v79 = 0;
        while ( 1 )
        {
          if ( v2 )
          {
            v27 = GetProcessHeap();
            HeapFree(v27, 0, (LPVOID)(v2 - 2));
            v26 = v79;
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            lpFileName = 0;
          }
          v28 = 2LL * v26;
          v29 = *(_QWORD *)&v61[4 * v26 - 2];
          v30 = CMiscHelpersT<CEmptyType>::CombinePath(*v56, v29, 0, &lpFileName);
          v8 = v30;
          if ( v30 < 0 )
            break;
          v2 = lpFileName;
          if ( (unsigned int)DirectoryExists(lpFileName) || !v61[2 * v28] )
          {
            if ( v3 )
            {
              v31 = GetProcessHeap();
              HeapFree(v31, 0, v3 - 2);
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              v82 = 0;
            }
            v32 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 91), v29, 0, &v82);
            v8 = v32;
            if ( v32 < 0 )
            {
              v39 = *((_QWORD *)this + 11);
              if ( v39 )
              {
                LODWORD(v53) = 1789;
                v40 = CDlpLogT<CEmptyType>::DlpLogFormat(
                        v39,
                        4,
                        L"%s(%d): Result = 0x%X",
                        L"CDlpActionWimLayout::ActionMediaToLayout",
                        v53,
                        v32);
                v41 = (unsigned int)v40;
                if ( v40 < 0 )
                  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v40);
                CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v41);
              }
              v3 = v82;
              goto LABEL_120;
            }
            v3 = v82;
            FolderPath = CMiscHelpersT<CEmptyType>::CreateFolderPath(v82);
            v8 = FolderPath;
            v9 = *((_QWORD *)this + 11);
            if ( FolderPath < 0 )
            {
              if ( !v9 )
                goto LABEL_120;
              v54 = FolderPath;
              LODWORD(v53) = 1793;
              goto LABEL_117;
            }
            v71 = 0;
            v73 = 0;
            v76 = 0;
            v70[0] = v2;
            v70[1] = v3;
            v77 = CDlpActionWimLayout::CopyProgressRoutine;
            v78 = this;
            v74 = CDlpActionWimLayout::CopyCallbackRoutine;
            v75 = this;
            v72 = 18;
            if ( v9 )
              CDlpLogT<CEmptyType>::DlpLogFormat(v9, 2, L"MediaLayout: Copying layout path: [%s]...", v29);
            if ( !(unsigned int)CopyDirectoryEx2(v70) )
            {
              if ( !(unsigned int)DirectoryExists(v2) )
              {
                v34 = *((_QWORD *)this + 11);
                if ( v34 )
                  CDlpLogT<CEmptyType>::DlpLogFormat(v34, 4, L"MediaLayout: %s doesn't exist any more", v2);
              }
              if ( !(unsigned int)DirectoryExists(v3) )
              {
                v35 = *((_QWORD *)this + 11);
                if ( v35 )
                  CDlpLogT<CEmptyType>::DlpLogFormat(v35, 4, L"MediaLayout: %s doesn't exist any more", v3);
              }
              v36 = GetLastError();
              v8 = v36;
              if ( v36 > 0 )
                v8 = (unsigned __int16)v36 | 0x80070000;
              if ( v8 == -2147023673 )
              {
                v8 = -2147023661;
LABEL_82:
                v9 = *((_QWORD *)this + 11);
                if ( !v9 )
                  goto LABEL_120;
                v54 = v8;
                LODWORD(v53) = 1819;
                goto LABEL_117;
              }
              if ( v8 < 0 )
                goto LABEL_82;
            }
            v37 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(this);
            v8 = v37;
            if ( v37 < 0 )
            {
              v9 = *((_QWORD *)this + 11);
              if ( !v9 )
                goto LABEL_120;
              v54 = v37;
              LODWORD(v53) = 1821;
              goto LABEL_117;
            }
          }
          v26 = v79 + 1;
          v79 = v26;
          if ( v26 >= 5 )
          {
            v38 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::SetProgress(
                    this,
                    100,
                    100);
            v8 = v38;
            if ( v38 < 0 )
            {
              v9 = *((_QWORD *)this + 11);
              if ( v9 )
              {
                v54 = v38;
                LODWORD(v53) = 1827;
                goto LABEL_117;
              }
            }
            goto LABEL_120;
          }
        }
        v42 = *((_QWORD *)this + 11);
        if ( !v42 )
          goto LABEL_112;
        v55 = v30;
        LODWORD(v53) = 1781;
LABEL_109:
        v45 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v42,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionWimLayout::ActionMediaToLayout",
                v53,
                v55);
        v46 = (unsigned int)v45;
        if ( v45 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v45);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v46);
        goto LABEL_112;
      }
    }
    v42 = *((_QWORD *)this + 11);
    if ( v42 )
    {
      v55 = v18;
      LODWORD(v53) = 1738;
      goto LABEL_109;
    }
LABEL_112:
    v2 = lpFileName;
    goto LABEL_120;
  }
  v8 = -2147024735;
  v9 = *((_QWORD *)this + 11);
  if ( v9 )
  {
    v54 = -2147024735;
    LODWORD(v53) = 1718;
    goto LABEL_117;
  }
LABEL_120:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
  v48 = v81;
  if ( v81 )
  {
    v49 = GetProcessHeap();
    HeapFree(v49, 0, (LPVOID)(v48 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v3 )
  {
    v50 = GetProcessHeap();
    HeapFree(v50, 0, v3 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v2 )
  {
    v51 = GetProcessHeap();
    HeapFree(v51, 0, (LPVOID)(v2 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005e00  push    rbp
0x180005e02  push    rbx
0x180005e03  push    rsi
0x180005e04  push    rdi
0x180005e05  push    r12
0x180005e07  push    r13
0x180005e09  push    r14
0x180005e0b  push    r15
0x180005e0d  lea     rbp, [rsp-18h]
0x180005e12  sub     rsp, 118h
0x180005e19  mov     rsi, rcx
0x180005e1c  xor     r14d, r14d
0x180005e1f  mov     [rbp+50h+lpFileName], r14
0x180005e23  xor     r13d, r13d
0x180005e26  mov     [rbp+50h+arg_18], r13
0x180005e2a  mov     [rbp+50h+arg_10], r13
0x180005e2e  xor     edx, edx; Val
0x180005e30  lea     r8d, [r14+48h]; Size
0x180005e34  lea     rcx, [rbp+50h+var_90]; void *
0x180005e38  call    memset_0
0x180005e3d  lea     rax, aBoot; "Boot"
0x180005e44  mov     [rsp+150h+var_E0], rax
0x180005e49  mov     [rsp+150h+var_D8], r13d
0x180005e4e  lea     rax, aEfi_0; "Efi"
0x180005e55  mov     [rbp+50h+var_D0], rax
0x180005e59  mov     [rbp+50h+var_C8], r13d
0x180005e5d  lea     rax, aSources_0; "Sources"
0x180005e64  mov     [rbp+50h+var_C0], rax
0x180005e68  mov     [rbp+50h+var_B8], r13d
0x180005e6c  lea     rax, aOem; "$OEM$"
0x180005e73  mov     [rbp+50h+var_B0], rax
0x180005e77  mov     [rbp+50h+var_A8], 1
0x180005e7e  lea     rax, aAutounattendFi; "AutoUnattend_Files"
0x180005e85  mov     [rbp+50h+var_A0], rax
0x180005e89  mov     [rbp+50h+var_98], 1
0x180005e90  mov     rcx, [rsi+58h]
0x180005e94  lea     rbx, [rsi+2D0h]
0x180005e9b  mov     [rsp+150h+var_120], rbx
0x180005ea0  lea     r15d, [r14+2]
0x180005ea4  test    rcx, rcx
0x180005ea7  jz      short loc_180005EBD
0x180005ea9  mov     r9, [rbx]
0x180005eac  lea     r8, aMedialayoutChe_0; "MediaLayout: Checking source layout pat"...
0x180005eb3  mov     edx, r15d
0x180005eb6  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180005ebb  jmp     short loc_180005EC2
0x180005ebd  mov     [rsp+150h+var_120], rbx
0x180005ec2  mov     rcx, [rbx]; lpFileName
0x180005ec5  call    cs:__imp_GetFileAttributesW
0x180005ecb  or      edi, 0FFFFFFFFh
0x180005ece  cmp     eax, edi
0x180005ed0  jz      loc_18000662F
0x180005ed6  mov     rcx, [rbx]
0x180005ed9  call    FileExists
0x180005ede  test    eax, eax
0x180005ee0  jnz     loc_18000662F
0x180005ee6  mov     rcx, [rsi+58h]
0x180005eea  test    rcx, rcx
0x180005eed  jz      short loc_180005F05
0x180005eef  mov     r9, [rsi+2D8h]
0x180005ef6  lea     r8, aMedialayoutChe; "MediaLayout: Checking target layout pat"...
0x180005efd  mov     edx, r15d
0x180005f00  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180005f05  mov     rcx, [rsi+2D8h]; lpFileName
0x180005f0c  call    cs:__imp_GetFileAttributesW
0x180005f12  cmp     eax, edi
0x180005f14  jz      loc_180006611
0x180005f1a  mov     rcx, [rsi+2D8h]
0x180005f21  call    FileExists
0x180005f26  test    eax, eax
0x180005f28  jnz     loc_180006611
0x180005f2e  lea     rbx, [rsi+228h]
0x180005f35  xor     edx, edx
0x180005f37  mov     rcx, rbx
0x180005f3a  call    ?SetSize@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180005f3f  lea     r9, [rbp+50h+arg_10]
0x180005f43  xor     r8d, r8d
0x180005f46  lea     rdx, aSourcesVista; "sources\\vista"
0x180005f4d  mov     rcx, [rsi+2D0h]
0x180005f54  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180005f59  mov     edi, eax
0x180005f5b  test    eax, eax
0x180005f5d  jns     short loc_180005F7D
0x180005f5f  mov     rcx, [rsi+58h]
0x180005f63  test    rcx, rcx
0x180005f66  jz      loc_180006673
0x180005f6c  mov     [rsp+150h+var_128], eax
0x180005f70  mov     dword ptr [rsp+150h+var_130], 6BDh
0x180005f78  jmp     loc_18000664B
0x180005f7d  lea     rdx, [rbp+50h+arg_10]
0x180005f81  mov     rcx, rbx
0x180005f84  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x180005f89  mov     edi, eax
0x180005f8b  test    eax, eax
0x180005f8d  jns     short loc_180005FAD
0x180005f8f  mov     rcx, [rsi+58h]
0x180005f93  test    rcx, rcx
0x180005f96  jz      loc_180006673
0x180005f9c  mov     [rsp+150h+var_128], eax
0x180005fa0  mov     dword ptr [rsp+150h+var_130], 6BEh
0x180005fa8  jmp     loc_18000664B
0x180005fad  lea     r9, [rbp+50h+arg_10]
0x180005fb1  xor     r8d, r8d
0x180005fb4  lea     rdx, aSourcesXp; "sources\\xp"
0x180005fbb  mov     rcx, [rsi+2D0h]
0x180005fc2  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180005fc7  mov     edi, eax
0x180005fc9  test    eax, eax
0x180005fcb  jns     short loc_180005FEB
0x180005fcd  mov     rcx, [rsi+58h]
0x180005fd1  test    rcx, rcx
0x180005fd4  jz      loc_180006673
0x180005fda  mov     [rsp+150h+var_128], eax
0x180005fde  mov     dword ptr [rsp+150h+var_130], 6BFh
0x180005fe6  jmp     loc_18000664B
0x180005feb  lea     rdx, [rbp+50h+arg_10]
0x180005fef  mov     rcx, rbx
0x180005ff2  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x180005ff7  mov     edi, eax
0x180005ff9  test    eax, eax
0x180005ffb  jns     short loc_18000601B
0x180005ffd  mov     rcx, [rsi+58h]
0x180006001  test    rcx, rcx
0x180006004  jz      loc_180006673
0x18000600a  mov     [rsp+150h+var_128], eax
0x18000600e  mov     dword ptr [rsp+150h+var_130], 6C0h
0x180006016  jmp     loc_18000664B
0x18000601b  lea     r9, [rbp+50h+arg_10]
0x18000601f  xor     r8d, r8d
0x180006022  lea     rdx, aSupport; "support"
0x180006029  mov     rcx, [rsi+2D0h]
0x180006030  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180006035  mov     edi, eax
0x180006037  test    eax, eax
0x180006039  jns     short loc_180006059
0x18000603b  mov     rcx, [rsi+58h]
0x18000603f  test    rcx, rcx
0x180006042  jz      loc_180006673
0x180006048  mov     [rsp+150h+var_128], eax
0x18000604c  mov     dword ptr [rsp+150h+var_130], 6C1h
0x180006054  jmp     loc_18000664B
0x180006059  lea     rdx, [rbp+50h+arg_10]
0x18000605d  mov     rcx, rbx
0x180006060  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x180006065  mov     edi, eax
0x180006067  test    eax, eax
0x180006069  jns     short loc_180006089
0x18000606b  mov     rcx, [rsi+58h]
0x18000606f  test    rcx, rcx
0x180006072  jz      loc_180006673
0x180006078  mov     [rsp+150h+var_128], eax
0x18000607c  mov     dword ptr [rsp+150h+var_130], 6C2h
0x180006084  jmp     loc_18000664B
0x180006089  mov     qword ptr [rsi+328h], 0
0x180006094  xor     r15d, r15d
0x180006097  test    r14, r14
0x18000609a  jz      short loc_1800060C0
0x18000609c  call    cs:__imp_GetProcessHeap
0x1800060a2  mov     rcx, rax; hHeap
0x1800060a5  lea     r8, [r14-4]; lpMem
0x1800060a9  xor     edx, edx; dwFlags
0x1800060ab  call    cs:__imp_HeapFree
0x1800060b1  xor     ecx, ecx
0x1800060b3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800060b8  mov     [rbp+50h+lpFileName], 0
0x1800060c0  mov     ebx, r15d
0x1800060c3  mov     eax, r15d
0x1800060c6  add     rax, rax
0x1800060c9  mov     r12, [rsp+rax*8+150h+var_E0]
0x1800060ce  lea     r9, [rbp+50h+lpFileName]
0x1800060d2  xor     r8d, r8d
0x1800060d5  mov     rdx, r12
0x1800060d8  mov     rcx, [rsi+2D0h]
0x1800060df  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800060e4  mov     edi, eax
0x1800060e6  test    eax, eax
0x1800060e8  js      loc_1800065CE
0x1800060ee  mov     r14, [rbp+50h+lpFileName]
0x1800060f2  mov     rcx, r14
0x1800060f5  call    DirectoryExists
0x1800060fa  test    eax, eax
0x1800060fc  jnz     short loc_18000610B
0x1800060fe  add     rbx, rbx
0x180006101  cmp     [rsp+rbx*8+150h+var_D8], eax
0x180006105  jnz     loc_1800061FA
0x18000610b  mov     rcx, [rsi+58h]
0x18000610f  test    rcx, rcx
0x180006112  jz      short loc_180006128
0x180006114  mov     r9, r12
0x180006117  lea     r8, aMedialayoutCal; "MediaLayout: Calculating size of media "...
0x18000611e  mov     edx, 2
0x180006123  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180006128  xorps   xmm0, xmm0
0x18000612b  movups  [rsp+150h+var_100], xmm0
0x180006130  movups  [rsp+150h+var_F0], xmm0
0x180006135  test    r14, r14
0x180006138  jz      loc_18000657E
0x18000613e  xor     eax, eax
0x180006140  cmp     ax, [r14]
0x180006144  jz      loc_18000657E
0x18000614a  lea     rax, ?CopyCallbackRoutine@CDlpActionWimLayout@@CA?AW4FILE_ENUM_ACTION@@PEBGPEAX@Z; CDlpActionWimLayout::CopyCallbackRoutine(ushort const *,void *)
0x180006151  mov     qword ptr [rsp+150h+var_100+8], rax
0x180006156  mov     qword ptr [rsp+150h+var_F0], rsi
0x18000615b  mov     [rsp+150h+var_118], 1
0x180006164  lea     rax, [rsp+150h+var_100]
0x180006169  mov     [rsp+150h+var_110], rax
0x18000616e  lea     rax, GetDirectorySizeCallback
0x180006175  mov     [rsp+150h+var_108], rax
0x18000617a  mov     dword ptr [rsp+150h+var_130], 0; int
0x180006182  lea     r9, [rsp+150h+var_118]
0x180006187  lea     r8, EnumeratePathFileCallback
0x18000618e  lea     rdx, EnumeratePathDirCallback
0x180006195  mov     rcx, r14; lpFileName
0x180006198  call    EnumeratePathEx
0x18000619d  xor     ebx, ebx
0x18000619f  cmp     eax, 1
0x1800061a2  cmovz   rbx, qword ptr [rsp+150h+var_F0+8]
0x1800061a8  test    eax, eax
0x1800061aa  jz      loc_180006589
0x1800061b0  mov     rcx, rsi
0x1800061b3  call    ?CheckUserInterrupt@?$CDlpActionImpl@V?$CDlpErrorImpl@V?$CDlpObjectInternalImpl@V?$CUnknownImpl@VIDlpAction@@@@@@@@@@QEAAJPEAW4WINDLP_INTERRUPT_REASON@@@Z; CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(WINDLP_INTERRUPT_REASON *)
0x1800061b8  mov     edi, eax
0x1800061ba  test    eax, eax
0x1800061bc  js      loc_180006560
0x1800061c2  mov     rax, [rsi+328h]
0x1800061c9  lea     rcx, [rax+rbx]
0x1800061cd  cmp     rcx, rax
0x1800061d0  jb      short loc_1800061DD
0x1800061d2  mov     [rsi+328h], rcx
0x1800061d9  xor     edi, edi
0x1800061db  jmp     short loc_1800061EB
0x1800061dd  mov     eax, 80070216h
0x1800061e2  mov     edi, eax
0x1800061e4  mov     ecx, eax
0x1800061e6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800061eb  mov     ecx, edi
0x1800061ed  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800061f2  test    edi, edi
0x1800061f4  js      loc_180006542
0x1800061fa  inc     r15d
0x1800061fd  cmp     r15d, 5
0x180006201  jb      loc_180006097
0x180006207  mov     qword ptr [rsi+320h], 0
0x180006212  mov     ebx, 64h ; 'd'
0x180006217  xor     r8d, r8d
0x18000621a  mov     edx, ebx
0x18000621c  mov     rcx, rsi
0x18000621f  call    ?SetProgress@?$CDlpActionImpl@V?$CDlpErrorImpl@V?$CDlpObjectInternalImpl@V?$CUnknownImpl@VIDlpAction@@@@@@@@@@QEAAJT_ULARGE_INTEGER@@0@Z; CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::SetProgress(_ULARGE_INTEGER,_ULARGE_INTEGER)
0x180006224  mov     edi, eax
0x180006226  test    eax, eax
0x180006228  jns     short loc_180006248
0x18000622a  mov     rcx, [rsi+58h]
0x18000622e  test    rcx, rcx
0x180006231  jz      loc_180006673
0x180006237  mov     [rsp+150h+var_128], eax
0x18000623b  mov     dword ptr [rsp+150h+var_130], 6E5h
0x180006243  jmp     loc_18000664B
0x180006248  mov     dword ptr [rsi+30Ch], 0
0x180006252  mov     [rsi+310h], ebx
0x180006258  mov     rcx, rsi
0x18000625b  call    ?ResetActionProgress@?$CDlpActionImpl@V?$CDlpErrorImpl@V?$CDlpObjectInternalImpl@V?$CUnknownImpl@VIDlpAction@@@@@@@@@@QEAAJXZ; CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::ResetActionProgress(void)
0x180006260  mov     edi, eax
0x180006262  test    eax, eax
0x180006264  jns     short loc_180006284
0x180006266  mov     rcx, [rsi+58h]
0x18000626a  test    rcx, rcx
0x18000626d  jz      loc_180006673
0x180006273  mov     [rsp+150h+var_128], eax
0x180006277  mov     dword ptr [rsp+150h+var_130], 6EEh
0x18000627f  jmp     loc_18000664B
0x180006284  xor     edi, edi
0x180006286  mov     [rbp+50h+arg_0], edi
0x180006289  test    r14, r14
0x18000628c  jz      short loc_1800062B5
0x18000628e  call    cs:__imp_GetProcessHeap
0x180006294  mov     rcx, rax; hHeap
0x180006297  lea     r8, [r14-4]; lpMem
0x18000629b  xor     edx, edx; dwFlags
0x18000629d  call    cs:__imp_HeapFree
0x1800062a3  mov     edi, [rbp+50h+arg_0]
0x1800062a6  xor     ecx, ecx
0x1800062a8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800062ad  mov     [rbp+50h+lpFileName], 0
0x1800062b5  mov     r15d, edi
0x1800062b8  add     r15, r15
0x1800062bb  mov     r12, [rsp+r15*8+150h+var_E0]
0x1800062c0  lea     r9, [rbp+50h+lpFileName]
0x1800062c4  xor     r8d, r8d
0x1800062c7  mov     rdx, r12
0x1800062ca  mov     rax, [rsp+150h+var_120]
0x1800062cf  mov     rcx, [rax]
0x1800062d2  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800062d7  mov     edi, eax
0x1800062d9  test    eax, eax
0x1800062db  js      loc_180006524
0x1800062e1  mov     r14, [rbp+50h+lpFileName]
0x1800062e5  mov     rcx, r14
0x1800062e8  call    DirectoryExists
0x1800062ed  test    eax, eax
0x1800062ef  jnz     short loc_1800062FC
  ... truncated ...
```
