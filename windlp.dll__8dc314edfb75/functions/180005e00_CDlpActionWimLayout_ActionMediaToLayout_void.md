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
__int64 __fastcall CDlpActionWimLayout::ActionMediaToLayout(CDlpActionWimLayout *this)
{
  LPCWSTR v2; // r14
  __int64 v3; // r13
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
  int v21; // eax
  int v22; // eax
  unsigned int v23; // edi
  HANDLE v24; // rax
  __int64 v25; // r15
  __int64 v26; // r12
  int v27; // eax
  HANDLE v28; // rax
  int v29; // eax
  int FolderPath; // eax
  __int64 v31; // rcx
  __int64 v32; // rcx
  signed int v33; // eax
  int v34; // eax
  int v35; // eax
  __int64 v36; // rcx
  int v37; // eax
  __int64 v38; // rcx
  __int64 v39; // rcx
  signed int LastError; // eax
  __int64 v41; // rcx
  int v42; // eax
  __int64 v43; // rcx
  int v44; // eax
  __int64 v45; // rbx
  HANDLE v46; // rax
  HANDLE v47; // rax
  HANDLE v48; // rax
  __int64 v50; // [rsp+20h] [rbp-E0h]
  int v51; // [rsp+28h] [rbp-D8h]
  int v52; // [rsp+28h] [rbp-D8h]
  _QWORD *v53; // [rsp+30h] [rbp-D0h]
  const wchar_t *v54; // [rsp+70h] [rbp-90h]
  _DWORD v55[2]; // [rsp+78h] [rbp-88h]
  const wchar_t *v56; // [rsp+80h] [rbp-80h]
  int v57; // [rsp+88h] [rbp-78h]
  const wchar_t *v58; // [rsp+90h] [rbp-70h]
  int v59; // [rsp+98h] [rbp-68h]
  const wchar_t *v60; // [rsp+A0h] [rbp-60h]
  int v61; // [rsp+A8h] [rbp-58h]
  const wchar_t *v62; // [rsp+B0h] [rbp-50h]
  int v63; // [rsp+B8h] [rbp-48h]
  _QWORD v64[2]; // [rsp+C0h] [rbp-40h] BYREF
  int v65; // [rsp+D0h] [rbp-30h]
  int v66; // [rsp+D4h] [rbp-2Ch]
  __int64 v67; // [rsp+D8h] [rbp-28h]
  void *v68; // [rsp+E0h] [rbp-20h]
  CDlpActionWimLayout *v69; // [rsp+E8h] [rbp-18h]
  __int64 v70; // [rsp+F0h] [rbp-10h]
  unsigned int (__fastcall *v71)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *); // [rsp+F8h] [rbp-8h]
  CDlpActionWimLayout *v72; // [rsp+100h] [rbp+0h]
  unsigned int v73; // [rsp+160h] [rbp+60h]
  LPCWSTR lpFileName; // [rsp+168h] [rbp+68h] BYREF
  __int64 v75; // [rsp+170h] [rbp+70h] BYREF
  __int64 v76; // [rsp+178h] [rbp+78h] BYREF

  v2 = 0;
  lpFileName = 0;
  v3 = 0;
  v76 = 0;
  v75 = 0;
  memset_0(v64, 0, 0x48u);
  v54 = L"Boot";
  v55[0] = 0;
  v56 = L"Efi";
  v57 = 0;
  v58 = L"Sources";
  v59 = 0;
  v60 = L"$OEM$";
  v61 = 1;
  v62 = L"AutoUnattend_Files";
  v63 = 1;
  v4 = *((_QWORD *)this + 11);
  v5 = (LPCWSTR *)((char *)this + 720);
  v53 = (_QWORD *)((char *)this + 720);
  if ( v4 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v4, 2, L"MediaLayout: Checking source layout path: [%s]", *v5);
  else
    v53 = (_QWORD *)((char *)this + 720);
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
        v51 = -2147024735;
        LODWORD(v50) = 1720;
        goto LABEL_110;
      }
      goto LABEL_113;
    }
    CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 552, 0);
    v7 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 90), L"sources\\vista", 0, &v75);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = *((_QWORD *)this + 11);
      if ( v9 )
      {
        v51 = v7;
        LODWORD(v50) = 1725;
        goto LABEL_110;
      }
      goto LABEL_113;
    }
    v10 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 552, &v75);
    v8 = v10;
    if ( v10 < 0 )
    {
      v9 = *((_QWORD *)this + 11);
      if ( v9 )
      {
        v51 = v10;
        LODWORD(v50) = 1726;
        goto LABEL_110;
      }
      goto LABEL_113;
    }
    v11 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 90), L"sources\\xp", 0, &v75);
    v8 = v11;
    if ( v11 < 0 )
    {
      v9 = *((_QWORD *)this + 11);
      if ( v9 )
      {
        v51 = v11;
        LODWORD(v50) = 1727;
        goto LABEL_110;
      }
      goto LABEL_113;
    }
    v12 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 552, &v75);
    v8 = v12;
    if ( v12 < 0 )
    {
      v9 = *((_QWORD *)this + 11);
      if ( v9 )
      {
        v51 = v12;
        LODWORD(v50) = 1728;
        goto LABEL_110;
      }
      goto LABEL_113;
    }
    v13 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 90), L"support", 0, &v75);
    v8 = v13;
    if ( v13 < 0 )
    {
      v9 = *((_QWORD *)this + 11);
      if ( v9 )
      {
        v51 = v13;
        LODWORD(v50) = 1729;
        goto LABEL_110;
      }
      goto LABEL_113;
    }
    v14 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 552, &v75);
    v8 = v14;
    if ( v14 < 0 )
    {
      v9 = *((_QWORD *)this + 11);
      if ( v9 )
      {
        v51 = v14;
        LODWORD(v50) = 1730;
        goto LABEL_110;
      }
      goto LABEL_113;
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
      v17 = *(_QWORD *)&v55[4 * v15 - 2];
      v18 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 90), v17, 0, &lpFileName);
      v8 = v18;
      if ( v18 < 0 )
        break;
      v2 = lpFileName;
      if ( (unsigned int)DirectoryExists(lpFileName) || !v55[4 * v15] )
      {
        v19 = *((_QWORD *)this + 11);
        if ( v19 )
          CDlpLogT<CEmptyType>::DlpLogFormat(v19, 2, L"MediaLayout: Calculating size of media path: [%s]...", v17);
        if ( !v2 || !*v2 )
        {
          SetLastError(0x57u);
LABEL_93:
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
            v41 = 0;
            if ( v8 >= 0 )
              goto LABEL_112;
            v51 = v8;
            LODWORD(v50) = 1752;
            v9 = *((_QWORD *)this + 11);
LABEL_110:
            v44 = CDlpLogT<CEmptyType>::DlpLogFormat(
                    v9,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDlpActionWimLayout::ActionMediaToLayout",
                    v50,
                    v51);
            v41 = (unsigned int)v44;
            if ( v44 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v44);
LABEL_112:
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v41);
          }
          goto LABEL_113;
        }
        if ( !(unsigned int)EnumeratePathEx(v2, 0) )
          goto LABEL_93;
        v20 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(this);
        v8 = v20;
        if ( v20 < 0 )
        {
          v9 = *((_QWORD *)this + 11);
          if ( !v9 )
            goto LABEL_113;
          v51 = v20;
          LODWORD(v50) = 1753;
          goto LABEL_110;
        }
        *((_QWORD *)this + 101) = *((_QWORD *)this + 101);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      if ( (unsigned int)++v15 >= 5 )
      {
        *((_QWORD *)this + 100) = 0;
        v21 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::SetProgress(this, 100, 0);
        v8 = v21;
        if ( v21 < 0 )
        {
          v9 = *((_QWORD *)this + 11);
          if ( !v9 )
            goto LABEL_113;
          v51 = v21;
          LODWORD(v50) = 1765;
          goto LABEL_110;
        }
        *((_DWORD *)this + 195) = 0;
        *((_DWORD *)this + 196) = 100;
        v22 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::ResetActionProgress(this);
        v8 = v22;
        if ( v22 < 0 )
        {
          v9 = *((_QWORD *)this + 11);
          if ( !v9 )
            goto LABEL_113;
          v51 = v22;
          LODWORD(v50) = 1774;
          goto LABEL_110;
        }
        v23 = 0;
        v73 = 0;
        while ( 1 )
        {
          if ( v2 )
          {
            v24 = GetProcessHeap();
            HeapFree(v24, 0, (LPVOID)(v2 - 2));
            v23 = v73;
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            lpFileName = 0;
          }
          v25 = 2LL * v23;
          v26 = *(_QWORD *)&v55[4 * v23 - 2];
          v27 = CMiscHelpersT<CEmptyType>::CombinePath(*v53, v26, 0, &lpFileName);
          v8 = v27;
          if ( v27 < 0 )
            break;
          v2 = lpFileName;
          if ( (unsigned int)DirectoryExists(lpFileName) || !v55[2 * v25] )
          {
            if ( v3 )
            {
              v28 = GetProcessHeap();
              HeapFree(v28, 0, (LPVOID)(v3 - 4));
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              v76 = 0;
            }
            v29 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 91), v26, 0, &v76);
            v8 = v29;
            if ( v29 < 0 )
            {
              v36 = *((_QWORD *)this + 11);
              if ( v36 )
              {
                LODWORD(v50) = 1789;
                v37 = CDlpLogT<CEmptyType>::DlpLogFormat(
                        v36,
                        4,
                        L"%s(%d): Result = 0x%X",
                        L"CDlpActionWimLayout::ActionMediaToLayout",
                        v50,
                        v29);
                v38 = (unsigned int)v37;
                if ( v37 < 0 )
                  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v37);
                CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v38);
              }
              v3 = v76;
              goto LABEL_113;
            }
            v3 = v76;
            FolderPath = CMiscHelpersT<CEmptyType>::CreateFolderPath(v76);
            v8 = FolderPath;
            v9 = *((_QWORD *)this + 11);
            if ( FolderPath < 0 )
            {
              if ( !v9 )
                goto LABEL_113;
              v51 = FolderPath;
              LODWORD(v50) = 1793;
              goto LABEL_110;
            }
            v65 = 0;
            v67 = 0;
            v70 = 0;
            v64[0] = v2;
            v64[1] = v3;
            v71 = CDlpActionWimLayout::CopyProgressRoutine;
            v72 = this;
            v68 = &CDlpActionWimLayout::CopyCallbackRoutine;
            v69 = this;
            v66 = 18;
            if ( v9 )
              CDlpLogT<CEmptyType>::DlpLogFormat(v9, 2, L"MediaLayout: Copying layout path: [%s]...", v26);
            if ( !(unsigned int)CopyDirectoryEx2(v64) )
            {
              if ( !(unsigned int)DirectoryExists(v2) )
              {
                v31 = *((_QWORD *)this + 11);
                if ( v31 )
                  CDlpLogT<CEmptyType>::DlpLogFormat(v31, 4, L"MediaLayout: %s doesn't exist any more", v2);
              }
              if ( !(unsigned int)DirectoryExists(v3) )
              {
                v32 = *((_QWORD *)this + 11);
                if ( v32 )
                  CDlpLogT<CEmptyType>::DlpLogFormat(v32, 4, L"MediaLayout: %s doesn't exist any more", v3);
              }
              v33 = GetLastError();
              v8 = v33;
              if ( v33 > 0 )
                v8 = (unsigned __int16)v33 | 0x80070000;
              if ( v8 == -2147023673 )
              {
                v8 = -2147023661;
LABEL_77:
                v9 = *((_QWORD *)this + 11);
                if ( !v9 )
                  goto LABEL_113;
                v51 = v8;
                LODWORD(v50) = 1819;
                goto LABEL_110;
              }
              if ( v8 < 0 )
                goto LABEL_77;
            }
            v34 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(this);
            v8 = v34;
            if ( v34 < 0 )
            {
              v9 = *((_QWORD *)this + 11);
              if ( !v9 )
                goto LABEL_113;
              v51 = v34;
              LODWORD(v50) = 1821;
              goto LABEL_110;
            }
          }
          v23 = v73 + 1;
          v73 = v23;
          if ( v23 >= 5 )
          {
            v35 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::SetProgress(
                    this,
                    100,
                    100);
            v8 = v35;
            if ( v35 < 0 )
            {
              v9 = *((_QWORD *)this + 11);
              if ( v9 )
              {
                v51 = v35;
                LODWORD(v50) = 1827;
                goto LABEL_110;
              }
            }
            goto LABEL_113;
          }
        }
        v39 = *((_QWORD *)this + 11);
        if ( !v39 )
          goto LABEL_105;
        v52 = v27;
        LODWORD(v50) = 1781;
LABEL_102:
        v42 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v39,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionWimLayout::ActionMediaToLayout",
                v50,
                v52);
        v43 = (unsigned int)v42;
        if ( v42 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v42);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v43);
        goto LABEL_105;
      }
    }
    v39 = *((_QWORD *)this + 11);
    if ( v39 )
    {
      v52 = v18;
      LODWORD(v50) = 1738;
      goto LABEL_102;
    }
LABEL_105:
    v2 = lpFileName;
    goto LABEL_113;
  }
  v8 = -2147024735;
  v9 = *((_QWORD *)this + 11);
  if ( v9 )
  {
    v51 = -2147024735;
    LODWORD(v50) = 1718;
    goto LABEL_110;
  }
LABEL_113:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
  v45 = v75;
  if ( v75 )
  {
    v46 = GetProcessHeap();
    HeapFree(v46, 0, (LPVOID)(v45 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v3 )
  {
    v47 = GetProcessHeap();
    HeapFree(v47, 0, (LPVOID)(v3 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v2 )
  {
    v48 = GetProcessHeap();
    HeapFree(v48, 0, (LPVOID)(v2 - 2));
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
