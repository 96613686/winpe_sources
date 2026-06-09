# CWbemNamespace::InitializeSD(IWmiDbSession *)

- ea: `0x180021520`
- end: `0x1800220bf`
- name: `?InitializeSD@CWbemNamespace@@QEAAJPEAUIWmiDbSession@@@Z`
- size: `2975`
- prototype: `__int64 __fastcall(CWbemNamespace *__hidden this, struct IWmiDbSession *)`
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001f6d0`
- `0x1800231e8`
- `0x18002ab80`
- `0x1800827d0`

## callees

- `0x18000b140`
- `0x18000b1dc`
- `0x18000e87c`
- `0x18000e950`
- `0x180021520`
- `0x1800220d0`
- `0x18002c9f0`
- `0x18002cabc`
- `0x18003cfe0`
- `0x180060ba4`
- `0x180060bd4`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800215ce`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002195c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180021a01`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180021b78`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180021f39`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800220a8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800215ce`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002195c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180021a01`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180021b78`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180021f39`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800220a8`
- `wbemcomn!?IsValid@CNtSid@@QEAAHXZ` at `0x1800217e4`
- `wbemcomn!?IsValid@CNtSid@@QEAAHXZ` at `0x1800217e4`
- `wbemcomn!?GetSid@CNtAce@@QEAAPEAVCNtSid@@XZ` at `0x1800217cb`
- `wbemcomn!?GetSid@CNtAce@@QEAAPEAVCNtSid@@XZ` at `0x1800217cb`
- `wbemcomn!?ContainsSid@CNtAcl@@QEAAHAEAVCNtSid@@AEAE@Z` at `0x180021800`
- `wbemcomn!?ContainsSid@CNtAcl@@QEAAHAEAVCNtSid@@AEAE@Z` at `0x180021800`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x18002183d`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x1800219b4`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x180021b2b`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x18002183d`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x1800219b4`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x180021b2b`
- `wbemcomn!?AddAce@CNtAcl@@QEAAHPEAVCNtAce@@@Z` at `0x180021ef8`
- `wbemcomn!?AddAce@CNtAcl@@QEAAHPEAVCNtAce@@@Z` at `0x180021ef8`
- `wbemcomn!?GetDacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ` at `0x1800217ae`
- `wbemcomn!?GetDacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ` at `0x1800217ae`
- `wbemcomn!?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x180021818`
- `wbemcomn!?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x180021818`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002182a`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x1800219a1`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x180021b18`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18002182a`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x1800219a1`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x180021b18`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021833`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021846`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800219aa`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800219bd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021b21`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021b34`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021833`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021846`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800219aa`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800219bd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021b21`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180021b34`
- `wbemcomn!GetMemLogObject` at `0x180021a56`
- `wbemcomn!GetMemLogObject` at `0x180021aa9`
- `wbemcomn!GetMemLogObject` at `0x180021bd8`
- `wbemcomn!GetMemLogObject` at `0x180021d58`
- `wbemcomn!GetMemLogObject` at `0x180021e05`
- `wbemcomn!GetMemLogObject` at `0x180021e28`
- `wbemcomn!GetMemLogObject` at `0x180021ed8`
- `wbemcomn!GetMemLogObject` at `0x180021f53`
- `wbemcomn!GetMemLogObject` at `0x180021fb0`
- `wbemcomn!GetMemLogObject` at `0x18002201c`
- `wbemcomn!GetMemLogObject` at `0x180022051`
- `wbemcomn!GetMemLogObject` at `0x180021a56`
- `wbemcomn!GetMemLogObject` at `0x180021aa9`
- `wbemcomn!GetMemLogObject` at `0x180021bd8`
- `wbemcomn!GetMemLogObject` at `0x180021d58`
- `wbemcomn!GetMemLogObject` at `0x180021e05`
- `wbemcomn!GetMemLogObject` at `0x180021e28`
- `wbemcomn!GetMemLogObject` at `0x180021ed8`
- `wbemcomn!GetMemLogObject` at `0x180021f53`
- `wbemcomn!GetMemLogObject` at `0x180021fb0`
- `wbemcomn!GetMemLogObject` at `0x18002201c`
- `wbemcomn!GetMemLogObject` at `0x180022051`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021a62`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021ab4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021be3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021d66`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021e10`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021e36`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021ee3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021f5f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021fc2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022028`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002205c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021a62`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021ab4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021be3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021d66`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021e10`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021e36`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021ee3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021f5f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180021fc2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180022028`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002205c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180021bc8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180021bc8`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18002157c`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18002157c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180021ca8`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002203f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180021ca8`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002203f`
- `OLEAUT32!__imp_VariantInit` at `0x18002187d`
- `OLEAUT32!__imp_VariantInit` at `0x18002187d`
- `OLEAUT32!__imp_VariantClear` at `0x1800218cd`
- `OLEAUT32!__imp_VariantClear` at `0x180021afa`
- `OLEAUT32!__imp_VariantClear` at `0x1800218cd`
- `OLEAUT32!__imp_VariantClear` at `0x180021afa`

## string_xrefs

- `0x1800216b9`: `__SystemSecurity=@`
- `0x180021725`: `__SystemSecurity=@`
- `0x180021e80`: `__SystemSecurity=@`
- `0x18002179b`: `SECURITY_DESCRIPTOR`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CWbemNamespace::InitializeSD(CWbemNamespace *this, struct IWmiDbSession *a2)
{
  struct IWmiDbSession *v2; // r14
  HRESULT v4; // eax
  int v5; // r15d
  int v6; // ebx
  __int64 v7; // rdi
  void *v8; // rbx
  int v9; // esi
  struct IWbemClassObject *v10; // rdi
  __int64 v11; // rsi
  void *v12; // rbx
  __int64 v13; // rbx
  CNtAcl *Dacl; // rax
  CNtAcl *v15; // r15
  CNtSid *Sid; // rax
  struct CNtSid *v17; // rsi
  int v18; // r15d
  CNtSid *v19; // rsi
  int v20; // eax
  HRESULT v21; // eax
  struct IErrorInfo *v22; // rdx
  CClientCnt *v23; // rcx
  int DefaultSession; // ebx
  CMemoryLog *v26; // rax
  CMemoryLog *MemLogObject; // rax
  HRESULT v28; // eax
  struct IErrorInfo *v29; // rdx
  HRESULT v30; // ebx
  CMemoryLog *v31; // rax
  CNtSid *NewPath; // rax
  CNtSid *v33; // rbx
  CMemoryLog *v34; // rax
  CMemoryLog *v35; // rax
  CNtSid *v36; // rax
  CNtSid *v37; // rbx
  CMemoryLog *v38; // rax
  CMemoryLog *v39; // rax
  CMemoryLog *v40; // rax
  CMemoryLog *v41; // rax
  CMemoryLog *v42; // rax
  CMemoryLog *v43; // rax
  CNtSid *v44; // [rsp+40h] [rbp-29h] BYREF
  struct IWbemClassObject *v45; // [rsp+48h] [rbp-21h] BYREF
  struct IWbemClassObject *v46; // [rsp+50h] [rbp-19h] BYREF
  __int64 v47; // [rsp+58h] [rbp-11h] BYREF
  __int64 v48; // [rsp+60h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-1h] BYREF
  CNtAcl *v50[8]; // [rsp+80h] [rbp+17h] BYREF
  void *ppInterface; // [rsp+D8h] [rbp+6Fh] BYREF
  int v52; // [rsp+E0h] [rbp+77h]
  struct IWmiDbSession *v53; // [rsp+E8h] [rbp+7Fh] BYREF

  ppInterface = a2;
  v2 = a2;
  if ( a2 )
  {
    (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  else
  {
    DefaultSession = CRepository::GetDefaultSession((struct IWmiDbSession **)&ppInterface);
    if ( DefaultSession < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, DefaultSession);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          158,
          WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
          (unsigned int)DefaultSession);
      }
      return (unsigned int)DefaultSession;
    }
    v2 = (struct IWmiDbSession *)ppInterface;
  }
  v53 = v2;
  v46 = 0;
  v47 = 0;
  ppInterface = 0;
  v4 = CoGetCallContext(&IID_IServerSecurity, &ppInterface);
  v5 = 0;
  v52 = 0;
  if ( !v4 )
  {
    v6 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface);
    LOBYTE(v5) = v6 == 1;
    v52 = v5;
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
    if ( v6 == 1 )
    {
      v30 = CoRevertToSelf();
      if ( v30 < 0 )
      {
        v31 = GetMemLogObject();
        CMemoryLog::Write(v31, v30);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            159,
            WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
            (unsigned int)v30);
        }
        if ( v2 )
          (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)v2 + 16LL))(v2);
        v53 = 0;
        return (unsigned int)v30;
      }
    }
  }
  v50[1] = 0;
  TlsSetValue(g_SecFlagTlsIndex, 0);
  v7 = *((_QWORD *)this + 7);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      46,
      (unsigned int)WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
      (_DWORD)v2,
      v7,
      (__int64)L"__thisnamespace=@");
  }
  ppInterface = 0;
  if ( (**(int (__fastcall ***)(struct IWmiDbSession *, GUID *, void **))v2)(v2, &IID_IWmiDbSessionEx, &ppInterface) >= 0 )
  {
    v8 = ppInterface;
    v44 = (CNtSid *)ppInterface;
    v9 = (*(__int64 (__fastcall **)(void *, __int64, const unsigned __int16 *, __int64, GUID *, struct IWbemClassObject **))(*(_QWORD *)ppInterface + 96LL))(
           ppInterface,
           v7,
           L"__thisnamespace=@",
           262160,
           &IID_IWbemClassObject,
           &v46);
    if ( v8 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
    v44 = 0;
    goto LABEL_11;
  }
  NewPath = (CNtSid *)ConfigMgr::GetNewPath();
  v33 = NewPath;
  if ( NewPath )
  {
    v44 = NewPath;
    (*(void (__fastcall **)(CNtSid *, __int64, const unsigned __int16 *))(*(_QWORD *)NewPath + 24LL))(
      NewPath,
      4,
      L"__thisnamespace=@");
    v9 = (*(__int64 (__fastcall **)(struct IWmiDbSession *, __int64, CNtSid *, __int64, GUID *, struct IWbemClassObject **))(*(_QWORD *)v2 + 32LL))(
           v2,
           v7,
           v33,
           262160,
           &IID_IWbemClassObject,
           &v46);
    CReleaseMe::release((CReleaseMe *)&v44);
LABEL_11:
    if ( v9 == -2147217406 )
    {
      v9 = -2147217406;
    }
    else
    {
      if ( v9 < 0 )
      {
        v35 = GetMemLogObject();
        CMemoryLog::Write(v35, v9);
      }
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
          (unsigned int)v9);
      }
    }
    goto LABEL_16;
  }
  v34 = GetMemLogObject();
  CMemoryLog::Write(v34, -2147217402);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, 2147749894LL);
  }
  v9 = -2147217402;
LABEL_16:
  v10 = v46;
  v45 = v46;
  if ( v9 < 0 )
    goto LABEL_135;
  v11 = *((_QWORD *)this + 7);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      46,
      (unsigned int)WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
      (_DWORD)v2,
      v11,
      (__int64)L"__SystemSecurity=@");
  }
  ppInterface = 0;
  if ( (**(int (__fastcall ***)(struct IWmiDbSession *, GUID *, void **))v2)(v2, &IID_IWmiDbSessionEx, &ppInterface) >= 0 )
  {
    v12 = ppInterface;
    v44 = (CNtSid *)ppInterface;
    v9 = (*(__int64 (__fastcall **)(void *, __int64, const wchar_t *, __int64, GUID *, __int64 *))(*(_QWORD *)ppInterface
                                                                                                 + 96LL))(
           ppInterface,
           v11,
           L"__SystemSecurity=@",
           16,
           &IID_IWbemClassObject,
           &v47);
    if ( v12 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
    v44 = 0;
    goto LABEL_23;
  }
  v36 = (CNtSid *)ConfigMgr::GetNewPath();
  v37 = v36;
  if ( v36 )
  {
    v44 = v36;
    (*(void (__fastcall **)(CNtSid *, __int64, const wchar_t *))(*(_QWORD *)v36 + 24LL))(v36, 4, L"__SystemSecurity=@");
    v9 = (*(__int64 (__fastcall **)(struct IWmiDbSession *, __int64, CNtSid *, __int64, GUID *, __int64 *))(*(_QWORD *)v2 + 32LL))(
           v2,
           v11,
           v37,
           16,
           &IID_IWbemClassObject,
           &v47);
    CReleaseMe::release((CReleaseMe *)&v44);
LABEL_23:
    if ( v9 == -2147217406 )
    {
      v9 = -2147217406;
    }
    else
    {
      if ( v9 < 0 )
      {
        v39 = GetMemLogObject();
        CMemoryLog::Write(v39, v9);
      }
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids,
          (unsigned int)v9);
      }
    }
    goto LABEL_28;
  }
  v38 = GetMemLogObject();
  CMemoryLog::Write(v38, -2147217402);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_3195b2018fcf36e0cdc4b4f2f02aaf3d_Traceguids, 2147749894LL);
  }
  v9 = -2147217402;
LABEL_28:
  if ( v9 < 0 )
  {
LABEL_135:
    if ( v5 && CoImpersonateClient() < 0 )
      v9 = -2147217407;
    v43 = GetMemLogObject();
    CMemoryLog::Write(v43, v9);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        160,
        WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
        (unsigned int)v9);
    }
    CReleaseMe::release((CReleaseMe *)&v45);
    TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
    CReleaseMe::release((CReleaseMe *)&v53);
    return (unsigned int)v9;
  }
  v13 = v47;
  v48 = v47;
  GetSDFromProperty(L"SECURITY_DESCRIPTOR", (CWbemNamespace *)((char *)this + 216), v46);
  Dacl = CNtSecurityDescriptor::GetDacl((CWbemNamespace *)((char *)this + 216));
  v15 = Dacl;
  if ( !Dacl )
    goto LABEL_35;
  v50[0] = Dacl;
  Sid = CNtAce::GetSid(*((CNtAce **)this + 29));
  v17 = Sid;
  v44 = Sid;
  if ( Sid && CNtSid::IsValid(Sid) )
  {
    LOBYTE(ppInterface) = 0;
    if ( !CNtAcl::ContainsSid(v15, v17, (unsigned __int8 *)&ppInterface)
      && !CNtAcl::AddAce(v15, *((struct CNtAce **)this + 29)) )
    {
      CDeleteMe<CNtSid>::~CDeleteMe<CNtSid>(&v44);
      CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(v50);
      CReleaseMe::release((CReleaseMe *)&v48);
      CReleaseMe::release((CReleaseMe *)&v45);
      TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
      CReleaseMe::release((CReleaseMe *)&v53);
      return 2147749889LL;
    }
    if ( CNtSecurityDescriptor::SetDacl((CWbemNamespace *)((char *)this + 216), v15) )
    {
      CNtSid::~CNtSid(v17);
      CWin32DefaultArena::WbemMemFree(v17);
      CNtAcl::~CNtAcl(v15);
      CWin32DefaultArena::WbemMemFree(v15);
LABEL_35:
      v44 = 0;
      v18 = (*(__int64 (__fastcall **)(__int64, CNtSid **))(*(_QWORD *)v47 + 24LL))(v47, &v44);
      if ( v18 < 0 )
      {
        v26 = GetMemLogObject();
        CMemoryLog::Write(v26, v18);
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_43:
          if ( v52 )
          {
            if ( CoImpersonateClient() < 0 )
            {
              v18 = -2147217407;
LABEL_134:
              v42 = GetMemLogObject();
              CMemoryLog::Write(v42, v18);
              v23 = WPP_GLOBAL_Control;
LABEL_45:
              if ( v23 != (CClientCnt *)&WPP_GLOBAL_Control
                && (*((_BYTE *)v23 + 28) & 1) != 0
                && *((_BYTE *)v23 + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)v23 + 2), 161, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, (unsigned int)v18);
              }
              if ( v13 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
              v48 = 0;
              if ( v10 )
                ((void (__fastcall *)(struct IWbemClassObject *))v10->lpVtbl->Release)(v10);
              v45 = 0;
              TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
              if ( v2 )
                (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)v2 + 16LL))(v2);
              v53 = 0;
              return (unsigned int)v18;
            }
            v23 = WPP_GLOBAL_Control;
          }
          if ( v18 >= 0 )
            goto LABEL_45;
          goto LABEL_134;
        }
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
          (unsigned int)v18);
      }
      else
      {
        v19 = v44;
        ppInterface = v44;
        VariantInit(&pvarg);
        v20 = (*(__int64 (__fastcall **)(CNtSid *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD))(*(_QWORD *)v44 + 24LL))(
                v44,
                L"RequiresEncryption",
                0,
                &pvarg,
                0);
        v18 = v20;
        if ( v20 >= 0 )
        {
          if ( pvarg.vt == 11 )
          {
            *((_BYTE *)this + 328) = pvarg.iVal == 0xFFFF;
            v28 = VariantClear(&pvarg);
            if ( v28 < 0 )
              _com_raise_error(v28, v29);
            goto LABEL_39;
          }
          v41 = GetMemLogObject();
          v18 = -2147217403;
          CMemoryLog::Write(v41, -2147217403);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              53,
              WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
              2147749893LL);
          }
        }
        else
        {
          if ( v20 == -2147217406 )
          {
            *((_BYTE *)this + 328) = 0;
            v21 = VariantClear(&pvarg);
            if ( v21 < 0 )
              _com_raise_error(v21, v22);
LABEL_39:
            if ( v19 )
              (*(void (__fastcall **)(CNtSid *))(*(_QWORD *)v19 + 16LL))(v19);
            v18 = 0;
            ppInterface = 0;
            goto LABEL_42;
          }
          v40 = GetMemLogObject();
          CMemoryLog::Write(v40, v18);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              52,
              WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
              (unsigned int)v18);
          }
        }
        _variant_t::~_variant_t(&pvarg);
        CReleaseMe::release((CReleaseMe *)&ppInterface);
      }
LABEL_42:
      v23 = WPP_GLOBAL_Control;
      goto LABEL_43;
    }
    CNtSid::~CNtSid(v17);
    CWin32DefaultArena::WbemMemFree(v17);
    CNtAcl::~CNtAcl(v15);
    CWin32DefaultArena::WbemMemFree(v15);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v48 = 0;
    if ( v10 )
      ((void (__fastcall *)(struct IWbemClassObject *))v10->lpVtbl->Release)(v10);
    v45 = 0;
    TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
    if ( v2 )
      (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)v2 + 16LL))(v2);
    v53 = 0;
    return 2147749889LL;
  }
  else
  {
    if ( v17 )
    {
      CNtSid::~CNtSid(v17);
      CWin32DefaultArena::WbemMemFree(v17);
    }
    CNtAcl::~CNtAcl(v15);
    CWin32DefaultArena::WbemMemFree(v15);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v48 = 0;
    if ( v10 )
      ((void (__fastcall *)(struct IWbemClassObject *))v10->lpVtbl->Release)(v10);
    v45 = 0;
    TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
    if ( v2 )
      (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)v2 + 16LL))(v2);
    v53 = 0;
    return 2147749894LL;
  }
}

```

## disassembly

```asm
0x180021520  mov     [rsp-8+arg_0], rbx
0x180021525  mov     [rsp-8+ppInterface], rdx
0x18002152a  push    rbp
0x18002152b  push    rsi
0x18002152c  push    rdi
0x18002152d  push    r12
0x18002152f  push    r13
0x180021531  push    r14
0x180021533  push    r15
0x180021535  lea     rbp, [rsp-27h]
0x18002153a  sub     rsp, 90h
0x180021541  mov     r14, rdx
0x180021544  mov     r13, rcx
0x180021547  test    rdx, rdx
0x18002154a  jz      loc_180021A2A
0x180021550  mov     rax, [rdx]
0x180021553  mov     rcx, rdx
0x180021556  mov     rax, [rax+8]
0x18002155a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002155f  mov     [rbp+57h+arg_18], r14
0x180021563  xor     esi, esi
0x180021565  mov     [rbp+57h+var_70], rsi
0x180021569  mov     [rbp+57h+var_68], rsi
0x18002156d  mov     [rbp+57h+ppInterface], rsi
0x180021571  lea     rdx, [rbp+57h+ppInterface]; ppInterface
0x180021575  lea     rcx, IID_IServerSecurity; riid
0x18002157c  call    cs:__imp_CoGetCallContext
0x180021582  mov     r15d, esi
0x180021585  mov     [rbp+57h+arg_10], esi
0x180021588  test    eax, eax
0x18002158a  jnz     short loc_1800215C2
0x18002158c  mov     rcx, [rbp+57h+ppInterface]
0x180021590  mov     rax, [rcx]
0x180021593  mov     rax, [rax+30h]
0x180021597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002159c  mov     ebx, eax
0x18002159e  cmp     eax, 1
0x1800215a1  setz    r15b
0x1800215a5  mov     [rbp+57h+arg_10], r15d
0x1800215a9  mov     rcx, [rbp+57h+ppInterface]
0x1800215ad  mov     rdx, [rcx]
0x1800215b0  mov     rax, [rdx+10h]
0x1800215b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215b9  cmp     ebx, 1
0x1800215bc  jz      loc_180021BC8
0x1800215c2  mov     [rbp+57h+var_38], rsi
0x1800215c6  xor     edx, edx; lpTlsValue
0x1800215c8  mov     ecx, cs:?g_SecFlagTlsIndex@@3VCTLS@@A; dwTlsIndex
0x1800215ce  call    cs:__imp_TlsSetValue
0x1800215d4  nop
0x1800215d5  mov     rdi, [r13+38h]
0x1800215d9  lea     r12, WPP_GLOBAL_Control
0x1800215e0  lea     rax, aThisnamespace_0; "__thisnamespace=@"
0x1800215e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215ee  cmp     rcx, r12
0x1800215f1  jz      short loc_1800215FD
0x1800215f3  test    byte ptr [rcx+1Ch], 1
0x1800215f7  jnz     loc_180021C1F
0x1800215fd  mov     [rbp+57h+ppInterface], rsi
0x180021601  mov     rax, [r14]
0x180021604  lea     r8, [rbp+57h+ppInterface]
0x180021608  lea     rdx, IID_IWmiDbSessionEx
0x18002160f  mov     rcx, r14
0x180021612  mov     rax, [rax]
0x180021615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002161a  lea     rsi, IID_IWbemClassObject
0x180021621  test    eax, eax
0x180021623  js      loc_180021D4B
0x180021629  mov     rbx, [rbp+57h+ppInterface]
0x18002162d  mov     [rbp+57h+var_80], rbx
0x180021631  mov     rcx, [rbp+57h+ppInterface]
0x180021635  mov     rax, [rcx]
0x180021638  lea     rdx, [rbp+57h+var_70]
0x18002163c  mov     [rsp+0C0h+var_98], rdx
0x180021641  mov     [rsp+0C0h+var_A0], rsi
0x180021646  mov     r9d, 40010h
0x18002164c  lea     r8, aThisnamespace_0; "__thisnamespace=@"
0x180021653  mov     rdx, rdi
0x180021656  mov     rax, [rax+60h]
0x18002165a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002165f  mov     esi, eax
0x180021661  test    rbx, rbx
0x180021664  jz      short loc_180021675
0x180021666  mov     rax, [rbx]
0x180021669  mov     rcx, rbx
0x18002166c  mov     rax, [rax+10h]
0x180021670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021675  xor     ebx, ebx
0x180021677  mov     [rbp+57h+var_80], rbx
0x18002167b  cmp     esi, 80041002h
0x180021681  jz      loc_180021A42
0x180021687  test    esi, esi
0x180021689  js      loc_180021E05
0x18002168f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021696  cmp     rcx, r12
0x180021699  jz      short loc_1800216A5
0x18002169b  test    byte ptr [rcx+1Ch], 1
0x18002169f  jnz     loc_180021C81
0x1800216a5  mov     rdi, [rbp+57h+var_70]
0x1800216a9  mov     [rbp+57h+var_78], rdi
0x1800216ad  test    esi, esi
0x1800216af  js      loc_18002203A
0x1800216b5  mov     rsi, [r13+38h]
0x1800216b9  lea     rax, aSystemsecurity_1; "__SystemSecurity=@"
0x1800216c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216c7  cmp     rcx, r12
0x1800216ca  jz      short loc_1800216D6
0x1800216cc  test    byte ptr [rcx+1Ch], 1
0x1800216d0  jnz     loc_180021C50
0x1800216d6  mov     [rbp+57h+ppInterface], rbx
0x1800216da  mov     rax, [r14]
0x1800216dd  lea     r8, [rbp+57h+ppInterface]
0x1800216e1  lea     rdx, IID_IWmiDbSessionEx
0x1800216e8  mov     rcx, r14
0x1800216eb  mov     rax, [rax]
0x1800216ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216f3  test    eax, eax
0x1800216f5  js      loc_180021E1B
0x1800216fb  mov     rbx, [rbp+57h+ppInterface]
0x1800216ff  mov     [rbp+57h+var_80], rbx
0x180021703  mov     rcx, [rbp+57h+ppInterface]
0x180021707  mov     rax, [rcx]
0x18002170a  lea     rdx, [rbp+57h+var_68]
0x18002170e  mov     [rsp+0C0h+var_98], rdx
0x180021713  lea     rdx, IID_IWbemClassObject
0x18002171a  mov     [rsp+0C0h+var_A0], rdx
0x18002171f  mov     r9d, 10h
0x180021725  lea     r8, aSystemsecurity_1; "__SystemSecurity=@"
0x18002172c  mov     rdx, rsi
0x18002172f  mov     rax, [rax+60h]
0x180021733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021738  mov     esi, eax
0x18002173a  test    rbx, rbx
0x18002173d  jz      short loc_18002174E
0x18002173f  mov     rax, [rbx]
0x180021742  mov     rcx, rbx
0x180021745  mov     rax, [rax+10h]
0x180021749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002174e  mov     [rbp+57h+var_80], 0
0x180021756  cmp     esi, 80041002h
0x18002175c  jz      loc_180021A4C
0x180021762  test    esi, esi
0x180021764  js      loc_180021ED8
0x18002176a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021771  cmp     rcx, r12
0x180021774  jz      short loc_180021780
0x180021776  test    byte ptr [rcx+1Ch], 1
0x18002177a  jnz     loc_180021CC2
0x180021780  test    esi, esi
0x180021782  js      loc_18002203A
0x180021788  mov     rbx, [rbp+57h+var_68]
0x18002178c  mov     [rbp+57h+var_60], rbx
0x180021790  mov     r8, [rbp+57h+var_70]; struct IWbemClassObject *
0x180021794  lea     rdx, [r13+0D8h]; struct CNtSecurityDescriptor *
0x18002179b  lea     rcx, aSecurityDescri; "SECURITY_DESCRIPTOR"
0x1800217a2  call    ?GetSDFromProperty@@YAJPEAGPEAVCNtSecurityDescriptor@@PEAUIWbemClassObject@@@Z; GetSDFromProperty(ushort *,CNtSecurityDescriptor *,IWbemClassObject *)
0x1800217a7  lea     rcx, [r13+0D8h]
0x1800217ae  call    cs:__imp_?GetDacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ; CNtSecurityDescriptor::GetDacl(void)
0x1800217b4  mov     r15, rax
0x1800217b7  test    rax, rax
0x1800217ba  jz      loc_18002184C
0x1800217c0  mov     [rbp+57h+var_40], rax
0x1800217c4  mov     rcx, [r13+0E8h]
0x1800217cb  call    cs:__imp_?GetSid@CNtAce@@QEAAPEAVCNtSid@@XZ; CNtAce::GetSid(void)
0x1800217d1  mov     rsi, rax
0x1800217d4  mov     [rbp+57h+var_80], rax
0x1800217d8  test    rax, rax
0x1800217db  jz      loc_180021B10
0x1800217e1  mov     rcx, rax
0x1800217e4  call    cs:__imp_?IsValid@CNtSid@@QEAAHXZ; CNtSid::IsValid(void)
0x1800217ea  test    eax, eax
0x1800217ec  jz      loc_180021B10
0x1800217f2  mov     byte ptr [rbp+57h+ppInterface], 0
0x1800217f6  lea     r8, [rbp+57h+ppInterface]
0x1800217fa  mov     rdx, rsi
0x1800217fd  mov     rcx, r15
0x180021800  call    cs:__imp_?ContainsSid@CNtAcl@@QEAAHAEAVCNtSid@@AEAE@Z; CNtAcl::ContainsSid(CNtSid &,uchar &)
0x180021806  test    eax, eax
0x180021808  jz      loc_180021EEE
0x18002180e  mov     rdx, r15
0x180021811  lea     rcx, [r13+0D8h]
0x180021818  call    cs:__imp_?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z; CNtSecurityDescriptor::SetDacl(CNtAcl *)
0x18002181e  nop
0x18002181f  mov     rcx, rsi
0x180021822  test    eax, eax
0x180021824  jz      loc_1800219A1
0x18002182a  call    cs:__imp_??1CNtSid@@QEAA@XZ; CNtSid::~CNtSid(void)
0x180021830  mov     rcx, rsi
0x180021833  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180021839  nop
0x18002183a  mov     rcx, r15
0x18002183d  call    cs:__imp_??1CNtAcl@@QEAA@XZ; CNtAcl::~CNtAcl(void)
0x180021843  mov     rcx, r15
0x180021846  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002184c  mov     rcx, [rbp+57h+var_68]
0x180021850  xor     esi, esi
0x180021852  mov     [rbp+57h+var_80], rsi
0x180021856  mov     rax, [rcx]
0x180021859  lea     rdx, [rbp+57h+var_80]
0x18002185d  mov     rax, [rax+18h]
0x180021861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021866  mov     r15d, eax
0x180021869  test    eax, eax
0x18002186b  js      loc_180021A56
0x180021871  mov     rsi, [rbp+57h+var_80]
0x180021875  mov     [rbp+57h+ppInterface], rsi
0x180021879  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002187d  call    cs:__imp_VariantInit
0x180021883  nop
0x180021884  mov     rcx, [rbp+57h+var_80]
0x180021888  mov     rax, [rcx]
0x18002188b  mov     [rsp+0C0h+var_A0], 0
0x180021894  lea     r9, [rbp+57h+pvarg]
0x180021898  xor     r8d, r8d
0x18002189b  lea     rdx, aRequiresencryp; "RequiresEncryption"
0x1800218a2  mov     rax, [rax+18h]
0x1800218a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218ab  mov     r15d, eax
0x1800218ae  test    eax, eax
0x1800218b0  jns     loc_180021AD8
0x1800218b6  cmp     eax, 80041002h
0x1800218bb  jnz     loc_180021F53
0x1800218c1  mov     byte ptr [r13+148h], 0
0x1800218c9  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800218cd  call    cs:__imp_VariantClear
0x1800218d3  test    eax, eax
0x1800218d5  js      loc_180021999
0x1800218db  test    rsi, rsi
0x1800218de  jz      short loc_1800218EF
0x1800218e0  mov     rax, [rsi]
0x1800218e3  mov     rcx, rsi
0x1800218e6  mov     rax, [rax+10h]
0x1800218ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218ef  xor     esi, esi
0x1800218f1  mov     r15d, esi
0x1800218f4  mov     [rbp+57h+ppInterface], rsi
0x1800218f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800218ff  cmp     [rbp+57h+arg_10], 0
0x180021903  jnz     loc_180021CA8
0x180021909  test    r15d, r15d
0x18002190c  js      loc_18002201C
0x180021912  cmp     rcx, r12
0x180021915  jz      short loc_180021921
0x180021917  test    byte ptr [rcx+1Ch], 1
0x18002191b  jnz     loc_180021BA1
0x180021921  test    rbx, rbx
0x180021924  jz      short loc_180021935
0x180021926  mov     rax, [rbx]
0x180021929  mov     rcx, rbx
0x18002192c  mov     rax, [rax+10h]
0x180021930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021935  mov     [rbp+57h+var_60], rsi
0x180021939  test    rdi, rdi
0x18002193c  jz      short loc_18002194D
0x18002193e  mov     rax, [rdi]
0x180021941  mov     rcx, rdi
0x180021944  mov     rax, [rax+10h]
0x180021948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002194d  mov     [rbp+57h+var_78], rsi
0x180021951  mov     edx, 1; lpTlsValue
0x180021956  mov     ecx, cs:?g_SecFlagTlsIndex@@3VCTLS@@A; dwTlsIndex
0x18002195c  call    cs:__imp_TlsSetValue
0x180021962  nop
0x180021963  test    r14, r14
0x180021966  jz      short loc_180021977
0x180021968  mov     rcx, [r14]
0x18002196b  mov     rax, [rcx+10h]
0x18002196f  mov     rcx, r14
0x180021972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021977  mov     [rbp+57h+arg_18], rsi
0x18002197b  mov     eax, r15d
0x18002197e  mov     rbx, [rsp+0C0h+arg_0]
0x180021986  add     rsp, 90h
0x18002198d  pop     r15
0x18002198f  pop     r14
0x180021991  pop     r13
0x180021993  pop     r12
0x180021995  pop     rdi
0x180021996  pop     rsi
0x180021997  pop     rbp
0x180021998  retn
0x180021999  mov     ecx, eax; int
0x18002199b  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800219a1  call    cs:__imp_??1CNtSid@@QEAA@XZ; CNtSid::~CNtSid(void)
0x1800219a7  mov     rcx, rsi
0x1800219aa  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800219b0  nop
0x1800219b1  mov     rcx, r15
0x1800219b4  call    cs:__imp_??1CNtAcl@@QEAA@XZ; CNtAcl::~CNtAcl(void)
0x1800219ba  mov     rcx, r15
0x1800219bd  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800219c3  nop
0x1800219c4  test    rbx, rbx
0x1800219c7  jz      short loc_1800219D8
0x1800219c9  mov     rax, [rbx]
0x1800219cc  mov     rcx, rbx
0x1800219cf  mov     rax, [rax+10h]
0x1800219d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219d8  xor     ebx, ebx
0x1800219da  mov     [rbp+57h+var_60], rbx
  ... truncated ...
```
