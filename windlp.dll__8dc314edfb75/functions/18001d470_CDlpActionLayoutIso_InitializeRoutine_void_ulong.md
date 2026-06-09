# CDlpActionLayoutIso::InitializeRoutine(void *,ulong)

- ea: `0x18001d470`
- end: `0x18001dd9a`
- name: `?InitializeRoutine@CDlpActionLayoutIso@@EEAAJPEAXK@Z`
- size: `2346`
- prototype: `__int64 __fastcall(CDlpActionLayoutIso *__hidden this, void *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002898`
- `0x18000aba4`
- `0x18000b9a8`
- `0x18000ea20`
- `0x180012f5c`
- `0x18001d470`
- `0x18001fd60`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001d5bd`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001d5bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001db9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dbe1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dcc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dce7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001db9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dbe1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dcc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dce7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dbaa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dbf0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dcd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dcf6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dbaa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dbf0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dcd4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dcf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5c7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001d979`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001d979`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001dd68`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001dd68`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d9e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001da38`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001da7f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d9e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001da38`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001da7f`

## string_xrefs

- `0x18001d783`: `boot\etfsboot.com`
- `0x18001d7f9`: `boot\etfsboot.com`
- `0x18001d8aa`: `LayoutIso: Initializing ISO Path: [%s]`
- `0x18001d8c9`: `LayoutIso: Initializing Layout Path: [%s]`
- `0x18001d914`: `LayoutIso: Initializing BootFile Path: [%s]`
- `0x18001d939`: `LayoutIso: Initializing EFI BootFile Path: [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CDlpActionLayoutIso::InitializeRoutine(CDlpActionLayoutIso *this, unsigned int *a2, int a3)
{
  int v5; // ebx
  int *v6; // r15
  int *v7; // r13
  signed int v8; // esi
  __int64 v9; // rcx
  signed int LastError; // eax
  __int64 v11; // rcx
  _WORD *v12; // rdi
  int StringCch; // eax
  int v14; // eax
  _WORD *v15; // rdi
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  int v23; // eax
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  int *v31; // rdi
  int *v32; // r9
  __int64 v33; // rcx
  int *v34; // r9
  __int64 v35; // rcx
  HRESULT v36; // eax
  HRESULT v37; // eax
  HRESULT v38; // eax
  HRESULT v39; // eax
  _WORD *v40; // rdi
  unsigned int v41; // edx
  int Internal; // eax
  int v43; // eax
  __int64 v44; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v46; // rdi
  HANDLE v47; // rax
  _WORD *v48; // rdi
  int v49; // eax
  int v50; // eax
  HANDLE v51; // rax
  HANDLE v52; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int v56; // [rsp+28h] [rbp-D8h]
  int v57; // [rsp+28h] [rbp-D8h]
  int *v58; // [rsp+30h] [rbp-D0h] BYREF
  int *v59; // [rsp+38h] [rbp-C8h] BYREF
  int *v60; // [rsp+40h] [rbp-C0h] BYREF
  int v61; // [rsp+48h] [rbp-B8h]
  LPVOID v62; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v63; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v64; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[520]; // [rsp+70h] [rbp-90h] BYREF

  v5 = 0;
  v61 = 0;
  v64 = 0;
  v63 = 0;
  v62 = 0;
  v6 = 0;
  v59 = 0;
  v7 = 0;
  v60 = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    v9 = *((_QWORD *)this + 11);
    if ( !v9 )
      goto LABEL_138;
    v56 = -2147024809;
    LODWORD(ppv) = 119;
    goto LABEL_135;
  }
  if ( a3 != 64 )
  {
    v8 = -2147024809;
    v9 = *((_QWORD *)this + 11);
    if ( !v9 )
      goto LABEL_138;
    v56 = -2147024809;
    LODWORD(ppv) = 120;
    goto LABEL_135;
  }
  if ( WINDLP_ACTION_LAYOUTISO != *(_OWORD *)a2 )
  {
    v8 = -2147024809;
    v9 = *((_QWORD *)this + 11);
    if ( !v9 )
      goto LABEL_138;
    v56 = -2147024809;
    LODWORD(ppv) = 125;
    goto LABEL_135;
  }
  if ( !*((_QWORD *)a2 + 3) )
  {
    v8 = -2147024809;
    v9 = *((_QWORD *)this + 11);
    if ( !v9 )
      goto LABEL_138;
    v56 = -2147024809;
    LODWORD(ppv) = 126;
    goto LABEL_135;
  }
  if ( !*((_QWORD *)a2 + 2) )
  {
    v8 = -2147024809;
    v9 = *((_QWORD *)this + 11);
    if ( !v9 )
      goto LABEL_138;
    v56 = -2147024809;
    LODWORD(ppv) = 127;
    goto LABEL_135;
  }
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( !GetFullPathNameW(*((LPCWSTR *)a2 + 2), 0x208u, Buffer, 0) )
  {
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
      v11 = 0;
      if ( v8 >= 0 )
      {
LABEL_137:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
        goto LABEL_138;
      }
      v56 = v8;
      LODWORD(ppv) = 132;
      v9 = *((_QWORD *)this + 11);
LABEL_135:
      v50 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v9,
              4u,
              (__int64)L"%s(%d): Result = 0x%X",
              L"CDlpActionLayoutIso::InitializeRoutine",
              ppv,
              v56);
      v11 = (unsigned int)v50;
      if ( v50 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v50);
      goto LABEL_137;
    }
    goto LABEL_138;
  }
  if ( a2[8] > 2 )
  {
    v8 = -2147024809;
    v9 = *((_QWORD *)this + 11);
    if ( !v9 )
      goto LABEL_138;
    v56 = -2147024809;
    LODWORD(ppv) = 139;
    goto LABEL_135;
  }
  v12 = (_WORD *)*((_QWORD *)a2 + 5);
  if ( v12 )
  {
    if ( a2[8] )
    {
      v8 = -2147024809;
      v9 = *((_QWORD *)this + 11);
      if ( !v9 )
        goto LABEL_138;
      v56 = -2147024809;
      LODWORD(ppv) = 144;
      goto LABEL_135;
    }
    LODWORD(v58) = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v12, &v58);
    v8 = StringCch;
    if ( StringCch >= 0 )
    {
      v14 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
              v12,
              (unsigned int)v58,
              &v59);
      v8 = v14;
      if ( v14 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v14);
      v6 = v59;
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
    if ( v8 < 0 )
    {
      v9 = *((_QWORD *)this + 11);
      if ( !v9 )
        goto LABEL_138;
      v56 = v8;
      LODWORD(ppv) = 150;
      goto LABEL_135;
    }
  }
  v15 = (_WORD *)*((_QWORD *)a2 + 6);
  if ( v15 )
  {
    LODWORD(v58) = 0;
    v16 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v15, &v58);
    v8 = v16;
    if ( v16 >= 0 )
    {
      v17 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
              v15,
              (unsigned int)v58,
              &v60);
      v8 = v17;
      if ( v17 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v17);
      v7 = v60;
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v16);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
    if ( v8 < 0 )
    {
      v9 = *((_QWORD *)this + 11);
      if ( !v9 )
        goto LABEL_138;
      v56 = v8;
      LODWORD(ppv) = 154;
      goto LABEL_135;
    }
  }
  if ( !v6 && !v7 )
  {
    if ( a2[8] == 1 )
    {
      v18 = CMiscHelpersT<CEmptyType>::CombinePath((__int64)Buffer, (__int64)L"boot\\etfsboot.com", 0);
      v8 = v18;
      if ( v18 < 0 )
      {
        v19 = *((_QWORD *)this + 11);
        if ( v19 )
        {
          v57 = v18;
          ppva = 162;
LABEL_52:
          v20 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v19,
                  4u,
                  (__int64)L"%s(%d): Result = 0x%X",
                  L"CDlpActionLayoutIso::InitializeRoutine",
                  ppva,
                  v57);
          v21 = (unsigned int)v20;
          if ( v20 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v20);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v21);
          goto LABEL_55;
        }
        goto LABEL_55;
      }
    }
    else
    {
      if ( a2[8] != 2 )
        goto LABEL_68;
      v22 = CMiscHelpersT<CEmptyType>::CombinePath((__int64)Buffer, (__int64)L"boot\\etfsboot.com", 0);
      v8 = v22;
      if ( v22 < 0 )
      {
        v19 = *((_QWORD *)this + 11);
        if ( v19 )
        {
          v57 = v22;
          ppva = 166;
          goto LABEL_52;
        }
LABEL_55:
        v6 = v59;
        goto LABEL_138;
      }
      v23 = CMiscHelpersT<CEmptyType>::CombinePath((__int64)Buffer, (__int64)L"efi\\microsoft\\boot\\efisys.bin", 0);
      v8 = v23;
      if ( v23 < 0 )
      {
        v24 = *((_QWORD *)this + 11);
        if ( v24 )
        {
          v25 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v24,
                  4u,
                  (__int64)L"%s(%d): Result = 0x%X",
                  L"CDlpActionLayoutIso::InitializeRoutine",
                  167,
                  v23);
          v26 = (unsigned int)v25;
          if ( v25 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v25);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v26);
        }
        v6 = v59;
        v7 = v60;
        goto LABEL_138;
      }
      v7 = v60;
    }
    v6 = v59;
  }
LABEL_68:
  v27 = *((_QWORD *)this + 11);
  if ( v27 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v27, 2u, (__int64)L"LayoutIso: Initializing ISO Path: [%s]", *((_QWORD *)a2 + 3));
  v28 = *((_QWORD *)this + 11);
  if ( v28 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v28, 2u, (__int64)L"LayoutIso: Initializing Layout Path: [%s]", Buffer);
  v29 = *((_QWORD *)this + 11);
  if ( v29 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v29, 2u, (__int64)L"LayoutIso: Initializing Media Type: [0x%X]", a2[8]);
  v30 = *((_QWORD *)this + 11);
  v31 = &dword_180084C74;
  if ( v30 )
  {
    v32 = v6;
    if ( !v6 )
      v32 = &dword_180084C74;
    CDlpLogT<CEmptyType>::DlpLogFormat(v30, 2u, (__int64)L"LayoutIso: Initializing BootFile Path: [%s]", v32);
  }
  v33 = *((_QWORD *)this + 11);
  if ( v33 )
  {
    v34 = v7;
    if ( !v7 )
      v34 = &dword_180084C74;
    CDlpLogT<CEmptyType>::DlpLogFormat(v33, 2u, (__int64)L"LayoutIso: Initializing EFI BootFile Path: [%s]", v34);
  }
  v35 = *((_QWORD *)this + 11);
  if ( v35 )
  {
    if ( *((_QWORD *)a2 + 7) )
      v31 = (int *)*((_QWORD *)a2 + 7);
    CDlpLogT<CEmptyType>::DlpLogFormat(v35, 2u, (__int64)L"LayoutIso: Initializing Volume Label: [%s]", v31);
  }
  v8 = 0;
  v36 = CoInitializeEx(0, 0);
  if ( v36 < 0 )
  {
    if ( v36 != -2147417850 )
    {
      v8 = v36;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v36);
    }
  }
  else
  {
    v5 = 1;
    v61 = 1;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
  if ( v8 < 0 )
  {
    v9 = *((_QWORD *)this + 11);
    if ( !v9 )
      goto LABEL_138;
    v56 = v8;
    LODWORD(ppv) = 182;
    goto LABEL_135;
  }
  v37 = CoCreateInstance(&CLSID_MsftFileSystemImage, 0, 0x17u, &GUID_2c941fe1_975b_59be_a960_9a2a262853a5, &v64);
  v8 = v37;
  if ( v37 < 0 )
  {
    v9 = *((_QWORD *)this + 11);
    if ( !v9 )
      goto LABEL_138;
    v56 = v37;
    LODWORD(ppv) = 189;
    goto LABEL_135;
  }
  if ( v6 )
  {
    if ( v7 )
    {
      v38 = CoCreateInstance(&CLSID_MsftFileSystemImage, 0, 0x17u, &GUID_d7644b2c_1537_4767_b62f_f1387b02ddfd, &v63);
      v8 = v38;
      if ( v38 < 0 )
      {
        v9 = *((_QWORD *)this + 11);
        if ( !v9 )
          goto LABEL_138;
        v56 = v38;
        LODWORD(ppv) = 197;
        goto LABEL_135;
      }
    }
  }
  v39 = CoCreateInstance(&CLSID_BootOptions, 0, 0x17u, &GUID_2c941fd4_975b_59be_a960_9a2a262853a5, &v62);
  v8 = v39;
  if ( v39 < 0 )
  {
    v9 = *((_QWORD *)this + 11);
    if ( !v9 )
      goto LABEL_138;
    v56 = v39;
    LODWORD(ppv) = 203;
    goto LABEL_135;
  }
  v40 = (_WORD *)*((_QWORD *)a2 + 3);
  v41 = 0;
  LODWORD(v58) = 0;
  if ( !v40 )
  {
LABEL_107:
    Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                 v40,
                 v41,
                 (_QWORD *)this + 69);
    v8 = Internal;
    if ( Internal >= 0 )
      goto LABEL_109;
    goto LABEL_108;
  }
  Internal = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v40, &v58);
  v8 = Internal;
  if ( Internal >= 0 )
  {
    v41 = (unsigned int)v58;
    goto LABEL_107;
  }
LABEL_108:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(Internal);
LABEL_109:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
  if ( v8 < 0 )
  {
    v9 = *((_QWORD *)this + 11);
    if ( !v9 )
      goto LABEL_138;
    v56 = v8;
    LODWORD(ppv) = 207;
    goto LABEL_135;
  }
  LODWORD(v58) = 0;
  v43 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Buffer, &v58);
  v8 = v43;
  if ( v43 < 0
    || (v43 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                Buffer,
                (unsigned int)v58,
                (_QWORD *)this + 70),
        v8 = v43,
        v43 < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v43);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
  if ( v8 < 0 )
  {
    v9 = *((_QWORD *)this + 11);
    if ( !v9 )
      goto LABEL_138;
    v56 = v8;
    LODWORD(ppv) = 208;
    goto LABEL_135;
  }
  if ( v6 )
  {
    v58 = v6;
    v6 = 0;
    v59 = 0;
    v44 = *((_QWORD *)this + 71);
    if ( v44 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)(v44 - 4));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    *((_QWORD *)this + 71) = v58;
  }
  if ( v7 )
  {
    v58 = v7;
    v7 = 0;
    v60 = 0;
    v46 = *((_QWORD *)this + 72);
    if ( v46 )
    {
      v47 = GetProcessHeap();
      HeapFree(v47, 0, (LPVOID)(v46 - 4));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    *((_QWORD *)this + 72) = v58;
  }
  v48 = (_WORD *)*((_QWORD *)a2 + 7);
  if ( v48 )
  {
    LODWORD(v58) = 0;
    v49 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v48, &v58);
    v8 = v49;
    if ( v49 < 0
      || (v49 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(
                  v48,
                  (unsigned int)v58,
                  (_QWORD *)this + 73),
          v8 = v49,
          v49 < 0) )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v49);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
    if ( v8 < 0 )
    {
      v9 = *((_QWORD *)this + 11);
      if ( v9 )
      {
        v56 = v8;
        LODWORD(ppv) = 223;
        goto LABEL_135;
      }
    }
  }
LABEL_138:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
  if ( v7 )
  {
    v51 = GetProcessHeap();
    HeapFree(v51, 0, v7 - 1);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v6 )
  {
    v52 = GetProcessHeap();
    HeapFree(v52, 0, v6 - 1);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v62 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v62 + 16LL))(v62);
    v62 = 0;
  }
  if ( v63 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v63 + 16LL))(v63);
    v63 = 0;
  }
  if ( v64 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v64 + 16LL))(v64);
    v64 = 0;
  }
  if ( v5 )
    CoUninitialize();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001d470  mov     [rsp-8+arg_10], rbx
0x18001d475  push    rbp
0x18001d476  push    rsi
0x18001d477  push    rdi
0x18001d478  push    r12
0x18001d47a  push    r13
0x18001d47c  push    r14
0x18001d47e  push    r15
0x18001d480  lea     rbp, [rsp-390h]
0x18001d488  sub     rsp, 490h
0x18001d48f  mov     rax, cs:__security_cookie
0x18001d496  xor     rax, rsp
0x18001d499  mov     [rbp+3C0h+var_40], rax
0x18001d4a0  mov     r12, rdx
0x18001d4a3  mov     r14, rcx
0x18001d4a6  xor     ebx, ebx
0x18001d4a8  mov     [rsp+4C0h+var_478], ebx
0x18001d4ac  mov     [rsp+4C0h+var_460], rbx
0x18001d4b1  mov     [rsp+4C0h+var_468], rbx
0x18001d4b6  mov     [rsp+4C0h+var_470], rbx
0x18001d4bb  xor     r15d, r15d
0x18001d4be  mov     [rsp+4C0h+var_488], r15
0x18001d4c3  xor     r13d, r13d
0x18001d4c6  mov     [rsp+4C0h+var_480], r13
0x18001d4cb  test    rdx, rdx
0x18001d4ce  jnz     short loc_18001D4F5
0x18001d4d0  mov     eax, 80070057h
0x18001d4d5  mov     esi, eax
0x18001d4d7  mov     rcx, [rcx+58h]
0x18001d4db  test    rcx, rcx
0x18001d4de  jz      loc_18001DCB8
0x18001d4e4  mov     [rsp+4C0h+var_498], eax
0x18001d4e8  mov     dword ptr [rsp+4C0h+ppv], 77h ; 'w'
0x18001d4f0  jmp     loc_18001DC90
0x18001d4f5  cmp     r8d, 40h ; '@'
0x18001d4f9  jz      short loc_18001D520
0x18001d4fb  mov     eax, 80070057h
0x18001d500  mov     esi, eax
0x18001d502  mov     rcx, [rcx+58h]
0x18001d506  test    rcx, rcx
0x18001d509  jz      loc_18001DCB8
0x18001d50f  mov     [rsp+4C0h+var_498], eax
0x18001d513  mov     dword ptr [rsp+4C0h+ppv], 78h ; 'x'
0x18001d51b  jmp     loc_18001DC90
0x18001d520  mov     rax, qword ptr cs:WINDLP_ACTION_LAYOUTISO
0x18001d527  cmp     rax, [rdx]
0x18001d52a  jnz     loc_18001DC74
0x18001d530  mov     rax, qword ptr cs:WINDLP_ACTION_LAYOUTISO+8
0x18001d537  cmp     rax, [rdx+8]
0x18001d53b  jnz     loc_18001DC74
0x18001d541  cmp     qword ptr [rdx+18h], 0
0x18001d546  jnz     short loc_18001D56D
0x18001d548  mov     eax, 80070057h
0x18001d54d  mov     esi, eax
0x18001d54f  mov     rcx, [rcx+58h]
0x18001d553  test    rcx, rcx
0x18001d556  jz      loc_18001DCB8
0x18001d55c  mov     [rsp+4C0h+var_498], eax
0x18001d560  mov     dword ptr [rsp+4C0h+ppv], 7Eh ; '~'
0x18001d568  jmp     loc_18001DC90
0x18001d56d  cmp     qword ptr [rdx+10h], 0
0x18001d572  jnz     short loc_18001D599
0x18001d574  mov     eax, 80070057h
0x18001d579  mov     esi, eax
0x18001d57b  mov     rcx, [rcx+58h]
0x18001d57f  test    rcx, rcx
0x18001d582  jz      loc_18001DCB8
0x18001d588  mov     [rsp+4C0h+var_498], eax
0x18001d58c  mov     dword ptr [rsp+4C0h+ppv], 7Fh
0x18001d594  jmp     loc_18001DC90
0x18001d599  xor     edx, edx; Val
0x18001d59b  mov     r8d, 410h; Size
0x18001d5a1  lea     rcx, [rsp+4C0h+Buffer]; void *
0x18001d5a6  call    memset_0
0x18001d5ab  xor     r9d, r9d; lpFilePart
0x18001d5ae  lea     r8, [rsp+4C0h+Buffer]; lpBuffer
0x18001d5b3  mov     edx, 208h; nBufferLength
0x18001d5b8  mov     rcx, [r12+10h]; lpFileName
0x18001d5bd  call    cs:__imp_GetFullPathNameW
0x18001d5c3  test    eax, eax
0x18001d5c5  jnz     short loc_18001D60F
0x18001d5c7  call    cs:__imp_GetLastError
0x18001d5cd  mov     esi, eax
0x18001d5cf  test    eax, eax
0x18001d5d1  jnz     short loc_18001D5DA
0x18001d5d3  mov     esi, 80004005h
0x18001d5d8  jmp     short loc_18001D5E5
0x18001d5da  jle     short loc_18001D5E5
0x18001d5dc  movzx   esi, ax
0x18001d5df  or      esi, 80070000h
0x18001d5e5  cmp     qword ptr [r14+58h], 0
0x18001d5ea  jz      loc_18001DCB8
0x18001d5f0  xor     ecx, ecx
0x18001d5f2  test    esi, esi
0x18001d5f4  jns     loc_18001DCB3
0x18001d5fa  mov     [rsp+4C0h+var_498], esi
0x18001d5fe  mov     dword ptr [rsp+4C0h+ppv], 84h
0x18001d606  mov     rcx, [r14+58h]
0x18001d60a  jmp     loc_18001DC90
0x18001d60f  cmp     dword ptr [r12+20h], 2
0x18001d615  jbe     short loc_18001D63C
0x18001d617  mov     eax, 80070057h
0x18001d61c  mov     esi, eax
0x18001d61e  mov     rcx, [r14+58h]
0x18001d622  test    rcx, rcx
0x18001d625  jz      loc_18001DCB8
0x18001d62b  mov     [rsp+4C0h+var_498], eax
0x18001d62f  mov     dword ptr [rsp+4C0h+ppv], 8Bh
0x18001d637  jmp     loc_18001DC90
0x18001d63c  mov     rdi, [r12+28h]
0x18001d641  test    rdi, rdi
0x18001d644  jz      loc_18001D6E7
0x18001d64a  cmp     dword ptr [r12+20h], 0
0x18001d650  jz      short loc_18001D677
0x18001d652  mov     eax, 80070057h
0x18001d657  mov     esi, eax
0x18001d659  mov     rcx, [r14+58h]
0x18001d65d  test    rcx, rcx
0x18001d660  jz      loc_18001DCB8
0x18001d666  mov     [rsp+4C0h+var_498], eax
0x18001d66a  mov     dword ptr [rsp+4C0h+ppv], 90h
0x18001d672  jmp     loc_18001DC90
0x18001d677  mov     dword ptr [rsp+4C0h+var_490], 0
0x18001d67f  lea     rdx, [rsp+4C0h+var_490]
0x18001d684  mov     rcx, rdi
0x18001d687  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18001d68c  mov     esi, eax
0x18001d68e  test    eax, eax
0x18001d690  jns     short loc_18001D69B
0x18001d692  mov     ecx, eax
0x18001d694  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001d699  jmp     short loc_18001D6BE
0x18001d69b  lea     r8, [rsp+4C0h+var_488]
0x18001d6a0  mov     edx, dword ptr [rsp+4C0h+var_490]
0x18001d6a4  mov     rcx, rdi; Src
0x18001d6a7  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18001d6ac  mov     esi, eax
0x18001d6ae  test    eax, eax
0x18001d6b0  jns     short loc_18001D6B9
0x18001d6b2  mov     ecx, eax
0x18001d6b4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001d6b9  mov     r15, [rsp+4C0h+var_488]
0x18001d6be  mov     ecx, esi
0x18001d6c0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001d6c5  test    esi, esi
0x18001d6c7  jns     short loc_18001D6E7
0x18001d6c9  mov     rcx, [r14+58h]
0x18001d6cd  test    rcx, rcx
0x18001d6d0  jz      loc_18001DCB8
0x18001d6d6  mov     [rsp+4C0h+var_498], esi
0x18001d6da  mov     dword ptr [rsp+4C0h+ppv], 96h
0x18001d6e2  jmp     loc_18001DC90
0x18001d6e7  mov     rdi, [r12+30h]
0x18001d6ec  test    rdi, rdi
0x18001d6ef  jz      short loc_18001D761
0x18001d6f1  mov     dword ptr [rsp+4C0h+var_490], 0
0x18001d6f9  lea     rdx, [rsp+4C0h+var_490]
0x18001d6fe  mov     rcx, rdi
0x18001d701  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x18001d706  mov     esi, eax
0x18001d708  test    eax, eax
0x18001d70a  jns     short loc_18001D715
0x18001d70c  mov     ecx, eax
0x18001d70e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001d713  jmp     short loc_18001D738
0x18001d715  lea     r8, [rsp+4C0h+var_480]
0x18001d71a  mov     edx, dword ptr [rsp+4C0h+var_490]
0x18001d71e  mov     rcx, rdi; Src
0x18001d721  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x18001d726  mov     esi, eax
0x18001d728  test    eax, eax
0x18001d72a  jns     short loc_18001D733
0x18001d72c  mov     ecx, eax
0x18001d72e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001d733  mov     r13, [rsp+4C0h+var_480]
0x18001d738  mov     ecx, esi
0x18001d73a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001d73f  test    esi, esi
0x18001d741  jns     short loc_18001D761
0x18001d743  mov     rcx, [r14+58h]
0x18001d747  test    rcx, rcx
0x18001d74a  jz      loc_18001DCB8
0x18001d750  mov     [rsp+4C0h+var_498], esi
0x18001d754  mov     dword ptr [rsp+4C0h+ppv], 9Ah
0x18001d75c  jmp     loc_18001DC90
0x18001d761  test    r15, r15
0x18001d764  jnz     loc_18001D89C
0x18001d76a  test    r13, r13
0x18001d76d  jnz     loc_18001D89C
0x18001d773  cmp     dword ptr [r12+20h], 1
0x18001d779  jnz     short loc_18001D7E5
0x18001d77b  lea     r9, [rsp+4C0h+var_488]
0x18001d780  xor     r8d, r8d
0x18001d783  lea     rdx, aBootEtfsbootCo; "boot\\etfsboot.com"
0x18001d78a  lea     rcx, [rsp+4C0h+Buffer]
0x18001d78f  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001d794  mov     esi, eax
0x18001d796  test    eax, eax
0x18001d798  jns     loc_18001D897
0x18001d79e  mov     rcx, [r14+58h]
0x18001d7a2  test    rcx, rcx
0x18001d7a5  jz      short loc_18001D7DB
0x18001d7a7  mov     [rsp+4C0h+var_498], eax
0x18001d7ab  mov     dword ptr [rsp+4C0h+ppv], 0A2h
0x18001d7b3  lea     r9, aCdlpactionlayo_8; "CDlpActionLayoutIso::InitializeRoutine"
0x18001d7ba  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18001d7c1  mov     edx, 4
0x18001d7c6  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001d7cb  test    eax, eax
0x18001d7cd  mov     ecx, eax
0x18001d7cf  jns     short loc_18001D7D6
0x18001d7d1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001d7d6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001d7db  mov     r15, [rsp+4C0h+var_488]
0x18001d7e0  jmp     loc_18001DCB8
0x18001d7e5  cmp     dword ptr [r12+20h], 2
0x18001d7eb  jnz     loc_18001D89C
0x18001d7f1  lea     r9, [rsp+4C0h+var_488]
0x18001d7f6  xor     r8d, r8d
0x18001d7f9  lea     rdx, aBootEtfsbootCo; "boot\\etfsboot.com"
0x18001d800  lea     rcx, [rsp+4C0h+Buffer]
0x18001d805  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001d80a  mov     esi, eax
0x18001d80c  test    eax, eax
0x18001d80e  jns     short loc_18001D827
0x18001d810  mov     rcx, [r14+58h]
0x18001d814  test    rcx, rcx
0x18001d817  jz      short loc_18001D7DB
0x18001d819  mov     [rsp+4C0h+var_498], eax
0x18001d81d  mov     dword ptr [rsp+4C0h+ppv], 0A6h
0x18001d825  jmp     short loc_18001D7B3
0x18001d827  lea     r9, [rsp+4C0h+var_480]
0x18001d82c  xor     r8d, r8d
0x18001d82f  lea     rdx, aEfiMicrosoftBo_2; "efi\\microsoft\\boot\\efisys.bin"
0x18001d836  lea     rcx, [rsp+4C0h+Buffer]
0x18001d83b  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001d840  mov     esi, eax
0x18001d842  test    eax, eax
0x18001d844  jns     short loc_18001D892
0x18001d846  mov     rcx, [r14+58h]
0x18001d84a  test    rcx, rcx
0x18001d84d  jz      short loc_18001D883
0x18001d84f  mov     [rsp+4C0h+var_498], eax
0x18001d853  mov     dword ptr [rsp+4C0h+ppv], 0A7h
0x18001d85b  lea     r9, aCdlpactionlayo_8; "CDlpActionLayoutIso::InitializeRoutine"
0x18001d862  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18001d869  mov     edx, 4
0x18001d86e  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001d873  mov     ecx, eax
0x18001d875  test    eax, eax
0x18001d877  jns     short loc_18001D87E
0x18001d879  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001d87e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001d883  mov     r15, [rsp+4C0h+var_488]
0x18001d888  mov     r13, [rsp+4C0h+var_480]
0x18001d88d  jmp     loc_18001DCB8
0x18001d892  mov     r13, [rsp+4C0h+var_480]
0x18001d897  mov     r15, [rsp+4C0h+var_488]
0x18001d89c  mov     rcx, [r14+58h]
0x18001d8a0  test    rcx, rcx
0x18001d8a3  jz      short loc_18001D8BB
0x18001d8a5  mov     r9, [r12+18h]
0x18001d8aa  lea     r8, aLayoutisoIniti_1; "LayoutIso: Initializing ISO Path: [%s]"
0x18001d8b1  mov     edx, 2
0x18001d8b6  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001d8bb  mov     rcx, [r14+58h]
0x18001d8bf  test    rcx, rcx
0x18001d8c2  jz      short loc_18001D8DA
0x18001d8c4  lea     r9, [rsp+4C0h+Buffer]
0x18001d8c9  lea     r8, aLayoutisoIniti_3; "LayoutIso: Initializing Layout Path: [%"...
0x18001d8d0  mov     edx, 2
0x18001d8d5  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001d8da  mov     rcx, [r14+58h]
0x18001d8de  test    rcx, rcx
0x18001d8e1  jz      short loc_18001D8F9
0x18001d8e3  mov     r9d, [r12+20h]
0x18001d8e8  lea     r8, aLayoutisoIniti_4; "LayoutIso: Initializing Media Type: [0x"...
0x18001d8ef  mov     edx, 2
0x18001d8f4  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001d8f9  mov     rcx, [r14+58h]
0x18001d8fd  lea     rdi, dword_180084C74
0x18001d904  test    rcx, rcx
0x18001d907  jz      short loc_18001D925
0x18001d909  test    r15, r15
0x18001d90c  mov     r9, r15
0x18001d90f  jnz     short loc_18001D914
0x18001d911  mov     r9, rdi
0x18001d914  lea     r8, aLayoutisoIniti_0; "LayoutIso: Initializing BootFile Path: "...
0x18001d91b  mov     edx, 2
0x18001d920  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18001d925  mov     rcx, [r14+58h]
0x18001d929  test    rcx, rcx
0x18001d92c  jz      short loc_18001D94A
0x18001d92e  test    r13, r13
0x18001d931  mov     r9, r13
0x18001d934  jnz     short loc_18001D939
0x18001d936  mov     r9, rdi
0x18001d939  lea     r8, aLayoutisoIniti; "LayoutIso: Initializing EFI BootFile Pa"...
0x18001d940  mov     edx, 2
0x18001d945  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
  ... truncated ...
```
