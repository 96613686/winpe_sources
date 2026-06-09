# CServerTableEntry::RegisterServer(CProcess *,_GUID,CClassData *,CAppidData *,uchar,ulong,ulong *)

- ea: `0x180043e48`
- end: `0x180044639`
- name: `?RegisterServer@CServerTableEntry@@QEAAJPEAVCProcess@@U_GUID@@PEAVCClassData@@PEAVCAppidData@@EKPEAK@Z`
- size: `2033`
- prototype: `__int64 __usercall@<rax>(CServerTableEntry *__hidden this@<rcx>, struct CProcess *@<rdx>, struct _GUID *__struct_ptr@<r8>, struct CClassData *@<r9>, struct CAppidData *, char, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180013e40`
- `0x1800436b0`
- `0x180045a90`

## callees

- `0x180003194`
- `0x1800065a4`
- `0x18000c894`
- `0x18000fe7c`
- `0x1800169b0`
- `0x1800189d0`
- `0x180018d24`
- `0x180018d8c`
- `0x1800210f8`
- `0x180023090`
- `0x180024fd0`
- `0x1800307c0`
- `0x180031b98`
- `0x180034260`
- `0x18003fb60`
- `0x180043e48`
- `0x180050fd0`
- `0x180051d0c`
- `0x180051e0c`
- `0x1800535d0`
- `0x180059020`
- `0x18005e438`
- `0x18005efe4`
- `0x180070940`
- `0x180070d50`
- `0x180070d78`
- `0x180070e74`
- `0x180070f04`
- `0x1800768f0`
- `0x1800772dc`
- `0x180085f0c`
- `0x18009e160`
- `0x1800a7388`
- `0x1800b7ac0`
- `0x1800fbf68`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044173`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800443d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044173`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800443d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004439a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004457f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004439a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004457f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004427b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004427b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004402e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044043`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004405c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800445dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800445f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044607`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004402e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044043`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004405c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800445dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800445f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044607`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800440a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800440f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800440a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800440f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004450d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004450d`

## string_xrefs

- `0x1800440be`: `onecore\com\combase\rpcss\olescm\clsid.hxx`
- `0x18004410b`: `onecore\com\combase\rpcss\olescm\clsid.hxx`
- `0x180043f38`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180044011`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18004420d`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180044242`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x1800442ca`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18004447d`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180044562`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x1800445bd`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x1800442ae`: `Failed to wait on ServerProcessLaunchCompletedEvent: %!WINERROR!.`

## pseudocode

```c
__int64 __fastcall CServerTableEntry::RegisterServer(
        CServerTableEntry *this,
        struct CProcess *a2,
        struct _GUID *a3,
        HSTRING *a4,
        HSTRING *a5,
        char a6,
        unsigned int a7,
        unsigned int *a8)
{
  int PreferredServerBitness; // r12d
  char v12; // r15
  char v13; // bl
  int PackageRelativeApplicationId; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdx
  unsigned __int64 v17; // r9
  char HasActivateAsPackage; // al
  int v19; // eax
  HRESULT v20; // eax
  HRESULT v21; // eax
  LPVOID v22; // rax
  char v23; // r12
  __int64 v24; // rsi
  int v25; // ecx
  struct CNamedObject *v26; // rax
  CNamedObject *v27; // rbx
  DWORD v28; // r8d
  CProcessIdTable *v29; // rcx
  CSurrogateListEntry *v30; // rax
  struct CSurrogateListEntry *v31; // rax
  CSurrogateList *v32; // rcx
  struct _GUID v33; // xmm0
  int ComCatalogObject; // eax
  char *v35; // rdi
  unsigned int (__fastcall *v36)(char *, __int64, __int64, _QWORD, struct _GUID *, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, GUID *, PSRWLOCK *); // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int v39; // [rsp+20h] [rbp-C1h]
  __int64 v40; // [rsp+28h] [rbp-B9h]
  int v41; // [rsp+40h] [rbp-A1h]
  unsigned __int8 v42; // [rsp+80h] [rbp-61h] BYREF
  unsigned __int8 v43; // [rsp+81h] [rbp-60h] BYREF
  char v44; // [rsp+82h] [rbp-5Fh]
  HSTRING string; // [rsp+88h] [rbp-59h] BYREF
  HSTRING v46; // [rsp+90h] [rbp-51h] BYREF
  HSTRING newString; // [rsp+98h] [rbp-49h] BYREF
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp-41h] BYREF
  char *v49; // [rsp+A8h] [rbp-39h] BYREF
  unsigned int *v50; // [rsp+B0h] [rbp-31h]
  struct _GUID v51; // [rsp+C0h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]

  v44 = a6;
  LODWORD(SRWLock) = a7;
  v50 = a8;
  PreferredServerBitness = 0;
  *(_QWORD *)&v51.Data1 = a3;
  v12 = 0;
  v43 = 0;
  v13 = 0;
  v42 = 0;
  newString = 0;
  v46 = 0;
  string = 0;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_DWORD *)this + 2) == 1 )
    {
      CAppidData::GetContextAndSubcontext((CAppidData *)a5, &v43, &v42);
      PreferredServerBitness = CAppidData::GetPreferredServerBitness(a5);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &newString,
        0);
      v20 = WindowsDuplicateString(a5[31], &newString);
      v15 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x149,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.hxx",
          (const char *)(unsigned int)v20,
          v39);
        v17 = v15;
        v16 = 1372;
        goto LABEL_8;
      }
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &v46,
        0);
      v21 = WindowsDuplicateString(a5[34], &v46);
      v15 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x159,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\clsid.hxx",
          (const char *)(unsigned int)v21,
          v39);
        v17 = v15;
        v16 = 1373;
        goto LABEL_8;
      }
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      PackageRelativeApplicationId = CAppidData::GetPackageRelativeApplicationId((CAppidData *)a5, &string);
      v15 = PackageRelativeApplicationId;
      if ( PackageRelativeApplicationId < 0 )
      {
        v16 = 1374;
        goto LABEL_7;
      }
      HasActivateAsPackage = CAppidData::HasActivateAsPackage((CAppidData *)a5);
      goto LABEL_32;
    }
  }
  else
  {
    CClassData::GetContextAndSubcontext((struct CClassData *)a4, &v43, &v42);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      PreferredServerBitness = CClassData::GetPreferredServerBitness(a4);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &newString,
        0);
      PackageRelativeApplicationId = CClassData::GetDeployingPackageName((CClassData *)a4, &newString);
      v15 = PackageRelativeApplicationId;
      if ( PackageRelativeApplicationId < 0 )
      {
        v16 = 1342;
LABEL_7:
        v17 = (unsigned int)PackageRelativeApplicationId;
LABEL_8:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
          (const char *)v17,
          v39);
LABEL_80:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&string);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v46);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&newString);
        return v15;
      }
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &v46,
        0);
      PackageRelativeApplicationId = CClassData::GetExecutionPackageName((CClassData *)a4, &v46);
      v15 = PackageRelativeApplicationId;
      if ( PackageRelativeApplicationId < 0 )
      {
        v16 = 1343;
        goto LABEL_7;
      }
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      PackageRelativeApplicationId = CClassData::GetPackageRelativeApplicationId((CClassData *)a4, &string);
      v15 = PackageRelativeApplicationId;
      if ( PackageRelativeApplicationId < 0 )
      {
        v16 = 1344;
        goto LABEL_7;
      }
      goto LABEL_11;
    }
    if ( a4 )
    {
      PreferredServerBitness = CClassData::GetPreferredServerBitness(a4);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &newString,
        0);
      PackageRelativeApplicationId = CClassData::GetDeployingPackageName((CClassData *)a4, &newString);
      v15 = PackageRelativeApplicationId;
      if ( PackageRelativeApplicationId < 0 )
      {
        v16 = 1354;
        goto LABEL_7;
      }
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &v46,
        0);
      PackageRelativeApplicationId = CClassData::GetExecutionPackageName((CClassData *)a4, &v46);
      v15 = PackageRelativeApplicationId;
      if ( PackageRelativeApplicationId < 0 )
      {
        v16 = 1355;
        goto LABEL_7;
      }
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      v19 = CClassData::GetPackageRelativeApplicationId((CClassData *)a4, &string);
      v15 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x54C,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
          (const char *)(unsigned int)v19,
          v39);
        if ( string )
          WindowsDeleteString(string);
        if ( v46 )
          WindowsDeleteString(v46);
        if ( newString )
          WindowsDeleteString(newString);
        return v15;
      }
LABEL_11:
      v12 = a4[12] != 0;
      HasActivateAsPackage = (*((__int64 (__fastcall **)(HSTRING *))*a4 + 6))(a4);
LABEL_32:
      v13 = HasActivateAsPackage;
    }
  }
  LODWORD(v49) = 0;
  v22 = HeapAlloc(g_hHeap, 0, 0xD0u);
  if ( v22 )
  {
    v41 = PreferredServerBitness;
    v23 = v44;
    v51 = *(struct _GUID *)*(_QWORD *)&v51.Data1;
    v24 = CServerListEntry::CServerListEntry(
            (_DWORD)v22,
            (_DWORD)this,
            (_DWORD)a2,
            (unsigned int)&v51,
            v43,
            v44,
            v42,
            v12,
            v41,
            (_DWORD)SRWLock,
            (__int64)&newString,
            (__int64)&v46,
            (__int64)&string,
            v13,
            (__int64)&v49);
    if ( v24 )
    {
      v15 = (unsigned int)v49;
      if ( (int)v49 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x57E,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
          (const char *)(unsigned int)v49,
          v39);
LABEL_79:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        goto LABEL_80;
      }
      v25 = *((_DWORD *)this + 3);
      if ( v25 )
      {
        v26 = ServerProcessLaunchCompletedEvent(v25);
        v27 = v26;
        if ( !v26 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x588,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
            (const char *)0x8007000ELL,
            v39);
LABEL_40:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          v15 = -2147024882;
          goto LABEL_80;
        }
        v28 = WaitForSingleObject(*((HANDLE *)v26 + 3), 0x2710u);
        if ( v28
          && (dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8)) )
        {
          LODWORD(v40) = v28;
          ComTraceMessageT<int>(
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
            (unsigned int)"CServerTableEntry::RegisterServer",
            1421,
            0,
            (__int64)L"Failed to wait on ServerProcessLaunchCompletedEvent: %!WINERROR!.",
            v40);
        }
        CNamedObject::Release(v27);
      }
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &gpServerLock);
      CSharedLock::LockExclusive((CServerTableEntry *)((char *)this + 88));
      if ( *((_QWORD *)this + 3) || (v15 = 0, *((_QWORD *)this + 4)) )
      {
        v15 = CServerTableEntry::RegisterHandles(this, (struct CServerListEntry *)v24, a2);
        if ( (v15 & 0x80000000) != 0 )
        {
LABEL_58:
          CSharedLock::UnlockExclusive((CServerTableEntry *)((char *)this + 88));
          if ( (v15 & 0x80000000) != 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x5BF,
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
              (const char *)v15,
              v39);
            if ( SRWLock )
              ReleaseSRWLockExclusive(SRWLock);
            goto LABEL_79;
          }
          CProcessIdTable::AddIfNecessary(v29, a2);
          if ( SRWLock )
            ReleaseSRWLockExclusive(SRWLock);
          if ( a4 && (v23 & 4) != 0 && (-(__int64)(a4[11] != 0) & ((unsigned __int64)a4[11] + 118)) != 0 )
          {
            v30 = (CSurrogateListEntry *)HeapAlloc(g_hHeap, 0, 0x80u);
            if ( !v30 )
              goto LABEL_40;
            v31 = CSurrogateListEntry::CSurrogateListEntry(
                    v30,
                    (unsigned __int16 *)(-(__int64)(a4[11] != 0) & ((unsigned __int64)a4[11] + 118)),
                    (struct CServerListEntry *)v24);
            if ( !v31 )
              goto LABEL_40;
            CSurrogateList::Insert(v32, v31);
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
            && a4
            && *((_BYTE *)a4 + 173)
            && CClassData::Service((CClassData *)a4) )
          {
            v33 = (struct _GUID)*((_OWORD *)a4 + 12);
            SRWLock = 0;
            v49 = 0;
            v51 = v33;
            ComCatalogObject = GetComCatalogObject(&GUID_bcf8570c_b66f_4849_aa7a_94d710f655bf, &v49);
            if ( ComCatalogObject >= 0 )
            {
              v35 = v49;
              v36 = *(unsigned int (__fastcall **)(char *, __int64, __int64, _QWORD, struct _GUID *, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, GUID *, PSRWLOCK *))(*(_QWORD *)v49 + 24LL);
              wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::reset(&SRWLock);
              if ( v36(
                     v35,
                     4,
                     0x8000000,
                     *((_QWORD *)a2 + 3),
                     &v51,
                     0,
                     0,
                     0,
                     0,
                     0,
                     0,
                     &GUID_000001e1_0000_0000_c000_000000000046,
                     &SRWLock) )
              {
                StringRawBuffer = WindowsGetStringRawBuffer(a4[17], 0);
                AddPrivateHiveOnlyServiceServerClsidForCompatTelemetry(&v51, StringRawBuffer);
                *(_BYTE *)(v24 + 200) = 1;
              }
            }
            else
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x5F5,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                (const char *)(unsigned int)ComCatalogObject,
                v39);
            }
            wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&SRWLock);
            wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v49);
          }
          *v50 = *(_DWORD *)(v24 + 132);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          v15 = 0;
          goto LABEL_80;
        }
      }
      if ( *((_DWORD *)this + 2)
        || ((*(void (__fastcall **)(CServerTableEntry *, __int64))(*(_QWORD *)this + 24LL))(this, v24),
            *((_DWORD *)this + 2)) )
      {
        if ( *((_DWORD *)this + 2) != 1 || !*((_DWORD *)this + 11) )
          goto LABEL_57;
      }
      else if ( !*((_DWORD *)this + 10) )
      {
        goto LABEL_57;
      }
      CProcess::FlagsOn(a2, 5u);
LABEL_57:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
      CListBase<1,1>::Insert((char *)this + 72, v24 + 16);
      goto LABEL_58;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x574,
    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
    (const char *)0x8007000ELL,
    v39);
  if ( string )
    WindowsDeleteString(string);
  if ( v46 )
    WindowsDeleteString(v46);
  if ( newString )
    WindowsDeleteString(newString);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180043e48  push    rbp
0x180043e4a  push    rbx
0x180043e4b  push    rsi
0x180043e4c  push    rdi
0x180043e4d  push    r12
0x180043e4f  push    r13
0x180043e51  push    r14
0x180043e53  push    r15
0x180043e55  lea     rbp, [rsp-7]
0x180043e5a  sub     rsp, 0E8h
0x180043e61  mov     rax, cs:__security_cookie
0x180043e68  xor     rax, rsp
0x180043e6b  mov     [rbp+3Fh+var_50], rax
0x180043e6f  mov     al, [rbp+3Fh+arg_28]
0x180043e72  mov     r14, r9
0x180043e75  mov     rsi, [rbp+3Fh+arg_20]
0x180043e79  mov     r13, rdx
0x180043e7c  mov     [rbp+3Fh+var_9E], al
0x180043e7f  mov     rdi, rcx
0x180043e82  mov     eax, [rbp+3Fh+arg_30]
0x180043e85  mov     dword ptr [rbp+3Fh+SRWLock], eax
0x180043e88  mov     rax, [rbp+3Fh+arg_38]
0x180043e8f  mov     [rbp+3Fh+var_70], rax
0x180043e93  xor     eax, eax
0x180043e95  mov     r12d, eax
0x180043e98  mov     qword ptr [rbp+3Fh+var_60.Data1], r8
0x180043e9c  mov     r15b, al
0x180043e9f  mov     [rbp+3Fh+var_9F], al
0x180043ea2  mov     bl, al
0x180043ea4  mov     [rbp+3Fh+var_A0], al
0x180043ea7  mov     [rbp+3Fh+newString], rax
0x180043eab  mov     [rbp+3Fh+var_90], rax
0x180043eaf  mov     [rbp+3Fh+string], rax
0x180043eb3  cmp     [rcx+8], eax
0x180043eb6  jnz     loc_18004406D
0x180043ebc  lea     r8, [rbp+3Fh+var_A0]; unsigned __int8 *
0x180043ec0  mov     rcx, r9; this
0x180043ec3  lea     rdx, [rbp+3Fh+var_9F]; unsigned __int8 *
0x180043ec7  call    ?GetContextAndSubcontext@CClassData@@SAXPEAV1@PEAE1@Z; CClassData::GetContextAndSubcontext(CClassData *,uchar *,uchar *)
0x180043ecc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180043ed3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180043ed8  test    al, al
0x180043eda  jz      loc_180043F8A
0x180043ee0  mov     rcx, r14
0x180043ee3  call    ?GetPreferredServerBitness@CClassData@@QEAA?AW4tagPreferredServerBitness@@XZ; CClassData::GetPreferredServerBitness(void)
0x180043ee8  xor     edx, edx
0x180043eea  lea     rcx, [rbp+3Fh+newString]
0x180043eee  mov     r12d, eax
0x180043ef1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180043ef6  lea     rdx, [rbp+3Fh+newString]; HSTRING *
0x180043efa  mov     rcx, r14; this
0x180043efd  call    ?GetDeployingPackageName@CClassData@@QEBAJPEAPEAUHSTRING__@@@Z; CClassData::GetDeployingPackageName(HSTRING__ * *)
0x180043f02  mov     ebx, eax
0x180043f04  test    eax, eax
0x180043f06  jns     short loc_180043F0F
0x180043f08  mov     edx, 53Eh
0x180043f0d  jmp     short loc_180043F31
0x180043f0f  xor     edx, edx
0x180043f11  lea     rcx, [rbp+3Fh+var_90]
0x180043f15  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180043f1a  lea     rdx, [rbp+3Fh+var_90]; HSTRING *
0x180043f1e  mov     rcx, r14; this
0x180043f21  call    ?GetExecutionPackageName@CClassData@@QEBAJPEAPEAUHSTRING__@@@Z; CClassData::GetExecutionPackageName(HSTRING__ * *)
0x180043f26  mov     ebx, eax
0x180043f28  test    eax, eax
0x180043f2a  jns     short loc_180043F49
0x180043f2c  mov     edx, 53Fh; void *
0x180043f31  mov     r9d, eax; char *
0x180043f34  mov     rcx, [rbp+47h]; this
0x180043f38  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180043f3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043f44  jmp     loc_18004459A
0x180043f49  xor     edx, edx
0x180043f4b  lea     rcx, [rbp+3Fh+string]
0x180043f4f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180043f54  lea     rdx, [rbp+3Fh+string]; HSTRING *
0x180043f58  mov     rcx, r14; this
0x180043f5b  call    ?GetPackageRelativeApplicationId@CClassData@@QEBAJPEAPEAUHSTRING__@@@Z; CClassData::GetPackageRelativeApplicationId(HSTRING__ * *)
0x180043f60  mov     ebx, eax
0x180043f62  test    eax, eax
0x180043f64  jns     short loc_180043F6D
0x180043f66  mov     edx, 540h
0x180043f6b  jmp     short loc_180043F31
0x180043f6d  mov     rax, [r14]
0x180043f70  mov     rcx, r14
0x180043f73  cmp     qword ptr [r14+60h], 0
0x180043f78  setnz   r15b
0x180043f7c  mov     rax, [rax+30h]
0x180043f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f85  jmp     loc_18004415B
0x180043f8a  test    r14, r14
0x180043f8d  jz      loc_18004415D
0x180043f93  mov     rcx, r14
0x180043f96  call    ?GetPreferredServerBitness@CClassData@@QEAA?AW4tagPreferredServerBitness@@XZ; CClassData::GetPreferredServerBitness(void)
0x180043f9b  xor     edx, edx
0x180043f9d  lea     rcx, [rbp+3Fh+newString]
0x180043fa1  mov     r12d, eax
0x180043fa4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180043fa9  lea     rdx, [rbp+3Fh+newString]; HSTRING *
0x180043fad  mov     rcx, r14; this
0x180043fb0  call    ?GetDeployingPackageName@CClassData@@QEBAJPEAPEAUHSTRING__@@@Z; CClassData::GetDeployingPackageName(HSTRING__ * *)
0x180043fb5  mov     ebx, eax
0x180043fb7  test    eax, eax
0x180043fb9  jns     short loc_180043FC5
0x180043fbb  mov     edx, 54Ah
0x180043fc0  jmp     loc_180043F31
0x180043fc5  xor     edx, edx
0x180043fc7  lea     rcx, [rbp+3Fh+var_90]
0x180043fcb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180043fd0  lea     rdx, [rbp+3Fh+var_90]; HSTRING *
0x180043fd4  mov     rcx, r14; this
0x180043fd7  call    ?GetExecutionPackageName@CClassData@@QEBAJPEAPEAUHSTRING__@@@Z; CClassData::GetExecutionPackageName(HSTRING__ * *)
0x180043fdc  mov     ebx, eax
0x180043fde  test    eax, eax
0x180043fe0  jns     short loc_180043FEC
0x180043fe2  mov     edx, 54Bh
0x180043fe7  jmp     loc_180043F31
0x180043fec  xor     edx, edx
0x180043fee  lea     rcx, [rbp+3Fh+string]
0x180043ff2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180043ff7  lea     rdx, [rbp+3Fh+string]; HSTRING *
0x180043ffb  mov     rcx, r14; this
0x180043ffe  call    ?GetPackageRelativeApplicationId@CClassData@@QEBAJPEAPEAUHSTRING__@@@Z; CClassData::GetPackageRelativeApplicationId(HSTRING__ * *)
0x180044003  mov     ebx, eax
0x180044005  test    eax, eax
0x180044007  jns     loc_180043F6D
0x18004400d  mov     rcx, [rbp+47h]; this
0x180044011  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180044018  mov     r9d, eax; char *
0x18004401b  mov     edx, 54Ch; void *
0x180044020  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044025  mov     rcx, [rbp+3Fh+string]; string
0x180044029  test    rcx, rcx
0x18004402c  jz      short loc_18004403A
0x18004402e  call    cs:__imp_WindowsDeleteString
0x180044035  nop     dword ptr [rax+rax+00h]
0x18004403a  mov     rcx, [rbp+3Fh+var_90]; string
0x18004403e  test    rcx, rcx
0x180044041  jz      short loc_18004404F
0x180044043  call    cs:__imp_WindowsDeleteString
0x18004404a  nop     dword ptr [rax+rax+00h]
0x18004404f  mov     rcx, [rbp+3Fh+newString]; string
0x180044053  test    rcx, rcx
0x180044056  jz      loc_1800445B5
0x18004405c  call    cs:__imp_WindowsDeleteString
0x180044063  nop     dword ptr [rax+rax+00h]
0x180044068  jmp     loc_1800445B5
0x18004406d  cmp     dword ptr [rcx+8], 1
0x180044071  jnz     loc_18004415D
0x180044077  lea     r8, [rbp+3Fh+var_A0]; unsigned __int8 *
0x18004407b  mov     rcx, rsi; this
0x18004407e  lea     rdx, [rbp+3Fh+var_9F]; unsigned __int8 *
0x180044082  call    ?GetContextAndSubcontext@CAppidData@@QEBAXPEAE0@Z; CAppidData::GetContextAndSubcontext(uchar *,uchar *)
0x180044087  mov     rcx, rsi
0x18004408a  call    ?GetPreferredServerBitness@CAppidData@@QEAA?AW4tagPreferredServerBitness@@XZ; CAppidData::GetPreferredServerBitness(void)
0x18004408f  xor     edx, edx
0x180044091  lea     rcx, [rbp+3Fh+newString]
0x180044095  mov     r12d, eax
0x180044098  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18004409d  mov     rcx, [rsi+0F8h]; string
0x1800440a4  lea     rdx, [rbp+3Fh+newString]; newString
0x1800440a8  call    cs:__imp_WindowsDuplicateString
0x1800440af  nop     dword ptr [rax+rax+00h]
0x1800440b4  mov     ebx, eax
0x1800440b6  test    eax, eax
0x1800440b8  jns     short loc_1800440DF
0x1800440ba  mov     rcx, [rbp+47h]; this
0x1800440be  lea     r8, aOnecoreComComb_115; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x1800440c5  mov     r9d, eax; char *
0x1800440c8  mov     edx, 149h; void *
0x1800440cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800440d2  mov     r9d, ebx
0x1800440d5  mov     edx, 55Ch
0x1800440da  jmp     loc_180043F34
0x1800440df  xor     edx, edx
0x1800440e1  lea     rcx, [rbp+3Fh+var_90]
0x1800440e5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800440ea  mov     rcx, [rsi+110h]; string
0x1800440f1  lea     rdx, [rbp+3Fh+var_90]; newString
0x1800440f5  call    cs:__imp_WindowsDuplicateString
0x1800440fc  nop     dword ptr [rax+rax+00h]
0x180044101  mov     ebx, eax
0x180044103  test    eax, eax
0x180044105  jns     short loc_18004412C
0x180044107  mov     rcx, [rbp+47h]; this
0x18004410b  lea     r8, aOnecoreComComb_115; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180044112  mov     r9d, eax; char *
0x180044115  mov     edx, 159h; void *
0x18004411a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004411f  mov     r9d, ebx
0x180044122  mov     edx, 55Dh
0x180044127  jmp     loc_180043F34
0x18004412c  xor     edx, edx
0x18004412e  lea     rcx, [rbp+3Fh+string]
0x180044132  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180044137  lea     rdx, [rbp+3Fh+string]; HSTRING *
0x18004413b  mov     rcx, rsi; this
0x18004413e  call    ?GetPackageRelativeApplicationId@CAppidData@@QEBAJPEAPEAUHSTRING__@@@Z; CAppidData::GetPackageRelativeApplicationId(HSTRING__ * *)
0x180044143  mov     ebx, eax
0x180044145  test    eax, eax
0x180044147  jns     short loc_180044153
0x180044149  mov     edx, 55Eh
0x18004414e  jmp     loc_180043F31
0x180044153  mov     rcx, rsi; this
0x180044156  call    ?HasActivateAsPackage@CAppidData@@QEBA_NXZ; CAppidData::HasActivateAsPackage(void)
0x18004415b  mov     bl, al
0x18004415d  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180044164  xor     edx, edx; dwFlags
0x180044166  mov     r8d, 0D0h; dwBytes
0x18004416c  mov     dword ptr [rbp+3Fh+var_78], 0
0x180044173  call    cs:__imp_HeapAlloc
0x18004417a  nop     dword ptr [rax+rax+00h]
0x18004417f  mov     rcx, rax
0x180044182  test    rax, rax
0x180044185  jz      loc_1800445B9
0x18004418b  mov     rax, qword ptr [rbp+3Fh+var_60.Data1]
0x18004418f  lea     r9, [rbp+3Fh+var_60]
0x180044193  mov     r8, r13
0x180044196  mov     rdx, rdi
0x180044199  movaps  xmm0, xmmword ptr [rax]
0x18004419c  lea     rax, [rbp+3Fh+var_78]
0x1800441a0  mov     [rsp+120h+var_B0], rax
0x1800441a5  lea     rax, [rbp+3Fh+string]
0x1800441a9  mov     [rsp+120h+var_B8], bl
0x1800441ad  mov     [rsp+120h+var_C0], rax
0x1800441b2  lea     rax, [rbp+3Fh+var_90]
0x1800441b6  mov     [rsp+120h+var_C8], rax
0x1800441bb  lea     rax, [rbp+3Fh+newString]
0x1800441bf  mov     [rsp+120h+var_D0], rax
0x1800441c4  mov     eax, dword ptr [rbp+3Fh+SRWLock]
0x1800441c7  mov     [rsp+120h+var_D8], eax
0x1800441cb  mov     al, [rbp+3Fh+var_A0]
0x1800441ce  mov     dword ptr [rsp+120h+var_E0], r12d
0x1800441d3  mov     r12b, [rbp+3Fh+var_9E]
0x1800441d7  mov     byte ptr [rsp+120h+var_E8], r15b
0x1800441dc  mov     byte ptr [rsp+120h+var_F0], al
0x1800441e0  mov     al, [rbp+3Fh+var_9F]
0x1800441e3  mov     byte ptr [rsp+120h+var_F8], r12b
0x1800441e8  mov     byte ptr [rsp+120h+var_100], al; int
0x1800441ec  movdqa  xmmword ptr [rbp+3Fh+var_60.Data1], xmm0
0x1800441f1  call    ??0CServerListEntry@@QEAA@PEAVCServerTableEntry@@PEAVCProcess@@U_GUID@@EEE_NKK$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@443AEAJ@Z; CServerListEntry::CServerListEntry(CServerTableEntry *,CProcess *,_GUID,uchar,uchar,uchar,bool,ulong,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&,bool,long &)
0x1800441f6  mov     rsi, rax
0x1800441f9  test    rax, rax
0x1800441fc  jz      loc_1800445B9
0x180044202  mov     ebx, dword ptr [rbp+3Fh+var_78]
0x180044205  test    ebx, ebx
0x180044207  jns     short loc_180044226
0x180044209  mov     rcx, [rbp+47h]; this
0x18004420d  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180044214  mov     r9d, ebx; char *
0x180044217  mov     edx, 57Eh; void *
0x18004421c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044221  jmp     loc_18004458B
0x180044226  mov     ecx, [rdi+0Ch]; int
0x180044229  test    ecx, ecx
0x18004422b  jz      loc_1800442DE
0x180044231  call    ?ServerProcessLaunchCompletedEvent@@YAPEAVCNamedObject@@J@Z; ServerProcessLaunchCompletedEvent(long)
0x180044236  mov     rbx, rax
0x180044239  test    rax, rax
0x18004423c  jnz     short loc_180044272
0x18004423e  mov     rcx, [rbp+47h]; this
0x180044242  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180044249  mov     r9d, 8007000Eh; char *
0x18004424f  mov     edx, 588h; void *
0x180044254  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044259  mov     rax, [rsi]
0x18004425c  mov     rcx, rsi
0x18004425f  mov     rax, [rax+10h]
0x180044263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044268  mov     ebx, 8007000Eh
0x18004426d  jmp     loc_18004459A
0x180044272  mov     rcx, [rax+18h]; hHandle
0x180044276  mov     edx, 2710h; dwMilliseconds
0x18004427b  call    cs:__imp_WaitForSingleObject
0x180044282  nop     dword ptr [rax+rax+00h]
0x180044287  mov     r8d, eax
0x18004428a  test    eax, eax
0x18004428c  jz      short loc_1800442D6
0x18004428e  mov     ecx, cs:dword_1801574B8
0x180044294  test    ecx, ecx
0x180044296  jnz     short loc_1800442A9
0x180044298  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x18004429e  jz      short loc_1800442D6
0x1800442a0  call    IsWppLevelEnabled
0x1800442a5  test    al, al
0x1800442a7  jz      short loc_1800442D6
0x1800442a9  mov     dword ptr [rsp+120h+var_F8], r8d
0x1800442ae  lea     rax, aFailedToWaitOn; "Failed to wait on ServerProcessLaunchCo"...
0x1800442b5  mov     r8d, 58Dh
0x1800442bb  mov     qword ptr [rsp+120h+var_100], rax; int
0x1800442c0  xor     r9d, r9d
0x1800442c3  lea     rdx, aCservertableen_6; "CServerTableEntry::RegisterServer"
0x1800442ca  lea     rcx, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x1800442d1  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x1800442d6  mov     rcx, rbx; this
0x1800442d9  call    ?Release@CNamedObject@@UEAAKXZ; CNamedObject::Release(void)
0x1800442de  lea     rdx, ?gpServerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpServerLock
0x1800442e5  lea     rcx, [rbp+3Fh+SRWLock]
0x1800442e9  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800442ee  lea     rcx, [rdi+58h]; this
  ... truncated ...
```
