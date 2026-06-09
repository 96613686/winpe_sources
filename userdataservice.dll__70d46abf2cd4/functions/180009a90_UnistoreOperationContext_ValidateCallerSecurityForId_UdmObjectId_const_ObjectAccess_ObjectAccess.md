# UnistoreOperationContext::ValidateCallerSecurityForId(UdmObjectId const &,ObjectAccess *,ObjectAccess *)

- ea: `0x180009a90`
- end: `0x18000a51f`
- name: `?ValidateCallerSecurityForId@UnistoreOperationContext@@UEAAJAEBUUdmObjectId@@PEAW4ObjectAccess@@1@Z`
- size: `2703`
- prototype: `__int64 __fastcall(UnistoreOperationContext *__hidden this, const struct UdmObjectId *, enum ObjectAccess *, enum ObjectAccess *)`
- caller_count: `7`
- callee_count: `20`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800096a0`
- `0x18000bb30`
- `0x1800b74c0`
- `0x1800b7980`
- `0x1800b7fc0`
- `0x180122f70`
- `0x180127910`

## callees

- `0x180008f0c`
- `0x180009a90`
- `0x18000a780`
- `0x18000ae80`
- `0x18000b22c`
- `0x18000b2d0`
- `0x18000b620`
- `0x180043124`
- `0x18004e380`
- `0x180054f2c`
- `0x180072ccc`
- `0x180096778`
- `0x1800977ac`
- `0x180097db8`
- `0x18009de18`
- `0x1800a5630`
- `0x1800be290`
- `0x1800e482c`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009b92`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009b92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009d11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009f7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009d11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009f7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009ef7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009fc8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a066`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a2ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009ef7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009fc8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a066`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a2ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009f5e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a031`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009f5e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a031`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180009db9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180009dce`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180009db9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180009dce`

## string_xrefs

- `0x180009fda`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\unistorecontext.cpp`
- `0x180009fff`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\unistorecontext.cpp`
- `0x18000a1e6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\unistorecontext.cpp`
- `0x18000a262`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\unistorecontext.cpp`
- `0x18000a351`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\unistorecontext.cpp`
- `0x18000a4d5`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\unistorecontext.cpp`
- `0x180009faf`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000a0e0`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000a226`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000a244`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000a2a1`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000a377`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`

## pseudocode

```c
__int64 __fastcall UnistoreOperationContext::ValidateCallerSecurityForId(
        UnistoreOperationContext *this,
        const struct UdmObjectId *a2,
        enum ObjectAccess *a3,
        enum ObjectAccess *a4)
{
  enum ObjectAccess *v4; // r13
  unsigned int v7; // r12d
  __int64 v8; // xmm0_8
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // ebx
  ServiceDataSession *v12; // r14
  unsigned int v13; // r15d
  int PropertiesForStore; // eax
  int v15; // ebx
  StorePropertyCache *v16; // rbx
  unsigned __int16 *v17; // rax
  __int64 v18; // r8
  int v19; // ecx
  int v20; // edx
  unsigned int v21; // ebx
  ServiceDataSession *v22; // r15
  int v23; // eax
  int v24; // r14d
  int v25; // ecx
  unsigned int v26; // ebx
  ServiceDataSession *v27; // r14
  int updated; // eax
  int v29; // r15d
  int v30; // ecx
  __int64 v31; // r14
  unsigned int v32; // eax
  __int64 v33; // r12
  unsigned int v34; // r15d
  struct _RTL_CRITICAL_SECTION *v35; // rbx
  __int64 v36; // r13
  __int64 v37; // rdx
  char v38; // cl
  unsigned __int64 v39; // r8
  __int64 *v40; // r14
  __int64 *v41; // rcx
  __int64 *v42; // rax
  __int64 *v43; // rcx
  __int64 v44; // rdx
  __int64 **v45; // rdx
  __int64 *v46; // rax
  __int64 *v47; // rax
  int v48; // esi
  ServiceDataSession *v49; // rdi
  int v50; // eax
  unsigned int v51; // ebx
  __int64 result; // rax
  int EnterpriseIdentity; // eax
  const unsigned __int16 *v54; // r14
  __int64 v55; // rcx
  __int64 v56; // r15
  int v57; // eax
  int v58; // edx
  int v59; // ecx
  struct _RTL_CRITICAL_SECTION *v60; // r14
  char *v61; // rax
  void *v62; // rbx
  __int64 v63; // rax
  void *v64; // rcx
  unsigned int v65; // ebx
  unsigned __int64 v66; // rcx
  int v67; // r15d
  int v68; // r14d
  int v69; // eax
  __int64 v70; // r9
  int v71; // ecx
  int v72; // r9d
  int v73; // ecx
  int v74; // r9d
  __int64 v75; // r9
  __int64 v76; // r9
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // r9
  int v80; // ecx
  int IsCallerOnAccessList; // eax
  unsigned int v82; // edi
  WINBOOL fPending[2]; // [rsp+30h] [rbp-69h] BYREF
  union _RTL_RUN_ONCE *v84; // [rsp+38h] [rbp-61h] BYREF
  struct _FILETIME v85; // [rsp+40h] [rbp-59h] BYREF
  LPVOID Context; // [rsp+48h] [rbp-51h] BYREF
  int v87; // [rsp+50h] [rbp-49h] BYREF
  int v88; // [rsp+54h] [rbp-45h] BYREF
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+58h] [rbp-41h] BYREF
  enum ObjectAccess *v90; // [rsp+68h] [rbp-31h]
  enum ObjectAccess *v91; // [rsp+70h] [rbp-29h]
  __int64 v92; // [rsp+80h] [rbp-19h] BYREF
  int v93; // [rsp+88h] [rbp-11h]
  char v94; // [rsp+90h] [rbp-9h]

  v90 = a4;
  v4 = a4;
  v91 = a3;
  v7 = 2;
  if ( a3 )
    *(_DWORD *)a3 = 2;
  if ( a4 )
    *(_DWORD *)a4 = 2;
  if ( !(*(unsigned int (__fastcall **)(UnistoreOperationContext *))(*(_QWORD *)this + 80LL))(this) )
  {
    Log_HREvent(
      2147549183LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\unistorecontext.cpp",
      558);
    return 2147549183LL;
  }
  v8 = *(_QWORD *)a2;
  v87 = 0;
  v88 = 0;
  v93 = *((_DWORD *)a2 + 2);
  v9 = *(_QWORD *)this;
  v92 = v8;
  v10 = (*(__int64 (__fastcall **)(UnistoreOperationContext *, __int64 *, int *, int *))(v9 + 64))(
          this,
          &v92,
          &v87,
          &v88);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v12 = (ServiceDataSession *)*((_QWORD *)this + 1);
    if ( !v12 )
      goto LABEL_52;
    if ( *((_DWORD *)a2 + 1) == 41 )
    {
      v15 = UnistoreOperationContext::ValidateCallerOwnsGrouping(this, *((_DWORD *)a2 + 2));
      goto LABEL_19;
    }
    v13 = *(_DWORD *)a2;
    PropertiesForStore = ServiceDataSession::EnsureIntializedSecurityAndAppInfo(v12);
    v15 = PropertiesForStore;
    if ( PropertiesForStore < 0 )
    {
      v79 = 1448;
    }
    else
    {
      v85 = 0;
      fPending[0] = 0;
      Context = 0;
      InitOnceBeginInitialize(&stru_18015EA68, 0, fPending, &Context);
      v16 = (StorePropertyCache *)Context;
      if ( !Context )
      {
        v84 = &stru_18015EA68;
        v16 = (StorePropertyCache *)tlx::_LazyImpl<StorePropertyCache,tlx::lazy_construct<StorePropertyCache>,tlx::static_lazy<StorePropertyCache,0,tlx::lazy_construct<StorePropertyCache>>>::_Initializer::_Construct(&v84);
        tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v84);
      }
      PropertiesForStore = StorePropertyCache::GetPropertiesForStore(v16, v13, (const struct StorePropertySet **)&v85);
      v15 = PropertiesForStore;
      if ( PropertiesForStore >= 0 )
      {
        v17 = *(unsigned __int16 **)(*(_QWORD *)&v85 + 8LL);
        if ( !v17 )
          goto LABEL_18;
        v18 = *((_QWORD *)v12 + 226) - (_QWORD)v17;
        do
        {
          v19 = *(unsigned __int16 *)((char *)v17 + v18);
          v20 = *v17 - v19;
          if ( v20 )
            break;
          ++v17;
        }
        while ( v19 );
        if ( !v20 )
          v15 = 0;
        else
LABEL_18:
          v15 = -2147024891;
LABEL_19:
        if ( v15 < 0 )
        {
          if ( !*((_QWORD *)this + 1) )
            goto LABEL_34;
          v21 = (*(__int64 (__fastcall **)(UnistoreOperationContext *, __int64))(*(_QWORD *)this + 72LL))(this, 1);
          if ( !v21 )
          {
LABEL_27:
            if ( *((_QWORD *)this + 1) )
            {
              v26 = (*(__int64 (__fastcall **)(UnistoreOperationContext *, __int64))(*(_QWORD *)this + 72LL))(this, 2);
              if ( v26 )
              {
                v27 = (ServiceDataSession *)*((_QWORD *)this + 1);
                updated = ServiceDataSession::EnsureIntializedSecurityAndAppInfo(v27);
                v29 = updated;
                if ( updated < 0 )
                {
                  v76 = 1255;
                }
                else
                {
                  v30 = *((_DWORD *)v27 + 447);
                  if ( (v26 & v30) == 0 )
                  {
                    v29 = -2147024891;
                    goto LABEL_33;
                  }
                  if ( (v30 & v26 & *((_DWORD *)v27 + 449)) != 0 )
                  {
LABEL_32:
                    v29 = 0;
                    goto LABEL_33;
                  }
                  updated = ServiceDataSession::_UpdateSecurityFlagsForPrivacy(v27, 0, v26);
                  v29 = updated;
                  if ( updated >= 0 )
                  {
                    v73 = *((_DWORD *)v27 + 449);
                    v74 = *((_DWORD *)v27 + 447);
                    if ( (v73 & v26 & v74) != 0 )
                      goto LABEL_32;
                    if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x80u) != 0 )
                      McTemplateU0qqq_EventWriteTransfer(
                        v73,
                        (unsigned int)ClientPrivacyCapabilityFailed,
                        v26,
                        v74,
                        *((_DWORD *)v27 + 449));
                    v29 = -2147467260;
LABEL_33:
                    LODWORD(v84) = 0;
                    if ( v29 < 0 )
                      goto LABEL_35;
                    goto LABEL_34;
                  }
                  v76 = 1265;
                }
                Log_HREvent(
                  (unsigned int)updated,
                  1,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
                  v76);
                goto LABEL_33;
              }
            }
LABEL_34:
            LODWORD(v84) = 1;
LABEL_35:
            v31 = *((_QWORD *)this + 1);
            v32 = UdmTypeToUnistoreType(*((unsigned int *)a2 + 1));
            v33 = *(unsigned int *)a2;
            v34 = v32;
            if ( v32 == 0x80000 )
            {
              fPending[0] = *((_DWORD *)a2 + 2);
            }
            else
            {
              v34 = 0x10000;
              fPending[0] = *(_DWORD *)a2;
            }
            v35 = (struct _RTL_CRITICAL_SECTION *)(v31 + 1920);
            EnterCriticalSection((LPCRITICAL_SECTION)(v31 + 1920));
            v36 = v31 + 1960;
            v37 = *(_QWORD *)(v31 + 1976);
            if ( v37 )
            {
              v38 = *(_BYTE *)(v31 + 1992);
              v39 = (unsigned int)fPending[0] + 999 * (v34 + 3 * v33);
              v40 = *(__int64 **)(v37 + 16 * (v39 & ((8LL << v38) - 1)));
              if ( v40 )
              {
                v41 = **(__int64 ***)(v37 + 16 * (v39 & ((8LL << v38) - 1)) + 8);
                while ( v40 != v41 )
                {
                  if ( v40[2] >= v39 )
                  {
                    if ( v40[2] > v39 )
                      break;
                    if ( (_DWORD)v33 == *((_DWORD *)v40 + 6)
                      && v34 == *((_DWORD *)v40 + 7)
                      && fPending[0] == *((_DWORD *)v40 + 8) )
                    {
                      if ( v40 == (__int64 *)v36 )
                        break;
                      if ( CompareFileTime((const FILETIME *)v40 + 6, &FileTime2) )
                      {
                        if ( CompareFileTime((const FILETIME *)v40 + 6, &stru_18013B878) )
                        {
                          v85 = 0;
                          GetSystemTimeAsFileTime(&v85);
                          v66 = v40[6];
                          if ( *(_QWORD *)&v85 >= v66 && *(_QWORD *)&v85 - v66 < 0x430E234000LL )
                          {
                            v67 = *((unsigned __int8 *)v40 + 40);
                            LeaveCriticalSection(v35);
                            goto LABEL_85;
                          }
                        }
                      }
                      v42 = (__int64 *)*v40;
                      v43 = (__int64 *)v40[1];
                      v44 = (8LL << *(_BYTE *)(v36 + 32)) - 1;
                      *v43 = *v40;
                      v42[1] = (__int64)v43;
                      v45 = (__int64 **)(*(_QWORD *)(v36 + 16) + 16 * (v40[2] & v44));
                      v46 = v45[1];
                      if ( *v45 == v40 )
                      {
                        if ( v46 == v40 )
                        {
                          v45[1] = 0;
                          v47 = 0;
                        }
                        else
                        {
                          v47 = (__int64 *)*v40;
                        }
                        *v45 = v47;
                      }
                      else if ( v46 == v40 )
                      {
                        v45[1] = (__int64 *)v40[1];
                      }
                      --*(_QWORD *)(v36 + 24);
                      operator delete(v40);
                      break;
                    }
                  }
                  v40 = (__int64 *)*v40;
                }
              }
            }
            LeaveCriticalSection(v35);
            Context = 0;
            EnterpriseIdentity = UnistoreOperationContext::GetEnterpriseIdentity(
                                   this,
                                   a2,
                                   (unsigned __int16 **)&Context);
            v51 = EnterpriseIdentity;
            if ( EnterpriseIdentity < 0 )
            {
              Log_HREvent(
                (unsigned int)EnterpriseIdentity,
                1,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\unistorecontext.cpp",
                231);
              v64 = Context;
              if ( !Context )
                goto LABEL_79;
              goto LABEL_78;
            }
            v54 = (const unsigned __int16 *)Context;
            v55 = *((unsigned int *)a2 + 1);
            v56 = *((_QWORD *)this + 1);
            v85 = (struct _FILETIME)Context;
            v57 = UdmTypeToUnistoreType(v55);
            v58 = *(_DWORD *)a2;
            v59 = *((_DWORD *)a2 + 2);
            LODWORD(v92) = *(_DWORD *)a2;
            v93 = v59;
            HIDWORD(v92) = v57;
            if ( v57 != 0x80000 )
            {
              HIDWORD(v92) = 0x10000;
              v93 = v58;
            }
            SystemTimeAsFileTime[1] = 0;
            SystemTimeAsFileTime[0] = 0;
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime[1]);
            LOBYTE(SystemTimeAsFileTime[0].dwLowDateTime) = 1;
            if ( !v54 )
            {
LABEL_73:
              v60 = (struct _RTL_CRITICAL_SECTION *)(v56 + 1920);
              EnterCriticalSection((LPCRITICAL_SECTION)(v56 + 1920));
              v61 = (char *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
              v62 = v61;
              if ( v61 )
              {
                v80 = v93;
                *((_QWORD *)v61 + 3) = v92;
                *((_DWORD *)v61 + 8) = v80;
                *(_OWORD *)(v61 + 40) = *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime;
                utl::_HashTable<OLITEMID,utl::pair<OLITEMID const,EdpIdentityManagementInfo>,utl::hash<OLITEMID>,utl::equal_to<OLITEMID>,utl::allocator<utl::pair<OLITEMID const,EdpIdentityManagementInfo>>,0>::_FindInsertPos(
                  v56 + 1960,
                  &v92,
                  v61 + 24);
                if ( v94 )
                {
                  operator delete(v62);
                  v63 = v92;
                }
                else
                {
                  v63 = *(_QWORD *)utl::_HashTable<ServiceDataSession *,utl::pair<ServiceDataSession * const,ATL::CComPtr<SessionComposingStatusHandler>>,utl::hash<ServiceDataSession *>,utl::equal_to<ServiceDataSession *>,utl::allocator<utl::pair<ServiceDataSession * const,ATL::CComPtr<SessionComposingStatusHandler>>>,0>::_InsertAt(
                                     v56 + 1960,
                                     &v85,
                                     &v92,
                                     v62);
                }
              }
              else
              {
                v63 = 0;
              }
              if ( !v63 )
              {
                v51 = -2147024882;
                Log_HREvent(
                  2147942414LL,
                  0,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
                  1549);
                LeaveCriticalSection((LPCRITICAL_SECTION)(v56 + 1920));
                goto LABEL_77;
              }
              v67 = *(unsigned __int8 *)(v63 + 40);
              LeaveCriticalSection(v60);
              if ( Context )
                operator delete(Context);
LABEL_85:
              v68 = (int)v84;
              v65 = 0;
              if ( !v67 )
              {
                v7 = 2;
                goto LABEL_88;
              }
              if ( v87 == 2 )
              {
                v7 = 2;
                v65 = 2;
LABEL_88:
                if ( !v68 && v88 )
                  v7 = v88 == 2;
                goto LABEL_89;
              }
              if ( v87 )
              {
                if ( v87 == 1 )
                {
                  if ( (_DWORD)v84 )
                  {
                    v7 = 2;
                    v65 = 2;
                    goto LABEL_89;
                  }
                  v65 = 1;
                }
              }
              else if ( (_DWORD)v84 )
              {
                v7 = 2;
                v65 = 2;
LABEL_89:
                v4 = v90;
                if ( v7 >= v65 )
                  v7 = v65;
LABEL_59:
                if ( v91 )
                  *(_DWORD *)v91 = v65;
                if ( v4 )
                  *(_DWORD *)v4 = v7;
                result = 0;
                if ( !v65 )
                  return 2147942405LL;
                return result;
              }
              fPending[0] = 0;
              IsCallerOnAccessList = UnistoreOperationContext::IsCallerOnAccessList(this, a2, fPending);
              v82 = IsCallerOnAccessList;
              if ( IsCallerOnAccessList < 0 )
              {
                Log_HREvent(
                  (unsigned int)IsCallerOnAccessList,
                  1,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\unistorecontext.cpp",
                  616);
                return v82;
              }
              v7 = 2;
              if ( fPending[0] )
                v65 = 2;
              goto LABEL_88;
            }
            v69 = ServiceDataSession::EnsureIntializedSecurityAndAppInfo((ServiceDataSession *)v56);
            v51 = v69;
            if ( v69 >= 0 )
            {
              v69 = ServiceDataSession::CheckEdpAccess(
                      (ServiceDataSession *)v56,
                      v54,
                      (unsigned __int8 *)SystemTimeAsFileTime);
              v51 = v69;
              if ( v69 >= 0 )
              {
                if ( !LOBYTE(SystemTimeAsFileTime[0].dwLowDateTime) )
                {
                  v77 = *(_QWORD *)(v56 + 1840);
                  if ( v77 == *(_QWORD *)(v56 + 1848) )
                    v77 = *(_QWORD *)(v56 + 1888);
                  *(_QWORD *)fPending = v77;
                  UserDataServiceTelemetry::EdpCheckAccessDenied<unsigned short const * &,unsigned short const * &,USOID &>(
                    (const unsigned __int16 **)&v85,
                    (const unsigned __int16 **)fPending,
                    (const struct USOID *)&v92);
                  if ( !LOBYTE(SystemTimeAsFileTime[0].dwLowDateTime) )
                  {
                    v78 = *(_QWORD *)(v56 + 1840);
                    if ( v78 == *(_QWORD *)(v56 + 1848) )
                      v78 = *(_QWORD *)(v56 + 1888);
                    *(_QWORD *)fPending = v78;
                    UserDataServiceTelemetry::EdpCheckAccessDenied<unsigned short const * &,unsigned short const * &,USOID &>(
                      (const unsigned __int16 **)&v85,
                      (const unsigned __int16 **)fPending,
                      (const struct USOID *)&v92);
                  }
                }
                goto LABEL_73;
              }
              v70 = 1531;
            }
            else
            {
              v70 = 1530;
            }
            Log_HREvent(
              (unsigned int)v69,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
              v70);
LABEL_77:
            Log_HREvent(
              v51,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\unistorecontext.cpp",
              232);
            v64 = Context;
            if ( !Context )
            {
LABEL_79:
              Log_HREvent(
                v51,
                1,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\unistorecontext.cpp",
                585);
              return v51;
            }
LABEL_78:
            operator delete(v64);
            goto LABEL_79;
          }
          v22 = (ServiceDataSession *)*((_QWORD *)this + 1);
          v23 = ServiceDataSession::EnsureIntializedSecurityAndAppInfo(v22);
          v24 = v23;
          if ( v23 < 0 )
          {
            v75 = 1255;
          }
          else
          {
            v25 = *((_DWORD *)v22 + 447);
            if ( (v21 & v25) == 0 )
            {
              v24 = -2147024891;
              goto LABEL_26;
            }
            if ( (v21 & *((_DWORD *)v22 + 449) & v25) != 0 )
            {
LABEL_25:
              v24 = 0;
              goto LABEL_26;
            }
            v23 = ServiceDataSession::_UpdateSecurityFlagsForPrivacy(v22, 0, v21);
            v24 = v23;
            if ( v23 >= 0 )
            {
              v71 = *((_DWORD *)v22 + 449);
              v72 = *((_DWORD *)v22 + 447);
              if ( (v71 & v21 & v72) != 0 )
                goto LABEL_25;
              if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x80u) != 0 )
                McTemplateU0qqq_EventWriteTransfer(
                  v71,
                  (unsigned int)ClientPrivacyCapabilityFailed,
                  v21,
                  v72,
                  *((_DWORD *)v22 + 449));
              v24 = -2147467260;
LABEL_26:
              if ( v24 < 0 )
                return (unsigned int)v24;
              goto LABEL_27;
            }
            v75 = 1265;
          }
          Log_HREvent(
            (unsigned int)v23,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
            v75);
          goto LABEL_26;
        }
LABEL_52:
        if ( *((_QWORD *)this + 1) )
        {
          v48 = (*(__int64 (__fastcall **)(UnistoreOperationContext *, _QWORD))(*(_QWORD *)this + 72LL))(this, 0);
          if ( v48 )
          {
            v49 = (ServiceDataSession *)*((_QWORD *)this + 1);
            v50 = ServiceDataSession::EnsureIntializedSecurityAndAppInfo(v49);
            v51 = v50;
            if ( v50 < 0 )
            {
              Log_HREvent(
                (unsigned int)v50,
                1,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
                1255);
            }
            else
            {
              v51 = 0;
              if ( (v48 & *((_DWORD *)v49 + 447)) == 0 )
                v51 = -2147024891;
            }
            if ( (v51 & 0x80000000) != 0 )
              return v51;
          }
        }
        v65 = 2;
        goto LABEL_59;
      }
      v79 = 1451;
    }
    Log_HREvent(
      (unsigned int)PropertiesForStore,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      v79);
    goto LABEL_19;
  }
  if ( v10 != -2147023728 )
    Log_HREvent(
      (unsigned int)v10,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\unistorecontext.cpp",
      563);
  return v11;
}

```

## disassembly

```asm
0x180009a90  push    rbp
0x180009a92  push    rsi
0x180009a93  push    rdi
0x180009a94  push    r12
0x180009a96  push    r13
0x180009a98  lea     rbp, [rsp-37h]
0x180009a9d  sub     rsp, 0D0h
0x180009aa4  mov     rax, cs:__security_cookie
0x180009aab  xor     rax, rsp
0x180009aae  mov     [rbp+57h+var_50], rax
0x180009ab2  mov     [rbp+57h+var_88], r9
0x180009ab6  mov     r13, r9
0x180009ab9  mov     [rbp+57h+var_80], r8
0x180009abd  mov     rsi, rdx
0x180009ac0  mov     rdi, rcx
0x180009ac3  mov     r12d, 2
0x180009ac9  test    r8, r8
0x180009acc  jz      short loc_180009AD1
0x180009ace  mov     [r8], r12d
0x180009ad1  test    r9, r9
0x180009ad4  jnz     loc_18000A0B1
0x180009ada  mov     rax, [rcx]
0x180009add  mov     rax, [rax+50h]
0x180009ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ae6  test    eax, eax
0x180009ae8  jz      loc_18000A1E0
0x180009aee  movsd   xmm0, qword ptr [rsi]
0x180009af2  lea     r9, [rbp+57h+var_9C]
0x180009af6  xor     eax, eax
0x180009af8  mov     [rsp+0F0h+var_28], rbx
0x180009b00  mov     [rbp+57h+var_A0], eax
0x180009b03  lea     r8, [rbp+57h+var_A0]
0x180009b07  mov     [rbp+57h+var_9C], eax
0x180009b0a  lea     rdx, [rbp+57h+var_70]
0x180009b0e  mov     eax, [rsi+8]
0x180009b11  mov     rcx, rdi
0x180009b14  mov     [rbp+57h+var_68], eax
0x180009b17  mov     rax, [rdi]
0x180009b1a  movsd   [rbp+57h+var_70], xmm0
0x180009b1f  mov     rax, [rax+40h]
0x180009b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b28  mov     ebx, eax
0x180009b2a  test    eax, eax
0x180009b2c  js      loc_18000A0F6
0x180009b32  mov     [rsp+0F0h+var_30], r14
0x180009b3a  mov     r14, [rdi+8]
0x180009b3e  mov     [rsp+0F0h+var_38], r15
0x180009b46  mov     r15d, 80070005h
0x180009b4c  test    r14, r14
0x180009b4f  jz      loc_180009E24
0x180009b55  cmp     dword ptr [rsi+4], 29h ; ')'
0x180009b59  jz      loc_18000A20E
0x180009b5f  mov     r15d, [rsi]
0x180009b62  mov     rcx, r14; this
0x180009b65  call    ?EnsureIntializedSecurityAndAppInfo@ServiceDataSession@@AEAAJXZ; ServiceDataSession::EnsureIntializedSecurityAndAppInfo(void)
0x180009b6a  mov     ebx, eax
0x180009b6c  test    eax, eax
0x180009b6e  js      loc_18000A369
0x180009b74  xor     eax, eax
0x180009b76  lea     r9, [rbp+57h+Context]; lpContext
0x180009b7a  lea     r8, [rbp+57h+fPending]; fPending
0x180009b7e  mov     qword ptr [rbp+57h+var_B0.dwLowDateTime], rax
0x180009b82  xor     edx, edx; dwFlags
0x180009b84  mov     [rbp+57h+fPending], eax
0x180009b87  lea     rcx, stru_18015EA68; lpInitOnce
0x180009b8e  mov     [rbp+57h+Context], rax
0x180009b92  call    cs:__imp_InitOnceBeginInitialize
0x180009b98  mov     rbx, [rbp+57h+Context]
0x180009b9c  test    rbx, rbx
0x180009b9f  jz      loc_18000A38F
0x180009ba5  lea     r8, [rbp+57h+var_B0]; struct StorePropertySet **
0x180009ba9  mov     edx, r15d; unsigned int
0x180009bac  mov     rcx, rbx; this
0x180009baf  call    ?GetPropertiesForStore@StorePropertyCache@@QEAAJKPEAPEBUStorePropertySet@@@Z; StorePropertyCache::GetPropertiesForStore(ulong,StorePropertySet const * *)
0x180009bb4  mov     ebx, eax
0x180009bb6  test    eax, eax
0x180009bb8  js      loc_18000A371
0x180009bbe  mov     rax, qword ptr [rbp+57h+var_B0.dwLowDateTime]
0x180009bc2  mov     rax, [rax+8]
0x180009bc6  test    rax, rax
0x180009bc9  jz      short loc_180009BFB
0x180009bcb  mov     r8, [r14+710h]
0x180009bd2  sub     r8, rax
0x180009bd5  nop     word ptr [rax+rax+00000000h]
0x180009be0  movzx   edx, word ptr [rax]
0x180009be3  movzx   ecx, word ptr [rax+r8]
0x180009be8  sub     edx, ecx
0x180009bea  jnz     short loc_180009BF3
0x180009bec  add     rax, r12
0x180009bef  test    ecx, ecx
0x180009bf1  jnz     short loc_180009BE0
0x180009bf3  test    edx, edx
0x180009bf5  jz      loc_18000A109
0x180009bfb  mov     r15d, 80070005h
0x180009c01  mov     ebx, r15d
0x180009c04  test    ebx, ebx
0x180009c06  jns     loc_180009E24
0x180009c0c  cmp     qword ptr [rdi+8], 0
0x180009c11  jz      loc_180009CD9
0x180009c17  mov     rax, [rdi]
0x180009c1a  mov     edx, 1
0x180009c1f  mov     rcx, rdi
0x180009c22  mov     rax, [rax+48h]
0x180009c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c2b  mov     ebx, eax
0x180009c2d  test    eax, eax
0x180009c2f  jz      short loc_180009C74
0x180009c31  mov     r15, [rdi+8]
0x180009c35  mov     rcx, r15; this
0x180009c38  call    ?EnsureIntializedSecurityAndAppInfo@ServiceDataSession@@AEAAJXZ; ServiceDataSession::EnsureIntializedSecurityAndAppInfo(void)
0x180009c3d  mov     r14d, eax
0x180009c40  test    eax, eax
0x180009c42  js      loc_18000A28B
0x180009c48  mov     ecx, [r15+6FCh]
0x180009c4f  test    ecx, ebx
0x180009c51  jz      loc_18000A3B4
0x180009c57  mov     eax, [r15+704h]
0x180009c5e  and     eax, ebx
0x180009c60  test    ecx, eax
0x180009c62  jz      loc_18000A12C
0x180009c68  xor     r14d, r14d
0x180009c6b  test    r14d, r14d
0x180009c6e  js      loc_18000A3BF
0x180009c74  cmp     qword ptr [rdi+8], 0
0x180009c79  jz      short loc_180009CD9
0x180009c7b  mov     rax, [rdi]
0x180009c7e  mov     edx, r12d
0x180009c81  mov     rcx, rdi
0x180009c84  mov     rax, [rax+48h]
0x180009c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c8d  mov     ebx, eax
0x180009c8f  test    eax, eax
0x180009c91  jz      short loc_180009CD9
0x180009c93  mov     r14, [rdi+8]
0x180009c97  mov     rcx, r14; this
0x180009c9a  call    ?EnsureIntializedSecurityAndAppInfo@ServiceDataSession@@AEAAJXZ; ServiceDataSession::EnsureIntializedSecurityAndAppInfo(void)
0x180009c9f  mov     r15d, eax
0x180009ca2  test    eax, eax
0x180009ca4  js      loc_18000A293
0x180009caa  mov     ecx, [r14+6FCh]
0x180009cb1  test    ecx, ebx
0x180009cb3  jz      loc_18000A3C7
0x180009cb9  mov     eax, ebx
0x180009cbb  and     eax, ecx
0x180009cbd  test    [r14+704h], eax
0x180009cc4  jz      loc_18000A186
0x180009cca  xor     r15d, r15d
0x180009ccd  mov     dword ptr [rbp+57h+var_B8], 0
0x180009cd4  test    r15d, r15d
0x180009cd7  js      short loc_180009CE0
0x180009cd9  mov     dword ptr [rbp+57h+var_B8], 1
0x180009ce0  mov     ecx, [rsi+4]
0x180009ce3  mov     r14, [rdi+8]
0x180009ce7  call    ?UdmTypeToUnistoreType@@YA?AW4US_OBJECTTYPE@@W4UdmItemType@@@Z; UdmTypeToUnistoreType(UdmItemType)
0x180009cec  mov     r12d, [rsi]
0x180009cef  mov     r15d, eax
0x180009cf2  cmp     eax, 80000h
0x180009cf7  jz      loc_18000A203
0x180009cfd  mov     r15d, 10000h
0x180009d03  mov     [rbp+57h+fPending], r12d
0x180009d07  lea     rbx, [r14+780h]
0x180009d0e  mov     rcx, rbx; lpCriticalSection
0x180009d11  call    cs:__imp_EnterCriticalSection
0x180009d17  lea     r13, [r14+7A8h]
0x180009d1e  mov     rdx, [r13+10h]
0x180009d22  test    rdx, rdx
0x180009d25  jz      loc_180009EF4
0x180009d2b  mov     r9d, [rbp+57h+fPending]
0x180009d2f  lea     rcx, [r12+r12*2]
0x180009d33  mov     eax, r15d
0x180009d36  add     rcx, rax
0x180009d39  mov     eax, 8
0x180009d3e  imul    r8, rcx, 3E7h
0x180009d45  movzx   ecx, byte ptr [r13+20h]
0x180009d4a  shl     rax, cl
0x180009d4d  add     r8, r9
0x180009d50  dec     rax
0x180009d53  and     rax, r8
0x180009d56  add     rax, rax
0x180009d59  mov     r14, [rdx+rax*8]
0x180009d5d  test    r14, r14
0x180009d60  jz      loc_180009EF4
0x180009d66  mov     rax, [rdx+rax*8+8]
0x180009d6b  mov     rcx, [rax]
0x180009d6e  cmp     r14, rcx
0x180009d71  jz      loc_180009EF4
0x180009d77  cmp     [r14+10h], r8
0x180009d7b  jb      loc_18000A015
0x180009d81  ja      loc_180009EF4
0x180009d87  cmp     r12d, [r14+18h]
0x180009d8b  jnz     loc_18000A015
0x180009d91  cmp     r15d, [r14+1Ch]
0x180009d95  jnz     loc_18000A015
0x180009d9b  cmp     r9d, [r14+20h]
0x180009d9f  jnz     loc_18000A015
0x180009da5  cmp     r14, r13
0x180009da8  jz      loc_180009EF4
0x180009dae  lea     rdx, FileTime2; lpFileTime2
0x180009db5  lea     rcx, [r14+30h]; lpFileTime1
0x180009db9  call    cs:__imp_CompareFileTime
0x180009dbf  test    eax, eax
0x180009dc1  jz      short loc_180009DDC
0x180009dc3  lea     rdx, stru_18013B878; lpFileTime2
0x180009dca  lea     rcx, [r14+30h]; lpFileTime1
0x180009dce  call    cs:__imp_CompareFileTime
0x180009dd4  test    eax, eax
0x180009dd6  jnz     loc_18000A025
0x180009ddc  movzx   ecx, byte ptr [r13+20h]
0x180009de1  mov     edx, 8
0x180009de6  mov     rax, [r14]
0x180009de9  shl     rdx, cl
0x180009dec  mov     rcx, [r14+8]
0x180009df0  dec     rdx
0x180009df3  mov     [rcx], rax
0x180009df6  mov     [rax+8], rcx
0x180009dfa  and     rdx, [r14+10h]
0x180009dfe  shl     rdx, 4
0x180009e02  add     rdx, [r13+10h]
0x180009e06  mov     rax, [rdx+8]
0x180009e0a  cmp     [rdx], r14
0x180009e0d  jnz     loc_18000A116
0x180009e13  cmp     rax, r14
0x180009e16  jz      loc_180009ED4
0x180009e1c  mov     rax, [r14]
0x180009e1f  jmp     loc_180009EDE
0x180009e24  cmp     qword ptr [rdi+8], 0
0x180009e29  mov     r14d, 1
0x180009e2f  jz      loc_18000A01D
0x180009e35  mov     rax, [rdi]
0x180009e38  xor     edx, edx
0x180009e3a  mov     rcx, rdi
0x180009e3d  mov     rax, [rax+48h]
0x180009e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e46  mov     esi, eax
0x180009e48  test    eax, eax
0x180009e4a  jz      loc_18000A01D
0x180009e50  mov     rdi, [rdi+8]
0x180009e54  mov     rcx, rdi; this
0x180009e57  call    ?EnsureIntializedSecurityAndAppInfo@ServiceDataSession@@AEAAJXZ; ServiceDataSession::EnsureIntializedSecurityAndAppInfo(void)
0x180009e5c  mov     ebx, eax
0x180009e5e  test    eax, eax
0x180009e60  js      loc_18000A29B
0x180009e66  xor     ebx, ebx
0x180009e68  test    [rdi+6FCh], esi
0x180009e6e  cmovz   ebx, r15d
0x180009e72  test    ebx, ebx
0x180009e74  jns     loc_18000A01D
0x180009e7a  mov     eax, ebx
0x180009e7c  jmp     short loc_180009EA1
0x180009e7e  mov     r12d, ebx
0x180009e81  mov     rax, [rbp+57h+var_80]
0x180009e85  test    rax, rax
0x180009e88  jz      short loc_180009E8C
0x180009e8a  mov     [rax], ebx
0x180009e8c  test    r13, r13
0x180009e8f  jnz     loc_18000A0B9
0x180009e95  xor     eax, eax
0x180009e97  mov     ecx, 80070005h
0x180009e9c  test    ebx, ebx
0x180009e9e  cmovz   eax, ecx
0x180009ea1  mov     r14, [rsp+0F0h+var_30]
0x180009ea9  mov     r15, [rsp+0F0h+var_38]
0x180009eb1  mov     rbx, [rsp+0F0h+var_28]
0x180009eb9  mov     rcx, [rbp+57h+var_50]
0x180009ebd  xor     rcx, rsp; StackCookie
0x180009ec0  call    __security_check_cookie
0x180009ec5  add     rsp, 0D0h
0x180009ecc  pop     r13
0x180009ece  pop     r12
0x180009ed0  pop     rdi
0x180009ed1  pop     rsi
0x180009ed2  pop     rbp
0x180009ed3  retn
0x180009ed4  mov     qword ptr [rdx+8], 0
0x180009edc  xor     eax, eax
0x180009ede  mov     [rdx], rax
0x180009ee1  dec     qword ptr [r13+18h]
0x180009ee5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180009eec  mov     rcx, r14; Block
0x180009eef  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009ef4  mov     rcx, rbx; lpCriticalSection
0x180009ef7  call    cs:__imp_LeaveCriticalSection
0x180009efd  xor     r13d, r13d
0x180009f00  lea     r8, [rbp+57h+Context]; unsigned __int16 **
0x180009f04  mov     rdx, rsi; struct UdmObjectId *
0x180009f07  mov     [rbp+57h+Context], r13
0x180009f0b  mov     rcx, rdi; this
0x180009f0e  call    ?GetEnterpriseIdentity@UnistoreOperationContext@@QEAAJAEBUUdmObjectId@@PEAPEAG@Z; UnistoreOperationContext::GetEnterpriseIdentity(UdmObjectId const &,ushort * *)
0x180009f13  mov     ebx, eax
0x180009f15  test    eax, eax
0x180009f17  js      loc_18000A25C
0x180009f1d  mov     r14, [rbp+57h+Context]
0x180009f21  mov     ecx, [rsi+4]
0x180009f24  mov     r15, [rdi+8]
0x180009f28  mov     qword ptr [rbp+57h+var_B0.dwLowDateTime], r14
0x180009f2c  call    ?UdmTypeToUnistoreType@@YA?AW4US_OBJECTTYPE@@W4UdmItemType@@@Z; UdmTypeToUnistoreType(UdmItemType)
0x180009f31  mov     edx, [rsi]
0x180009f33  mov     ecx, [rsi+8]
0x180009f36  mov     dword ptr [rbp+57h+var_70], edx
0x180009f39  mov     [rbp+57h+var_68], ecx
  ... truncated ...
```
