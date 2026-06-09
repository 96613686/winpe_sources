# CWiaItem::ReadMultiple(ulong,tagPROPSPEC const * const,tagPROPVARIANT * const)

- ea: `0x1800279b0`
- end: `0x1800283d8`
- name: `?ReadMultiple@CWiaItem@@UEAAJKQEBUtagPROPSPEC@@QEAUtagPROPVARIANT@@@Z`
- size: `2600`
- prototype: `int(CWiaItem *__hidden this, unsigned int, const struct tagPROPSPEC *const, struct tagPROPVARIANT *const)`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x180065510`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x180018ad8`
- `0x18001bbc4`
- `0x18001da54`
- `0x18001db34`
- `0x18001e364`
- `0x18001e3dc`
- `0x1800279b0`
- `0x180028560`
- `0x18002de18`
- `0x18002def8`
- `0x180030060`
- `0x180057454`
- `0x18005d1e0`
- `0x180062bfc`
- `0x1800649a0`
- `0x1800657a8`
- `0x1800659c8`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18002830e`
- `KERNEL32!LocalFree` at `0x18002830e`
- `ole32!PropVariantClear` at `0x180027f12`
- `ole32!PropVariantClear` at `0x180027f12`
- `api-ms-win-core-com-l1-1-0!FreePropVariantArray` at `0x1800281c9`
- `api-ms-win-core-com-l1-1-0!FreePropVariantArray` at `0x18002825e`
- `api-ms-win-core-com-l1-1-0!FreePropVariantArray` at `0x1800281c9`
- `api-ms-win-core-com-l1-1-0!FreePropVariantArray` at `0x18002825e`

## string_xrefs

- `0x1800279d2`: `CWiaItem::ReadMultiple`
- `0x1800279e3`: `CWiaItem::ReadMultiple`
- `0x180027a59`: `CWiaItem::ReadMultiple`
- `0x180027a85`: `CWiaItem::ReadMultiple`
- `0x180027ac7`: `CWiaItem::ReadMultiple`
- `0x180027af7`: `CWiaItem::ReadMultiple`
- `0x180027ba0`: `CWiaItem::ReadMultiple`
- `0x180027c54`: `CWiaItem::ReadMultiple`
- `0x180027c84`: `CWiaItem::ReadMultiple`
- `0x180027cd1`: `CWiaItem::ReadMultiple`
- `0x180027f42`: `CWiaItem::ReadMultiple`
- `0x180027f72`: `CWiaItem::ReadMultiple`
- `0x180027fcf`: `CWiaItem::ReadMultiple`
- `0x180028003`: `CWiaItem::ReadMultiple`
- `0x18002803c`: `CWiaItem::ReadMultiple`
- `0x180028076`: `CWiaItem::ReadMultiple`
- `0x1800280bd`: `CWiaItem::ReadMultiple`
- `0x1800280ed`: `CWiaItem::ReadMultiple`
- `0x18002810a`: `CWiaItem::ReadMultiple`
- `0x18002813a`: `CWiaItem::ReadMultiple`
- `0x180028188`: `CWiaItem::ReadMultiple`
- `0x180028355`: `CWiaItem::ReadMultiple`
- `0x180027ab8`: `ValidateWiaDrvItemAccess failed (0x%X)`
- `0x180027ade`: `ValidateWiaDrvItemAccess failed (0x%X)`
- `0x180027cc2`: `failed to read WIA_DPS_DOCUMENT_HANDLING_SELECT on the root D-AIT item (0x%X)`
- `0x180027ce8`: `failed to read WIA_DPS_DOCUMENT_HANDLING_SELECT on the root D-AIT item (0x%X)`
- `0x180028064`: `ReadMultiple for %u on D-AIT item failed (0x%X)`
- `0x180028091`: `ReadMultiple for %u on D-AIT item failed (0x%X)`
- `0x180028340`: `from cache`
- `0x1800280fb`: `failed to translate call to linked D-AIT item(s) (0x%X)`
- `0x180028121`: `failed to translate call to linked D-AIT item(s) (0x%X)`
- `0x18002802a`: `WriteMultiple for %u on A-AIT item failed (0x%X)`
- `0x180028057`: `WriteMultiple for %u on A-AIT item failed (0x%X)`

## pseudocode

```c
__int64 __fastcall CWiaItem::ReadMultiple(
        CWiaItem *this,
        unsigned int a2,
        struct tagPROPSPEC *a3,
        struct tagPROPVARIANT *const a4)
{
  struct tagWiaTraceData_Type *v8; // rax
  char *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r12
  __int64 v12; // rax
  int inited; // edi
  int v14; // ebx
  char *v15; // rbx
  void *v16; // rdx
  void **v17; // rax
  void *v18; // rdx
  __int64 v19; // rcx
  char *v20; // rbx
  void *v21; // rdx
  void **v22; // rax
  void *v23; // rdx
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  bool v27; // zf
  unsigned __int16 *v28; // rcx
  char *v29; // rbx
  void *v30; // rdx
  CWiaItem *v31; // rcx
  unsigned int v32; // ebx
  char *v33; // rcx
  char *v34; // rbx
  void *v35; // rdx
  void **v36; // rax
  void *v37; // rdx
  __int64 v38; // rcx
  unsigned int v39; // ebx
  char *v40; // rbx
  void *v41; // rdx
  void **v42; // rax
  void *v43; // rdx
  __int64 v44; // rcx
  __int64 i; // rax
  __int64 v46; // rax
  struct tagPROPSPEC v47; // xmm0
  int v48; // edx
  int v49; // edx
  char *v50; // rbx
  int v51; // eax
  char *v52; // rbx
  void *v53; // rdx
  char *v54; // rbx
  void *v55; // rdx
  void **v56; // rax
  void *v57; // rdx
  __int64 v58; // rcx
  char *v59; // rbx
  void *v60; // rdx
  char *v61; // rbx
  void *v62; // rdx
  char *v63; // rbx
  void *v64; // rdx
  char *v65; // rbx
  void *v66; // rdx
  void **v67; // rax
  void *v68; // rdx
  __int64 v69; // rcx
  char *v70; // rbx
  void *v71; // rdx
  unsigned int j; // ebx
  __int64 v73; // rdx
  int v74; // r12d
  int v75; // eax
  int v76; // edx
  CWiaPropStg *v77; // rcx
  struct tagPROPSPEC *v78; // rbx
  struct tagPROPSPEC *v79; // r8
  int v80; // eax
  int v81; // ecx
  __int64 v82; // rax
  unsigned int lpMem; // [rsp+20h] [rbp-E0h]
  unsigned int v85; // [rsp+40h] [rbp-C0h] BYREF
  int v86; // [rsp+44h] [rbp-BCh]
  int v87; // [rsp+48h] [rbp-B8h]
  BOOL v88; // [rsp+4Ch] [rbp-B4h]
  struct tagPROPSPEC v89; // [rsp+50h] [rbp-B0h] BYREF
  char *v90; // [rsp+60h] [rbp-A0h]
  __int128 v91; // [rsp+68h] [rbp-98h] BYREF
  struct tagPROPSPEC v92; // [rsp+78h] [rbp-88h] BYREF
  PROPVARIANT pvar[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v94; // [rsp+98h] [rbp-68h]
  __int128 v95; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v96; // [rsp+B0h] [rbp-50h]
  _BYTE v97[128]; // [rsp+C0h] [rbp-40h] BYREF
  int v98; // [rsp+150h] [rbp+50h] BYREF
  HLOCAL hMem; // [rsp+168h] [rbp+68h] BYREF

  v8 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaItem::ReadMultiple");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v97, v9, v10, "CWiaItem::ReadMultiple", lpMem, v8);
  v11 = (char *)this - 8;
  v12 = *((_QWORD *)this + 25);
  inited = 0;
  if ( !v12 || !*(_DWORD *)(v12 + 104) || !*(_QWORD *)(v12 + 64) || (v86 = 1, !*(_DWORD *)(v12 + 108)) )
    v86 = 0;
  LODWORD(hMem) = *((_DWORD *)this + 54);
  v14 = (int)hMem;
  v88 = (_DWORD)hMem == 1;
  if ( a4 )
  {
    if ( !*(_QWORD *)(v12 + 64) )
    {
      inited = ValidateWiaDrvItemAccess(*((struct CWiaDrvItem **)this + 21));
      if ( inited < 0 )
      {
        v20 = (char *)WiaTrace_TraceLog("ValidateWiaDrvItemAccess failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::ReadMultiple", v20);
        WiaTrcLib::Free((WiaTrcLib *)v20, v21);
        v22 = (void **)WiaTrace_Trace("ValidateWiaDrvItemAccess failed (0x%X)", (unsigned int)inited);
LABEL_11:
        WiaTrace_ProcessTrace_Ex(v24, v23, (void *)"CWiaItem::ReadMultiple", 1, v22);
        goto LABEL_133;
      }
    }
    v25 = v86;
    if ( !v86 && !*((_DWORD *)this + 30) )
    {
      if ( (unsigned int)AreWiaInitializedProps(a2, a3) )
      {
        inited = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct tagPROPSPEC *, struct tagPROPVARIANT *const))(***((_QWORD ***)v11 + 27) + 24LL))(
                   **((_QWORD **)v11 + 27),
                   a2,
                   a3,
                   a4);
        if ( !(unsigned int)CWiaItem::IsCompatMode((CWiaItem *)((char *)this - 8)) )
          goto LABEL_131;
        v26 = *((_QWORD *)this + 25);
        if ( !v26 )
          goto LABEL_131;
        v27 = *(_DWORD *)(v26 + 108) == 0;
        v28 = L"D-AIT";
LABEL_130:
        if ( !v27 )
        {
LABEL_132:
          LogRWMultiple(1, a2, a3, a4, v28);
          goto LABEL_133;
        }
LABEL_131:
        v28 = L"AIT";
        goto LABEL_132;
      }
      inited = CWiaItem::InitLazyProps((CWiaItem *)((char *)this - 8));
      if ( inited < 0 )
      {
        v29 = (char *)WiaTrace_TraceLog("InitLazyProps failed (%#x)");
        WriteDbgTraceErrorWI("CWiaItem::ReadMultiple", v29);
        WiaTrcLib::Free((WiaTrcLib *)v29, v30);
        v22 = (void **)WiaTrace_Trace("InitLazyProps failed (%#x)", (unsigned int)inited);
        goto LABEL_11;
      }
      v25 = v86;
    }
    if ( v25 )
    {
      v31 = (CWiaItem *)*((_QWORD *)v11 + 26);
      if ( v31 == (CWiaItem *)v11 )
      {
        v85 = 0;
        if ( v14 == 1 )
        {
          v32 = 0;
          v98 = 0;
          inited = CWiaItem::GetDocumentHandling(v31, &v85, 0);
          if ( inited >= 0 )
          {
            v32 = v85 & 1;
            v98 = v32;
          }
          v33 = *(char **)(*((_QWORD *)this + 25) + 8 * (v32 ^ 1LL) + 88);
          v90 = v33;
          if ( inited >= 0 && !v33 )
          {
            inited = -2147467261;
            v34 = (char *)WiaTrace_TraceLog("NULL D-AIT item (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::ReadMultiple", v34);
            WiaTrcLib::Free((WiaTrcLib *)v34, v35);
            v36 = (void **)WiaTrace_Trace("NULL D-AIT item (0x%X)", -2147467261);
            WiaTrace_ProcessTrace_Ex(v38, v37, (void *)"CWiaItem::ReadMultiple", 1, v36);
            v32 = v98;
          }
          if ( inited >= 0 )
          {
            v39 = (v32 ^ 1) + 5;
LABEL_34:
            v98 = v39;
            for ( i = 0; ; i = (unsigned int)(v87 + 1) )
            {
              v87 = i;
              if ( (unsigned int)i >= a2 )
                break;
              v46 = i;
              v89 = 0;
              v47 = a3[v46];
              v92 = v47;
              if ( a3[v46].ulKind )
              {
                v89 = v47;
              }
              else
              {
                inited = CWiaPropStg::GetPropIDFromName(*((CWiaPropStg **)this + 26), &v92, &v89);
                if ( inited < 0 )
                {
                  v52 = (char *)WiaTrace_TraceLog("GetPropIDFromName failed (0x%X)");
                  WriteDbgTraceErrorWI("CWiaItem::ReadMultiple", v52);
                  WiaTrcLib::Free((WiaTrcLib *)v52, v53);
                  v42 = (void **)WiaTrace_Trace("GetPropIDFromName failed (0x%X)", (unsigned int)inited);
                  goto LABEL_78;
                }
                v89.ulKind = 1;
              }
              v95 = 0;
              v96 = 0;
              if ( (unsigned int)CWiaItem::GetPropCompatCategory(v33, v89.propid, v88, v39, &v95)
                && (unsigned int)(v48 - 4105) > 1
                && v48 != 3088
                && v48 != 4108 )
              {
                v49 = (int)hMem;
                if ( (_DWORD)hMem == 1 )
                {
                  if ( DWORD1(v96) == 4 || DWORD1(v96) == 8 && *((char **)v11 + 26) == v11 )
                  {
                    v33 = (char *)this + 56;
                    v50 = (char *)*((_QWORD *)this + 7);
                  }
                  else
                  {
                    v33 = (char *)this + 56;
                    if ( DWORD1(v96) == 6 && !*(_QWORD *)(*(_QWORD *)v33 + 96LL) )
                      continue;
                    if ( DWORD1(v96) == 5 )
                    {
                      if ( !*(_QWORD *)(*(_QWORD *)v33 + 88LL) )
                        continue;
                      v50 = *(char **)(*(_QWORD *)v33 + 88LL);
                    }
                    else if ( DWORD1(v96) == 6 )
                    {
                      v50 = *(char **)(*(_QWORD *)v33 + 96LL);
                    }
                    else
                    {
                      v50 = v90;
                    }
                  }
                  v49 = (int)hMem;
                }
                else
                {
                  if ( !DWORD2(v95) )
                    continue;
                  if ( DWORD2(v95) == 1 || DWORD2(v95) == 3 && *((char **)v11 + 26) == v11 )
                  {
                    v33 = (char *)this + 56;
                    v50 = (char *)*((_QWORD *)this + 7);
                  }
                  else
                  {
                    v33 = (char *)this + 56;
                    v50 = *(char **)(*((_QWORD *)this + 7) + 80LL);
                  }
                }
                if ( !v50 )
                {
                  inited = -2147467261;
                  v65 = (char *)WiaTrace_TraceLog("NULL D-AIT item (2) (0x%X)");
                  WriteDbgTraceErrorWI("CWiaItem::ReadMultiple", v65);
                  WiaTrcLib::Free((WiaTrcLib *)v65, v66);
                  v67 = (void **)WiaTrace_Trace("NULL D-AIT item (2) (0x%X)", -2147467261);
                  WiaTrace_ProcessTrace_Ex(v69, v68, (void *)"CWiaItem::ReadMultiple", 1, v67);
                  goto LABEL_88;
                }
                if ( v49 != 1 && v50 != *(char **)v33 )
                {
                  inited = CWiaItem::SetLegacyItemContext((CWiaItem *)((char *)this - 8));
                  if ( inited < 0 )
                  {
                    v59 = (char *)WiaTrace_TraceLog("SetLegacyItemContext failed (0x%X)");
                    WriteDbgTraceErrorWI("CWiaItem::ReadMultiple", v59);
                    WiaTrcLib::Free((WiaTrcLib *)v59, v60);
                    v42 = (void **)WiaTrace_Trace("SetLegacyItemContext failed (0x%X)", (unsigned int)inited);
                    goto LABEL_78;
                  }
                  v49 = (int)hMem;
                }
                v51 = DWORD1(v95);
                if ( v49 == 1 )
                  v51 = v96;
                v91 = 0;
                DWORD2(v91) = v51;
                v94 = 0;
                LODWORD(v91) = 1;
                *(_OWORD *)pvar = 0;
                inited = (*(__int64 (__fastcall **)(char *, __int64, __int128 *, PROPVARIANT *))(*((_QWORD *)v50 + 1)
                                                                                               + 24LL))(
                           v50 + 8,
                           1,
                           &v91,
                           pvar);
                if ( inited < 0 )
                {
                  v63 = (char *)WiaTrace_TraceLog("ReadMultiple for %u on D-AIT item failed (0x%X)");
                  WriteDbgTraceErrorWI("CWiaItem::ReadMultiple", v63);
                  WiaTrcLib::Free((WiaTrcLib *)v63, v64);
                  v42 = (void **)WiaTrace_Trace(
                                   "ReadMultiple for %u on D-AIT item failed (0x%X)",
                                   DWORD2(v91),
                                   (unsigned int)inited);
                  goto LABEL_78;
                }
                inited = (*(__int64 (__fastcall **)(_QWORD, __int64, struct tagPROPSPEC *, PROPVARIANT *, int))(***((_QWORD ***)this + 26) + 32LL))(
                           **((_QWORD **)this + 26),
                           1,
                           &v89,
                           pvar,
                           2);
                if ( LOWORD(pvar[0]) )
                  PropVariantClear(pvar);
                if ( inited < 0 )
                {
                  v61 = (char *)WiaTrace_TraceLog("WriteMultiple for %u on A-AIT item failed (0x%X)");
                  WriteDbgTraceErrorWI("CWiaItem::ReadMultiple", v61);
                  WiaTrcLib::Free((WiaTrcLib *)v61, v62);
                  v42 = (void **)WiaTrace_Trace(
                                   "WriteMultiple for %u on A-AIT item failed (0x%X)",
                                   v89.propid,
                                   (unsigned int)inited);
                  goto LABEL_78;
                }
                v39 = v98;
              }
            }
          }
        }
        else
        {
          inited = CWiaItem::GetDocumentHandling(*((CWiaItem **)this + 7), &v85, 1);
          if ( inited >= 0 )
          {
            v90 = 0;
            v39 = 8;
            goto LABEL_34;
          }
          v40 = (char *)WiaTrace_TraceLog("failed to read WIA_DPS_DOCUMENT_HANDLING_SELECT on the root D-AIT item (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::ReadMultiple", v40);
          WiaTrcLib::Free((WiaTrcLib *)v40, v41);
          v42 = (void **)WiaTrace_Trace(
                           "failed to read WIA_DPS_DOCUMENT_HANDLING_SELECT on the root D-AIT item (0x%X)",
                           (unsigned int)inited);
LABEL_78:
          WiaTrace_ProcessTrace_Ex(v44, v43, (void *)"CWiaItem::ReadMultiple", 1, v42);
        }
        if ( inited < 0 )
        {
LABEL_88:
          v70 = (char *)WiaTrace_TraceLog("failed to translate call to linked D-AIT item(s) (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::ReadMultiple", v70);
          WiaTrcLib::Free((WiaTrcLib *)v70, v71);
          v56 = (void **)WiaTrace_Trace("failed to translate call to linked D-AIT item(s) (0x%X)", (unsigned int)inited);
          goto LABEL_89;
        }
        if ( (_DWORD)hMem != 1 )
        {
          if ( v85 )
          {
            inited = CWiaItem::SetDocumentHandling(*((CWiaItem **)this + 7), v85, 0);
            if ( inited < 0 )
            {
              inited = -2147467261;
              v54 = (char *)WiaTrace_TraceLog("failed to restore WIA_DPS_DOCUMENT_HANDLING_SELECT on the root D-AIT item (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::ReadMultiple", v54);
              WiaTrcLib::Free((WiaTrcLib *)v54, v55);
              v56 = (void **)WiaTrace_Trace(
                               "failed to restore WIA_DPS_DOCUMENT_HANDLING_SELECT on the root D-AIT item (0x%X)",
                               2147500035LL);
LABEL_89:
              WiaTrace_ProcessTrace_Ex(v58, v57, (void *)"CWiaItem::ReadMultiple", 1, v56);
            }
          }
        }
      }
    }
    if ( inited < 0 )
      goto LABEL_125;
    inited = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct tagPROPSPEC *, struct tagPROPVARIANT *const))(**(_QWORD **)(*((_QWORD *)this + 26) + 16LL) + 24LL))(
               *(_QWORD *)(*((_QWORD *)this + 26) + 16LL),
               a2,
               a3,
               a4);
    if ( inited < 0 )
    {
      ReportReadWriteMultipleError(inited, "CWiaItem::ReadMultiple", 0, 1, a2, a3);
      goto LABEL_111;
    }
    for ( j = 0; j < a2; ++j )
    {
      if ( a4[j].vt == 19 && (a4[j].lVal & 0x10000) == 0 )
        break;
    }
    FreePropVariantArray(a2, (PROPVARIANT *)a4);
    v73 = *((_QWORD *)this + 25);
    if ( v73 && *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 18) + 4128LL) + 32LL) == v73 )
    {
      v74 = 1;
    }
    else
    {
      v74 = 0;
      if ( j != a2 )
      {
LABEL_110:
        v11 = (char *)this - 8;
LABEL_111:
        if ( inited >= 0 )
        {
          v77 = (CWiaPropStg *)*((_QWORD *)this + 26);
          hMem = 0;
          inited = CWiaPropStg::NamesToPropIDs(v77, a2, a3, (struct tagPROPSPEC **)&hMem);
          v98 = inited;
          if ( inited < 0 )
            goto LABEL_127;
          v78 = (struct tagPROPSPEC *)hMem;
          if ( !v86 )
          {
            LOCK_WIA_DEVICE::LOCK_WIA_DEVICE((LOCK_WIA_DEVICE *)&v92, (struct CWiaItem *)v11, &v98, 0);
            inited = v98;
            if ( v98 >= 0 )
            {
              v79 = a3;
              if ( v78 )
                v79 = v78;
              inited = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, _QWORD, struct tagPROPSPEC *, char *))(**((_QWORD **)this + 18) + 400LL))(
                         *((_QWORD *)this + 18),
                         v11,
                         0,
                         a2,
                         v79,
                         (char *)this + 152);
            }
            LOCK_WIA_DEVICE::~LOCK_WIA_DEVICE((LOCK_WIA_DEVICE *)&v92);
          }
          if ( v78 )
            LocalFree(v78);
          if ( inited < 0 )
            goto LABEL_127;
          v80 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct tagPROPSPEC *, struct tagPROPVARIANT *const))(***((_QWORD ***)this + 26) + 24LL))(
                  **((_QWORD **)this + 26),
                  a2,
                  a3,
                  a4);
          inited = v80;
          if ( v80 >= 0 )
            goto LABEL_127;
          v81 = v80;
LABEL_126:
          ReportReadWriteMultipleError(v81, "CWiaItem::ReadMultiple", 0, 1, a2, a3);
LABEL_127:
          if ( !(unsigned int)CWiaItem::IsCompatMode((CWiaItem *)v11) )
            goto LABEL_131;
          v82 = *((_QWORD *)this + 25);
          if ( !v82 )
            goto LABEL_131;
          v27 = *(_DWORD *)(v82 + 108) == 0;
          v28 = L"A-AIT";
          goto LABEL_130;
        }
LABEL_125:
        v81 = inited;
        goto LABEL_126;
      }
    }
    v75 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct tagPROPSPEC *, struct tagPROPVARIANT *const))(***((_QWORD ***)this + 26) + 24LL))(
            **((_QWORD **)this + 26),
            a2,
            a3,
            a4);
    inited = v75;
    if ( v75 && (v75 < 0 || !v74) )
      goto LABEL_110;
    v76 = 0;
    if ( a2 )
    {
      while ( a4[v76].vt )
      {
        if ( ++v76 >= a2 )
          goto LABEL_107;
      }
    }
    else
    {
LABEL_107:
      if ( v76 == a2 )
        goto LABEL_124;
    }
    if ( !v74 )
    {
      FreePropVariantArray(a2, (PROPVARIANT *)a4);
      goto LABEL_110;
    }
LABEL_124:
    LogRWMultiple(1, a2, a3, a4, L"from cache");
    goto LABEL_133;
  }
  v15 = (char *)WiaTrace_TraceLog("last parameter (rgpropvar) is invalid");
  WriteDbgTraceErrorWI("CWiaItem::ReadMultiple", v15);
  WiaTrcLib::Free((WiaTrcLib *)v15, v16);
  v17 = (void **)WiaTrace_Trace("last parameter (rgpropvar) is invalid");
  WiaTrace_ProcessTrace_Ex(v19, v18, (void *)"CWiaItem::ReadMultiple", 1, v17);
  inited = -2147024809;
LABEL_133:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v97);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800279b0  mov     [rsp-8+arg_8], rbx
0x1800279b5  push    rbp
0x1800279b6  push    rsi
0x1800279b7  push    rdi
0x1800279b8  push    r12
0x1800279ba  push    r13
0x1800279bc  push    r14
0x1800279be  push    r15
0x1800279c0  lea     rbp, [rsp-10h]
0x1800279c5  sub     rsp, 110h
0x1800279cc  mov     r14, rcx
0x1800279cf  mov     r13, r9
0x1800279d2  lea     rcx, aCwiaitemReadmu; "CWiaItem::ReadMultiple"
0x1800279d9  mov     r15, r8
0x1800279dc  mov     esi, edx
0x1800279de  call    WiaTrace_Trace
0x1800279e3  lea     r9, aCwiaitemReadmu; "CWiaItem::ReadMultiple"
0x1800279ea  mov     [rsp+140h+var_118], rax; struct tagWiaTraceData_Type *
0x1800279ef  lea     rcx, [rbp+40h+var_80]; this
0x1800279f3  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x1800279f8  xor     r8d, r8d
0x1800279fb  lea     r12, [r14-8]
0x1800279ff  mov     rax, [r12+0D0h]
0x180027a07  mov     edi, r8d
0x180027a0a  test    rax, rax
0x180027a0d  jz      short loc_180027A29
0x180027a0f  cmp     [rax+68h], r8d
0x180027a13  jz      short loc_180027A29
0x180027a15  cmp     [rax+40h], r8
0x180027a19  jz      short loc_180027A29
0x180027a1b  mov     [rsp+140h+var_FC], 1
0x180027a23  cmp     [rax+6Ch], r8d
0x180027a27  jnz     short loc_180027A2E
0x180027a29  mov     [rsp+140h+var_FC], r8d
0x180027a2e  mov     ebx, [r14+0D8h]
0x180027a35  mov     ecx, r8d
0x180027a38  cmp     ebx, 1
0x180027a3b  mov     dword ptr [rbp+40h+hMem], ebx
0x180027a3e  setz    cl
0x180027a41  mov     [rsp+140h+var_F4], ecx
0x180027a45  test    r13, r13
0x180027a48  jnz     short loc_180027A9B
0x180027a4a  lea     rcx, aLastParameterR; "last parameter (rgpropvar) is invalid"
0x180027a51  call    WiaTrace_TraceLog
0x180027a56  mov     rdx, rax; char *
0x180027a59  lea     rcx, aCwiaitemReadmu; "CWiaItem::ReadMultiple"
0x180027a60  mov     rbx, rax
0x180027a63  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180027a68  mov     rcx, rbx; this
0x180027a6b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180027a70  lea     rcx, aLastParameterR; "last parameter (rgpropvar) is invalid"
0x180027a77  call    WiaTrace_Trace
0x180027a7c  lea     r9d, [r13+1]; int
0x180027a80  mov     [rsp+140h+lpMem], rax; lpMem
0x180027a85  lea     r8, aCwiaitemReadmu; "CWiaItem::ReadMultiple"
0x180027a8c  call    WiaTrace_ProcessTrace_Ex
0x180027a91  mov     edi, 80070057h
0x180027a96  jmp     loc_1800283B2
0x180027a9b  cmp     [rax+40h], r8
0x180027a9f  jnz     short loc_180027B08
0x180027aa1  mov     rcx, [r14+0A8h]; struct CWiaDrvItem *
0x180027aa8  call    ?ValidateWiaDrvItemAccess@@YAJPEAVCWiaDrvItem@@@Z; ValidateWiaDrvItemAccess(CWiaDrvItem *)
0x180027aad  xor     r8d, r8d
0x180027ab0  mov     edi, eax
0x180027ab2  test    eax, eax
0x180027ab4  jns     short loc_180027B08
0x180027ab6  mov     edx, eax
0x180027ab8  lea     rcx, aValidatewiadrv_1; "ValidateWiaDrvItemAccess failed (0x%X)"
0x180027abf  call    WiaTrace_TraceLog
0x180027ac4  mov     rdx, rax; char *
0x180027ac7  lea     rcx, aCwiaitemReadmu; "CWiaItem::ReadMultiple"
0x180027ace  mov     rbx, rax
0x180027ad1  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180027ad6  mov     rcx, rbx; this
0x180027ad9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180027ade  lea     rcx, aValidatewiadrv_1; "ValidateWiaDrvItemAccess failed (0x%X)"
0x180027ae5  mov     edx, edi
0x180027ae7  call    WiaTrace_Trace
0x180027aec  mov     r9d, 1; int
0x180027af2  mov     [rsp+140h+lpMem], rax; lpMem
0x180027af7  lea     r8, aCwiaitemReadmu; "CWiaItem::ReadMultiple"
0x180027afe  call    WiaTrace_ProcessTrace_Ex
0x180027b03  jmp     loc_1800283B2
0x180027b08  mov     eax, [rsp+140h+var_FC]
0x180027b0c  test    eax, eax
0x180027b0e  jnz     loc_180027BC7
0x180027b14  cmp     [r14+78h], r8d
0x180027b18  jnz     loc_180027BC7
0x180027b1e  mov     rdx, r15; struct tagPROPSPEC *
0x180027b21  mov     ecx, esi; unsigned int
0x180027b23  call    ?AreWiaInitializedProps@@YAHKPEAUtagPROPSPEC@@@Z; AreWiaInitializedProps(ulong,tagPROPSPEC *)
0x180027b28  test    eax, eax
0x180027b2a  jz      short loc_180027B7E
0x180027b2c  mov     rax, [r12+0D8h]
0x180027b34  mov     r9, r13
0x180027b37  mov     r8, r15
0x180027b3a  mov     edx, esi
0x180027b3c  mov     rcx, [rax]
0x180027b3f  mov     rax, [rcx]
0x180027b42  mov     rax, [rax+18h]
0x180027b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b4b  mov     rcx, r12; this
0x180027b4e  mov     edi, eax
0x180027b50  call    ?IsCompatMode@CWiaItem@@QEBAHXZ; CWiaItem::IsCompatMode(void)
0x180027b55  xor     edx, edx
0x180027b57  test    eax, eax
0x180027b59  jz      loc_180028394
0x180027b5f  mov     rcx, [r14+0C8h]
0x180027b66  test    rcx, rcx
0x180027b69  jz      loc_180028394
0x180027b6f  cmp     [rcx+6Ch], edx
0x180027b72  lea     rcx, aDAit; "D-AIT"
0x180027b79  jmp     loc_180028392
0x180027b7e  mov     rcx, r12; this
0x180027b81  call    ?InitLazyProps@CWiaItem@@QEAAJXZ; CWiaItem::InitLazyProps(void)
0x180027b86  xor     r8d, r8d
0x180027b89  mov     edi, eax
0x180027b8b  test    eax, eax
0x180027b8d  jns     short loc_180027BC3
0x180027b8f  mov     edx, eax
0x180027b91  lea     rcx, aInitlazypropsF; "InitLazyProps failed (%#x)"
0x180027b98  call    WiaTrace_TraceLog
0x180027b9d  mov     rdx, rax; char *
0x180027ba0  lea     rcx, aCwiaitemReadmu; "CWiaItem::ReadMultiple"
0x180027ba7  mov     rbx, rax
0x180027baa  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180027baf  mov     rcx, rbx; this
0x180027bb2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180027bb7  lea     rcx, aInitlazypropsF; "InitLazyProps failed (%#x)"
0x180027bbe  jmp     loc_180027AE5
0x180027bc3  mov     eax, [rsp+140h+var_FC]
0x180027bc7  test    edi, edi
0x180027bc9  js      loc_18002834E
0x180027bcf  test    eax, eax
0x180027bd1  jz      loc_180028149
0x180027bd7  mov     rcx, [r12+0D0h]; this
0x180027bdf  cmp     rcx, r12
0x180027be2  jnz     loc_180028149
0x180027be8  mov     [rsp+140h+var_100], r8d
0x180027bed  lea     rdx, [rsp+140h+var_100]; unsigned int *
0x180027bf2  cmp     ebx, 1
0x180027bf5  jnz     loc_180027CA8
0x180027bfb  mov     ebx, r8d
0x180027bfe  xor     r8d, r8d; int
0x180027c01  mov     [rbp+40h+arg_0], ebx
0x180027c04  call    ?GetDocumentHandling@CWiaItem@@QEAAJAEAKH@Z; CWiaItem::GetDocumentHandling(ulong &,int)
0x180027c09  xor     r8d, r8d
0x180027c0c  mov     edi, eax
0x180027c0e  test    eax, eax
0x180027c10  js      short loc_180027C1C
0x180027c12  mov     ebx, [rsp+140h+var_100]
0x180027c16  and     ebx, 1
0x180027c19  mov     [rbp+40h+arg_0], ebx
0x180027c1c  mov     rax, [r14+0C8h]
0x180027c23  mov     ecx, ebx
0x180027c25  xor     rcx, 1
0x180027c29  mov     rcx, [rax+rcx*8+58h]
0x180027c2e  mov     [rsp+140h+var_E0], rcx
0x180027c33  test    edi, edi
0x180027c35  js      short loc_180027C96
0x180027c37  test    rcx, rcx
0x180027c3a  jnz     short loc_180027C96
0x180027c3c  mov     eax, 80004003h
0x180027c41  lea     rcx, aNullDAitItem0x; "NULL D-AIT item (0x%X)"
0x180027c48  mov     edx, eax
0x180027c4a  mov     edi, eax
0x180027c4c  call    WiaTrace_TraceLog
0x180027c51  mov     rdx, rax; char *
0x180027c54  lea     rcx, aCwiaitemReadmu; "CWiaItem::ReadMultiple"
0x180027c5b  mov     rbx, rax
0x180027c5e  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180027c63  mov     rcx, rbx; this
0x180027c66  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180027c6b  mov     edx, edi
0x180027c6d  lea     rcx, aNullDAitItem0x; "NULL D-AIT item (0x%X)"
0x180027c74  call    WiaTrace_Trace
0x180027c79  mov     r9d, 1; int
0x180027c7f  mov     [rsp+140h+lpMem], rax; lpMem
0x180027c84  lea     r8, aCwiaitemReadmu; "CWiaItem::ReadMultiple"
0x180027c8b  call    WiaTrace_ProcessTrace_Ex
0x180027c90  mov     ebx, [rbp+40h+arg_0]
0x180027c93  xor     r8d, r8d
0x180027c96  mov     eax, edi
0x180027c98  test    eax, eax
0x180027c9a  js      loc_180027F81
0x180027ca0  xor     ebx, 1
0x180027ca3  add     ebx, 5
0x180027ca6  jmp     short loc_180027CFE
0x180027ca8  mov     rcx, [r14+38h]; this
0x180027cac  mov     r8d, 1; int
0x180027cb2  call    ?GetDocumentHandling@CWiaItem@@QEAAJAEAKH@Z; CWiaItem::GetDocumentHandling(ulong &,int)
0x180027cb7  xor     r8d, r8d
0x180027cba  mov     edi, eax
0x180027cbc  test    eax, eax
0x180027cbe  jns     short loc_180027CF4
0x180027cc0  mov     edx, eax
0x180027cc2  lea     rcx, aFailedToReadWi; "failed to read WIA_DPS_DOCUMENT_HANDLIN"...
0x180027cc9  call    WiaTrace_TraceLog
0x180027cce  mov     rdx, rax; char *
0x180027cd1  lea     rcx, aCwiaitemReadmu; "CWiaItem::ReadMultiple"
0x180027cd8  mov     rbx, rax
0x180027cdb  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180027ce0  mov     rcx, rbx; this
0x180027ce3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180027ce8  lea     rcx, aFailedToReadWi; "failed to read WIA_DPS_DOCUMENT_HANDLIN"...
0x180027cef  jmp     loc_180027F60
0x180027cf4  mov     [rsp+140h+var_E0], r8
0x180027cf9  mov     ebx, 8
0x180027cfe  mov     [rbp+40h+arg_0], ebx
0x180027d01  mov     eax, r8d
0x180027d04  mov     [rsp+140h+var_F8], eax
0x180027d08  cmp     eax, esi
0x180027d0a  jnb     loc_180027F81
0x180027d10  add     rax, rax
0x180027d13  xorps   xmm0, xmm0
0x180027d16  movups  xmmword ptr [rsp+140h+var_F0.ulKind], xmm0
0x180027d1b  movups  xmm0, xmmword ptr [r15+rax*8]
0x180027d20  movdqu  xmmword ptr [rsp+140h+var_C8.ulKind], xmm0
0x180027d26  cmp     [r15+rax*8], r8d
0x180027d2a  jnz     short loc_180027D56
0x180027d2c  mov     rcx, [r14+0D0h]; this
0x180027d33  lea     r8, [rsp+140h+var_F0]; struct tagPROPSPEC *
0x180027d38  lea     rdx, [rsp+140h+var_C8]; struct tagPROPSPEC *
0x180027d3d  call    ?GetPropIDFromName@CWiaPropStg@@QEAAJPEBUtagPROPSPEC@@PEAU2@@Z; CWiaPropStg::GetPropIDFromName(tagPROPSPEC const *,tagPROPSPEC *)
0x180027d42  mov     edi, eax
0x180027d44  test    eax, eax
0x180027d46  js      loc_180027F31
0x180027d4c  mov     [rsp+140h+var_F0.ulKind], 1
0x180027d54  jmp     short loc_180027D5C
0x180027d56  movdqu  xmmword ptr [rsp+140h+var_F0.ulKind], xmm0
0x180027d5c  mov     r8d, [rsp+140h+var_F4]
0x180027d61  lea     rax, [rbp+40h+var_A0]
0x180027d65  mov     edx, dword ptr [rsp+140h+var_F0.8]
0x180027d69  xorps   xmm0, xmm0
0x180027d6c  mov     r9d, ebx
0x180027d6f  mov     [rsp+140h+lpMem], rax
0x180027d74  movups  [rbp+40h+var_A0], xmm0
0x180027d78  movups  [rbp+40h+var_90], xmm0
0x180027d7c  call    ?GetPropCompatCategory@CWiaItem@@QEAAHKHW4_CL_ITEM@@AEAU_PROP_COMPAT_TABLE@@@Z; CWiaItem::GetPropCompatCategory(ulong,int,_CL_ITEM,_PROP_COMPAT_TABLE &)
0x180027d81  xor     r8d, r8d
0x180027d84  test    eax, eax
0x180027d86  jz      loc_180027F26
0x180027d8c  lea     eax, [rdx-1009h]
0x180027d92  cmp     eax, 1
0x180027d95  jbe     loc_180027F26
0x180027d9b  cmp     edx, 0C10h
0x180027da1  jz      loc_180027F26
0x180027da7  cmp     edx, 100Ch
0x180027dad  jz      loc_180027F26
0x180027db3  mov     edx, dword ptr [rbp+40h+hMem]
0x180027db6  cmp     edx, 1
0x180027db9  jz      short loc_180027DF0
0x180027dbb  mov     eax, dword ptr [rbp+40h+var_A0+8]
0x180027dbe  test    eax, eax
0x180027dc0  jz      loc_180027F26
0x180027dc6  cmp     eax, 1
0x180027dc9  jz      short loc_180027DE7
0x180027dcb  cmp     eax, 3
0x180027dce  jnz     short loc_180027DDA
0x180027dd0  cmp     [r12+0D0h], r12
0x180027dd8  jz      short loc_180027DE7
0x180027dda  lea     rcx, [r14+38h]
0x180027dde  mov     rax, [rcx]
0x180027de1  mov     rbx, [rax+50h]
0x180027de5  jmp     short loc_180027E5E
0x180027de7  lea     rcx, [r14+38h]
0x180027deb  mov     rbx, [rcx]
0x180027dee  jmp     short loc_180027E5E
0x180027df0  mov     edx, dword ptr [rbp+40h+var_90+4]
0x180027df3  cmp     edx, 4
0x180027df6  jz      short loc_180027E54
0x180027df8  cmp     edx, 8
0x180027dfb  jnz     short loc_180027E07
0x180027dfd  cmp     [r12+0D0h], r12
0x180027e05  jz      short loc_180027E54
0x180027e07  lea     rcx, [r14+38h]
0x180027e0b  cmp     edx, 6
0x180027e0e  jnz     short loc_180027E1D
0x180027e10  mov     rax, [rcx]
0x180027e13  cmp     [rax+60h], r8
0x180027e17  jz      loc_180027F26
0x180027e1d  cmp     edx, 5
0x180027e20  jnz     short loc_180027E31
0x180027e22  mov     rax, [rcx]
0x180027e25  cmp     [rax+58h], r8
0x180027e29  jz      loc_180027F26
0x180027e2f  jmp     short loc_180027E44
0x180027e31  cmp     edx, 6
0x180027e34  jnz     short loc_180027E3F
0x180027e36  mov     rax, [rcx]
0x180027e39  mov     rbx, [rax+60h]
0x180027e3d  jmp     short loc_180027E5B
0x180027e3f  cmp     edx, 5
0x180027e42  jnz     short loc_180027E4D
0x180027e44  mov     rax, [rcx]
0x180027e47  mov     rbx, [rax+58h]
0x180027e4b  jmp     short loc_180027E5B
0x180027e4d  mov     rbx, [rsp+140h+var_E0]
0x180027e52  jmp     short loc_180027E5B
0x180027e54  lea     rcx, [r14+38h]
  ... truncated ...
```
