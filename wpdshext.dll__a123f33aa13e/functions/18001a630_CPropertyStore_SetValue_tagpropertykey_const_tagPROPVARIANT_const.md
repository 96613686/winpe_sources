# CPropertyStore::SetValue(_tagpropertykey const &,tagPROPVARIANT const &)

- ea: `0x18001a630`
- end: `0x18001b0a8`
- name: `?SetValue@CPropertyStore@@UEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z`
- size: `2680`
- prototype: `__int64 __fastcall(CPropertyStore *__hidden this, const struct _tagpropertykey *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18001a630`
- `0x18001b0b0`
- `0x18001bb80`
- `0x18001f680`
- `0x180022c04`
- `0x18002e0d8`
- `0x18002ff5c`
- `0x180035590`
- `0x18007559c`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001adbb`
- `KERNEL32!GetLastError` at `0x18001aeaa`
- `KERNEL32!GetLastError` at `0x18001b012`
- `KERNEL32!GetLastError` at `0x18001adbb`
- `KERNEL32!GetLastError` at `0x18001aeaa`
- `KERNEL32!GetLastError` at `0x18001b012`
- `KERNEL32!HeapAlloc` at `0x18001a6f4`
- `KERNEL32!HeapAlloc` at `0x18001a8b8`
- `KERNEL32!HeapAlloc` at `0x18001a9e9`
- `KERNEL32!HeapAlloc` at `0x18001a6f4`
- `KERNEL32!HeapAlloc` at `0x18001a8b8`
- `KERNEL32!HeapAlloc` at `0x18001a9e9`
- `KERNEL32!GetProcessHeap` at `0x18001a6e0`
- `KERNEL32!GetProcessHeap` at `0x18001a8a4`
- `KERNEL32!GetProcessHeap` at `0x18001a9d5`
- `KERNEL32!GetProcessHeap` at `0x18001a6e0`
- `KERNEL32!GetProcessHeap` at `0x18001a8a4`
- `KERNEL32!GetProcessHeap` at `0x18001a9d5`
- `KERNEL32!DeactivateActCtx` at `0x18001adc9`
- `KERNEL32!DeactivateActCtx` at `0x18001adf3`
- `KERNEL32!DeactivateActCtx` at `0x18001aeb8`
- `KERNEL32!DeactivateActCtx` at `0x18001aee9`
- `KERNEL32!DeactivateActCtx` at `0x18001b020`
- `KERNEL32!DeactivateActCtx` at `0x18001b083`
- `KERNEL32!DeactivateActCtx` at `0x18001adc9`
- `KERNEL32!DeactivateActCtx` at `0x18001adf3`
- `KERNEL32!DeactivateActCtx` at `0x18001aeb8`
- `KERNEL32!DeactivateActCtx` at `0x18001aee9`
- `KERNEL32!DeactivateActCtx` at `0x18001b020`
- `KERNEL32!DeactivateActCtx` at `0x18001b083`
- `KERNEL32!SetLastError` at `0x18001add1`
- `KERNEL32!SetLastError` at `0x18001aec0`
- `KERNEL32!SetLastError` at `0x18001b028`
- `KERNEL32!SetLastError` at `0x18001add1`
- `KERNEL32!SetLastError` at `0x18001aec0`
- `KERNEL32!SetLastError` at `0x18001b028`
- `ole32!PropVariantCopy` at `0x18001a72a`
- `ole32!PropVariantCopy` at `0x18001a8ea`
- `ole32!PropVariantCopy` at `0x18001aa1c`
- `ole32!PropVariantCopy` at `0x18001a72a`
- `ole32!PropVariantCopy` at `0x18001a8ea`
- `ole32!PropVariantCopy` at `0x18001aa1c`
- `ole32!PropVariantClear` at `0x18001a7d5`
- `ole32!PropVariantClear` at `0x18001a7df`
- `ole32!PropVariantClear` at `0x18001a822`
- `ole32!PropVariantClear` at `0x18001a82c`
- `ole32!PropVariantClear` at `0x18001a932`
- `ole32!PropVariantClear` at `0x18001aa68`
- `ole32!PropVariantClear` at `0x18001ac92`
- `ole32!PropVariantClear` at `0x18001ad3b`
- `ole32!PropVariantClear` at `0x18001ad45`
- `ole32!PropVariantClear` at `0x18001af8f`
- `ole32!PropVariantClear` at `0x18001a7d5`
- `ole32!PropVariantClear` at `0x18001a7df`
- `ole32!PropVariantClear` at `0x18001a822`
- `ole32!PropVariantClear` at `0x18001a82c`
- `ole32!PropVariantClear` at `0x18001a932`
- `ole32!PropVariantClear` at `0x18001aa68`
- `ole32!PropVariantClear` at `0x18001ac92`
- `ole32!PropVariantClear` at `0x18001ad3b`
- `ole32!PropVariantClear` at `0x18001ad45`
- `ole32!PropVariantClear` at `0x18001af8f`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18001af17`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18001af17`

## pseudocode

```c
__int64 __fastcall CPropertyStore::SetValue(
        CPropertyStore *this,
        const struct _tagpropertykey *a2,
        const struct tagPROPVARIANT *a3)
{
  bool v3; // zf
  int vt; // ecx
  unsigned __int64 v8; // rdx
  DWORD pid; // eax
  unsigned int v10; // edi
  HANDLE ProcessHeap; // rax
  PROPVARIANT *v12; // rax
  PROPERTY_ITEM *v13; // r13
  HRESULT v14; // eax
  unsigned int v15; // edx
  unsigned int v16; // r12d
  unsigned int (__fastcall *v17)(__int64, __int64, PROPERTY_ITEM *); // rbx
  __int64 v18; // rax
  int v19; // ebx
  DWORD v20; // eax
  __int64 v22; // rax
  DWORD v23; // ebx
  HANDLE v24; // rax
  PROPVARIANT *v25; // rax
  PROPERTY_ITEM *v26; // r14
  GUID fmtid; // xmm0
  HRESULT v28; // eax
  unsigned int v29; // edx
  unsigned int v30; // r12d
  unsigned int (__fastcall *v31)(__int64, __int64, PROPERTY_ITEM *); // rbx
  __int64 v32; // rsi
  __int64 v33; // rax
  struct _SYSTEMTIME *QuadPart; // rax
  HANDLE v35; // rax
  PROPVARIANT *v36; // rax
  PROPERTY_ITEM *v37; // r13
  HRESULT v38; // eax
  unsigned int v39; // edx
  unsigned int (__fastcall *v40)(__int64, __int64, PROPERTY_ITEM *); // rbx
  __int64 v41; // rax
  PROPVARIANT *p_pvar; // rcx
  __int64 v43; // rax
  LONG v44; // ebx
  __int64 v45; // rax
  unsigned __int64 v46; // rax
  _QWORD *v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // rax
  DWORD LastError; // ebx
  __int64 v51; // rax
  DWORD v52; // ebx
  int v53; // eax
  __int64 v54; // r9
  __int64 v55; // rax
  DWORD v56; // ebx
  ULONG_PTR ulCookie; // [rsp+30h] [rbp-59h] BYREF
  PROPVARIANT pvar; // [rsp+38h] [rbp-51h] BYREF
  struct _tagpropertykey v59; // [rsp+50h] [rbp-39h] BYREF
  PROPVARIANT v60; // [rsp+68h] [rbp-21h] BYREF
  struct _SYSTEMTIME Buf2; // [rsp+80h] [rbp-9h] BYREF

  v3 = *((_DWORD *)this + 20) == 1;
  memset(&v59, 0, sizeof(v59));
  memset(&pvar, 0, sizeof(pvar));
  memset(&v60, 0, sizeof(v60));
  if ( v3 )
  {
    PropVariantClear(&pvar);
    PropVariantClear(&v60);
    v10 = -2147467263;
LABEL_20:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids, v10);
    return v10;
  }
  vt = a3->vt;
  if ( (unsigned __int16)(vt - 1) > 0x3Fu
    || (v8 = 0x80000030417F96FFuLL, !_bittest64((const __int64 *)&v8, (unsigned int)(vt - 1))) )
  {
    if ( (_WORD)vt != 72 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids, 0);
      PropVariantClear(&pvar);
      PropVariantClear(&v60);
      return 0;
    }
  }
  pid = a2->pid;
  v10 = 0;
  if ( pid != 3 )
  {
    if ( pid == 2 )
    {
      v22 = *(_QWORD *)&PKEY_FreeSpace.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
      if ( *(_QWORD *)&PKEY_FreeSpace.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
        v22 = *(_QWORD *)PKEY_FreeSpace.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
      if ( !v22 )
        goto LABEL_50;
    }
LABEL_6:
    ProcessHeap = GetProcessHeap();
    v12 = (PROPVARIANT *)HeapAlloc(ProcessHeap, 8u, 0x30u);
    v13 = (PROPERTY_ITEM *)v12;
    if ( !v12 )
    {
      v19 = -2147024882;
      v16 = -2147024882;
LABEL_53:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids, v16);
      goto LABEL_15;
    }
    *(_OWORD *)&v12[1].vt = 0;
    v12[1].bstrblobVal.pData = 0;
    *(GUID *)&v12->vt = a2->fmtid;
    *((_DWORD *)&v12->decVal + 4) = a2->pid;
    v14 = PropVariantCopy(v12 + 1, a3);
    v16 = v14;
    if ( v14 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids,
          (unsigned int)v14);
      goto LABEL_102;
    }
    v17 = (unsigned int (__fastcall *)(__int64, __int64, PROPERTY_ITEM *))`IsolationAwareDPA_InsertPtr'::`2'::s_pfn;
    v18 = *((_QWORD *)this + 14);
    *(_QWORD *)&Buf2.wYear = v18;
    if ( `IsolationAwareDPA_InsertPtr'::`2'::s_pfn )
      goto LABEL_9;
    ulCookie = 0;
    if ( IsolationAwarePrivateT_SAbnPgpgk
      || IsolationAwarePrivateT_SqbjaYRiRY
      || (unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
    {
      v49 = Dpa_dsaIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("DPA_InsertPtr");
      v17 = (unsigned int (__fastcall *)(__int64, __int64, PROPERTY_ITEM *))v49;
      if ( IsolationAwarePrivateT_SqbjaYRiRY )
      {
        if ( !v49 )
          goto LABEL_101;
      }
      else
      {
        if ( !v49 )
        {
          LastError = GetLastError();
          DeactivateActCtx(0, ulCookie);
          SetLastError(LastError);
          goto LABEL_101;
        }
        DeactivateActCtx(0, ulCookie);
      }
      v18 = *(_QWORD *)&Buf2.wYear;
      `IsolationAwareDPA_InsertPtr'::`2'::s_pfn = (__int64)v17;
LABEL_9:
      if ( v17(v18, 0x7FFFFFFF, v13) != -1 )
      {
        v19 = v16;
        goto LABEL_11;
      }
    }
LABEL_101:
    v16 = -2147467259;
LABEL_102:
    PROPERTY_ITEM::`scalar deleting destructor'(v13, v15);
    v19 = v16;
    goto LABEL_53;
  }
  v43 = *(_QWORD *)&PKEY_Capacity.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
  if ( *(_QWORD *)&PKEY_Capacity.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
    v43 = *(_QWORD *)PKEY_Capacity.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
  if ( v43 )
    goto LABEL_6;
LABEL_50:
  if ( a3->hVal.QuadPart != -1 )
    goto LABEL_6;
  v19 = 1;
LABEL_11:
  if ( !*((_DWORD *)this + 21) )
    goto LABEL_15;
  v20 = a2->pid;
  if ( v20 == 7 )
  {
    v33 = *(_QWORD *)&WPD_OBJECT_CONTENT_TYPE.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
    if ( *(_QWORD *)&WPD_OBJECT_CONTENT_TYPE.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
      v33 = *(_QWORD *)WPD_OBJECT_CONTENT_TYPE.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
    if ( v33 || a3->vt != 72 )
    {
LABEL_14:
      if ( (unsigned int)CPropertyStore::_ConvertToPKEY(this, a2, a3, &v59, &pvar) )
        goto LABEL_15;
      v23 = v59.pid;
      if ( v59.pid == 3 )
      {
        if ( memcmp_0(&PKEY_Capacity, &v59, 0x10u) )
          goto LABEL_29;
      }
      else if ( v59.pid != 2 || memcmp_0(&PKEY_FreeSpace, &v59, 0x10u) )
      {
        goto LABEL_29;
      }
      if ( pvar.hVal.QuadPart == -1 )
      {
        v19 = 1;
        PropVariantClear(&pvar);
        goto LABEL_15;
      }
LABEL_29:
      v24 = GetProcessHeap();
      v25 = (PROPVARIANT *)HeapAlloc(v24, 8u, 0x30u);
      v26 = (PROPERTY_ITEM *)v25;
      if ( !v25 )
      {
        v19 = -2147024882;
        v30 = -2147024882;
        goto LABEL_139;
      }
      *(_OWORD *)&v25[1].vt = 0;
      fmtid = v59.fmtid;
      v25[1].bstrblobVal.pData = 0;
      *(GUID *)&v25->vt = fmtid;
      *((_DWORD *)&v25->decVal + 4) = v23;
      v28 = PropVariantCopy(v25 + 1, &pvar);
      v30 = v28;
      if ( v28 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            46,
            WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids,
            (unsigned int)v28);
        goto LABEL_138;
      }
      v31 = (unsigned int (__fastcall *)(__int64, __int64, PROPERTY_ITEM *))`IsolationAwareDPA_InsertPtr'::`2'::s_pfn;
      v32 = *((_QWORD *)this + 14);
      if ( `IsolationAwareDPA_InsertPtr'::`2'::s_pfn )
        goto LABEL_32;
      ulCookie = 0;
      if ( IsolationAwarePrivateT_SAbnPgpgk
        || IsolationAwarePrivateT_SqbjaYRiRY
        || (unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
      {
        v55 = Dpa_dsaIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("DPA_InsertPtr");
        v31 = (unsigned int (__fastcall *)(__int64, __int64, PROPERTY_ITEM *))v55;
        if ( IsolationAwarePrivateT_SqbjaYRiRY )
        {
          if ( !v55 )
            goto LABEL_137;
        }
        else
        {
          if ( !v55 )
          {
            v56 = GetLastError();
            DeactivateActCtx(0, ulCookie);
            SetLastError(v56);
            goto LABEL_137;
          }
          DeactivateActCtx(0, ulCookie);
        }
        `IsolationAwareDPA_InsertPtr'::`2'::s_pfn = (__int64)v31;
LABEL_32:
        if ( v31(v32, 0x7FFFFFFF, v26) != -1 )
        {
          v19 = v30;
          PropVariantClear(&pvar);
          goto LABEL_15;
        }
      }
LABEL_137:
      v30 = -2147467259;
LABEL_138:
      PROPERTY_ITEM::`scalar deleting destructor'(v26, v29);
      v19 = v30;
LABEL_139:
      v47 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_15;
      v48 = 28;
      goto LABEL_142;
    }
    v59.pid = 9;
    pvar.vt = 19;
    QuadPart = (struct _SYSTEMTIME *)a3->hVal.QuadPart;
    v59.fmtid = PKEY_PerceivedType.fmtid;
    Buf2 = *QuadPart;
    if ( !memcmp_0(&WPD_CONTENT_TYPE_UNSPECIFIED, &Buf2, 0x10u) )
    {
      pvar.lVal = -2;
    }
    else if ( !memcmp_0(&WPD_CONTENT_TYPE_FOLDER, &Buf2, 0x10u)
           || !memcmp_0(&WPD_CONTENT_TYPE_FUNCTIONAL_OBJECT, &Buf2, 0x10u) )
    {
      pvar.lVal = -1;
    }
    else if ( !memcmp_0(&WPD_CONTENT_TYPE_IMAGE, &Buf2, 0x10u) )
    {
      pvar.lVal = 2;
    }
    else if ( !memcmp_0(&WPD_CONTENT_TYPE_AUDIO, &Buf2, 0x10u) )
    {
      pvar.lVal = 3;
    }
    else if ( !memcmp_0(&WPD_CONTENT_TYPE_VIDEO, &Buf2, 0x10u) )
    {
      pvar.lVal = 4;
    }
    else if ( !memcmp_0(&WPD_CONTENT_TYPE_DOCUMENT, &Buf2, 0x10u) )
    {
      pvar.lVal = 6;
    }
    else
    {
      v44 = 0;
      if ( !memcmp_0(&WPD_CONTENT_TYPE_CONTACT, &Buf2, 0x10u) )
        v44 = 10;
      pvar.lVal = v44;
    }
    v35 = GetProcessHeap();
    v36 = (PROPVARIANT *)HeapAlloc(v35, 8u, 0x30u);
    v37 = (PROPERTY_ITEM *)v36;
    if ( !v36 )
    {
      v19 = -2147024882;
      v30 = -2147024882;
      goto LABEL_83;
    }
    *(_OWORD *)&v36[1].vt = 0;
    v36[1].bstrblobVal.pData = 0;
    *(GUID *)&v36->vt = PKEY_PerceivedType.fmtid;
    *((_DWORD *)&v36->decVal + 4) = 9;
    v38 = PropVariantCopy(v36 + 1, &pvar);
    v30 = v38;
    if ( v38 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids,
          (unsigned int)v38);
      goto LABEL_118;
    }
    v40 = (unsigned int (__fastcall *)(__int64, __int64, PROPERTY_ITEM *))`IsolationAwareDPA_InsertPtr'::`2'::s_pfn;
    v41 = *((_QWORD *)this + 14);
    *(_QWORD *)&Buf2.wYear = v41;
    if ( `IsolationAwareDPA_InsertPtr'::`2'::s_pfn )
      goto LABEL_44;
    ulCookie = 0;
    if ( IsolationAwarePrivateT_SAbnPgpgk
      || IsolationAwarePrivateT_SqbjaYRiRY
      || (unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
    {
      v51 = Dpa_dsaIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("DPA_InsertPtr");
      v40 = (unsigned int (__fastcall *)(__int64, __int64, PROPERTY_ITEM *))v51;
      if ( IsolationAwarePrivateT_SqbjaYRiRY )
      {
        if ( !v51 )
          goto LABEL_117;
      }
      else
      {
        if ( !v51 )
        {
          v52 = GetLastError();
          DeactivateActCtx(0, ulCookie);
          SetLastError(v52);
          goto LABEL_117;
        }
        DeactivateActCtx(0, ulCookie);
      }
      v41 = *(_QWORD *)&Buf2.wYear;
      `IsolationAwareDPA_InsertPtr'::`2'::s_pfn = (__int64)v40;
LABEL_44:
      if ( v40(v41, 0x7FFFFFFF, v37) != -1 )
      {
        v19 = v30;
        p_pvar = &pvar;
LABEL_46:
        PropVariantClear(p_pvar);
        goto LABEL_14;
      }
    }
LABEL_117:
    v30 = -2147467259;
LABEL_118:
    PROPERTY_ITEM::`scalar deleting destructor'(v37, v39);
    v19 = v30;
LABEL_83:
    v47 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_15;
    v48 = 26;
LABEL_142:
    v54 = v30;
    goto LABEL_143;
  }
  if ( v20 != 14 )
    goto LABEL_14;
  v45 = *(_QWORD *)&WPD_MEDIA_RELEASE_DATE.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
  if ( *(_QWORD *)&WPD_MEDIA_RELEASE_DATE.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
    v45 = *(_QWORD *)WPD_MEDIA_RELEASE_DATE.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
  if ( v45
    || (*(int (__fastcall **)(CPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)this + 40LL))(
         this,
         &WPD_OBJECT_CONTENT_TYPE,
         &v60) < 0 )
  {
    goto LABEL_14;
  }
  if ( v60.vt != 72 )
    goto LABEL_75;
  v46 = *(_QWORD *)&WPD_CONTENT_TYPE_AUDIO.Data1 - (unsigned __int64)*v60.pbstrVal;
  if ( *(BSTR *)&WPD_CONTENT_TYPE_AUDIO.Data1 == *v60.pbstrVal )
    v46 = *(_QWORD *)WPD_CONTENT_TYPE_AUDIO.Data4 - *(_QWORD *)(v60.hVal.QuadPart + 8);
  if ( v46 )
    goto LABEL_75;
  if ( a3->vt != 7 )
    goto LABEL_75;
  Buf2 = 0;
  if ( !VariantTimeToSystemTime(a3->dblVal, &Buf2) )
    goto LABEL_75;
  v59.pid = 5;
  pvar.vt = 19;
  pvar.lVal = Buf2.wYear;
  v59.fmtid = PKEY_Media_Year.fmtid;
  v53 = CPropertyStore::_AddItem(this, &v59, &pvar);
  v19 = v53;
  if ( v53 >= 0 )
  {
    PropVariantClear(&pvar);
LABEL_75:
    p_pvar = &v60;
    goto LABEL_46;
  }
  v47 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v48 = 27;
    v54 = (unsigned int)v53;
LABEL_143:
    WPP_SF_d(v47[2], v48, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids, v54);
  }
LABEL_15:
  if ( v19 != 1 )
    v10 = v19;
  PropVariantClear(&pvar);
  PropVariantClear(&v60);
  if ( (v10 & 0x80000000) != 0 )
    goto LABEL_20;
  return v10;
}

```

## disassembly

```asm
0x18001a630  push    rbp
0x18001a632  push    rsi
0x18001a633  push    rdi
0x18001a634  push    r14
0x18001a636  push    r15
0x18001a638  lea     rbp, [rsp-37h]
0x18001a63d  sub     rsp, 0C0h
0x18001a644  mov     rax, cs:__security_cookie
0x18001a64b  xor     rax, rsp
0x18001a64e  mov     [rbp+57h+var_50], rax
0x18001a652  xor     eax, eax
0x18001a654  xorps   xmm0, xmm0
0x18001a657  cmp     dword ptr [rcx+50h], 1
0x18001a65b  xorps   xmm1, xmm1
0x18001a65e  mov     r15, r8
0x18001a661  mov     [rbp+57h+var_90.pid], eax
0x18001a664  mov     r14, rdx
0x18001a667  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18001a66b  mov     rsi, rcx
0x18001a66e  mov     qword ptr [rbp+57h+var_78+10h], rax
0x18001a672  movups  xmmword ptr [rbp+57h+var_90.fmtid.Data1], xmm0
0x18001a676  movups  xmmword ptr [rbp+57h+pvar], xmm1
0x18001a67a  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x18001a67e  jz      loc_18001A81E
0x18001a684  movzx   ecx, word ptr [r8]
0x18001a688  lea     eax, [rcx-1]
0x18001a68b  cmp     ax, 3Fh ; '?'
0x18001a68f  ja      loc_18001ACFC
0x18001a695  mov     rdx, 80000030417F96FFh
0x18001a69f  bt      rdx, rax
0x18001a6a3  jnb     loc_18001ACFC
0x18001a6a9  mov     eax, [r14+10h]
0x18001a6ad  xor     edi, edi
0x18001a6af  mov     [rsp+0E0h+arg_18], rbx
0x18001a6b7  lea     rbx, WPP_GLOBAL_Control
0x18001a6be  mov     [rsp+0E0h+var_28], r12
0x18001a6c6  mov     [rsp+0E0h+var_30], r13
0x18001a6ce  cmp     eax, 3
0x18001a6d1  jz      loc_18001AA73
0x18001a6d7  cmp     eax, 2
0x18001a6da  jz      loc_18001A86A
0x18001a6e0  call    cs:__imp_GetProcessHeap
0x18001a6e6  mov     edx, 8; dwFlags
0x18001a6eb  mov     r8d, 30h ; '0'; dwBytes
0x18001a6f1  mov     rcx, rax; hHeap
0x18001a6f4  call    cs:__imp_HeapAlloc
0x18001a6fa  mov     r13, rax
0x18001a6fd  test    rax, rax
0x18001a700  jz      loc_18001AAA8
0x18001a706  lea     rcx, [rax+18h]; pvarDest
0x18001a70a  xorps   xmm0, xmm0
0x18001a70d  movups  xmmword ptr [rcx], xmm0
0x18001a710  xor     eax, eax
0x18001a712  mov     rdx, r15; pvarSrc
0x18001a715  mov     [rcx+10h], rax
0x18001a719  movups  xmm0, xmmword ptr [r14]
0x18001a71d  movups  xmmword ptr [r13+0], xmm0
0x18001a722  mov     eax, [r14+10h]
0x18001a726  mov     [r13+10h], eax
0x18001a72a  call    cs:__imp_PropVariantCopy
0x18001a730  mov     r12d, eax
0x18001a733  test    eax, eax
0x18001a735  js      loc_18001AD52
0x18001a73b  mov     rbx, cs:?s_pfn@?1??IsolationAwareDPA_InsertPtr@@9@4P6AHPEAU_DPA@@HPEAX@ZEA; int (*`IsolationAwareDPA_InsertPtr'::`2'::s_pfn)(_DPA *,int,void *)
0x18001a742  mov     rax, [rsi+70h]
0x18001a746  mov     qword ptr [rbp+57h+Buf2], rax
0x18001a74a  test    rbx, rbx
0x18001a74d  jz      loc_18001AD7E
0x18001a753  mov     rcx, rax
0x18001a756  mov     r8, r13
0x18001a759  mov     rax, rbx
0x18001a75c  mov     edx, 7FFFFFFFh
0x18001a761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a766  cmp     eax, 0FFFFFFFFh
0x18001a769  jz      loc_18001ADD7
0x18001a76f  mov     ebx, r12d
0x18001a772  cmp     [rsi+54h], edi
0x18001a775  jz      loc_18001B09C
0x18001a77b  mov     eax, [r14+10h]
0x18001a77f  movaps  [rsp+0E0h+var_40], xmm6
0x18001a787  cmp     eax, 7
0x18001a78a  jz      loc_18001A93D
0x18001a790  cmp     eax, 0Eh
0x18001a793  jz      loc_18001ABCF
0x18001a799  lea     rax, [rbp+57h+pvar]
0x18001a79d  mov     r8, r15; struct tagPROPVARIANT *
0x18001a7a0  lea     r9, [rbp+57h+var_90]; struct _tagpropertykey *
0x18001a7a4  mov     [rsp+0E0h+var_C0], rax; struct tagPROPVARIANT *
0x18001a7a9  mov     rdx, r14; struct _tagpropertykey *
0x18001a7ac  mov     rcx, rsi; this
0x18001a7af  call    ?_ConvertToPKEY@CPropertyStore@@AEAAJAEBU_tagpropertykey@@PEBUtagPROPVARIANT@@PEAU2@PEAU3@@Z; CPropertyStore::_ConvertToPKEY(_tagpropertykey const &,tagPROPVARIANT const *,_tagpropertykey *,tagPROPVARIANT *)
0x18001a7b4  test    eax, eax
0x18001a7b6  jz      loc_18001A88F
0x18001a7bc  lea     rsi, WPP_GLOBAL_Control
0x18001a7c3  movaps  xmm6, [rsp+0E0h+var_40]
0x18001a7cb  cmp     ebx, 1
0x18001a7ce  lea     rcx, [rbp+57h+pvar]; pvar
0x18001a7d2  cmovnz  edi, ebx
0x18001a7d5  call    cs:__imp_PropVariantClear
0x18001a7db  lea     rcx, [rbp+57h+var_78]; pvar
0x18001a7df  call    cs:__imp_PropVariantClear
0x18001a7e5  mov     r13, [rsp+0E0h+var_30]
0x18001a7ed  mov     r12, [rsp+0E0h+var_28]
0x18001a7f5  mov     rbx, [rsp+0E0h+arg_18]
0x18001a7fd  test    edi, edi
0x18001a7ff  js      short loc_18001A83E
0x18001a801  mov     eax, edi
0x18001a803  mov     rcx, [rbp+57h+var_50]
0x18001a807  xor     rcx, rsp; StackCookie
0x18001a80a  call    __security_check_cookie
0x18001a80f  add     rsp, 0C0h
0x18001a816  pop     r15
0x18001a818  pop     r14
0x18001a81a  pop     rdi
0x18001a81b  pop     rsi
0x18001a81c  pop     rbp
0x18001a81d  retn
0x18001a81e  lea     rcx, [rbp+57h+pvar]; pvar
0x18001a822  call    cs:__imp_PropVariantClear
0x18001a828  lea     rcx, [rbp+57h+var_78]; pvar
0x18001a82c  call    cs:__imp_PropVariantClear
0x18001a832  mov     edi, 80004001h
0x18001a837  lea     rsi, WPP_GLOBAL_Control
0x18001a83e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a845  cmp     rcx, rsi
0x18001a848  jz      short loc_18001A801
0x18001a84a  test    byte ptr [rcx+1Ch], 2
0x18001a84e  jz      short loc_18001A801
0x18001a850  mov     rcx, [rcx+10h]
0x18001a854  lea     r8, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids
0x18001a85b  mov     edx, 1Dh
0x18001a860  mov     r9d, edi
0x18001a863  call    WPP_SF_d
0x18001a868  jmp     short loc_18001A801
0x18001a86a  mov     rax, qword ptr cs:PKEY_FreeSpace.fmtid.Data1
0x18001a871  sub     rax, [r14]
0x18001a874  jnz     short loc_18001A881
0x18001a876  mov     rax, qword ptr cs:PKEY_FreeSpace.fmtid.Data4
0x18001a87d  sub     rax, [r14+8]
0x18001a881  test    rax, rax
0x18001a884  jnz     loc_18001A6E0
0x18001a88a  jmp     loc_18001AA93
0x18001a88f  mov     ebx, [rbp+57h+var_90.pid]
0x18001a892  cmp     ebx, 3
0x18001a895  jz      loc_18001AC60
0x18001a89b  cmp     ebx, 2
0x18001a89e  jz      loc_18001ABAC
0x18001a8a4  call    cs:__imp_GetProcessHeap
0x18001a8aa  mov     edx, 8; dwFlags
0x18001a8af  mov     r8d, 30h ; '0'; dwBytes
0x18001a8b5  mov     rcx, rax; hHeap
0x18001a8b8  call    cs:__imp_HeapAlloc
0x18001a8be  mov     r14, rax
0x18001a8c1  test    rax, rax
0x18001a8c4  jz      loc_18001AC9D
0x18001a8ca  lea     rcx, [rax+18h]; pvarDest
0x18001a8ce  xorps   xmm0, xmm0
0x18001a8d1  movups  xmmword ptr [rcx], xmm0
0x18001a8d4  xor     eax, eax
0x18001a8d6  lea     rdx, [rbp+57h+pvar]; pvarSrc
0x18001a8da  movups  xmm0, xmmword ptr [rbp+57h+var_90.fmtid.Data1]
0x18001a8de  mov     [rcx+10h], rax
0x18001a8e2  movups  xmmword ptr [r14], xmm0
0x18001a8e6  mov     [r14+10h], ebx
0x18001a8ea  call    cs:__imp_PropVariantCopy
0x18001a8f0  mov     r12d, eax
0x18001a8f3  test    eax, eax
0x18001a8f5  js      loc_18001AF9A
0x18001a8fb  mov     rbx, cs:?s_pfn@?1??IsolationAwareDPA_InsertPtr@@9@4P6AHPEAU_DPA@@HPEAX@ZEA; int (*`IsolationAwareDPA_InsertPtr'::`2'::s_pfn)(_DPA *,int,void *)
0x18001a902  mov     rsi, [rsi+70h]
0x18001a906  test    rbx, rbx
0x18001a909  jz      loc_18001AFD5
0x18001a90f  mov     r8, r14
0x18001a912  mov     edx, 7FFFFFFFh
0x18001a917  mov     rcx, rsi
0x18001a91a  mov     rax, rbx
0x18001a91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a922  cmp     eax, 0FFFFFFFFh
0x18001a925  jz      loc_18001B02E
0x18001a92b  lea     rcx, [rbp+57h+pvar]; pvar
0x18001a92f  mov     ebx, r12d
0x18001a932  call    cs:__imp_PropVariantClear
0x18001a938  jmp     loc_18001A7BC
0x18001a93d  mov     rax, qword ptr cs:WPD_OBJECT_CONTENT_TYPE.fmtid.Data1
0x18001a944  sub     rax, [r14]
0x18001a947  jnz     short loc_18001A954
0x18001a949  mov     rax, qword ptr cs:WPD_OBJECT_CONTENT_TYPE.fmtid.Data4
0x18001a950  sub     rax, [r14+8]
0x18001a954  test    rax, rax
0x18001a957  jnz     loc_18001A799
0x18001a95d  mov     eax, 48h ; 'H'
0x18001a962  cmp     ax, [r15]
0x18001a966  jnz     loc_18001A799
0x18001a96c  movups  xmm6, xmmword ptr cs:PKEY_PerceivedType.fmtid.Data1
0x18001a973  mov     eax, 13h
0x18001a978  mov     [rbp+57h+var_90.pid], 9
0x18001a97f  mov     word ptr [rbp+57h+pvar], ax
0x18001a983  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18001a987  mov     rax, [r15+8]
0x18001a98b  lea     rcx, WPD_CONTENT_TYPE_UNSPECIFIED; Buf1
0x18001a992  mov     r8d, 10h; Size
0x18001a998  movups  xmmword ptr [rbp+57h+var_90.fmtid.Data1], xmm6
0x18001a99c  movups  xmm0, xmmword ptr [rax]
0x18001a99f  movaps  [rbp+57h+Buf2], xmm0
0x18001a9a3  call    memcmp_0
0x18001a9a8  test    eax, eax
0x18001a9aa  jz      loc_18001ACB1
0x18001a9b0  mov     r8d, 10h; Size
0x18001a9b6  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18001a9ba  lea     rcx, WPD_CONTENT_TYPE_FOLDER; Buf1
0x18001a9c1  call    memcmp_0
0x18001a9c6  test    eax, eax
0x18001a9c8  jnz     loc_18001AAEE
0x18001a9ce  mov     dword ptr [rbp+57h+pvar+8], 0FFFFFFFFh
0x18001a9d5  call    cs:__imp_GetProcessHeap
0x18001a9db  mov     edx, 8; dwFlags
0x18001a9e0  mov     r8d, 30h ; '0'; dwBytes
0x18001a9e6  mov     rcx, rax; hHeap
0x18001a9e9  call    cs:__imp_HeapAlloc
0x18001a9ef  mov     r13, rax
0x18001a9f2  test    rax, rax
0x18001a9f5  jz      loc_18001ACBD
0x18001a9fb  lea     rcx, [rax+18h]; pvarDest
0x18001a9ff  xorps   xmm0, xmm0
0x18001aa02  movups  xmmword ptr [rcx], xmm0
0x18001aa05  xor     eax, eax
0x18001aa07  lea     rdx, [rbp+57h+pvar]; pvarSrc
0x18001aa0b  mov     [rcx+10h], rax
0x18001aa0f  movups  xmmword ptr [r13+0], xmm6
0x18001aa14  mov     dword ptr [r13+10h], 9
0x18001aa1c  call    cs:__imp_PropVariantCopy
0x18001aa22  mov     r12d, eax
0x18001aa25  test    eax, eax
0x18001aa27  js      loc_18001AE32
0x18001aa2d  mov     rbx, cs:?s_pfn@?1??IsolationAwareDPA_InsertPtr@@9@4P6AHPEAU_DPA@@HPEAX@ZEA; int (*`IsolationAwareDPA_InsertPtr'::`2'::s_pfn)(_DPA *,int,void *)
0x18001aa34  mov     rax, [rsi+70h]
0x18001aa38  mov     qword ptr [rbp+57h+Buf2], rax
0x18001aa3c  test    rbx, rbx
0x18001aa3f  jz      loc_18001AE6D
0x18001aa45  mov     rcx, rax
0x18001aa48  mov     r8, r13
0x18001aa4b  mov     rax, rbx
0x18001aa4e  mov     edx, 7FFFFFFFh
0x18001aa53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa58  cmp     eax, 0FFFFFFFFh
0x18001aa5b  jz      loc_18001AEC6
0x18001aa61  mov     ebx, r12d
0x18001aa64  lea     rcx, [rbp+57h+pvar]; pvar
0x18001aa68  call    cs:__imp_PropVariantClear
0x18001aa6e  jmp     loc_18001A799
0x18001aa73  mov     rax, qword ptr cs:PKEY_Capacity.fmtid.Data1
0x18001aa7a  sub     rax, [r14]
0x18001aa7d  jnz     short loc_18001AA8A
0x18001aa7f  mov     rax, qword ptr cs:PKEY_Capacity.fmtid.Data4
0x18001aa86  sub     rax, [r14+8]
0x18001aa8a  test    rax, rax
0x18001aa8d  jnz     loc_18001A6E0
0x18001aa93  cmp     qword ptr [r8+8], 0FFFFFFFFFFFFFFFFh
0x18001aa98  jnz     loc_18001A6E0
0x18001aa9e  mov     ebx, 1
0x18001aaa3  jmp     loc_18001A772
0x18001aaa8  mov     ebx, 8007000Eh
0x18001aaad  mov     r12d, ebx
0x18001aab0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aab7  lea     rsi, WPP_GLOBAL_Control
0x18001aabe  cmp     rcx, rsi
0x18001aac1  jz      loc_18001A7CB
0x18001aac7  test    byte ptr [rcx+1Ch], 2
0x18001aacb  jz      loc_18001A7CB
0x18001aad1  mov     rcx, [rcx+10h]
0x18001aad5  lea     r8, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids
0x18001aadc  mov     edx, 19h
0x18001aae1  mov     r9d, r12d
0x18001aae4  call    WPP_SF_d
0x18001aae9  jmp     loc_18001A7CB
0x18001aaee  mov     r8d, 10h; Size
0x18001aaf4  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18001aaf8  lea     rcx, WPD_CONTENT_TYPE_FUNCTIONAL_OBJECT; Buf1
0x18001aaff  call    memcmp_0
0x18001ab04  test    eax, eax
0x18001ab06  jz      loc_18001A9CE
0x18001ab0c  mov     r8d, 10h; Size
0x18001ab12  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18001ab16  lea     rcx, WPD_CONTENT_TYPE_IMAGE; Buf1
0x18001ab1d  call    memcmp_0
0x18001ab22  test    eax, eax
0x18001ab24  jz      loc_18001AC54
0x18001ab2a  mov     r8d, 10h; Size
0x18001ab30  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18001ab34  lea     rcx, WPD_CONTENT_TYPE_AUDIO; Buf1
0x18001ab3b  call    memcmp_0
0x18001ab40  test    eax, eax
0x18001ab42  jz      loc_18001ACF0
0x18001ab48  mov     r8d, 10h; Size
0x18001ab4e  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18001ab52  lea     rcx, WPD_CONTENT_TYPE_VIDEO; Buf1
0x18001ab59  call    memcmp_0
0x18001ab5e  test    eax, eax
0x18001ab60  jz      loc_18001AE10
0x18001ab66  mov     r8d, 10h; Size
  ... truncated ...
```
