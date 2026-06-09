# NotificationPlatform::LoadAppsFromRegistry(bool,bool)

- ea: `0x18000e620`
- end: `0x18000f8d2`
- name: `?LoadAppsFromRegistry@NotificationPlatform@@AEAAJ_N0@Z`
- size: `4786`
- prototype: `__int64 __fastcall(NotificationPlatform *__hidden this, bool, bool)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001953c`
- `0x180047440`

## callees

- `0x180004e38`
- `0x18000de40`
- `0x18000e090`
- `0x18000e620`
- `0x18000f8d8`
- `0x18000f9d4`
- `0x180010560`
- `0x180010b90`
- `0x180011618`
- `0x18002db0c`
- `0x18002ee38`
- `0x18004e750`
- `0x180067e28`
- `0x18007a74c`
- `0x180081910`
- `0x1800823a8`
- `0x1800b9a20`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f1a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f2be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f49b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f514`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f1a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f2be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f49b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f514`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f1b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f2cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f4a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f522`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f1b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f2cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f4a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f522`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e760`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000eea2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f0df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f2a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f5ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f6b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e760`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000eea2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f0df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f2a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f5ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f6b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000eab9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000eb39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000eec8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ef51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000eab9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000eb39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000eec8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ef51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f029`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f210`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f32f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f029`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f210`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f32f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NotificationPlatform::LoadAppsFromRegistry(
        struct IPlatformConfigurationProvider **this,
        char a2,
        char a3)
{
  NotificationPlatform *v3; // r13
  void *v4; // r15
  struct IPlatformConfigurationProvider *v5; // rcx
  int PreinstalledOnSystemUserRegistrationInformation; // eax
  unsigned int v7; // ebx
  __int64 i; // rax
  __int16 *v9; // rdx
  __int64 v10; // r12
  unsigned int v11; // ecx
  unsigned int j; // eax
  __int16 *v13; // rdi
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rsi
  unsigned int v16; // r14d
  unsigned __int64 v17; // r14
  int v18; // esi
  int v19; // eax
  unsigned int v20; // edi
  unsigned int k; // ebx
  __int64 v22; // rax
  int v23; // ecx
  __int64 v24; // rdx
  int v25; // eax
  __int64 v26; // rdx
  struct INotificationHandlerSettings *v27; // rbx
  __int16 *v28; // rsi
  __int16 *v29; // r13
  __int16 *v30; // r12
  NotificationHandler *v31; // rcx
  NotificationHandler *v32; // rax
  NotificationHandler *v33; // rax
  NotificationHandler *v34; // rdi
  _QWORD *v35; // r15
  unsigned __int64 v36; // r9
  unsigned __int64 v37; // r14
  unsigned __int64 v38; // r8
  int v39; // esi
  __int64 v40; // rdx
  NotificationHandler v41; // rcx
  NotificationHandler v42; // rcx
  NotificationHandler v43; // rcx
  unsigned __int64 v44; // r14
  unsigned __int64 v45; // rbx
  unsigned __int64 v46; // r8
  unsigned __int64 v47; // r14
  unsigned __int64 v48; // rbx
  unsigned __int64 v49; // r8
  _WORD *v50; // rax
  _WORD *v51; // rdx
  __int16 v52; // ax
  _WORD *v53; // rcx
  _WORD *v54; // rax
  int v55; // edx
  _WORD *v56; // rdx
  unsigned __int64 v57; // rcx
  __int16 v58; // ax
  _WORD *v59; // rcx
  __int64 v60; // rdi
  __int64 (__fastcall *v61)(__int64, char *, _QWORD **); // rbx
  int v62; // eax
  int SettingObjectFromMask; // eax
  _QWORD *v64; // rdi
  __int64 (__fastcall *v65)(_QWORD *, struct IStream **); // rbx
  int v66; // eax
  struct IStream *v67; // r14
  struct INotificationHandlerSettings *v68; // r15
  const unsigned __int16 *v69; // rdi
  const unsigned __int16 *v70; // rsi
  const unsigned __int16 *v71; // r12
  NotificationHandler *v72; // rax
  NotificationHandler *v73; // rbx
  NotificationHandler *v74; // rdx
  int v75; // eax
  struct IStream *v76; // rcx
  _QWORD *v77; // rcx
  NotificationHandler *v78; // rdx
  unsigned int v79; // ebx
  __int64 v81; // rsi
  struct INotificationHandlerSettings *v82; // rcx
  NotificationHandler *v83; // rcx
  void (__stdcall *v84)(GUID, void *); // rax
  _WORD *v85; // rdx
  unsigned __int64 v86; // rcx
  __int16 v87; // ax
  _WORD *v88; // rcx
  void (__stdcall *v89)(GUID, void *); // rax
  _WORD *v90; // rdx
  unsigned __int64 v91; // rcx
  __int16 v92; // ax
  _WORD *v93; // rcx
  unsigned __int64 v94; // r15
  void (__stdcall *v95)(GUID, void *); // rax
  struct IPlatformConfigurationProvider *v96; // rdi
  __int64 (__fastcall *v97)(char *, char *, _QWORD **); // rbx
  int v98; // eax
  _QWORD *v99; // rbx
  __int64 (__fastcall *v100)(_QWORD *, LPVOID *); // rdi
  int v101; // eax
  unsigned __int16 *v102; // rax
  int v103; // ecx
  int v104; // edx
  void *v105; // rbx
  HANDLE v106; // rax
  unsigned __int64 v108; // rsi
  void (__stdcall *v109)(GUID, void *); // rax
  _QWORD *v110; // rcx
  struct INotificationHandlerSettings *v111; // rcx
  NotificationHandler *v112; // rcx
  void *v113; // rdi
  HANDLE v114; // rax
  unsigned __int64 v115; // rsi
  void (__stdcall *v116)(GUID, void *); // rax
  void *v117; // rbx
  HANDLE ProcessHeap; // rax
  void *v119; // rbx
  HANDLE v120; // rax
  _QWORD *v121; // rcx
  __int64 v122; // rdx
  _QWORD *v123; // rcx
  struct INotificationHandlerSettings *v124; // rcx
  NotificationHandler *v125; // rcx
  int v126; // eax
  _QWORD *v127; // rcx
  struct INotificationHandlerSettings *v128; // rcx
  NotificationHandler *v129; // rcx
  int v130; // eax
  NotificationHandler *v131; // rdx
  int v132; // eax
  bool v133; // zf
  __int64 v134; // rdx
  int v135; // [rsp+20h] [rbp-99h]
  int v136; // [rsp+20h] [rbp-99h]
  int v137; // [rsp+20h] [rbp-99h]
  NotificationHandler *v138; // [rsp+50h] [rbp-69h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-61h] BYREF
  struct INotificationHandlerSettings *v140; // [rsp+60h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-51h] BYREF
  __int64 v142; // [rsp+70h] [rbp-49h]
  __int64 v143; // [rsp+78h] [rbp-41h]
  unsigned int v144; // [rsp+80h] [rbp-39h] BYREF
  struct IStream *v145; // [rsp+88h] [rbp-31h] BYREF
  int v146; // [rsp+90h] [rbp-29h]
  char *v147; // [rsp+98h] [rbp-21h] BYREF
  LPVOID *p_lpMem; // [rsp+A0h] [rbp-19h] BYREF
  char v149; // [rsp+A8h] [rbp-11h]
  unsigned __int64 v150; // [rsp+B0h] [rbp-9h]
  __int64 v151; // [rsp+B8h] [rbp-1h]
  NotificationHandler *v152; // [rsp+C0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  _QWORD *v157; // [rsp+138h] [rbp+7Fh] BYREF

  v3 = (NotificationPlatform *)this;
  v4 = 0;
  v144 = 0;
  lpMem = 0;
  p_lpMem = &lpMem;
  v149 = 1;
  v5 = this[42];
  if ( a3 )
  {
    PreinstalledOnSystemUserRegistrationInformation = WpnGetPreinstalledOnSystemUserRegistrationInformation(
                                                        v5,
                                                        &v144,
                                                        (struct WPN_REGISTRATION_INFO **)&lpMem);
  }
  else
  {
    v133 = a2 == 0;
    v134 = -2147483647;
    if ( v133 )
      v134 = -2147483646;
    PreinstalledOnSystemUserRegistrationInformation = WpnEnumerateRegistrationInformation(
                                                        v5,
                                                        (HKEY)v134,
                                                        &v144,
                                                        (struct WPN_REGISTRATION_INFO **)&lpMem);
  }
  v7 = PreinstalledOnSystemUserRegistrationInformation;
  if ( PreinstalledOnSystemUserRegistrationInformation )
  {
    if ( PreinstalledOnSystemUserRegistrationInformation < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x390,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
        (const char *)(unsigned int)PreinstalledOnSystemUserRegistrationInformation,
        v135);
    goto LABEL_219;
  }
  for ( i = 0; ; i = (unsigned int)(v146 + 1) )
  {
    v9 = &_ImageBase;
    v146 = i;
    if ( (unsigned int)i >= v144 )
    {
      if ( !a3 )
      {
        if ( a2 )
        {
          v130 = WpnCleanupPreinstalledRegistrationInformation(*((struct IPlatformConfigurationProvider **)v3 + 42));
          if ( v130 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x3F4,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
              (const char *)(unsigned int)v130,
              v135);
        }
      }
      v149 = 0;
      lambda_d5c261f7a769db825fc46774a27f5aa0_::operator()(&p_lpMem, v9);
      return 0;
    }
    pv = 0;
    v142 = -1;
    v143 = -1;
    v10 = 4632 * i;
    v151 = 4632 * i;
    v11 = *((_DWORD *)lpMem + 1158 * i + 129) & 0xF0000000;
    for ( j = 0; ; ++j )
    {
      if ( j >= 4 )
      {
        v16 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x182,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\databasehelpers.cpp",
          (const char *)0x80070057LL,
          v135);
        goto LABEL_252;
      }
      if ( v11 == dword_18015C4E8[4 * j] )
        break;
    }
    v13 = (__int16 *)*(&c_appTypeMap + 2 * (int)j);
    if ( v13 )
    {
      v14 = -1;
      do
        ++v14;
      while ( v13[v14] );
      v15 = v14 + 1;
      if ( v14 + 1 < v14 || (v157 = 0, !is_mul_ok(v15, 2u)) )
      {
        v16 = -2147024362;
        goto LABEL_15;
      }
      v50 = CoTaskMemAlloc(2 * v15);
      v51 = v50;
      if ( !v50 )
      {
        v16 = -2147024882;
        goto LABEL_16;
      }
      v16 = 0;
      v4 = v50;
      *v50 = 0;
      if ( v14 != -1 )
      {
        if ( v14 > 0x7FFFFFFE || v15 > 0x7FFFFFFF )
        {
          *v50 = 0;
        }
        else
        {
          do
          {
            if ( !v14 )
              break;
            v52 = *v13;
            if ( !*v13 )
              break;
            ++v13;
            *v51++ = v52;
            --v14;
            --v15;
          }
          while ( v15 );
          v53 = v51 - 1;
          if ( v15 )
            v53 = v51;
          *v53 = 0;
        }
      }
LABEL_15:
      if ( (v16 & 0x80000000) != 0 )
      {
LABEL_16:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17C,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\databasehelpers.cpp",
          (const char *)v16,
          v135);
        if ( v4 )
          CoTaskMemFree(v4);
LABEL_252:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x397,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
          (const char *)v16,
          v136);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
        v117 = lpMem;
        if ( lpMem )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v117);
        }
        return v16;
      }
    }
    pv = v4;
    v17 = *(_QWORD *)((char *)lpMem + v10 + 520);
    v150 = v17;
    v4 = 0;
    v138 = 0;
    v140 = 0;
    if ( (*((_BYTE *)lpMem + v10 + 528) & 2) != 0 )
    {
      v157 = 0;
      v60 = *((_QWORD *)v3 + 18);
      v61 = *(__int64 (__fastcall **)(__int64, char *, _QWORD **))(*(_QWORD *)(v60 + 32) + 192LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v157);
      v62 = v61(v60 + 32, (char *)lpMem + v10, &v157);
      if ( v62 < 0 )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x3C6,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
          (const char *)(unsigned int)v62,
          v135);
      }
      else
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v140);
        SettingObjectFromMask = WpnDatabaseHelpers::GetSettingObjectFromMask(
                                  *(unsigned int *)((char *)lpMem + v10 + 516),
                                  (char *)lpMem + v10,
                                  100695808,
                                  &v140);
        v7 = SettingObjectFromMask;
        if ( SettingObjectFromMask < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3AF,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
            (const char *)(unsigned int)SettingObjectFromMask,
            v135);
          v110 = v157;
          if ( v157 )
          {
            v157 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v110 + 16LL))(v110);
          }
          v111 = v140;
          if ( v140 )
          {
            v140 = 0;
            (*(void (__fastcall **)(struct INotificationHandlerSettings *))(*(_QWORD *)v111 + 16LL))(v111);
          }
          v112 = v138;
          if ( v138 )
          {
            v138 = 0;
            (*((void (__fastcall **)(NotificationHandler *))*v112 + 2))(v112);
          }
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          v142 = 0;
          v143 = 0;
          goto LABEL_219;
        }
        v145 = 0;
        v64 = v157;
        v65 = *(__int64 (__fastcall **)(_QWORD *, struct IStream **))(*v157 + 80LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v145);
        v66 = v65(v64, &v145);
        v7 = v66;
        if ( v66 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3B3,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
            (const char *)(unsigned int)v66,
            v135);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v145);
          goto LABEL_304;
        }
        v67 = v145;
        v68 = v140;
        v69 = (const unsigned __int16 *)((char *)lpMem + v10);
        v70 = 0;
        if ( (*(_DWORD *)((_BYTE *)lpMem + v10 + 516) & 0x10000000) == 0 )
          v70 = (const unsigned __int16 *)((char *)lpMem + v10 + 260);
        v71 = (const unsigned __int16 *)pv;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
        v138 = 0;
        v72 = (NotificationHandler *)operator new(0xE0u, (const struct std::nothrow_t *)std::nothrow);
        if ( !v72 )
        {
          v20 = -2147024882;
          goto LABEL_197;
        }
        v73 = NotificationHandler::NotificationHandler(v72);
        v20 = NotificationHandler::RuntimeClassInitialize(v73, v69, v71, v70, v68, 0, v67, v150, 0, 0);
        if ( (v20 & 0x80000000) != 0 )
        {
          if ( v73 )
            (*((void (__fastcall **)(NotificationHandler *))*v73 + 2))(v73);
LABEL_197:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3C0,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
            (const char *)v20,
            v135);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v145);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v157);
LABEL_198:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v140);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
          v105 = lpMem;
          if ( lpMem )
          {
            v106 = GetProcessHeap();
            HeapFree(v106, 0, v105);
          }
          return v20;
        }
        if ( v73 )
          (*((void (__fastcall **)(NotificationHandler *))*v73 + 1))(v73);
        v138 = v73;
        if ( v73 )
        {
          (*((void (__fastcall **)(NotificationHandler *))*v73 + 2))(v73);
          v73 = v138;
        }
        v74 = v73 + 4;
        v4 = 0;
        if ( !v73 )
          v74 = 0;
        v75 = (*(__int64 (__fastcall **)(__int64, NotificationHandler *))(*(_QWORD *)(*((_QWORD *)v3 + 18) + 32LL)
                                                                        + 200LL))(
                *((_QWORD *)v3 + 18) + 32LL,
                v74);
        if ( v75 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x3C2,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
            (const char *)(unsigned int)v75,
            v135);
        v76 = v145;
        if ( v145 )
        {
          v145 = 0;
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v76 + 16LL))(v76);
        }
      }
      goto LABEL_120;
    }
    v18 = *(_DWORD *)((char *)lpMem + v10 + 516);
    v147 = (char *)lpMem + v10;
    v157 = 0;
    v19 = Microsoft::WRL::Details::MakeAndInitialize<NotificationSettings,NotificationSettings,unsigned short const * &>(
            &v157,
            &v147);
    v20 = v19;
    if ( v19 < 0 )
    {
      v26 = 319;
LABEL_307:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\databasehelpers.cpp",
        (const char *)(unsigned int)v19,
        v135);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v157);
LABEL_263:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3CE,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
        (const char *)v20,
        v137);
      goto LABEL_198;
    }
    for ( k = 0; k < 0x18; ++k )
    {
      v22 = 2LL * (int)k;
      v23 = qword_18015C368[v22];
      if ( (v23 & 0x7F7FFFF) != 0 )
      {
        v24 = *(__int64 *)((char *)&c_settingMap + v22 * 8);
        if ( (v23 & v18) != 0 )
        {
          v25 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64))(v157[4] + 40LL))(v157 + 4, v24, 1);
          v20 = v25;
          if ( v25 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x149,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\databasehelpers.cpp",
              (const char *)(unsigned int)v25,
              v135);
            v121 = v157;
            if ( v157 )
            {
              v157 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v121 + 16LL))(v121);
            }
            goto LABEL_263;
          }
        }
        else
        {
          v19 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD))(v157[4] + 40LL))(v157 + 4, v24, 0);
          v20 = v19;
          if ( v19 < 0 )
          {
            v26 = 333;
            goto LABEL_307;
          }
        }
      }
    }
    v27 = (struct INotificationHandlerSettings *)(v157 + 4);
    if ( !v157 )
      v27 = 0;
    v140 = v27;
    v28 = (__int16 *)((char *)lpMem + v10);
    v29 = 0;
    if ( (*(_DWORD *)((_BYTE *)lpMem + v10 + 516) & 0x10000000) == 0 )
      v29 = (__int16 *)((char *)lpMem + v10 + 260);
    v30 = (__int16 *)pv;
    v31 = v138;
    if ( v138 )
    {
      v138 = 0;
      (*((void (__fastcall **)(NotificationHandler *))*v31 + 2))(v31);
    }
    v138 = 0;
    v32 = (NotificationHandler *)operator new(0xE0u, (const struct std::nothrow_t *)std::nothrow);
    if ( !v32 )
    {
      v39 = -2147024882;
      goto LABEL_258;
    }
    v33 = NotificationHandler::NotificationHandler(v32);
    v34 = v33;
    v152 = v33;
    v35 = v33 + 6;
    if ( !v28 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v33 + 6);
      goto LABEL_48;
    }
    v36 = -1;
    do
      ++v36;
    while ( v28[v36] );
    v147 = (char *)v36;
    v37 = v36 + 1;
    if ( v36 + 1 < v36 )
    {
LABEL_43:
      v39 = -2147024362;
      goto LABEL_44;
    }
    v38 = (unsigned __int64)v33[8];
    if ( v38 == -1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(v33 + 6);
      if ( *v35 )
        v38 = v35[1] + 1LL;
      else
        v38 = 0;
      v35[2] = v38;
    }
    if ( v38 )
    {
      LODWORD(v157) = 0;
      if ( v37 <= v38 )
        goto LABEL_91;
      v157 = 0;
      v94 = 2 * v38;
      if ( !is_mul_ok(v38, 2u) )
        goto LABEL_43;
      if ( v38 > 0x800 )
        v94 = v38 + 2048;
      if ( v37 > v94 )
        v94 = v37;
      v95 = (void (__stdcall *)(GUID, void *))CoTaskMemRealloc(v34[6], 2 * v94);
      if ( !v95 )
      {
        v39 = -2147024882;
        goto LABEL_45;
      }
      LODWORD(v157) = 0;
      v34[8] = (NotificationHandler)v94;
      v35 = v34 + 6;
      v34[6] = v95;
    }
    else
    {
      v157 = 0;
      if ( !is_mul_ok(v37, 2u) )
        goto LABEL_43;
      v54 = CoTaskMemAlloc(2 * v37);
      if ( v54 )
      {
        v55 = 0;
        v35[2] = v37;
        *v35 = v54;
        *v54 = 0;
      }
      else
      {
        v55 = -2147024882;
      }
      LODWORD(v157) = v55;
      if ( v55 < 0 )
      {
        v39 = (int)v157;
LABEL_45:
        v40 = 35;
LABEL_46:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v40,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notificationhandler.cpp",
          (const char *)(unsigned int)v39,
          v135);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v152);
LABEL_258:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3DA,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
          (const char *)(unsigned int)v39,
          v135);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v140);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
        v119 = lpMem;
        if ( lpMem )
        {
          v120 = GetProcessHeap();
          HeapFree(v120, 0, v119);
        }
        return (unsigned int)v39;
      }
    }
    v36 = (unsigned __int64)v147;
LABEL_91:
    if ( v37 )
    {
      v56 = (_WORD *)*v35;
      if ( v37 > 0x7FFFFFFF )
      {
        *v56 = 0;
      }
      else
      {
        if ( v36 > 0x7FFFFFFE )
        {
          *v56 = 0;
          v35[1] = v36;
          v39 = (int)v157;
          goto LABEL_44;
        }
        v57 = v36;
        do
        {
          if ( !v57 )
            break;
          v58 = *v28;
          if ( !*v28 )
            break;
          ++v28;
          *v56++ = v58;
          --v57;
          --v37;
        }
        while ( v37 );
        v59 = v56 - 1;
        if ( v37 )
          v59 = v56;
        *v59 = 0;
      }
    }
    v35[1] = v36;
    v39 = (int)v157;
LABEL_44:
    if ( v39 < 0 )
      goto LABEL_45;
    v17 = v150;
LABEL_48:
    if ( (char *)v34[9] != (char *)v27 )
    {
      if ( v27 )
        (*(void (__fastcall **)(struct INotificationHandlerSettings *))(*(_QWORD *)v27 + 8LL))(v27);
      v41 = v34[9];
      v34[9] = (NotificationHandler)v27;
      if ( v41 )
        (*(void (__fastcall **)(NotificationHandler))(*(_QWORD *)v41 + 16LL))(v41);
    }
    v42 = v34[10];
    v39 = 0;
    if ( v42 )
    {
      v34[10] = 0;
      (*(void (__fastcall **)(NotificationHandler))(*(_QWORD *)v42 + 16LL))(v42);
    }
    v43 = v34[11];
    if ( v43 )
    {
      v34[11] = 0;
      (*(void (__fastcall **)(NotificationHandler))(*(_QWORD *)v43 + 16LL))(v43);
    }
    v34[21] = (NotificationHandler)v17;
    if ( !v30 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v34 + 12);
      goto LABEL_66;
    }
    v44 = -1;
    do
      ++v44;
    while ( v30[v44] );
    v45 = v44 + 1;
    if ( v44 + 1 < v44 )
    {
LABEL_64:
      v39 = -2147024362;
      goto LABEL_65;
    }
    v46 = (unsigned __int64)v34[14];
    if ( v46 == -1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(v34 + 12);
      if ( v34[12] )
        v46 = (unsigned __int64)v34[13] + 1;
      else
        v46 = 0;
      v34[14] = (NotificationHandler)v46;
    }
    if ( v46 )
    {
      if ( v45 > v46 )
      {
        v157 = 0;
        v108 = 2 * v46;
        if ( !is_mul_ok(v46, 2u) )
          goto LABEL_64;
        if ( v46 > 0x800 )
          v108 = v46 + 2048;
        if ( v45 > v108 )
          v108 = v44 + 1;
        v109 = (void (__stdcall *)(GUID, void *))CoTaskMemRealloc(v34[12], 2 * v108);
        if ( !v109 )
        {
          v39 = -2147024882;
LABEL_240:
          v40 = 40;
          goto LABEL_46;
        }
        LODWORD(v157) = 0;
        v34[14] = (NotificationHandler)v108;
        v34[12] = v109;
        v39 = 0;
      }
    }
    else
    {
      v157 = 0;
      if ( !is_mul_ok(v45, 2u) )
        goto LABEL_64;
      v84 = (void (__stdcall *)(GUID, void *))CoTaskMemAlloc(2 * v45);
      if ( v84 )
      {
        v34[14] = (NotificationHandler)v45;
        v34[12] = v84;
        *(_WORD *)v84 = 0;
      }
      else
      {
        v39 = -2147024882;
      }
      if ( v39 < 0 )
        goto LABEL_240;
    }
    if ( v44 == -1 )
      goto LABEL_157;
    v85 = v34[12];
    if ( v45 > 0x7FFFFFFF )
    {
      *v85 = 0;
LABEL_157:
      v34[13] = (NotificationHandler)v44;
      goto LABEL_65;
    }
    if ( v44 <= 0x7FFFFFFE )
    {
      v86 = v44;
      do
      {
        if ( !v86 )
          break;
        v87 = *v30;
        if ( !*v30 )
          break;
        ++v30;
        *v85++ = v87;
        --v86;
        --v45;
      }
      while ( v45 );
      v88 = v85 - 1;
      if ( v45 )
        v88 = v85;
      *v88 = 0;
      goto LABEL_157;
    }
    *v85 = 0;
    v34[13] = (NotificationHandler)v44;
LABEL_65:
    if ( v39 < 0 )
      goto LABEL_240;
LABEL_66:
    if ( !v29 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v34 + 15);
      goto LABEL_75;
    }
    v47 = -1;
    do
      ++v47;
    while ( v29[v47] );
    v48 = v47 + 1;
    if ( v47 + 1 < v47 )
    {
LABEL_73:
      v39 = -2147024362;
      goto LABEL_74;
    }
    v49 = (unsigned __int64)v34[17];
    if ( v49 == -1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(v34 + 15);
      if ( v34[15] )
        v49 = (unsigned __int64)v34[16] + 1;
      else
        v49 = 0;
      v34[17] = (NotificationHandler)v49;
    }
    if ( v49 )
    {
      v39 = 0;
      if ( v48 > v49 )
      {
        v157 = 0;
        v115 = 2 * v49;
        if ( !is_mul_ok(v49, 2u) )
          goto LABEL_73;
        if ( v49 > 0x800 )
          v115 = v49 + 2048;
        if ( v48 > v115 )
          v115 = v47 + 1;
        v116 = (void (__stdcall *)(GUID, void *))CoTaskMemRealloc(v34[15], 2 * v115);
        if ( !v116 )
        {
          v39 = -2147024882;
LABEL_243:
          v40 = 41;
          goto LABEL_46;
        }
        LODWORD(v157) = 0;
        v34[17] = (NotificationHandler)v115;
        v34[15] = v116;
        v39 = 0;
      }
    }
    else
    {
      v157 = 0;
      if ( !is_mul_ok(v48, 2u) )
        goto LABEL_73;
      v89 = (void (__stdcall *)(GUID, void *))CoTaskMemAlloc(2 * v48);
      if ( v89 )
      {
        v39 = 0;
        v34[17] = (NotificationHandler)v48;
        v34[15] = v89;
        *(_WORD *)v89 = 0;
      }
      else
      {
        v39 = -2147024882;
      }
      if ( v39 < 0 )
        goto LABEL_243;
    }
    if ( v47 == -1 )
      goto LABEL_171;
    v90 = v34[15];
    if ( v48 > 0x7FFFFFFF )
    {
      *v90 = 0;
LABEL_171:
      v34[16] = (NotificationHandler)v47;
      goto LABEL_74;
    }
    if ( v47 <= 0x7FFFFFFE )
    {
      v91 = v47;
      do
      {
        if ( !v91 )
          break;
        v92 = *v29;
        if ( !*v29 )
          break;
        ++v29;
        *v90++ = v92;
        --v91;
        --v48;
      }
      while ( v48 );
      v93 = v90 - 1;
      if ( v48 )
        v93 = v90;
      *v93 = 0;
      goto LABEL_171;
    }
    *v90 = 0;
    v34[16] = (NotificationHandler)v47;
LABEL_74:
    if ( v39 < 0 )
      goto LABEL_243;
LABEL_75:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v34 + 18);
    v39 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            v34 + 22,
            0,
            -1);
    if ( v39 < 0 )
    {
      v40 = 43;
      goto LABEL_46;
    }
    if ( v34 )
      (*((void (__fastcall **)(NotificationHandler *))*v34 + 1))(v34);
    v138 = v34;
    if ( v34 )
    {
      (*((void (__fastcall **)(NotificationHandler *))*v34 + 2))(v34);
      v34 = v138;
    }
    v3 = (NotificationPlatform *)this;
    v78 = v34 + 4;
    v4 = 0;
    if ( !v34 )
      v78 = 0;
    v79 = (*(__int64 (__fastcall **)(__int64, NotificationHandler *))(*((_QWORD *)this[18] + 4) + 184LL))(
            (__int64)this[18] + 32,
            v78);
    if ( (int)(v79 + 0x80000000) >= 0 && v79 != -2018572269 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3DD,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
        (const char *)v79,
        v135);
    if ( v79 == -2018572269 )
    {
      v81 = v151;
      if ( (*(_DWORD *)((_BYTE *)lpMem + v151 + 516) & 0x40000000) != 0 )
        break;
    }
LABEL_135:
    v82 = v140;
    if ( v140 )
    {
      v140 = 0;
      (*(void (__fastcall **)(struct INotificationHandlerSettings *))(*(_QWORD *)v82 + 16LL))(v82);
    }
    v83 = v138;
    if ( v138 )
    {
      v138 = 0;
      (*((void (__fastcall **)(NotificationHandler *))*v83 + 2))(v83);
    }
    if ( pv )
      CoTaskMemFree(pv);
  }
  v157 = 0;
  v96 = this[18];
  v97 = *(__int64 (__fastcall **)(char *, char *, _QWORD **))(*((_QWORD *)v96 + 4) + 192LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v157);
  v98 = v97((char *)v96 + 32, (char *)lpMem + v81, &v157);
  v7 = v98;
  if ( v98 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E5,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
      (const char *)(unsigned int)v98,
      v135);
    v123 = v157;
    if ( v157 )
    {
      v157 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v123 + 16LL))(v123);
    }
    v124 = v140;
    if ( v140 )
    {
      v140 = 0;
      (*(void (__fastcall **)(struct INotificationHandlerSettings *))(*(_QWORD *)v124 + 16LL))(v124);
    }
    v125 = v138;
    if ( v138 )
    {
      v138 = 0;
      (*((void (__fastcall **)(NotificationHandler *))*v125 + 2))(v125);
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    goto LABEL_272;
  }
  v99 = v157;
  v100 = *(__int64 (__fastcall **)(_QWORD *, LPVOID *))(*v157 + 48LL);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v142 = -1;
  v143 = -1;
  v101 = v100(v99, &pv);
  v7 = v101;
  if ( v101 >= 0 )
  {
    v102 = (unsigned __int16 *)pv;
    do
    {
      v103 = *(unsigned __int16 *)((char *)v102 + (char *)L"app:desktop" - (_BYTE *)pv);
      v104 = *v102 - v103;
      if ( v104 )
        break;
      ++v102;
    }
    while ( v103 );
    if ( v104 )
    {
LABEL_120:
      v77 = v157;
      if ( v157 )
      {
        v157 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v77 + 16LL))(v77);
      }
      goto LABEL_135;
    }
    v126 = (*(__int64 (__fastcall **)(__int64, char *))(*((_QWORD *)this[18] + 4) + 224LL))(
             (__int64)this[18] + 32,
             (char *)lpMem + v81);
    v7 = v126;
    if ( v126 >= 0 )
    {
      v131 = v138 + 4;
      if ( !v138 )
        v131 = 0;
      v132 = (*(__int64 (__fastcall **)(__int64, NotificationHandler *))(*((_QWORD *)this[18] + 4) + 184LL))(
               (__int64)this[18] + 32,
               v131);
      if ( v132 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3EA,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
          (const char *)(unsigned int)v132,
          v135);
      goto LABEL_120;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E9,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
      (const char *)(unsigned int)v126,
      v135);
    v127 = v157;
    if ( v157 )
    {
      v157 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v127 + 16LL))(v127);
    }
    v128 = v140;
    if ( v140 )
    {
      v140 = 0;
      (*(void (__fastcall **)(struct INotificationHandlerSettings *))(*(_QWORD *)v128 + 16LL))(v128);
    }
    v129 = v138;
    if ( v138 )
    {
      v138 = 0;
      (*((void (__fastcall **)(NotificationHandler *))*v129 + 2))(v129);
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
LABEL_272:
    v142 = 0;
    v143 = 0;
    v149 = 0;
    lambda_d5c261f7a769db825fc46774a27f5aa0_::operator()(&p_lpMem, v122);
    return v7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3E6,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
    (const char *)(unsigned int)v101,
    v135);
LABEL_304:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v157);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v140);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
LABEL_219:
  v113 = lpMem;
  if ( lpMem )
  {
    v114 = GetProcessHeap();
    HeapFree(v114, 0, v113);
  }
  return v7;
}

```

## disassembly

```asm
0x18000e620  mov     [rsp-8+arg_10], r8b
0x18000e625  mov     [rsp-8+arg_8], dl
0x18000e629  mov     [rsp-8+arg_0], rcx
0x18000e62e  push    rbp
0x18000e62f  push    rbx
0x18000e630  push    rsi
0x18000e631  push    rdi
0x18000e632  push    r12
0x18000e634  push    r13
0x18000e636  push    r14
0x18000e638  push    r15
0x18000e63a  lea     rbp, [rsp-1Fh]
0x18000e63f  sub     rsp, 0D8h
0x18000e646  mov     r13, rcx
0x18000e649  xor     r15d, r15d
0x18000e64c  mov     [rbp+57h+var_90], r15d
0x18000e650  mov     [rbp+57h+lpMem], r15
0x18000e654  lea     rax, [rbp+57h+lpMem]
0x18000e658  mov     [rbp+57h+var_70], rax
0x18000e65c  mov     [rbp+57h+var_68], 1
0x18000e660  mov     rcx, [rcx+150h]; struct IPlatformConfigurationProvider *
0x18000e667  test    r8b, r8b
0x18000e66a  jz      loc_18000F79F
0x18000e670  lea     r8, [rbp+57h+lpMem]; struct WPN_REGISTRATION_INFO **
0x18000e674  lea     rdx, [rbp+57h+var_90]; unsigned int *
0x18000e678  call    ?WpnGetPreinstalledOnSystemUserRegistrationInformation@@YAJPEAUIPlatformConfigurationProvider@@PEAIPEAPEAUWPN_REGISTRATION_INFO@@@Z; WpnGetPreinstalledOnSystemUserRegistrationInformation(IPlatformConfigurationProvider *,uint *,WPN_REGISTRATION_INFO * *)
0x18000e67d  mov     ebx, eax
0x18000e67f  test    eax, eax
0x18000e681  jnz     loc_18000F430
0x18000e687  mov     eax, r15d
0x18000e68a  lea     rdx, __ImageBase
0x18000e691  mov     [rbp+57h+var_80], eax
0x18000e694  cmp     eax, [rbp+57h+var_90]
0x18000e697  jnb     loc_18000F412
0x18000e69d  mov     [rbp+57h+pv], r15
0x18000e6a1  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFFh
0x18000e6a9  mov     [rbp+57h+var_98], 0FFFFFFFFFFFFFFFFh
0x18000e6b1  imul    r12, rax, 1218h
0x18000e6b8  mov     [rbp+57h+var_58], r12
0x18000e6bc  mov     rax, [rbp+57h+lpMem]
0x18000e6c0  mov     ecx, [r12+rax+204h]
0x18000e6c8  and     ecx, 0F0000000h
0x18000e6ce  mov     eax, r15d
0x18000e6d1  cmp     eax, 4
0x18000e6d4  jnb     loc_18000F453
0x18000e6da  movsxd  rdi, eax
0x18000e6dd  add     rdi, rdi
0x18000e6e0  cmp     ecx, rva dword_18015C4E8[rdx+rdi*8]
0x18000e6e7  jnz     loc_18000F06F
0x18000e6ed  mov     rdi, rva ?c_appTypeMap@@3PAUAPPTYPE_MAP@@A[rdx+rdi*8]; APPTYPE_MAP near * c_appTypeMap ...
0x18000e6f5  test    rdi, rdi
0x18000e6f8  jz      loc_18000EBCD
0x18000e6fe  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000e705  inc     rbx
0x18000e708  cmp     word ptr [rdi+rbx*2], 0
0x18000e70d  jnz     short loc_18000E705
0x18000e70f  lea     rsi, [rbx+1]
0x18000e713  cmp     rsi, rbx
0x18000e716  jb      short loc_18000E731
0x18000e718  mov     [rbp+57h+arg_18], 0
0x18000e720  mov     eax, 2
0x18000e725  mul     rsi
0x18000e728  test    rdx, rdx
0x18000e72b  jz      loc_18000EAB6
0x18000e731  mov     r14d, 80070216h
0x18000e737  test    r14d, r14d
0x18000e73a  jns     loc_18000EBCD
0x18000e740  mov     rcx, [rbp+5Fh]; this
0x18000e744  mov     r9d, r14d; char *
0x18000e747  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000e74e  mov     edx, 17Ch; void *
0x18000e753  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e758  test    r15, r15
0x18000e75b  jz      short loc_18000E766
0x18000e75d  mov     rcx, r15; pv
0x18000e760  call    cs:__imp_CoTaskMemFree
0x18000e766  test    r14d, r14d
0x18000e769  js      loc_18000F471
0x18000e76f  mov     rcx, [rbp+57h+lpMem]
0x18000e773  add     rcx, r12
0x18000e776  mov     r14, [rcx+208h]
0x18000e77d  mov     [rbp+57h+var_60], r14
0x18000e781  xor     r15d, r15d
0x18000e784  mov     [rbp+57h+var_C0], r15
0x18000e788  mov     [rbp+57h+var_B0], r15
0x18000e78c  test    byte ptr [rcx+210h], 2
0x18000e793  jnz     loc_18000EBD6
0x18000e799  mov     esi, [rcx+204h]
0x18000e79f  mov     [rbp+57h+var_78], rcx
0x18000e7a3  mov     [rbp+57h+arg_18], r15
0x18000e7a7  lea     rdx, [rbp+57h+var_78]
0x18000e7ab  lea     rcx, [rbp+57h+arg_18]
0x18000e7af  call    ??$MakeAndInitialize@VNotificationSettings@@V1@AEAPEBG@Details@WRL@Microsoft@@YAJPEAPEAVNotificationSettings@@AEAPEBG@Z; Microsoft::WRL::Details::MakeAndInitialize<NotificationSettings,NotificationSettings,ushort const * &>(NotificationSettings * *,ushort const * &)
0x18000e7b4  mov     edi, eax
0x18000e7b6  test    eax, eax
0x18000e7b8  js      loc_18000F8AC
0x18000e7be  mov     ebx, r15d
0x18000e7c1  cmp     ebx, 18h
0x18000e7c4  jnb     short loc_18000E83F
0x18000e7c6  movsxd  rax, ebx
0x18000e7c9  shl     rax, 4
0x18000e7cd  lea     rdx, __ImageBase
0x18000e7d4  mov     ecx, [rax+rdx+15C368h]
0x18000e7db  test    ecx, 7F7FFFFh
0x18000e7e1  jz      short loc_18000E818
0x18000e7e3  lea     rdx, rva ?c_settingMap@@3PAUSETTING_MAP@@A[rdx]; SETTING_MAP near * c_settingMap ...
0x18000e7ea  add     rdx, rax
0x18000e7ed  mov     rdx, [rdx]
0x18000e7f0  test    esi, ecx
0x18000e7f2  mov     rcx, [rbp+57h+arg_18]
0x18000e7f6  jz      short loc_18000E81C
0x18000e7f8  add     rcx, 20h ; ' '
0x18000e7fc  mov     rax, [rcx]
0x18000e7ff  mov     r8d, 1
0x18000e805  mov     rax, [rax+28h]
0x18000e809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e80e  mov     edi, eax
0x18000e810  test    eax, eax
0x18000e812  js      loc_18000F52F
0x18000e818  inc     ebx
0x18000e81a  jmp     short loc_18000E7C1
0x18000e81c  add     rcx, 20h ; ' '
0x18000e820  mov     rax, [rcx]
0x18000e823  xor     r8d, r8d
0x18000e826  mov     rax, [rax+28h]
0x18000e82a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e82f  mov     edi, eax
0x18000e831  test    eax, eax
0x18000e833  jns     short loc_18000E818
0x18000e835  mov     edx, 14Dh
0x18000e83a  jmp     loc_18000F8B1
0x18000e83f  mov     rcx, [rbp+57h+arg_18]
0x18000e843  lea     rbx, [rcx+20h]
0x18000e847  test    rcx, rcx
0x18000e84a  cmovz   rbx, r15
0x18000e84e  mov     [rbp+57h+var_B0], rbx
0x18000e852  mov     rsi, [rbp+57h+lpMem]
0x18000e856  add     rsi, r12
0x18000e859  test    dword ptr [rsi+204h], 10000000h
0x18000e863  lea     rax, [rsi+104h]
0x18000e86a  mov     r13, r15
0x18000e86d  cmovz   r13, rax
0x18000e871  mov     r12, [rbp+57h+pv]
0x18000e875  mov     rcx, [rbp+57h+var_C0]
0x18000e879  test    rcx, rcx
0x18000e87c  jz      short loc_18000E88F
0x18000e87e  mov     [rbp+57h+var_C0], r15
0x18000e882  mov     rax, [rcx]
0x18000e885  mov     rax, [rax+10h]
0x18000e889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e88e  nop
0x18000e88f  mov     [rbp+57h+var_C0], r15
0x18000e893  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e89a  mov     ecx, 0E0h; unsigned __int64
0x18000e89f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e8a4  test    rax, rax
0x18000e8a7  jz      loc_18000F4D3
0x18000e8ad  mov     rcx, rax; this
0x18000e8b0  call    ??0NotificationHandler@@QEAA@XZ; NotificationHandler::NotificationHandler(void)
0x18000e8b5  mov     rdi, rax
0x18000e8b8  mov     [rbp+57h+var_50], rax
0x18000e8bc  lea     r15, [rax+30h]
0x18000e8c0  test    rsi, rsi
0x18000e8c3  jz      loc_18000F405
0x18000e8c9  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18000e8d0  inc     r9
0x18000e8d3  cmp     word ptr [rsi+r9*2], 0
0x18000e8d9  jnz     short loc_18000E8D0
0x18000e8db  mov     [rbp+57h+var_78], r9
0x18000e8df  lea     r14, [r9+1]
0x18000e8e3  cmp     r14, r9
0x18000e8e6  jb      short loc_18000E914
0x18000e8e8  mov     r8, [r15+10h]
0x18000e8ec  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000e8f0  jz      loc_18000F04D
0x18000e8f6  test    r8, r8
0x18000e8f9  jnz     loc_18000EFDF
0x18000e8ff  mov     [rbp+57h+arg_18], r8
0x18000e903  mov     eax, 2
0x18000e908  mul     r14
0x18000e90b  test    rdx, rdx
0x18000e90e  jz      loc_18000EB36
0x18000e914  mov     esi, 80070216h
0x18000e919  test    esi, esi
0x18000e91b  jns     short loc_18000E943
0x18000e91d  mov     edx, 23h ; '#'; void *
0x18000e922  mov     r9d, esi; char *
0x18000e925  mov     rcx, [rbp+5Fh]; this
0x18000e929  lea     r8, aOnecoreuapBase_83; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000e930  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e935  lea     rcx, [rbp+57h+var_50]
0x18000e939  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e93e  jmp     loc_18000F4D8
0x18000e943  mov     r14, [rbp+57h+var_60]
0x18000e947  cmp     [rdi+48h], rbx
0x18000e94b  jz      short loc_18000E97C
0x18000e94d  test    rbx, rbx
0x18000e950  jz      short loc_18000E962
0x18000e952  mov     rax, [rbx]
0x18000e955  mov     rcx, rbx
0x18000e958  mov     rax, [rax+8]
0x18000e95c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e961  nop
0x18000e962  mov     rcx, [rdi+48h]
0x18000e966  mov     [rdi+48h], rbx
0x18000e96a  test    rcx, rcx
0x18000e96d  jz      short loc_18000E97C
0x18000e96f  mov     rax, [rcx]
0x18000e972  mov     rax, [rax+10h]
0x18000e976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e97b  nop
0x18000e97c  mov     rcx, [rdi+50h]
0x18000e980  test    rcx, rcx
0x18000e983  jz      loc_18000F7E1
0x18000e989  xor     esi, esi
0x18000e98b  mov     [rdi+50h], rsi
0x18000e98f  mov     rax, [rcx]
0x18000e992  mov     rax, [rax+10h]
0x18000e996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e99b  nop
0x18000e99c  mov     rcx, [rdi+58h]
0x18000e9a0  test    rcx, rcx
0x18000e9a3  jz      short loc_18000E9B6
0x18000e9a5  mov     [rdi+58h], rsi
0x18000e9a9  mov     rax, [rcx]
0x18000e9ac  mov     rax, [rax+10h]
0x18000e9b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9b5  nop
0x18000e9b6  mov     [rdi+0A8h], r14
0x18000e9bd  test    r12, r12
0x18000e9c0  jz      loc_18000F4B7
0x18000e9c6  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18000e9cd  nop     dword ptr [rax]
0x18000e9d0  inc     r14
0x18000e9d3  cmp     word ptr [r12+r14*2], 0
0x18000e9d9  jnz     short loc_18000E9D0
0x18000e9db  lea     rbx, [r14+1]
0x18000e9df  cmp     rbx, r14
0x18000e9e2  jb      short loc_18000EA10
0x18000e9e4  mov     r8, [rdi+70h]
0x18000e9e8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000e9ec  jz      loc_18000F355
0x18000e9f2  test    r8, r8
0x18000e9f5  jnz     loc_18000F1C7
0x18000e9fb  mov     [rbp+57h+arg_18], rsi
0x18000e9ff  mov     eax, 2
0x18000ea04  mul     rbx
0x18000ea07  test    rdx, rdx
0x18000ea0a  jz      loc_18000EEC5
0x18000ea10  mov     esi, 80070216h
0x18000ea15  test    esi, esi
0x18000ea17  js      loc_18000F3D5
0x18000ea1d  test    r13, r13
0x18000ea20  jz      loc_18000F4C5
0x18000ea26  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18000ea2d  nop     dword ptr [rax]
0x18000ea30  inc     r14
0x18000ea33  cmp     word ptr [r13+r14*2+0], 0
0x18000ea3a  jnz     short loc_18000EA30
0x18000ea3c  lea     rbx, [r14+1]
0x18000ea40  cmp     rbx, r14
0x18000ea43  jb      short loc_18000EA74
0x18000ea45  mov     r8, [rdi+88h]
0x18000ea4c  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000ea50  jz      loc_18000F379
0x18000ea56  test    r8, r8
0x18000ea59  jnz     loc_18000F2E8
0x18000ea5f  mov     [rbp+57h+arg_18], r8
0x18000ea63  mov     eax, 2
0x18000ea68  mul     rbx
0x18000ea6b  test    rdx, rdx
0x18000ea6e  jz      loc_18000EF4E
0x18000ea74  mov     esi, 80070216h
0x18000ea79  test    esi, esi
0x18000ea7b  js      loc_18000F3EE
0x18000ea81  lea     rcx, [rdi+90h]
0x18000ea88  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000ea8d  lea     rcx, [rdi+0B0h]
0x18000ea94  xor     edx, edx
0x18000ea96  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000ea9d  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18000eaa2  mov     esi, eax
0x18000eaa4  test    eax, eax
0x18000eaa6  jns     loc_18000EDC8
0x18000eaac  mov     edx, 2Bh ; '+'
0x18000eab1  jmp     loc_18000E922
0x18000eab6  mov     rcx, rax; cb
0x18000eab9  call    cs:__imp_CoTaskMemAlloc
0x18000eabf  mov     rdx, rax
0x18000eac2  test    rax, rax
0x18000eac5  jz      loc_18000F076
0x18000eacb  xor     r14d, r14d
0x18000eace  mov     r15, rax
0x18000ead1  xor     ecx, ecx
0x18000ead3  mov     [rax], cx
0x18000ead6  test    rsi, rsi
0x18000ead9  jz      loc_18000E737
0x18000eadf  cmp     rbx, 7FFFFFFEh
0x18000eae6  ja      loc_18000F717
0x18000eaec  cmp     rsi, 7FFFFFFFh
  ... truncated ...
```
