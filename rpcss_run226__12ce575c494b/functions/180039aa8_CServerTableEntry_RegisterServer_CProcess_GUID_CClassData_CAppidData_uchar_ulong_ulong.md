# CServerTableEntry::RegisterServer(CProcess *,_GUID,CClassData *,CAppidData *,uchar,ulong,ulong *)

- ea: `0x180039aa8`
- end: `0x18003a244`
- name: `?RegisterServer@CServerTableEntry@@QEAAJPEAVCProcess@@U_GUID@@PEAVCClassData@@PEAVCAppidData@@EKPEAK@Z`
- size: `1948`
- prototype: `__int64 __fastcall(CServerTableEntry *this, struct CProcess *, struct _GUID *, HSTRING *, HSTRING *, char, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000ff80`
- `0x180039340`
- `0x18003b720`

## callees

- `0x180003064`
- `0x180003654`
- `0x180005c40`
- `0x18000b710`
- `0x180012910`
- `0x180014870`
- `0x180014b80`
- `0x180014be0`
- `0x18001cbf8`
- `0x18001e9c4`
- `0x1800262fc`
- `0x1800267a8`
- `0x18002ba28`
- `0x18002d960`
- `0x18002effc`
- `0x180034540`
- `0x18003868c`
- `0x180039aa8`
- `0x180043850`
- `0x18004fc9c`
- `0x180053cf4`
- `0x1800595bc`
- `0x18005d3fc`
- `0x18005d4f4`
- `0x18006b8e4`
- `0x18006b90c`
- `0x18006b9ec`
- `0x18006ba74`
- `0x1800721c8`
- `0x180072f94`
- `0x180081a18`
- `0x180098b54`
- `0x1800a1e98`
- `0x1800b27e0`
- `0x1800f4178`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039db5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a003`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039db5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a003`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039fd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a1a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039fd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a1a3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180039eb7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180039eb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039c8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039c9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039cb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a1fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a20a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a219`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039c8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039c9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039cb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a1fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a20a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a219`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180039cf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180039d3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180039cf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180039d3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a137`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a137`

## string_xrefs

- `0x180039d06`: `onecore\com\combase\rpcss\olescm\clsid.hxx`
- `0x180039d4d`: `onecore\com\combase\rpcss\olescm\clsid.hxx`
- `0x180039b98`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180039c71`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180039e49`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180039e7e`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180039f00`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18003a0a7`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18003a186`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18003a1db`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180039ee4`: `Failed to wait on ServerProcessLaunchCompletedEvent: %!WINERROR!.`

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
          && (dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8)) )
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
0x180039aa8  push    rbp
0x180039aaa  push    rbx
0x180039aab  push    rsi
0x180039aac  push    rdi
0x180039aad  push    r12
0x180039aaf  push    r13
0x180039ab1  push    r14
0x180039ab3  push    r15
0x180039ab5  lea     rbp, [rsp-7]
0x180039aba  sub     rsp, 0E8h
0x180039ac1  mov     rax, cs:__security_cookie
0x180039ac8  xor     rax, rsp
0x180039acb  mov     [rbp+3Fh+var_50], rax
0x180039acf  mov     al, [rbp+3Fh+arg_28]
0x180039ad2  mov     r14, r9
0x180039ad5  mov     rsi, [rbp+3Fh+arg_20]
0x180039ad9  mov     r13, rdx
0x180039adc  mov     [rbp+3Fh+var_9E], al
0x180039adf  mov     rdi, rcx
0x180039ae2  mov     eax, [rbp+3Fh+arg_30]
0x180039ae5  mov     dword ptr [rbp+3Fh+SRWLock], eax
0x180039ae8  mov     rax, [rbp+3Fh+arg_38]
0x180039aef  mov     [rbp+3Fh+var_70], rax
0x180039af3  xor     eax, eax
0x180039af5  mov     r12d, eax
0x180039af8  mov     qword ptr [rbp+3Fh+var_60.Data1], r8
0x180039afc  mov     r15b, al
0x180039aff  mov     [rbp+3Fh+var_9F], al
0x180039b02  mov     bl, al
0x180039b04  mov     [rbp+3Fh+var_A0], al
0x180039b07  mov     [rbp+3Fh+newString], rax
0x180039b0b  mov     [rbp+3Fh+var_90], rax
0x180039b0f  mov     [rbp+3Fh+string], rax
0x180039b13  cmp     [rcx+8], eax
0x180039b16  jnz     loc_180039CBB
0x180039b1c  lea     r8, [rbp+3Fh+var_A0]; unsigned __int8 *
0x180039b20  mov     rcx, r9; this
0x180039b23  lea     rdx, [rbp+3Fh+var_9F]; unsigned __int8 *
0x180039b27  call    ?GetContextAndSubcontext@CClassData@@SAXPEAV1@PEAE1@Z; CClassData::GetContextAndSubcontext(CClassData *,uchar *,uchar *)
0x180039b2c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180039b33  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180039b38  test    al, al
0x180039b3a  jz      loc_180039BEA
0x180039b40  mov     rcx, r14
0x180039b43  call    ?GetPreferredServerBitness@CClassData@@QEAA?AW4tagPreferredServerBitness@@XZ; CClassData::GetPreferredServerBitness(void)
0x180039b48  xor     edx, edx
0x180039b4a  lea     rcx, [rbp+3Fh+newString]
0x180039b4e  mov     r12d, eax
0x180039b51  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180039b56  lea     rdx, [rbp+3Fh+newString]; HSTRING *
0x180039b5a  mov     rcx, r14; this
0x180039b5d  call    ?GetDeployingPackageName@CClassData@@QEBAJPEAPEAUHSTRING__@@@Z; CClassData::GetDeployingPackageName(HSTRING__ * *)
0x180039b62  mov     ebx, eax
0x180039b64  test    eax, eax
0x180039b66  jns     short loc_180039B6F
0x180039b68  mov     edx, 53Eh
0x180039b6d  jmp     short loc_180039B91
0x180039b6f  xor     edx, edx
0x180039b71  lea     rcx, [rbp+3Fh+var_90]
0x180039b75  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180039b7a  lea     rdx, [rbp+3Fh+var_90]; HSTRING *
0x180039b7e  mov     rcx, r14; this
0x180039b81  call    ?GetExecutionPackageName@CClassData@@QEBAJPEAPEAUHSTRING__@@@Z; CClassData::GetExecutionPackageName(HSTRING__ * *)
0x180039b86  mov     ebx, eax
0x180039b88  test    eax, eax
0x180039b8a  jns     short loc_180039BA9
0x180039b8c  mov     edx, 53Fh; void *
0x180039b91  mov     r9d, eax; char *
0x180039b94  mov     rcx, [rbp+47h]; this
0x180039b98  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180039b9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039ba4  jmp     loc_18003A1B8
0x180039ba9  xor     edx, edx
0x180039bab  lea     rcx, [rbp+3Fh+string]
0x180039baf  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180039bb4  lea     rdx, [rbp+3Fh+string]; HSTRING *
0x180039bb8  mov     rcx, r14; this
0x180039bbb  call    ?GetPackageRelativeApplicationId@CClassData@@QEBAJPEAPEAUHSTRING__@@@Z; CClassData::GetPackageRelativeApplicationId(HSTRING__ * *)
0x180039bc0  mov     ebx, eax
0x180039bc2  test    eax, eax
0x180039bc4  jns     short loc_180039BCD
0x180039bc6  mov     edx, 540h
0x180039bcb  jmp     short loc_180039B91
0x180039bcd  mov     rax, [r14]
0x180039bd0  mov     rcx, r14
0x180039bd3  cmp     qword ptr [r14+60h], 0
0x180039bd8  setnz   r15b
0x180039bdc  mov     rax, [rax+30h]
0x180039be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039be5  jmp     loc_180039D9D
0x180039bea  test    r14, r14
0x180039bed  jz      loc_180039D9F
0x180039bf3  mov     rcx, r14
0x180039bf6  call    ?GetPreferredServerBitness@CClassData@@QEAA?AW4tagPreferredServerBitness@@XZ; CClassData::GetPreferredServerBitness(void)
0x180039bfb  xor     edx, edx
0x180039bfd  lea     rcx, [rbp+3Fh+newString]
0x180039c01  mov     r12d, eax
0x180039c04  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180039c09  lea     rdx, [rbp+3Fh+newString]; HSTRING *
0x180039c0d  mov     rcx, r14; this
0x180039c10  call    ?GetDeployingPackageName@CClassData@@QEBAJPEAPEAUHSTRING__@@@Z; CClassData::GetDeployingPackageName(HSTRING__ * *)
0x180039c15  mov     ebx, eax
0x180039c17  test    eax, eax
0x180039c19  jns     short loc_180039C25
0x180039c1b  mov     edx, 54Ah
0x180039c20  jmp     loc_180039B91
0x180039c25  xor     edx, edx
0x180039c27  lea     rcx, [rbp+3Fh+var_90]
0x180039c2b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180039c30  lea     rdx, [rbp+3Fh+var_90]; HSTRING *
0x180039c34  mov     rcx, r14; this
0x180039c37  call    ?GetExecutionPackageName@CClassData@@QEBAJPEAPEAUHSTRING__@@@Z; CClassData::GetExecutionPackageName(HSTRING__ * *)
0x180039c3c  mov     ebx, eax
0x180039c3e  test    eax, eax
0x180039c40  jns     short loc_180039C4C
0x180039c42  mov     edx, 54Bh
0x180039c47  jmp     loc_180039B91
0x180039c4c  xor     edx, edx
0x180039c4e  lea     rcx, [rbp+3Fh+string]
0x180039c52  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180039c57  lea     rdx, [rbp+3Fh+string]; HSTRING *
0x180039c5b  mov     rcx, r14; this
0x180039c5e  call    ?GetPackageRelativeApplicationId@CClassData@@QEBAJPEAPEAUHSTRING__@@@Z; CClassData::GetPackageRelativeApplicationId(HSTRING__ * *)
0x180039c63  mov     ebx, eax
0x180039c65  test    eax, eax
0x180039c67  jns     loc_180039BCD
0x180039c6d  mov     rcx, [rbp+47h]; this
0x180039c71  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180039c78  mov     r9d, eax; char *
0x180039c7b  mov     edx, 54Ch; void *
0x180039c80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039c85  mov     rcx, [rbp+3Fh+string]; string
0x180039c89  test    rcx, rcx
0x180039c8c  jz      short loc_180039C94
0x180039c8e  call    cs:__imp_WindowsDeleteString
0x180039c94  mov     rcx, [rbp+3Fh+var_90]; string
0x180039c98  test    rcx, rcx
0x180039c9b  jz      short loc_180039CA3
0x180039c9d  call    cs:__imp_WindowsDeleteString
0x180039ca3  mov     rcx, [rbp+3Fh+newString]; string
0x180039ca7  test    rcx, rcx
0x180039caa  jz      loc_18003A1D3
0x180039cb0  call    cs:__imp_WindowsDeleteString
0x180039cb6  jmp     loc_18003A1D3
0x180039cbb  cmp     dword ptr [rcx+8], 1
0x180039cbf  jnz     loc_180039D9F
0x180039cc5  lea     r8, [rbp+3Fh+var_A0]; unsigned __int8 *
0x180039cc9  mov     rcx, rsi; this
0x180039ccc  lea     rdx, [rbp+3Fh+var_9F]; unsigned __int8 *
0x180039cd0  call    ?GetContextAndSubcontext@CAppidData@@QEBAXPEAE0@Z; CAppidData::GetContextAndSubcontext(uchar *,uchar *)
0x180039cd5  mov     rcx, rsi
0x180039cd8  call    ?GetPreferredServerBitness@CAppidData@@QEAA?AW4tagPreferredServerBitness@@XZ; CAppidData::GetPreferredServerBitness(void)
0x180039cdd  xor     edx, edx
0x180039cdf  lea     rcx, [rbp+3Fh+newString]
0x180039ce3  mov     r12d, eax
0x180039ce6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180039ceb  mov     rcx, [rsi+0F8h]; string
0x180039cf2  lea     rdx, [rbp+3Fh+newString]; newString
0x180039cf6  call    cs:__imp_WindowsDuplicateString
0x180039cfc  mov     ebx, eax
0x180039cfe  test    eax, eax
0x180039d00  jns     short loc_180039D27
0x180039d02  mov     rcx, [rbp+47h]; this
0x180039d06  lea     r8, aOnecoreComComb_115; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180039d0d  mov     r9d, eax; char *
0x180039d10  mov     edx, 149h; void *
0x180039d15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039d1a  mov     r9d, ebx
0x180039d1d  mov     edx, 55Ch
0x180039d22  jmp     loc_180039B94
0x180039d27  xor     edx, edx
0x180039d29  lea     rcx, [rbp+3Fh+var_90]
0x180039d2d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180039d32  mov     rcx, [rsi+110h]; string
0x180039d39  lea     rdx, [rbp+3Fh+var_90]; newString
0x180039d3d  call    cs:__imp_WindowsDuplicateString
0x180039d43  mov     ebx, eax
0x180039d45  test    eax, eax
0x180039d47  jns     short loc_180039D6E
0x180039d49  mov     rcx, [rbp+47h]; this
0x180039d4d  lea     r8, aOnecoreComComb_115; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180039d54  mov     r9d, eax; char *
0x180039d57  mov     edx, 159h; void *
0x180039d5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039d61  mov     r9d, ebx
0x180039d64  mov     edx, 55Dh
0x180039d69  jmp     loc_180039B94
0x180039d6e  xor     edx, edx
0x180039d70  lea     rcx, [rbp+3Fh+string]
0x180039d74  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180039d79  lea     rdx, [rbp+3Fh+string]; HSTRING *
0x180039d7d  mov     rcx, rsi; this
0x180039d80  call    ?GetPackageRelativeApplicationId@CAppidData@@QEBAJPEAPEAUHSTRING__@@@Z; CAppidData::GetPackageRelativeApplicationId(HSTRING__ * *)
0x180039d85  mov     ebx, eax
0x180039d87  test    eax, eax
0x180039d89  jns     short loc_180039D95
0x180039d8b  mov     edx, 55Eh
0x180039d90  jmp     loc_180039B91
0x180039d95  mov     rcx, rsi; this
0x180039d98  call    ?HasActivateAsPackage@CAppidData@@QEBA_NXZ; CAppidData::HasActivateAsPackage(void)
0x180039d9d  mov     bl, al
0x180039d9f  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180039da6  xor     edx, edx; dwFlags
0x180039da8  mov     r8d, 0D0h; dwBytes
0x180039dae  mov     dword ptr [rbp+3Fh+var_78], 0
0x180039db5  call    cs:__imp_HeapAlloc
0x180039dbb  mov     rcx, rax
0x180039dbe  test    rax, rax
0x180039dc1  jz      loc_18003A1D7
0x180039dc7  mov     rax, qword ptr [rbp+3Fh+var_60.Data1]
0x180039dcb  lea     r9, [rbp+3Fh+var_60]
0x180039dcf  mov     r8, r13
0x180039dd2  mov     rdx, rdi
0x180039dd5  movaps  xmm0, xmmword ptr [rax]
0x180039dd8  lea     rax, [rbp+3Fh+var_78]
0x180039ddc  mov     [rsp+120h+var_B0], rax
0x180039de1  lea     rax, [rbp+3Fh+string]
0x180039de5  mov     [rsp+120h+var_B8], bl
0x180039de9  mov     [rsp+120h+var_C0], rax
0x180039dee  lea     rax, [rbp+3Fh+var_90]
0x180039df2  mov     [rsp+120h+var_C8], rax
0x180039df7  lea     rax, [rbp+3Fh+newString]
0x180039dfb  mov     [rsp+120h+var_D0], rax
0x180039e00  mov     eax, dword ptr [rbp+3Fh+SRWLock]
0x180039e03  mov     [rsp+120h+var_D8], eax
0x180039e07  mov     al, [rbp+3Fh+var_A0]
0x180039e0a  mov     dword ptr [rsp+120h+var_E0], r12d
0x180039e0f  mov     r12b, [rbp+3Fh+var_9E]
0x180039e13  mov     byte ptr [rsp+120h+var_E8], r15b
0x180039e18  mov     byte ptr [rsp+120h+var_F0], al
0x180039e1c  mov     al, [rbp+3Fh+var_9F]
0x180039e1f  mov     byte ptr [rsp+120h+var_F8], r12b
0x180039e24  mov     byte ptr [rsp+120h+var_100], al; int
0x180039e28  movdqa  xmmword ptr [rbp+3Fh+var_60.Data1], xmm0
0x180039e2d  call    ??0CServerListEntry@@QEAA@PEAVCServerTableEntry@@PEAVCProcess@@U_GUID@@EEE_NKK$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@443AEAJ@Z; CServerListEntry::CServerListEntry(CServerTableEntry *,CProcess *,_GUID,uchar,uchar,uchar,bool,ulong,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&,bool,long &)
0x180039e32  mov     rsi, rax
0x180039e35  test    rax, rax
0x180039e38  jz      loc_18003A1D7
0x180039e3e  mov     ebx, dword ptr [rbp+3Fh+var_78]
0x180039e41  test    ebx, ebx
0x180039e43  jns     short loc_180039E62
0x180039e45  mov     rcx, [rbp+47h]; this
0x180039e49  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180039e50  mov     r9d, ebx; char *
0x180039e53  mov     edx, 57Eh; void *
0x180039e58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039e5d  jmp     loc_18003A1A9
0x180039e62  mov     ecx, [rdi+0Ch]; int
0x180039e65  test    ecx, ecx
0x180039e67  jz      loc_180039F14
0x180039e6d  call    ?ServerProcessLaunchCompletedEvent@@YAPEAVCNamedObject@@J@Z; ServerProcessLaunchCompletedEvent(long)
0x180039e72  mov     rbx, rax
0x180039e75  test    rax, rax
0x180039e78  jnz     short loc_180039EAE
0x180039e7a  mov     rcx, [rbp+47h]; this
0x180039e7e  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180039e85  mov     r9d, 8007000Eh; char *
0x180039e8b  mov     edx, 588h; void *
0x180039e90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039e95  mov     rax, [rsi]
0x180039e98  mov     rcx, rsi
0x180039e9b  mov     rax, [rax+10h]
0x180039e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ea4  mov     ebx, 8007000Eh
0x180039ea9  jmp     loc_18003A1B8
0x180039eae  mov     rcx, [rax+18h]; hHandle
0x180039eb2  mov     edx, 2710h; dwMilliseconds
0x180039eb7  call    cs:__imp_WaitForSingleObject
0x180039ebd  mov     r8d, eax
0x180039ec0  test    eax, eax
0x180039ec2  jz      short loc_180039F0C
0x180039ec4  mov     ecx, cs:dword_18014E4B8
0x180039eca  test    ecx, ecx
0x180039ecc  jnz     short loc_180039EDF
0x180039ece  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x180039ed4  jz      short loc_180039F0C
0x180039ed6  call    IsWppLevelEnabled
0x180039edb  test    al, al
0x180039edd  jz      short loc_180039F0C
0x180039edf  mov     dword ptr [rsp+120h+var_F8], r8d
0x180039ee4  lea     rax, aFailedToWaitOn; "Failed to wait on ServerProcessLaunchCo"...
0x180039eeb  mov     r8d, 58Dh
0x180039ef1  mov     qword ptr [rsp+120h+var_100], rax; int
0x180039ef6  xor     r9d, r9d
0x180039ef9  lea     rdx, aCservertableen_6; "CServerTableEntry::RegisterServer"
0x180039f00  lea     rcx, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180039f07  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x180039f0c  mov     rcx, rbx; this
0x180039f0f  call    ?Release@CNamedObject@@UEAAKXZ; CNamedObject::Release(void)
0x180039f14  lea     rdx, ?gpServerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK gpServerLock
0x180039f1b  lea     rcx, [rbp+3Fh+SRWLock]
0x180039f1f  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180039f24  lea     rcx, [rdi+58h]; this
0x180039f28  call    ?LockExclusive@CSharedLock@@QEAAXXZ; CSharedLock::LockExclusive(void)
0x180039f2d  cmp     qword ptr [rdi+18h], 0
0x180039f32  jnz     short loc_180039F3C
0x180039f34  xor     ebx, ebx
0x180039f36  cmp     [rdi+20h], rbx
0x180039f3a  jz      short loc_180039F50
0x180039f3c  mov     r8, r13; struct CProcess *
  ... truncated ...
```
