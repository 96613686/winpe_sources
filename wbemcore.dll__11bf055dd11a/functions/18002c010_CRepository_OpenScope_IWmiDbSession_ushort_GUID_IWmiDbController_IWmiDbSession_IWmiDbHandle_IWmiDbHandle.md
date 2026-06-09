# CRepository::OpenScope(IWmiDbSession *,ushort *,_GUID *,IWmiDbController * *,IWmiDbSession * *,IWmiDbHandle * *,IWmiDbHandle * *)

- ea: `0x18002c010`
- end: `0x18002c9df`
- name: `?OpenScope@CRepository@@SAJPEAUIWmiDbSession@@PEAGPEAU_GUID@@PEAPEAUIWmiDbController@@PEAPEAU2@PEAPEAUIWmiDbHandle@@5@Z`
- size: `2511`
- prototype: `__int64 __usercall@<rax>(struct IWmiDbSession *@<rcx>, unsigned __int16 *@<rdx>, struct _GUID *@<r8>, struct IWmiDbController **@<r9>, struct IWmiDbSession **, struct IWmiDbHandle **, struct IWmiDbHandle **)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010e80`
- `0x18002ab80`

## callees

- `0x18000a86c`
- `0x18000b140`
- `0x18002c010`
- `0x18002c9f0`
- `0x18002ca8c`
- `0x18002cc48`
- `0x18002cca4`
- `0x18003cfe0`
- `0x18005f0a0`
- `0x180060ab0`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18002c5c5`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18002c60d`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18002c5c5`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18002c60d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002c1ea`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002c1ea`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002c41e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002c659`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002c41e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002c659`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x18002c312`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x18002c312`
- `wbemcomn!??0WString2@@QEAA@PEBG@Z` at `0x18002c186`
- `wbemcomn!??0WString2@@QEAA@PEBG@Z` at `0x18002c2ae`
- `wbemcomn!??0WString2@@QEAA@PEBG@Z` at `0x18002c186`
- `wbemcomn!??0WString2@@QEAA@PEBG@Z` at `0x18002c2ae`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002c412`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002c4de`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002c563`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002c64d`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002c668`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002c926`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002c412`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002c4de`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002c563`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002c64d`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002c668`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002c926`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18002c2bc`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18002c2cd`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18002c2de`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18002c2eb`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18002c2bc`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18002c2cd`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18002c2de`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x18002c2eb`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18002c0f9`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18002c0f9`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18002c126`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18002c126`
- `wbemcomn!GetMemLogObject` at `0x18002c4ac`
- `wbemcomn!GetMemLogObject` at `0x18002c716`
- `wbemcomn!GetMemLogObject` at `0x18002c7c3`
- `wbemcomn!GetMemLogObject` at `0x18002c81a`
- `wbemcomn!GetMemLogObject` at `0x18002c89a`
- `wbemcomn!GetMemLogObject` at `0x18002c98e`
- `wbemcomn!GetMemLogObject` at `0x18002c4ac`
- `wbemcomn!GetMemLogObject` at `0x18002c716`
- `wbemcomn!GetMemLogObject` at `0x18002c7c3`
- `wbemcomn!GetMemLogObject` at `0x18002c81a`
- `wbemcomn!GetMemLogObject` at `0x18002c89a`
- `wbemcomn!GetMemLogObject` at `0x18002c98e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002c4b7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002c724`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002c7d3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002c82a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002c8a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002c99c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002c4b7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002c724`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002c7d3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002c82a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002c8a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002c99c`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CRepository::OpenScope(
        struct IWmiDbSession *a1,
        unsigned __int16 *a2,
        struct _GUID *a3,
        struct IWmiDbController **a4,
        struct IWmiDbSession **a5,
        struct IWmiDbHandle **a6,
        struct IWmiDbHandle **a7)
{
  struct IWmiDbSession **v10; // rdi
  unsigned int v11; // esi
  struct IWmiDbHandle **v12; // rax
  struct IWmiDbHandle **v13; // r12
  struct IWbemPath *NewPath; // rax
  struct IWbemPath *v15; // r14
  struct IWmiDbSession *v16; // rbx
  __int64 Add; // rdi
  int v18; // edi
  WCHAR *v19; // rax
  WCHAR *v20; // rbx
  WCHAR *v21; // rsi
  const unsigned __int16 *i; // rdi
  unsigned __int16 v23; // bx
  WCHAR v24; // cx
  struct IWbemPath *v25; // rax
  struct IWbemPath *v26; // rsi
  HRESULT (__stdcall *SetText)(IWbemPath *, ULONG, LPCWSTR); // rbx
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rbx
  CMemoryLog *v31; // rax
  CMemoryLog *v33; // rax
  CMemoryLog *v34; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v36; // rax
  CMemoryLog *v37; // rax
  WCHAR DestStr; // [rsp+40h] [rbp-C0h] BYREF
  struct IWmiDbHandle *v39; // [rsp+48h] [rbp-B8h] BYREF
  int v40; // [rsp+50h] [rbp-B0h] BYREF
  struct IWmiDbHandle *v41; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v42; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v43; // [rsp+64h] [rbp-9Ch]
  struct IWbemPath *v44; // [rsp+68h] [rbp-98h] BYREF
  struct IWbemPath *v45; // [rsp+70h] [rbp-90h] BYREF
  WCHAR *v46; // [rsp+78h] [rbp-88h]
  void *v47[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v48; // [rsp+90h] [rbp-70h] BYREF
  __int64 v49; // [rsp+98h] [rbp-68h]
  struct IWmiDbController *v50; // [rsp+A0h] [rbp-60h]
  char v51[8]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v52[40]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v53[104]; // [rsp+D8h] [rbp-28h] BYREF
  struct _GUID *SrcStr; // [rsp+160h] [rbp+60h] BYREF

  SrcStr = a3;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = a5;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, a5, a7);
  }
  else
  {
    v10 = a5;
  }
  v11 = 0;
  v42 = 0;
  v12 = a7;
  if ( a7 && v10 )
  {
    v13 = a6;
    if ( a6 )
      *a6 = 0;
    *v12 = 0;
    *v10 = 0;
    if ( a4 )
      *a4 = 0;
    if ( a2 )
    {
      NewPath = ConfigMgr::GetNewPath();
      v15 = NewPath;
      if ( NewPath )
      {
        v45 = NewPath;
        if ( ((int (__fastcall *)(struct IWbemPath *, __int64, unsigned __int16 *))NewPath->lpVtbl->SetText)(
               NewPath,
               12,
               a2) < 0 )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, -2147217394);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              123,
              WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
              2147749902LL);
          }
          CReleaseMe::release((CReleaseMe *)&v45);
          return 2147749902LL;
        }
        else
        {
          ((void (__fastcall *)(struct IWbemPath *, unsigned int *))v15->lpVtbl->GetNamespaceCount)(v15, &v42);
          v41 = 0;
          v39 = 0;
          CInCritSec::CInCritSec((CInCritSec *)v51, (struct _RTL_CRITICAL_SECTION *)g_globCS);
          v16 = CRepository::m_pEseSession;
          if ( CRepository::m_pEseSession )
          {
            (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)CRepository::m_pEseSession + 8LL))(CRepository::m_pEseSession);
            v16 = CRepository::m_pEseSession;
          }
          CInCritSec::~CInCritSec((CInCritSec *)v51);
          Add = GetAddRef<IWmiDbController>();
          v50 = (struct IWmiDbController *)Add;
          if ( a1 )
          {
            (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)v16 + 16LL))(v16);
            (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)a1 + 8LL))(a1);
          }
          else
          {
            a1 = v16;
          }
          if ( (int)CRepository::OpenEseNs(a1, L"ROOT", &v39) < 0 )
          {
            (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)a1 + 16LL))(a1);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)Add + 16LL))(Add);
            v36 = GetMemLogObject();
            CMemoryLog::Write(v36, -2147217398);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                124,
                WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
                2147749898LL);
            }
            CReleaseMe::release((CReleaseMe *)&v45);
            return 2147749898LL;
          }
          else
          {
            WString2::WString2((WString2 *)v53, L"ROOT");
            while ( 1 )
            {
              v43 = v11;
              if ( v11 >= v42 )
                break;
              v48 = 0;
              v40 = 0;
              v18 = ((__int64 (__fastcall *)(struct IWbemPath *, _QWORD, int *, _QWORD))v15->lpVtbl->GetNamespaceAt)(
                      v15,
                      v11,
                      &v40,
                      0);
              if ( v18 < 0 )
                goto LABEL_50;
              v19 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v40 + 1), 2u));
              v20 = v19;
              v46 = v19;
              if ( !v19 )
              {
                v18 = -2147217402;
                goto LABEL_50;
              }
              v47[0] = v19;
              v47[1] = 0;
              v18 = ((__int64 (__fastcall *)(struct IWbemPath *, _QWORD, int *, WCHAR *))v15->lpVtbl->GetNamespaceAt)(
                      v15,
                      v11,
                      &v40,
                      v19);
              if ( v18 < 0 || !*v20 )
                goto LABEL_49;
              if ( !v11 )
              {
                v21 = v20;
                for ( i = L"root"; ; ++i )
                {
                  v23 = *i;
                  if ( *i )
                  {
                    if ( v23 > 0x7Fu )
                    {
                      LOWORD(SrcStr) = *i;
                      DestStr = 0;
                      v23 = LCMapStringW(0x7Fu, 0x100u, (LPCWSTR)&SrcStr, 1, &DestStr, 1)
                          ? DestStr
                          : (unsigned __int16)SrcStr;
                    }
                    else if ( (unsigned __int16)(v23 - 65) <= 0x19u )
                    {
                      v23 += 32;
                    }
                  }
                  else if ( !*v21 )
                  {
                    goto LABEL_47;
                  }
                  v24 = *v21;
                  if ( *v21 > 0x7Fu )
                  {
                    LOWORD(SrcStr) = *v21;
                    DestStr = 0;
                    v24 = LCMapStringW(0x7Fu, 0x100u, (LPCWSTR)&SrcStr, 1, &DestStr, 1)
                        ? DestStr
                        : (unsigned __int16)SrcStr;
                  }
                  else if ( (unsigned __int16)(v24 - 65) <= 0x19u )
                  {
                    v24 += 32;
                  }
                  if ( v23 != v24 )
                    break;
                  ++v21;
                }
                v18 = -2147217394;
LABEL_49:
                CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v47);
LABEL_50:
                if ( v39 )
                  (*(void (__fastcall **)(struct IWmiDbHandle *))(*(_QWORD *)v39 + 16LL))(v39);
                v39 = 0;
                if ( v41 )
                  (*(void (__fastcall **)(struct IWmiDbHandle *))(*(_QWORD *)v41 + 16LL))(v41);
                v41 = 0;
                if ( v50 )
                  (*(void (__fastcall **)(struct IWmiDbController *))(*(_QWORD *)v50 + 16LL))(v50);
                if ( a1 )
                  (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)a1 + 16LL))(a1);
                if ( v18 == -2147217406 )
                {
                  WString2::~WString2((WString2 *)v53);
                  ((void (__fastcall *)(struct IWbemPath *))v15->lpVtbl->Release)(v15);
                  v45 = 0;
                  return 2147749890LL;
                }
                else
                {
                  if ( v18 < 0 )
                  {
                    v31 = GetMemLogObject();
                    CMemoryLog::Write(v31, v18);
                  }
                  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      126,
                      WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
                      (unsigned int)v18);
                  }
                  WString2::~WString2((WString2 *)v53);
                  ((void (__fastcall *)(struct IWbemPath *))v15->lpVtbl->Release)(v15);
                  v45 = 0;
                  return (unsigned int)v18;
                }
              }
              WString2::WString2((WString2 *)v52, L"__namespace='");
              WString2::operator+=(v52, v20);
              WString2::operator+=(v52, L"'");
              WString2::operator+=(v53, L"\\");
              WString2::operator+=(v53, v20);
              v25 = ConfigMgr::GetNewPath();
              v26 = v25;
              if ( !v25 )
              {
                v18 = -2147217402;
                goto LABEL_120;
              }
              v44 = v25;
              SetText = v25->lpVtbl->SetText;
              v28 = WString2::operator unsigned short *(v52);
              v18 = ((__int64 (__fastcall *)(struct IWbemPath *, __int64, __int64))SetText)(v26, 12, v28);
              if ( v18 < 0 )
                goto LABEL_118;
              v29 = (*(__int64 (__fastcall **)(struct IWmiDbSession *, struct IWmiDbHandle *, struct IWbemPath *, _QWORD, GUID *, __int64 *))(*(_QWORD *)a1 + 32LL))(
                      a1,
                      v39,
                      v26,
                      0,
                      &IID_IWbemClassObject,
                      &v48);
              v18 = v29;
              if ( v29 == -2147217406 )
              {
                v18 = -2147217394;
LABEL_79:
                ((void (__fastcall *)(struct IWbemPath *))v26->lpVtbl->Release)(v26);
                v44 = 0;
                WString2::~WString2((WString2 *)v52);
                CWin32DefaultArena::WbemMemFree(v46);
                goto LABEL_50;
              }
              if ( v29 < 0 )
              {
LABEL_118:
                CReleaseMe::release((CReleaseMe *)&v44);
LABEL_120:
                WString2::~WString2((WString2 *)v52);
                CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v47);
                goto LABEL_50;
              }
              v30 = v48;
              v49 = v48;
              v18 = (*(__int64 (__fastcall **)(struct IWmiDbSession *, struct IWmiDbHandle *, struct IWbemPath *, _QWORD, int, struct IWmiDbHandle **))(*(_QWORD *)a1 + 24LL))(
                      a1,
                      v39,
                      v26,
                      0,
                      1,
                      &v41);
              if ( v39 )
                (*(void (__fastcall **)(struct IWmiDbHandle *))(*(_QWORD *)v39 + 16LL))(v39);
              v39 = v41;
              v41 = 0;
              if ( v18 < 0 )
              {
                if ( v30 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
                v49 = 0;
                goto LABEL_79;
              }
              if ( v30 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
              v49 = 0;
              ((void (__fastcall *)(struct IWbemPath *))v26->lpVtbl->Release)(v26);
              v44 = 0;
              WString2::~WString2((WString2 *)v52);
LABEL_47:
              CWin32DefaultArena::WbemMemFree(v46);
              v11 = v43 + 1;
            }
            if ( v41 )
              (*(void (__fastcall **)(struct IWmiDbHandle *))(*(_QWORD *)v41 + 16LL))(v41);
            v41 = 0;
            if ( v13 )
              *v13 = 0;
            *a7 = v39;
            *a5 = a1;
            if ( a4 )
              *a4 = v50;
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, 0);
            }
            WString2::~WString2((WString2 *)v53);
            ((void (__fastcall *)(struct IWbemPath *))v15->lpVtbl->Release)(v15);
            v45 = 0;
            return 0;
          }
        }
      }
      else
      {
        v34 = GetMemLogObject();
        CMemoryLog::Write(v34, -2147217402);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            122,
            WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
            2147749894LL);
        }
        return 2147749894LL;
      }
    }
    else if ( CRepository::m_pEseRoot )
    {
      if ( a4 )
        *a4 = (struct IWmiDbController *)GetAddRef<IWmiDbController>();
      *v10 = (struct IWmiDbSession *)GetAddRef<IWmiDbSession>();
      *a7 = (struct IWmiDbHandle *)GetAddRef<IWmiDbHandle>();
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, 0);
      }
      return 0;
    }
    else
    {
      v33 = GetMemLogObject();
      CMemoryLog::Write(v33, -2147217398);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          120,
          WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
          2147749898LL);
      }
      return 2147749898LL;
    }
  }
  else
  {
    v37 = GetMemLogObject();
    CMemoryLog::Write(v37, -2147217400);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, 2147749896LL);
    }
    return 2147749896LL;
  }
}

```

## disassembly

```asm
0x18002c010  mov     [rsp-8+SrcStr], r8
0x18002c015  push    rbp
0x18002c016  push    rbx
0x18002c017  push    rsi
0x18002c018  push    rdi
0x18002c019  push    r12
0x18002c01b  push    r13
0x18002c01d  push    r14
0x18002c01f  push    r15
0x18002c021  lea     rbp, [rsp-8]
0x18002c026  sub     rsp, 108h
0x18002c02d  mov     r13, r9
0x18002c030  mov     rbx, rdx
0x18002c033  mov     r15, rcx
0x18002c036  lea     r14, WPP_GLOBAL_Control
0x18002c03d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c044  cmp     rcx, r14
0x18002c047  jz      short loc_18002C053
0x18002c049  test    byte ptr [rcx+1Ch], 1
0x18002c04d  jnz     loc_18002C6AF
0x18002c053  mov     rdi, [rbp+40h+arg_20]
0x18002c057  xor     esi, esi
0x18002c059  mov     [rsp+140h+var_E0], esi
0x18002c05d  mov     rax, [rbp+40h+arg_30]
0x18002c064  test    rax, rax
0x18002c067  jz      loc_18002C98E
0x18002c06d  test    rdi, rdi
0x18002c070  jz      loc_18002C98E
0x18002c076  mov     r12, [rbp+40h+arg_28]
0x18002c07a  test    r12, r12
0x18002c07d  jz      short loc_18002C083
0x18002c07f  mov     [r12], rsi
0x18002c083  mov     [rax], rsi
0x18002c086  mov     [rdi], rsi
0x18002c089  test    r13, r13
0x18002c08c  jz      short loc_18002C092
0x18002c08e  mov     [r13+0], rsi
0x18002c092  test    rbx, rbx
0x18002c095  jz      loc_18002C70D
0x18002c09b  call    ?GetNewPath@ConfigMgr@@SAPEAUIWbemPath@@XZ; ConfigMgr::GetNewPath(void)
0x18002c0a0  mov     r14, rax
0x18002c0a3  test    rax, rax
0x18002c0a6  jz      loc_18002C7C3
0x18002c0ac  mov     [rsp+140h+var_D0], rax
0x18002c0b1  mov     rax, [rax]
0x18002c0b4  mov     r8, rbx
0x18002c0b7  mov     edx, 0Ch
0x18002c0bc  mov     rcx, r14
0x18002c0bf  mov     rax, [rax+18h]
0x18002c0c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0c8  test    eax, eax
0x18002c0ca  js      loc_18002C81A
0x18002c0d0  mov     rax, [r14]
0x18002c0d3  lea     rdx, [rsp+140h+var_E0]
0x18002c0d8  mov     rcx, r14
0x18002c0db  mov     rax, [rax+40h]
0x18002c0df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0e4  mov     [rsp+140h+var_E8], rsi
0x18002c0e9  mov     [rsp+140h+var_F8], rsi
0x18002c0ee  lea     rdx, ?g_globCS@@3VCStaticCritSec@@A; CStaticCritSec g_globCS
0x18002c0f5  lea     rcx, [rbp+40h+var_98]
0x18002c0f9  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18002c0ff  nop
0x18002c100  mov     rbx, cs:?m_pEseSession@CRepository@@0PEAUIWmiDbSession@@EA; IWmiDbSession * CRepository::m_pEseSession
0x18002c107  test    rbx, rbx
0x18002c10a  jz      short loc_18002C122
0x18002c10c  mov     rax, [rbx]
0x18002c10f  mov     rcx, rbx
0x18002c112  mov     rax, [rax+8]
0x18002c116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c11b  mov     rbx, cs:?m_pEseSession@CRepository@@0PEAUIWmiDbSession@@EA; IWmiDbSession * CRepository::m_pEseSession
0x18002c122  lea     rcx, [rbp+40h+var_98]
0x18002c126  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18002c12c  call    ??$GetAddRef@UIWmiDbController@@@@YAPEAUIWmiDbController@@AEAPEAU0@@Z; GetAddRef<IWmiDbController>(IWmiDbController * &)
0x18002c131  mov     rdi, rax
0x18002c134  mov     [rbp+40h+var_A0], rax
0x18002c138  test    r15, r15
0x18002c13b  jz      loc_18002C624
0x18002c141  mov     rdx, [rbx]
0x18002c144  mov     rcx, rbx
0x18002c147  mov     rax, [rdx+10h]
0x18002c14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c150  mov     rcx, [r15]
0x18002c153  mov     rax, [rcx+8]
0x18002c157  mov     rcx, r15
0x18002c15a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c15f  lea     r8, [rsp+140h+var_F8]; struct IWmiDbHandle **
0x18002c164  lea     rdx, aRoot; "ROOT"
0x18002c16b  mov     rcx, r15; struct IWmiDbSession *
0x18002c16e  call    ?OpenEseNs@CRepository@@SAJPEAUIWmiDbSession@@PEBGPEAPEAUIWmiDbHandle@@@Z; CRepository::OpenEseNs(IWmiDbSession *,ushort const *,IWmiDbHandle * *)
0x18002c173  test    eax, eax
0x18002c175  js      loc_18002C87C
0x18002c17b  lea     rdx, aRoot; "ROOT"
0x18002c182  lea     rcx, [rbp+40h+var_68]
0x18002c186  call    cs:__imp_??0WString2@@QEAA@PEBG@Z; WString2::WString2(ushort const *)
0x18002c18c  nop
0x18002c18d  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18002c194  mov     [rsp+140h+var_DC], esi
0x18002c198  cmp     esi, [rsp+140h+var_E0]
0x18002c19c  jnb     loc_18002C501
0x18002c1a2  mov     [rbp+40h+var_B0], 0
0x18002c1aa  mov     [rsp+140h+var_F0], 0
0x18002c1b2  mov     rax, [r14]
0x18002c1b5  xor     r9d, r9d
0x18002c1b8  lea     r8, [rsp+140h+var_F0]
0x18002c1bd  mov     edx, esi
0x18002c1bf  mov     rcx, r14
0x18002c1c2  mov     rax, [rax+50h]
0x18002c1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1cb  mov     edi, eax
0x18002c1cd  test    eax, eax
0x18002c1cf  js      loc_18002C43D
0x18002c1d5  mov     ecx, [rsp+140h+var_F0]
0x18002c1d9  inc     ecx
0x18002c1db  mov     eax, 2
0x18002c1e0  mul     rcx
0x18002c1e3  cmovb   rax, rbx
0x18002c1e7  mov     rcx, rax
0x18002c1ea  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002c1f0  mov     rbx, rax
0x18002c1f3  mov     [rsp+140h+var_C8], rax
0x18002c1f8  test    rax, rax
0x18002c1fb  jz      loc_18002C93B
0x18002c201  mov     [rbp+40h+var_C0], rax
0x18002c205  mov     [rbp+40h+var_B8], 0
0x18002c20d  mov     rcx, [r14]
0x18002c210  mov     rax, [rcx+50h]
0x18002c214  mov     r9, rbx
0x18002c217  lea     r8, [rsp+140h+var_F0]
0x18002c21c  mov     edx, esi
0x18002c21e  mov     rcx, r14
0x18002c221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c226  mov     edi, eax
0x18002c228  test    eax, eax
0x18002c22a  js      loc_18002C434
0x18002c230  cmp     word ptr [rbx], 0
0x18002c234  jz      loc_18002C434
0x18002c23a  test    esi, esi
0x18002c23c  jnz     short loc_18002C2A3
0x18002c23e  mov     rsi, rbx
0x18002c241  lea     rdi, aRoot_0; "root"
0x18002c248  movzx   ebx, word ptr [rdi]
0x18002c24b  test    bx, bx
0x18002c24e  jz      short loc_18002C298
0x18002c250  cmp     bx, 7Fh
0x18002c254  ja      loc_18002C594
0x18002c25a  lea     eax, [rbx-41h]
0x18002c25d  cmp     ax, 19h
0x18002c261  jbe     short loc_18002C28C
0x18002c263  movzx   ecx, word ptr [rsi]
0x18002c266  cmp     cx, 7Fh
0x18002c26a  ja      loc_18002C5DC
0x18002c270  lea     eax, [rcx-41h]
0x18002c273  cmp     ax, 19h
0x18002c277  jbe     short loc_18002C292
0x18002c279  cmp     bx, cx
0x18002c27c  jnz     loc_18002C42F
0x18002c282  add     rdi, 2
0x18002c286  add     rsi, 2
0x18002c28a  jmp     short loc_18002C248
0x18002c28c  add     bx, 20h ; ' '
0x18002c290  jmp     short loc_18002C263
0x18002c292  add     cx, 20h ; ' '
0x18002c296  jmp     short loc_18002C279
0x18002c298  cmp     word ptr [rsi], 0
0x18002c29c  jnz     short loc_18002C263
0x18002c29e  jmp     loc_18002C419
0x18002c2a3  lea     rdx, aNamespace_3; "__namespace='"
0x18002c2aa  lea     rcx, [rbp+40h+var_90]
0x18002c2ae  call    cs:__imp_??0WString2@@QEAA@PEBG@Z; WString2::WString2(ushort const *)
0x18002c2b4  nop
0x18002c2b5  mov     rdx, rbx
0x18002c2b8  lea     rcx, [rbp+40h+var_90]
0x18002c2bc  call    cs:__imp_??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x18002c2c2  lea     rdx, asc_1800EB884; "'"
0x18002c2c9  lea     rcx, [rbp+40h+var_90]
0x18002c2cd  call    cs:__imp_??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x18002c2d3  lea     rdx, Delimiter; "\\"
0x18002c2da  lea     rcx, [rbp+40h+var_68]
0x18002c2de  call    cs:__imp_??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x18002c2e4  mov     rdx, rbx
0x18002c2e7  lea     rcx, [rbp+40h+var_68]
0x18002c2eb  call    cs:__imp_??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x18002c2f1  call    ?GetNewPath@ConfigMgr@@SAPEAUIWbemPath@@XZ; ConfigMgr::GetNewPath(void)
0x18002c2f6  mov     rsi, rax
0x18002c2f9  test    rax, rax
0x18002c2fc  jz      loc_18002C91D
0x18002c302  mov     [rsp+140h+var_D8], rax
0x18002c307  mov     rcx, [rax]
0x18002c30a  mov     rbx, [rcx+18h]
0x18002c30e  lea     rcx, [rbp+40h+var_90]
0x18002c312  call    cs:__imp_??BWString2@@QEAAPEAGXZ; WString2::operator ushort *(void)
0x18002c318  mov     r8, rax
0x18002c31b  mov     edx, 0Ch
0x18002c320  mov     rcx, rsi
0x18002c323  mov     rax, rbx
0x18002c326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c32b  mov     edi, eax
0x18002c32d  test    eax, eax
0x18002c32f  js      loc_18002C911
0x18002c335  mov     rax, [r15]
0x18002c338  lea     rcx, [rbp+40h+var_B0]
0x18002c33c  mov     qword ptr [rsp+140h+cchDest], rcx
0x18002c341  lea     rcx, IID_IWbemClassObject
0x18002c348  mov     [rsp+140h+lpDestStr], rcx
0x18002c34d  xor     r9d, r9d
0x18002c350  mov     r8, rsi
0x18002c353  mov     rdx, [rsp+140h+var_F8]
0x18002c358  mov     rcx, r15
0x18002c35b  mov     rax, [rax+20h]
0x18002c35f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c364  mov     edi, eax
0x18002c366  cmp     eax, 80041002h
0x18002c36b  jz      loc_18002C62C
0x18002c371  test    eax, eax
0x18002c373  js      loc_18002C911
0x18002c379  mov     rbx, [rbp+40h+var_B0]
0x18002c37d  mov     [rbp+40h+var_A8], rbx
0x18002c381  mov     rax, [r15]
0x18002c384  lea     rcx, [rsp+140h+var_E8]
0x18002c389  mov     qword ptr [rsp+140h+cchDest], rcx
0x18002c38e  mov     dword ptr [rsp+140h+lpDestStr], 1
0x18002c396  xor     r9d, r9d
0x18002c399  mov     r8, rsi
0x18002c39c  mov     rdx, [rsp+140h+var_F8]
0x18002c3a1  mov     rcx, r15
0x18002c3a4  mov     rax, [rax+18h]
0x18002c3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c3ad  mov     edi, eax
0x18002c3af  mov     rcx, [rsp+140h+var_F8]
0x18002c3b4  test    rcx, rcx
0x18002c3b7  jz      short loc_18002C3C5
0x18002c3b9  mov     rax, [rcx]
0x18002c3bc  mov     rax, [rax+10h]
0x18002c3c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c3c5  mov     rax, [rsp+140h+var_E8]
0x18002c3ca  mov     [rsp+140h+var_F8], rax
0x18002c3cf  mov     [rsp+140h+var_E8], 0
0x18002c3d8  test    edi, edi
0x18002c3da  js      loc_18002C691
0x18002c3e0  test    rbx, rbx
0x18002c3e3  jz      short loc_18002C3F4
0x18002c3e5  mov     rax, [rbx]
0x18002c3e8  mov     rcx, rbx
0x18002c3eb  mov     rax, [rax+10h]
0x18002c3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c3f4  xor     ebx, ebx
0x18002c3f6  mov     [rbp+40h+var_A8], rbx
0x18002c3fa  mov     rax, [rsi]
0x18002c3fd  mov     rcx, rsi
0x18002c400  mov     rax, [rax+10h]
0x18002c404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c409  mov     [rsp+140h+var_D8], rbx
0x18002c40e  lea     rcx, [rbp+40h+var_90]
0x18002c412  call    cs:__imp_??1WString2@@QEAA@XZ; WString2::~WString2(void)
0x18002c418  nop
0x18002c419  mov     rcx, [rsp+140h+var_C8]
0x18002c41e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002c424  mov     esi, [rsp+140h+var_DC]
0x18002c428  inc     esi
0x18002c42a  jmp     loc_18002C18D
0x18002c42f  mov     edi, 8004100Eh
0x18002c434  lea     rcx, [rbp+40h+var_C0]
0x18002c438  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x18002c43d  mov     rcx, [rsp+140h+var_F8]
0x18002c442  test    rcx, rcx
0x18002c445  jz      short loc_18002C453
0x18002c447  mov     rax, [rcx]
0x18002c44a  mov     rax, [rax+10h]
0x18002c44e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c453  mov     [rsp+140h+var_F8], 0
0x18002c45c  mov     rcx, [rsp+140h+var_E8]
0x18002c461  test    rcx, rcx
0x18002c464  jnz     loc_18002C945
0x18002c46a  mov     [rsp+140h+var_E8], 0
0x18002c473  mov     rcx, [rbp+40h+var_A0]
0x18002c477  test    rcx, rcx
0x18002c47a  jz      short loc_18002C488
0x18002c47c  mov     rax, [rcx]
0x18002c47f  mov     rax, [rax+10h]
0x18002c483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c488  test    r15, r15
0x18002c48b  jz      short loc_18002C49C
0x18002c48d  mov     rax, [r15]
0x18002c490  mov     rcx, r15
0x18002c493  mov     rax, [rax+10h]
0x18002c497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c49c  cmp     edi, 80041002h
0x18002c4a2  jz      loc_18002C664
0x18002c4a8  test    edi, edi
0x18002c4aa  jns     short loc_18002C4BD
0x18002c4ac  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002c4b2  mov     edx, edi
0x18002c4b4  mov     rcx, rax
0x18002c4b7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002c4bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c4c4  lea     rax, WPP_GLOBAL_Control
0x18002c4cb  cmp     rcx, rax
0x18002c4ce  jz      short loc_18002C4DA
0x18002c4d0  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
