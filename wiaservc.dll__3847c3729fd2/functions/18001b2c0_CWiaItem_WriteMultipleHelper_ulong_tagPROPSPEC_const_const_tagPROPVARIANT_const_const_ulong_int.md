# CWiaItem::WriteMultipleHelper(ulong,tagPROPSPEC const * const,tagPROPVARIANT const * const,ulong,int)

- ea: `0x18001b2c0`
- end: `0x18001bbbd`
- name: `?WriteMultipleHelper@CWiaItem@@QEAAJKQEBUtagPROPSPEC@@QEBUtagPROPVARIANT@@KH@Z`
- size: `2301`
- prototype: `__int64 __usercall@<rax>(CWiaItem *__hidden this@<rcx>, unsigned int@<edx>, const struct tagPROPSPEC *const@<r8>, const struct tagPROPVARIANT *const@<r9>, unsigned int, int)`
- caller_count: `2`
- callee_count: `30`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18006afc0`
- `0x180071e00`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000dd00`
- `0x180018ad8`
- `0x18001b2c0`
- `0x18001bbc4`
- `0x18001da54`
- `0x18001db34`
- `0x18001e3dc`
- `0x180028560`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x180030060`
- `0x180034658`
- `0x18005c6c4`
- `0x18005c7b0`
- `0x18005d87c`
- `0x18005dd2c`
- `0x180062bfc`
- `0x1800649a0`
- `0x18006ade0`
- `0x18006b040`
- `0x180077608`
- `0x180077614`
- `0x180078010`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x18001b644`
- `KERNEL32!lstrcmpW` at `0x18001b644`
- `KERNEL32!LocalFree` at `0x18001b8e8`
- `KERNEL32!LocalFree` at `0x18001bafb`
- `KERNEL32!LocalFree` at `0x18001bb0d`
- `KERNEL32!LocalFree` at `0x18001bb1f`
- `KERNEL32!LocalFree` at `0x18001b8e8`
- `KERNEL32!LocalFree` at `0x18001bafb`
- `KERNEL32!LocalFree` at `0x18001bb0d`
- `KERNEL32!LocalFree` at `0x18001bb1f`
- `KERNEL32!LocalAlloc` at `0x18001b4de`
- `KERNEL32!LocalAlloc` at `0x18001b4f3`
- `KERNEL32!LocalAlloc` at `0x18001b505`
- `KERNEL32!LocalAlloc` at `0x18001b4de`
- `KERNEL32!LocalAlloc` at `0x18001b4f3`
- `KERNEL32!LocalAlloc` at `0x18001b505`
- `api-ms-win-core-com-l1-1-0!FreePropVariantArray` at `0x18001baf2`
- `api-ms-win-core-com-l1-1-0!FreePropVariantArray` at `0x18001baf2`

## string_xrefs

- `0x18001b2ec`: `CWiaItem::WriteMultipleHelper`
- `0x18001b381`: `CWiaItem::WriteMultipleHelper`
- `0x18001b3c8`: `CWiaItem::WriteMultipleHelper`
- `0x18001b3f3`: `CWiaItem::WriteMultipleHelper`
- `0x18001b48b`: `CWiaItem::WriteMultipleHelper`
- `0x18001b4b8`: `CWiaItem::WriteMultipleHelper`
- `0x18001b714`: `CWiaItem::WriteMultipleHelper`
- `0x18001b746`: `CWiaItem::WriteMultipleHelper`
- `0x18001b783`: `CWiaItem::WriteMultipleHelper`
- `0x18001b7b0`: `CWiaItem::WriteMultipleHelper`
- `0x18001b8ff`: `CWiaItem::WriteMultipleHelper`
- `0x18001b92a`: `CWiaItem::WriteMultipleHelper`
- `0x18001b94e`: `CWiaItem::WriteMultipleHelper`
- `0x18001b97d`: `CWiaItem::WriteMultipleHelper`
- `0x18001b9a8`: `CWiaItem::WriteMultipleHelper`
- `0x18001ba07`: `CWiaItem::WriteMultipleHelper`
- `0x18001ba42`: `CWiaItem::WriteMultipleHelper`
- `0x18001ba6d`: `CWiaItem::WriteMultipleHelper`
- `0x18001bab0`: `CWiaItem::WriteMultipleHelper`
- `0x18001badb`: `CWiaItem::WriteMultipleHelper`
- `0x18001b701`: `WriteMultiple: all values were optimimized away, write is no-op`
- `0x18001b72b`: `WriteMultiple: all values were optimimized away, write is no-op`
- `0x18001b372`: `ValidateDrvItemAccess failed`
- `0x18001b398`: `ValidateDrvItemAccess failed`
- `0x18001bb31`: `CWiaItem::WriteMultiple`
- `0x18001b47c`: `failed reading WIA_DPS_DOCUMENT_HANDLING_SELECT on root legacy A-AIT (0x%X)`
- `0x18001b4a4`: `failed reading WIA_DPS_DOCUMENT_HANDLING_SELECT on root legacy A-AIT (0x%X)`
- `0x18001b96e`: `couldn't make backup copy of properties`
- `0x18001b994`: `couldn't make backup copy of properties`
- `0x18001b93f`: `test write failed`
- `0x18001b965`: `test write failed`
- `0x18001b774`: `CheckPropertyAccess failed with 0x%X`
- `0x18001b79c`: `CheckPropertyAccess failed with 0x%X`

## pseudocode

```c
__int64 __fastcall CWiaItem::WriteMultipleHelper(
        CWiaItem *this,
        unsigned int a2,
        const struct tagPROPSPEC *const a3,
        const struct tagPROPVARIANT *const a4,
        unsigned int a5,
        int a6)
{
  CWiaItem *v6; // r14
  __int64 v7; // r13
  struct tagWiaTraceData_Type *v9; // rax
  char *v10; // rdx
  unsigned int v11; // r8d
  int inited; // edi
  __int64 v13; // rax
  int v14; // ecx
  BOOL v15; // ebx
  int v16; // r12d
  char *v17; // rbx
  void *v18; // rdx
  void **v19; // rax
  void *v20; // rdx
  __int64 v21; // rcx
  char *v22; // rbx
  void *v23; // rdx
  __int64 v25; // rax
  bool v26; // zf
  unsigned __int16 *v27; // rax
  char *v28; // rbx
  void *v29; // rdx
  void **v30; // rax
  void *v31; // rdx
  __int64 v32; // rcx
  PROPVARIANT *v33; // r12
  HLOCAL v34; // rax
  struct tagPROPSPEC *v35; // rbx
  CWiaPropStg **v36; // r15
  BOOL v37; // eax
  int v38; // ecx
  __int64 v39; // rdi
  __int64 v40; // r15
  int v41; // r9d
  unsigned int i; // edx
  const struct tagPROPVARIANT *v43; // rcx
  __int16 v44; // dx
  unsigned __int64 v45; // rax
  BSTR *v46; // rdx
  BSTR *pbstrVal; // r8
  signed __int64 v48; // rax
  __int64 v49; // rbx
  int v50; // eax
  char *v51; // rbx
  void *v52; // rdx
  void **v53; // rax
  void *v54; // rdx
  __int64 v55; // rcx
  char *v56; // rbx
  void *v57; // rdx
  void **v58; // rax
  void *v59; // rdx
  __int64 v60; // rcx
  CWiaPropStg *v61; // rcx
  HLOCAL v62; // rbx
  HLOCAL v63; // r8
  HLOCAL v64; // r8
  char *v65; // rbx
  void *v66; // rdx
  void **v67; // rax
  void *v68; // rdx
  __int64 v69; // rcx
  char *v70; // rbx
  void *v71; // rdx
  void **v72; // rax
  void *v73; // rdx
  __int64 v74; // rcx
  char *v75; // rbx
  void *v76; // rdx
  char *v77; // rbx
  void *v78; // rdx
  void **v79; // rax
  void *v80; // rdx
  __int64 v81; // rcx
  char *v82; // rbx
  void *v83; // rdx
  char *v84; // rbx
  void *v85; // rdx
  void **v86; // rax
  void *v87; // rdx
  __int64 v88; // rcx
  char *v89; // rbx
  void *v90; // rdx
  void **v91; // rax
  void *v92; // rdx
  __int64 v93; // rcx
  unsigned int lpMem; // [rsp+28h] [rbp-A9h]
  BOOL v95; // [rsp+48h] [rbp-89h]
  int v96; // [rsp+4Ch] [rbp-85h] BYREF
  int v97; // [rsp+50h] [rbp-81h]
  HLOCAL v98; // [rsp+58h] [rbp-79h]
  unsigned int v99; // [rsp+60h] [rbp-71h] BYREF
  HLOCAL v100; // [rsp+68h] [rbp-69h]
  HLOCAL hMem[3]; // [rsp+70h] [rbp-61h] BYREF
  _BYTE v102[144]; // [rsp+88h] [rbp-49h] BYREF
  unsigned int v104; // [rsp+130h] [rbp+5Fh]

  v6 = this;
  v7 = a2;
  v9 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaItem::WriteMultipleHelper");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v102, v10, v11, "CWiaItem::WriteMultipleHelper", lpMem, v9);
  inited = 0;
  if ( (unsigned int)v7 <= 0xAAAAAAA )
  {
    if ( !(_DWORD)v7 )
    {
LABEL_15:
      CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v102);
      return (unsigned int)inited;
    }
    v13 = *((_QWORD *)v6 + 26);
    v14 = *(_DWORD *)(v13 + 104);
    v97 = v14;
    v15 = v13 && v14 && *(_QWORD *)(v13 + 64);
    v16 = *((_DWORD *)v6 + 56);
    v95 = v15;
    if ( !v15 )
    {
      inited = ValidateWiaDrvItemAccess(*((struct CWiaDrvItem **)v6 + 22));
      if ( inited < 0 )
      {
        v17 = (char *)WiaTrace_TraceLog("ValidateDrvItemAccess failed");
        WriteDbgTraceErrorWI("CWiaItem::WriteMultipleHelper", v17);
        WiaTrcLib::Free((WiaTrcLib *)v17, v18);
        v19 = (void **)WiaTrace_Trace("ValidateDrvItemAccess failed");
LABEL_14:
        WiaTrace_ProcessTrace_Ex(v21, v20, (void *)"CWiaItem::WriteMultipleHelper", 1, v19);
        goto LABEL_15;
      }
      if ( !*((_DWORD *)v6 + 32) )
      {
        inited = CWiaItem::InitLazyProps(v6);
        if ( inited < 0 )
        {
          v22 = (char *)WiaTrace_TraceLog("InitLazyProps failed");
          WriteDbgTraceErrorWI("CWiaItem::WriteMultipleHelper", v22);
          WiaTrcLib::Free((WiaTrcLib *)v22, v23);
          v19 = (void **)WiaTrace_Trace("InitLazyProps failed");
          goto LABEL_14;
        }
      }
    }
    if ( !(unsigned int)CWiaItem::IsCompatMode(v6)
      || (v25 = *((_QWORD *)v6 + 26)) == 0
      || (v26 = *(_DWORD *)(v25 + 108) == 0, v27 = L"A-AIT", v26) )
    {
      v27 = L"AIT";
    }
    LogRWMultiple(0, v7, a3, a4, v27);
    v99 = 0;
    if ( v15 )
    {
      if ( v16 == 1 )
      {
        inited = CWiaItem::GetDocumentHandling(*((CWiaItem **)v6 + 26), &v99, 0);
        if ( inited < 0 )
        {
          v28 = (char *)WiaTrace_TraceLog("failed reading WIA_DPS_DOCUMENT_HANDLING_SELECT on root legacy A-AIT (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::WriteMultipleHelper", v28);
          WiaTrcLib::Free((WiaTrcLib *)v28, v29);
          v30 = (void **)WiaTrace_Trace(
                           "failed reading WIA_DPS_DOCUMENT_HANDLING_SELECT on root legacy A-AIT (0x%X)",
                           inited);
          WiaTrace_ProcessTrace_Ex(v32, v31, (void *)"CWiaItem::WriteMultipleHelper", 1, v30);
        }
      }
    }
    v33 = (PROPVARIANT *)LocalAlloc(0x40u, 24 * v7);
    v98 = LocalAlloc(0x40u, 16 * v7);
    v34 = LocalAlloc(0x40u, 24 * v7);
    v100 = v34;
    if ( !v33 || !v98 || !v34 )
    {
      v84 = (char *)WiaTrace_TraceLog("failed to allocate memory");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleHelper", v84);
      WiaTrcLib::Free((WiaTrcLib *)v84, v85);
      v86 = (void **)WiaTrace_Trace("failed to allocate memory");
      WiaTrace_ProcessTrace_Ex(v88, v87, (void *)"CWiaItem::WriteMultipleHelper", 1, v86);
      if ( !v33 )
      {
LABEL_99:
        if ( v100 )
          LocalFree(v100);
        if ( v98 )
          LocalFree(v98);
        if ( inited < 0 )
          ReportReadWriteMultipleError(inited, "CWiaItem::WriteMultiple", 0, 0, v7, a3);
        goto LABEL_15;
      }
LABEL_98:
      FreePropVariantArray(v7, v33);
      LocalFree(v33);
      goto LABEL_99;
    }
    v35 = (struct tagPROPSPEC *)v98;
    v104 = v7;
    memcpy_0(v98, a3, 16 * v7);
    memcpy_0(v100, a4, 24 * v7);
    memset_0(v33, 0, 24 * v7);
    v36 = (CWiaPropStg **)((char *)v6 + 216);
    if ( (*(int (__fastcall **)(_QWORD, _QWORD, const struct tagPROPSPEC *const, PROPVARIANT *))(***((_QWORD ***)v6 + 27)
                                                                                               + 24LL))(
           **((_QWORD **)v6 + 27),
           (unsigned int)v7,
           a3,
           v33) < 0 )
    {
      v50 = v7;
    }
    else
    {
      v37 = v95;
      v38 = v97;
      if ( v95 || v97 != 1 )
      {
        v39 = 0;
        LODWORD(hMem[0]) = 0;
        v96 = 0;
        v40 = 0;
        while ( 1 )
        {
          v41 = 1;
          if ( v37 && v38 == 1 )
          {
            for ( i = 0; i < 2; ++i )
            {
              if ( *((_DWORD *)&qword_18009F650 + (int)i) == a3[v40].propid )
              {
                v41 = 0;
                break;
              }
            }
          }
          v43 = a4;
          v44 = (__int16)v33[3 * v40];
          if ( v44 == a4[v40].vt )
          {
            if ( v41 )
            {
              v45 = (unsigned __int64)v33[3 * v40] - *(_QWORD *)&a4[v40].vt;
              if ( !v45 )
              {
                v45 = (unsigned __int64)v33[3 * v40 + 1] - a4[v40].hVal.QuadPart;
                if ( !v45 )
                  v45 = (_BYTE *)v33[3 * v40 + 2] - a4[v40].bstrblobVal.pData;
              }
              if ( !v45 )
                break;
              if ( v44 == 8 )
              {
                if ( !lstrcmpW((LPCWSTR)v33[3 * v40 + 1], a4[v40].bstrVal) )
                  break;
                v43 = a4;
              }
              if ( LOWORD(v33[3 * v40]) == 72 )
              {
                v46 = (BSTR *)v33[3 * v40 + 1];
                pbstrVal = v43[v40].pbstrVal;
                v48 = (char *)*v46 - (char *)*pbstrVal;
                if ( *v46 == *pbstrVal )
                  v48 = (char *)v46[1] - (char *)pbstrVal[1];
                if ( !v48 )
                  break;
              }
            }
          }
          v39 = (unsigned int)(v39 + 1);
          LODWORD(hMem[0]) = v39;
LABEL_56:
          v37 = v95;
          ++v40;
          ++v96;
          v38 = v97;
          if ( v96 >= (unsigned int)v7 )
          {
            v6 = this;
            v35 = (struct tagPROPSPEC *)v98;
            v36 = (CWiaPropStg **)((char *)this + 216);
            goto LABEL_58;
          }
        }
        if ( v96 != (_DWORD)v7 - 1 )
        {
          v49 = (unsigned int)(v7 - v96 - 1);
          memmove_0((char *)v100 + 24 * v39, (char *)v100 + 24 * v39 + 24, 24 * v49);
          memmove_0((char *)v98 + 16 * v39, (char *)v98 + 16 * v39 + 16, 16 * v49);
          v39 = LODWORD(hMem[0]);
        }
        --v104;
        goto LABEL_56;
      }
LABEL_58:
      v50 = v104;
      if ( !v104 )
      {
        v51 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                        0,
                        0,
                        "WriteMultiple: all values were optimimized away, write is no-op");
        WriteDbgTraceInfoWI("CWiaItem::WriteMultipleHelper", v51);
        WiaTrcLib::Free((WiaTrcLib *)v51, v52);
        v53 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                         0,
                         0,
                         "WriteMultiple: all values were optimimized away, write is no-op");
        WiaTrace_ProcessTrace_Ex(v55, v54, (void *)"CWiaItem::WriteMultipleHelper", 4, v53);
        inited = 0;
        goto LABEL_98;
      }
    }
    inited = CWiaPropStg::CheckPropertyAccess(*v36, 1, v50, v35);
    if ( inited < 0 )
    {
      v56 = (char *)WiaTrace_TraceLog("CheckPropertyAccess failed with 0x%X");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleHelper", v56);
      WiaTrcLib::Free((WiaTrcLib *)v56, v57);
      v58 = (void **)WiaTrace_Trace("CheckPropertyAccess failed with 0x%X", inited);
      WiaTrace_ProcessTrace_Ex(v60, v59, (void *)"CWiaItem::WriteMultipleHelper", 1, v58);
      goto LABEL_98;
    }
    inited = CWiaPropStg::Backup(*v36);
    if ( inited < 0 )
    {
      v75 = (char *)WiaTrace_TraceLog("couldn't make backup copy of properties");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleHelper", v75);
      WiaTrcLib::Free((WiaTrcLib *)v75, v76);
      v72 = (void **)WiaTrace_Trace("couldn't make backup copy of properties");
    }
    else
    {
      inited = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct tagPROPSPEC *, HLOCAL, unsigned int))(**(_QWORD **)*v36 + 32LL))(
                 *(_QWORD *)*v36,
                 v104,
                 v35,
                 v100,
                 a5);
      if ( inited >= 0 )
      {
        v61 = *v36;
        hMem[0] = 0;
        v96 = CWiaPropStg::NamesToPropIDs(v61, v104, v35, (struct tagPROPSPEC **)hMem);
        inited = v96;
        if ( v96 < 0 )
        {
          v65 = (char *)WiaTrace_TraceLog("conversion to PropIDs failed");
          WriteDbgTraceErrorWI("CWiaItem::WriteMultipleHelper", v65);
          WiaTrcLib::Free((WiaTrcLib *)v65, v66);
          v67 = (void **)WiaTrace_Trace("conversion to PropIDs failed");
          WiaTrace_ProcessTrace_Ex(v69, v68, (void *)"CWiaItem::WriteMultipleHelper", 1, v67);
        }
        else
        {
          v62 = hMem[0];
          if ( !v95 )
          {
            if ( a6 )
            {
              v64 = v98;
              if ( hMem[0] )
                v64 = hMem[0];
              inited = (*(__int64 (__fastcall **)(_QWORD, CWiaItem *, _QWORD, _QWORD, HLOCAL, __int64))(**((_QWORD **)v6 + 19) + 384LL))(
                         *((_QWORD *)v6 + 19),
                         v6,
                         0,
                         v104,
                         v64,
                         (__int64)v6 + 160);
            }
            else
            {
              LOCK_WIA_DEVICE::LOCK_WIA_DEVICE((LOCK_WIA_DEVICE *)hMem, v6, &v96, 0);
              inited = v96;
              if ( v96 >= 0 )
              {
                v63 = v98;
                if ( v62 )
                  v63 = v62;
                inited = (*(__int64 (__fastcall **)(_QWORD, CWiaItem *, _QWORD, _QWORD, HLOCAL, __int64))(**((_QWORD **)v6 + 19) + 384LL))(
                           *((_QWORD *)v6 + 19),
                           v6,
                           0,
                           v104,
                           v63,
                           (__int64)v6 + 160);
              }
              LOCK_WIA_DEVICE::~LOCK_WIA_DEVICE((LOCK_WIA_DEVICE *)hMem);
            }
          }
          if ( v62 )
            LocalFree(v62);
        }
        v36 = (CWiaPropStg **)((char *)v6 + 216);
LABEL_83:
        if ( inited < 0 )
          goto LABEL_89;
        if ( v95 )
          inited = CWiaItem::WriteMultipleToDAIT(
                     (CWiaItem **)v6,
                     v104,
                     (const struct tagPROPSPEC *const)v98,
                     (const struct tagPROPVARIANT *const)v100,
                     a5,
                     &v99);
        if ( inited < 0 )
        {
LABEL_89:
          if ( (int)CWiaPropStg::Undo(*v36) < 0 )
          {
            v82 = (char *)WiaTrace_TraceLog("Undo() failed, could not restore invalid properties to their original values");
            WriteDbgTraceErrorWI("CWiaItem::WriteMultipleHelper", v82);
            WiaTrcLib::Free((WiaTrcLib *)v82, v83);
            v79 = (void **)WiaTrace_Trace("Undo() failed, could not restore invalid properties to their original values");
            goto LABEL_91;
          }
        }
        else if ( (int)CWiaPropStg::ReleaseBackups(*v36) < 0 )
        {
          v77 = (char *)WiaTrace_TraceLog("ReleaseBackups failed, continuing anyway...");
          WriteDbgTraceErrorWI("CWiaItem::WriteMultipleHelper", v77);
          WiaTrcLib::Free((WiaTrcLib *)v77, v78);
          v79 = (void **)WiaTrace_Trace("ReleaseBackups failed, continuing anyway...");
LABEL_91:
          WiaTrace_ProcessTrace_Ex(v81, v80, (void *)"CWiaItem::WriteMultipleHelper", 1, v79);
        }
        if ( inited >= 0 && v95 && v97 == 2 && v6 != *((CWiaItem **)v6 + 26) )
          CWiaItem::UpdateManagedAAITProperties(v6, v99);
        goto LABEL_98;
      }
      v70 = (char *)WiaTrace_TraceLog("test write failed");
      WriteDbgTraceErrorWI("CWiaItem::WriteMultipleHelper", v70);
      WiaTrcLib::Free((WiaTrcLib *)v70, v71);
      v72 = (void **)WiaTrace_Trace("test write failed");
    }
    WiaTrace_ProcessTrace_Ex(v74, v73, (void *)"CWiaItem::WriteMultipleHelper", 1, v72);
    goto LABEL_83;
  }
  v89 = (char *)WiaTrace_TraceLog("Invalid cpspec argument (%u) (E_INVALIDARG)");
  WriteDbgTraceErrorWI("CWiaItem::WriteMultipleHelper", v89);
  WiaTrcLib::Free((WiaTrcLib *)v89, v90);
  v91 = (void **)WiaTrace_Trace("Invalid cpspec argument (%u) (E_INVALIDARG)", v7);
  WiaTrace_ProcessTrace_Ex(v93, v92, (void *)"CWiaItem::WriteMultipleHelper", 1, v91);
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v102);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001b2c0  mov     rax, rsp
0x18001b2c3  mov     [rax+20h], r9
0x18001b2c7  mov     [rax+18h], r8
0x18001b2cb  mov     [rax+8], rcx
0x18001b2cf  push    rbp
0x18001b2d0  push    rbx
0x18001b2d1  push    rsi
0x18001b2d2  push    rdi
0x18001b2d3  push    r12
0x18001b2d5  push    r13
0x18001b2d7  push    r14
0x18001b2d9  push    r15
0x18001b2db  lea     rbp, [rax-4Fh]
0x18001b2df  sub     rsp, 0D8h
0x18001b2e6  mov     r14, rcx
0x18001b2e9  mov     r13d, edx
0x18001b2ec  lea     r12, aCwiaitemWritem; "CWiaItem::WriteMultipleHelper"
0x18001b2f3  mov     r15, r9
0x18001b2f6  mov     rcx, r12
0x18001b2f9  call    WiaTrace_Trace
0x18001b2fe  mov     r9, r12; char *
0x18001b301  mov     qword ptr [rsp+110h+lpMem+8], rax; struct tagWiaTraceData_Type *
0x18001b306  lea     rcx, [rbp+47h+var_90]; this
0x18001b30a  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18001b30f  xor     edi, edi
0x18001b311  cmp     r13d, 0AAAAAAAh
0x18001b318  ja      loc_18001BB54
0x18001b31e  test    r13d, r13d
0x18001b321  jz      loc_18001B3FF
0x18001b327  mov     rax, [r14+0D0h]
0x18001b32e  lea     esi, [rdi+1]
0x18001b331  mov     ecx, [rax+68h]
0x18001b334  mov     [rsp+110h+var_C8], ecx
0x18001b338  test    rax, rax
0x18001b33b  jz      short loc_18001B34B
0x18001b33d  test    ecx, ecx
0x18001b33f  jz      short loc_18001B34B
0x18001b341  cmp     [rax+40h], rdi
0x18001b345  jz      short loc_18001B34B
0x18001b347  mov     ebx, esi
0x18001b349  jmp     short loc_18001B34D
0x18001b34b  xor     ebx, ebx
0x18001b34d  mov     r12d, [r14+0E0h]
0x18001b354  mov     [rsp+110h+var_D0], ebx
0x18001b358  test    ebx, ebx
0x18001b35a  jnz     loc_18001B40F
0x18001b360  mov     rcx, [r14+0B0h]; struct CWiaDrvItem *
0x18001b367  call    ?ValidateWiaDrvItemAccess@@YAJPEAVCWiaDrvItem@@@Z; ValidateWiaDrvItemAccess(CWiaDrvItem *)
0x18001b36c  mov     edi, eax
0x18001b36e  test    eax, eax
0x18001b370  jns     short loc_18001B3A1
0x18001b372  lea     rcx, aValidatedrvite; "ValidateDrvItemAccess failed"
0x18001b379  call    WiaTrace_TraceLog
0x18001b37e  mov     rdx, rax; char *
0x18001b381  lea     rcx, aCwiaitemWritem; "CWiaItem::WriteMultipleHelper"
0x18001b388  mov     rbx, rax
0x18001b38b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001b390  mov     rcx, rbx; this
0x18001b393  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001b398  lea     rcx, aValidatedrvite; "ValidateDrvItemAccess failed"
0x18001b39f  jmp     short loc_18001B3E6
0x18001b3a1  cmp     dword ptr [r14+80h], 0
0x18001b3a9  jnz     short loc_18001B40F
0x18001b3ab  mov     rcx, r14; this
0x18001b3ae  call    ?InitLazyProps@CWiaItem@@QEAAJXZ; CWiaItem::InitLazyProps(void)
0x18001b3b3  mov     edi, eax
0x18001b3b5  test    eax, eax
0x18001b3b7  jns     short loc_18001B40F
0x18001b3b9  lea     rcx, aInitlazypropsF_0; "InitLazyProps failed"
0x18001b3c0  call    WiaTrace_TraceLog
0x18001b3c5  mov     rdx, rax; char *
0x18001b3c8  lea     rcx, aCwiaitemWritem; "CWiaItem::WriteMultipleHelper"
0x18001b3cf  mov     rbx, rax
0x18001b3d2  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001b3d7  mov     rcx, rbx; this
0x18001b3da  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001b3df  lea     rcx, aInitlazypropsF_0; "InitLazyProps failed"
0x18001b3e6  call    WiaTrace_Trace
0x18001b3eb  mov     r9d, esi; int
0x18001b3ee  mov     qword ptr [rsp+110h+lpMem], rax; lpMem
0x18001b3f3  lea     r8, aCwiaitemWritem; "CWiaItem::WriteMultipleHelper"
0x18001b3fa  call    WiaTrace_ProcessTrace_Ex
0x18001b3ff  lea     rcx, [rbp+47h+var_90]; this
0x18001b403  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18001b408  mov     eax, edi
0x18001b40a  jmp     loc_18001BBA9
0x18001b40f  mov     rcx, r14; this
0x18001b412  call    ?IsCompatMode@CWiaItem@@QEBAHXZ; CWiaItem::IsCompatMode(void)
0x18001b417  test    eax, eax
0x18001b419  jz      short loc_18001B434
0x18001b41b  mov     rax, [r14+0D0h]
0x18001b422  test    rax, rax
0x18001b425  jz      short loc_18001B434
0x18001b427  cmp     dword ptr [rax+6Ch], 0
0x18001b42b  lea     rax, aAAit; "A-AIT"
0x18001b432  jnz     short loc_18001B43B
0x18001b434  lea     rax, aAit; "AIT"
0x18001b43b  mov     r8, [rbp+47h+Src]; struct tagPROPSPEC *
0x18001b43f  mov     r9, r15; struct tagPROPVARIANT *
0x18001b442  mov     edx, r13d; unsigned int
0x18001b445  mov     qword ptr [rsp+110h+lpMem], rax; unsigned __int16 *
0x18001b44a  xor     ecx, ecx; int
0x18001b44c  call    ?LogRWMultiple@@YAXHKQEBUtagPROPSPEC@@QEBUtagPROPVARIANT@@PEAG@Z; LogRWMultiple(int,ulong,tagPROPSPEC const * const,tagPROPVARIANT const * const,ushort *)
0x18001b451  mov     [rbp+47h+var_B8], 0
0x18001b458  test    ebx, ebx
0x18001b45a  jz      short loc_18001B4C4
0x18001b45c  cmp     r12d, esi
0x18001b45f  jnz     short loc_18001B4C4
0x18001b461  mov     rcx, [r14+0D0h]; this
0x18001b468  lea     rdx, [rbp+47h+var_B8]; unsigned int *
0x18001b46c  xor     r8d, r8d; int
0x18001b46f  call    ?GetDocumentHandling@CWiaItem@@QEAAJAEAKH@Z; CWiaItem::GetDocumentHandling(ulong &,int)
0x18001b474  mov     edi, eax
0x18001b476  test    eax, eax
0x18001b478  jns     short loc_18001B4C4
0x18001b47a  mov     edx, eax
0x18001b47c  lea     rcx, aFailedReadingW; "failed reading WIA_DPS_DOCUMENT_HANDLIN"...
0x18001b483  call    WiaTrace_TraceLog
0x18001b488  mov     rdx, rax; char *
0x18001b48b  lea     rcx, aCwiaitemWritem; "CWiaItem::WriteMultipleHelper"
0x18001b492  mov     rbx, rax
0x18001b495  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001b49a  mov     rcx, rbx; this
0x18001b49d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001b4a2  mov     edx, edi
0x18001b4a4  lea     rcx, aFailedReadingW; "failed reading WIA_DPS_DOCUMENT_HANDLIN"...
0x18001b4ab  call    WiaTrace_Trace
0x18001b4b0  mov     r9d, esi; int
0x18001b4b3  mov     qword ptr [rsp+110h+lpMem], rax; lpMem
0x18001b4b8  lea     r8, aCwiaitemWritem; "CWiaItem::WriteMultipleHelper"
0x18001b4bf  call    WiaTrace_ProcessTrace_Ex
0x18001b4c4  lea     r15, ds:0[r13*2]
0x18001b4cc  mov     ecx, 40h ; '@'; uFlags
0x18001b4d1  add     r15, r13
0x18001b4d4  mov     rbx, r13
0x18001b4d7  shl     r15, 3
0x18001b4db  mov     rdx, r15; uBytes
0x18001b4de  call    cs:__imp_LocalAlloc
0x18001b4e4  shl     rbx, 4
0x18001b4e8  mov     ecx, 40h ; '@'; uFlags
0x18001b4ed  mov     rdx, rbx; uBytes
0x18001b4f0  mov     r12, rax
0x18001b4f3  call    cs:__imp_LocalAlloc
0x18001b4f9  mov     rdx, r15; uBytes
0x18001b4fc  mov     ecx, 40h ; '@'; uFlags
0x18001b501  mov     [rbp+47h+var_C0], rax
0x18001b505  call    cs:__imp_LocalAlloc
0x18001b50b  mov     [rbp+47h+var_B0], rax
0x18001b50f  test    r12, r12
0x18001b512  jz      loc_18001BAA1
0x18001b518  cmp     [rbp+47h+var_C0], 0
0x18001b51d  jz      loc_18001BAA1
0x18001b523  test    rax, rax
0x18001b526  jz      loc_18001BAA1
0x18001b52c  mov     rdx, [rbp+47h+Src]; Src
0x18001b530  mov     r8, rbx; Size
0x18001b533  mov     rbx, [rbp+47h+var_C0]
0x18001b537  mov     rcx, rbx; void *
0x18001b53a  mov     [rbp+47h+arg_8], r13d
0x18001b53e  call    memcpy_0
0x18001b543  mov     rdx, [rbp+47h+arg_18]; Src
0x18001b547  mov     r8, r15; Size
0x18001b54a  mov     rcx, [rbp+47h+var_B0]; void *
0x18001b54e  call    memcpy_0
0x18001b553  mov     r8, r15; Size
0x18001b556  xor     edx, edx; Val
0x18001b558  mov     rcx, r12; void *
0x18001b55b  call    memset_0
0x18001b560  mov     r8, [rbp+47h+Src]
0x18001b564  lea     r15, [r14+0D8h]
0x18001b56b  mov     rax, [r15]
0x18001b56e  mov     r9, r12
0x18001b571  mov     edx, r13d
0x18001b574  mov     rcx, [rax]
0x18001b577  mov     rax, [rcx]
0x18001b57a  mov     rax, [rax+18h]
0x18001b57e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b583  test    eax, eax
0x18001b585  js      loc_18001B759
0x18001b58b  mov     eax, [rsp+110h+var_D0]
0x18001b58f  mov     ecx, [rsp+110h+var_C8]
0x18001b593  test    eax, eax
0x18001b595  jnz     short loc_18001B59F
0x18001b597  cmp     ecx, esi
0x18001b599  jz      loc_18001B6FA
0x18001b59f  xor     edi, edi
0x18001b5a1  mov     dword ptr [rbp+47h+hMem], edi
0x18001b5a4  mov     [rsp+110h+var_CC], edi
0x18001b5a8  test    r13d, r13d
0x18001b5ab  jz      loc_18001B6FA
0x18001b5b1  xor     r15d, r15d
0x18001b5b4  mov     r14, rbx
0x18001b5b7  mov     r9d, esi
0x18001b5ba  test    eax, eax
0x18001b5bc  jz      short loc_18001B5EF
0x18001b5be  cmp     ecx, esi
0x18001b5c0  jnz     short loc_18001B5EF
0x18001b5c2  xor     edx, edx
0x18001b5c4  mov     r8, r15
0x18001b5c7  add     r8, r8
0x18001b5ca  cmp     edx, 2
0x18001b5cd  jnb     short loc_18001B5EF
0x18001b5cf  mov     rax, [rbp+47h+Src]
0x18001b5d3  lea     r10, qword_18009F650
0x18001b5da  movsxd  rcx, edx
0x18001b5dd  mov     eax, [rax+r8*8+8]
0x18001b5e2  cmp     [r10+rcx*4], eax
0x18001b5e6  jz      short loc_18001B5EC
0x18001b5e8  add     edx, esi
0x18001b5ea  jmp     short loc_18001B5CA
0x18001b5ec  xor     r9d, r9d
0x18001b5ef  mov     rcx, [rbp+47h+arg_18]
0x18001b5f3  lea     rbx, [r15+r15*2]
0x18001b5f7  movzx   edx, word ptr [r12+rbx*8]
0x18001b5fc  cmp     dx, [rcx+rbx*8]
0x18001b600  jnz     loc_18001B6C8
0x18001b606  test    r9d, r9d
0x18001b609  jz      loc_18001B6C8
0x18001b60f  mov     rax, [r12+rbx*8]
0x18001b613  sub     rax, [rcx+rbx*8]
0x18001b617  jnz     short loc_18001B62F
0x18001b619  mov     rax, [r12+rbx*8+8]
0x18001b61e  sub     rax, [rcx+rbx*8+8]
0x18001b623  jnz     short loc_18001B62F
0x18001b625  mov     rax, [r12+rbx*8+10h]
0x18001b62a  sub     rax, [rcx+rbx*8+10h]
0x18001b62f  test    rax, rax
0x18001b632  jz      short loc_18001B679
0x18001b634  cmp     dx, 8
0x18001b638  jnz     short loc_18001B652
0x18001b63a  mov     rdx, [rcx+rbx*8+8]; lpString2
0x18001b63f  mov     rcx, [r12+rbx*8+8]; lpString1
0x18001b644  call    cs:__imp_lstrcmpW
0x18001b64a  test    eax, eax
0x18001b64c  jz      short loc_18001B679
0x18001b64e  mov     rcx, [rbp+47h+arg_18]
0x18001b652  cmp     word ptr [r12+rbx*8], 48h ; 'H'
0x18001b658  jnz     short loc_18001B6C8
0x18001b65a  mov     rdx, [r12+rbx*8+8]
0x18001b65f  mov     r8, [rcx+rbx*8+8]
0x18001b664  mov     rax, [rdx]
0x18001b667  sub     rax, [r8]
0x18001b66a  jnz     short loc_18001B674
0x18001b66c  mov     rax, [rdx+8]
0x18001b670  sub     rax, [r8+8]
0x18001b674  test    rax, rax
0x18001b677  jnz     short loc_18001B6C8
0x18001b679  mov     ecx, [rsp+110h+var_CC]
0x18001b67d  lea     eax, [r13-1]
0x18001b681  cmp     ecx, eax
0x18001b683  jz      short loc_18001B6C3
0x18001b685  mov     ebx, r13d
0x18001b688  lea     rax, [rdi+rdi*2]
0x18001b68c  sub     ebx, ecx
0x18001b68e  mov     rcx, [rbp+47h+var_B0]
0x18001b692  sub     ebx, esi
0x18001b694  lea     rcx, [rcx+rax*8]; void *
0x18001b698  lea     r8, [rbx+rbx*2]
0x18001b69c  shl     r8, 3; Size
0x18001b6a0  lea     rdx, [rcx+18h]; Src
0x18001b6a4  call    memmove_0
0x18001b6a9  add     rdi, rdi
0x18001b6ac  shl     rbx, 4
0x18001b6b0  mov     r8, rbx; Size
0x18001b6b3  lea     rcx, [r14+rdi*8]; void *
0x18001b6b7  lea     rdx, [rcx+10h]; Src
0x18001b6bb  call    memmove_0
0x18001b6c0  mov     edi, dword ptr [rbp+47h+hMem]
0x18001b6c3  dec     [rbp+47h+arg_8]
0x18001b6c6  jmp     short loc_18001B6CD
0x18001b6c8  add     edi, esi
0x18001b6ca  mov     dword ptr [rbp+47h+hMem], edi
0x18001b6cd  mov     ecx, [rsp+110h+var_CC]
0x18001b6d1  mov     eax, [rsp+110h+var_D0]
0x18001b6d5  add     ecx, esi
0x18001b6d7  inc     r15
0x18001b6da  mov     [rsp+110h+var_CC], ecx
0x18001b6de  cmp     ecx, r13d
0x18001b6e1  mov     ecx, [rsp+110h+var_C8]
0x18001b6e5  jb      loc_18001B5B7
0x18001b6eb  mov     r14, [rbp+47h+arg_0]
0x18001b6ef  mov     rbx, [rbp+47h+var_C0]
0x18001b6f3  lea     r15, [r14+0D8h]
0x18001b6fa  mov     eax, [rbp+47h+arg_8]
0x18001b6fd  test    eax, eax
0x18001b6ff  jnz     short loc_18001B75C
0x18001b701  lea     r8, aWritemultipleA; "WriteMultiple: all values were optimimi"...
0x18001b708  xor     edx, edx
0x18001b70a  xor     ecx, ecx
0x18001b70c  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001b711  mov     rdx, rax; char *
0x18001b714  lea     rcx, aCwiaitemWritem; "CWiaItem::WriteMultipleHelper"
0x18001b71b  mov     rbx, rax
0x18001b71e  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001b723  mov     rcx, rbx; this
0x18001b726  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001b72b  lea     r8, aWritemultipleA; "WriteMultiple: all values were optimimi"...
0x18001b732  xor     edx, edx
0x18001b734  xor     ecx, ecx
0x18001b736  call    WiaTrace_TraceWithSubCompTraceLevel
  ... truncated ...
```
