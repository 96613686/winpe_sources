# CWiaItem::InitializeWiaItem(int,int,CWiaItem *,IWiaPropertyStorage *,USDWrapper *,CWiaDrvItem *,IUnknown *)

- ea: `0x180023288`
- end: `0x180023b60`
- name: `?InitializeWiaItem@CWiaItem@@QEAAJHHPEAV1@PEAUIWiaPropertyStorage@@PEAVUSDWrapper@@PEAVCWiaDrvItem@@PEAUIUnknown@@@Z`
- size: `2264`
- prototype: `__int64 __usercall@<rax>(CWiaItem *__hidden this@<rcx>, int@<edx>, int@<r8d>, struct CWiaItem *@<r9>, struct IWiaPropertyStorage *, struct USDWrapper *, struct CWiaDrvItem *, struct IUnknown *)`
- caller_count: `5`
- callee_count: `29`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800453c0`
- `0x1800552bc`
- `0x18005e91c`
- `0x180060520`
- `0x180065eb4`

## callees

- `0x18000ac34`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000dd00`
- `0x18000f4fc`
- `0x180011a94`
- `0x180013bfc`
- `0x180017740`
- `0x1800185a0`
- `0x1800202b8`
- `0x180021224`
- `0x180022720`
- `0x180023288`
- `0x1800284dc`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x180033884`
- `0x180033cc0`
- `0x18003c550`
- `0x18005df28`
- `0x18005df4c`
- `0x18005e718`
- `0x1800651c4`
- `0x180078010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18002341e`
- `KERNEL32!LeaveCriticalSection` at `0x18002341e`
- `KERNEL32!GetLastError` at `0x1800237b1`
- `KERNEL32!GetLastError` at `0x1800237b1`
- `OLEAUT32!__imp_SysAllocString` at `0x180023921`
- `OLEAUT32!__imp_SysAllocString` at `0x180023921`
- `OLEAUT32!__imp_SysFreeString` at `0x1800234fc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800234fc`
- `ole32!PropVariantClear` at `0x180023995`
- `ole32!PropVariantClear` at `0x180023995`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800236f8`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800236f8`

## string_xrefs

- `0x1800239d5`: `not enough memory to create CWiaPropStg`
- `0x1800239fb`: `not enough memory to create CWiaPropStg`
- `0x18002349d`: `LinkToDrvItem failed`
- `0x1800234c3`: `LinkToDrvItem failed`
- `0x1800237c8`: `InitWiaManagedItemProperties failed`
- `0x1800237ee`: `InitWiaManagedItemProperties failed`

## pseudocode

```c
__int64 __fastcall CWiaItem::InitializeWiaItem(
        CWiaItem *this,
        DWORD a2,
        int a3,
        struct CWiaItem *a4,
        struct IWiaPropertyStorage *a5,
        struct USDWrapper *a6,
        struct CWiaDrvItem *a7,
        struct IUnknown *a8)
{
  char ***v11; // rax
  char *v12; // rdx
  __int64 v13; // r8
  int v14; // edi
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
  _DWORD *v25; // rdi
  _QWORD *v26; // r15
  bool v27; // zf
  int Storage; // esi
  char *v29; // rbx
  void *v30; // rdx
  void **v31; // rax
  void *v32; // rdx
  __int64 v33; // rcx
  OLECHAR *v34; // rcx
  char *v35; // rbx
  void *v36; // rdx
  IUnknown **v37; // rbx
  __int64 i; // rax
  signed int j; // r13d
  unsigned int v40; // edx
  CWiaPropStg *v41; // rcx
  char *v42; // rbx
  void *v43; // rdx
  BOOL v44; // ebx
  WCHAR *Buffer; // rax
  signed int LastError; // eax
  char *v47; // rbx
  void *v48; // rdx
  char *v49; // rbx
  void *v50; // rdx
  void **v51; // rax
  void *v52; // rdx
  __int64 v53; // rcx
  char *v54; // rbx
  void *v55; // rdx
  void **v56; // rax
  void *v57; // rdx
  __int64 v58; // rcx
  char *v59; // rbx
  void *v60; // rdx
  void **v61; // rax
  void *v62; // rdx
  __int64 v63; // rcx
  const wchar_t *v64; // rdi
  const wchar_t *v65; // rcx
  char *v66; // rbx
  void *v67; // rdx
  void **v68; // rax
  void *v69; // rdx
  __int64 v70; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+30h] [rbp-D0h] BYREF
  void *ppInterface; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cchReferencedDomainName[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR Name; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v77[4]; // [rsp+50h] [rbp-B0h] BYREF
  PROPVARIANT pvar[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v79; // [rsp+70h] [rbp-90h]
  _BYTE v80[80]; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int64 *v81; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v82; // [rsp+D8h] [rbp-28h] BYREF
  OLECHAR *psz; // [rsp+1D8h] [rbp+D8h]
  __int64 v84; // [rsp+1E0h] [rbp+E0h]
  __int64 v85; // [rsp+1E8h] [rbp+E8h]
  char v86; // [rsp+1F0h] [rbp+F0h]
  const unsigned __int64 *v87; // [rsp+200h] [rbp+100h] BYREF
  __int16 v88; // [rsp+208h] [rbp+108h] BYREF
  __int16 *v89; // [rsp+308h] [rbp+208h]
  __int64 v90; // [rsp+310h] [rbp+210h]
  __int64 v91; // [rsp+318h] [rbp+218h]
  char v92; // [rsp+320h] [rbp+220h]
  _QWORD v93[38]; // [rsp+330h] [rbp+230h] BYREF

  *(_QWORD *)cchReferencedDomainName = a5;
  ppInterface = a4;
  cchName = a2;
  v11 = (char ***)WiaTrace_Trace("CWiaItem::Initialize");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v80, v12, v13, (char **)"CWiaItem::InitializeWiaItem", lpMem, v11);
  if ( a6 && a4 && a7 )
  {
    if ( a8 )
    {
      v14 = CRIT_SECT::Lock((CWiaItem *)((char *)this + 256));
      v15 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      0,
                      0,
                      "CWiaItem %p, calling AddRef() on IUnknownInner %p...",
                      this,
                      a8);
      WriteDbgTraceInfoWI("CWiaItem::InitializeWiaItem", v15);
      WiaTrcLib::Free((WiaTrcLib *)v15, v16);
      v17 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       0,
                       0,
                       "CWiaItem %p, calling AddRef() on IUnknownInner %p...",
                       this,
                       a8);
      WiaTrace_ProcessTrace_Ex(v19, v18, (void *)"CWiaItem::InitializeWiaItem", 4, v17);
      *((_QWORD *)this + 23) = a8;
      ((void (__fastcall *)(struct IUnknown *))a8->lpVtbl->AddRef)(a8);
      v20 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      0,
                      0,
                      "CWiaItem %p, called AddRef() on IUnknownInner %p",
                      this,
                      a8);
      WriteDbgTraceInfoWI("CWiaItem::InitializeWiaItem", v20);
      WiaTrcLib::Free((WiaTrcLib *)v20, v21);
      v22 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       0,
                       0,
                       "CWiaItem %p, called AddRef() on IUnknownInner %p",
                       this,
                       a8);
      WiaTrace_ProcessTrace_Ex(v24, v23, (void *)"CWiaItem::InitializeWiaItem", 4, v22);
      if ( v14 )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 256));
    }
    v25 = (_DWORD *)((char *)this + 228);
    v26 = (_QWORD *)((char *)this + 176);
    *((_QWORD *)this + 22) = a7;
    *((_DWORD *)this + 56) = (a3 != 0) + 1;
    *((_DWORD *)this + 57) = cchName;
    (*(void (__fastcall **)(struct CWiaDrvItem *))(*(_QWORD *)a7 + 8LL))(a7);
    v27 = *((_DWORD *)this + 57) == 0;
    *((_QWORD *)this + 26) = ppInterface;
    *((_QWORD *)this + 19) = a6;
    if ( v27 )
      *(_QWORD *)(*v26 + 32LL) = a6;
    Storage = (*(__int64 (__fastcall **)(struct CWiaDrvItem *, CWiaItem *))(*(_QWORD *)a7 + 128LL))(a7, this);
    if ( Storage < 0 )
    {
      v29 = (char *)WiaTrace_TraceLog("LinkToDrvItem failed");
      WriteDbgTraceErrorWI("CWiaItem::InitializeWiaItem", v29);
      WiaTrcLib::Free((WiaTrcLib *)v29, v30);
      v31 = (void **)WiaTrace_Trace("LinkToDrvItem failed");
LABEL_11:
      WiaTrace_ProcessTrace_Ex(v33, v32, (void *)"CWiaItem::InitializeWiaItem", 1, v31);
      goto LABEL_67;
    }
    if ( !*v25 )
    {
      v34 = (OLECHAR *)*((_QWORD *)this + 24);
      if ( v34 )
      {
        SysFreeString(v34);
        *((_QWORD *)this + 24) = 0;
      }
      Storage = (*(__int64 (__fastcall **)(struct CWiaDrvItem *, char *))(*(_QWORD *)a7 + 40LL))(a7, (char *)this + 192);
      if ( Storage < 0 )
      {
        v35 = (char *)WiaTrace_TraceLog("unable to get driver item name");
        WriteDbgTraceErrorWI("CWiaItem::InitializeWiaItem", v35);
        WiaTrcLib::Free((WiaTrcLib *)v35, v36);
        v31 = (void **)WiaTrace_Trace("unable to get driver item name");
        goto LABEL_11;
      }
    }
    v37 = (IUnknown **)operator new(0x70u);
    if ( v37 )
    {
      for ( i = 0; i != 7; ++i )
      {
        v37[i] = 0;
        v37[i + 7] = 0;
      }
    }
    else
    {
      v37 = 0;
    }
    *((_QWORD *)this + 27) = v37;
    if ( v37 )
    {
      for ( j = 0; j < 3; ++j )
      {
        Storage = CWiaPropStg::CreateStorage(v37, j);
        if ( Storage < 0 )
        {
          v41 = (CWiaPropStg *)*((_QWORD *)this + 27);
          if ( v41 )
            CWiaPropStg::`scalar deleting destructor'(v41, v40);
          *((_QWORD *)this + 27) = 0;
          v42 = (char *)WiaTrace_TraceLog("PropertyStorage Initialize failed");
          WriteDbgTraceErrorWI("CWiaItem::InitializeWiaItem", v42);
          WiaTrcLib::Free((WiaTrcLib *)v42, v43);
          v31 = (void **)WiaTrace_Trace("PropertyStorage Initialize failed");
          goto LABEL_11;
        }
      }
      v27 = *v25 == 0;
      *((_DWORD *)this + 32) = 1;
      if ( v27 )
      {
        Storage = CWiaItem::InitWiaManagedItemProperties(this, *(struct IWiaPropertyStorage **)cchReferencedDomainName);
        if ( Storage < 0 )
        {
          v47 = (char *)WiaTrace_TraceLog("InitWiaManagedItemProperties failed");
          WriteDbgTraceErrorWI("CWiaItem::InitializeWiaItem", v47);
          WiaTrcLib::Free((WiaTrcLib *)v47, v48);
          v31 = (void **)WiaTrace_Trace("InitWiaManagedItemProperties failed");
          goto LABEL_11;
        }
        if ( *((CWiaItem **)this + 26) == this )
          Storage = CWiaItem::BuildWiaItemTree(this, *(struct IWiaPropertyStorage **)cchReferencedDomainName);
      }
      if ( Storage >= 0 && *((CWiaItem **)this + 26) == this && !(unsigned int)CWiaItem::IsLegacyDriver(this) )
      {
        v92 = 0;
        v90 = 128;
        v89 = &v88;
        v84 = 128;
        v88 = 0;
        v91 = 16;
        psz = (OLECHAR *)&v82;
        v85 = 16;
        v82 = 0;
        *(_OWORD *)v77 = 0;
        ppInterface = 0;
        v87 = &CSimpleStringBase<unsigned short>::`vftable';
        v81 = &CSimpleStringBase<unsigned short>::`vftable';
        v86 = 0;
        v77[0] = 1;
        v77[2] = 3112;
        Storage = CoGetCallContext(&IID_IServerSecurity, &ppInterface);
        if ( Storage >= 0 )
        {
          v44 = 0;
          if ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface) )
          {
            Storage = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
            v44 = Storage >= 0;
          }
          if ( !Storage )
          {
            cchName = 0;
            cchReferencedDomainName[0] = 0;
            if ( (unsigned int)GetCurrentUserAndDomain(0, &cchName, 0, cchReferencedDomainName) )
            {
              Storage = -2147418113;
            }
            else
            {
              Name = (LPWSTR)CSimpleStringBase<unsigned short>::GetBuffer(&v87, cchName);
              Buffer = (WCHAR *)CSimpleStringBase<unsigned short>::GetBuffer(&v81, cchReferencedDomainName[0]);
              if ( Name && Buffer )
              {
                if ( !(unsigned int)GetCurrentUserAndDomain(Name, &cchName, Buffer, cchReferencedDomainName) )
                {
                  LastError = GetLastError();
                  Storage = LastError;
                  if ( LastError > 0 )
                    Storage = (unsigned __int16)LastError | 0x80070000;
                }
              }
              else
              {
                Storage = -2147024882;
              }
            }
          }
          if ( v44 )
          {
            cchName = SafeCoRevertToSelf();
            if ( (cchName & 0x80000000) != 0 )
            {
              v49 = (char *)WiaTrace_TraceLog("SafeCoRevertToSelf failed (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::InitializeWiaItem", v49);
              WiaTrcLib::Free((WiaTrcLib *)v49, v50);
              Storage = cchName;
              v51 = (void **)WiaTrace_Trace("SafeCoRevertToSelf failed (0x%X)", cchName);
              WiaTrace_ProcessTrace_Ex(v53, v52, (void *)"CWiaItem::InitializeWiaItem", 1, v51);
            }
          }
          if ( Storage >= 0 )
          {
            CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v93, L"\\");
            CSimpleStringBase<unsigned short>::Concat(&v81, v93);
            v93[0] = &CSimpleStringBase<unsigned short>::`vftable';
            CSimpleStringBase<unsigned short>::DeleteStorage((__int64)v93);
            CSimpleStringBase<unsigned short>::Concat(&v81, &v87);
          }
        }
        if ( v86 )
        {
          Storage = -2147024882;
        }
        else if ( Storage >= 0 )
        {
          Name = L"User Name";
          Storage = wiasSetItemPropNames((struct IWiaItem *)this, 1, &v77[2], &Name);
          if ( Storage >= 0 )
          {
            v79 = 0;
            *(_OWORD *)pvar = 0;
            LOWORD(pvar[0]) = 8;
            pvar[1] = SysAllocString(psz);
            if ( pvar[1] )
            {
              cchName = 65545;
              Storage = wiasSetPropertyAttributes(
                          (struct IWiaItem *)this,
                          1,
                          (const struct tagPROPSPEC *)v77,
                          (__int64)&cchName,
                          (__int64)pvar);
              if ( Storage >= 0 )
                Storage = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *, PROPVARIANT *, int))(***((_QWORD ***)this + 27) + 32LL))(
                            **((_QWORD **)this + 27),
                            1,
                            v77,
                            pvar,
                            2);
            }
            else
            {
              Storage = -2147024882;
            }
            PropVariantClear(pvar);
          }
        }
        ATL::CComPtr<IWiaPropertyStorage>::~CComPtr<IWiaPropertyStorage>((__int64 *)&ppInterface);
        v81 = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage((__int64)&v81);
        v84 = 0;
        v87 = &CSimpleStringBase<unsigned short>::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage((__int64)&v87);
      }
    }
    else
    {
      v54 = (char *)WiaTrace_TraceLog("not enough memory to create CWiaPropStg");
      WriteDbgTraceErrorWI("CWiaItem::InitializeWiaItem", v54);
      WiaTrcLib::Free((WiaTrcLib *)v54, v55);
      v56 = (void **)WiaTrace_Trace("not enough memory to create CWiaPropStg");
      WiaTrace_ProcessTrace_Ex(v58, v57, (void *)"CWiaItem::InitializeWiaItem", 1, v56);
      Storage = -2147024882;
    }
  }
  else
  {
    v59 = (char *)WiaTrace_TraceLog("NULL input parameters");
    WriteDbgTraceErrorWI("CWiaItem::InitializeWiaItem", v59);
    WiaTrcLib::Free((WiaTrcLib *)v59, v60);
    v61 = (void **)WiaTrace_Trace("NULL input parameters");
    WiaTrace_ProcessTrace_Ex(v63, v62, (void *)"CWiaItem::InitializeWiaItem", 1, v61);
    Storage = -2147467261;
    v25 = (_DWORD *)((char *)this + 228);
    v26 = (_QWORD *)((char *)this + 176);
  }
LABEL_67:
  if ( !*v25 )
    *((_DWORD *)this + 32) = 0;
  if ( Storage >= 0 )
  {
    v64 = L"-";
    v65 = L"-";
    if ( *((_QWORD *)this + 24) )
      v65 = (const wchar_t *)*((_QWORD *)this + 24);
    v66 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                    1,
                    0,
                    "Item (%p, %S) with driver item (%p) successfully initialized",
                    this,
                    v65,
                    *v26);
    WriteDbgTraceInfoWI("CWiaItem::InitializeWiaItem", v66);
    WiaTrcLib::Free((WiaTrcLib *)v66, v67);
    if ( *((_QWORD *)this + 24) )
      v64 = (const wchar_t *)*((_QWORD *)this + 24);
    v68 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                     1,
                     0,
                     "Item (%p, %S) with driver item (%p) successfully initialized",
                     this,
                     v64,
                     *v26);
    WiaTrace_ProcessTrace_Ex(v70, v69, (void *)"CWiaItem::InitializeWiaItem", 4, v68);
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v80);
  return (unsigned int)Storage;
}

```

## disassembly

```asm
0x180023288  push    rbp
0x18002328a  push    rbx
0x18002328b  push    rsi
0x18002328c  push    rdi
0x18002328d  push    r12
0x18002328f  push    r13
0x180023291  push    r14
0x180023293  push    r15
0x180023295  lea     rbp, [rsp-378h]
0x18002329d  sub     rsp, 478h
0x1800232a4  mov     rax, cs:__security_cookie
0x1800232ab  xor     rax, rsp
0x1800232ae  mov     [rbp+3B0h+var_50], rax
0x1800232b5  mov     rax, [rbp+3B0h+arg_20]
0x1800232bc  mov     r14, rcx
0x1800232bf  mov     r13, [rbp+3B0h+arg_30]
0x1800232c6  lea     rcx, aCwiaitemInitia_0; "CWiaItem::Initialize"
0x1800232cd  mov     r15, [rbp+3B0h+arg_38]
0x1800232d4  mov     rdi, r9
0x1800232d7  mov     qword ptr [rsp+4B0h+cchReferencedDomainName], rax
0x1800232dc  mov     r12d, r8d
0x1800232df  mov     [rsp+4B0h+ppInterface], r9
0x1800232e4  mov     [rsp+4B0h+cchName], edx
0x1800232e8  call    WiaTrace_Trace
0x1800232ed  lea     r9, aCwiaitemInitia; "CWiaItem::InitializeWiaItem"
0x1800232f4  mov     [rsp+4B0h+var_488], rax; struct tagWiaTraceData_Type *
0x1800232f9  lea     rcx, [rbp+3B0h+var_430]; this
0x1800232fd  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180023302  mov     rsi, [rbp+3B0h+arg_28]
0x180023309  test    rsi, rsi
0x18002330c  jz      loc_180023A22
0x180023312  test    rdi, rdi
0x180023315  jz      loc_180023A22
0x18002331b  test    r13, r13
0x18002331e  jz      loc_180023A22
0x180023324  test    r15, r15
0x180023327  jz      loc_180023424
0x18002332d  lea     rcx, [r14+100h]; this
0x180023334  call    ?Lock@CRIT_SECT@@QEAAHXZ; CRIT_SECT::Lock(void)
0x180023339  mov     r9, r14
0x18002333c  mov     [rsp+4B0h+lpMem], r15
0x180023341  lea     r8, aCwiaitemPCalli; "CWiaItem %p, calling AddRef() on IUnkno"...
0x180023348  xor     edx, edx
0x18002334a  xor     ecx, ecx
0x18002334c  mov     edi, eax
0x18002334e  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180023353  mov     rdx, rax; char *
0x180023356  lea     rcx, aCwiaitemInitia; "CWiaItem::InitializeWiaItem"
0x18002335d  mov     rbx, rax
0x180023360  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180023365  mov     rcx, rbx; this
0x180023368  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002336d  mov     r9, r14
0x180023370  mov     [rsp+4B0h+lpMem], r15
0x180023375  lea     r8, aCwiaitemPCalli; "CWiaItem %p, calling AddRef() on IUnkno"...
0x18002337c  xor     edx, edx
0x18002337e  xor     ecx, ecx
0x180023380  call    WiaTrace_TraceWithSubCompTraceLevel
0x180023385  mov     r9d, 4; int
0x18002338b  mov     [rsp+4B0h+lpMem], rax; lpMem
0x180023390  lea     r8, aCwiaitemInitia; "CWiaItem::InitializeWiaItem"
0x180023397  call    WiaTrace_ProcessTrace_Ex
0x18002339c  mov     [r14+0B8h], r15
0x1800233a3  mov     rcx, r15
0x1800233a6  mov     rax, [r15]
0x1800233a9  mov     rax, [rax+8]
0x1800233ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233b2  mov     r9, r14
0x1800233b5  mov     [rsp+4B0h+lpMem], r15
0x1800233ba  lea     r8, aCwiaitemPCalle; "CWiaItem %p, called AddRef() on IUnknow"...
0x1800233c1  xor     edx, edx
0x1800233c3  xor     ecx, ecx
0x1800233c5  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800233ca  mov     rdx, rax; char *
0x1800233cd  lea     rcx, aCwiaitemInitia; "CWiaItem::InitializeWiaItem"
0x1800233d4  mov     rbx, rax
0x1800233d7  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800233dc  mov     rcx, rbx; this
0x1800233df  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800233e4  mov     r9, r14
0x1800233e7  mov     [rsp+4B0h+lpMem], r15
0x1800233ec  lea     r8, aCwiaitemPCalle; "CWiaItem %p, called AddRef() on IUnknow"...
0x1800233f3  xor     edx, edx
0x1800233f5  xor     ecx, ecx
0x1800233f7  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800233fc  mov     r9d, 4; int
0x180023402  mov     [rsp+4B0h+lpMem], rax; lpMem
0x180023407  lea     r8, aCwiaitemInitia; "CWiaItem::InitializeWiaItem"
0x18002340e  call    WiaTrace_ProcessTrace_Ex
0x180023413  test    edi, edi
0x180023415  jz      short loc_180023424
0x180023417  lea     rcx, [r14+100h]; lpCriticalSection
0x18002341e  call    cs:__imp_LeaveCriticalSection
0x180023424  neg     r12d
0x180023427  lea     rdi, [r14+0E4h]
0x18002342e  mov     r12d, 1
0x180023434  lea     r15, [r14+0B0h]
0x18002343b  sbb     eax, eax
0x18002343d  mov     [r15], r13
0x180023440  neg     eax
0x180023442  mov     rcx, r13
0x180023445  add     eax, r12d
0x180023448  mov     [r14+0E0h], eax
0x18002344f  mov     eax, [rsp+4B0h+cchName]
0x180023453  mov     [rdi], eax
0x180023455  mov     rax, [r13+0]
0x180023459  mov     rax, [rax+8]
0x18002345d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023462  cmp     dword ptr [rdi], 0
0x180023465  mov     rax, [rsp+4B0h+ppInterface]
0x18002346a  mov     [r14+0D0h], rax
0x180023471  mov     [r14+98h], rsi
0x180023478  jnz     short loc_180023481
0x18002347a  mov     rax, [r15]
0x18002347d  mov     [rax+20h], rsi
0x180023481  mov     rax, [r13+0]
0x180023485  mov     rdx, r14
0x180023488  mov     rcx, r13
0x18002348b  mov     rax, [rax+80h]
0x180023492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023497  mov     esi, eax
0x180023499  test    eax, eax
0x18002349b  jns     short loc_1800234E8
0x18002349d  lea     rcx, aLinktodrvitemF; "LinkToDrvItem failed"
0x1800234a4  call    WiaTrace_TraceLog
0x1800234a9  mov     rdx, rax; char *
0x1800234ac  lea     rcx, aCwiaitemInitia; "CWiaItem::InitializeWiaItem"
0x1800234b3  mov     rbx, rax
0x1800234b6  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800234bb  mov     rcx, rbx; this
0x1800234be  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800234c3  lea     rcx, aLinktodrvitemF; "LinkToDrvItem failed"
0x1800234ca  call    WiaTrace_Trace
0x1800234cf  mov     r9d, r12d; int
0x1800234d2  mov     [rsp+4B0h+lpMem], rax; lpMem
0x1800234d7  lea     r8, aCwiaitemInitia; "CWiaItem::InitializeWiaItem"
0x1800234de  call    WiaTrace_ProcessTrace_Ex
0x1800234e3  jmp     loc_180023A81
0x1800234e8  cmp     dword ptr [rdi], 0
0x1800234eb  jnz     short loc_180023554
0x1800234ed  lea     rbx, [r14+0C0h]
0x1800234f4  mov     rcx, [rbx]; bstrString
0x1800234f7  test    rcx, rcx
0x1800234fa  jz      short loc_180023509
0x1800234fc  call    cs:__imp_SysFreeString
0x180023502  mov     qword ptr [rbx], 0
0x180023509  mov     rax, [r13+0]
0x18002350d  mov     rdx, rbx
0x180023510  mov     rcx, r13
0x180023513  mov     rax, [rax+28h]
0x180023517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002351c  mov     esi, eax
0x18002351e  test    eax, eax
0x180023520  jns     short loc_180023554
0x180023522  lea     rcx, aUnableToGetDri; "unable to get driver item name"
0x180023529  call    WiaTrace_TraceLog
0x18002352e  mov     rdx, rax; char *
0x180023531  lea     rcx, aCwiaitemInitia; "CWiaItem::InitializeWiaItem"
0x180023538  mov     rbx, rax
0x18002353b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180023540  mov     rcx, rbx; this
0x180023543  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180023548  lea     rcx, aUnableToGetDri; "unable to get driver item name"
0x18002354f  jmp     loc_1800234CA
0x180023554  mov     ecx, 70h ; 'p'; Size
0x180023559  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002355e  mov     rbx, rax
0x180023561  test    rax, rax
0x180023564  jz      short loc_180023584
0x180023566  xor     eax, eax
0x180023568  mov     qword ptr [rbx+rax*8], 0
0x180023570  mov     qword ptr [rbx+rax*8+38h], 0
0x180023579  add     rax, r12
0x18002357c  cmp     rax, 7
0x180023580  jnz     short loc_180023568
0x180023582  jmp     short loc_180023586
0x180023584  xor     ebx, ebx
0x180023586  mov     [r14+0D8h], rbx
0x18002358d  test    rbx, rbx
0x180023590  jz      loc_1800239D5
0x180023596  xor     r13d, r13d
0x180023599  mov     edx, r13d; unsigned int
0x18002359c  mov     rcx, rbx; this
0x18002359f  call    ?CreateStorage@CWiaPropStg@@AEAAJK@Z; CWiaPropStg::CreateStorage(ulong)
0x1800235a4  mov     esi, eax
0x1800235a6  test    eax, eax
0x1800235a8  js      short loc_1800235B7
0x1800235aa  add     r13d, r12d
0x1800235ad  cmp     r13d, 3
0x1800235b1  jl      short loc_180023599
0x1800235b3  test    eax, eax
0x1800235b5  jns     short loc_180023605
0x1800235b7  mov     rcx, [r14+0D8h]; this
0x1800235be  test    rcx, rcx
0x1800235c1  jz      short loc_1800235C8
0x1800235c3  call    ??_GCWiaPropStg@@QEAAPEAXI@Z; CWiaPropStg::`scalar deleting destructor'(uint)
0x1800235c8  lea     rcx, aPropertystorag; "PropertyStorage Initialize failed"
0x1800235cf  mov     qword ptr [r14+0D8h], 0
0x1800235da  call    WiaTrace_TraceLog
0x1800235df  mov     rdx, rax; char *
0x1800235e2  lea     rcx, aCwiaitemInitia; "CWiaItem::InitializeWiaItem"
0x1800235e9  mov     rbx, rax
0x1800235ec  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800235f1  mov     rcx, rbx; this
0x1800235f4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800235f9  lea     rcx, aPropertystorag; "PropertyStorage Initialize failed"
0x180023600  jmp     loc_1800234CA
0x180023605  cmp     dword ptr [rdi], 0
0x180023608  mov     [r14+80h], r12d
0x18002360f  jnz     short loc_180023641
0x180023611  mov     rbx, qword ptr [rsp+4B0h+cchReferencedDomainName]
0x180023616  mov     rcx, r14; this
0x180023619  mov     rdx, rbx; struct IWiaPropertyStorage *
0x18002361c  call    ?InitWiaManagedItemProperties@CWiaItem@@QEAAJPEAUIWiaPropertyStorage@@@Z; CWiaItem::InitWiaManagedItemProperties(IWiaPropertyStorage *)
0x180023621  mov     esi, eax
0x180023623  test    eax, eax
0x180023625  js      loc_1800237C8
0x18002362b  cmp     [r14+0D0h], r14
0x180023632  jnz     short loc_180023641
0x180023634  mov     rdx, rbx; struct IWiaPropertyStorage *
0x180023637  mov     rcx, r14; this
0x18002363a  call    ?BuildWiaItemTree@CWiaItem@@QEAAJPEAUIWiaPropertyStorage@@@Z; CWiaItem::BuildWiaItemTree(IWiaPropertyStorage *)
0x18002363f  mov     esi, eax
0x180023641  test    esi, esi
0x180023643  js      loc_180023A81
0x180023649  cmp     [r14+0D0h], r14
0x180023650  jnz     loc_180023A81
0x180023656  mov     rcx, r14; this
0x180023659  call    ?IsLegacyDriver@CWiaItem@@QEAAHXZ; CWiaItem::IsLegacyDriver(void)
0x18002365e  test    eax, eax
0x180023660  jnz     loc_180023A81
0x180023666  mov     edx, 80h
0x18002366b  mov     [rbp+3B0h+var_190], 0
0x180023672  lea     rax, [rbp+3B0h+var_2A8]
0x180023679  mov     [rbp+3B0h+var_1A0], rdx
0x180023680  mov     [rbp+3B0h+var_1A8], rax
0x180023687  lea     rbx, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18002368e  xor     eax, eax
0x180023690  mov     [rbp+3B0h+var_2D0], rdx
0x180023697  lea     ecx, [rdx-70h]
0x18002369a  mov     [rbp+3B0h+var_2A8], ax
0x1800236a1  lea     rax, [rbp+3B0h+var_3D8]
0x1800236a5  mov     [rbp+3B0h+var_198], rcx
0x1800236ac  mov     [rbp+3B0h+psz], rax
0x1800236b3  lea     rdx, [rsp+4B0h+ppInterface]; ppInterface
0x1800236b8  xor     eax, eax
0x1800236ba  mov     [rbp+3B0h+var_2C8], rcx
0x1800236c1  xorps   xmm0, xmm0
0x1800236c4  mov     [rbp+3B0h+var_3D8], ax
0x1800236c8  movups  xmmword ptr [rsp+4B0h+var_460], xmm0
0x1800236cd  lea     rcx, IID_IServerSecurity; riid
0x1800236d4  mov     [rsp+4B0h+ppInterface], rax
0x1800236d9  mov     [rbp+3B0h+var_2B0], rbx
0x1800236e0  mov     [rbp+3B0h+var_3E0], rbx
0x1800236e4  mov     [rbp+3B0h+var_2C0], 0
0x1800236eb  mov     [rsp+4B0h+var_460], r12d
0x1800236f0  mov     [rsp+4B0h+var_460+8], 0C28h
0x1800236f8  call    cs:__imp_CoGetCallContext
0x1800236fe  mov     esi, eax
0x180023700  mov     r13d, 8007000Eh
0x180023706  test    eax, eax
0x180023708  js      loc_1800238BD
0x18002370e  mov     rcx, [rsp+4B0h+ppInterface]
0x180023713  xor     ebx, ebx
0x180023715  mov     rax, [rcx]
0x180023718  mov     rax, [rax+30h]
0x18002371c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023721  test    eax, eax
0x180023723  jnz     short loc_18002373E
0x180023725  mov     rcx, [rsp+4B0h+ppInterface]
0x18002372a  mov     rax, [rcx]
0x18002372d  mov     rax, [rax+20h]
0x180023731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023736  test    eax, eax
0x180023738  mov     esi, eax
0x18002373a  cmovns  ebx, r12d
0x18002373e  test    esi, esi
0x180023740  jnz     loc_180023804
0x180023746  lea     r9, [rsp+4B0h+cchReferencedDomainName]; cchReferencedDomainName
0x18002374b  mov     [rsp+4B0h+cchName], esi
0x18002374f  xor     r8d, r8d; ReferencedDomainName
0x180023752  mov     [rsp+4B0h+cchReferencedDomainName], esi
0x180023756  lea     rdx, [rsp+4B0h+cchName]; cchName
0x18002375b  xor     ecx, ecx; Name
0x18002375d  call    ?GetCurrentUserAndDomain@@YAHPEAGPEAK01@Z; GetCurrentUserAndDomain(ushort *,ulong *,ushort *,ulong *)
0x180023762  test    eax, eax
0x180023764  jnz     loc_1800237FF
0x18002376a  mov     edx, [rsp+4B0h+cchName]
0x18002376e  lea     rcx, [rbp+3B0h+var_2B0]
0x180023775  call    ?GetBuffer@?$CSimpleStringBase@G@@QEAAPEAG_K@Z; CSimpleStringBase<ushort>::GetBuffer(unsigned __int64)
0x18002377a  mov     edx, [rsp+4B0h+cchReferencedDomainName]
0x18002377e  lea     rcx, [rbp+3B0h+var_3E0]
0x180023782  mov     [rsp+4B0h+Name], rax
0x180023787  call    ?GetBuffer@?$CSimpleStringBase@G@@QEAAPEAG_K@Z; CSimpleStringBase<ushort>::GetBuffer(unsigned __int64)
0x18002378c  mov     rcx, [rsp+4B0h+Name]; Name
0x180023791  test    rcx, rcx
0x180023794  jz      short loc_1800237FA
0x180023796  test    rax, rax
0x180023799  jz      short loc_1800237FA
0x18002379b  lea     r9, [rsp+4B0h+cchReferencedDomainName]; cchReferencedDomainName
  ... truncated ...
```
