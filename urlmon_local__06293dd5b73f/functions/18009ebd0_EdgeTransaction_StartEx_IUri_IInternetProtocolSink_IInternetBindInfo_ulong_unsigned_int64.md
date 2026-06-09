# EdgeTransaction::StartEx(IUri *,IInternetProtocolSink *,IInternetBindInfo *,ulong,unsigned __int64)

- ea: `0x18009ebd0`
- end: `0x18009f97a`
- name: `?StartEx@EdgeTransaction@@UEAAJPEAUIUri@@PEAUIInternetProtocolSink@@PEAUIInternetBindInfo@@K_K@Z`
- size: `3498`
- prototype: `__int64 __usercall@<rax>(EdgeTransaction *__hidden this@<rcx>, struct IUri *@<rdx>, struct IInternetProtocolSink *@<r8>, struct IInternetBindInfo *@<r9>, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f8a00`

## callees

- `0x18002b290`
- `0x18002bb64`
- `0x180048100`
- `0x18004bec4`
- `0x18005d1e0`
- `0x180062eb8`
- `0x18006b7a0`
- `0x18006bfac`
- `0x18006cba8`
- `0x18006fcd8`
- `0x1800702e0`
- `0x180074620`
- `0x1800861b0`
- `0x18009e0f0`
- `0x18009ebd0`
- `0x18009fb40`
- `0x1800a25dc`
- `0x1800f20a0`
- `0x1800f5af4`
- `0x1800f8600`
- `0x1800f8850`
- `0x1801285fe`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18009f731`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18009f731`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ecf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ed03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ed68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ed77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ee13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ee85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009eebc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ef37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f068`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f263`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f28d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f40d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f426`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f509`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f5ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ecf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ed03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ed68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ed77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ee13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ee85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009eebc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ef37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f068`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f263`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f28d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f40d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f426`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f509`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f5ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ecd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ecdf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ed44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ed53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ed93`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ee4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ee98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f032`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f0d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f3ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f3fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f4ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f594`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ecd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ecdf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ed44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ed53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ed93`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ee4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ee98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f032`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f0d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f3ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f3fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f4ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f594`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18009f15f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18009f18b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18009f1de`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18009f15f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18009f18b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18009f1de`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009efee`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009efee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009f0f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009f0f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009f3e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009f3e0`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18009f3b3`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18009f3b3`

## string_xrefs

- `0x18009f965`: `onecoreuap\inetcore\urlmon\trans\common\ctransaction.cpp`

## pseudocode

```c
__int64 __fastcall EdgeTransaction::StartEx(
        EdgeTransaction *this,
        struct IUri *a2,
        struct IInternetProtocolSink *a3,
        struct IInternetBindInfo *a4,
        unsigned int a5)
{
  char *v9; // r13
  int v11; // esi
  __int64 v12; // r8
  __int64 v13; // r9
  struct _RTL_CRITICAL_SECTION *v14; // r12
  int v15; // edi
  int v16; // edi
  _DWORD *v17; // rax
  struct IInternetProtocolSink *v18; // rdx
  struct IUri *v19; // rdx
  struct IInternetBindInfo *v20; // r8
  void (__fastcall ***v21)(_QWORD, GUID *, struct IInternetProtocolSink **); // rcx
  struct IInternetProtocolSink *v22; // rcx
  const WCHAR *v23; // r8
  __int64 v24; // rcx
  _WORD *v25; // rax
  unsigned __int64 v26; // r9
  __int64 v27; // rcx
  const WCHAR *v28; // rax
  unsigned __int64 v29; // rdx
  struct IInternetProtocolSink *v30; // rcx
  void (__fastcall ***v31)(_QWORD, GUID *, struct IInternetProtocolSink **); // rcx
  struct IInternetProtocol **v32; // r15
  IID *v33; // rdi
  struct IUnknown **v34; // r14
  COInetSession *v35; // rdi
  unsigned int v36; // ecx
  __int64 v37; // rax
  int v38; // eax
  COInetSession *v39; // rdi
  const unsigned __int16 *v40; // rdx
  int v41; // eax
  struct IUnknown *v42; // rcx
  struct IInternetProtocol *v43; // rcx
  const OLECHAR *v44; // rcx
  struct IServiceProvider *v45; // r8
  struct IInternetProtocolSink *v46; // r12
  _QWORD *v47; // rdi
  __int64 v48; // rdi
  __int64 v49; // rcx
  struct IInternetProtocol *v50; // r12
  struct IUnknownVtbl *lpVtbl; // rax
  struct IInternetProtocol *v52; // rcx
  int v53; // eax
  char *v54; // r9
  char *v55; // r8
  int v56; // eax
  __int64 v57; // rcx
  struct IUnknown *v58; // rcx
  struct IUnknown *v59; // rcx
  struct IUnknown *v60; // r8
  const unsigned __int16 *v61; // rdx
  int v62; // eax
  struct IUnknown *v63; // rdi
  struct IInternetProtocolSink *v64; // rcx
  __int64 v65; // rax
  int v66; // eax
  unsigned int *v68; // r8
  char v69; // al
  int v70; // eax
  struct IInternetProtocolSink *v71; // rcx
  struct IUnknown *lpString2; // [rsp+20h] [rbp-A9h]
  unsigned __int64 cchCount2; // [rsp+28h] [rbp-A1h]
  char v74; // [rsp+40h] [rbp-89h] BYREF
  int v75; // [rsp+44h] [rbp-85h] BYREF
  struct IInternetProtocolSink *v76; // [rsp+48h] [rbp-81h] BYREF
  struct IUnknown *v77; // [rsp+50h] [rbp-79h]
  COInetSession *v78; // [rsp+58h] [rbp-71h]
  int v79; // [rsp+60h] [rbp-69h]
  unsigned int v80; // [rsp+64h] [rbp-65h] BYREF
  IID *rclsid; // [rsp+68h] [rbp-61h]
  LPOLESTR lpsz; // [rsp+70h] [rbp-59h] BYREF
  const OLECHAR *v83; // [rsp+78h] [rbp-51h] BYREF
  struct IInternetProtocolSink *v84; // [rsp+80h] [rbp-49h]
  __int64 v85; // [rsp+88h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v86; // [rsp+90h] [rbp-39h] BYREF
  const OLECHAR **v87; // [rsp+B0h] [rbp-19h]
  __int64 v88; // [rsp+B8h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+4Fh]

  v84 = a3;
  if ( (unsigned int)dword_180166000 > 5 && (qword_180166010 & 0x20) != 0 && (qword_180166018 & 0x20) == qword_180166018 )
  {
    v88 = 8;
    v83 = (const OLECHAR *)((char *)this - 48);
    v87 = &v83;
    tlgWriteTransfer_BrowserWriteTransfer((__int64)&dword_180166000, (unsigned __int8 *)&unk_180152CC8, 0, 0, 3u, &v86);
  }
  v9 = (char *)this - 48;
  if ( this == (EdgeTransaction *)48 )
    return 2147942487LL;
  v11 = -2147467259;
  if ( !EdgeTransaction::IsTerminated((EdgeTransaction *)((char *)this - 48)) )
  {
    v80 = 0;
    _InterlockedIncrement((volatile signed __int32 *)this + 26);
    if ( a2 && a4 && a3 )
    {
      v14 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1504);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1504));
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1504));
      v15 = *((_DWORD *)this + 80);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1504));
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1504));
      if ( v15 != 4 )
      {
        *((_BYTE *)this + 394) = *((_BYTE *)this + 394) & 0xFB | (a5 >> 20) & 4;
        if ( (a5 & 0x40000000) != 0 )
          *((_DWORD *)this + 93) |= 1u;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1504));
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1504));
        v16 = *((_DWORD *)this + 80);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1504));
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1504));
        if ( v16 == 2 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
          v17 = (_DWORD *)((char *)this + 368);
          if ( (a5 & 0x2000000) != 0 )
            *v17 |= 0x2000000u;
          if ( (a5 & 0x1000000) != 0 )
          {
            *((_DWORD *)this + 92) &= ~0x10000000u;
            *((_DWORD *)this + 92) |= 0x1000000u;
          }
          else if ( (a5 & 0x10000000) != 0 )
          {
            *v17 |= 0x10000000u;
            COInetProt::InitAttachedBindToObject((EdgeTransaction *)((char *)this + 736));
          }
          v18 = v84;
          *((_DWORD *)this + 177) = a5 & 0xFFFFFDCF;
          EdgeTransaction::SetClientSink((EdgeTransaction *)((char *)this - 48), v18, 0);
          EdgeTransaction::SetClientBindInfo((EdgeTransaction *)((char *)this - 48), a4);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
          v11 = CTransaction::OnAttach(
                  (EdgeTransaction *)((char *)this - 48),
                  v19,
                  v20,
                  v84,
                  (unsigned int)lpString2,
                  cchCount2);
          goto LABEL_148;
        }
        if ( (a5 & 0x8000) != 0 )
          *((_BYTE *)this + 393) &= ~0x20u;
        v76 = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1584));
        v21 = (void (__fastcall ***)(_QWORD, GUID *, struct IInternetProtocolSink **))*((_QWORD *)this + 203);
        if ( v21 )
          (**v21)(v21, &GUID_79eac9e5_baf9_11ce_8c82_00aa004ba90b, &v76);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1584));
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
        v11 = CTransaction::SetIUri((EdgeTransaction *)((char *)this - 48), a2);
        if ( v11 < 0 )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
          v22 = v76;
          if ( v76 )
          {
            v76 = 0;
            ((void (__fastcall *)(struct IInternetProtocolSink *))v22->lpVtbl->Release)(v22);
          }
          goto LABEL_148;
        }
        v78 = 0;
        EdgeTransaction::SetClientSink((EdgeTransaction *)((char *)this - 48), v84, 0);
        EdgeTransaction::SetClientBindInfo((EdgeTransaction *)((char *)this - 48), a4);
        if ( (a5 & 0x2000000) != 0 )
          *((_DWORD *)this + 92) |= 0x2000000u;
        *((_DWORD *)this + 177) = a5 & 0xFFFFFDCF;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
        if ( *((_DWORD *)this + 54) > 6u )
        {
          v23 = (const WCHAR *)*((_QWORD *)this + 26);
          if ( v23 )
          {
            v24 = 6;
            v25 = (_WORD *)*((_QWORD *)this + 26);
            do
            {
              if ( !*v25 )
                break;
              ++v25;
              --v24;
            }
            while ( v24 );
            v26 = 6 - v24;
            if ( !v24 || v26 > 0xFFFFFFFF )
              LODWORD(v26) = 6;
            v27 = 6;
            v28 = L"mhtml:";
            do
            {
              if ( !*v28 )
                break;
              ++v28;
              --v27;
            }
            while ( v27 );
            v29 = 6 - v27;
            if ( !v27 || v29 > 0xFFFFFFFF )
              LODWORD(v29) = 6;
            if ( CompareStringW(0x7Fu, 0x1001u, v23, v26, L"mhtml:", v29) == 2 )
              *((_BYTE *)this + 394) |= 2u;
          }
        }
        v30 = v76;
        if ( v76 )
        {
          v76 = 0;
          ((void (__fastcall *)(struct IInternetProtocolSink *))v30->lpVtbl->Release)(v30);
        }
        v76 = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1584));
        v31 = (void (__fastcall ***)(_QWORD, GUID *, struct IInternetProtocolSink **))*((_QWORD *)this + 203);
        if ( v31 )
          (**v31)(v31, &GUID_79eac9e5_baf9_11ce_8c82_00aa004ba90b, &v76);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1584));
        v32 = (struct IInternetProtocol **)((char *)this + 264);
        if ( !EdgeTransaction::QueryService(
                (EdgeTransaction *)((char *)this - 16),
                &IID_IInternetProtocol,
                &IID_IInternetProtocol,
                (void **)this + 33)
          && *v32 )
        {
          v33 = (IID *)((char *)this + 288);
          v79 = 0;
          rclsid = (IID *)((char *)this + 288);
          *((GUID *)this + 18) = CLSID_FtpProtocol;
          v34 = (struct IUnknown **)((char *)this + 96);
          v77 = 0;
          v75 = 0;
          while ( 1 )
          {
LABEL_71:
            v43 = *v32;
            v83 = 0;
            if ( ((__int64 (__fastcall *)(struct IInternetProtocol *, GUID *, const OLECHAR **))v43->lpVtbl->QueryInterface)(
                   v43,
                   &IID_ICrossApartmentProtocolHandler,
                   &v83) >= 0
              && (v44 = v83) != 0 )
            {
              *((_BYTE *)this + 395) |= 2u;
              (*(void (__fastcall **)(const OLECHAR *))(*(_QWORD *)v44 + 16LL))(v44);
            }
            else
            {
              *((_BYTE *)this + 395) &= ~2u;
            }
            lpsz = 0;
            if ( StringFromCLSID(v33, &lpsz) >= 0 )
            {
              ((void (__fastcall *)(struct IInternetProtocolSink *, __int64, LPOLESTR))v84->lpVtbl->ReportProgress)(
                v84,
                20,
                lpsz);
              CoTaskMemFree(lpsz);
            }
            EnterCriticalSection(v14);
            EnterCriticalSection(v14);
            LeaveCriticalSection(v14);
            *((_DWORD *)this + 80) = 2;
            LeaveCriticalSection(v14);
            if ( v75 )
            {
              v48 = *((_QWORD *)v9 + 39);
              if ( v48 )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v48 + 8LL))(*((_QWORD *)v9 + 39));
              v49 = *((_QWORD *)this + 106);
              if ( v49 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
              *((_QWORD *)this + 106) = v48;
              v47 = (_QWORD *)((char *)this + 168);
            }
            else
            {
              v46 = v84;
              v47 = (_QWORD *)((char *)this + 168);
              COInetProt::Initialize(
                (EdgeTransaction *)((char *)this + 736),
                (EdgeTransaction *)((char *)this - 48),
                v45,
                a5,
                lpString2,
                *v32,
                v84,
                *((struct IUri **)this + 21));
              EdgeTransaction::SetClientSink((EdgeTransaction *)((char *)this - 48), v46, 0);
              v75 = 1;
            }
            v50 = *v32;
            if ( *v34 )
            {
              lpVtbl = (*v34)->lpVtbl;
              v77 = *v34;
              ((void (*)(void))lpVtbl->AddRef)();
            }
            *((_BYTE *)this + 395) |= 0x20u;
            *v32 = (struct IInternetProtocol *)((char *)this + 736);
            CTransaction::SetProtocolPriority((EdgeTransaction *)((char *)this - 48));
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
            *((_BYTE *)this + 394) |= 0x10u;
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
            v52 = *v32;
            v85 = 0;
            v53 = ((__int64 (__fastcall *)(struct IInternetProtocol *, GUID *, __int64 *))v52->lpVtbl->QueryInterface)(
                    v52,
                    &IID_IInternetProtocolEx,
                    &v85);
            v54 = (char *)this - 32;
            v55 = (char *)this - 48;
            if ( v53 < 0 )
              v56 = ((__int64 (__fastcall *)(struct IInternetProtocol *, _QWORD, char *, char *, _DWORD, _QWORD))(*v32)->lpVtbl->Start)(
                      *v32,
                      *((_QWORD *)this + 26),
                      v55,
                      v54,
                      0,
                      0);
            else
              v56 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *, char *, _DWORD, _QWORD))(*(_QWORD *)v85 + 104LL))(
                      v85,
                      *v47,
                      v55,
                      v54,
                      0,
                      0);
            v11 = v56;
            if ( v85 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
              v85 = 0;
            }
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
            *((_BYTE *)this + 394) &= ~0x10u;
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
            if ( (*((_BYTE *)this + 394) & 0x20) != 0 )
              break;
            if ( v11 == -2147483638 )
            {
              v11 = 0;
              goto LABEL_128;
            }
            if ( v11 != -2146697199 )
            {
              if ( v11 )
              {
                *((_BYTE *)this + 392) |= 4u;
                if ( *v32 )
                {
                  if ( (*((_BYTE *)this + 393) & 2) == 0 )
                  {
                    v64 = v76;
                    if ( v76 )
                    {
                      v76 = 0;
                      ((void (__fastcall *)(struct IInternetProtocolSink *))v64->lpVtbl->Release)(v64);
                    }
                    EdgeTransaction::GetClientSink((EdgeTransaction *)((char *)this - 48), &v76);
                    *((_BYTE *)this + 393) |= 1u;
                    if ( !*((_DWORD *)this + 103) && (v11 == -2146697190 || IsDualEngineProcess() && v11 == -2146697182) )
                      goto LABEL_121;
                    v75 = 1;
                    lpsz = (LPOLESTR)&v74;
                    v65 = *((_QWORD *)this + 9);
                    v74 = 0;
                    v66 = (*(__int64 (__fastcall **)(char *, __int64, LPOLESTR *, int *))(v65 + 32))(
                            (char *)this + 72,
                            3,
                            &lpsz,
                            &v75);
                    if ( !v66 && v75 != 1 )
                      wil::details::in1diag3::_FailFast_Unexpected(
                        retaddr,
                        (void *)0xD6B,
                        (unsigned int)"onecoreuap\\inetcore\\urlmon\\trans\\common\\ctransaction.cpp",
                        (const char *)retaddr);
                    if ( !v66 && v74 )
                    {
LABEL_121:
                      v68 = (unsigned int *)((char *)this + 416);
                      *((_DWORD *)this + 103) = v11;
                      *((_DWORD *)this + 104) = 12017;
                    }
                    else
                    {
                      v68 = (unsigned int *)((char *)this + 416);
                    }
                    ((void (__fastcall *)(struct IInternetProtocolSink *, _QWORD, _QWORD, _QWORD))v76->lpVtbl->ReportResult)(
                      v76,
                      *((unsigned int *)this + 103),
                      *v68,
                      0);
                    EdgeTransaction::Terminate(this, 0);
                  }
                }
              }
              goto LABEL_128;
            }
            v57 = *((_QWORD *)this + 106);
            if ( v57 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
            *((_QWORD *)this + 106) = 0;
            if ( v50 )
            {
              ((void (__fastcall *)(struct IInternetProtocol *))v50->lpVtbl->Release)(v50);
              v50 = 0;
            }
            v58 = *v34;
            *v32 = 0;
            if ( v58 )
            {
              ((void (__fastcall *)(struct IUnknown *))v58->lpVtbl->Release)(v58);
              v59 = v77;
              *v34 = 0;
              ((void (__fastcall *)(struct IUnknown *))v59->lpVtbl->Release)(v59);
              v77 = 0;
            }
            v60 = (struct IUnknown *)((char *)this - 32);
            v33 = rclsid;
            v61 = (const unsigned __int16 *)*((_QWORD *)this + 26);
            if ( v79 )
            {
              v62 = COInetSession::CreateNextProtocol(
                      v78,
                      v61,
                      v60,
                      v34,
                      (struct IInternetProtocol **)this + 33,
                      rclsid,
                      &v80);
            }
            else
            {
              v62 = COInetSession::CreateFirstProtocol(
                      v78,
                      v61,
                      v60,
                      v34,
                      (struct IInternetProtocol **)this + 33,
                      rclsid,
                      &v80,
                      (unsigned __int8)(*((_BYTE *)this + 394) & 4) << 20);
              v79 = 1;
            }
            v11 = v62;
            if ( v62 )
            {
              *v32 = 0;
              v63 = 0;
              *v34 = 0;
              goto LABEL_129;
            }
            v14 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1504);
          }
          if ( v11 || *((char *)this + 392) >= 0 )
            v11 = EdgeTransaction::Abort(this, *((_DWORD *)this + 100), *((_DWORD *)this + 101));
LABEL_128:
          v63 = v77;
LABEL_129:
          if ( v50 )
            ((void (__fastcall *)(struct IInternetProtocol *))v50->lpVtbl->Release)(v50);
          if ( v63 )
            ((void (__fastcall *)(struct IUnknown *))v63->lpVtbl->Release)(v63);
          if ( (a5 & 0x80u) != 0 && v11 >= 0 )
          {
            v69 = *((_BYTE *)this + 394);
            if ( (v69 & 1) == 0 )
            {
              *((_BYTE *)this + 394) = v69 | 1;
              v70 = EdgeTransaction::CompleteOperation((EdgeTransaction *)((char *)this - 48), a5 & 0x11000000);
              *((_BYTE *)this + 394) &= ~1u;
              v11 = v70;
            }
          }
          v71 = v76;
          if ( !v76 )
            goto LABEL_145;
          v76 = 0;
          goto LABEL_144;
        }
        EnterCriticalSection(&g_mxsOInet);
        v35 = g_pCOInetSession;
        if ( g_pCOInetSession )
        {
          v11 = 0;
        }
        else
        {
          v35 = (COInetSession *)CoTaskMemAlloc(0x180u);
          v11 = -2147024882;
          if ( v35 )
          {
            *((_DWORD *)v35 + 5) = 0;
            memset_0((char *)v35 + 40, 0, 0x158u);
            *(_QWORD *)v35 = &COInetSession::`vftable'{for `IInternetSession'};
            *((_DWORD *)v35 + 4) = 1;
            *((_QWORD *)v35 + 1) = &COInetSession::`vftable'{for `IInternetProtocolInfo'};
            *((_QWORD *)v35 + 3) = &CProtMgr::`vftable';
            *((_DWORD *)v35 + 8) = 1;
            *((_DWORD *)v35 + 9) = -1;
            InitializeCriticalSection((LPCRITICAL_SECTION)v35 + 1);
            *((_QWORD *)v35 + 11) = 0;
            *((_QWORD *)v35 + 10) = 0;
            *((_QWORD *)v35 + 12) = &CProtMgr::`vftable';
            *((_DWORD *)v35 + 26) = 1;
            *((_DWORD *)v35 + 27) = -1;
            InitializeCriticalSection((LPCRITICAL_SECTION)((char *)v35 + 112));
            *((_QWORD *)v35 + 20) = 0;
            *((_QWORD *)v35 + 19) = 0;
            *((_QWORD *)v35 + 21) = 0;
            *((_DWORD *)v35 + 27) = 0;
            *((_QWORD *)v35 + 12) = &CProtMgrNameSpace::`vftable';
            *((_QWORD *)v35 + 22) = &CProtMgr::`vftable';
            *((_DWORD *)v35 + 46) = 1;
            *((_DWORD *)v35 + 47) = -1;
            InitializeCriticalSection((LPCRITICAL_SECTION)((char *)v35 + 192));
            *((_QWORD *)v35 + 30) = 0;
            v36 = 0;
            *((_QWORD *)v35 + 29) = 0;
            *((_QWORD *)v35 + 22) = &CProtMgrMimeHandler::`vftable';
            *((_DWORD *)v35 + 62) = 8;
            do
            {
              v37 = v36++;
              *((_QWORD *)v35 + 2 * v37 + 33) = 0;
            }
            while ( v36 < *((_DWORD *)v35 + 62) );
            _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
            v38 = 0;
            g_pCOInetSession = v35;
          }
          else
          {
            v35 = g_pCOInetSession;
            v38 = -2147024882;
          }
          if ( !v35 )
          {
            LeaveCriticalSection(&g_mxsOInet);
            goto LABEL_141;
          }
          v11 = v38;
        }
        _InterlockedIncrement((volatile signed __int32 *)v35 + 4);
        v39 = g_pCOInetSession;
        v78 = g_pCOInetSession;
        LeaveCriticalSection(&g_mxsOInet);
        if ( !v11 )
        {
          v40 = (const unsigned __int16 *)*((_QWORD *)this + 26);
          v34 = (struct IUnknown **)((char *)this + 96);
          v41 = *((_BYTE *)this + 394) & 4;
          rclsid = (IID *)((char *)this + 288);
          v11 = COInetSession::CreateFirstProtocol(
                  v39,
                  v40,
                  (struct IUnknown *)this - 4,
                  (struct IUnknown **)this + 12,
                  (struct IInternetProtocol **)this + 33,
                  (IID *)this + 18,
                  &v80,
                  v41 << 20);
          if ( !v11 )
          {
            v42 = *v34;
            v79 = 1;
            if ( v42 && *((_DWORD *)this + 364) == 1 )
            {
              IUnknown_EnablePreBinding(v42, 1);
              v33 = (IID *)((char *)this + 288);
              v77 = 0;
              v75 = 0;
            }
            else
            {
              v78 = v39;
              v33 = (IID *)((char *)this + 288);
              rclsid = (IID *)((char *)this + 288);
              v77 = 0;
              v75 = 0;
            }
            goto LABEL_71;
          }
          v78 = v39;
          goto LABEL_142;
        }
        v78 = v39;
LABEL_141:
        v34 = (struct IUnknown **)((char *)this + 96);
LABEL_142:
        v71 = v76;
        *v32 = 0;
        *v34 = 0;
        if ( !v71 )
          goto LABEL_145;
        v76 = 0;
LABEL_144:
        ((void (__fastcall *)(struct IInternetProtocolSink *))v71->lpVtbl->Release)(v71);
LABEL_145:
        if ( v78 )
          _InterlockedDecrement((volatile signed __int32 *)v78 + 4);
      }
    }
    else
    {
      v11 = -2147024809;
    }
LABEL_148:
    if ( (unsigned int)dword_180166000 > 5
      && (qword_180166010 & 0x20) != 0
      && (qword_180166018 & 0x20) == qword_180166018 )
    {
      v83 = (const OLECHAR *)*((_QWORD *)this + 26);
      v75 = v11;
      lpsz = (LPOLESTR)((char *)this - 48);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        qword_180166018,
        (unsigned __int8 *)byte_180152C75,
        v12,
        v13,
        (__int64)&lpsz,
        (__int64)&v75,
        &v83);
    }
    CTransaction::Release((EdgeTransaction *)((char *)this - 48));
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18009ebd0  push    rbp
0x18009ebd2  push    rbx
0x18009ebd3  push    rdi
0x18009ebd4  push    r12
0x18009ebd6  push    r13
0x18009ebd8  push    r14
0x18009ebda  push    r15
0x18009ebdc  lea     rbp, [rsp-17h]
0x18009ebe1  sub     rsp, 0E0h
0x18009ebe8  mov     rax, cs:__security_cookie
0x18009ebef  xor     rax, rsp
0x18009ebf2  mov     [rbp+47h+var_50], rax
0x18009ebf6  mov     eax, cs:dword_180166000
0x18009ebfc  xor     r12d, r12d
0x18009ebff  mov     [rbp+47h+var_90], r8
0x18009ec03  mov     r14, r9
0x18009ec06  mov     rdi, r8
0x18009ec09  mov     r15, rdx
0x18009ec0c  mov     rbx, rcx
0x18009ec0f  cmp     eax, 5
0x18009ec12  jbe     short loc_18009EC73
0x18009ec14  mov     rcx, cs:qword_180166018
0x18009ec1b  mov     rax, cs:qword_180166010
0x18009ec22  test    al, 20h
0x18009ec24  jz      short loc_18009EC73
0x18009ec26  mov     rax, rcx
0x18009ec29  and     eax, 20h
0x18009ec2c  cmp     rax, rcx
0x18009ec2f  jnz     short loc_18009EC73
0x18009ec31  lea     rax, [rbx-30h]
0x18009ec35  mov     [rbp+47h+var_58], 8
0x18009ec3d  mov     [rbp+47h+var_98], rax
0x18009ec41  lea     rdx, unk_180152CC8
0x18009ec48  lea     rax, [rbp+47h+var_98]
0x18009ec4c  xor     r9d, r9d
0x18009ec4f  mov     [rbp+47h+var_60], rax
0x18009ec53  lea     rcx, dword_180166000
0x18009ec5a  lea     rax, [rbp+47h+var_80]
0x18009ec5e  xor     r8d, r8d
0x18009ec61  mov     qword ptr [rsp+110h+cchCount2], rax; unsigned __int64
0x18009ec66  mov     dword ptr [rsp+110h+lpString2], 3; unsigned int
0x18009ec6e  call    _tlgWriteTransfer_BrowserWriteTransfer
0x18009ec73  lea     r13, [rbx-30h]
0x18009ec77  mov     [rsp+110h+var_38], rsi
0x18009ec7f  test    r13, r13
0x18009ec82  jnz     short loc_18009EC8E
0x18009ec84  mov     eax, 80070057h
0x18009ec89  jmp     loc_18009F93D
0x18009ec8e  mov     rcx, r13; this
0x18009ec91  mov     esi, 80004005h
0x18009ec96  call    ?IsTerminated@EdgeTransaction@@AEAA_NXZ; EdgeTransaction::IsTerminated(void)
0x18009ec9b  test    al, al
0x18009ec9d  jnz     loc_18009F93B
0x18009eca3  mov     [rbp+47h+var_AC], r12d
0x18009eca7  lock inc dword ptr [rbx+68h]
0x18009ecab  test    r15, r15
0x18009ecae  jz      loc_18009F8CB
0x18009ecb4  test    r14, r14
0x18009ecb7  jz      loc_18009F8CB
0x18009ecbd  test    rdi, rdi
0x18009ecc0  jz      loc_18009F8CB
0x18009ecc6  lea     r12, [rbx+5E0h]
0x18009eccd  mov     rcx, r12; lpCriticalSection
0x18009ecd0  call    cs:__imp_EnterCriticalSection
0x18009ecd7  nop     dword ptr [rax+rax+00h]
0x18009ecdc  mov     rcx, r12; lpCriticalSection
0x18009ecdf  call    cs:__imp_EnterCriticalSection
0x18009ece6  nop     dword ptr [rax+rax+00h]
0x18009eceb  mov     edi, [rbx+140h]
0x18009ecf1  mov     rcx, r12; lpCriticalSection
0x18009ecf4  call    cs:__imp_LeaveCriticalSection
0x18009ecfb  nop     dword ptr [rax+rax+00h]
0x18009ed00  mov     rcx, r12; lpCriticalSection
0x18009ed03  call    cs:__imp_LeaveCriticalSection
0x18009ed0a  nop     dword ptr [rax+rax+00h]
0x18009ed0f  cmp     edi, 4
0x18009ed12  jz      loc_18009F8D0
0x18009ed18  mov     esi, [rbp+47h+arg_20]
0x18009ed1b  mov     ecx, esi
0x18009ed1d  movzx   eax, byte ptr [rbx+18Ah]
0x18009ed24  shr     ecx, 14h
0x18009ed27  and     al, 0FBh
0x18009ed29  and     cl, 4
0x18009ed2c  or      cl, al
0x18009ed2e  mov     [rbx+18Ah], cl
0x18009ed34  bt      esi, 1Eh
0x18009ed38  jnb     short loc_18009ED41
0x18009ed3a  or      dword ptr [rbx+174h], 1
0x18009ed41  mov     rcx, r12; lpCriticalSection
0x18009ed44  call    cs:__imp_EnterCriticalSection
0x18009ed4b  nop     dword ptr [rax+rax+00h]
0x18009ed50  mov     rcx, r12; lpCriticalSection
0x18009ed53  call    cs:__imp_EnterCriticalSection
0x18009ed5a  nop     dword ptr [rax+rax+00h]
0x18009ed5f  mov     edi, [rbx+140h]
0x18009ed65  mov     rcx, r12; lpCriticalSection
0x18009ed68  call    cs:__imp_LeaveCriticalSection
0x18009ed6f  nop     dword ptr [rax+rax+00h]
0x18009ed74  mov     rcx, r12; lpCriticalSection
0x18009ed77  call    cs:__imp_LeaveCriticalSection
0x18009ed7e  nop     dword ptr [rax+rax+00h]
0x18009ed83  cmp     edi, 2
0x18009ed86  jnz     loc_18009EE32
0x18009ed8c  lea     rcx, [rbx+240h]; lpCriticalSection
0x18009ed93  call    cs:__imp_EnterCriticalSection
0x18009ed9a  nop     dword ptr [rax+rax+00h]
0x18009ed9f  lea     rax, [rbx+170h]
0x18009eda6  bt      esi, 19h
0x18009edaa  jnb     short loc_18009EDB2
0x18009edac  or      dword ptr [rax], 2000000h
0x18009edb2  bt      esi, 18h
0x18009edb6  jnb     short loc_18009EDCE
0x18009edb8  and     dword ptr [rbx+170h], 0EFFFFFFFh
0x18009edc2  or      dword ptr [rbx+170h], 1000000h
0x18009edcc  jmp     short loc_18009EDE6
0x18009edce  bt      esi, 1Ch
0x18009edd2  jnb     short loc_18009EDE6
0x18009edd4  or      dword ptr [rax], 10000000h
0x18009edda  lea     rcx, [rbx+2E0h]; this
0x18009ede1  call    ?InitAttachedBindToObject@COInetProt@@QEAAXXZ; COInetProt::InitAttachedBindToObject(void)
0x18009ede6  mov     rdx, [rbp+47h+var_90]; struct IInternetProtocolSink *
0x18009edea  and     esi, 0FFFFFDCFh
0x18009edf0  xor     r8d, r8d; bool
0x18009edf3  mov     [rbx+2C4h], esi
0x18009edf9  mov     rcx, r13; this
0x18009edfc  call    ?SetClientSink@EdgeTransaction@@MEAAXPEAUIInternetProtocolSink@@_N@Z; EdgeTransaction::SetClientSink(IInternetProtocolSink *,bool)
0x18009ee01  mov     rdx, r14; struct IInternetBindInfo *
0x18009ee04  mov     rcx, r13; this
0x18009ee07  call    ?SetClientBindInfo@EdgeTransaction@@MEAAXPEAUIInternetBindInfo@@@Z; EdgeTransaction::SetClientBindInfo(IInternetBindInfo *)
0x18009ee0c  lea     rcx, [rbx+240h]; lpCriticalSection
0x18009ee13  call    cs:__imp_LeaveCriticalSection
0x18009ee1a  nop     dword ptr [rax+rax+00h]
0x18009ee1f  mov     r9, [rbp+47h+var_90]; struct IInternetProtocolSink *
0x18009ee23  mov     rcx, r13; this
0x18009ee26  call    ?OnAttach@CTransaction@@QEAAJPEAUIUri@@PEAUIInternetBindInfo@@PEAUIInternetProtocolSink@@K_K@Z; CTransaction::OnAttach(IUri *,IInternetBindInfo *,IInternetProtocolSink *,ulong,unsigned __int64)
0x18009ee2b  mov     esi, eax
0x18009ee2d  jmp     loc_18009F8D0
0x18009ee32  bt      esi, 0Fh
0x18009ee36  jnb     short loc_18009EE3F
0x18009ee38  and     byte ptr [rbx+189h], 0DFh
0x18009ee3f  lea     rcx, [rbx+630h]; lpCriticalSection
0x18009ee46  mov     [rsp+110h+var_C8], 0
0x18009ee4f  call    cs:__imp_EnterCriticalSection
0x18009ee56  nop     dword ptr [rax+rax+00h]
0x18009ee5b  mov     rcx, [rbx+658h]
0x18009ee62  test    rcx, rcx
0x18009ee65  jz      short loc_18009EE7E
0x18009ee67  mov     rax, [rcx]
0x18009ee6a  lea     r8, [rsp+110h+var_C8]
0x18009ee6f  lea     rdx, _GUID_79eac9e5_baf9_11ce_8c82_00aa004ba90b
0x18009ee76  mov     rax, [rax]
0x18009ee79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ee7e  lea     rcx, [rbx+630h]; lpCriticalSection
0x18009ee85  call    cs:__imp_LeaveCriticalSection
0x18009ee8c  nop     dword ptr [rax+rax+00h]
0x18009ee91  lea     rcx, [rbx+240h]; lpCriticalSection
0x18009ee98  call    cs:__imp_EnterCriticalSection
0x18009ee9f  nop     dword ptr [rax+rax+00h]
0x18009eea4  mov     rdx, r15; struct IUri *
0x18009eea7  mov     rcx, r13; this
0x18009eeaa  call    ?SetIUri@CTransaction@@QEAAJPEAUIUri@@@Z; CTransaction::SetIUri(IUri *)
0x18009eeaf  mov     esi, eax
0x18009eeb1  test    eax, eax
0x18009eeb3  jns     short loc_18009EEF0
0x18009eeb5  lea     rcx, [rbx+240h]; lpCriticalSection
0x18009eebc  call    cs:__imp_LeaveCriticalSection
0x18009eec3  nop     dword ptr [rax+rax+00h]
0x18009eec8  mov     rcx, [rsp+110h+var_C8]
0x18009eecd  test    rcx, rcx
0x18009eed0  jz      loc_18009F8D0
0x18009eed6  mov     [rsp+110h+var_C8], 0
0x18009eedf  mov     rax, [rcx]
0x18009eee2  mov     rax, [rax+10h]
0x18009eee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eeeb  jmp     loc_18009F8D0
0x18009eef0  mov     rdx, [rbp+47h+var_90]; struct IInternetProtocolSink *
0x18009eef4  xor     r8d, r8d; bool
0x18009eef7  mov     rcx, r13; this
0x18009eefa  mov     [rbp+47h+var_B8], 0
0x18009ef02  call    ?SetClientSink@EdgeTransaction@@MEAAXPEAUIInternetProtocolSink@@_N@Z; EdgeTransaction::SetClientSink(IInternetProtocolSink *,bool)
0x18009ef07  mov     rdx, r14; struct IInternetBindInfo *
0x18009ef0a  mov     rcx, r13; this
0x18009ef0d  call    ?SetClientBindInfo@EdgeTransaction@@MEAAXPEAUIInternetBindInfo@@@Z; EdgeTransaction::SetClientBindInfo(IInternetBindInfo *)
0x18009ef12  mov     eax, [rbp+47h+arg_20]
0x18009ef15  bt      eax, 19h
0x18009ef19  jnb     short loc_18009EF25
0x18009ef1b  or      dword ptr [rbx+170h], 2000000h
0x18009ef25  and     eax, 0FFFFFDCFh
0x18009ef2a  lea     rcx, [rbx+240h]; lpCriticalSection
0x18009ef31  mov     [rbx+2C4h], eax
0x18009ef37  call    cs:__imp_LeaveCriticalSection
0x18009ef3e  nop     dword ptr [rax+rax+00h]
0x18009ef43  cmp     dword ptr [rbx+0D8h], 6
0x18009ef4a  jbe     loc_18009F008
0x18009ef50  mov     r8, [rbx+0D0h]; lpString1
0x18009ef57  test    r8, r8
0x18009ef5a  jz      loc_18009F008
0x18009ef60  mov     ecx, 6
0x18009ef65  mov     rax, r8
0x18009ef68  cmp     word ptr [rax], 0
0x18009ef6c  jz      short loc_18009EF78
0x18009ef6e  add     rax, 2
0x18009ef72  sub     rcx, 1
0x18009ef76  jnz     short loc_18009EF68
0x18009ef78  xor     r14d, r14d
0x18009ef7b  mov     r9d, 6
0x18009ef81  sub     r9, rcx
0x18009ef84  mov     r10d, 0FFFFFFFFh
0x18009ef8a  test    rcx, rcx
0x18009ef8d  cmovz   r9, r14
0x18009ef91  jz      short loc_18009EF98
0x18009ef93  cmp     r9, r10
0x18009ef96  jbe     short loc_18009EF9E
0x18009ef98  mov     r9d, 6; cchCount1
0x18009ef9e  lea     r11, aMhtml_1; "mhtml:"
0x18009efa5  mov     ecx, 6
0x18009efaa  mov     rax, r11
0x18009efad  nop     dword ptr [rax]
0x18009efb0  cmp     [rax], r14w
0x18009efb4  jz      short loc_18009EFC0
0x18009efb6  add     rax, 2
0x18009efba  sub     rcx, 1
0x18009efbe  jnz     short loc_18009EFB0
0x18009efc0  mov     edx, 6
0x18009efc5  sub     rdx, rcx
0x18009efc8  test    rcx, rcx
0x18009efcb  cmovz   rdx, r14
0x18009efcf  jz      short loc_18009EFD6
0x18009efd1  cmp     rdx, r10
0x18009efd4  jbe     short loc_18009EFDB
0x18009efd6  mov     edx, 6
0x18009efdb  mov     [rsp+110h+cchCount2], edx; cchCount2
0x18009efdf  mov     ecx, 7Fh; Locale
0x18009efe4  mov     edx, 1001h; dwCmpFlags
0x18009efe9  mov     [rsp+110h+lpString2], r11; lpString2
0x18009efee  call    cs:__imp_CompareStringW
0x18009eff5  nop     dword ptr [rax+rax+00h]
0x18009effa  add     eax, 0FFFFFFFEh
0x18009effd  jnz     short loc_18009F00B
0x18009efff  or      byte ptr [rbx+18Ah], 2
0x18009f006  jmp     short loc_18009F00B
0x18009f008  xor     r14d, r14d
0x18009f00b  mov     rcx, [rsp+110h+var_C8]
0x18009f010  test    rcx, rcx
0x18009f013  jz      short loc_18009F026
0x18009f015  mov     [rsp+110h+var_C8], r14
0x18009f01a  mov     rax, [rcx]
0x18009f01d  mov     rax, [rax+10h]
0x18009f021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f026  lea     rcx, [rbx+630h]; lpCriticalSection
0x18009f02d  mov     [rsp+110h+var_C8], r14
0x18009f032  call    cs:__imp_EnterCriticalSection
0x18009f039  nop     dword ptr [rax+rax+00h]
0x18009f03e  mov     rcx, [rbx+658h]
0x18009f045  test    rcx, rcx
0x18009f048  jz      short loc_18009F061
0x18009f04a  mov     rax, [rcx]
0x18009f04d  lea     r8, [rsp+110h+var_C8]
0x18009f052  lea     rdx, _GUID_79eac9e5_baf9_11ce_8c82_00aa004ba90b
0x18009f059  mov     rax, [rax]
0x18009f05c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f061  lea     rcx, [rbx+630h]; lpCriticalSection
0x18009f068  call    cs:__imp_LeaveCriticalSection
0x18009f06f  nop     dword ptr [rax+rax+00h]
0x18009f074  lea     r15, [rbx+108h]
0x18009f07b  mov     r9, r15; void **
0x18009f07e  lea     rcx, [rbx-10h]; this
0x18009f082  lea     r8, IID_IInternetProtocol; struct _GUID *
0x18009f089  lea     rdx, IID_IInternetProtocol; struct _GUID *
0x18009f090  call    ?QueryService@EdgeTransaction@@UEAAJAEBU_GUID@@0PEAPEAX@Z; EdgeTransaction::QueryService(_GUID const &,_GUID const &,void * *)
0x18009f095  test    eax, eax
0x18009f097  jnz     short loc_18009F0CB
0x18009f099  cmp     qword ptr [r15], 0
0x18009f09d  jz      short loc_18009F0CB
0x18009f09f  movups  xmm0, xmmword ptr cs:CLSID_FtpProtocol.Data1
0x18009f0a6  lea     rdi, [rbx+120h]
0x18009f0ad  mov     [rbp+47h+var_B0], r14d
0x18009f0b1  xor     eax, eax
0x18009f0b3  mov     [rbp+47h+rclsid], rdi
0x18009f0b7  movups  xmmword ptr [rdi], xmm0
0x18009f0ba  lea     r14, [rbx+60h]
0x18009f0be  mov     [rbp+47h+var_C0], rax
0x18009f0c2  mov     [rsp+110h+var_CC], eax
0x18009f0c6  jmp     loc_18009F357
0x18009f0cb  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x18009f0d2  call    cs:__imp_EnterCriticalSection
0x18009f0d9  nop     dword ptr [rax+rax+00h]
0x18009f0de  mov     rdi, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x18009f0e5  test    rdi, rdi
0x18009f0e8  jnz     loc_18009F274
0x18009f0ee  mov     ecx, 180h; cb
0x18009f0f3  call    cs:__imp_CoTaskMemAlloc
0x18009f0fa  nop     dword ptr [rax+rax+00h]
0x18009f0ff  mov     rdi, rax
0x18009f102  mov     esi, 8007000Eh
0x18009f107  test    rax, rax
0x18009f10a  jz      loc_18009F24A
0x18009f110  xor     eax, eax
0x18009f112  lea     rcx, [rdi+28h]; void *
0x18009f116  xor     edx, edx; Val
  ... truncated ...
```
