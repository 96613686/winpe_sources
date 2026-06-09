# CBinding::StartBinding(IUri *,IBindCtx *,_GUID const &,int,ushort * *,void * *)

- ea: `0x18002bc70`
- end: `0x18002d26f`
- name: `?StartBinding@CBinding@@QEAAJPEAUIUri@@PEAUIBindCtx@@AEBU_GUID@@HPEAPEAGPEAPEAX@Z`
- size: `5631`
- prototype: `__int64 __usercall@<rax>(CBinding *__hidden this@<rcx>, struct IUri *@<rdx>, struct IBindCtx *@<r8>, const struct _GUID *@<r9>, int, unsigned __int16 **, void **)`
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f604`

## callees

- `0x180008b2c`
- `0x18001db50`
- `0x18001e4d0`
- `0x18002bac4`
- `0x18002bc70`
- `0x18002d278`
- `0x18002d6a0`
- `0x18002debc`
- `0x18002e078`
- `0x18002e15c`
- `0x18002e300`
- `0x18002e34c`
- `0x18002e3ac`
- `0x180030e40`
- `0x180031480`
- `0x180048100`
- `0x18005aee4`
- `0x18005fa60`
- `0x180063690`
- `0x18006375c`
- `0x180063a40`
- `0x180068068`
- `0x180083bec`
- `0x1800a2600`
- `0x1800f5af4`
- `0x1801285e6`
- `0x1801285fe`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_DSA_InsertItem` at `0x18002c73a`
- `iertutil!__imp_DSA_InsertItem` at `0x18002c73a`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18002c10f`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18002c10f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c75b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c81b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ca73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cbdd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d148`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c75b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c81b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ca73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002cbdd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d148`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c097`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c711`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c097`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c711`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002c251`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002c251`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002be0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cc7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002be0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cc7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c128`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c860`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c889`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c128`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c860`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c889`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cef5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cf06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d166`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cef5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cf06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d166`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ce4c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ce4c`
- `OLEAUT32!__imp_SysStringLen` at `0x18002ce9b`
- `OLEAUT32!__imp_SysStringLen` at `0x18002ce9b`
- `api-ms-win-ole32-ie-l1-1-0!ReleaseStgMedium` at `0x18002bf54`
- `api-ms-win-ole32-ie-l1-1-0!ReleaseStgMedium` at `0x18002bf54`

## string_xrefs

- `0x18002cc55`: `onecoreuap\inetcore\urlmon\trans\common\ctransaction.cpp`

## pseudocode

```c
__int64 __fastcall CBinding::StartBinding(
        CBinding *this,
        struct IUri *a2,
        struct IBindCtx *a3,
        struct _GUID *a4,
        int a5,
        unsigned __int16 **a6,
        void **a7)
{
  int v7; // r12d
  int COInetSession; // esi
  _QWORD *v14; // r15
  int v15; // edi
  _QWORD *v16; // rax
  _QWORD *v17; // rsi
  struct IUri *v18; // rcx
  __int64 (__fastcall ***v19)(__int64, GUID *, __int128 *); // rdi
  __int64 (__fastcall ***v20)(__int64, GUID *, __int128 *); // r15
  unsigned int v21; // eax
  OLECHAR *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  void *v25; // rcx
  void *v26; // rcx
  _DWORD *v27; // r15
  __int64 (__fastcall ***v28)(_QWORD, GUID *, __int128 *); // rcx
  int v29; // eax
  char *v30; // r8
  int v31; // r12d
  int v32; // eax
  int v33; // eax
  _QWORD *v34; // rsi
  unsigned int v35; // edi
  bool v36; // cf
  void **v37; // r12
  unsigned int v38; // edi
  __int64 (__fastcall **v39)(_QWORD, _QWORD, _QWORD); // rax
  EdgeTransaction *v40; // rax
  const char *v41; // r9
  EdgeTransaction *v42; // r12
  int v43; // eax
  __int64 v44; // rcx
  int (__fastcall ***v45)(_QWORD, GUID *, __int128 *); // rcx
  void **v46; // xmm0_8
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rax
  int v50; // ecx
  int v51; // edx
  struct IUriVtbl *v52; // rax
  int v53; // eax
  __int64 v54; // rcx
  int v55; // ecx
  int v56; // edx
  int v57; // ecx
  unsigned int v58; // edx
  int v59; // ecx
  int v60; // edx
  int v61; // ecx
  int v62; // r15d
  __int64 v63; // rax
  unsigned int v64; // edi
  const OLECHAR *v65; // rdx
  __int16 v66; // r8
  __int64 v67; // rcx
  const OLECHAR *v68; // rdx
  const OLECHAR *v69; // rcx
  int v70; // edx
  EdgeTransaction *v71; // rax
  HDSA *GlobalTransactionManager; // rdi
  int v73; // edi
  int v74; // esi
  struct COInetSession *v75; // rdi
  EdgeTransaction *v76; // rcx
  char *v77; // r12
  struct COInetSession *v78; // xmm6_8
  unsigned __int8 *v79; // rax
  unsigned __int8 *v80; // rdi
  CTransData *v81; // rax
  unsigned int v82; // edx
  CTransData *v83; // rsi
  struct CTransaction *v84; // rdx
  unsigned int v85; // r9d
  void *v86; // r9
  __int64 v87; // rdx
  __int64 v88; // rsi
  __int64 v89; // rdi
  CTransData *v90; // rcx
  __int64 (__fastcall **v91)(__int64, GUID *, __int128 *); // rax
  int v92; // eax
  __int64 v93; // rdx
  void *v94; // rdi
  char *v95; // rax
  struct COInetSession *v96; // rdi
  struct COInetSession *v97; // rcx
  __int64 v98; // rax
  __int64 v99; // rcx
  int v100; // edi
  __int64 v101; // r14
  __int64 v102; // rdi
  __int64 v103; // rcx
  int v104; // ecx
  int (__fastcall ***v105)(_QWORD, GUID *, void **); // rcx
  int v106; // eax
  __int128 *v107; // rax
  __int128 v108; // xmm0
  struct IBindCtxVtbl *lpVtbl; // rax
  OLECHAR *v110; // rcx
  const unsigned __int16 *v111; // rdx
  struct COInetSession *v112; // rdi
  int v113; // eax
  int v114; // eax
  CBinding *v115; // rcx
  __int64 v116; // r12
  void **v117; // rcx
  int v118; // ecx
  int v119; // ecx
  int v120; // ecx
  LPCOLESTR lpsz; // [rsp+20h] [rbp-C1h]
  LPCOLESTR lpsza; // [rsp+20h] [rbp-C1h]
  unsigned int v123; // [rsp+40h] [rbp-A1h] BYREF
  int v124; // [rsp+44h] [rbp-9Dh]
  struct COInetSession *v125; // [rsp+50h] [rbp-91h] BYREF
  unsigned int Data1; // [rsp+58h] [rbp-89h]
  void *Buf1; // [rsp+60h] [rbp-81h] BYREF
  void **v128; // [rsp+70h] [rbp-71h] BYREF
  int v129; // [rsp+78h] [rbp-69h]
  unsigned __int16 **v130; // [rsp+80h] [rbp-61h]
  __int128 v131; // [rsp+88h] [rbp-59h] BYREF
  struct IBindCtx *v132; // [rsp+98h] [rbp-49h]
  void *v133; // [rsp+A0h] [rbp-41h]
  __int128 pitem; // [rsp+A8h] [rbp-39h] BYREF
  IID rclsid; // [rsp+B8h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]

  v7 = 0;
  v130 = a6;
  v128 = a7;
  Buf1 = a4;
  v124 = 0;
  COInetSession = -2147467259;
  *(_QWORD *)&pitem = 0;
  if ( !a3
    || (COInetSession = ((__int64 (__fastcall *)(struct IBindCtx *, const wchar_t *, __int128 *))a3->lpVtbl->GetObjectParam)(
                          a3,
                          L"_BSCB_Holder_",
                          &pitem),
        COInetSession < 0)
    || (COInetSession = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))pitem)(
                          pitem,
                          &IID_IBindStatusCallback,
                          (char *)this + 128),
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)pitem + 16LL))(pitem),
        COInetSession < 0) )
  {
    *((_QWORD *)this + 16) = 0;
    goto LABEL_4;
  }
  if ( !*((_QWORD *)this + 16) )
  {
    COInetSession = -2147024809;
    goto LABEL_77;
  }
  *((_DWORD *)this + 68) = a5;
  if ( a5 )
  {
    v107 = (__int128 *)*((_QWORD *)this + 42);
    *((_DWORD *)this + 82) |= 0x2000000u;
    *((_QWORD *)this + 51) = a4;
    v108 = *v107;
    lpVtbl = a3->lpVtbl;
    pitem = v108;
    LODWORD(pitem) = 16;
    COInetSession = ((__int64 (__fastcall *)(struct IBindCtx *, __int128 *))lpVtbl->GetBindOptions)(a3, &pitem);
    if ( COInetSession < 0 )
      goto LABEL_77;
    *(_OWORD *)*((_QWORD *)this + 42) = pitem;
  }
  v14 = (_QWORD *)((char *)this + 400);
  *((_QWORD *)this + 50) = 0;
  v15 = ((__int64 (__fastcall *)(struct IBindCtx *, GUID *, char *))a3->lpVtbl->QueryInterface)(
          a3,
          &IID_IAsyncBindCtx,
          (char *)this + 400);
  if ( v15 )
  {
    v15 = 0;
    *v14 = 0;
  }
  ((void (__fastcall *)(struct IBindCtx *))a3->lpVtbl->AddRef)(a3);
  if ( !*v14 )
  {
    v16 = operator new(0x48u);
    v17 = v16;
    if ( v16 )
    {
      *v16 = &CBindCtx::`vftable'{for `IBindCtx'};
      v16[1] = &CBindCtx::`vftable'{for `IMarshal'};
      *((_DWORD *)v16 + 4) = 1;
      v16[4] = a3;
      ((void (__fastcall *)(struct IBindCtx *))a3->lpVtbl->AddRef)(a3);
      v17[3] = 0;
      *((_DWORD *)v17 + 14) = GetCurrentThreadId();
      v17[5] = 0;
      v17[6] = 0;
      v17[8] = 0;
      _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
      *v14 = v17;
    }
    else
    {
      *v14 = 0;
      v15 = -2147024882;
    }
  }
  ((void (__fastcall *)(struct IBindCtx *))a3->lpVtbl->Release)(a3);
  if ( v15 < 0 )
  {
    COInetSession = -2147024882;
    goto LABEL_77;
  }
  v18 = (struct IUri *)*((_QWORD *)this + 25);
  COInetSession = 0;
  if ( v18 != a2 )
  {
    if ( v18 )
    {
      ((void (__fastcall *)(struct IUri *))v18->lpVtbl->Release)(v18);
      *((_QWORD *)this + 25) = 0;
    }
    if ( a2 )
    {
      *((_QWORD *)this + 25) = a2;
      ((void (__fastcall *)(struct IUri *))a2->lpVtbl->AddRef)(a2);
    }
    v19 = (__int64 (__fastcall ***)(__int64, GUID *, __int128 *))*((_QWORD *)this + 25);
    COInetSession = 0;
    v20 = (__int64 (__fastcall ***)(__int64, GUID *, __int128 *))*((_QWORD *)this + 27);
    v21 = *((_DWORD *)this + 56);
    v123 = v21;
    if ( v19 != v20 || v21 )
    {
      v22 = (OLECHAR *)*((_QWORD *)this + 29);
      if ( v22 )
      {
        SysFreeString(v22);
        v21 = v123;
        *((_QWORD *)this + 29) = 0;
      }
      *((_QWORD *)this + 30) = 0;
      *((_DWORD *)this + 62) = 0;
      if ( v19 != v20 )
      {
        v23 = *((_QWORD *)this + 27);
        if ( v23 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          v21 = v123;
          *((_QWORD *)this + 27) = 0;
        }
      }
    }
    *((_DWORD *)this + 56) = 0;
    if ( v19 && (v21 || v19 != v20) )
    {
      v91 = *v19;
      *(_QWORD *)&pitem = 0;
      v92 = (*v91)((__int64)v19, &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60, &pitem);
      v93 = *((unsigned int *)this + 56);
      if ( v92 < 0 )
      {
        COInetSession = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int128 *), __int64, char *, _QWORD))(*v19)[3])(
                          v19,
                          v93,
                          (char *)this + 232,
                          0);
        if ( COInetSession >= 0 )
        {
          v110 = (OLECHAR *)*((_QWORD *)this + 29);
          *((_QWORD *)this + 30) = v110;
          *((_DWORD *)this + 62) = SysStringLen(v110);
        }
      }
      else
      {
        COInetSession = (*(__int64 (__fastcall **)(_QWORD, __int64, char *, char *))(*(_QWORD *)pitem + 224LL))(
                          pitem,
                          v93,
                          (char *)this + 240,
                          (char *)this + 248);
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)pitem + 16LL))(pitem);
      }
      if ( v19 != v20 && COInetSession >= 0 )
      {
        *((_QWORD *)this + 27) = v19;
        ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int128 *)))(*v19)[1])(v19);
      }
      if ( COInetSession == 1 )
        COInetSession = CUString::Set(
                          (CBinding *)((char *)this + 208),
                          *((struct IUri **)this + 25),
                          Uri_PROPERTY_RAW_URI);
    }
  }
  if ( !*((_QWORD *)this + 30) )
  {
    if ( COInetSession >= 0 )
    {
      COInetSession = -2147024809;
      goto LABEL_4;
    }
LABEL_77:
    if ( *((_QWORD *)this + 16) && v7 )
    {
      *((_DWORD *)this + 86) = COInetSession;
      CBinding::CallOnStopBinding(this, COInetSession, 0);
    }
    v54 = *((_QWORD *)this + 48);
    if ( v54 )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v54 + 48LL))(v54, 0);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 16LL))(*((_QWORD *)this + 48));
      *((_QWORD *)this + 48) = 0;
    }
    return (unsigned int)COInetSession;
  }
  if ( COInetSession < 0 )
    goto LABEL_77;
  *((_DWORD *)this + 110) = 128;
  if ( this != (CBinding *)-440LL )
  {
    v24 = *((_QWORD *)this + 69);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v25 = (void *)*((_QWORD *)this + 56);
    if ( v25 )
      CoTaskMemFree(v25);
    v26 = (void *)*((_QWORD *)this + 61);
    if ( v26 )
      CoTaskMemFree(v26);
    ReleaseStgMedium((LPSTGMEDIUM)this + 19);
    memset_0((char *)this + 444, 0, 0x7Cu);
    *((_DWORD *)this + 110) = 128;
  }
  v27 = (_DWORD *)((char *)this + 176);
  COInetSession = -2147467259;
  *((_QWORD *)this + 22) = 0;
  *((_DWORD *)this + 46) = 0;
  if ( !*((_DWORD *)this + 40) )
  {
    v28 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int128 *))*((_QWORD *)this + 16);
    *(_QWORD *)&pitem = 0;
    v29 = (**v28)(v28, &GUID_aaa74ef9_8ee7_4659_88d9_f8c504da73cc, &pitem);
    v30 = (char *)this + 440;
    if ( v29 < 0 )
    {
      COInetSession = (*(__int64 (__fastcall **)(_QWORD, char *, char *))(**((_QWORD **)this + 16) + 64LL))(
                        *((_QWORD *)this + 16),
                        (char *)this + 176,
                        v30);
    }
    else
    {
      COInetSession = (*(__int64 (__fastcall **)(_QWORD, char *, char *, char *, char *))(*(_QWORD *)pitem + 88LL))(
                        pitem,
                        (char *)this + 176,
                        v30,
                        (char *)this + 180,
                        (char *)this + 184);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)pitem + 16LL))(pitem);
    }
    *((_DWORD *)this + 40) = 2;
  }
  if ( COInetSession )
  {
    if ( COInetSession < 0 )
    {
LABEL_76:
      v7 = v124;
      goto LABEL_77;
    }
  }
  else if ( !*((_QWORD *)this + 16) || (*(_BYTE *)v27 & 1) == 0 )
  {
    *v27 &= ~2u;
  }
  v31 = *((_DWORD *)this + 125);
  if ( (g_dwSettings & 0x20000000) != 0 )
    *v27 |= 0x20000u;
  if ( (_WORD)v31 )
  {
    if ( a5 )
      goto LABEL_47;
    v125 = 0;
    *(_QWORD *)&pitem = 0;
    COInetSession = GetCOInetSession(&v125);
    if ( COInetSession )
      goto LABEL_249;
    v111 = (const unsigned __int16 *)*((_QWORD *)this + 30);
    v123 = 0;
    v112 = v125;
    rclsid = GUID_NULL;
    v113 = COInetSession::CreateFirstProtocol(
             v125,
             v111,
             0,
             0,
             (struct IInternetProtocol **)&pitem,
             &rclsid,
             &v123,
             (unsigned __int16)v31);
    _InterlockedDecrement((volatile signed __int32 *)v112 + 4);
    COInetSession = v113;
    if ( v113 )
      goto LABEL_249;
    v94 = Buf1;
    v132 = a3;
    v133 = 0;
    v125 = 0;
    v131 = *(_OWORD *)Buf1;
    if ( (**(int (__fastcall ***)(_QWORD, GUID *, struct COInetSession **))pitem)(
           pitem,
           &IID_IInternetProtocolEx,
           &v125) < 0 )
      v114 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, __int128 *))(*(_QWORD *)pitem + 24LL))(
               pitem,
               *((_QWORD *)this + 30),
               0,
               0,
               0,
               &v131);
    else
      v114 = (*(__int64 (__fastcall **)(struct COInetSession *, _QWORD, _QWORD, _QWORD, _DWORD, __int128 *))(*(_QWORD *)v125 + 104LL))(
               v125,
               *((_QWORD *)this + 25),
               0,
               0,
               0,
               &v131);
    COInetSession = v114;
    if ( v125 )
      (*(void (__fastcall **)(struct COInetSession *))(*(_QWORD *)v125 + 16LL))(v125);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)pitem + 16LL))(pitem);
    if ( !COInetSession )
    {
      if ( !v133 )
        return (unsigned int)COInetSession;
      COInetSession = -2146697193;
      *v128 = v133;
      goto LABEL_76;
    }
    if ( COInetSession != -2146697199 )
    {
LABEL_249:
      v7 = v124;
      goto LABEL_4;
    }
  }
  else
  {
    if ( a5 )
      goto LABEL_47;
    v94 = Buf1;
  }
  if ( memcmp_0(v94, &IID_IStream, 0x10u) && memcmp_0(v94, &IID_IStorage, 0x10u) && memcmp_0(v94, &IID_IUnknown, 0x10u) )
  {
    COInetSession = -2147024809;
    goto LABEL_76;
  }
LABEL_47:
  v32 = IsOInetProtocol(a3, *((const unsigned __int16 **)this + 30));
  COInetSession = v32;
  if ( v32 )
  {
    v7 = v124;
    if ( v32 != -2146697202 )
      COInetSession = -2146697203;
    goto LABEL_77;
  }
  v33 = 33554688;
  v34 = (_QWORD *)((char *)this + 376);
  if ( !*((_DWORD *)this + 68) )
    v33 = 256;
  v35 = v33 | 0x20000000;
  v36 = (v31 & 0x400000) != 0;
  v37 = (void **)*((_QWORD *)this + 50);
  v128 = v37;
  if ( !v36 )
    v35 = v33;
  v123 = v35;
  EnterCriticalSection(&g_mxsTransMgr);
  v125 = 0;
  if ( v37 )
  {
    v38 = (*(__int64 (__fastcall **)(void **, GUID *, struct COInetSession **))*v37)(v37, &IID_IAsyncBindCtx, &v125);
    if ( v38 )
    {
LABEL_54:
      if ( v38 <= 1 )
      {
LABEL_56:
        v35 = v123;
        goto LABEL_57;
      }
      goto LABEL_55;
    }
    v96 = v125;
    *(_QWORD *)&pitem = v125;
    if ( !memcmp_0(&IID_IProxyManager, &IID_IUnknown, 0x10u)
      || !memcmp_0(&IID_IProxyManager, &IID_IBindCtx, 0x10u)
      || !memcmp_0(&IID_IProxyManager, &IID_IAsyncBindCtx, 0x10u) )
    {
      v97 = v96;
    }
    else
    {
      if ( memcmp_0(&IID_IProxyManager, &IID_IMarshal, 0x10u) )
      {
        v42 = (EdgeTransaction *)*((_QWORD *)v96 + 5);
        if ( v42 )
        {
          v38 = 0;
          (*(void (__fastcall **)(EdgeTransaction *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2147500034LL);
        }
        else
        {
          v38 = -2147467262;
        }
        v98 = pitem;
        v99 = *(_QWORD *)(pitem + 48);
        if ( !v99 || this == (CBinding *)-376LL )
        {
          if ( !*(_QWORD *)(pitem + 40) )
            v38 = -2147467262;
          if ( this != (CBinding *)-376LL )
            *v34 = 0;
        }
        else
        {
          *v34 = v99;
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v98 + 48) + 16LL));
        }
        if ( !v38 )
        {
          v100 = *((_DWORD *)v42 + 94);
          if ( v100 != GetCurrentThreadId() )
            CBindCtx::SetTransactionObject(v125, 0);
          v74 = 1;
          if ( !v42 )
            goto LABEL_143;
          goto LABEL_261;
        }
        v37 = v128;
        goto LABEL_54;
      }
      if ( v96 )
        v97 = (struct COInetSession *)((char *)v96 + 8);
      else
        v97 = 0;
    }
    _InterlockedIncrement((volatile signed __int32 *)v96 + 4);
    (*(void (__fastcall **)(struct COInetSession *))(*(_QWORD *)v97 + 16LL))(v97);
    CBindCtx::Release(v125);
    v125 = 0;
LABEL_55:
    v39 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v37;
    *(_QWORD *)&pitem = 0;
    ((__int64 (__fastcall **)(void **, const wchar_t *, __int128 *))v39)[10](v37, L"CBinding Context", &pitem);
    if ( !(_QWORD)pitem )
      goto LABEL_56;
    *(_QWORD *)&rclsid.Data1 = 0;
    if ( !(unsigned int)CBinding::QueryInterface((CBinding *)pitem, &IID_IProxyManager, (void **)&rclsid) )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&rclsid.Data1 + 16LL))(*(_QWORD *)&rclsid.Data1);
      v115 = (CBinding *)pitem;
LABEL_257:
      CBinding::Release(v115);
      goto LABEL_56;
    }
    v115 = (CBinding *)pitem;
    v116 = *(_QWORD *)(pitem + 384);
    if ( !v116 )
      goto LABEL_257;
    v42 = (EdgeTransaction *)(v116 - 48);
    if ( !v42 )
      goto LABEL_257;
    (*(void (__fastcall **)(EdgeTransaction *))(*(_QWORD *)v42 + 8LL))(v42);
    CBinding::Release((CBinding *)pitem);
LABEL_261:
    v74 = 1;
    goto LABEL_143;
  }
LABEL_57:
  if ( !InternalForkingSupport_ShouldUseEdge() )
  {
    v40 = (EdgeTransaction *)CoTaskMemAlloc(0x640u);
    v42 = v40;
    if ( v40 )
    {
      memset_0(v40, 0, 0x640u);
      CTransaction::CTransaction(v42, v35);
      *(_QWORD *)v42 = &LegacyTransaction::`vftable'{for `IInternetProtocolSink'};
      *((_QWORD *)v42 + 1) = &LegacyTransaction::`vftable'{for `ITransProtocolSink'};
      *((_QWORD *)v42 + 2) = &CTransaction::`vftable'{for `IInternetBindInfoEx'};
      *((_QWORD *)v42 + 3) = &CTransaction::`vftable'{for `IDevToolbarDownloadInitiatorInfo'};
      *((_QWORD *)v42 + 4) = &LegacyTransaction::`vftable'{for `IServiceProvider'};
      *((_QWORD *)v42 + 5) = &LegacyTransaction::`vftable'{for `IAuthenticate'};
      *((_QWORD *)v42 + 6) = &LegacyTransaction::`vftable'{for `IInternetProtocolEx'};
      *((_QWORD *)v42 + 7) = &LegacyTransaction::`vftable'{for `IInternetPriority'};
      *((_QWORD *)v42 + 8) = &CTransaction::`vftable'{for `IInternetPriorityInternal'};
      *((_QWORD *)v42 + 9) = &EdgeTransaction::`vftable'{for `IWrappedProtocol'};
      *((_QWORD *)v42 + 10) = &EdgeTransaction::`vftable'{for `IUriContainer'};
      *((_QWORD *)v42 + 11) = &EdgeTransaction::`vftable'{for `IPreBindingSupport'};
      *((_QWORD *)v42 + 12) = &CTransaction::`vftable'{for `ITransactionInternal'};
      *((_QWORD *)v42 + 13) = &CTransaction::`vftable'{for `IProtocolHandlerValidator'};
      *((_QWORD *)v42 + 14) = &CTransaction::`vftable'{for `IWinInetHttpTimeouts'};
      *((_QWORD *)v42 + 15) = &LegacyTransaction::`vftable'{for `IInternetBindInfoInternal'};
      *((_QWORD *)v42 + 16) = &CTransaction::`vftable'{for `IDownloadModeHandleCallback'};
      *((_QWORD *)v42 + 17) = &LegacyTransaction::`vftable'{for `IInternetPriorityInfoInternal'};
      *((_QWORD *)v42 + 193) = 0;
      *((_QWORD *)v42 + 194) = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)v42 + 39);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)v42 + 1544);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)v42 + 1552);
      CTransaction::Init(v42, v123);
      goto LABEL_133;
    }
LABEL_207:
    wil::details::in1diag3::_FailFast_NullAlloc(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"onecoreuap\\inetcore\\urlmon\\trans\\common\\ctransaction.cpp",
      v41);
  }
  v71 = (EdgeTransaction *)operator new(0x698u);
  if ( !v71 )
    goto LABEL_207;
  v42 = EdgeTransaction::EdgeTransaction(v71, v35);
  if ( !v42 )
    goto LABEL_207;
LABEL_133:
  if ( !(*(__int64 (__fastcall **)(EdgeTransaction *))(*(_QWORD *)v42 + 112LL))(v42) )
  {
LABEL_203:
    v42 = 0;
    v74 = -2147467259;
    goto LABEL_143;
  }
  GlobalTransactionManager = (HDSA *)GetGlobalTransactionManager();
  if ( !GlobalTransactionManager )
  {
LABEL_202:
    (*(void (__fastcall **)(EdgeTransaction *, __int64))(*(_QWORD *)v42 + 56LL))(v42, 1);
    goto LABEL_203;
  }
  pitem = (unsigned __int64)v42;
  EnterCriticalSection(&g_mxsTransMgr);
  DWORD2(pitem) = ++dword_18016B828;
  if ( DSA_InsertItem(*GlobalTransactionManager, 0x7FFFFFFF, &pitem) < 0 )
  {
    LeaveCriticalSection(&g_mxsTransMgr);
    goto LABEL_202;
  }
  v73 = dword_18016B828;
  LeaveCriticalSection(&g_mxsTransMgr);
  *((_DWORD *)v42 + 92) = 1;
  *((_DWORD *)v42 + 377) = v73;
  v74 = (**(__int64 (__fastcall ***)(EdgeTransaction *, GUID *, char *))v42)(
          v42,
          &IID_IInternetProtocol,
          (char *)this + 384);
  if ( !v74 )
    (*(void (__fastcall **)(EdgeTransaction *))(*(_QWORD *)v42 + 16LL))(v42);
  if ( !v125 )
  {
    if ( !v128 )
      goto LABEL_174;
    (*(void (__fastcall **)(void **, GUID *, struct COInetSession **))*v128)(v128, &IID_IAsyncBindCtx, &v125);
    if ( !v125 )
      goto LABEL_174;
  }
  v75 = v125;
  v76 = (EdgeTransaction *)*((_QWORD *)v125 + 5);
  if ( v42 != v76 )
  {
    if ( v76 )
      (*(void (__fastcall **)(EdgeTransaction *))(*(_QWORD *)v76 + 16LL))(v76);
    *((_QWORD *)v75 + 5) = v42;
    (*(void (__fastcall **)(EdgeTransaction *))(*(_QWORD *)v42 + 8LL))(v42);
  }
LABEL_143:
  if ( v125 )
    CBindCtx::Release(v125);
  if ( !v42 )
  {
    *((_QWORD *)this + 48) = 0;
    v77 = (char *)this + 376;
    goto LABEL_147;
  }
LABEL_174:
  v95 = (char *)v42 + 48;
  *((_QWORD *)this + 48) = (char *)v42 + 48;
  v77 = (char *)this + 376;
  if ( !v95 || this == (CBinding *)-376LL || !*(_QWORD *)v77 )
  {
LABEL_147:
    if ( v74 == 1 && v77 && !*(_QWORD *)v77 )
    {
      LeaveCriticalSection(&g_mxsTransMgr);
    }
    else
    {
      LeaveCriticalSection(&g_mxsTransMgr);
      if ( v74 )
      {
        if ( v74 == 1 )
          goto LABEL_61;
LABEL_269:
        COInetSession = -2147024882;
        goto LABEL_76;
      }
    }
    v78 = *(struct COInetSession **)v27;
    v123 = *((_DWORD *)this + 68);
    v128 = (void **)*((_QWORD *)this + 50);
    *(_QWORD *)&pitem = *((_QWORD *)this + 30);
    rclsid.Data1 = *((_DWORD *)this + 46);
    v79 = (unsigned __int8 *)CoTaskMemAlloc(0x2000u);
    v80 = v79;
    if ( v79 )
      memset_0(v79, 0, 0x2000u);
    v81 = (CTransData *)CoTaskMemAlloc(0x4E8u);
    v83 = v81;
    if ( v81 )
    {
      memset_0(v81, 0, 0x4E8u);
      v81 = CTransData::CTransData(v83, v84, v80, v85, v123);
    }
    if ( v80 )
    {
      if ( v81 )
      {
        v86 = Buf1;
        v87 = pitem;
        Data1 = rclsid.Data1;
        lpsza = (LPCOLESTR)v128;
        *(_QWORD *)v77 = v81;
        v125 = v78;
        CTransData::Initialize(v81, v87, &v125, v86, lpsza, 0);
        v88 = *((_QWORD *)this + 50);
        v89 = *(_QWORD *)v77;
        v90 = *(CTransData **)(v88 + 48);
        if ( *(CTransData **)v77 != v90 )
        {
          if ( v90 )
            CTransData::Release(v90);
          *(_QWORD *)(v88 + 48) = v89;
          if ( v89 )
            _InterlockedIncrement((volatile signed __int32 *)(v89 + 16));
        }
        goto LABEL_70;
      }
      CoTaskMemFree(v80);
    }
    else if ( v81 )
    {
      CTransData::`scalar deleting destructor'(v81, v82);
    }
    *(_QWORD *)v77 = 0;
    goto LABEL_269;
  }
  LeaveCriticalSection(&g_mxsTransMgr);
LABEL_61:
  v43 = 0x10000000;
  if ( !a5 )
    v43 = 0x1000000;
  v44 = *((_QWORD *)this + 48);
  *((_DWORD *)this + 82) |= v43;
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
    v45 = (int (__fastcall ***)(_QWORD, GUID *, __int128 *))*((_QWORD *)this + 48);
    *(_QWORD *)&pitem = 0;
    if ( (**v45)(v45, &GUID_c28722e5_bc1a_4c55_a68d_33219f698910, &pitem) >= 0 )
    {
      if ( (*((_BYTE *)this + 180) & 4) != 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)pitem + 48LL))(pitem);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)pitem + 16LL))(pitem);
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 16LL))(*((_QWORD *)this + 48));
  }
  v46 = *(void ***)v27;
  v47 = *((_QWORD *)this + 30);
  v48 = *(_QWORD *)v77;
  v129 = *((_DWORD *)this + 46);
  lpsz = (LPCOLESTR)*((_QWORD *)this + 50);
  v128 = v46;
  COInetSession = CTransData::Initialize(v48, v47, &v128, Buf1, lpsz, a5);
  if ( COInetSession < 0 )
    goto LABEL_76;
LABEL_70:
  *v130 = (unsigned __int16 *)*((_QWORD *)this + 56);
  v49 = *(_QWORD *)v77;
  v50 = *v27;
  v51 = *(_DWORD *)(*(_QWORD *)v77 + 188LL);
  *(_DWORD *)(*(_QWORD *)v77 + 112LL) = *v27;
  if ( v51 == 4 )
  {
    if ( (v50 & 0x82) != 0x82 )
      goto LABEL_74;
    *(_QWORD *)(v49 + 1232) = 0;
    goto LABEL_73;
  }
  if ( v51 )
  {
    if ( v51 == 5 )
    {
      v70 = *(_DWORD *)(v49 + 164);
      if ( v70 && v70 == *(_DWORD *)(v49 + 168) )
      {
        *(_DWORD *)(v49 + 188) = 4;
      }
      else if ( (v50 & 0x82) == 0x82 )
      {
LABEL_73:
        *(_DWORD *)(v49 + 188) = 1;
      }
    }
  }
  else if ( (*(_BYTE *)(v49 + 144) & 1) != 0 )
  {
    *(_DWORD *)(v49 + 188) = 5;
  }
LABEL_74:
  v52 = a2->lpVtbl;
  v123 = 0;
  v53 = ((__int64 (__fastcall *)(struct IUri *, unsigned int *))v52->GetScheme)(a2, &v123);
  COInetSession = v53;
  if ( v53 )
  {
    if ( v53 < 0 )
      goto LABEL_76;
  }
  else
  {
    v55 = *(_DWORD *)(*(_QWORD *)v77 + 188LL);
    if ( v55 == 2 || v55 == 4 || !ProtocolFromScheme(v123) )
      *v27 |= 0x40u;
  }
  *v27 |= 0x100000u;
  *((_DWORD *)this + 45) |= 0x80000000;
  if ( *((_DWORD *)this + 68) )
    *((_DWORD *)this + 125) |= 0x100000u;
  if ( *((_DWORD *)this + 40) == 2 )
  {
    COInetSession = (*(__int64 (__fastcall **)(_QWORD, _QWORD, CBinding *))(**((_QWORD **)this + 16) + 24LL))(
                      *((_QWORD *)this + 16),
                      0,
                      this);
    *((_DWORD *)this + 40) = 1;
  }
  else
  {
    COInetSession = -2147467259;
  }
  v7 = 1;
  if ( *((_QWORD *)this + 16) && (*(_BYTE *)v27 & 1) != 0 )
    v56 = 304;
  else
    v56 = 432;
  if ( COInetSession < 0 )
    goto LABEL_77;
  v128 = 0;
  v57 = v56 | 0x400000;
  if ( (*v27 & 0x400000) == 0 )
    v57 = v56;
  v58 = v57 & 0xFFFFFEFF;
  if ( (*v27 & 0x10000) == 0 )
    v58 = v57;
  v59 = v58 | 0x40000000;
  if ( (*((_BYTE *)this + 180) & 4) == 0 )
    v59 = v58;
  v60 = v59 | 0x2000200;
  if ( !*((_DWORD *)this + 68) )
    v60 = v59;
  v61 = v60 | 0x10000000;
  if ( (*((_DWORD *)this + 82) & 0x10000000) == 0 )
    v61 = v60;
  v62 = v61 | 0x1000000;
  if ( (*((_DWORD *)this + 82) & 0x1000000) == 0 )
    v62 = v61;
  if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, void ***))a3->lpVtbl->GetObjectParam)(
         a3,
         L"EnablePreBinding",
         &v128) >= 0 )
  {
    v117 = v128;
    *((_DWORD *)this + 145) = 1;
    (*((void (__fastcall **)(void **))*v117 + 2))(v117);
  }
  if ( *((_QWORD *)this + 48) )
  {
    *((_BYTE *)this + 584) |= 0x10u;
    CBinding::SetProtocolPriority(this);
  }
  v63 = *((_QWORD *)this + 47);
  if ( (*(_BYTE *)(v63 + 124) & 5) == 0 && !*(_DWORD *)(v63 + 168) || (*(_BYTE *)(v63 + 144) & 0x10) == 0 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 8LL))(*((_QWORD *)this + 48));
    v101 = *((_QWORD *)this + 47);
    v102 = *((_QWORD *)this + 48);
    v103 = *(_QWORD *)(v101 + 24);
    if ( v103 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
      *(_QWORD *)(v101 + 24) = 0;
    }
    v104 = *(_DWORD *)(v101 + 188);
    if ( v104 == 4 || (v118 = v104 - 1) == 0 || (v119 = v118 - 1) == 0 || (v120 = v119 - 1) == 0 || v120 == 2 )
    {
      *(_QWORD *)(v101 + 24) = v102;
      if ( v102 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v102 + 8LL))(v102);
    }
    v105 = (int (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)this + 48);
    Buf1 = 0;
    if ( (**v105)(v105, &IID_IInternetProtocolEx, &Buf1) < 0 )
    {
      v106 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, char *, int, _QWORD))(**((_QWORD **)this + 48) + 24LL))(
               *((_QWORD *)this + 48),
               *((_QWORD *)this + 30),
               (char *)this + 16,
               (char *)this + 24,
               v62,
               0);
    }
    else
    {
      if ( *((_DWORD *)this + 145) == 1 )
        IUnknown_EnablePreBinding((struct IUnknown *)Buf1, 1);
      v106 = (*(__int64 (__fastcall **)(void *, _QWORD, char *, char *, int, _QWORD))(*(_QWORD *)Buf1 + 104LL))(
               Buf1,
               *((_QWORD *)this + 25),
               (char *)this + 16,
               (char *)this + 24,
               v62,
               0);
    }
    COInetSession = v106;
    if ( Buf1 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)Buf1 + 16LL))(Buf1);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 16LL))(*((_QWORD *)this + 48));
LABEL_4:
    if ( COInetSession >= 0 )
      return (unsigned int)COInetSession;
    goto LABEL_77;
  }
  v64 = *(_DWORD *)(v63 + 164);
  v65 = (const OLECHAR *)(v63 + 200);
  v66 = *(_WORD *)(v63 + 200);
  v67 = v63 + 200;
  if ( !v66 )
    v67 = 0;
  if ( v67 )
  {
    if ( !v66 )
      v65 = 0;
    CBinding::OnTransNotification(this, BINDSTATUS_MIMETYPEAVAILABLE, v64, v64, v65, 0);
  }
  v68 = (const OLECHAR *)(*((_QWORD *)this + 47) + 712LL);
  v69 = v68;
  if ( !*v68 )
    v69 = 0;
  if ( v69 )
  {
    if ( !*v68 )
      v68 = 0;
    CBinding::OnTransNotification(this, BINDSTATUS_CACHEFILENAMEAVAILABLE, v64, v64, v68, 0);
  }
  CBinding::OnTransNotification(this, BINDSTATUS_ENDDOWNLOADDATA, v64, v64, 0, 0);
  return (unsigned int)COInetSession;
}

```

## disassembly

```asm
0x18002bc70  push    rbp
0x18002bc72  push    rbx
0x18002bc73  push    rsi
0x18002bc74  push    rdi
0x18002bc75  push    r12
0x18002bc77  push    r13
0x18002bc79  push    r14
0x18002bc7b  push    r15
0x18002bc7d  lea     rbp, [rsp-7]
0x18002bc82  sub     rsp, 0E8h
0x18002bc89  movaps  [rsp+120h+var_50], xmm6
0x18002bc91  mov     rax, cs:__security_cookie
0x18002bc98  xor     rax, rsp
0x18002bc9b  mov     [rbp+3Fh+var_58], rax
0x18002bc9f  mov     rax, [rbp+3Fh+arg_28]
0x18002bca3  xor     r12d, r12d
0x18002bca6  mov     [rbp+3Fh+var_A0], rax
0x18002bcaa  mov     r15, r9
0x18002bcad  mov     rax, [rbp+3Fh+arg_30]
0x18002bcb1  mov     r14, r8
0x18002bcb4  mov     [rbp+3Fh+var_B0], rax
0x18002bcb8  mov     r13, rdx
0x18002bcbb  mov     [rsp+120h+Buf1], r9
0x18002bcc0  mov     rbx, rcx
0x18002bcc3  mov     [rsp+120h+var_DC], r12d
0x18002bcc8  mov     esi, 80004005h
0x18002bccd  mov     qword ptr [rbp+3Fh+pitem], r12
0x18002bcd1  test    r8, r8
0x18002bcd4  jz      short loc_18002BCF6
0x18002bcd6  mov     rax, [r8]
0x18002bcd9  lea     rdx, aBscbHolder; "_BSCB_Holder_"
0x18002bce0  lea     r8, [rbp+3Fh+pitem]
0x18002bce4  mov     rcx, r14
0x18002bce7  mov     rax, [rax+50h]
0x18002bceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcf0  mov     esi, eax
0x18002bcf2  test    eax, eax
0x18002bcf4  jns     short loc_18002BD32
0x18002bcf6  xor     eax, eax
0x18002bcf8  mov     [rbx+80h], rax
0x18002bcff  test    esi, esi
0x18002bd01  js      loc_18002C3D2
0x18002bd07  mov     eax, esi
0x18002bd09  mov     rcx, [rbp+3Fh+var_58]
0x18002bd0d  xor     rcx, rsp; StackCookie
0x18002bd10  call    __security_check_cookie
0x18002bd15  movaps  xmm6, [rsp+120h+var_50]
0x18002bd1d  add     rsp, 0E8h
0x18002bd24  pop     r15
0x18002bd26  pop     r14
0x18002bd28  pop     r13
0x18002bd2a  pop     r12
0x18002bd2c  pop     rdi
0x18002bd2d  pop     rsi
0x18002bd2e  pop     rbx
0x18002bd2f  pop     rbp
0x18002bd30  retn
0x18002bd32  mov     rcx, qword ptr [rbp+3Fh+pitem]
0x18002bd36  lea     r8, [rbx+80h]
0x18002bd3d  lea     rdx, IID_IBindStatusCallback
0x18002bd44  mov     rax, [rcx]
0x18002bd47  mov     rax, [rax]
0x18002bd4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd4f  mov     rcx, qword ptr [rbp+3Fh+pitem]
0x18002bd53  mov     esi, eax
0x18002bd55  mov     rax, [rcx]
0x18002bd58  mov     rax, [rax+10h]
0x18002bd5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd61  test    esi, esi
0x18002bd63  js      short loc_18002BCF6
0x18002bd65  cmp     [rbx+80h], r12
0x18002bd6c  jz      loc_18002CDE2
0x18002bd72  mov     eax, [rbp+3Fh+arg_20]
0x18002bd75  mov     [rbx+110h], eax
0x18002bd7b  test    eax, eax
0x18002bd7d  jnz     loc_18002CDEC
0x18002bd83  lea     r15, [rbx+190h]
0x18002bd8a  xor     esi, esi
0x18002bd8c  mov     [r15], rsi
0x18002bd8f  lea     rdx, IID_IAsyncBindCtx
0x18002bd96  mov     rax, [r14]
0x18002bd99  mov     r8, r15
0x18002bd9c  mov     rcx, r14
0x18002bd9f  mov     rax, [rax]
0x18002bda2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bda7  mov     edi, eax
0x18002bda9  mov     rcx, r14
0x18002bdac  test    eax, eax
0x18002bdae  jz      short loc_18002BDB5
0x18002bdb0  mov     edi, esi
0x18002bdb2  mov     [r15], rsi
0x18002bdb5  mov     rax, [r14]
0x18002bdb8  mov     rax, [rax+8]
0x18002bdbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdc1  cmp     [r15], rsi
0x18002bdc4  jnz     short loc_18002BE36
0x18002bdc6  mov     ecx, 48h ; 'H'; Size
0x18002bdcb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bdd0  mov     rsi, rax
0x18002bdd3  test    rax, rax
0x18002bdd6  jz      loc_18002CC44
0x18002bddc  lea     rax, ??_7CBindCtx@@6BIBindCtx@@@; const CBindCtx::`vftable'{for `IBindCtx'}
0x18002bde3  mov     [rsi], rax
0x18002bde6  lea     rax, ??_7CBindCtx@@6BIMarshal@@@; const CBindCtx::`vftable'{for `IMarshal'}
0x18002bded  mov     [rsi+8], rax
0x18002bdf1  mov     dword ptr [rsi+10h], 1
0x18002bdf8  mov     [rsi+20h], r14
0x18002bdfc  mov     rcx, [r14]
0x18002bdff  mov     rax, [rcx+8]
0x18002be03  mov     rcx, r14
0x18002be06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be0b  mov     [rsi+18h], r12
0x18002be0f  call    cs:__imp_GetCurrentThreadId
0x18002be16  nop     dword ptr [rax+rax+00h]
0x18002be1b  mov     [rsi+38h], eax
0x18002be1e  xor     eax, eax
0x18002be20  mov     [rsi+28h], rax
0x18002be24  mov     [rsi+30h], rax
0x18002be28  mov     [rsi+40h], rax
0x18002be2c  lock inc cs:?g_cRef@@3VCRefCount@@A; CRefCount g_cRef
0x18002be33  mov     [r15], rsi
0x18002be36  mov     rax, [r14]
0x18002be39  mov     rcx, r14
0x18002be3c  mov     rax, [rax+10h]
0x18002be40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be45  test    edi, edi
0x18002be47  js      loc_18002CE42
0x18002be4d  mov     rcx, [rbx+0C8h]
0x18002be54  xor     edx, edx
0x18002be56  mov     esi, edx
0x18002be58  cmp     rcx, r13
0x18002be5b  jz      loc_18002BF01
0x18002be61  test    rcx, rcx
0x18002be64  jnz     loc_18002CCAC
0x18002be6a  test    r13, r13
0x18002be6d  jz      short loc_18002BE88
0x18002be6f  mov     [rbx+0C8h], r13
0x18002be76  mov     rcx, r13
0x18002be79  mov     rax, [r13+0]
0x18002be7d  mov     rax, [rax+8]
0x18002be81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be86  xor     edx, edx
0x18002be88  mov     rdi, [rbx+0C8h]
0x18002be8f  mov     esi, edx
0x18002be91  mov     r15, [rbx+0D8h]
0x18002be98  mov     eax, [rbx+0E0h]
0x18002be9e  mov     [rsp+120h+var_E0], eax
0x18002bea2  cmp     rdi, r15
0x18002bea5  jz      loc_18002CA84
0x18002beab  mov     rcx, [rbx+0E8h]; bstrString
0x18002beb2  test    rcx, rcx
0x18002beb5  jnz     loc_18002CE4C
0x18002bebb  mov     [rbx+0F0h], rdx
0x18002bec2  mov     [rbx+0F8h], edx
0x18002bec8  cmp     rdi, r15
0x18002becb  jz      short loc_18002BEF2
0x18002becd  mov     rcx, [rbx+0D8h]
0x18002bed4  test    rcx, rcx
0x18002bed7  jz      short loc_18002BEF2
0x18002bed9  mov     rax, [rcx]
0x18002bedc  mov     rax, [rax+10h]
0x18002bee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bee5  mov     eax, [rsp+120h+var_E0]
0x18002bee9  xor     edx, edx
0x18002beeb  mov     [rbx+0D8h], rdx
0x18002bef2  mov     [rbx+0E0h], edx
0x18002bef8  test    rdi, rdi
0x18002befb  jnz     loc_18002C941
0x18002bf01  cmp     qword ptr [rbx+0F0h], 0
0x18002bf09  jz      loc_18002CED2
0x18002bf0f  test    esi, esi
0x18002bf11  js      loc_18002C3D2
0x18002bf17  lea     rdi, [rbx+1B8h]
0x18002bf1e  mov     dword ptr [rdi], 80h
0x18002bf24  test    rdi, rdi
0x18002bf27  jz      short loc_18002BF7C
0x18002bf29  mov     rcx, [rdi+70h]
0x18002bf2d  test    rcx, rcx
0x18002bf30  jnz     loc_18002CEE4
0x18002bf36  mov     rcx, [rdi+8]; pv
0x18002bf3a  test    rcx, rcx
0x18002bf3d  jnz     loc_18002CEF5
0x18002bf43  mov     rcx, [rdi+30h]; pv
0x18002bf47  test    rcx, rcx
0x18002bf4a  jnz     loc_18002CF06
0x18002bf50  lea     rcx, [rdi+10h]; LPSTGMEDIUM
0x18002bf54  call    cs:__imp_ReleaseStgMedium
0x18002bf5b  nop     dword ptr [rax+rax+00h]
0x18002bf60  lea     rcx, [rbx+1BCh]; void *
0x18002bf67  xor     edx, edx; Val
0x18002bf69  mov     r8d, 7Ch ; '|'; Size
0x18002bf6f  call    memset_0
0x18002bf74  xor     edx, edx
0x18002bf76  mov     dword ptr [rdi], 80h
0x18002bf7c  lea     r15, [rbx+0B0h]
0x18002bf83  mov     esi, 80004005h
0x18002bf88  mov     qword ptr [r15], 0
0x18002bf8f  mov     [r15+8], edx
0x18002bf93  cmp     dword ptr [rbx+0A0h], 0
0x18002bf9a  jnz     short loc_18002C006
0x18002bf9c  mov     rcx, [rbx+80h]
0x18002bfa3  lea     r8, [rbp+3Fh+pitem]
0x18002bfa7  mov     qword ptr [rbp+3Fh+pitem], rdx
0x18002bfab  lea     rdx, _GUID_aaa74ef9_8ee7_4659_88d9_f8c504da73cc
0x18002bfb2  mov     rax, [rcx]
0x18002bfb5  mov     rax, [rax]
0x18002bfb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfbd  mov     r8, rdi
0x18002bfc0  test    eax, eax
0x18002bfc2  js      loc_18002CC0B
0x18002bfc8  mov     rcx, qword ptr [rbp+3Fh+pitem]
0x18002bfcc  lea     rdx, [r15+8]
0x18002bfd0  mov     [rsp+120h+lpsz], rdx
0x18002bfd5  lea     r9, [r15+4]
0x18002bfd9  mov     rdx, r15
0x18002bfdc  mov     rax, [rcx]
0x18002bfdf  mov     rax, [rax+58h]
0x18002bfe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfe8  mov     rcx, qword ptr [rbp+3Fh+pitem]
0x18002bfec  mov     esi, eax
0x18002bfee  mov     rax, [rcx]
0x18002bff1  mov     rax, [rax+10h]
0x18002bff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bffa  mov     dword ptr [rbx+0A0h], 2
0x18002c004  xor     edx, edx
0x18002c006  test    esi, esi
0x18002c008  jz      loc_18002CA91
0x18002c00e  js      loc_18002C3CD
0x18002c014  test    cs:?g_dwSettings@@3KA, 20000000h; ulong g_dwSettings
0x18002c01e  mov     r12d, [rbx+1F4h]
0x18002c025  jnz     loc_18002CF17
0x18002c02b  movzx   edi, r12w
0x18002c02f  test    edi, edi
0x18002c031  jnz     loc_18002CF23
0x18002c037  cmp     [rbp+3Fh+arg_20], edi
0x18002c03a  jz      loc_18002C9D6
0x18002c040  mov     rdx, [rbx+0F0h]; unsigned __int16 *
0x18002c047  mov     rcx, r14; struct IBindCtx *
0x18002c04a  call    ?IsOInetProtocol@@YAJPEAUIBindCtx@@PEBG@Z; IsOInetProtocol(IBindCtx *,ushort const *)
0x18002c04f  mov     esi, eax
0x18002c051  test    eax, eax
0x18002c053  jnz     loc_18002D07A
0x18002c059  cmp     [rbx+110h], esi
0x18002c05f  mov     eax, 2000100h
0x18002c064  mov     ecx, 100h
0x18002c069  lea     rsi, [rbx+178h]
0x18002c070  cmovz   eax, ecx
0x18002c073  lea     rcx, ?g_mxsTransMgr@@3VCMutexSem@@A; lpCriticalSection
0x18002c07a  mov     edi, eax
0x18002c07c  bts     edi, 1Dh
0x18002c080  bt      r12d, 16h
0x18002c085  mov     r12, [rbx+190h]
0x18002c08c  mov     [rbp+3Fh+var_B0], r12
0x18002c090  cmovnb  edi, eax
0x18002c093  mov     [rsp+120h+var_E0], edi
0x18002c097  call    cs:__imp_EnterCriticalSection
0x18002c09e  nop     dword ptr [rax+rax+00h]
0x18002c0a3  mov     [rsp+120h+var_D0], 0
0x18002c0ac  test    r12, r12
0x18002c0af  jz      short loc_18002C10F
0x18002c0b1  mov     rax, [r12]
0x18002c0b5  lea     r8, [rsp+120h+var_D0]
0x18002c0ba  lea     rdx, IID_IAsyncBindCtx
0x18002c0c1  mov     rcx, r12
0x18002c0c4  mov     rax, [rax]
0x18002c0c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0cc  mov     edi, eax
0x18002c0ce  test    eax, eax
0x18002c0d0  jz      loc_18002CAAE
0x18002c0d6  cmp     edi, 1
0x18002c0d9  jbe     short loc_18002C10B
0x18002c0db  mov     rax, [r12]
0x18002c0df  lea     r8, [rbp+3Fh+pitem]
0x18002c0e3  lea     rdx, aCbindingContex; "CBinding Context"
0x18002c0ea  mov     qword ptr [rbp+3Fh+pitem], 0
0x18002c0f2  mov     rcx, r12
0x18002c0f5  mov     rax, [rax+50h]
0x18002c0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0fe  mov     rcx, qword ptr [rbp+3Fh+pitem]; this
0x18002c102  test    rcx, rcx
0x18002c105  jnz     loc_18002D0A9
0x18002c10b  mov     edi, [rsp+120h+var_E0]
0x18002c10f  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
0x18002c116  nop     dword ptr [rax+rax+00h]
0x18002c11b  test    al, al
0x18002c11d  jnz     loc_18002C6AB
0x18002c123  mov     ecx, 640h; cb
0x18002c128  call    cs:__imp_CoTaskMemAlloc
0x18002c12f  nop     dword ptr [rax+rax+00h]
0x18002c134  mov     r12, rax
0x18002c137  test    rax, rax
0x18002c13a  jz      loc_18002CC51
0x18002c140  xor     edx, edx; Val
0x18002c142  mov     r8d, 640h; Size
0x18002c148  mov     rcx, rax; void *
0x18002c14b  call    memset_0
0x18002c150  mov     edx, edi; unsigned int
0x18002c152  mov     rcx, r12; this
0x18002c155  call    ??0CTransaction@@IEAA@K@Z; CTransaction::CTransaction(ulong)
0x18002c15a  lea     rax, ??_7LegacyTransaction@@6BIInternetProtocolSink@@@; const LegacyTransaction::`vftable'{for `IInternetProtocolSink'}
  ... truncated ...
```
