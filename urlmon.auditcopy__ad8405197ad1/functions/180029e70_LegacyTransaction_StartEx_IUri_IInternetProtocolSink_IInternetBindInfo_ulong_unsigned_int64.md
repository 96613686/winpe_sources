# LegacyTransaction::StartEx(IUri *,IInternetProtocolSink *,IInternetBindInfo *,ulong,unsigned __int64)

- ea: `0x180029e70`
- end: `0x18002af16`
- name: `?StartEx@LegacyTransaction@@UEAAJPEAUIUri@@PEAUIInternetProtocolSink@@PEAUIInternetBindInfo@@K_K@Z`
- size: `4262`
- prototype: `__int64 __fastcall(LegacyTransaction *this, struct IUri *, struct IInternetProtocolSink *, struct IInternetBindInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f9510`

## callees

- `0x180008b2c`
- `0x18001db50`
- `0x18001db94`
- `0x180029e70`
- `0x18002b290`
- `0x18002bb64`
- `0x180031480`
- `0x180043018`
- `0x180048100`
- `0x180048854`
- `0x18004bec4`
- `0x18006cd48`
- `0x18006f330`
- `0x180074750`
- `0x180076b40`
- `0x1800803d8`
- `0x180084eb0`
- `0x180088604`
- `0x180094900`
- `0x1800969fc`
- `0x1800f20a0`
- `0x1800f5af4`
- `0x1800f8850`
- `0x1801285e6`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `msvcrt!wcschr` at `0x18002a382`
- `msvcrt!wcschr` at `0x18002a382`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a031`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a098`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a12c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a264`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a2e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a4ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a71a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a7fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a8b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a957`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002aa6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ab10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002abd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ac75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002aca4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a031`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a098`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a12c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a264`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a2e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a4ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a71a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a7fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a8b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a957`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002aa6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ab10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002abd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ac75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002aca4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029f33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a011`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a052`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a23a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a2b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a6cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a7ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a896`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a93d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002aaf5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ab48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029f33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a011`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a052`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a23a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a2b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a6cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a7ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a896`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a93d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002aaf5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ab48`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a201`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a201`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a686`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a792`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002add4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a686`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a792`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002add4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002a659`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002a659`
- `OLEAUT32!__imp_SysFreeString` at `0x18002abfa`
- `OLEAUT32!__imp_SysFreeString` at `0x18002abfa`
- `OLEAUT32!__imp_SysStringLen` at `0x18002ac39`
- `OLEAUT32!__imp_SysStringLen` at `0x18002ac39`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18002a288`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18002a288`

## pseudocode

```c
__int64 __fastcall LegacyTransaction::StartEx(
        LegacyTransaction *this,
        struct IUri *a2,
        struct IInternetProtocolSink *a3,
        struct IInternetBindInfo *a4,
        unsigned int a5)
{
  LegacyTransaction *v5; // r13
  int v10; // ecx
  unsigned int v11; // r14d
  struct _RTL_CRITICAL_SECTION *v12; // r12
  struct IUri *v13; // rcx
  int v14; // ebx
  __int64 v15; // r14
  __int64 v16; // r12
  int v17; // r13d
  OLECHAR *v18; // rcx
  __int64 v19; // rcx
  IUnknown **v20; // rsi
  char *v21; // rbx
  __int64 v22; // rcx
  IUnknown *v23; // rcx
  __int64 v24; // rcx
  const WCHAR *v25; // r14
  int cchCount2; // ebx
  __int64 v27; // rdx
  const WCHAR *v28; // rax
  int v29; // eax
  int v30; // r15d
  __int64 v31; // rdx
  const WCHAR *v32; // rax
  int v33; // eax
  struct _RTL_CRITICAL_SECTION *v34; // rcx
  IUnknown *v35; // rbx
  HRESULT Service; // esi
  bool v37; // zf
  COInetSession *v38; // rax
  COInetSession *v39; // r12
  wchar_t *v40; // r8
  wchar_t *v41; // rdx
  int v42; // ebx
  int v43; // esi
  __int64 v44; // rcx
  unsigned int v45; // r14d
  __int64 v46; // r9
  wchar_t *v47; // rcx
  wchar_t *v48; // rax
  __int64 v49; // r14
  int v51; // eax
  __int64 v52; // rdx
  COInetSession *v53; // rax
  int v54; // ecx
  struct IUnknown *v55; // rcx
  __int64 v56; // r15
  int v57; // r12d
  int (__fastcall ***v58)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v59; // rbx
  struct IUri *v60; // rsi
  struct _RTL_CRITICAL_SECTION *v61; // rcx
  struct IInternetProtocolSink *v62; // r12
  __int64 v63; // rcx
  struct _RTL_CRITICAL_SECTION *v64; // r12
  __int64 v65; // rcx
  int v66; // eax
  void *v67; // rcx
  void *v68; // rcx
  char *v69; // rbx
  __int64 v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rsi
  __int64 (__fastcall ***v73)(_QWORD, GUID *, struct IClassFactory **); // rcx
  int v74; // eax
  char *v75; // r9
  int v76; // eax
  __int64 v77; // rcx
  char v78; // al
  int v79; // eax
  char v80; // al
  IUnknown *v81; // rbx
  _DWORD *v82; // rax
  struct IUri *v83; // rdx
  OLECHAR *v84; // r8
  OLECHAR *v85; // rcx
  int v86; // esi
  __int64 (__fastcall ***v87)(_QWORD, GUID *, char *); // rcx
  __int64 v88; // rcx
  __int64 v89; // rcx
  struct IUnknown *v90; // r8
  unsigned __int16 *v91; // rdx
  struct IUnknown **v92; // r9
  int v93; // eax
  struct IClassFactory *v94; // [rsp+40h] [rbp-89h] BYREF
  unsigned int v95; // [rsp+48h] [rbp-81h] BYREF
  COInetSession *v96; // [rsp+50h] [rbp-79h] BYREF
  int v97; // [rsp+58h] [rbp-71h]
  int cchCount1[2]; // [rsp+68h] [rbp-61h] BYREF
  struct IInternetProtocolSink *v99; // [rsp+70h] [rbp-59h]
  __int64 v100; // [rsp+78h] [rbp-51h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+80h] [rbp-49h]
  wchar_t Str[32]; // [rsp+90h] [rbp-39h] BYREF

  v5 = (LegacyTransaction *)((char *)this - 48);
  v99 = a3;
  if ( this != (LegacyTransaction *)48 )
  {
    v95 = 0;
    _InterlockedIncrement((volatile signed __int32 *)this + 26);
    if ( a2 && a4 && a3 )
    {
      v10 = *((_DWORD *)v5 + 92);
      if ( v10 == 4 )
      {
        v14 = -2147467259;
      }
      else
      {
        v11 = a5;
        *((_BYTE *)this + 394) &= ~4u;
        *((_BYTE *)this + 394) |= (a5 >> 20) & 4;
        if ( (a5 & 0x40000000) != 0 )
          *((_DWORD *)this + 93) |= 1u;
        if ( v10 == 2 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
          v82 = (_DWORD *)((char *)this + 368);
          if ( (a5 & 0x2000000) != 0 )
            *v82 |= 0x2000000u;
          if ( (a5 & 0x1000000) != 0 )
          {
            *((_DWORD *)this + 92) &= ~0x10000000u;
            *((_DWORD *)this + 92) |= 0x1000000u;
          }
          else if ( (a5 & 0x10000000) != 0 )
          {
            *v82 |= 0x10000000u;
            COInetProt::InitAttachedBindToObject((LegacyTransaction *)((char *)this + 736));
          }
          *((_DWORD *)this + 177) = a5 & 0xFFFFFDCF;
          LegacyTransaction::SetClientSink(v5, a3, 0);
          Microsoft::WRL::ComPtr<IInternetBindInfo>::operator=((__int64 *)this + 188, (__int64)a4);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
          v14 = CTransaction::OnAttach(v5, v83, v84, a3);
          goto LABEL_75;
        }
        if ( (a5 & 0x8000) != 0 )
          *((_BYTE *)this + 393) &= ~0x20u;
        v12 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 576);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
        v13 = (struct IUri *)*((_QWORD *)this + 21);
        v14 = 0;
        if ( a2 != v13 )
        {
          if ( v13 )
            ((void (__fastcall *)(struct IUri *))v13->lpVtbl->Release)(v13);
          *((_QWORD *)this + 21) = a2;
          ((void (__fastcall *)(struct IUri *))a2->lpVtbl->AddRef)(a2);
          v15 = *((_QWORD *)this + 21);
          v16 = *((_QWORD *)this + 23);
          v17 = *((_DWORD *)this + 48);
          if ( v15 != v16 || v17 )
          {
            v18 = (OLECHAR *)*((_QWORD *)this + 25);
            if ( v18 )
            {
              SysFreeString(v18);
              *((_QWORD *)this + 25) = 0;
            }
            *((_QWORD *)this + 26) = 0;
            *((_DWORD *)this + 54) = 0;
            if ( v15 != v16 )
            {
              v19 = *((_QWORD *)this + 23);
              if ( v19 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                *((_QWORD *)this + 23) = 0;
              }
            }
          }
          *((_DWORD *)this + 48) = 0;
          if ( v15 && (v17 || v15 != v16) )
          {
            v96 = 0;
            v51 = (**(__int64 (__fastcall ***)(__int64, GUID *, COInetSession **))v15)(
                    v15,
                    &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
                    &v96);
            v52 = *((unsigned int *)this + 48);
            if ( v51 < 0 )
            {
              v14 = (*(__int64 (__fastcall **)(__int64, __int64, char *, _QWORD))(*(_QWORD *)v15 + 24LL))(
                      v15,
                      v52,
                      (char *)this + 200,
                      0);
              if ( v14 >= 0 )
              {
                v85 = (OLECHAR *)*((_QWORD *)this + 25);
                *((_QWORD *)this + 26) = v85;
                *((_DWORD *)this + 54) = SysStringLen(v85);
              }
            }
            else
            {
              v14 = (*(__int64 (__fastcall **)(COInetSession *, __int64, char *, char *))(*(_QWORD *)v96 + 224LL))(
                      v96,
                      v52,
                      (char *)this + 208,
                      (char *)this + 216);
              (*(void (__fastcall **)(COInetSession *))(*(_QWORD *)v96 + 16LL))(v96);
            }
            if ( v15 != v16 && v14 >= 0 )
            {
              *((_QWORD *)this + 23) = v15;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
            }
            if ( v14 == 1 )
              v14 = CUString::Set((LegacyTransaction *)((char *)this + 176), *((struct IUri **)this + 21), 0xBu);
          }
          v11 = a5;
          v12 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 576);
          v5 = (LegacyTransaction *)((char *)this - 48);
        }
        if ( *((_QWORD *)this + 26) )
        {
          if ( v14 >= 0 )
          {
            v96 = 0;
            v97 = 0;
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1512));
            v20 = (IUnknown **)((char *)this + 1496);
            if ( *((_QWORD *)this + 187) )
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)this + 187);
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1512));
            v21 = (char *)this + 736;
            lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 1032);
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1032));
            if ( *((struct IInternetProtocolSink **)this + 107) != v99 )
            {
              ((void (__fastcall *)(struct IInternetProtocolSink *))v99->lpVtbl->AddRef)(v99);
              v22 = *((_QWORD *)this + 107);
              *((_QWORD *)this + 107) = v99;
              if ( v22 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            }
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1032));
            if ( this != (LegacyTransaction *)-736LL )
            {
              v21 = (char *)this + 744;
              if ( this != (LegacyTransaction *)-744LL )
                (*(void (__fastcall **)(char *))(*(_QWORD *)v21 + 8LL))(v21);
            }
            v23 = *v20;
            *v20 = (IUnknown *)v21;
            if ( v23 )
              ((void (__fastcall *)(IUnknown *))v23->lpVtbl->Release)(v23);
            if ( *((struct IInternetBindInfo **)this + 188) != a4 )
            {
              ((void (__fastcall *)(struct IInternetBindInfo *))a4->lpVtbl->AddRef)(a4);
              v24 = *((_QWORD *)this + 188);
              *((_QWORD *)this + 188) = a4;
              if ( v24 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
            }
            if ( (v11 & 0x2000000) != 0 )
              *((_DWORD *)this + 92) |= 0x2000000u;
            *((_DWORD *)this + 177) = v11 & 0xFFFFFDCF;
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
            if ( *((_DWORD *)this + 54) > 6u )
            {
              v25 = (const WCHAR *)*((_QWORD *)this + 26);
              if ( v25 )
              {
                cchCount2 = 6;
                cchCount1[0] = 0;
                v27 = 6;
                LODWORD(v94) = 0;
                v28 = v25;
                do
                {
                  if ( !*v28 )
                    break;
                  ++v28;
                  --v27;
                }
                while ( v27 );
                if ( !v27 || (v29 = LongLongToULong(6 - v27, (unsigned int *)cchCount1), v30 = cchCount1[0], v29 < 0) )
                  v30 = 6;
                v31 = 6;
                v32 = L"mhtml:";
                do
                {
                  if ( !*v32 )
                    break;
                  ++v32;
                  --v31;
                }
                while ( v31 );
                if ( v31 && (int)LongLongToULong(6 - v31, (unsigned int *)&v94) >= 0 )
                  cchCount2 = (int)v94;
                if ( CompareStringW(0x7Fu, 0x1001u, v25, v30, L"mhtml:", cchCount2) == 2 )
                  *((_BYTE *)this + 394) |= 2u;
              }
            }
            v33 = memcmp_0(&IID_IInternetProtocol, &IID_IBindingExInternal, 0x10u);
            v34 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1512);
            if ( v33 )
            {
              EnterCriticalSection(v34);
              v35 = *v20;
              if ( !*v20 )
              {
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1512));
                goto LABEL_60;
              }
              ((void (__fastcall *)(IUnknown *))v35->lpVtbl->AddRef)(*v20);
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1512));
              Service = IUnknown_QueryService(v35, &IID_IInternetProtocol, &IID_IInternetProtocol, (void **)this + 33);
              ((void (__fastcall *)(IUnknown *))v35->lpVtbl->Release)(v35);
            }
            else
            {
              EnterCriticalSection(v34);
              v81 = *v20;
              if ( *v20 )
              {
                ((void (__fastcall *)(IUnknown *))v81->lpVtbl->AddRef)(*v20);
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1512));
                v86 = ((__int64 (__fastcall *)(IUnknown *, GUID *, char *))v81->lpVtbl->QueryInterface)(
                        v81,
                        &IID_IInternetProtocol,
                        (char *)this + 264);
                ((void (__fastcall *)(IUnknown *))v81->lpVtbl->Release)(v81);
                v37 = v86 == 0;
                if ( v86 >= 0 )
                  goto LABEL_59;
              }
              else
              {
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1512));
              }
              v87 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 33);
              if ( !v87 )
                goto LABEL_60;
              Service = (**v87)(v87, &IID_IInternetProtocol, (char *)this + 264);
            }
            v37 = Service == 0;
LABEL_59:
            if ( v37 && *((_QWORD *)this + 33) )
            {
              *((GUID *)this + 18) = CLSID_FtpProtocol;
LABEL_109:
              v56 = 0;
              v57 = 0;
              while ( 1 )
              {
                v58 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 33);
                v100 = 0;
                if ( (**v58)(v58, &IID_ICrossApartmentProtocolHandler, &v100) >= 0 && (v88 = v100) != 0 )
                {
                  *((_BYTE *)this + 395) |= 2u;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
                }
                else
                {
                  *((_BYTE *)this + 395) &= ~2u;
                }
                *(_QWORD *)cchCount1 = 0;
                if ( StringFromCLSID((const IID *const)this + 18, (LPOLESTR *)cchCount1) >= 0 )
                {
                  ((void (__fastcall *)(struct IInternetProtocolSink *, __int64, _QWORD))v99->lpVtbl->ReportProgress)(
                    v99,
                    20,
                    *(_QWORD *)cchCount1);
                  CoTaskMemFree(*(LPVOID *)cchCount1);
                }
                *((_DWORD *)this + 80) = 2;
                v59 = *((_QWORD *)this + 33);
                if ( v57 )
                {
                  if ( v59 )
                    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v59 + 8LL))(*((_QWORD *)this + 33));
                  v77 = *((_QWORD *)this + 106);
                  if ( v77 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
                  *((_QWORD *)this + 106) = v59;
                }
                else
                {
                  v60 = (struct IUri *)*((_QWORD *)this + 21);
                  *((_QWORD *)this + 105) = 0;
                  *((_QWORD *)this + 108) = 0;
                  v61 = lpCriticalSection;
                  *((_QWORD *)this + 109) = v5;
                  EnterCriticalSection(v61);
                  v62 = v99;
                  if ( *((struct IInternetProtocolSink **)this + 107) != v99 )
                  {
                    ((void (__fastcall *)(struct IInternetProtocolSink *))v99->lpVtbl->AddRef)(v99);
                    v63 = *((_QWORD *)this + 107);
                    *((_QWORD *)this + 107) = v62;
                    if ( v63 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
                  }
                  v64 = lpCriticalSection;
                  LeaveCriticalSection(lpCriticalSection);
                  if ( v59 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
                  v65 = *((_QWORD *)this + 106);
                  if ( v65 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                  *((_QWORD *)this + 106) = v59;
                  *((_DWORD *)this + 221) = a5;
                  if ( (a5 & 0x30) != 0 )
                  {
                    v66 = 4096;
                    if ( (a5 & 0x200) == 0 )
                      v66 = 2048;
                    if ( v66 != *((_DWORD *)this + 224) )
                    {
                      v67 = (void *)*((_QWORD *)this + 111);
                      *((_DWORD *)this + 224) = v66;
                      if ( v67 )
                        CoTaskMemFree(v67);
                      *((_QWORD *)this + 111) = operator new(*((unsigned int *)this + 224));
                    }
                    if ( *((_QWORD *)this + 111) )
                      *((_DWORD *)this + 227) = 256;
                    else
                      *((_DWORD *)this + 224) = 0;
                    if ( v60 )
                      COInetProt::SetUriAndAbsoluteUrl((LegacyTransaction *)((char *)this + 736), v60);
                    v68 = (void *)*((_QWORD *)this + 116);
                    if ( v68 )
                    {
                      CoTaskMemFree(v68);
                      *((_QWORD *)this + 116) = 0;
                    }
                  }
                  EnterCriticalSection(v64);
                  LeaveCriticalSection(v64);
                  if ( this == (LegacyTransaction *)-736LL )
                    v69 = 0;
                  else
                    v69 = (char *)this + 744;
                  if ( *((char **)this + 187) != v69 )
                  {
                    if ( v69 )
                      (*(void (__fastcall **)(char *))(*(_QWORD *)v69 + 8LL))(v69);
                    v70 = *((_QWORD *)this + 187);
                    *((_QWORD *)this + 187) = v69;
                    if ( v70 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
                  }
                  v57 = 1;
                }
                v71 = *((_QWORD *)this + 12);
                v72 = *((_QWORD *)this + 33);
                if ( v71 )
                {
                  v56 = *((_QWORD *)this + 12);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 8LL))(v71);
                }
                *((_BYTE *)this + 395) |= 0x20u;
                *((_QWORD *)this + 33) = (char *)this + 736;
                CTransaction::SetProtocolPriority(v5);
                EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
                *((_BYTE *)this + 394) |= 0x10u;
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
                v73 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IClassFactory **))*((_QWORD *)this + 33);
                v94 = 0;
                v74 = (**v73)(v73, &IID_IInternetProtocolEx, &v94);
                v75 = (char *)this - 32;
                if ( v74 < 0 )
                  v76 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LegacyTransaction *, char *, _DWORD, _QWORD))(**((_QWORD **)this + 33) + 24LL))(
                          *((_QWORD *)this + 33),
                          *((_QWORD *)this + 26),
                          v5,
                          v75,
                          0,
                          0);
                else
                  v76 = ((__int64 (__fastcall *)(struct IClassFactory *, _QWORD, LegacyTransaction *, char *, _DWORD, _QWORD))v94->lpVtbl[2].CreateInstance)(
                          v94,
                          *((_QWORD *)this + 21),
                          v5,
                          v75,
                          0,
                          0);
                v14 = v76;
                if ( v94 )
                {
                  ((void (__fastcall *)(struct IClassFactory *))v94->lpVtbl->Release)(v94);
                  v94 = 0;
                }
                EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
                *((_BYTE *)this + 394) &= ~0x10u;
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
                if ( (*((_BYTE *)this + 394) & 0x20) != 0 )
                  break;
                if ( v14 == -2147483638 )
                {
                  v14 = 0;
                  goto LABEL_153;
                }
                if ( v14 != -2146697199 )
                {
                  if ( v14 )
                  {
                    *((_BYTE *)this + 392) |= 4u;
                    if ( *((_QWORD *)this + 33) )
                    {
                      v80 = *((_BYTE *)this + 393);
                      if ( (v80 & 2) == 0 )
                      {
                        *((_BYTE *)this + 393) = v80 | 1;
                        CTransaction::SetResultOnSynchronousStartFailure((LegacyTransaction *)((char *)this - 48), v14);
                        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 187) + 48LL))(
                          *((_QWORD *)this + 187),
                          *((unsigned int *)this + 103),
                          *((unsigned int *)this + 104),
                          0);
                        LegacyTransaction::Terminate(this, 0);
                      }
                    }
                  }
                  goto LABEL_153;
                }
                COInetProt::SetProtocol((LegacyTransaction *)((char *)this + 736), 0);
                if ( v72 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
                  v72 = 0;
                }
                v89 = *((_QWORD *)this + 12);
                *((_QWORD *)this + 33) = 0;
                if ( v89 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
                  *((_QWORD *)this + 12) = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
                  v56 = 0;
                }
                v90 = (struct IUnknown *)((char *)this - 32);
                v91 = (unsigned __int16 *)*((_QWORD *)this + 26);
                v92 = (struct IUnknown **)((char *)this + 96);
                if ( v97 )
                {
                  v93 = COInetSession::CreateNextProtocol(
                          v96,
                          v91,
                          v90,
                          v92,
                          (struct IInternetProtocol **)this + 33,
                          (struct _GUID *)this + 18,
                          &v95);
                }
                else
                {
                  v93 = COInetSession::CreateFirstProtocol(
                          v96,
                          v91,
                          v90,
                          v92,
                          (struct IInternetProtocol **)this + 33,
                          (IID *)this + 18,
                          &v95,
                          (unsigned __int8)(*((_BYTE *)this + 394) & 4) << 20);
                  v97 = 1;
                }
                v14 = v93;
                if ( v93 )
                {
                  *((_QWORD *)this + 33) = 0;
                  v56 = 0;
                  *((_QWORD *)this + 12) = 0;
                  goto LABEL_153;
                }
              }
              if ( v14 || *((char *)this + 392) >= 0 )
                LegacyTransaction::Abort(this, *((_DWORD *)this + 100), *((_DWORD *)this + 101));
LABEL_153:
              if ( v72 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
              if ( v56 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
              if ( (a5 & 0x80u) != 0 && v14 >= 0 )
              {
                v78 = *((_BYTE *)this + 394);
                if ( (v78 & 1) == 0 )
                {
                  *((_BYTE *)this + 394) = v78 | 1;
                  v79 = LegacyTransaction::CompleteOperation(v5, a5 & 0x11000000);
                  *((_BYTE *)this + 394) &= ~1u;
                  v14 = v79;
                }
              }
              v39 = v96;
              goto LABEL_73;
            }
LABEL_60:
            EnterCriticalSection(&g_mxsOInet);
            v38 = g_pCOInetSession;
            if ( g_pCOInetSession )
            {
              v14 = 0;
            }
            else
            {
              v53 = (COInetSession *)operator new(0x180u);
              v14 = -2147024882;
              if ( v53 && (v38 = COInetSession::COInetSession(v53)) != 0 )
              {
                v54 = 0;
                g_pCOInetSession = v38;
              }
              else
              {
                v38 = g_pCOInetSession;
                v54 = -2147024882;
              }
              if ( !v38 )
              {
                LeaveCriticalSection(&g_mxsOInet);
                v39 = v96;
                goto LABEL_108;
              }
              v14 = v54;
            }
            _InterlockedIncrement((volatile signed __int32 *)v38 + 4);
            v39 = g_pCOInetSession;
            v96 = g_pCOInetSession;
            LeaveCriticalSection(&g_mxsOInet);
            if ( v14 )
            {
              v96 = v39;
              goto LABEL_108;
            }
            v40 = Str;
            v41 = (wchar_t *)*((_QWORD *)this + 26);
            v42 = *((_BYTE *)this + 394) & 4;
            v94 = 0;
            v43 = -2146697203;
            *((GUID *)this + 18) = GUID_NULL;
            v44 = 31;
            v45 = (_BYTE)v42 != 0 ? 0x400000 : 0;
            v46 = 32;
            do
            {
              if ( !v44 )
                break;
              if ( !*v41 )
                break;
              *v40++ = *v41++;
              --v44;
              --v46;
            }
            while ( v46 );
            v47 = v40 - 1;
            if ( v46 )
              v47 = v40;
            *v47 = 0;
            v48 = wcschr(Str, 0x3Au);
            if ( !v48 )
              goto LABEL_70;
            *v48 = 0;
            if ( (_BYTE)v42 )
            {
              v95 = 3;
              if ( !(unsigned int)COInetSession::FindInternalCF(v39, Str, &v94, (struct _GUID *)this + 18) )
                goto LABEL_100;
              v95 = 0;
              v45 = 0;
            }
            if ( (unsigned int)COInetSession::FindFirstCF(
                                 v39,
                                 Str,
                                 (LPVOID *)&v94,
                                 (struct _GUID *)this + 18,
                                 &v95,
                                 v45) )
            {
              v43 = -2147221020;
LABEL_70:
              v49 = (__int64)this + 264;
LABEL_71:
              v97 = 1;
              *(_QWORD *)v49 = 0;
              v14 = v43;
              goto LABEL_72;
            }
LABEL_100:
            if ( this == (LegacyTransaction *)32 )
            {
              v49 = 296;
            }
            else
            {
              v49 = (__int64)this + 264;
              v43 = ((__int64 (__fastcall *)(struct IClassFactory *, char *, GUID *, char *))v94->lpVtbl->CreateInstance)(
                      v94,
                      (char *)this - 32,
                      &IID_IUnknown,
                      (char *)this + 96);
              if ( !v43 )
                v43 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, char *))this + 12))(
                        *((_QWORD *)this + 12),
                        &IID_IInternetProtocol,
                        (char *)this + 264);
              if ( v43 != -2147221232 )
                goto LABEL_104;
            }
            v43 = ((__int64 (__fastcall *)(struct IClassFactory *, _QWORD, GUID *, __int64))v94->lpVtbl->CreateInstance)(
                    v94,
                    0,
                    &IID_IInternetProtocol,
                    v49);
LABEL_104:
            v14 = v43;
            ((void (__fastcall *)(struct IClassFactory *))v94->lpVtbl->Release)(v94);
            if ( v43 )
              goto LABEL_71;
            v97 = 1;
            v55 = (struct IUnknown *)*((_QWORD *)this + 12);
            if ( v55 && *((_DWORD *)this + 364) == 1 )
              IUnknown_EnablePreBinding(v55, 1u);
LABEL_108:
            if ( !v14 )
              goto LABEL_109;
LABEL_72:
            *((_QWORD *)this + 33) = 0;
            *((_QWORD *)this + 12) = 0;
LABEL_73:
            if ( v39 )
              _InterlockedDecrement((volatile signed __int32 *)v39 + 4);
            goto LABEL_75;
          }
        }
        else if ( v14 >= 0 )
        {
          v14 = -2147024809;
        }
        LeaveCriticalSection(v12);
      }
    }
    else
    {
      v14 = -2147024809;
    }
LABEL_75:
    CTransaction::Release(v5);
    return (unsigned int)v14;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180029e70  push    rbp
0x180029e72  push    rbx
0x180029e73  push    rsi
0x180029e74  push    rdi
0x180029e75  push    r12
0x180029e77  push    r13
0x180029e79  push    r15
0x180029e7b  lea     rbp, [rsp-17h]
0x180029e80  sub     rsp, 0E0h
0x180029e87  mov     rax, cs:__security_cookie
0x180029e8e  xor     rax, rsp
0x180029e91  mov     [rbp+47h+var_40], rax
0x180029e95  lea     r13, [rcx-30h]
0x180029e99  mov     [rbp+47h+var_A0], r8
0x180029e9d  mov     r15, r9
0x180029ea0  mov     r12, r8
0x180029ea3  mov     rsi, rdx
0x180029ea6  mov     rdi, rcx
0x180029ea9  test    r13, r13
0x180029eac  jz      loc_18002AB21
0x180029eb2  mov     [rsp+110h+arg_8], r14
0x180029eba  mov     [rsp+110h+var_C8], 0
0x180029ec2  lock inc dword ptr [rcx+68h]
0x180029ec6  test    rdx, rdx
0x180029ec9  jz      loc_18002A493
0x180029ecf  test    r9, r9
0x180029ed2  jz      loc_18002A493
0x180029ed8  test    r8, r8
0x180029edb  jz      loc_18002A493
0x180029ee1  mov     ecx, [r13+170h]
0x180029ee8  cmp     ecx, 4
0x180029eeb  jz      loc_18002AB2B
0x180029ef1  mov     r14d, [rbp+47h+arg_20]
0x180029ef5  mov     eax, r14d
0x180029ef8  and     byte ptr [rdi+18Ah], 0FBh
0x180029eff  shr     eax, 14h
0x180029f02  and     al, 4
0x180029f04  or      [rdi+18Ah], al
0x180029f0a  bt      r14d, 1Eh
0x180029f0f  jb      loc_18002AB35
0x180029f15  cmp     ecx, 2
0x180029f18  jz      loc_18002AB41
0x180029f1e  bt      r14d, 0Fh
0x180029f23  jb      loc_18002ABEE
0x180029f29  lea     r12, [rdi+240h]
0x180029f30  mov     rcx, r12; lpCriticalSection
0x180029f33  call    cs:__imp_EnterCriticalSection
0x180029f3a  nop     dword ptr [rax+rax+00h]
0x180029f3f  mov     rcx, [rdi+0A8h]
0x180029f46  xor     eax, eax
0x180029f48  mov     ebx, eax
0x180029f4a  cmp     rsi, rcx
0x180029f4d  jz      loc_180029FEA
0x180029f53  test    rcx, rcx
0x180029f56  jz      short loc_180029F64
0x180029f58  mov     rax, [rcx]
0x180029f5b  mov     rax, [rax+10h]
0x180029f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f64  mov     [rdi+0A8h], rsi
0x180029f6b  mov     rcx, rsi
0x180029f6e  mov     rax, [rsi]
0x180029f71  mov     rax, [rax+8]
0x180029f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f7a  mov     r14, [rdi+0A8h]
0x180029f81  lea     rsi, [rdi+0B0h]
0x180029f88  mov     r12, [rsi+8]
0x180029f8c  xor     eax, eax
0x180029f8e  mov     r13d, [rsi+10h]
0x180029f92  cmp     r14, r12
0x180029f95  jz      loc_18002A485
0x180029f9b  mov     rcx, [rsi+18h]; bstrString
0x180029f9f  test    rcx, rcx
0x180029fa2  jnz     loc_18002ABFA
0x180029fa8  mov     [rsi+20h], rax
0x180029fac  mov     [rsi+28h], eax
0x180029faf  cmp     r14, r12
0x180029fb2  jz      short loc_180029FCF
0x180029fb4  mov     rcx, [rsi+8]
0x180029fb8  test    rcx, rcx
0x180029fbb  jz      short loc_180029FCF
0x180029fbd  mov     rax, [rcx]
0x180029fc0  mov     rax, [rax+10h]
0x180029fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fc9  xor     eax, eax
0x180029fcb  mov     [rsi+8], rax
0x180029fcf  mov     [rsi+10h], eax
0x180029fd2  test    r14, r14
0x180029fd5  jnz     loc_18002A3FB
0x180029fdb  mov     r14d, [rbp+47h+arg_20]
0x180029fdf  lea     r12, [rdi+240h]
0x180029fe6  lea     r13, [rdi-30h]
0x180029fea  cmp     qword ptr [rdi+0D0h], 0
0x180029ff2  jz      loc_18002AC69
0x180029ff8  test    ebx, ebx
0x180029ffa  js      loc_18002AC72
0x18002a000  lea     r12, [rdi+5E8h]
0x18002a007  mov     [rbp+47h+var_C0], rax
0x18002a00b  mov     rcx, r12; lpCriticalSection
0x18002a00e  mov     [rbp+47h+var_B8], eax
0x18002a011  call    cs:__imp_EnterCriticalSection
0x18002a018  nop     dword ptr [rax+rax+00h]
0x18002a01d  lea     rsi, [rdi+5D8h]
0x18002a024  cmp     qword ptr [rsi], 0
0x18002a028  jnz     loc_18002A49D
0x18002a02e  mov     rcx, r12; lpCriticalSection
0x18002a031  call    cs:__imp_LeaveCriticalSection
0x18002a038  nop     dword ptr [rax+rax+00h]
0x18002a03d  lea     rbx, [rdi+2E0h]
0x18002a044  lea     rax, [rbx+128h]
0x18002a04b  mov     rcx, rax; lpCriticalSection
0x18002a04e  mov     [rbp+47h+lpCriticalSection], rax
0x18002a052  call    cs:__imp_EnterCriticalSection
0x18002a059  nop     dword ptr [rax+rax+00h]
0x18002a05e  mov     rcx, [rbp+47h+var_A0]
0x18002a062  cmp     [rbx+78h], rcx
0x18002a066  jz      short loc_18002A091
0x18002a068  mov     rax, [rcx]
0x18002a06b  mov     rax, [rax+8]
0x18002a06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a074  mov     rcx, [rbx+78h]
0x18002a078  mov     rax, [rbp+47h+var_A0]
0x18002a07c  mov     [rbx+78h], rax
0x18002a080  test    rcx, rcx
0x18002a083  jz      short loc_18002A091
0x18002a085  mov     rax, [rcx]
0x18002a088  mov     rax, [rax+10h]
0x18002a08c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a091  lea     rcx, [rbx+128h]; lpCriticalSection
0x18002a098  call    cs:__imp_LeaveCriticalSection
0x18002a09f  nop     dword ptr [rax+rax+00h]
0x18002a0a4  test    rbx, rbx
0x18002a0a7  jz      short loc_18002A0BE
0x18002a0a9  add     rbx, 8
0x18002a0ad  jz      short loc_18002A0BE
0x18002a0af  mov     rax, [rbx]
0x18002a0b2  mov     rcx, rbx
0x18002a0b5  mov     rax, [rax+8]
0x18002a0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0be  mov     rcx, [rsi]
0x18002a0c1  mov     [rsi], rbx
0x18002a0c4  test    rcx, rcx
0x18002a0c7  jz      short loc_18002A0D5
0x18002a0c9  mov     rax, [rcx]
0x18002a0cc  mov     rax, [rax+10h]
0x18002a0d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0d5  cmp     [rdi+5E0h], r15
0x18002a0dc  jz      short loc_18002A10C
0x18002a0de  mov     rax, [r15]
0x18002a0e1  mov     rcx, r15
0x18002a0e4  mov     rax, [rax+8]
0x18002a0e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0ed  mov     rcx, [rdi+5E0h]
0x18002a0f4  mov     [rdi+5E0h], r15
0x18002a0fb  test    rcx, rcx
0x18002a0fe  jz      short loc_18002A10C
0x18002a100  mov     rax, [rcx]
0x18002a103  mov     rax, [rax+10h]
0x18002a107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a10c  bt      r14d, 19h
0x18002a111  jb      loc_18002A4AA
0x18002a117  mov     eax, r14d
0x18002a11a  lea     rcx, [rdi+240h]; lpCriticalSection
0x18002a121  and     eax, 0FFFFFDCFh
0x18002a126  mov     [rdi+2C4h], eax
0x18002a12c  call    cs:__imp_LeaveCriticalSection
0x18002a133  nop     dword ptr [rax+rax+00h]
0x18002a138  cmp     dword ptr [rdi+0D8h], 6
0x18002a13f  jbe     loc_18002A216
0x18002a145  mov     r14, [rdi+0D0h]
0x18002a14c  test    r14, r14
0x18002a14f  jz      loc_18002A216
0x18002a155  xor     r8d, r8d
0x18002a158  mov     ebx, 6
0x18002a15d  mov     [rbp+47h+cchCount1], r8d
0x18002a161  mov     edx, ebx
0x18002a163  mov     dword ptr [rsp+110h+var_D0], r8d
0x18002a168  mov     rax, r14
0x18002a16b  nop     dword ptr [rax+rax+00h]
0x18002a170  cmp     [rax], r8w
0x18002a174  jz      short loc_18002A180
0x18002a176  add     rax, 2
0x18002a17a  sub     rdx, 1
0x18002a17e  jnz     short loc_18002A170
0x18002a180  mov     rcx, rbx
0x18002a183  sub     rcx, rdx
0x18002a186  test    rdx, rdx
0x18002a189  cmovz   rcx, r8; __int64
0x18002a18d  jz      short loc_18002A1A3
0x18002a18f  lea     rdx, [rbp+47h+cchCount1]; unsigned int *
0x18002a193  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x18002a198  mov     r15d, [rbp+47h+cchCount1]
0x18002a19c  xor     r8d, r8d
0x18002a19f  test    eax, eax
0x18002a1a1  jns     short loc_18002A1A6
0x18002a1a3  mov     r15d, ebx
0x18002a1a6  mov     rdx, rbx
0x18002a1a9  lea     rax, aMhtml_1; "mhtml:"
0x18002a1b0  cmp     word ptr [rax], 0
0x18002a1b4  jz      short loc_18002A1C0
0x18002a1b6  add     rax, 2
0x18002a1ba  sub     rdx, 1
0x18002a1be  jnz     short loc_18002A1B0
0x18002a1c0  mov     rcx, rbx
0x18002a1c3  sub     rcx, rdx
0x18002a1c6  test    rdx, rdx
0x18002a1c9  cmovz   rcx, r8; __int64
0x18002a1cd  jz      short loc_18002A1E1
0x18002a1cf  lea     rdx, [rsp+110h+var_D0]; unsigned int *
0x18002a1d4  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x18002a1d9  test    eax, eax
0x18002a1db  js      short loc_18002A1E1
0x18002a1dd  mov     ebx, dword ptr [rsp+110h+var_D0]
0x18002a1e1  lea     rax, aMhtml_1; "mhtml:"
0x18002a1e8  mov     [rsp+110h+cchCount2], ebx; cchCount2
0x18002a1ec  mov     r9d, r15d; cchCount1
0x18002a1ef  mov     [rsp+110h+lpString2], rax; unsigned int *
0x18002a1f4  mov     r8, r14; lpString1
0x18002a1f7  mov     edx, 1001h; dwCmpFlags
0x18002a1fc  mov     ecx, 7Fh; Locale
0x18002a201  call    cs:__imp_CompareStringW
0x18002a208  nop     dword ptr [rax+rax+00h]
0x18002a20d  add     eax, 0FFFFFFFEh
0x18002a210  jz      loc_18002AC86
0x18002a216  mov     r8d, 10h; Size
0x18002a21c  lea     rdx, IID_IBindingExInternal; Buf2
0x18002a223  lea     rcx, IID_IInternetProtocol; Buf1
0x18002a22a  call    memcmp_0
0x18002a22f  mov     rcx, r12; lpCriticalSection
0x18002a232  test    eax, eax
0x18002a234  jz      loc_18002AAF5
0x18002a23a  call    cs:__imp_EnterCriticalSection
0x18002a241  nop     dword ptr [rax+rax+00h]
0x18002a246  mov     rbx, [rsi]
0x18002a249  test    rbx, rbx
0x18002a24c  jz      loc_18002A4C7
0x18002a252  mov     rax, [rbx]
0x18002a255  mov     rcx, rbx
0x18002a258  mov     rax, [rax+8]
0x18002a25c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a261  mov     rcx, r12; lpCriticalSection
0x18002a264  call    cs:__imp_LeaveCriticalSection
0x18002a26b  nop     dword ptr [rax+rax+00h]
0x18002a270  lea     r9, [rdi+108h]; ppvOut
0x18002a277  mov     rcx, rbx; punk
0x18002a27a  lea     r8, IID_IInternetProtocol; riid
0x18002a281  lea     rdx, IID_IInternetProtocol; guidService
0x18002a288  call    cs:__imp_IUnknown_QueryService
0x18002a28f  nop     dword ptr [rax+rax+00h]
0x18002a294  mov     esi, eax
0x18002a296  mov     rcx, rbx
0x18002a299  mov     rax, [rbx]
0x18002a29c  mov     rax, [rax+10h]
0x18002a2a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2a5  test    esi, esi
0x18002a2a7  jz      loc_18002AD15
0x18002a2ad  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x18002a2b4  call    cs:__imp_EnterCriticalSection
0x18002a2bb  nop     dword ptr [rax+rax+00h]
0x18002a2c0  mov     rax, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x18002a2c7  test    rax, rax
0x18002a2ca  jz      loc_18002A4DB
0x18002a2d0  xor     ebx, ebx
0x18002a2d2  lock inc dword ptr [rax+10h]
0x18002a2d6  mov     r12, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x18002a2dd  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x18002a2e4  mov     [rbp+47h+var_C0], r12
0x18002a2e8  call    cs:__imp_LeaveCriticalSection
0x18002a2ef  nop     dword ptr [rax+rax+00h]
0x18002a2f4  test    ebx, ebx
0x18002a2f6  jnz     loc_18002A520
0x18002a2fc  movzx   ebx, byte ptr [rdi+18Ah]
0x18002a303  lea     r8, [rbp+47h+Str]
0x18002a307  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002a30e  mov     rdx, [rdi+0D0h]
0x18002a315  and     bl, 4
0x18002a318  movzx   eax, bl
0x18002a31b  mov     [rsp+110h+var_D0], 0
0x18002a324  neg     al
0x18002a326  mov     esi, 800C000Dh
0x18002a32b  movups  xmmword ptr [rdi+120h], xmm0
0x18002a332  sbb     r14d, r14d
0x18002a335  mov     ecx, 1Fh
0x18002a33a  and     r14d, 400000h
0x18002a341  mov     r9d, 20h ; ' '
0x18002a347  test    rcx, rcx
0x18002a34a  jz      short loc_18002A369
0x18002a34c  movzx   eax, word ptr [rdx]
0x18002a34f  test    ax, ax
0x18002a352  jz      short loc_18002A369
0x18002a354  mov     [r8], ax
0x18002a358  add     rdx, 2
0x18002a35c  add     r8, 2
0x18002a360  dec     rcx
0x18002a363  sub     r9, 1
0x18002a367  jnz     short loc_18002A347
0x18002a369  test    r9, r9
0x18002a36c  lea     rcx, [r8-2]
0x18002a370  mov     edx, 3Ah ; ':'; Ch
0x18002a375  cmovnz  rcx, r8
0x18002a379  xor     eax, eax
  ... truncated ...
```
