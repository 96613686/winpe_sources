# DockedClient::DoLXPBizCritUpdates(ushort *,int *,ushort * *)

- ea: `0x18002ee90`
- end: `0x18002f870`
- name: `?DoLXPBizCritUpdates@DockedClient@@UEAAJPEAGPEAHPEAPEAG@Z`
- size: `2528`
- prototype: `__int64 __fastcall(DockedClient *__hidden this, unsigned __int16 *, int *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180007660`
- `0x180007dfc`
- `0x180012170`
- `0x1800183f4`
- `0x18001ba70`
- `0x18001ee04`
- `0x18002107c`
- `0x18002178c`
- `0x180021a34`
- `0x180023a34`
- `0x180024030`
- `0x18002778c`
- `0x180027c14`
- `0x1800297f4`
- `0x180029f10`
- `0x18002bd54`
- `0x18002be1c`
- `0x18002ee90`
- `0x180036568`
- `0x180037440`
- `0x180045bd4`
- `0x180071010`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002f2fd`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002f483`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002f795`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002f2fd`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002f483`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002f795`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002f2ef`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002f475`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002f787`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002f2ef`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002f475`
- `msvcp_win!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18002f787`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f6fd`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f6fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f3fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f569`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f3fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f569`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromFullName` at `0x18002f3c5`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromFullName` at `0x18002f3c5`
- `ext-ms-win-resources-languageoverlay-l1-1-7!EnumerateLocalExperiencePacksForExpeditedUpdate` at `0x18002f26b`
- `ext-ms-win-resources-languageoverlay-l1-1-7!EnumerateLocalExperiencePacksForExpeditedUpdate` at `0x18002f26b`

## string_xrefs

- `0x18002f85d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002f066`: `UpdateOrchestratorCurrentVersionRoot`
- `0x18002eeee`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedclient.cpp`
- `0x18002ef1b`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedclient.cpp`
- `0x18002f286`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedclient.cpp`
- `0x18002f3e0`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedclient.cpp`
- `0x18002f132`: `LXP APIs are not present, removing allowedToRerun flag from LXP updater`
- `0x18002f5eb`: `No LXPs currently installed on device`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DockedClient::DoLXPBizCritUpdates(
        DockedClient *this,
        unsigned __int16 *a2,
        int *a3,
        unsigned __int16 **a4)
{
  int v4; // r12d
  __int64 result; // rax
  unsigned int v6; // r13d
  int v7; // r14d
  char v8; // r15
  char *v9; // rbx
  void (__fastcall *v10)(char *, unsigned __int128 *, PCWSTR *, __int128 *, OLECHAR **); // rsi
  _QWORD *System; // rax
  __int64 v12; // rax
  __int64 v13; // rdi
  void (__fastcall *v14)(__int64, unsigned __int128 *, __int64); // rsi
  volatile signed __int32 *v15; // rsi
  volatile signed __int32 *v16; // rsi
  int v17; // eax
  unsigned int v18; // ebx
  const char *v19; // r9
  __int64 v20; // rax
  unsigned __int128 v21; // kr10_16
  __int64 v22; // r13
  __int64 v23; // rdi
  __int64 v24; // rdx
  PWSTR v25; // rbx
  const WCHAR *v26; // rcx
  unsigned int v27; // eax
  unsigned int v28; // edi
  __int64 v29; // r8
  __int64 v30; // rdx
  _QWORD *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rbx
  void (__fastcall *v34)(__int64, PCWSTR *, __int64); // rsi
  volatile signed __int32 *v35; // rbx
  volatile signed __int32 *v36; // rbx
  int v37; // r12d
  const OLECHAR *v38; // rcx
  BSTR v39; // rax
  const char *v40; // r9
  __int64 v41; // rbx
  __int64 v42; // rcx
  unsigned int v43; // [rsp+20h] [rbp-218h]
  char v44[4]; // [rsp+30h] [rbp-208h] BYREF
  unsigned int v45; // [rsp+34h] [rbp-204h]
  OLECHAR *psz[2]; // [rsp+38h] [rbp-200h] BYREF
  __int64 v47; // [rsp+48h] [rbp-1F0h]
  unsigned __int64 v48; // [rsp+50h] [rbp-1E8h]
  char v49; // [rsp+58h] [rbp-1E0h]
  char v50; // [rsp+59h] [rbp-1DFh]
  int v51; // [rsp+5Ah] [rbp-1DEh]
  __int16 v52; // [rsp+5Eh] [rbp-1DAh]
  PWSTR packageFamilyName; // [rsp+60h] [rbp-1D8h] BYREF
  volatile signed __int32 *v54; // [rsp+68h] [rbp-1D0h]
  unsigned __int16 *v55; // [rsp+70h] [rbp-1C8h] BYREF
  volatile signed __int32 *v56; // [rsp+78h] [rbp-1C0h]
  int *v57; // [rsp+80h] [rbp-1B8h]
  unsigned __int16 **v58; // [rsp+88h] [rbp-1B0h]
  UINT32 packageFamilyNameLength; // [rsp+90h] [rbp-1A8h] BYREF
  volatile signed __int32 *v60; // [rsp+98h] [rbp-1A0h]
  PCWSTR packageFullName[2]; // [rsp+A0h] [rbp-198h] BYREF
  __int64 v62; // [rsp+B0h] [rbp-188h]
  unsigned __int64 v63; // [rsp+B8h] [rbp-180h]
  unsigned __int128 v64; // [rsp+C0h] [rbp-178h] BYREF
  __int64 v65; // [rsp+D0h] [rbp-168h]
  __int64 v66; // [rsp+D8h] [rbp-160h]
  __int128 v67; // [rsp+E0h] [rbp-158h] BYREF
  __int64 v68; // [rsp+F0h] [rbp-148h]
  __int64 v69; // [rsp+F8h] [rbp-140h]
  __int64 v70; // [rsp+100h] [rbp-138h] BYREF
  char v71[8]; // [rsp+108h] [rbp-130h] BYREF
  _BYTE v72[120]; // [rsp+110h] [rbp-128h] BYREF
  _BYTE v73[104]; // [rsp+188h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  v58 = a4;
  v57 = a3;
  v55 = a2;
  v4 = 0;
  packageFamilyNameLength = 0;
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedclient.cpp",
      (const char *)0x80004003LL,
      v43);
    return 2147500035LL;
  }
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDA,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedclient.cpp",
      (const char *)0x80004003LL,
      v43);
    return 2147500035LL;
  }
  v6 = 0;
  v45 = 0;
  try
  {
    std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>();
    v7 = 1;
    v8 = 1;
    v44[0] = 1;
    if ( !(unsigned __int8)IsEnumerateLocalExperiencePacksForExpeditedUpdatePresent() )
    {
      v9 = (char *)operator new(0x18u);
      *((_DWORD *)v9 + 2) = 1;
      *((_DWORD *)v9 + 3) = 1;
      *(_QWORD *)v9 = &std::_Ref_count_obj2<Windows::Network>::`vftable';
      *((_QWORD *)v9 + 2) = &Windows::Registry::`vftable';
      v4 = 1;
      v55 = (unsigned __int16 *)(v9 + 16);
      v56 = (volatile signed __int32 *)v9;
      *(_OWORD *)packageFullName = 0;
      v62 = 0;
      v63 = 0;
      std::wstring::_Construct<1,unsigned short const *>(packageFullName, L"\\UScheduler", 11);
      std::wstring::_Append<unsigned short>(packageFullName);
      std::wstring::_Append<unsigned short>(packageFullName);
      v10 = *(void (__fastcall **)(char *, unsigned __int128 *, PCWSTR *, __int128 *, OLECHAR **))(*((_QWORD *)v9 + 2)
                                                                                                 + 56LL);
      LODWORD(psz[0]) = 0;
      v49 = 0;
      v67 = 0;
      v68 = 0;
      v69 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v67, L"allowedToReRun", 14);
      v64 = 0;
      v65 = 0;
      v66 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v64, L"UpdateOrchestratorCurrentVersionRoot", 36);
      v10(v9 + 16, &v64, packageFullName, &v67, psz);
      std::wstring::_Tidy_deallocate(&v64);
      std::wstring::_Tidy_deallocate(&v67);
      if ( v49 != -1 && v49 && v49 != 1 )
        std::wstring::_Tidy_deallocate(psz);
      System = (_QWORD *)SystemInterface::Service::GetSystem(&packageFamilyNameLength);
      v12 = (*(__int64 (__fastcall **)(_QWORD, PWSTR *))(*(_QWORD *)*System + 96LL))(*System, &packageFamilyName);
      v13 = *(_QWORD *)v12;
      v14 = *(void (__fastcall **)(__int64, unsigned __int128 *, __int64))(**(_QWORD **)v12 + 112LL);
      v64 = 0;
      v65 = 0;
      v66 = 0;
      std::wstring::_Construct<1,unsigned short const *>(
        &v64,
        L"LXP APIs are not present, removing allowedToRerun flag from LXP updater",
        71);
      v14(v13, &v64, 1);
      std::wstring::_Tidy_deallocate(&v64);
      v15 = v54;
      if ( v54 )
      {
        if ( _InterlockedExchangeAdd(v54 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
      v16 = v60;
      if ( v60 )
      {
        if ( _InterlockedExchangeAdd(v60 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
          if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        }
      }
      std::wstring::_Tidy_deallocate(packageFullName);
      if ( v9 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(void *))v9)(v9);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
        }
      }
LABEL_56:
      *v57 = v7;
      std::basic_stringbuf<unsigned short>::str(v71, psz);
      v37 = v4 | 2;
      v38 = (const OLECHAR *)psz;
      if ( v48 > 7 )
        v38 = psz[0];
      v39 = SysAllocString(v38);
      v57 = (int *)v39;
      packageFamilyNameLength = v37 | 4;
      if ( !v39 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x15F3,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v40);
      *v58 = v39;
      std::wstring::_Tidy_deallocate(psz);
      *(_QWORD *)&v71[*(int *)(v70 + 4) - 8] = &std::basic_ostringstream<unsigned short>::`vftable';
      *(_DWORD *)((char *)&v69 + *(int *)(v70 + 4) + 4) = *(_DWORD *)(v70 + 4) - 136;
      std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v71);
      std::basic_ostream<unsigned short>::~basic_ostream<unsigned short,std::char_traits<unsigned short>>(v72);
      std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v73);
      return v6;
    }
    v64 = 0;
    v65 = 0;
    v17 = EnumerateLocalExperiencePacksForExpeditedUpdate(
            lambda_3c8ceebe0304d652cbbdf6877aa098e0_::_lambda_invoker_cdecl_,
            0,
            &v64);
    v18 = v17;
    if ( v17 >= 0 )
    {
      v67 = 0;
      v68 = 0;
      v20 = v64;
      v21 = v64;
      v22 = *((_QWORD *)&v64 + 1);
      v23 = -1;
      while ( (_QWORD)v21 != v22 )
      {
        *(_OWORD *)packageFullName = 0;
        v62 = 0;
        v63 = 0;
        if ( *(_QWORD *)(v21 + 24) <= 7u )
          v24 = v21;
        else
          v24 = *(_QWORD *)v21;
        std::wstring::_Construct<2,unsigned short const *>(packageFullName, v24, *(_QWORD *)(v21 + 16));
        packageFamilyNameLength = 65;
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &packageFamilyName,
          0,
          65);
        v25 = packageFamilyName;
        v26 = (const WCHAR *)packageFullName;
        if ( v63 > 7 )
          v26 = packageFullName[0];
        v27 = PackageFamilyNameFromFullName(v26, &packageFamilyNameLength, packageFamilyName);
        if ( v27 )
        {
          v28 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x111,
                  (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedclient.cpp",
                  (const char *)v27,
                  v43);
          if ( v25 )
            CoTaskMemFree(v25);
          std::wstring::_Tidy_deallocate(packageFullName);
          std::vector<Windows::AppInstaller::AppToInstall>::_Tidy(&v67);
          std::vector<std::wstring>::~vector<std::wstring>(&v64);
          *(_QWORD *)&v71[*(int *)(v70 + 4) - 8] = &std::basic_ostringstream<unsigned short>::`vftable';
          *(_DWORD *)((char *)&v69 + *(int *)(v70 + 4) + 4) = *(_DWORD *)(v70 + 4) - 136;
          std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v71);
          std::basic_ostream<unsigned short>::~basic_ostream<unsigned short,std::char_traits<unsigned short>>(v72);
          std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v73);
          return v28;
        }
        *(_OWORD *)psz = 0;
        v47 = 0;
        v48 = 0;
        v29 = -1;
        do
          ++v29;
        while ( v25[v29] );
        std::wstring::_Construct<1,unsigned short const *>(psz, v25, v29);
        v49 = 0;
        v50 = 0;
        v51 = 0;
        v52 = 0;
        v30 = *((_QWORD *)&v67 + 1);
        if ( *((_QWORD *)&v67 + 1) == v68 )
        {
          std::vector<Windows::AppInstaller::AppToInstall>::_Emplace_reallocate<Windows::AppInstaller::AppToInstall>(
            &v67,
            *((_QWORD *)&v67 + 1),
            psz);
        }
        else
        {
          **((_WORD **)&v67 + 1) = psz[0];
          *(OLECHAR **)(v30 + 2) = *(OLECHAR **)((char *)psz + 2);
          *(_DWORD *)(v30 + 10) = *(_DWORD *)((char *)&psz[1] + 2);
          *(_WORD *)(v30 + 14) = HIWORD(psz[1]);
          *(_QWORD *)(v30 + 16) = v47;
          *(_QWORD *)(v30 + 24) = v48;
          v47 = 0;
          v48 = 7;
          LOWORD(psz[0]) = 0;
          *(_BYTE *)(v30 + 32) = 0;
          *(_BYTE *)(v30 + 33) = 0;
          *((_QWORD *)&v67 + 1) += 40LL;
        }
        std::wstring::_Tidy_deallocate(psz);
        if ( v25 )
          CoTaskMemFree(v25);
        std::wstring::_Tidy_deallocate(packageFullName);
        v20 = v64;
        v21 = __PAIR128__(*((unsigned __int64 *)&v64 + 1), (__int64)v21 + 32);
      }
      if ( v20 == *((_QWORD *)&v21 + 1) )
      {
        v31 = (_QWORD *)SystemInterface::Service::GetSystem(&packageFamilyName);
        v32 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(*(_QWORD *)*v31 + 96LL))(*v31, &v55);
        v33 = *(_QWORD *)v32;
        v34 = *(void (__fastcall **)(__int64, PCWSTR *, __int64))(**(_QWORD **)v32 + 112LL);
        *(_OWORD *)packageFullName = 0;
        v62 = 0;
        v63 = 0;
        std::wstring::_Construct<1,unsigned short const *>(
          packageFullName,
          L"No LXPs currently installed on device",
          37);
        v34(v33, packageFullName, 1);
        std::wstring::_Tidy_deallocate(packageFullName);
        v35 = v56;
        if ( v56 )
        {
          if ( _InterlockedExchangeAdd(v56 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
            if ( _InterlockedExchangeAdd(v35 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
          }
        }
        v36 = v54;
        if ( v54 )
        {
          if ( _InterlockedExchangeAdd(v54 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
            if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
          }
        }
        v6 = v45;
      }
      else
      {
        packageFamilyName = (PWSTR)packageFullName;
        v41 = std::vector<Windows::AppInstaller::AppToInstall>::vector<Windows::AppInstaller::AppToInstall>(
                packageFullName,
                &v67);
        *(_OWORD *)psz = 0;
        v47 = 0;
        v48 = 0;
        do
          ++v23;
        while ( aLxp[v23] );
        std::wstring::_Construct<1,unsigned short const *>(psz, L"LXP", v23);
        v6 = DockedClient::PerformExpeditedStoreUpdates(v42, psz, v41, v55, v44, &v70);
        v8 = v44[0];
      }
      std::vector<Windows::AppInstaller::AppToInstall>::_Tidy(&v67);
      std::vector<std::wstring>::~vector<std::wstring>(&v64);
      if ( !v8 )
        v7 = 0;
      goto LABEL_56;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x109,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedclient.cpp",
      (const char *)(unsigned int)v17,
      v43);
    std::vector<std::wstring>::~vector<std::wstring>(&v64);
    *(_QWORD *)&v71[*(int *)(v70 + 4) - 8] = &std::basic_ostringstream<unsigned short>::`vftable';
    *(_DWORD *)((char *)&v69 + *(int *)(v70 + 4) + 4) = *(_DWORD *)(v70 + 4) - 136;
    std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v71);
    std::basic_ostream<unsigned short>::~basic_ostream<unsigned short,std::char_traits<unsigned short>>(v72);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v73);
    result = v18;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x127,
                           (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\d"
                                         "ll\\dockedclient.cpp",
                           v19);
  }
  return result;
}

```

## disassembly

```asm
0x18002ee90  push    rbx
0x18002ee92  push    rsi
0x18002ee93  push    rdi
0x18002ee94  push    r12
0x18002ee96  push    r13
0x18002ee98  push    r14
0x18002ee9a  push    r15
0x18002ee9c  sub     rsp, 200h
0x18002eea3  mov     rax, cs:__security_cookie
0x18002eeaa  xor     rax, rsp
0x18002eead  mov     [rsp+238h+var_48], rax
0x18002eeb5  mov     [rsp+238h+var_1B0], r9
0x18002eebd  mov     rax, r8
0x18002eec0  mov     [rsp+238h+var_1B8], rax
0x18002eec8  mov     [rsp+238h+var_1C8], rdx
0x18002eecd  xor     edi, edi
0x18002eecf  mov     r12d, edi
0x18002eed2  mov     [rsp+238h+packageFamilyNameLength], edi
0x18002eed9  test    rax, rax
0x18002eedc  jnz     short loc_18002EF06
0x18002eede  mov     rcx, [rsp+238h]; this
0x18002eee6  mov     ebx, 80004003h
0x18002eeeb  mov     r9d, ebx; char *
0x18002eeee  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002eef5  mov     edx, 0D9h; void *
0x18002eefa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002eeff  mov     eax, ebx
0x18002ef01  jmp     loc_18002F83A
0x18002ef06  test    r9, r9
0x18002ef09  jnz     short loc_18002EF33
0x18002ef0b  mov     rcx, [rsp+238h]; this
0x18002ef13  mov     ebx, 80004003h
0x18002ef18  mov     r9d, ebx; char *
0x18002ef1b  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002ef22  mov     edx, 0DAh; void *
0x18002ef27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ef2c  mov     eax, ebx
0x18002ef2e  jmp     loc_18002F83A
0x18002ef33  mov     r13d, edi
0x18002ef36  mov     [rsp+238h+var_204], edi
0x18002ef3a  lea     rcx, [rsp+238h+var_138]
0x18002ef42  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18002ef47  nop
0x18002ef48  mov     r14d, 1
0x18002ef4e  mov     r15b, r14b
0x18002ef51  mov     [rsp+238h+var_208], r14b
0x18002ef56  call    IsEnumerateLocalExperiencePacksForExpeditedUpdatePresent
0x18002ef5b  test    al, al
0x18002ef5d  jnz     loc_18002F246
0x18002ef63  lea     ecx, [r14+17h]; Size
0x18002ef67  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ef6c  mov     rbx, rax
0x18002ef6f  mov     [rax+8], r14d
0x18002ef73  mov     [rax+0Ch], r14d
0x18002ef77  lea     rax, ??_7?$_Ref_count_obj2@VNetwork@Windows@@@std@@6B@; const std::_Ref_count_obj2<Windows::Network>::`vftable'
0x18002ef7e  mov     [rbx], rax
0x18002ef81  lea     rdi, [rbx+10h]
0x18002ef85  lea     rax, ??_7Registry@Windows@@6B@; const Windows::Registry::`vftable'
0x18002ef8c  mov     [rdi], rax
0x18002ef8f  mov     r12d, r14d
0x18002ef92  mov     [rsp+238h+var_1C8], rdi
0x18002ef97  mov     [rsp+238h+var_1C0], rbx
0x18002ef9c  xorps   xmm0, xmm0
0x18002ef9f  movups  xmmword ptr [rsp+238h+packageFullName], xmm0
0x18002efa7  xor     r15d, r15d
0x18002efaa  mov     [rsp+238h+var_188], r15
0x18002efb2  mov     [rsp+238h+var_180], r15
0x18002efba  lea     r8d, [r14+0Ah]
0x18002efbe  lea     rdx, aUscheduler; "\\UScheduler"
0x18002efc5  lea     rcx, [rsp+238h+packageFullName]
0x18002efcd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002efd2  nop
0x18002efd3  mov     r8d, r14d
0x18002efd6  lea     rdx, asc_180078694; "\\"
0x18002efdd  lea     rcx, [rsp+238h+packageFullName]; Src
0x18002efe5  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002efea  lea     r8d, [r14+2]
0x18002efee  lea     rdx, aLxp; "LXP"
0x18002eff5  lea     rcx, [rsp+238h+packageFullName]; Src
0x18002effd  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002f002  mov     rax, [rdi]
0x18002f005  mov     rsi, [rax+38h]
0x18002f009  mov     dword ptr [rsp+238h+psz], r15d
0x18002f00e  mov     [rsp+238h+var_1E0], r15b
0x18002f013  xorps   xmm0, xmm0
0x18002f016  movups  [rsp+238h+var_158], xmm0
0x18002f01e  mov     [rsp+238h+var_148], r15
0x18002f026  mov     [rsp+238h+var_140], r15
0x18002f02e  lea     r8d, [r14+0Dh]
0x18002f032  lea     rdx, aAllowedtorerun; "allowedToReRun"
0x18002f039  lea     rcx, [rsp+238h+var_158]
0x18002f041  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002f046  nop
0x18002f047  xorps   xmm0, xmm0
0x18002f04a  movups  [rsp+238h+var_178], xmm0
0x18002f052  mov     [rsp+238h+var_168], r15
0x18002f05a  mov     [rsp+238h+var_160], r15
0x18002f062  lea     r8d, [r14+23h]
0x18002f066  lea     rdx, aUpdateorchestr_1; "UpdateOrchestratorCurrentVersionRoot"
0x18002f06d  lea     rcx, [rsp+238h+var_178]
0x18002f075  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002f07a  nop
0x18002f07b  lea     rax, [rsp+238h+psz]
0x18002f080  mov     [rsp+238h+var_218], rax
0x18002f085  lea     r9, [rsp+238h+var_158]
0x18002f08d  lea     r8, [rsp+238h+packageFullName]
0x18002f095  lea     rdx, [rsp+238h+var_178]
0x18002f09d  mov     rcx, rdi
0x18002f0a0  mov     rax, rsi
0x18002f0a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0a8  nop
0x18002f0a9  lea     rcx, [rsp+238h+var_178]
0x18002f0b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f0b6  nop
0x18002f0b7  lea     rcx, [rsp+238h+var_158]
0x18002f0bf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f0c4  nop
0x18002f0c5  movsx   rax, [rsp+238h+var_1E0]
0x18002f0cb  add     rax, r14
0x18002f0ce  jz      short loc_18002F0E4
0x18002f0d0  sub     rax, r14
0x18002f0d3  jz      short loc_18002F0E4
0x18002f0d5  cmp     rax, r14
0x18002f0d8  jz      short loc_18002F0E4
0x18002f0da  lea     rcx, [rsp+238h+psz]
0x18002f0df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f0e4  lea     rcx, [rsp+238h+packageFamilyNameLength]
0x18002f0ec  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18002f0f1  nop
0x18002f0f2  mov     rcx, [rax]
0x18002f0f5  mov     rax, [rcx]
0x18002f0f8  lea     rdx, [rsp+238h+packageFamilyName]
0x18002f0fd  mov     rax, [rax+60h]
0x18002f101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f106  nop
0x18002f107  mov     rdi, [rax]
0x18002f10a  mov     rax, [rdi]
0x18002f10d  mov     rsi, [rax+70h]
0x18002f111  xorps   xmm0, xmm0
0x18002f114  movups  [rsp+238h+var_178], xmm0
0x18002f11c  mov     [rsp+238h+var_168], r15
0x18002f124  mov     [rsp+238h+var_160], r15
0x18002f12c  mov     r8d, 47h ; 'G'
0x18002f132  lea     rdx, aLxpApisAreNotP; "LXP APIs are not present, removing allo"...
0x18002f139  lea     rcx, [rsp+238h+var_178]
0x18002f141  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002f146  nop
0x18002f147  mov     r8d, r14d
0x18002f14a  lea     rdx, [rsp+238h+var_178]
0x18002f152  mov     rcx, rdi
0x18002f155  mov     rax, rsi
0x18002f158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f15d  nop
0x18002f15e  lea     rcx, [rsp+238h+var_178]
0x18002f166  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f16b  nop
0x18002f16c  mov     rsi, [rsp+238h+var_1D0]
0x18002f171  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002f175  test    rsi, rsi
0x18002f178  jz      short loc_18002F1AE
0x18002f17a  mov     eax, edi
0x18002f17c  lock xadd [rsi+8], eax
0x18002f181  add     eax, edi
0x18002f183  jnz     short loc_18002F1AE
0x18002f185  mov     rax, [rsi]
0x18002f188  mov     rcx, rsi
0x18002f18b  mov     rax, [rax]
0x18002f18e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f193  mov     eax, edi
0x18002f195  lock xadd [rsi+0Ch], eax
0x18002f19a  add     eax, edi
0x18002f19c  jnz     short loc_18002F1AE
0x18002f19e  mov     rax, [rsi]
0x18002f1a1  mov     rcx, rsi
0x18002f1a4  mov     rax, [rax+8]
0x18002f1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1ad  nop
0x18002f1ae  mov     rsi, [rsp+238h+var_1A0]
0x18002f1b6  test    rsi, rsi
0x18002f1b9  jz      short loc_18002F1EF
0x18002f1bb  mov     eax, edi
0x18002f1bd  lock xadd [rsi+8], eax
0x18002f1c2  add     eax, edi
0x18002f1c4  jnz     short loc_18002F1EF
0x18002f1c6  mov     rax, [rsi]
0x18002f1c9  mov     rcx, rsi
0x18002f1cc  mov     rax, [rax]
0x18002f1cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1d4  mov     eax, edi
0x18002f1d6  lock xadd [rsi+0Ch], eax
0x18002f1db  add     eax, edi
0x18002f1dd  jnz     short loc_18002F1EF
0x18002f1df  mov     rax, [rsi]
0x18002f1e2  mov     rcx, rsi
0x18002f1e5  mov     rax, [rax+8]
0x18002f1e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1ee  nop
0x18002f1ef  lea     rcx, [rsp+238h+packageFullName]
0x18002f1f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f1fc  nop
0x18002f1fd  test    rbx, rbx
0x18002f200  jz      loc_18002F6CB
0x18002f206  mov     eax, edi
0x18002f208  lock xadd [rbx+8], eax
0x18002f20d  add     eax, edi
0x18002f20f  jnz     loc_18002F6CB
0x18002f215  mov     rax, [rbx]
0x18002f218  mov     rcx, rbx
0x18002f21b  mov     rax, [rax]
0x18002f21e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f223  mov     eax, edi
0x18002f225  lock xadd [rbx+0Ch], eax
0x18002f22a  add     eax, edi
0x18002f22c  jnz     loc_18002F6CB
0x18002f232  mov     rax, [rbx]
0x18002f235  mov     rcx, rbx
0x18002f238  mov     rax, [rax+8]
0x18002f23c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f241  jmp     loc_18002F6CB
0x18002f246  xorps   xmm0, xmm0
0x18002f249  movdqu  [rsp+238h+var_178], xmm0
0x18002f252  mov     [rsp+238h+var_168], rdi
0x18002f25a  lea     r8, [rsp+238h+var_178]
0x18002f262  xor     edx, edx
0x18002f264  lea     rcx, _lambda_3c8ceebe0304d652cbbdf6877aa098e0____lambda_invoker_cdecl_
0x18002f26b  call    cs:__imp_EnumerateLocalExperiencePacksForExpeditedUpdate
0x18002f271  mov     ebx, eax
0x18002f273  test    eax, eax
0x18002f275  jns     loc_18002F30A
0x18002f27b  mov     rcx, [rsp+238h]; this
0x18002f283  mov     r9d, eax; char *
0x18002f286  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002f28d  mov     edx, 109h; void *
0x18002f292  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f297  nop
0x18002f298  lea     rcx, [rsp+238h+var_178]
0x18002f2a0  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x18002f2a5  nop
0x18002f2a6  mov     rcx, [rsp+238h+var_138]
0x18002f2ae  movsxd  rax, dword ptr [rcx+4]
0x18002f2b2  lea     rdx, ??_7?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_ostringstream<ushort>::`vftable'
0x18002f2b9  mov     [rsp+rax+238h+var_138], rdx
0x18002f2c1  mov     rax, [rsp+238h+var_138]
0x18002f2c9  movsxd  rcx, dword ptr [rax+4]
0x18002f2cd  lea     edx, [rcx-88h]
0x18002f2d3  mov     dword ptr [rsp+rcx+238h+var_140+4], edx
0x18002f2da  lea     rcx, [rsp+238h+var_130]
0x18002f2e2  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x18002f2e7  lea     rcx, [rsp+238h+var_128]
0x18002f2ef  call    cs:__imp_??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ostream<ushort>::~basic_ostream<ushort,std::char_traits<ushort>>(void)
0x18002f2f5  lea     rcx, [rsp+238h+var_B0]
0x18002f2fd  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x18002f303  mov     eax, ebx
0x18002f305  jmp     loc_18002F83A
0x18002f30a  xorps   xmm0, xmm0
0x18002f30d  movdqu  [rsp+238h+var_158], xmm0
0x18002f316  mov     [rsp+238h+var_148], rdi
0x18002f31e  mov     rax, qword ptr [rsp+238h+var_178]
0x18002f326  mov     rsi, rax
0x18002f329  mov     rcx, qword ptr [rsp+238h+var_178+8]
0x18002f331  mov     r13, rcx
0x18002f334  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002f338  cmp     rsi, r13
0x18002f33b  jz      loc_18002F596
0x18002f341  xorps   xmm0, xmm0
0x18002f344  movups  xmmword ptr [rsp+238h+packageFullName], xmm0
0x18002f34c  xor     eax, eax
0x18002f34e  mov     [rsp+238h+var_188], rax
0x18002f356  mov     [rsp+238h+var_180], rax
0x18002f35e  cmp     qword ptr [rsi+18h], 7
0x18002f363  jbe     short loc_18002F36A
0x18002f365  mov     rdx, [rsi]
0x18002f368  jmp     short loc_18002F36D
0x18002f36a  mov     rdx, rsi
0x18002f36d  mov     r8, [rsi+10h]
0x18002f371  lea     rcx, [rsp+238h+packageFullName]
0x18002f379  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18002f37e  nop
0x18002f37f  mov     [rsp+238h+packageFamilyNameLength], 41h ; 'A'
0x18002f38a  xor     edx, edx
0x18002f38c  lea     r8d, [rdx+41h]
0x18002f390  lea     rcx, [rsp+238h+packageFamilyName]
0x18002f395  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002f39a  nop
0x18002f39b  mov     rbx, [rsp+238h+packageFamilyName]
0x18002f3a0  lea     rcx, [rsp+238h+packageFullName]
0x18002f3a8  cmp     [rsp+238h+var_180], 7
0x18002f3b1  cmova   rcx, [rsp+238h+packageFullName]; packageFullName
0x18002f3ba  mov     r8, rbx; packageFamilyName
0x18002f3bd  lea     rdx, [rsp+238h+packageFamilyNameLength]; packageFamilyNameLength
0x18002f3c5  call    cs:__imp_PackageFamilyNameFromFullName
0x18002f3cb  xor     ecx, ecx
0x18002f3cd  test    eax, eax
0x18002f3cf  jz      loc_18002F490
0x18002f3d5  mov     rcx, [rsp+238h]; this
0x18002f3dd  mov     r9d, eax; char *
0x18002f3e0  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002f3e7  mov     edx, 111h; void *
0x18002f3ec  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002f3f1  mov     edi, eax
  ... truncated ...
```
