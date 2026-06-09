# CDlpActionLayoutIso::ExecuteRoutine(IDlpTask *)

- ea: `0x1800153d0`
- end: `0x18001644e`
- name: `?ExecuteRoutine@CDlpActionLayoutIso@@EEAAJPEAVIDlpTask@@@Z`
- size: `4222`
- prototype: `__int64 __fastcall(CDlpActionLayoutIso *__hidden this, struct IDlpTask *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000aba4`
- `0x18000abc4`
- `0x180012f5c`
- `0x1800153d0`
- `0x18001fd60`
- `0x18002b5bc`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001629b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001629b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800162a9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800162a9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180015798`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180015917`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180015798`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180015917`
- `OLEAUT32!__imp_VariantInit` at `0x180015b41`
- `OLEAUT32!__imp_VariantInit` at `0x180015c43`
- `OLEAUT32!__imp_VariantInit` at `0x180015b41`
- `OLEAUT32!__imp_VariantInit` at `0x180015c43`
- `OLEAUT32!__imp_VariantClear` at `0x180015c39`
- `OLEAUT32!__imp_VariantClear` at `0x180015d2c`
- `OLEAUT32!__imp_VariantClear` at `0x180015c39`
- `OLEAUT32!__imp_VariantClear` at `0x180015d2c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800162c0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800162c0`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180015b76`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180015c78`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180015b76`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180015c78`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180015b00`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180015b00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015514`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800162cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015514`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800162cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015525`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015525`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800162da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800162da`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180015569`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180015569`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001641e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001641e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800155dd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015640`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015829`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800159a8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800155dd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015640`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180015829`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800159a8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180015866`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x1800159e5`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180016071`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180015866`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x1800159e5`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180016071`

## string_xrefs

- `0x180015614`: `LayoutIso: Successfully created IFileSystemImage object!`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall CDlpActionLayoutIso::ExecuteRoutine(CDlpActionLayoutIso *this, struct IDlpTask *a2)
{
  struct IDlpTask *v2; // r13
  int v4; // r14d
  void *v5; // rdi
  SAFEARRAY *v6; // rsi
  int v7; // r15d
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  HANDLE ProcessHeap; // rax
  LPVOID v14; // rax
  HRESULT v15; // eax
  HRESULT v16; // eax
  HRESULT v17; // eax
  __int64 v18; // rcx
  void *v19; // rbx
  int v20; // eax
  int v21; // eax
  int v22; // eax
  const WCHAR *v23; // rcx
  DWORD FileAttributesW; // eax
  BOOL v25; // ebx
  __int64 v26; // rcx
  HRESULT v27; // eax
  HRESULT v28; // eax
  int v29; // eax
  int v30; // eax
  const WCHAR *v31; // rcx
  DWORD v32; // eax
  BOOL v33; // ebx
  __int64 v34; // rcx
  HRESULT v35; // eax
  HRESULT v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  SAFEARRAY *Vector; // rax
  HRESULT v41; // eax
  LONG v42; // r13d
  __int64 v43; // rcx
  HRESULT v44; // eax
  LONG v45; // ebx
  __int64 v46; // rcx
  int v47; // eax
  LPVOID v48; // rax
  bool v49; // cl
  LPVOID v50; // rdx
  int v51; // eax
  int v52; // eax
  int v53; // eax
  int v54; // eax
  int v55; // eax
  int v56; // eax
  int v57; // eax
  int v58; // eax
  int v59; // eax
  int v60; // eax
  int v61; // eax
  HRESULT v62; // eax
  unsigned __int64 v63; // rbx
  unsigned int v64; // r13d
  int v65; // eax
  int v66; // eax
  int v67; // eax
  int v68; // eax
  int v69; // eax
  __int64 v70; // rcx
  IStream *v71; // rcx
  HANDLE v72; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  int v75; // [rsp+28h] [rbp-D8h]
  int v76; // [rsp+28h] [rbp-D8h]
  LPVOID v77; // [rsp+30h] [rbp-D0h] BYREF
  LONG rgIndices; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v79; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v80; // [rsp+48h] [rbp-B8h] BYREF
  IStream *v81; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v82; // [rsp+58h] [rbp-A8h] BYREF
  int v83; // [rsp+60h] [rbp-A0h] BYREF
  int v84; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v85; // [rsp+68h] [rbp-98h] BYREF
  __int64 v86; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v87; // [rsp+78h] [rbp-88h] BYREF
  IStream *v88; // [rsp+80h] [rbp-80h] BYREF
  IStream *ppstm; // [rsp+88h] [rbp-78h] BYREF
  __int64 v90; // [rsp+90h] [rbp-70h] BYREF
  __int64 v91; // [rsp+98h] [rbp-68h] BYREF
  int v92; // [rsp+A0h] [rbp-60h]
  int v93; // [rsp+A4h] [rbp-5Ch] BYREF
  int v94; // [rsp+A8h] [rbp-58h] BYREF
  struct IDlpTask *v95; // [rsp+B0h] [rbp-50h]
  VARIANTARG pvarg; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID v97; // [rsp+D0h] [rbp-30h]
  SAFEARRAY *v98; // [rsp+D8h] [rbp-28h]
  _BYTE v99[16]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v100; // [rsp+F0h] [rbp-10h]

  v2 = a2;
  v95 = a2;
  v4 = 0;
  v92 = 0;
  v77 = 0;
  v82 = 0;
  v91 = 0;
  v90 = 0;
  v80 = 0;
  v79 = 0;
  v86 = 0;
  v81 = 0;
  ppstm = 0;
  v88 = 0;
  v5 = 0;
  v97 = 0;
  v6 = 0;
  v98 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  rgIndices = 0;
  v83 = 0;
  v84 = 0;
  v93 = 0;
  v94 = 0;
  memset_0(v99, 0, 0x50u);
  v87 = 0;
  v85 = 0;
  if ( !v2 )
  {
    v7 = -2147024809;
    v8 = *((_QWORD *)this + 11);
    if ( !v8 )
      goto LABEL_211;
    v75 = -2147024809;
    LODWORD(ppv) = 357;
    goto LABEL_4;
  }
  v11 = (*(__int64 (__fastcall **)(CDlpActionLayoutIso *, unsigned __int64 *, __int64 *, _QWORD))(*(_QWORD *)this + 72LL))(
          this,
          &v87,
          &v85,
          0);
  v7 = v11;
  if ( v11 < 0 )
  {
    v12 = *((_QWORD *)this + 11);
    if ( !v12 )
      goto LABEL_204;
    v76 = v11;
    LODWORD(ppv) = 363;
    goto LABEL_201;
  }
  ProcessHeap = GetProcessHeap();
  v14 = HeapAlloc(ProcessHeap, 0, 0x100000u);
  v5 = v14;
  if ( !v14 )
  {
    v97 = 0;
    v7 = -2147024882;
    v8 = *((_QWORD *)this + 11);
    if ( v8 )
    {
      v75 = -2147024882;
      LODWORD(ppv) = 369;
LABEL_4:
      v9 = CDlpLogT<CEmptyType>::DlpLogFormat(
             v8,
             4,
             L"%s(%d): Result = 0x%X",
             L"CDlpActionLayoutIso::ExecuteRoutine",
             ppv,
             v75);
      v10 = (unsigned int)v9;
      if ( v9 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v9);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
      goto LABEL_205;
    }
    goto LABEL_205;
  }
  v97 = v14;
  v7 = 0;
  v15 = CoInitializeEx(0, 0);
  if ( v15 < 0 )
  {
    if ( v15 != -2147417850 )
    {
      v7 = v15;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v15);
    }
  }
  else
  {
    v4 = 1;
    v92 = 1;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( v7 < 0 )
  {
    v12 = *((_QWORD *)this + 11);
    if ( !v12 )
      goto LABEL_204;
    v76 = v7;
    LODWORD(ppv) = 373;
    goto LABEL_201;
  }
  v16 = CoCreateInstance(&CLSID_MsftFileSystemImage, 0, 0x17u, &GUID_2c941fe1_975b_59be_a960_9a2a262853a5, &v77);
  v7 = v16;
  v12 = *((_QWORD *)this + 11);
  if ( v16 < 0 )
  {
    if ( !v12 )
      goto LABEL_204;
    v76 = v16;
    LODWORD(ppv) = 380;
    goto LABEL_201;
  }
  if ( v12 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v12, 2, L"LayoutIso: Successfully created IFileSystemImage object!");
  v17 = CoCreateInstance(&CLSID_MsftFileSystemImage, 0, 0x17u, &GUID_d7644b2c_1537_4767_b62f_f1387b02ddfd, &v82);
  v18 = *((_QWORD *)this + 11);
  if ( v17 < 0 )
  {
    if ( v18 )
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v18,
        3,
        L"LayoutIso: Unable to retrieve IFileSystemImage2 interface! Error: [0x%X]",
        (unsigned int)v17);
  }
  else
  {
    if ( v18 )
      CDlpLogT<CEmptyType>::DlpLogFormat(v18, 2, L"LayoutIso: Successfully retrieved IFileSystemImage2 object!");
    if ( v77 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v77 + 16LL))(v77);
      v77 = 0;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v82 + 8LL))(v82);
    v19 = v82;
    if ( v77 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v77 + 16LL))(v77);
    v77 = v19;
  }
  v20 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v77 + 88LL))(v77, 0);
  v7 = v20;
  if ( v20 < 0 )
  {
    v12 = *((_QWORD *)this + 11);
    if ( !v12 )
      goto LABEL_204;
    v76 = v20;
    LODWORD(ppv) = 406;
    goto LABEL_201;
  }
  v21 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v77 + 232LL))(v77, 4);
  v7 = v21;
  if ( v21 < 0 )
  {
    v12 = *((_QWORD *)this + 11);
    if ( !v12 )
      goto LABEL_204;
    v76 = v21;
    LODWORD(ppv) = 410;
    goto LABEL_201;
  }
  v22 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v77 + 248LL))(v77, 258);
  v7 = v22;
  if ( v22 < 0 )
  {
    v12 = *((_QWORD *)this + 11);
    if ( !v12 )
      goto LABEL_204;
    v76 = v22;
    LODWORD(ppv) = 411;
    goto LABEL_201;
  }
  v23 = (const WCHAR *)*((_QWORD *)this + 71);
  if ( v23 )
  {
    FileAttributesW = GetFileAttributesW(v23);
    v25 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( !v25 )
    {
      v26 = *((_QWORD *)this + 11);
      if ( v26 )
        CDlpLogT<CEmptyType>::DlpLogFormat(
          v26,
          4,
          L"LayoutIso: Specified boot file [%s] is missing!",
          *((_QWORD *)this + 71));
      v7 = -1048575728;
      v8 = *((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_205;
      v75 = -1048575728;
      LODWORD(ppv) = 423;
      goto LABEL_4;
    }
    v27 = CoCreateInstance(&CLSID_BootOptions, 0, 0x17u, &GUID_2c941fd4_975b_59be_a960_9a2a262853a5, &v80);
    v7 = v27;
    if ( v27 < 0 )
    {
      v12 = *((_QWORD *)this + 11);
      if ( !v12 )
        goto LABEL_204;
      v76 = v27;
      LODWORD(ppv) = 431;
      goto LABEL_201;
    }
    v28 = SHCreateStreamOnFileW(*((LPCWSTR *)this + 71), 0x20u, &ppstm);
    v7 = v28;
    if ( v28 < 0 )
    {
      v12 = *((_QWORD *)this + 11);
      if ( !v12 )
        goto LABEL_204;
      v76 = v28;
      LODWORD(ppv) = 437;
      goto LABEL_201;
    }
    v29 = (*(__int64 (__fastcall **)(LPVOID, IStream *))(*(_QWORD *)v80 + 120LL))(v80, ppstm);
    v7 = v29;
    if ( v29 < 0 )
    {
      v12 = *((_QWORD *)this + 11);
      if ( !v12 )
        goto LABEL_204;
      v76 = v29;
      LODWORD(ppv) = 441;
      goto LABEL_201;
    }
    v30 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v80 + 104LL))(v80, 0);
    v7 = v30;
    if ( v30 < 0 )
    {
      v12 = *((_QWORD *)this + 11);
      if ( !v12 )
        goto LABEL_204;
      v76 = v30;
      LODWORD(ppv) = 445;
      goto LABEL_201;
    }
  }
  v31 = (const WCHAR *)*((_QWORD *)this + 72);
  if ( v31 )
  {
    v32 = GetFileAttributesW(v31);
    v33 = v32 != -1 && (v32 & 0x10) == 0;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( !v33 )
    {
      v34 = *((_QWORD *)this + 11);
      if ( v34 )
        CDlpLogT<CEmptyType>::DlpLogFormat(
          v34,
          4,
          L"LayoutIso: Specified EFI boot file [%s] is missing!",
          *((_QWORD *)this + 72));
      v7 = -1048575728;
      v8 = *((_QWORD *)this + 11);
      if ( !v8 )
        goto LABEL_205;
      v75 = -1048575728;
      LODWORD(ppv) = 456;
      goto LABEL_4;
    }
    v35 = CoCreateInstance(&CLSID_BootOptions, 0, 0x17u, &GUID_2c941fd4_975b_59be_a960_9a2a262853a5, &v79);
    v7 = v35;
    if ( v35 < 0 )
    {
      v12 = *((_QWORD *)this + 11);
      if ( !v12 )
        goto LABEL_204;
      v76 = v35;
      LODWORD(ppv) = 464;
      goto LABEL_201;
    }
    v36 = SHCreateStreamOnFileW(*((LPCWSTR *)this + 72), 0x20u, &v88);
    v7 = v36;
    if ( v36 < 0 )
    {
      v12 = *((_QWORD *)this + 11);
      if ( !v12 )
        goto LABEL_204;
      v76 = v36;
      LODWORD(ppv) = 470;
      goto LABEL_201;
    }
    v37 = (*(__int64 (__fastcall **)(LPVOID, IStream *))(*(_QWORD *)v79 + 120LL))(v79, v88);
    v7 = v37;
    if ( v37 < 0 )
    {
      v12 = *((_QWORD *)this + 11);
      if ( !v12 )
        goto LABEL_204;
      v76 = v37;
      LODWORD(ppv) = 474;
      goto LABEL_201;
    }
    v38 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v79 + 104LL))(v79, 0);
    v7 = v38;
    if ( v38 < 0 )
    {
      v12 = *((_QWORD *)this + 11);
      if ( !v12 )
        goto LABEL_204;
      v76 = v38;
      LODWORD(ppv) = 478;
      goto LABEL_201;
    }
    v39 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v79 + 88LL))(v79, 239);
    v7 = v39;
    if ( v39 < 0 )
    {
      v12 = *((_QWORD *)this + 11);
      if ( !v12 )
        goto LABEL_204;
      v76 = v39;
      LODWORD(ppv) = 482;
      goto LABEL_201;
    }
  }
  if ( !*((_QWORD *)this + 71) || !*((_QWORD *)this + 72) || !v82 )
  {
    v48 = v80;
    if ( v80 || v79 )
    {
      v49 = 0;
      if ( !v80 )
      {
        v48 = v79;
        if ( !v79 )
          v49 = 1;
      }
      v50 = 0;
      if ( !v49 )
        v50 = v48;
      v51 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v77 + 144LL))(v77, v50);
      v7 = v51;
      if ( v51 < 0 )
      {
        v12 = *((_QWORD *)this + 11);
        if ( !v12 )
          goto LABEL_204;
        v76 = v51;
        LODWORD(ppv) = 521;
        goto LABEL_201;
      }
    }
LABEL_144:
    if ( *((_QWORD *)this + 73)
      && (v52 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v77 + 120LL))(v77), v7 = v52, v52 < 0) )
    {
      v12 = *((_QWORD *)this + 11);
      if ( !v12 )
        goto LABEL_204;
      v76 = v52;
      LODWORD(ppv) = 530;
    }
    else
    {
      v53 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v77 + 56LL))(v77, &v90);
      v7 = v53;
      if ( v53 >= 0 )
      {
        v54 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v90 + 200LL))(
                v90,
                *((_QWORD *)this + 70),
                0);
        v7 = v54;
        if ( v54 >= 0 )
        {
          v55 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v77 + 152LL))(v77, &v93);
          v7 = v55;
          if ( v55 >= 0 )
          {
            v56 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v77 + 160LL))(v77, &v94);
            v7 = v56;
            if ( v56 >= 0 )
            {
              v57 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v77 + 312LL))(v77, &v91);
              v7 = v57;
              if ( v57 >= 0 )
              {
                v58 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v91 + 56LL))(v91, &v86);
                v7 = v58;
                if ( v58 >= 0 )
                {
                  memset_0(v99, 0, 0x50u);
                  v59 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v86 + 96LL))(v86, v99, 1);
                  v7 = v59;
                  if ( v59 >= 0 )
                  {
                    v87 = v100;
                    v60 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::SetProgress(
                            this,
                            v100,
                            v85);
                    v7 = v60;
                    if ( v60 >= 0 )
                    {
                      v61 = (*(__int64 (__fastcall **)(__int64, CDlpActionLayoutIso *))(*((_QWORD *)v2 + 2) + 8LL))(
                              (__int64)v2 + 16,
                              this);
                      v7 = v61;
                      if ( v61 >= 0 )
                      {
                        v62 = SHCreateStreamOnFileW(*((LPCWSTR *)this + 69), 0x1012u, &v81);
                        v7 = v62;
                        if ( v62 >= 0 )
                        {
                          v85 = 0;
                          v63 = v87;
                          while ( v63 )
                          {
                            v64 = 0x100000;
                            if ( v63 < 0x100000 )
                              v64 = v63;
                            v65 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, int *))(*(_QWORD *)v86 + 24LL))(
                                    v86,
                                    v5,
                                    v64,
                                    &v83);
                            v7 = v65;
                            if ( v65 < 0 )
                            {
                              v12 = *((_QWORD *)this + 11);
                              if ( !v12 )
                                break;
                              v76 = v65;
                              LODWORD(ppv) = 590;
                              goto LABEL_201;
                            }
                            if ( v64 != v83 )
                            {
                              v7 = -2147418113;
                              v8 = *((_QWORD *)this + 11);
                              if ( !v8 )
                                goto LABEL_205;
                              v75 = -2147418113;
                              LODWORD(ppv) = 591;
                              goto LABEL_4;
                            }
                            v66 = (*(__int64 (__fastcall **)(IStream *, void *, _QWORD, int *))(*(_QWORD *)v81 + 32LL))(
                                    v81,
                                    v5,
                                    v64,
                                    &v84);
                            v7 = v66;
                            if ( v66 < 0 )
                            {
                              v12 = *((_QWORD *)this + 11);
                              if ( !v12 )
                                break;
                              v76 = v66;
                              LODWORD(ppv) = 595;
                              goto LABEL_201;
                            }
                            if ( v64 != v84 )
                            {
                              v7 = -2147418113;
                              v8 = *((_QWORD *)this + 11);
                              if ( !v8 )
                                goto LABEL_205;
                              v75 = -2147418113;
                              LODWORD(ppv) = 596;
                              goto LABEL_4;
                            }
                            v85 += v64;
                            v63 -= v64;
                            v67 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::SetProgress(
                                    this,
                                    v87,
                                    v85);
                            v7 = v67;
                            if ( v67 < 0 )
                            {
                              v12 = *((_QWORD *)this + 11);
                              if ( !v12 )
                                break;
                              v76 = v67;
                              LODWORD(ppv) = 605;
                              goto LABEL_201;
                            }
                            v68 = CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::CheckUserInterrupt(this);
                            v7 = v68;
                            if ( v68 < 0 )
                            {
                              v12 = *((_QWORD *)this + 11);
                              if ( !v12 )
                                break;
                              v76 = v68;
                              LODWORD(ppv) = 609;
                              goto LABEL_201;
                            }
                          }
LABEL_204:
                          if ( v7 >= 0 )
                            goto LABEL_211;
                          goto LABEL_205;
                        }
                        v12 = *((_QWORD *)this + 11);
                        if ( !v12 )
                          goto LABEL_204;
                        v76 = v62;
                        LODWORD(ppv) = 572;
                      }
                      else
                      {
                        v12 = *((_QWORD *)this + 11);
                        if ( !v12 )
                          goto LABEL_204;
                        v76 = v61;
                        LODWORD(ppv) = 566;
                      }
                    }
                    else
                    {
                      v12 = *((_QWORD *)this + 11);
                      if ( !v12 )
                        goto LABEL_204;
                      v76 = v60;
                      LODWORD(ppv) = 562;
                    }
                  }
                  else
                  {
                    v12 = *((_QWORD *)this + 11);
                    if ( !v12 )
                      goto LABEL_204;
                    v76 = v59;
                    LODWORD(ppv) = 557;
                  }
                }
                else
                {
                  v12 = *((_QWORD *)this + 11);
                  if ( !v12 )
                    goto LABEL_204;
                  v76 = v58;
                  LODWORD(ppv) = 552;
                }
              }
              else
              {
                v12 = *((_QWORD *)this + 11);
                if ( !v12 )
                  goto LABEL_204;
                v76 = v57;
                LODWORD(ppv) = 548;
              }
            }
            else
            {
              v12 = *((_QWORD *)this + 11);
              if ( !v12 )
                goto LABEL_204;
              v76 = v56;
              LODWORD(ppv) = 544;
            }
          }
          else
          {
            v12 = *((_QWORD *)this + 11);
            if ( !v12 )
              goto LABEL_204;
            v76 = v55;
            LODWORD(ppv) = 543;
          }
        }
        else
        {
          v12 = *((_QWORD *)this + 11);
          if ( !v12 )
            goto LABEL_204;
          v76 = v54;
          LODWORD(ppv) = 539;
        }
      }
      else
      {
        v12 = *((_QWORD *)this + 11);
        if ( !v12 )
          goto LABEL_204;
        v76 = v53;
        LODWORD(ppv) = 535;
      }
    }
LABEL_201:
    v69 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v12,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpActionLayoutIso::ExecuteRoutine",
            ppv,
            v76);
    v70 = (unsigned int)v69;
    if ( v69 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v69);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v70);
    goto LABEL_204;
  }
  rgIndices = 0;
  Vector = SafeArrayCreateVector(0xCu, 0, 2u);
  v6 = Vector;
  if ( Vector )
  {
    v98 = Vector;
    VariantInit(&pvarg);
    pvarg.vt = 9;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v80 + 8LL))(v80);
    pvarg.llVal = (LONGLONG)v80;
    v41 = SafeArrayPutElement(v6, &rgIndices, &pvarg);
    v7 = v41;
    if ( v41 < 0 )
    {
      v12 = *((_QWORD *)this + 11);
      if ( !v12 )
        goto LABEL_204;
      v76 = v41;
      LODWORD(ppv) = 500;
      goto LABEL_201;
    }
    if ( rgIndices < 0 )
    {
      v7 = -2147024809;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942487LL);
LABEL_110:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
      if ( v7 < 0 )
      {
        v12 = *((_QWORD *)this + 11);
        if ( !v12 )
          goto LABEL_204;
        v76 = v7;
        LODWORD(ppv) = 501;
        goto LABEL_201;
      }
      VariantClear(&pvarg);
      VariantInit(&pvarg);
      pvarg.vt = 9;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v79 + 8LL))(v79);
      pvarg.llVal = (LONGLONG)v79;
      v44 = SafeArrayPutElement(v6, &rgIndices, &pvarg);
      v7 = v44;
      if ( v44 < 0 )
      {
        v12 = *((_QWORD *)this + 11);
        if ( !v12 )
          goto LABEL_204;
        v76 = v44;
        LODWORD(ppv) = 508;
        goto LABEL_201;
      }
      if ( rgIndices < 0 )
      {
        v7 = -2147024809;
        v46 = 2147942487LL;
      }
      else
      {
        v45 = rgIndices + 1;
        if ( rgIndices + 1 < (unsigned int)rgIndices )
        {
          v45 = 0;
          v7 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v7 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
        if ( v7 >= 0 )
        {
          if ( v45 >= 0 )
          {
            rgIndices = v45;
LABEL_127:
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
            if ( v7 < 0 )
            {
              v12 = *((_QWORD *)this + 11);
              if ( !v12 )
                goto LABEL_204;
              v76 = v7;
              LODWORD(ppv) = 509;
              goto LABEL_201;
            }
            VariantClear(&pvarg);
            v47 = (*(__int64 (__fastcall **)(LPVOID, SAFEARRAY *))(*(_QWORD *)v82 + 464LL))(v82, v6);
            v7 = v47;
            if ( v47 < 0 )
            {
              v12 = *((_QWORD *)this + 11);
              if ( !v12 )
                goto LABEL_204;
              v76 = v47;
              LODWORD(ppv) = 514;
              goto LABEL_201;
            }
            goto LABEL_144;
          }
          v7 = -2147024362;
          v46 = 2147942934LL;
        }
        else
        {
          v46 = (unsigned int)v7;
        }
      }
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v46);
      goto LABEL_127;
    }
    v42 = rgIndices + 1;
    if ( rgIndices + 1 < (unsigned int)rgIndices )
    {
      v42 = 0;
      v7 = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
    }
    else
    {
      v7 = 0;
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
    if ( v7 >= 0 )
    {
      if ( v42 >= 0 )
      {
        rgIndices = v42;
        goto LABEL_105;
      }
      v43 = 2147942934LL;
      v7 = -2147024362;
    }
    else
    {
      v43 = (unsigned int)v7;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v43);
LABEL_105:
    v2 = v95;
    goto LABEL_110;
  }
  v98 = 0;
  v7 = -2147024882;
  v8 = *((_QWORD *)this + 11);
  if ( v8 )
  {
    v75 = -2147024882;
    LODWORD(ppv) = 494;
    goto LABEL_4;
  }
LABEL_205:
  v71 = v81;
  if ( v81 )
  {
    if ( *((_QWORD *)this + 11) )
    {
      CDlpLogT<CEmptyType>::DlpLogFormat(
        *((_QWORD *)this + 11),
        4,
        L"LayoutIso: Deleting ISO file due to error: 0x%X",
        (unsigned int)v7);
      v71 = v81;
    }
    if ( v71 )
    {
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v71 + 16LL))(v71);
      v81 = 0;
    }
    SetFileAttributesW(*((LPCWSTR *)this + 69), 0x80u);
    DeleteFileW(*((LPCWSTR *)this + 69));
  }
LABEL_211:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( v6 )
    SafeArrayDestroy(v6);
  if ( v5 )
  {
    v72 = GetProcessHeap();
    HeapFree(v72, 0, v5);
  }
  if ( v88 )
  {
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v88 + 16LL))(v88);
    v88 = 0;
  }
  if ( ppstm )
  {
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
  }
  if ( v81 )
  {
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v81 + 16LL))(v81);
    v81 = 0;
  }
  if ( v86 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
    v86 = 0;
  }
  if ( v79 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v79 + 16LL))(v79);
    v79 = 0;
  }
  if ( v80 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v80 + 16LL))(v80);
    v80 = 0;
  }
  if ( v90 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
    v90 = 0;
  }
  if ( v91 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
    v91 = 0;
  }
  if ( v82 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v82 + 16LL))(v82);
    v82 = 0;
  }
  if ( v77 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v77 + 16LL))(v77);
    v77 = 0;
  }
  if ( v4 )
    CoUninitialize();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800153d0  mov     [rsp-8+arg_10], rbx
0x1800153d5  push    rbp
0x1800153d6  push    rsi
0x1800153d7  push    rdi
0x1800153d8  push    r12
0x1800153da  push    r13
0x1800153dc  push    r14
0x1800153de  push    r15
0x1800153e0  lea     rbp, [rsp-40h]
0x1800153e5  sub     rsp, 140h
0x1800153ec  mov     rax, cs:__security_cookie
0x1800153f3  xor     rax, rsp
0x1800153f6  mov     [rbp+70h+var_40], rax
0x1800153fa  mov     r13, rdx
0x1800153fd  mov     [rbp+70h+var_C0], rdx
0x180015401  mov     r12, rcx
0x180015404  xor     r14d, r14d
0x180015407  mov     [rbp+70h+var_D0], r14d
0x18001540b  mov     [rsp+170h+var_140], r14
0x180015410  mov     [rsp+170h+var_118], r14
0x180015415  mov     [rbp+70h+var_D8], r14
0x180015419  mov     [rbp+70h+var_E0], r14
0x18001541d  mov     [rsp+170h+var_128], r14
0x180015422  mov     [rsp+170h+var_130], r14
0x180015427  mov     [rsp+170h+var_100], r14
0x18001542c  mov     [rsp+170h+var_120], r14
0x180015431  mov     [rbp+70h+ppstm], r14
0x180015435  mov     [rbp+70h+var_F0], r14
0x180015439  xor     edi, edi
0x18001543b  mov     [rbp+70h+var_A0], rdi
0x18001543f  xor     esi, esi
0x180015441  mov     [rbp+70h+var_98], rsi
0x180015445  xorps   xmm0, xmm0
0x180015448  xor     eax, eax
0x18001544a  movups  xmmword ptr [rbp+70h+pvarg], xmm0
0x18001544e  mov     qword ptr [rbp+70h+pvarg+10h], rax
0x180015452  mov     [rsp+170h+rgIndices], eax
0x180015456  mov     [rsp+170h+var_110], eax
0x18001545a  mov     [rsp+170h+var_10C], eax
0x18001545e  mov     [rbp+70h+var_CC], eax
0x180015461  mov     [rbp+70h+var_C8], eax
0x180015464  xor     edx, edx; Val
0x180015466  lea     r8d, [r14+50h]; Size
0x18001546a  lea     rcx, [rbp+70h+var_90]; void *
0x18001546e  call    memset_0
0x180015473  mov     [rsp+170h+var_F8], rsi
0x180015478  mov     [rsp+170h+var_108], rsi
0x18001547d  test    r13, r13
0x180015480  jnz     short loc_1800154D1
0x180015482  mov     ebx, 80070057h
0x180015487  mov     r15d, ebx
0x18001548a  mov     rcx, [r12+58h]
0x18001548f  test    rcx, rcx
0x180015492  jz      loc_1800162AF
0x180015498  mov     [rsp+170h+var_148], ebx
0x18001549c  mov     dword ptr [rsp+170h+ppv], 165h
0x1800154a4  lea     r9, aCdlpactionlayo_27; "CDlpActionLayoutIso::ExecuteRoutine"
0x1800154ab  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800154b2  mov     edx, 4
0x1800154b7  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800154bc  test    eax, eax
0x1800154be  mov     ecx, eax
0x1800154c0  jns     short loc_1800154C7
0x1800154c2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800154c7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800154cc  jmp     loc_180016243
0x1800154d1  mov     rax, [r12]
0x1800154d5  xor     r9d, r9d
0x1800154d8  lea     r8, [rsp+170h+var_108]
0x1800154dd  lea     rdx, [rsp+170h+var_F8]
0x1800154e2  mov     rcx, r12
0x1800154e5  mov     rax, [rax+48h]
0x1800154e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154ee  mov     r15d, eax
0x1800154f1  test    eax, eax
0x1800154f3  jns     short loc_180015514
0x1800154f5  mov     rcx, [r12+58h]
0x1800154fa  test    rcx, rcx
0x1800154fd  jz      loc_18001623E
0x180015503  mov     [rsp+170h+var_148], eax
0x180015507  mov     dword ptr [rsp+170h+ppv], 16Bh
0x18001550f  jmp     loc_180016216
0x180015514  call    cs:__imp_GetProcessHeap
0x18001551a  mov     rcx, rax; hHeap
0x18001551d  xor     edx, edx; dwFlags
0x18001551f  mov     r8d, 100000h; dwBytes
0x180015525  call    cs:__imp_HeapAlloc
0x18001552b  mov     rdi, rax
0x18001552e  test    rax, rax
0x180015531  jnz     short loc_18001555E
0x180015533  mov     [rbp+70h+var_A0], rax
0x180015537  mov     eax, 8007000Eh
0x18001553c  mov     r15d, eax
0x18001553f  mov     rcx, [r12+58h]
0x180015544  test    rcx, rcx
0x180015547  jz      loc_180016243
0x18001554d  mov     [rsp+170h+var_148], eax
0x180015551  mov     dword ptr [rsp+170h+ppv], 171h
0x180015559  jmp     loc_1800154A4
0x18001555e  mov     [rbp+70h+var_A0], rdi
0x180015562  xor     r15d, r15d
0x180015565  xor     edx, edx; dwCoInit
0x180015567  xor     ecx, ecx; pvReserved
0x180015569  call    cs:__imp_CoInitializeEx
0x18001556f  test    eax, eax
0x180015571  js      short loc_18001557D
0x180015573  lea     r14d, [r15+1]
0x180015577  mov     [rbp+70h+var_D0], r14d
0x18001557b  jmp     short loc_18001558E
0x18001557d  cmp     eax, 80010106h
0x180015582  jz      short loc_18001558E
0x180015584  mov     r15d, eax
0x180015587  mov     ecx, eax
0x180015589  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001558e  mov     ecx, r15d
0x180015591  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180015596  test    r15d, r15d
0x180015599  jns     short loc_1800155BB
0x18001559b  mov     rcx, [r12+58h]
0x1800155a0  test    rcx, rcx
0x1800155a3  jz      loc_18001623E
0x1800155a9  mov     [rsp+170h+var_148], r15d
0x1800155ae  mov     dword ptr [rsp+170h+ppv], 175h
0x1800155b6  jmp     loc_180016216
0x1800155bb  lea     rax, [rsp+170h+var_140]
0x1800155c0  mov     [rsp+170h+ppv], rax; ppv
0x1800155c5  lea     r9, _GUID_2c941fe1_975b_59be_a960_9a2a262853a5; riid
0x1800155cc  mov     ebx, 17h
0x1800155d1  mov     r8d, ebx; dwClsContext
0x1800155d4  xor     edx, edx; pUnkOuter
0x1800155d6  lea     rcx, CLSID_MsftFileSystemImage; rclsid
0x1800155dd  call    cs:__imp_CoCreateInstance
0x1800155e3  mov     r15d, eax
0x1800155e6  mov     rcx, [r12+58h]
0x1800155eb  test    eax, eax
0x1800155ed  jns     short loc_180015609
0x1800155ef  test    rcx, rcx
0x1800155f2  jz      loc_18001623E
0x1800155f8  mov     [rsp+170h+var_148], eax
0x1800155fc  mov     dword ptr [rsp+170h+ppv], 17Ch
0x180015604  jmp     loc_180016216
0x180015609  mov     r15d, 2
0x18001560f  test    rcx, rcx
0x180015612  jz      short loc_180015623
0x180015614  lea     r8, aLayoutisoSucce_0; "LayoutIso: Successfully created IFileSy"...
0x18001561b  mov     edx, r15d
0x18001561e  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180015623  lea     rax, [rsp+170h+var_118]
0x180015628  mov     [rsp+170h+ppv], rax; ppv
0x18001562d  lea     r9, _GUID_d7644b2c_1537_4767_b62f_f1387b02ddfd; riid
0x180015634  mov     r8d, ebx; dwClsContext
0x180015637  xor     edx, edx; pUnkOuter
0x180015639  lea     rcx, CLSID_MsftFileSystemImage; rclsid
0x180015640  call    cs:__imp_CoCreateInstance
0x180015646  mov     rcx, [r12+58h]
0x18001564b  test    eax, eax
0x18001564d  js      short loc_1800156B7
0x18001564f  test    rcx, rcx
0x180015652  jz      short loc_180015663
0x180015654  lea     r8, aLayoutisoSucce; "LayoutIso: Successfully retrieved IFile"...
0x18001565b  mov     edx, r15d
0x18001565e  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180015663  mov     rcx, [rsp+170h+var_140]
0x180015668  test    rcx, rcx
0x18001566b  jz      short loc_180015683
0x18001566d  mov     rax, [rcx]
0x180015670  mov     rax, [rax+10h]
0x180015674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015679  nop
0x18001567a  mov     [rsp+170h+var_140], 0
0x180015683  mov     rcx, [rsp+170h+var_118]
0x180015688  mov     rax, [rcx]
0x18001568b  mov     rax, [rax+8]
0x18001568f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015694  mov     rbx, [rsp+170h+var_118]
0x180015699  mov     rcx, [rsp+170h+var_140]
0x18001569e  test    rcx, rcx
0x1800156a1  jz      short loc_1800156B0
0x1800156a3  mov     rax, [rcx]
0x1800156a6  mov     rax, [rax+10h]
0x1800156aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156af  nop
0x1800156b0  mov     [rsp+170h+var_140], rbx
0x1800156b5  jmp     short loc_1800156D0
0x1800156b7  test    rcx, rcx
0x1800156ba  jz      short loc_1800156D0
0x1800156bc  mov     r9d, eax
0x1800156bf  lea     r8, aLayoutisoUnabl; "LayoutIso: Unable to retrieve IFileSyst"...
0x1800156c6  mov     edx, 3
0x1800156cb  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800156d0  mov     rcx, [rsp+170h+var_140]
0x1800156d5  mov     rax, [rcx]
0x1800156d8  xor     edx, edx
0x1800156da  mov     rax, [rax+58h]
0x1800156de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156e3  mov     r15d, eax
0x1800156e6  test    eax, eax
0x1800156e8  jns     short loc_180015709
0x1800156ea  mov     rcx, [r12+58h]
0x1800156ef  test    rcx, rcx
0x1800156f2  jz      loc_18001623E
0x1800156f8  mov     [rsp+170h+var_148], eax
0x1800156fc  mov     dword ptr [rsp+170h+ppv], 196h
0x180015704  jmp     loc_180016216
0x180015709  mov     rcx, [rsp+170h+var_140]
0x18001570e  mov     rax, [rcx]
0x180015711  mov     edx, 4
0x180015716  mov     rax, [rax+0E8h]
0x18001571d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015722  mov     r15d, eax
0x180015725  test    eax, eax
0x180015727  jns     short loc_180015748
0x180015729  mov     rcx, [r12+58h]
0x18001572e  test    rcx, rcx
0x180015731  jz      loc_18001623E
0x180015737  mov     [rsp+170h+var_148], eax
0x18001573b  mov     dword ptr [rsp+170h+ppv], 19Ah
0x180015743  jmp     loc_180016216
0x180015748  mov     rcx, [rsp+170h+var_140]
0x18001574d  mov     rax, [rcx]
0x180015750  mov     edx, 102h
0x180015755  mov     rax, [rax+0F8h]
0x18001575c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015761  mov     r15d, eax
0x180015764  test    eax, eax
0x180015766  jns     short loc_180015787
0x180015768  mov     rcx, [r12+58h]
0x18001576d  test    rcx, rcx
0x180015770  jz      loc_18001623E
0x180015776  mov     [rsp+170h+var_148], eax
0x18001577a  mov     dword ptr [rsp+170h+ppv], 19Bh
0x180015782  jmp     loc_180016216
0x180015787  mov     rcx, [r12+238h]; lpFileName
0x18001578f  test    rcx, rcx
0x180015792  jz      loc_180015906
0x180015798  call    cs:__imp_GetFileAttributesW
0x18001579e  mov     ebx, eax
0x1800157a0  cmp     eax, 0FFFFFFFFh
0x1800157a3  jz      short loc_1800157AF
0x1800157a5  shr     ebx, 4
0x1800157a8  not     ebx
0x1800157aa  and     ebx, 1
0x1800157ad  jmp     short loc_1800157B1
0x1800157af  xor     ebx, ebx
0x1800157b1  xor     ecx, ecx
0x1800157b3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800157b8  xor     ecx, ecx
0x1800157ba  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800157bf  test    ebx, ebx
0x1800157c1  jnz     short loc_18001580B
0x1800157c3  mov     rcx, [r12+58h]
0x1800157c8  test    rcx, rcx
0x1800157cb  jz      short loc_1800157E4
0x1800157cd  mov     r9, [r12+238h]
0x1800157d5  lea     r8, aLayoutisoSpeci; "LayoutIso: Specified boot file [%s] is "...
0x1800157dc  lea     edx, [rbx+4]
0x1800157df  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800157e4  mov     eax, 0C1800110h
0x1800157e9  mov     r15d, eax
0x1800157ec  mov     rcx, [r12+58h]
0x1800157f1  test    rcx, rcx
0x1800157f4  jz      loc_180016243
0x1800157fa  mov     [rsp+170h+var_148], eax
0x1800157fe  mov     dword ptr [rsp+170h+ppv], 1A7h
0x180015806  jmp     loc_1800154A4
0x18001580b  lea     rax, [rsp+170h+var_128]
0x180015810  mov     [rsp+170h+ppv], rax; ppv
0x180015815  lea     r9, _GUID_2c941fd4_975b_59be_a960_9a2a262853a5; riid
0x18001581c  xor     edx, edx; pUnkOuter
0x18001581e  lea     r8d, [rdx+17h]; dwClsContext
0x180015822  lea     rcx, CLSID_BootOptions; rclsid
0x180015829  call    cs:__imp_CoCreateInstance
0x18001582f  mov     r15d, eax
0x180015832  test    eax, eax
0x180015834  jns     short loc_180015855
0x180015836  mov     rcx, [r12+58h]
0x18001583b  test    rcx, rcx
0x18001583e  jz      loc_18001623E
0x180015844  mov     [rsp+170h+var_148], eax
0x180015848  mov     dword ptr [rsp+170h+ppv], 1AFh
0x180015850  jmp     loc_180016216
0x180015855  lea     r8, [rbp+70h+ppstm]; ppstm
0x180015859  mov     edx, 20h ; ' '; grfMode
0x18001585e  mov     rcx, [r12+238h]; pszFile
0x180015866  call    cs:__imp_SHCreateStreamOnFileW
0x18001586c  mov     r15d, eax
0x18001586f  test    eax, eax
0x180015871  jns     short loc_180015892
0x180015873  mov     rcx, [r12+58h]
0x180015878  test    rcx, rcx
0x18001587b  jz      loc_18001623E
0x180015881  mov     [rsp+170h+var_148], eax
0x180015885  mov     dword ptr [rsp+170h+ppv], 1B5h
0x18001588d  jmp     loc_180016216
0x180015892  mov     rcx, [rsp+170h+var_128]
0x180015897  mov     rax, [rcx]
0x18001589a  mov     rdx, [rbp+70h+ppstm]
0x18001589e  mov     rax, [rax+78h]
0x1800158a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158a7  mov     r15d, eax
  ... truncated ...
```
