# LegacyTransaction::StartEx(IUri *,IInternetProtocolSink *,IInternetBindInfo *,ulong,unsigned __int64)

- ea: `0x180022f50`
- end: `0x180023f20`
- name: `?StartEx@LegacyTransaction@@UEAAJPEAUIUri@@PEAUIInternetProtocolSink@@PEAUIInternetBindInfo@@K_K@Z`
- size: `4048`
- prototype: `__int64 __fastcall(LegacyTransaction *this, struct IUri *, struct IInternetProtocolSink *, struct IInternetBindInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ef390`

## callees

- `0x180008300`
- `0x1800150e0`
- `0x18001511c`
- `0x1800151d0`
- `0x18001a4d0`
- `0x18001e160`
- `0x180022f50`
- `0x180024260`
- `0x180024ac8`
- `0x1800478b0`
- `0x180047ac8`
- `0x180054ad8`
- `0x1800683d0`
- `0x18006a578`
- `0x18006f0b0`
- `0x180070de0`
- `0x18007a5b4`
- `0x18007f820`
- `0x18008e680`
- `0x18009085c`
- `0x1800e826c`
- `0x1800ebb44`
- `0x1800ee71c`
- `0x18011ba26`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `msvcrt!wcschr` at `0x18002341b`
- `msvcrt!wcschr` at `0x18002341b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023105`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023160`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800231ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002330f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023381`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002355c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023794`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023860`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023908`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800239a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023ab3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023b4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023bfe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023c91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023cba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023105`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023160`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800231ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002330f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023381`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002355c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023794`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023860`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023908`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800239a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023ab3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023b4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023bfe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023c91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023cba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023013`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800230eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023120`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800232eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023353`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002374b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023857`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800238f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002398f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023b35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023b7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023013`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800230eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023120`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800232eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023353`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002374b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023857`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800238f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002398f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023b35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023b7c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800232b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800232b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002370c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023802`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023de4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002370c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023802`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023de4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800236e5`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800236e5`
- `OLEAUT32!__imp_SysFreeString` at `0x180023c22`
- `OLEAUT32!__imp_SysFreeString` at `0x180023c22`
- `OLEAUT32!__imp_SysStringLen` at `0x180023c5b`
- `OLEAUT32!__imp_SysStringLen` at `0x180023c5b`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18002332d`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18002332d`

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
  int v26; // ebx
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
  struct IInternetBindInfo *v84; // r8
  OLECHAR *v85; // rcx
  int v86; // esi
  __int64 (__fastcall ***v87)(_QWORD, GUID *, char *); // rcx
  __int64 v88; // rcx
  __int64 v89; // rcx
  struct IUnknown *v90; // r8
  const unsigned __int16 *v91; // rdx
  struct IUnknown **v92; // r9
  int v93; // eax
  unsigned int *lpString2; // [rsp+20h] [rbp-A9h]
  unsigned __int64 cchCount2; // [rsp+28h] [rbp-A1h]
  struct IClassFactory *v96; // [rsp+40h] [rbp-89h] BYREF
  unsigned int v97; // [rsp+48h] [rbp-81h] BYREF
  COInetSession *v98; // [rsp+50h] [rbp-79h] BYREF
  int v99; // [rsp+58h] [rbp-71h]
  int cchCount1[2]; // [rsp+68h] [rbp-61h] BYREF
  struct IInternetProtocolSink *v101; // [rsp+70h] [rbp-59h]
  __int64 v102; // [rsp+78h] [rbp-51h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+80h] [rbp-49h]
  wchar_t Str[32]; // [rsp+90h] [rbp-39h] BYREF

  v5 = (LegacyTransaction *)((char *)this - 48);
  v101 = a3;
  if ( this != (LegacyTransaction *)48 )
  {
    v97 = 0;
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
          Microsoft::WRL::ComPtr<IInternetBindInfo>::operator=((char *)this + 1504, a4);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
          v14 = CTransaction::OnAttach(v5, v83, v84, a3, (unsigned int)lpString2, cchCount2);
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
            v98 = 0;
            v51 = (**(__int64 (__fastcall ***)(__int64, GUID *, COInetSession **))v15)(
                    v15,
                    &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60,
                    &v98);
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
              v14 = (*(__int64 (__fastcall **)(COInetSession *, __int64, char *, char *))(*(_QWORD *)v98 + 224LL))(
                      v98,
                      v52,
                      (char *)this + 208,
                      (char *)this + 216);
              (*(void (__fastcall **)(COInetSession *))(*(_QWORD *)v98 + 16LL))(v98);
            }
            if ( v15 != v16 && v14 >= 0 )
            {
              *((_QWORD *)this + 23) = v15;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
            }
            if ( v14 == 1 )
              v14 = CUString::Set(
                      (LegacyTransaction *)((char *)this + 176),
                      *((struct IUri **)this + 21),
                      Uri_PROPERTY_RAW_URI);
          }
          v11 = a5;
          v12 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 576);
          v5 = (LegacyTransaction *)((char *)this - 48);
        }
        if ( *((_QWORD *)this + 26) )
        {
          if ( v14 >= 0 )
          {
            v98 = 0;
            v99 = 0;
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1512));
            v20 = (IUnknown **)((char *)this + 1496);
            if ( *((_QWORD *)this + 187) )
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 1496);
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1512));
            v21 = (char *)this + 736;
            lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 1032);
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1032));
            if ( *((struct IInternetProtocolSink **)this + 107) != v101 )
            {
              ((void (__fastcall *)(struct IInternetProtocolSink *))v101->lpVtbl->AddRef)(v101);
              v22 = *((_QWORD *)this + 107);
              *((_QWORD *)this + 107) = v101;
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
                v26 = 6;
                cchCount1[0] = 0;
                v27 = 6;
                LODWORD(v96) = 0;
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
                if ( v31 && (int)LongLongToULong(6 - v31, (unsigned int *)&v96) >= 0 )
                  v26 = (int)v96;
                if ( CompareStringW(0x7Fu, 0x1001u, v25, v30, L"mhtml:", v26) == 2 )
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
                v102 = 0;
                if ( (**v58)(v58, &IID_ICrossApartmentProtocolHandler, &v102) >= 0 && (v88 = v102) != 0 )
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
                  ((void (__fastcall *)(struct IInternetProtocolSink *, __int64, _QWORD))v101->lpVtbl->ReportProgress)(
                    v101,
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
                  v62 = v101;
                  if ( *((struct IInternetProtocolSink **)this + 107) != v101 )
                  {
                    ((void (__fastcall *)(struct IInternetProtocolSink *))v101->lpVtbl->AddRef)(v101);
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
                v96 = 0;
                v74 = (**v73)(v73, &IID_IInternetProtocolEx, &v96);
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
                  v76 = ((__int64 (__fastcall *)(struct IClassFactory *, _QWORD, LegacyTransaction *, char *, _DWORD, _QWORD))v96->lpVtbl[2].CreateInstance)(
                          v96,
                          *((_QWORD *)this + 21),
                          v5,
                          v75,
                          0,
                          0);
                v14 = v76;
                if ( v96 )
                {
                  ((void (__fastcall *)(struct IClassFactory *))v96->lpVtbl->Release)(v96);
                  v96 = 0;
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
                v91 = (const unsigned __int16 *)*((_QWORD *)this + 26);
                v92 = (struct IUnknown **)((char *)this + 96);
                if ( v99 )
                {
                  v93 = COInetSession::CreateNextProtocol(
                          v98,
                          v91,
                          v90,
                          v92,
                          (struct IInternetProtocol **)this + 33,
                          (struct _GUID *)this + 18,
                          &v97);
                }
                else
                {
                  v93 = COInetSession::CreateFirstProtocol(
                          v98,
                          v91,
                          v90,
                          v92,
                          (struct IInternetProtocol **)this + 33,
                          (IID *)this + 18,
                          &v97,
                          (unsigned __int8)(*((_BYTE *)this + 394) & 4) << 20);
                  v99 = 1;
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
              v39 = v98;
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
                v39 = v98;
                goto LABEL_108;
              }
              v14 = v54;
            }
            _InterlockedIncrement((volatile signed __int32 *)v38 + 4);
            v39 = g_pCOInetSession;
            v98 = g_pCOInetSession;
            LeaveCriticalSection(&g_mxsOInet);
            if ( v14 )
            {
              v98 = v39;
              goto LABEL_108;
            }
            v40 = Str;
            v41 = (wchar_t *)*((_QWORD *)this + 26);
            v42 = *((_BYTE *)this + 394) & 4;
            v96 = 0;
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
              v97 = 3;
              if ( !COInetSession::FindInternalCF(v39, Str, &v96, (struct _GUID *)this + 18, lpString2) )
                goto LABEL_100;
              v97 = 0;
              v45 = 0;
            }
            if ( COInetSession::FindFirstCF(v39, Str, &v96, (struct _GUID *)this + 18, &v97, v45) )
            {
              v43 = -2147221020;
LABEL_70:
              v49 = (__int64)this + 264;
LABEL_71:
              v99 = 1;
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
              v43 = ((__int64 (__fastcall *)(struct IClassFactory *, char *, GUID *, char *))v96->lpVtbl->CreateInstance)(
                      v96,
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
            v43 = ((__int64 (__fastcall *)(struct IClassFactory *, _QWORD, GUID *, __int64))v96->lpVtbl->CreateInstance)(
                    v96,
                    0,
                    &IID_IInternetProtocol,
                    v49);
LABEL_104:
            v14 = v43;
            ((void (__fastcall *)(struct IClassFactory *))v96->lpVtbl->Release)(v96);
            if ( v43 )
              goto LABEL_71;
            v99 = 1;
            v55 = (struct IUnknown *)*((_QWORD *)this + 12);
            if ( v55 && *((_DWORD *)this + 364) == 1 )
              IUnknown_EnablePreBinding(v55, 1);
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
0x180022f50  push    rbp
0x180022f52  push    rbx
0x180022f53  push    rsi
0x180022f54  push    rdi
0x180022f55  push    r12
0x180022f57  push    r13
0x180022f59  push    r15
0x180022f5b  lea     rbp, [rsp-17h]
0x180022f60  sub     rsp, 0E0h
0x180022f67  mov     rax, cs:__security_cookie
0x180022f6e  xor     rax, rsp
0x180022f71  mov     [rbp+47h+var_40], rax
0x180022f75  lea     r13, [rcx-30h]
0x180022f79  mov     [rbp+47h+var_A0], r8
0x180022f7d  mov     r15, r9
0x180022f80  mov     r12, r8
0x180022f83  mov     rsi, rdx
0x180022f86  mov     rdi, rcx
0x180022f89  test    r13, r13
0x180022f8c  jz      loc_180023B55
0x180022f92  mov     [rsp+110h+arg_8], r14
0x180022f9a  mov     [rsp+110h+var_C8], 0
0x180022fa2  lock inc dword ptr [rcx+68h]
0x180022fa6  test    rdx, rdx
0x180022fa9  jz      loc_180023525
0x180022faf  test    r9, r9
0x180022fb2  jz      loc_180023525
0x180022fb8  test    r8, r8
0x180022fbb  jz      loc_180023525
0x180022fc1  mov     ecx, [r13+170h]
0x180022fc8  cmp     ecx, 4
0x180022fcb  jz      loc_180023B5F
0x180022fd1  mov     r14d, [rbp+47h+arg_20]
0x180022fd5  mov     eax, r14d
0x180022fd8  and     byte ptr [rdi+18Ah], 0FBh
0x180022fdf  shr     eax, 14h
0x180022fe2  and     al, 4
0x180022fe4  or      [rdi+18Ah], al
0x180022fea  bt      r14d, 1Eh
0x180022fef  jb      loc_180023B69
0x180022ff5  cmp     ecx, 2
0x180022ff8  jz      loc_180023B75
0x180022ffe  bt      r14d, 0Fh
0x180023003  jb      loc_180023C16
0x180023009  lea     r12, [rdi+240h]
0x180023010  mov     rcx, r12; lpCriticalSection
0x180023013  call    cs:__imp_EnterCriticalSection
0x180023019  mov     rcx, [rdi+0A8h]
0x180023020  xor     eax, eax
0x180023022  mov     ebx, eax
0x180023024  cmp     rsi, rcx
0x180023027  jz      loc_1800230C4
0x18002302d  test    rcx, rcx
0x180023030  jz      short loc_18002303E
0x180023032  mov     rax, [rcx]
0x180023035  mov     rax, [rax+10h]
0x180023039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002303e  mov     [rdi+0A8h], rsi
0x180023045  mov     rcx, rsi
0x180023048  mov     rax, [rsi]
0x18002304b  mov     rax, [rax+8]
0x18002304f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023054  mov     r14, [rdi+0A8h]
0x18002305b  lea     rsi, [rdi+0B0h]
0x180023062  mov     r12, [rsi+8]
0x180023066  xor     eax, eax
0x180023068  mov     r13d, [rsi+10h]
0x18002306c  cmp     r14, r12
0x18002306f  jz      loc_180023517
0x180023075  mov     rcx, [rsi+18h]; bstrString
0x180023079  test    rcx, rcx
0x18002307c  jnz     loc_180023C22
0x180023082  mov     [rsi+20h], rax
0x180023086  mov     [rsi+28h], eax
0x180023089  cmp     r14, r12
0x18002308c  jz      short loc_1800230A9
0x18002308e  mov     rcx, [rsi+8]
0x180023092  test    rcx, rcx
0x180023095  jz      short loc_1800230A9
0x180023097  mov     rax, [rcx]
0x18002309a  mov     rax, [rax+10h]
0x18002309e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230a3  xor     eax, eax
0x1800230a5  mov     [rsi+8], rax
0x1800230a9  mov     [rsi+10h], eax
0x1800230ac  test    r14, r14
0x1800230af  jnz     loc_18002348D
0x1800230b5  mov     r14d, [rbp+47h+arg_20]
0x1800230b9  lea     r12, [rdi+240h]
0x1800230c0  lea     r13, [rdi-30h]
0x1800230c4  cmp     qword ptr [rdi+0D0h], 0
0x1800230cc  jz      loc_180023C85
0x1800230d2  test    ebx, ebx
0x1800230d4  js      loc_180023C8E
0x1800230da  lea     r12, [rdi+5E8h]
0x1800230e1  mov     [rbp+47h+var_C0], rax
0x1800230e5  mov     rcx, r12; lpCriticalSection
0x1800230e8  mov     [rbp+47h+var_B8], eax
0x1800230eb  call    cs:__imp_EnterCriticalSection
0x1800230f1  lea     rsi, [rdi+5D8h]
0x1800230f8  cmp     qword ptr [rsi], 0
0x1800230fc  jnz     loc_18002352F
0x180023102  mov     rcx, r12; lpCriticalSection
0x180023105  call    cs:__imp_LeaveCriticalSection
0x18002310b  lea     rbx, [rdi+2E0h]
0x180023112  lea     rax, [rbx+128h]
0x180023119  mov     rcx, rax; lpCriticalSection
0x18002311c  mov     [rbp+47h+lpCriticalSection], rax
0x180023120  call    cs:__imp_EnterCriticalSection
0x180023126  mov     rcx, [rbp+47h+var_A0]
0x18002312a  cmp     [rbx+78h], rcx
0x18002312e  jz      short loc_180023159
0x180023130  mov     rax, [rcx]
0x180023133  mov     rax, [rax+8]
0x180023137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002313c  mov     rcx, [rbx+78h]
0x180023140  mov     rax, [rbp+47h+var_A0]
0x180023144  mov     [rbx+78h], rax
0x180023148  test    rcx, rcx
0x18002314b  jz      short loc_180023159
0x18002314d  mov     rax, [rcx]
0x180023150  mov     rax, [rax+10h]
0x180023154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023159  lea     rcx, [rbx+128h]; lpCriticalSection
0x180023160  call    cs:__imp_LeaveCriticalSection
0x180023166  test    rbx, rbx
0x180023169  jz      short loc_180023180
0x18002316b  add     rbx, 8
0x18002316f  jz      short loc_180023180
0x180023171  mov     rax, [rbx]
0x180023174  mov     rcx, rbx
0x180023177  mov     rax, [rax+8]
0x18002317b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023180  mov     rcx, [rsi]
0x180023183  mov     [rsi], rbx
0x180023186  test    rcx, rcx
0x180023189  jz      short loc_180023197
0x18002318b  mov     rax, [rcx]
0x18002318e  mov     rax, [rax+10h]
0x180023192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023197  cmp     [rdi+5E0h], r15
0x18002319e  jz      short loc_1800231CE
0x1800231a0  mov     rax, [r15]
0x1800231a3  mov     rcx, r15
0x1800231a6  mov     rax, [rax+8]
0x1800231aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231af  mov     rcx, [rdi+5E0h]
0x1800231b6  mov     [rdi+5E0h], r15
0x1800231bd  test    rcx, rcx
0x1800231c0  jz      short loc_1800231CE
0x1800231c2  mov     rax, [rcx]
0x1800231c5  mov     rax, [rax+10h]
0x1800231c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231ce  bt      r14d, 19h
0x1800231d3  jb      loc_18002353C
0x1800231d9  mov     eax, r14d
0x1800231dc  lea     rcx, [rdi+240h]; lpCriticalSection
0x1800231e3  and     eax, 0FFFFFDCFh
0x1800231e8  mov     [rdi+2C4h], eax
0x1800231ee  call    cs:__imp_LeaveCriticalSection
0x1800231f4  cmp     dword ptr [rdi+0D8h], 6
0x1800231fb  jbe     loc_1800232C7
0x180023201  mov     r14, [rdi+0D0h]
0x180023208  test    r14, r14
0x18002320b  jz      loc_1800232C7
0x180023211  xor     r8d, r8d
0x180023214  mov     ebx, 6
0x180023219  mov     [rbp+47h+cchCount1], r8d
0x18002321d  mov     edx, ebx
0x18002321f  mov     dword ptr [rsp+110h+var_D0], r8d
0x180023224  mov     rax, r14
0x180023227  cmp     [rax], r8w
0x18002322b  jz      short loc_180023237
0x18002322d  add     rax, 2
0x180023231  sub     rdx, 1
0x180023235  jnz     short loc_180023227
0x180023237  mov     rcx, rbx
0x18002323a  sub     rcx, rdx
0x18002323d  test    rdx, rdx
0x180023240  cmovz   rcx, r8; __int64
0x180023244  jz      short loc_18002325A
0x180023246  lea     rdx, [rbp+47h+cchCount1]; unsigned int *
0x18002324a  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x18002324f  mov     r15d, [rbp+47h+cchCount1]
0x180023253  xor     r8d, r8d
0x180023256  test    eax, eax
0x180023258  jns     short loc_18002325D
0x18002325a  mov     r15d, ebx
0x18002325d  mov     rdx, rbx
0x180023260  lea     rax, aMhtml_1; "mhtml:"
0x180023267  cmp     word ptr [rax], 0
0x18002326b  jz      short loc_180023277
0x18002326d  add     rax, 2
0x180023271  sub     rdx, 1
0x180023275  jnz     short loc_180023267
0x180023277  mov     rcx, rbx
0x18002327a  sub     rcx, rdx
0x18002327d  test    rdx, rdx
0x180023280  cmovz   rcx, r8; __int64
0x180023284  jz      short loc_180023298
0x180023286  lea     rdx, [rsp+110h+var_D0]; unsigned int *
0x18002328b  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x180023290  test    eax, eax
0x180023292  js      short loc_180023298
0x180023294  mov     ebx, dword ptr [rsp+110h+var_D0]
0x180023298  lea     rax, aMhtml_1; "mhtml:"
0x18002329f  mov     [rsp+110h+cchCount2], ebx; cchCount2
0x1800232a3  mov     r9d, r15d; cchCount1
0x1800232a6  mov     [rsp+110h+lpString2], rax; unsigned int *
0x1800232ab  mov     r8, r14; lpString1
0x1800232ae  mov     edx, 1001h; dwCmpFlags
0x1800232b3  mov     ecx, 7Fh; Locale
0x1800232b8  call    cs:__imp_CompareStringW
0x1800232be  add     eax, 0FFFFFFFEh
0x1800232c1  jz      loc_180023C9C
0x1800232c7  mov     r8d, 10h; Size
0x1800232cd  lea     rdx, IID_IBindingExInternal; Buf2
0x1800232d4  lea     rcx, IID_IInternetProtocol; Buf1
0x1800232db  call    memcmp_0
0x1800232e0  mov     rcx, r12; lpCriticalSection
0x1800232e3  test    eax, eax
0x1800232e5  jz      loc_180023B35
0x1800232eb  call    cs:__imp_EnterCriticalSection
0x1800232f1  mov     rbx, [rsi]
0x1800232f4  test    rbx, rbx
0x1800232f7  jz      loc_180023559
0x1800232fd  mov     rax, [rbx]
0x180023300  mov     rcx, rbx
0x180023303  mov     rax, [rax+8]
0x180023307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002330c  mov     rcx, r12; lpCriticalSection
0x18002330f  call    cs:__imp_LeaveCriticalSection
0x180023315  lea     r9, [rdi+108h]; ppvOut
0x18002331c  mov     rcx, rbx; punk
0x18002331f  lea     r8, IID_IInternetProtocol; riid
0x180023326  lea     rdx, IID_IInternetProtocol; guidService
0x18002332d  call    cs:__imp_IUnknown_QueryService
0x180023333  mov     esi, eax
0x180023335  mov     rcx, rbx
0x180023338  mov     rax, [rbx]
0x18002333b  mov     rax, [rax+10h]
0x18002333f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023344  test    esi, esi
0x180023346  jz      loc_180023D25
0x18002334c  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x180023353  call    cs:__imp_EnterCriticalSection
0x180023359  mov     rax, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x180023360  test    rax, rax
0x180023363  jz      loc_180023567
0x180023369  xor     ebx, ebx
0x18002336b  lock inc dword ptr [rax+10h]
0x18002336f  mov     r12, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x180023376  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x18002337d  mov     [rbp+47h+var_C0], r12
0x180023381  call    cs:__imp_LeaveCriticalSection
0x180023387  test    ebx, ebx
0x180023389  jnz     loc_1800235AC
0x18002338f  movzx   ebx, byte ptr [rdi+18Ah]
0x180023396  lea     r8, [rbp+47h+Str]
0x18002339a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800233a1  mov     rdx, [rdi+0D0h]
0x1800233a8  and     bl, 4
0x1800233ab  movzx   eax, bl
0x1800233ae  mov     [rsp+110h+var_D0], 0
0x1800233b7  neg     al
0x1800233b9  mov     esi, 800C000Dh
0x1800233be  movups  xmmword ptr [rdi+120h], xmm0
0x1800233c5  sbb     r14d, r14d
0x1800233c8  mov     ecx, 1Fh
0x1800233cd  and     r14d, 400000h
0x1800233d4  mov     r9d, 20h ; ' '
0x1800233da  nop     word ptr [rax+rax+00h]
0x1800233e0  test    rcx, rcx
0x1800233e3  jz      short loc_180023402
0x1800233e5  movzx   eax, word ptr [rdx]
0x1800233e8  test    ax, ax
0x1800233eb  jz      short loc_180023402
0x1800233ed  mov     [r8], ax
0x1800233f1  add     rdx, 2
0x1800233f5  add     r8, 2
0x1800233f9  dec     rcx
0x1800233fc  sub     r9, 1
0x180023400  jnz     short loc_1800233E0
0x180023402  test    r9, r9
0x180023405  lea     rcx, [r8-2]
0x180023409  mov     edx, 3Ah ; ':'; Ch
0x18002340e  cmovnz  rcx, r8
0x180023412  xor     eax, eax
0x180023414  mov     [rcx], ax
0x180023417  lea     rcx, [rbp+47h+Str]; Str
0x18002341b  call    cs:__imp_wcschr
0x180023421  test    rax, rax
0x180023424  jnz     loc_1800235B5
0x18002342a  lea     r14, [rdi+108h]
0x180023431  xor     eax, eax
0x180023433  mov     [rbp+47h+var_B8], 1
0x18002343a  mov     [r14], rax
0x18002343d  mov     ebx, esi
0x18002343f  test    esi, esi
0x180023441  jz      loc_180023670
  ... truncated ...
```
