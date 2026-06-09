# CInvertedStoreDocument::AddProperty(tagSTAT_CHUNK const *,tagGATHER_CHUNK_ATTRIBUTES const *,tagPROPVARIANT const *,tagTEXT_SOURCE const *,IWordSink * *)

- ea: `0x180055c10`
- end: `0x180056724`
- name: `?AddProperty@CInvertedStoreDocument@@UEAAJPEBUtagSTAT_CHUNK@@PEBUtagGATHER_CHUNK_ATTRIBUTES@@PEBUtagPROPVARIANT@@PEBUtagTEXT_SOURCE@@PEAPEAUIWordSink@@@Z`
- size: `2836`
- prototype: `__int64 __usercall@<rax>(CInvertedStoreDocument *__hidden this@<rcx>, const struct tagSTAT_CHUNK *@<rdx>, const struct tagGATHER_CHUNK_ATTRIBUTES *@<r8>, const struct tagPROPVARIANT *@<r9>, const struct tagTEXT_SOURCE *, struct IWordSink **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180055be0`

## callees

- `0x180030a84`
- `0x180038f08`
- `0x180055c10`
- `0x18005672c`
- `0x18005679c`
- `0x1800c45c4`
- `0x1800c4b14`
- `0x18015708c`
- `0x18017504c`
- `0x180188d90`
- `0x180189280`
- `0x18018a0e1`
- `0x1801f2b00`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005613b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005613b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b7d31`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b7d59`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b7d85`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b7dca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b7df8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b7e23`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b7e4e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b7e79`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b7d31`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b7d59`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b7d85`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b7dca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b7df8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b7e23`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b7e4e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1802b7e79`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180055dfa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180055fa3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800560e6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180055dfa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180055fa3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800560e6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1802b7eb9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1802b7eb9`
- `OLEAUT32!__imp_VariantChangeType` at `0x180056362`
- `OLEAUT32!__imp_VariantChangeType` at `0x180056362`
- `PROPSYS!PropVariantChangeType` at `0x180055f3c`
- `PROPSYS!PropVariantChangeType` at `0x180055f8a`
- `PROPSYS!PropVariantChangeType` at `0x180055fd5`
- `PROPSYS!PropVariantChangeType` at `0x1800560af`
- `PROPSYS!PropVariantChangeType` at `0x180056192`
- `PROPSYS!PropVariantChangeType` at `0x180056247`
- `PROPSYS!PropVariantChangeType` at `0x1800562bc`
- `PROPSYS!PropVariantChangeType` at `0x180056304`
- `PROPSYS!PropVariantChangeType` at `0x180056537`
- `PROPSYS!PropVariantChangeType` at `0x18005657f`
- `PROPSYS!PropVariantChangeType` at `0x180056603`
- `PROPSYS!PropVariantChangeType` at `0x18005664c`
- `PROPSYS!PropVariantChangeType` at `0x180056695`
- `PROPSYS!PropVariantChangeType` at `0x1802b7cb6`
- `PROPSYS!PropVariantChangeType` at `0x180055f3c`
- `PROPSYS!PropVariantChangeType` at `0x180055f8a`
- `PROPSYS!PropVariantChangeType` at `0x180055fd5`
- `PROPSYS!PropVariantChangeType` at `0x1800560af`
- `PROPSYS!PropVariantChangeType` at `0x180056192`
- `PROPSYS!PropVariantChangeType` at `0x180056247`
- `PROPSYS!PropVariantChangeType` at `0x1800562bc`
- `PROPSYS!PropVariantChangeType` at `0x180056304`
- `PROPSYS!PropVariantChangeType` at `0x180056537`
- `PROPSYS!PropVariantChangeType` at `0x18005657f`
- `PROPSYS!PropVariantChangeType` at `0x180056603`
- `PROPSYS!PropVariantChangeType` at `0x18005664c`
- `PROPSYS!PropVariantChangeType` at `0x180056695`
- `PROPSYS!PropVariantChangeType` at `0x1802b7cb6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CInvertedStoreDocument::AddProperty(
        CInvertedStoreDocument *this,
        const struct tagSTAT_CHUNK *a2,
        const struct tagGATHER_CHUNK_ATTRIBUTES *a3,
        PROPVARIANT *p_pvar,
        const struct tagTEXT_SOURCE *a5,
        struct IWordSink **a6)
{
  const struct tagSTAT_CHUNK *v7; // rsi
  struct IWordSink **v9; // rbx
  unsigned int v10; // r15d
  unsigned int v11; // r13d
  char v12; // dl
  __int64 v13; // rcx
  VARTYPE v14; // si
  __int64 v16; // r8
  unsigned __int64 v17; // rax
  int v18; // esi
  __int64 v19; // rsi
  SHORT iVal; // ax
  LONG lVal; // r12d
  HRESULT v22; // eax
  const WCHAR *v23; // rax
  IRecordInfo *v24; // rbx
  int v25; // eax
  __int64 v26; // rsi
  LONG v27; // r13d
  LONG i; // r12d
  int v29; // edx
  __int64 v30; // rcx
  BYTE bVal; // al
  struct IRecordInfoVtbl *lpVtbl; // r15
  BYTE *v33; // r15
  LONG v34; // ebx
  int bIgnoreCase; // [rsp+20h] [rbp-148h]
  char v36; // [rsp+30h] [rbp-138h]
  _BYTE v37[7]; // [rsp+31h] [rbp-137h] BYREF
  VARIANTARG pvar; // [rsp+38h] [rbp-130h] BYREF
  LONG v39; // [rsp+50h] [rbp-118h] BYREF
  unsigned int v40; // [rsp+54h] [rbp-114h]
  LPCWCH lpString1; // [rsp+58h] [rbp-110h]
  const struct tagSTAT_CHUNK *v42; // [rsp+60h] [rbp-108h] BYREF
  void **v43; // [rsp+68h] [rbp-100h] BYREF
  SIZE_T cb; // [rsp+70h] [rbp-F8h]
  void **v45; // [rsp+78h] [rbp-F0h] BYREF
  int v46; // [rsp+80h] [rbp-E8h]
  const WCHAR *v47; // [rsp+88h] [rbp-E0h]
  const WCHAR *v48; // [rsp+90h] [rbp-D8h]
  char *v49; // [rsp+98h] [rbp-D0h]
  struct IWordSink **v50; // [rsp+A0h] [rbp-C8h]
  const WCHAR *v51; // [rsp+B0h] [rbp-B8h]
  _DWORD v52[2]; // [rsp+B8h] [rbp-B0h]
  const wchar_t *v53; // [rsp+C0h] [rbp-A8h]
  int v54; // [rsp+C8h] [rbp-A0h]
  const wchar_t *v55; // [rsp+D0h] [rbp-98h]
  int v56; // [rsp+D8h] [rbp-90h]
  const wchar_t *v57; // [rsp+E0h] [rbp-88h]
  int v58; // [rsp+E8h] [rbp-80h]
  const wchar_t *v59; // [rsp+F0h] [rbp-78h]
  int v60; // [rsp+F8h] [rbp-70h]
  const WCHAR *v61; // [rsp+100h] [rbp-68h]
  int v62; // [rsp+108h] [rbp-60h]
  __int64 v63; // [rsp+110h] [rbp-58h] BYREF
  int v64; // [rsp+118h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v7 = a2;
  v42 = a2;
  v9 = a6;
  v50 = a6;
  v10 = 0;
  *a6 = 0;
  v40 = 0;
  if ( *((_DWORD *)a3 + 6) >= 0x4000u )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\tripolipi\\inverteddocument.cpp",
      (const char *)0x8000FFFFLL,
      bIgnoreCase);
  v63 = 0;
  v64 = 0;
  v11 = *((unsigned __int16 *)a3 + 12);
  LOWORD(v39) = v11;
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 8) + 64LL))(
          *((_QWORD *)this + 8),
          (unsigned __int16)v11,
          &v63);
  v36 = v12;
  v37[0] = 1;
  if ( !p_pvar )
    goto LABEL_28;
  v13 = v11;
  if ( v11 == *((_DWORD *)this + 23) )
  {
    memset(&pvar, 0, sizeof(pvar));
    if ( PropVariantChangeType((PROPVARIANT *)&pvar, p_pvar, 2, 0xBu) >= 0 )
      *((_BYTE *)this + 176) = pvar.iVal != 0;
    goto LABEL_53;
  }
  if ( v11 == *((_DWORD *)this + 24) )
  {
    memset(&pvar, 0, sizeof(pvar));
    if ( PropVariantChangeType((PROPVARIANT *)&pvar, p_pvar, 2, 0x13u) >= 0 )
      *((_DWORD *)this + 54) = pvar.lVal;
    goto LABEL_53;
  }
  if ( v11 == *((_DWORD *)this + 36) )
  {
    memset(&pvar, 0, sizeof(pvar));
    if ( PropVariantChangeType((PROPVARIANT *)&pvar, p_pvar, 2, 0x1Fu) >= 0 && pvar.llVal )
    {
      v26 = -1;
      do
        ++v26;
      while ( *(_WORD *)(pvar.llVal + 2 * v26) );
      std::wstring::_Assign<wchar_t>((char *)this + 224, pvar.llVal, v26);
    }
    goto LABEL_53;
  }
  if ( v11 == *((_DWORD *)this + 34) )
  {
    memset(&pvar, 0, sizeof(pvar));
    if ( PropVariantChangeType((PROPVARIANT *)&pvar, p_pvar, 2, 0x13u) >= 0 && pvar.lVal < 0 )
      *((_DWORD *)this + 64) |= 0x40u;
    goto LABEL_53;
  }
  if ( v11 == *((_DWORD *)this + 35) )
  {
    memset(&pvar, 0, sizeof(pvar));
    if ( PropVariantChangeType((PROPVARIANT *)&pvar, p_pvar, 2, 0x13u) >= 0 )
      *((_DWORD *)this + 64) |= 0x1000000u;
    goto LABEL_53;
  }
  if ( v11 == *((_DWORD *)this + 29) )
  {
    memset(&pvar, 0, sizeof(pvar));
    if ( PropVariantChangeType((PROPVARIANT *)&pvar, p_pvar, 2, 0x13u) >= 0 )
    {
      bVal = pvar.bVal;
      if ( (pvar.bVal & 1) != 0 )
      {
        ETWLog::Log(
          L"CInvertedDocument::AddProperty, SyncTransferStatus CP_TRANSFERSTATUS_UPLOADING for wid: %d",
          *((unsigned int *)this + 70));
        *((_DWORD *)this + 64) |= 0x100000u;
        bVal = pvar.bVal;
      }
      if ( (bVal & 2) != 0 )
      {
        ETWLog::Log(
          L"CInvertedDocument::AddProperty, SyncTransferStatus CP_TRANSFERSTATUS_DOWNLOADING for wid: %d",
          *((unsigned int *)this + 70));
        *((_DWORD *)this + 64) |= 0x200000u;
      }
    }
    goto LABEL_53;
  }
  if ( v11 == *((_DWORD *)this + 30) )
  {
    memset(&pvar, 0, sizeof(pvar));
    if ( PropVariantChangeType((PROPVARIANT *)&pvar, p_pvar, 2, 0x13u) >= 0 )
    {
      iVal = pvar.iVal;
      if ( (pvar.bVal & 1) != 0 )
      {
        ETWLog::Log(
          L"CInvertedDocument::AddProperty, SyncTransferStatus CP_TRANSFERSTATUS_UPLOADING for wid: %d",
          *((unsigned int *)this + 70));
        *((_DWORD *)this + 64) |= 0x100000u;
        iVal = pvar.iVal;
      }
      if ( (iVal & 2) != 0 )
      {
        ETWLog::Log(
          L"CInvertedDocument::AddProperty, SyncTransferStatus CP_TRANSFERSTATUS_DOWNLOADING for wid: %d",
          *((unsigned int *)this + 70));
        *((_DWORD *)this + 64) |= 0x200000u;
        iVal = pvar.iVal;
      }
      if ( (iVal & 0x100) != 0 )
      {
        ETWLog::Log(
          L"CInvertedDocument::AddProperty, SyncTransferStatus CP_EXCLUDEDFROMSYNC for wid: %d",
          *((unsigned int *)this + 70));
        *((_DWORD *)this + 64) |= 0x2000000u;
        iVal = pvar.iVal;
      }
      if ( (iVal & 0x10) != 0 )
      {
        ETWLog::Log(
          L"CInvertedDocument::AddProperty, SyncTransferStatus CP_HASLASTSYNCERROR for wid: %d",
          *((unsigned int *)this + 70));
        *((_DWORD *)this + 64) |= 0x40u;
        iVal = pvar.iVal;
      }
      if ( (iVal & 0x80u) != 0 )
      {
        ETWLog::Log(
          L"CInvertedDocument::AddProperty, SyncTransferStatus CP_HASLASTSYNCWARNING for wid: %d",
          *((unsigned int *)this + 70));
        *((_DWORD *)this + 64) |= 0x1000000u;
        iVal = pvar.iVal;
      }
      if ( (iVal & 0x400) != 0 )
      {
        ETWLog::Log(
          L"CInvertedDocument::AddProperty, SyncTransferStatus CP_EMPTYFOLDERASPLACEHOLDER for wid: %d",
          *((unsigned int *)this + 70));
        *((_DWORD *)this + 64) |= 0x8000000u;
      }
    }
    goto LABEL_53;
  }
  if ( v11 == *((_DWORD *)this + 27) )
  {
    memset(&pvar, 0, sizeof(pvar));
    if ( PropVariantChangeType((PROPVARIANT *)&pvar, p_pvar, 2, 0x101Fu) < 0 )
      goto LABEL_53;
    lVal = pvar.lVal;
    if ( pvar.lVal <= 0 )
      goto LABEL_53;
    do
    {
      lpString1 = (LPCWCH)pvar.pRecInfo[v10].lpVtbl;
      if ( CompareStringOrdinal(lpString1, -1, L"unknown", -1, 1) == 2 )
      {
        *((_DWORD *)this + 64) |= 4u;
      }
      else if ( CompareStringOrdinal(lpString1, -1, L"document", -1, 1) == 2 )
      {
        *((_DWORD *)this + 64) |= 0x20u;
      }
      else if ( CompareStringOrdinal(lpString1, -1, L"picture", -1, 1) == 2 )
      {
        *((_DWORD *)this + 64) |= 0x10u;
      }
      ++v10;
    }
    while ( (int)v10 < lVal );
    goto LABEL_62;
  }
  if ( v11 == *((_DWORD *)this + 28) )
  {
    memset(&pvar, 0, sizeof(pvar));
    if ( PropVariantChangeType((PROPVARIANT *)&pvar, p_pvar, 2, 0x101Fu) < 0 )
      goto LABEL_53;
    v27 = pvar.lVal;
    for ( i = 0; i < v27; ++i )
    {
      lpVtbl = pvar.pRecInfo[i].lpVtbl;
      if ( CompareStringOrdinal((LPCWCH)lpVtbl, -1, L"Private", -1, 1) == 2 )
      {
        *((_DWORD *)this + 64) |= 0x8000u;
      }
      else if ( CompareStringOrdinal((LPCWCH)lpVtbl, -1, L"Shared", -1, 1) == 2 )
      {
        *((_DWORD *)this + 64) |= 0x10000u;
      }
      else if ( CompareStringOrdinal((LPCWCH)lpVtbl, -1, L"Public", -1, 1) == 2 )
      {
        *((_DWORD *)this + 64) |= 0x20000u;
      }
      else if ( CompareStringOrdinal((LPCWCH)lpVtbl, -1, L"Group", -1, 1) == 2 )
      {
        *((_DWORD *)this + 64) |= 0x40000u;
      }
      else if ( CompareStringOrdinal((LPCWCH)lpVtbl, -1, L"Owner", -1, 1) == 2 )
      {
        *((_DWORD *)this + 64) |= 0x80000u;
      }
    }
    goto LABEL_62;
  }
  if ( v11 == *((_DWORD *)this + 37) )
  {
    memset(&pvar, 0, sizeof(pvar));
    if ( PropVariantChangeType((PROPVARIANT *)&pvar, p_pvar, 2, 0x101Fu) < 0 )
    {
LABEL_53:
      PropVariantClear((PROPVARIANT *)&pvar);
      v12 = v36;
      goto LABEL_18;
    }
    v51 = L"picture";
    v52[0] = 1;
    v53 = L"music";
    v54 = 2;
    v55 = L"video";
    v56 = 4;
    v57 = L"movie";
    v58 = 8;
    v59 = L"recordedtv";
    v60 = 16;
    v61 = L"document";
    v62 = 32;
    v18 = 0;
    if ( pvar.lVal )
    {
      while ( 1 )
      {
        do
        {
          if ( !(unsigned int)_o__wcsicmp(pvar.pRecInfo[v18].lpVtbl, *(_QWORD *)&v52[4 * v10 - 2]) )
            *((_DWORD *)this + 45) |= v52[4 * v10];
          ++v10;
        }
        while ( v10 < 6 );
        if ( (unsigned int)++v18 >= pvar.lVal )
          break;
        v10 = 0;
      }
    }
LABEL_62:
    LOWORD(v11) = v39;
    goto LABEL_53;
  }
  if ( v11 == *((_DWORD *)this + 38) )
  {
    memset(&pvar, 0, sizeof(pvar));
    if ( PropVariantChangeType((PROPVARIANT *)&pvar, p_pvar, 2, 0x1Fu) >= 0 && pvar.llVal )
    {
      v19 = -1;
      do
        ++v19;
      while ( *(_WORD *)(pvar.llVal + 2 * v19) );
      std::wstring::_Assign<wchar_t>((char *)this + 184, pvar.llVal, v19);
    }
    goto LABEL_53;
  }
  if ( v11 == *((_DWORD *)this + 25) )
  {
    memset(&pvar, 0, sizeof(pvar));
    if ( *(_WORD *)p_pvar && PropVariantChangeType((PROPVARIANT *)&pvar, p_pvar, 2, 0x13u) >= 0 )
    {
      if ( (pvar.bVal & 3) == 3 )
        *((_DWORD *)this + 64) |= 0x4000000u;
      if ( (pvar.bVal & 2) == 0 )
        *((_DWORD *)this + 64) |= 2u;
    }
    goto LABEL_53;
  }
  if ( v11 != *((_DWORD *)this + 39) )
  {
    if ( v11 == *((_DWORD *)this + 40) )
    {
      memset(&pvar, 0, sizeof(pvar));
      if ( PropVariantChangeType((PROPVARIANT *)&pvar, p_pvar, 2, 0x15u) >= 0 && pvar.llVal )
        *((_DWORD *)this + 64) |= 0x400000u;
    }
    else
    {
      if ( v11 != *((_DWORD *)this + 41) )
        goto LABEL_18;
      memset(&pvar, 0, sizeof(pvar));
      if ( PropVariantChangeType((PROPVARIANT *)&pvar, p_pvar, 2, 0x13u) >= 0 && pvar.lVal < 0 )
        *((_DWORD *)this + 64) |= 0x800000u;
    }
    goto LABEL_53;
  }
  if ( *(_WORD *)p_pvar == 72 )
  {
    v13 = *((unsigned int *)this + 64);
    if ( (*((_BYTE *)p_pvar[1] + 15) & 1) != 0 )
      LODWORD(v13) = v13 | 0x2000;
    else
      v13 = (unsigned int)v13 | 0x4000;
    *((_DWORD *)this + 64) = v13;
  }
LABEL_18:
  if ( *((_DWORD *)this + 21) == (unsigned __int16)v11 )
  {
    if ( !v12 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v13);
    v39 = 0;
    v33 = (BYTE *)p_pvar[2];
    v34 = *((_DWORD *)p_pvar + 2);
    if ( v34 != GetSecurityDescriptorLength(v33) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x26B,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\tripolipi\\inverteddocument.cpp",
        (const char *)0x8007053ALL,
        bIgnoreCase);
    v25 = (*(__int64 (__fastcall **)(_QWORD, BYTE *, LONG *))(**((_QWORD **)this + 5) + 32LL))(
            *((_QWORD *)this + 5),
            v33,
            &v39);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x26E,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\tripolipi\\inverteddocument.cpp",
        (const char *)(unsigned int)v25,
        bIgnoreCase);
    memset(&pvar, 0, sizeof(pvar));
    pvar.vt = 19;
    pvar.lVal = v39;
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, VARIANTARG *, _BYTE *))(**((_QWORD **)this + 8) + 144LL))(
      *((_QWORD *)this + 8),
      *((_QWORD *)this + 34),
      *((unsigned __int16 *)this + 44),
      &pvar,
      v37);
    goto LABEL_25;
  }
  if ( !v12 || (v63 & 0x20000) == 0 )
    goto LABEL_26;
  memset(&pvar, 0, sizeof(pvar));
  if ( (_WORD)v63 == 65 )
  {
LABEL_92:
    v43 = &CSizeSerStream::`vftable';
    LODWORD(cb) = 0;
    CBaseStorageVariant::Marshall((CBaseStorageVariant *)p_pvar, (struct PSerStream *)&v43);
    v23 = (const WCHAR *)WINRT_IMPL_CoTaskMemAlloc((unsigned int)cb);
    v24 = (IRecordInfo *)v23;
    lpString1 = v23;
    if ( !v23 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3D4,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\tripolipi\\proputils.cxx",
        (const char *)0x8007000ELL,
        bIgnoreCase);
    v45 = &CMemSerStream::`vftable';
    v46 = 0;
    v47 = v23;
    v48 = v23;
    v49 = (char *)v23 + (unsigned int)cb;
    CBaseStorageVariant::Marshall((CBaseStorageVariant *)p_pvar, (struct PSerStream *)&v45);
    if ( v46 )
    {
      v47 = 0;
      v46 = 0;
    }
    pvar.vt = 65;
    pvar.lVal = cb;
    pvar.pRecInfo = v24;
    p_pvar = (PROPVARIANT *)&pvar;
    v45 = &CMemSerStream::`vftable';
    goto LABEL_23;
  }
  v14 = v63 & 0xFFF;
  if ( (*(_WORD *)p_pvar & 0xFFF) == (v63 & 0xFFF) || *(_WORD *)p_pvar < 2u )
    goto LABEL_23;
  if ( (int)PropVariantChangeTypeCustom((PROPVARIANT *)&pvar, p_pvar, v63) < 0 )
  {
    if ( (unsigned int)IsSimpleType(*(unsigned __int16 *)p_pvar) )
    {
      v22 = VariantChangeType(&pvar, (const VARIANTARG *)p_pvar, 0, v14);
      p_pvar = (PROPVARIANT *)&pvar;
      if ( v22 < 0 )
        p_pvar = 0;
      if ( !p_pvar )
        goto LABEL_24;
      goto LABEL_23;
    }
    if ( (unsigned int)IsSimpleType(v29 & 0xFFFFEFFF) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v30);
    goto LABEL_92;
  }
  p_pvar = (PROPVARIANT *)&pvar;
LABEL_23:
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, PROPVARIANT *, _BYTE *))(**((_QWORD **)this + 8) + 144LL))(
    *((_QWORD *)this + 8),
    *((_QWORD *)this + 34),
    (unsigned __int16)v11,
    p_pvar,
    v37);
LABEL_24:
  PropVariantClear((PROPVARIANT *)&pvar);
LABEL_25:
  v12 = v36;
LABEL_26:
  if ( !v37[0] )
    return v40;
  v9 = v50;
  v7 = v42;
LABEL_28:
  if ( v12 )
  {
    if ( (v63 & 0x10000) == 0 )
      return v40;
  }
  else if ( !a5
         || (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 8LL))(*((_QWORD *)this + 8)) + 8)
           & 4) == 0 )
  {
    return v40;
  }
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 152LL))(
    *((_QWORD *)this + 8),
    *((_QWORD *)this + 34),
    (unsigned __int16)v11);
  v16 = *((_QWORD *)this + 40);
  v17 = (v16 - *((_QWORD *)this + 39)) >> 2;
  if ( (unsigned __int16)v11 >= v17 )
  {
    v39 = 0;
    std::vector<unsigned long>::insert((char *)this + 312, &v42, v16, (unsigned __int16)v11 - v17 + 1, &v39);
  }
  *((_DWORD *)this + 84) = 0;
  *((_DWORD *)this + 85) = -1;
  *((_WORD *)this + 152) = v11;
  *((_QWORD *)this + 37) = v7;
  CInvertedStoreDocument::_ValidateLocale(this);
  *v9 = (struct IWordSink *)((char *)this + 8);
  (*(void (__fastcall **)(CInvertedStoreDocument *))(*(_QWORD *)this + 8LL))(this);
  return v40;
}

```

## disassembly

```asm
0x180055c10  mov     r11, rsp
0x180055c13  push    rbx
0x180055c14  push    rsi
0x180055c15  push    rdi
0x180055c16  push    r12
0x180055c18  push    r13
0x180055c1a  push    r14
0x180055c1c  push    r15
0x180055c1e  sub     rsp, 130h
0x180055c25  mov     rax, cs:__security_cookie
0x180055c2c  xor     rax, rsp
0x180055c2f  mov     [rsp+168h+var_48], rax
0x180055c37  mov     r14, r9
0x180055c3a  mov     rsi, rdx
0x180055c3d  mov     [rsp+168h+var_108], rdx
0x180055c42  mov     rdi, rcx
0x180055c45  mov     rbx, [rsp+168h+arg_28]
0x180055c4d  mov     [rsp+168h+var_C8], rbx
0x180055c55  xor     r15d, r15d
0x180055c58  mov     [rbx], r15
0x180055c5b  mov     [rsp+168h+var_114], r15d
0x180055c60  mov     r12d, 4000h
0x180055c66  cmp     [r8+18h], r12d
0x180055c6a  jnb     loc_1800564F7
0x180055c70  xor     eax, eax
0x180055c72  mov     [r11-58h], rax
0x180055c76  mov     [r11-50h], eax
0x180055c7a  movzx   r13d, word ptr [r8+18h]
0x180055c7f  mov     word ptr [rsp+168h+var_118], r13w
0x180055c85  mov     rcx, [rcx+40h]
0x180055c89  mov     rax, [rcx]
0x180055c8c  lea     r8, [r11-58h]
0x180055c90  movzx   edx, r13w
0x180055c94  mov     rax, [rax+40h]
0x180055c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c9d  mov     dl, al
0x180055c9f  mov     [rsp+168h+var_138], al
0x180055ca3  mov     [rsp+168h+var_137], 1
0x180055ca8  test    r14, r14
0x180055cab  jz      loc_180055E36
0x180055cb1  mov     ecx, r13d
0x180055cb4  cmp     r13d, [rdi+5Ch]
0x180055cb8  jz      loc_180056226
0x180055cbe  cmp     ecx, [rdi+60h]
0x180055cc1  jz      loc_180055F67
0x180055cc7  cmp     ecx, [rdi+90h]
0x180055ccd  jz      loc_180056516
0x180055cd3  cmp     ecx, [rdi+88h]
0x180055cd9  jz      loc_180056299
0x180055cdf  cmp     ecx, [rdi+8Ch]
0x180055ce5  jz      loc_18005655C
0x180055ceb  cmp     ecx, [rdi+74h]
0x180055cee  jz      loc_1802B7C93
0x180055cf4  cmp     ecx, [rdi+78h]
0x180055cf7  jz      loc_18005616F
0x180055cfd  cmp     r13d, [rdi+6Ch]
0x180055d01  jz      loc_1800562E1
0x180055d07  cmp     r13d, [rdi+70h]
0x180055d0b  jz      loc_1800565E0
0x180055d11  cmp     r13d, [rdi+94h]
0x180055d18  jz      loc_180055FB2
0x180055d1e  cmp     r13d, [rdi+98h]
0x180055d25  jz      loc_18005608E
0x180055d2b  cmp     r13d, [rdi+64h]
0x180055d2f  jz      loc_180055F13
0x180055d35  cmp     r13d, [rdi+9Ch]
0x180055d3c  jz      loc_180056269
0x180055d42  cmp     r13d, [rdi+0A0h]
0x180055d49  jz      loc_18005662B
0x180055d4f  cmp     r13d, [rdi+0A4h]
0x180055d56  jz      loc_180056672
0x180055d5c  mov     ebx, 2
0x180055d61  mov     esi, 13h
0x180055d66  movzx   eax, r13w
0x180055d6a  cmp     [rdi+54h], eax
0x180055d6d  jz      loc_1800566BB
0x180055d73  xor     r15d, r15d
0x180055d76  test    dl, dl
0x180055d78  jz      loc_180055E04
0x180055d7e  test    [rsp+168h+var_56], bl
0x180055d85  jz      short loc_180055E04
0x180055d87  xorps   xmm0, xmm0
0x180055d8a  xor     eax, eax
0x180055d8c  movups  xmmword ptr [rsp+168h+pvar], xmm0
0x180055d91  mov     [rsp+168h+var_120], rax
0x180055d96  movzx   r8d, [rsp+168h+var_58]; unsigned __int16
0x180055d9f  lea     r12d, [r15+41h]
0x180055da3  cmp     r8w, r12w
0x180055da7  jz      loc_180056381
0x180055dad  mov     ecx, 0FFFh
0x180055db2  movzx   esi, r8w
0x180055db6  and     si, cx
0x180055db9  movzx   eax, word ptr [r14]
0x180055dbd  and     ax, cx
0x180055dc0  cmp     ax, si
0x180055dc3  jnz     loc_1800560F5
0x180055dc9  mov     rcx, [rdi+40h]
0x180055dcd  mov     rax, [rcx]
0x180055dd0  lea     rdx, [rsp+168h+var_137]
0x180055dd5  mov     qword ptr [rsp+168h+bIgnoreCase], rdx
0x180055dda  mov     r9, r14
0x180055ddd  movzx   r8d, r13w
0x180055de1  mov     rdx, [rdi+110h]
0x180055de8  mov     rax, [rax+90h]
0x180055def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055df4  nop
0x180055df5  lea     rcx, [rsp+168h+pvar]; pvar
0x180055dfa  call    cs:__imp_PropVariantClear
0x180055e00  mov     dl, [rsp+168h+var_138]
0x180055e04  cmp     [rsp+168h+var_137], r15b
0x180055e09  jnz     loc_18005670D
0x180055e0f  mov     eax, [rsp+168h+var_114]
0x180055e13  mov     rcx, [rsp+168h+var_48]
0x180055e1b  xor     rcx, rsp; StackCookie
0x180055e1e  call    __security_check_cookie
0x180055e23  add     rsp, 130h
0x180055e2a  pop     r15
0x180055e2c  pop     r14
0x180055e2e  pop     r13
0x180055e30  pop     r12
0x180055e32  pop     rdi
0x180055e33  pop     rsi
0x180055e34  pop     rbx
0x180055e35  retn
0x180055e36  test    dl, dl
0x180055e38  jz      loc_180055EE6
0x180055e3e  test    [rsp+168h+var_56], 1
0x180055e46  jz      short loc_180055E0F
0x180055e48  mov     rcx, [rdi+40h]
0x180055e4c  mov     rax, [rcx]
0x180055e4f  movzx   r8d, r13w
0x180055e53  mov     rdx, [rdi+110h]
0x180055e5a  mov     rax, [rax+98h]
0x180055e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055e66  lea     rcx, [rdi+138h]
0x180055e6d  mov     r8, [rcx+8]
0x180055e71  mov     rax, r8
0x180055e74  sub     rax, [rcx]
0x180055e77  sar     rax, 2
0x180055e7b  movzx   r9d, r13w
0x180055e7f  cmp     r9, rax
0x180055e82  jb      short loc_180055EA3
0x180055e84  mov     [rsp+168h+var_118], r15d
0x180055e89  sub     r9, rax
0x180055e8c  inc     r9
0x180055e8f  lea     rax, [rsp+168h+var_118]
0x180055e94  mov     qword ptr [rsp+168h+bIgnoreCase], rax
0x180055e99  lea     rdx, [rsp+168h+var_108]
0x180055e9e  call    ?insert@?$vector@KV?$allocator@K@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@K@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@K@std@@@std@@@2@_KAEBK@Z; std::vector<ulong>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ulong>>>,unsigned __int64,ulong const &)
0x180055ea3  mov     [rdi+150h], r15d
0x180055eaa  mov     dword ptr [rdi+154h], 0FFFFFFFFh
0x180055eb4  mov     [rdi+130h], r13w
0x180055ebc  mov     [rdi+128h], rsi
0x180055ec3  mov     rcx, rdi; this
0x180055ec6  call    ?_ValidateLocale@CInvertedStoreDocument@@AEAAXXZ; CInvertedStoreDocument::_ValidateLocale(void)
0x180055ecb  lea     rax, [rdi+8]
0x180055ecf  mov     [rbx], rax
0x180055ed2  mov     rax, [rdi]
0x180055ed5  mov     rcx, rdi
0x180055ed8  mov     rax, [rax+8]
0x180055edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055ee1  jmp     loc_180055E0F
0x180055ee6  cmp     [rsp+168h+arg_20], r15
0x180055eee  jz      loc_180055E0F
0x180055ef4  mov     rcx, [rdi+40h]
0x180055ef8  mov     rax, [rcx]
0x180055efb  mov     rax, [rax+8]
0x180055eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f04  test    byte ptr [rax+8], 4
0x180055f08  jnz     loc_180055E48
0x180055f0e  jmp     loc_180055E0F
0x180055f13  xorps   xmm0, xmm0
0x180055f16  xor     eax, eax
0x180055f18  movups  xmmword ptr [rsp+168h+pvar], xmm0
0x180055f1d  mov     [rsp+168h+var_120], rax
0x180055f22  lea     esi, [rax+13h]
0x180055f25  lea     ebx, [rax+2]
0x180055f28  cmp     [r14], r15w
0x180055f2c  jz      short loc_180055F9E
0x180055f2e  mov     r9d, esi; vt
0x180055f31  mov     r8d, ebx; flags
0x180055f34  mov     rdx, r14; propvarSrc
0x180055f37  lea     rcx, [rsp+168h+pvar]; ppropvarDest
0x180055f3c  call    cs:__imp_PropVariantChangeType
0x180055f42  test    eax, eax
0x180055f44  js      short loc_180055F9E
0x180055f46  mov     eax, dword ptr [rsp+168h+pvar+8]
0x180055f4a  and     eax, 3
0x180055f4d  cmp     al, 3
0x180055f4f  jnz     short loc_180055F59
0x180055f51  bts     dword ptr [rdi+100h], 1Ah
0x180055f59  test    byte ptr [rsp+168h+pvar+8], bl
0x180055f5d  jnz     short loc_180055F9E
0x180055f5f  or      [rdi+100h], ebx
0x180055f65  jmp     short loc_180055F9E
0x180055f67  xorps   xmm0, xmm0
0x180055f6a  xor     eax, eax
0x180055f6c  movups  xmmword ptr [rsp+168h+pvar], xmm0
0x180055f71  mov     [rsp+168h+var_120], rax
0x180055f76  lea     esi, [rax+13h]
0x180055f79  mov     r9d, esi; vt
0x180055f7c  lea     ebx, [rax+2]
0x180055f7f  mov     r8d, ebx; flags
0x180055f82  mov     rdx, r14; propvarSrc
0x180055f85  lea     rcx, [rsp+168h+pvar]; ppropvarDest
0x180055f8a  call    cs:__imp_PropVariantChangeType
0x180055f90  test    eax, eax
0x180055f92  js      short loc_180055F9E
0x180055f94  mov     eax, dword ptr [rsp+168h+pvar+8]
0x180055f98  mov     [rdi+0D8h], eax
0x180055f9e  lea     rcx, [rsp+168h+pvar]; pvar
0x180055fa3  call    cs:__imp_PropVariantClear
0x180055fa9  mov     dl, [rsp+168h+var_138]
0x180055fad  jmp     loc_180055D66
0x180055fb2  xorps   xmm0, xmm0
0x180055fb5  xor     eax, eax
0x180055fb7  movups  xmmword ptr [rsp+168h+pvar], xmm0
0x180055fbc  mov     [rsp+168h+var_120], rax
0x180055fc1  lea     ebx, [rax+2]
0x180055fc4  mov     r9d, 101Fh; vt
0x180055fca  mov     r8d, ebx; flags
0x180055fcd  mov     rdx, r14; propvarSrc
0x180055fd0  lea     rcx, [rsp+168h+pvar]; ppropvarDest
0x180055fd5  call    cs:__imp_PropVariantChangeType
0x180055fdb  test    eax, eax
0x180055fdd  js      loc_1800560E1
0x180055fe3  lea     rax, aPicture; "picture"
0x180055fea  mov     [rsp+168h+var_B8], rax
0x180055ff2  mov     [rsp+168h+var_B0], 1
0x180055ffd  lea     rax, aMusic; "music"
0x180056004  mov     [rsp+168h+var_A8], rax
0x18005600c  mov     [rsp+168h+var_A0], ebx
0x180056013  lea     rax, aVideo; "video"
0x18005601a  mov     [rsp+168h+var_98], rax
0x180056022  mov     [rsp+168h+var_90], 4
0x18005602d  lea     rax, aMovie; "movie"
0x180056034  mov     [rsp+168h+var_88], rax
0x18005603c  mov     [rsp+168h+var_80], 8
0x180056047  lea     rax, aRecordedtv; "recordedtv"
0x18005604e  mov     [rsp+168h+var_78], rax
0x180056056  mov     [rsp+168h+var_70], 10h
0x180056061  lea     r13, aDocument; "document"
0x180056068  mov     [rsp+168h+var_68], r13
0x180056070  mov     [rsp+168h+var_60], 20h ; ' '
0x18005607b  mov     esi, r15d
0x18005607e  cmp     dword ptr [rsp+168h+pvar+8], r15d
0x180056083  jbe     loc_180056164
0x180056089  jmp     loc_180056121
0x18005608e  xorps   xmm0, xmm0
0x180056091  xor     eax, eax
0x180056093  movups  xmmword ptr [rsp+168h+pvar], xmm0
0x180056098  mov     [rsp+168h+var_120], rax
0x18005609d  lea     ebx, [rax+2]
0x1800560a0  lea     r9d, [rax+1Fh]; vt
0x1800560a4  mov     r8d, ebx; flags
0x1800560a7  mov     rdx, r14; propvarSrc
0x1800560aa  lea     rcx, [rsp+168h+pvar]; ppropvarDest
0x1800560af  call    cs:__imp_PropVariantChangeType
0x1800560b5  test    eax, eax
0x1800560b7  js      short loc_1800560E1
0x1800560b9  mov     rdx, [rsp+168h+pvar+8]
0x1800560be  test    rdx, rdx
0x1800560c1  jz      short loc_1800560E1
0x1800560c3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800560c7  inc     rsi
0x1800560ca  cmp     [rdx+rsi*2], r15w
0x1800560cf  jnz     short loc_1800560C7
0x1800560d1  lea     rcx, [rdi+0B8h]
0x1800560d8  mov     r8, rsi
0x1800560db  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800560e0  nop
0x1800560e1  lea     rcx, [rsp+168h+pvar]; pvar
0x1800560e6  call    cs:__imp_PropVariantClear
0x1800560ec  mov     dl, [rsp+168h+var_138]
0x1800560f0  jmp     loc_180055D61
0x1800560f5  cmp     [r14], bx
0x1800560f9  jb      loc_180055DC9
0x1800560ff  mov     rdx, r14; pvarSrc
0x180056102  lea     rcx, [rsp+168h+pvar]; pvarDest
0x180056107  call    ?PropVariantChangeTypeCustom@@YAJPEAUtagPROPVARIANT@@AEBU1@G@Z; PropVariantChangeTypeCustom(tagPROPVARIANT *,tagPROPVARIANT const &,ushort)
0x18005610c  test    eax, eax
0x18005610e  js      loc_1800566D0
0x180056114  lea     r14, [rsp+168h+pvar]
0x180056119  jmp     loc_180055DC9
0x18005611e  xor     r15d, r15d
0x180056121  mov     r13d, esi
0x180056124  movsxd  r12, r15d
0x180056127  add     r12, r12
0x18005612a  mov     rdx, [rsp+r12*8+168h+var_B8]
0x180056132  mov     rcx, [rsp+168h+var_120]
0x180056137  mov     rcx, [rcx+r13*8]
0x18005613b  call    cs:__imp__o__wcsicmp
0x180056141  test    eax, eax
0x180056143  jnz     short loc_180056153
0x180056145  mov     eax, [rsp+r12*8+168h+var_B0]
0x18005614d  or      [rdi+0B4h], eax
0x180056153  inc     r15d
0x180056156  cmp     r15d, 6
0x18005615a  jb      short loc_180056124
0x18005615c  inc     esi
  ... truncated ...
```
