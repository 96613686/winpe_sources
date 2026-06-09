# CInstallationJob::BeginInstallInternal(IUpdateSession2 *,tagDSDeploymentOperation,ulong,HWND__ *,IUpdateCollection *,unsigned __int64,wchar_t const *,void *,wchar_t const *,wchar_t const *,tagAttributeTargeting)

- ea: `0x18002327c`
- end: `0x1800241cd`
- name: `?BeginInstallInternal@CInstallationJob@@AEAAJPEAUIUpdateSession2@@W4tagDSDeploymentOperation@@KPEAUHWND__@@PEAUIUpdateCollection@@_KPEB_WPEAX55UtagAttributeTargeting@@@Z`
- size: `3921`
- prototype: `__int64 __fastcall(__int64, __int64, int, int, __int64, COMAPIHelper *, __int64, _WORD *, __int64, struct IUpdateCollection *, __int64, __int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180022f40`

## callees

- `0x18000588c`
- `0x180006ac4`
- `0x18000ed54`
- `0x18000ed90`
- `0x18002327c`
- `0x180025148`
- `0x180025948`
- `0x180027130`
- `0x1800449b8`
- `0x180044f1c`
- `0x180081a38`
- `0x180081adc`
- `0x180082720`
- `0x180082ab0`
- `0x180082b28`
- `0x180082ba4`
- `0x180083164`
- `0x18008da10`
- `0x180090bc8`
- `0x1800914bc`
- `0x180096c88`
- `0x18009ae75`
- `0x18009b050`
- `0x1800a1960`

## string_xrefs

- `0x18002355f`: `Updates in request: %ld`
- `0x180023840`: `ServiceID = {%ws} %ws, Final SessionData = %ws`
- `0x180023915`: `ServiceID = {%ws} %ws`
- `0x180023547`: `C:\__w\1\s\src\Client\comapi\InstallationJob.cpp`
- `0x1800235b8`: `C:\__w\1\s\src\Client\comapi\InstallationJob.cpp`
- `0x1800238b9`: `C:\__w\1\s\src\Client\comapi\InstallationJob.cpp`
- `0x1800239e5`: `C:\__w\1\s\src\Client\comapi\InstallationJob.cpp`
- `0x180023a48`: `C:\__w\1\s\src\Client\comapi\InstallationJob.cpp`
- `0x180023e25`: `C:\__w\1\s\src\Client\comapi\InstallationJob.cpp`
- `0x180024138`: `C:\__w\1\s\src\Client\comapi\InstallationJob.cpp`
- `0x180023432`: `Installer SessionData = %ws`
- `0x1800234ce`: `Allow source prompts: %ws; Forced: %ws; Force quiet: %ws; Attempt close apps if necessary: %ws`
- `0x180023972`: `All updates have unaccepted EULAs. This usually means that an API caller did not call IUpdate::AcceptEula as required.`
- `0x1800233c4`: `Install`
- `0x180023f17`: `Install`
- `0x1800233bb`: `Uninstall`
- `0x180023f0e`: `Uninstall`
- `0x1800233a9`: `Commit`
- `0x180023efc`: `Commit`

## pseudocode

```c
// Hidden C++ exception states: #wind=59
__int64 __fastcall CInstallationJob::BeginInstallInternal(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        COMAPIHelper *a6,
        __int64 a7,
        _WORD *a8,
        __int64 a9,
        struct IUpdateCollection *a10,
        __int64 a11,
        __int64 a12)
{
  int v14; // r15d
  _QWORD *v15; // rbx
  void *v16; // rcx
  signed int v17; // esi
  __int64 v18; // rdx
  __int64 v19; // rdi
  const wchar_t *v20; // rax
  void *v21; // r14
  bool v22; // zf
  const wchar_t *v23; // rax
  const wchar_t *v24; // r8
  const wchar_t *v25; // rdx
  const wchar_t *v26; // rcx
  const wchar_t *v27; // rax
  wchar_t **v28; // r9
  int FinalSessionData; // eax
  signed int v30; // ecx
  __int64 (__fastcall ***v31)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v32)(_QWORD, GUID *, void **); // rdi
  __int64 v33; // rdx
  __int64 v34; // rcx
  char v35; // dl
  __int64 v36; // rdx
  unsigned __int64 v37; // rbx
  unsigned int v38; // r8d
  bool v39; // bl
  int v40; // eax
  unsigned __int64 v41; // r9
  __int64 v42; // rdx
  unsigned __int64 v43; // rbx
  void *v44; // rcx
  void *v45; // rax
  unsigned __int64 v46; // r9
  __int64 v47; // rdx
  unsigned int v48; // esi
  void *v49; // rbx
  void *v50; // rdi
  __int64 v51; // rax
  __int64 (__fastcall ***v52)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 (__fastcall *v53)(_QWORD, GUID *, __int64 *); // r15
  __int64 v54; // rdx
  void *v55; // rdx
  void *v56; // rdx
  __int64 v57; // r15
  char *v58; // rsi
  int v59; // eax
  int v60; // eax
  unsigned __int64 v61; // r9
  __int64 v62; // rdx
  __int64 v63; // rbx
  void *v64; // rcx
  int v65; // eax
  __int64 v66; // rbx
  const wchar_t *v67; // rdi
  void *v68; // rcx
  int v69; // eax
  void **v70; // rdi
  _BYTE *v71; // rbx
  int v72; // eax
  char IsEnabled; // al
  int v74; // ebx
  int v75; // edi
  unsigned int v76; // esi
  __int64 v77; // xmm1_8
  int i; // eax
  int v80; // [rsp+20h] [rbp-E0h]
  int v81; // [rsp+20h] [rbp-E0h]
  int v82; // [rsp+20h] [rbp-E0h]
  wchar_t v85[4]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v86; // [rsp+90h] [rbp-70h]
  _WORD *v87; // [rsp+98h] [rbp-68h]
  struct _GUID v88; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v89; // [rsp+B0h] [rbp-50h]
  __int64 v90; // [rsp+C0h] [rbp-40h]
  struct IUpdateCollection *v91; // [rsp+C8h] [rbp-38h]
  __int64 v92; // [rsp+D0h] [rbp-30h]
  __int64 v93; // [rsp+D8h] [rbp-28h]
  __int64 v94; // [rsp+E0h] [rbp-20h]
  unsigned int *v95; // [rsp+E8h] [rbp-18h]
  int *v96; // [rsp+F0h] [rbp-10h]
  void **p_lpMem; // [rsp+F8h] [rbp-8h]
  char v98; // [rsp+100h] [rbp+0h]
  _BYTE v99[80]; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v100; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v101; // [rsp+164h] [rbp+64h] BYREF
  int v102; // [rsp+168h] [rbp+68h] BYREF
  void *lpMem; // [rsp+170h] [rbp+70h] BYREF
  __int16 v104; // [rsp+178h] [rbp+78h] BYREF
  __int64 v105; // [rsp+180h] [rbp+80h] BYREF
  void *v106; // [rsp+188h] [rbp+88h] BYREF
  __int64 (__fastcall ***v107)(_QWORD, GUID *, __int64 *); // [rsp+190h] [rbp+90h] BYREF
  int v108; // [rsp+198h] [rbp+98h] BYREF
  struct _GUID v109; // [rsp+1A0h] [rbp+A0h] BYREF
  struct _GUID v110; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v111[240]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v94 = a2;
  v93 = a5;
  *(_QWORD *)&v88.Data1 = a8;
  v92 = a9;
  v91 = a10;
  v86 = a11;
  v90 = a12;
  v101 = 0;
  v14 = 0;
  v100 = 0;
  lpMem = 0;
  v102 = 0;
  v109 = (struct _GUID)c_idSrvNone;
  v108 = 0;
  if ( a8 && *a8 )
    v87 = a8;
  else
    v87 = (_WORD *)*((_QWORD *)&xmmword_1800EF1F0 + 1);
  v15 = (_QWORD *)(a1 + 584);
  v16 = *(void **)(a1 + 584);
  if ( v16 )
  {
    SusFree(v16);
    *v15 = 0;
  }
  v17 = DuplicateOptionalString<wchar_t const *,wchar_t *>(a8, v15);
  if ( v17 < 0 )
  {
    v18 = 210;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\InstallationJob.cpp",
      (const char *)(unsigned int)v17,
      v80);
    goto LABEL_187;
  }
  v19 = a1 + 40;
  switch ( a3 )
  {
    case 1:
      v20 = L"Install";
      break;
    case 2:
      v20 = L"Uninstall";
      break;
    case 4:
      v20 = L"Revert";
      break;
    case 8:
      v20 = L"Commit";
      break;
    default:
      v20 = L"Unknown";
      break;
  }
  v21 = 0;
  WUTrace(
    0,
    0,
    0x10000,
    4,
    0,
    L"* START *   %ws ClientId = %ws, Flags: %#X (cV: %hs)",
    v20,
    *v15,
    a4,
    *(_QWORD *)(a1 + 424));
  if ( v91 )
  {
    v22 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl'::`2'::impl) == 0;
    v23 = L"Installer SessionData = %ws";
    if ( v22 )
      v23 = L"SessionData = %ws";
    WUTrace(0, 0, 0x10000, 4, 0, v23, v91);
  }
  if ( v86 )
    WUTrace(0, 0, 0x10000, 4, 0, L"IntentPFaNs = %ws", v86);
  v24 = L"No";
  v25 = L"No";
  if ( (a4 & 8) != 0 )
    v25 = L"Yes";
  v26 = L"No";
  if ( (a4 & 2) != 0 )
    v26 = L"Yes";
  v27 = L"No";
  if ( (a4 & 1) != 0 )
    v27 = L"Yes";
  if ( (a4 & 0x40) == 0 )
    v24 = L"Yes";
  WUTrace(
    0,
    0,
    0x10000,
    4,
    0,
    L"Allow source prompts: %ws; Forced: %ws; Force quiet: %ws; Attempt close apps if necessary: %ws",
    v24,
    v27,
    v26,
    v25);
  v17 = (*(__int64 (__fastcall **)(COMAPIHelper *, unsigned int *))(*(_QWORD *)a6 + 80LL))(a6, &v101);
  if ( v17 < 0 )
  {
    v18 = 245;
    goto LABEL_38;
  }
  if ( (int)v101 <= 0 )
  {
    v17 = -2145124316;
    v18 = 247;
    goto LABEL_38;
  }
  v17 = CInstallationResult::Initialize(*(CInstallationResult **)(a1 + 456), v101);
  if ( v17 < 0 )
  {
    v18 = 249;
    goto LABEL_38;
  }
  WUTrace(0, 0, 0x10000, 4, 0, L"Updates in request: %ld");
  *(_QWORD *)v85 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl'::`2'::impl) )
  {
    FinalSessionData = COMAPIHelper::GetFinalSessionData(a6, v91, v85, v28);
    v17 = FinalSessionData;
    if ( FinalSessionData < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x101,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\InstallationJob.cpp",
        (const char *)(unsigned int)FinalSessionData,
        v81);
      v21 = *(void **)v85;
      goto LABEL_185;
    }
    v21 = *(void **)v85;
  }
  if ( (int)v101 > 0 )
  {
    v30 = 0;
    while ( 1 )
    {
      v107 = 0;
      v106 = 0;
      LODWORD(v105) = 0;
      v110 = 0;
      v104 = 0;
      v17 = (*(__int64 (__fastcall **)(COMAPIHelper *, _QWORD, _QWORD))(*(_QWORD *)a6 + 56LL))(
              a6,
              (unsigned int)v30,
              &v107);
      if ( v17 < 0 )
        break;
      if ( !v107 )
      {
        v17 = -2145124323;
        v36 = 275;
        goto LABEL_78;
      }
      v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)(*(_QWORD *)(a1 + 448) + 24LL) + 96LL))(
              *(_QWORD *)(a1 + 448) + 24LL,
              v107,
              &v105);
      if ( v17 < 0 )
      {
        v36 = 276;
        goto LABEL_78;
      }
      v31 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v107;
      v32 = (__int64 (__fastcall *)(_QWORD, GUID *, void **))**v107;
      if ( v106 )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)v106 + 16LL))(v106);
        v106 = 0;
      }
      v17 = v32(v31, &GUID_e5f74104_b7f7_4d6a_a70a_9d066c2b59e6, &v106);
      if ( v17 < 0 )
      {
        v36 = 277;
        goto LABEL_78;
      }
      v17 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int16 *))(*v107)[16])(
              v107,
              &v104);
      if ( v17 < 0 )
      {
        v36 = 278;
        goto LABEL_78;
      }
      v17 = (*(__int64 (__fastcall **)(void *, struct _GUID *))(*(_QWORD *)v106 + 24LL))(v106, &v110);
      if ( v17 < 0 )
      {
        v36 = 279;
        goto LABEL_78;
      }
      if ( !v100 )
        v109 = v110;
      if ( v109.Data1 != v110.Data1
        || *(_QWORD *)&v109.Data2 != *(_QWORD *)&v110.Data2
        || *(_DWORD *)&v109.Data4[4] != *(_DWORD *)&v110.Data4[4] )
      {
        v17 = -2147024809;
        v36 = 287;
        goto LABEL_78;
      }
      if ( v104 == -1 )
      {
        ++*(_DWORD *)(a1 + 624);
      }
      else
      {
        ++v14;
        v33 = *(_QWORD *)(a1 + 456);
        if ( v100 >= *(_DWORD *)(v33 + 100) )
        {
          v17 = -2145124345;
          v36 = 298;
          goto LABEL_78;
        }
        _mm_lfence();
        v34 = *(_QWORD *)(*(_QWORD *)(v33 + 88) + 8LL * v100) + 16LL;
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v34 + 24LL))(v34, 4, 2149842979LL);
      }
      if ( v106 )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)v106 + 16LL))(v106);
        v106 = 0;
      }
      if ( v107 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v107)[2])(v107);
      v30 = v100 + 1;
      v100 = v30;
      if ( v30 >= (int)v101 )
      {
        v19 = a1 + 40;
        goto LABEL_68;
      }
    }
    v36 = 274;
LABEL_78:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\InstallationJob.cpp",
      (const char *)(unsigned int)v17,
      v81);
    if ( v106 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v106 + 16LL))(v106);
      v106 = 0;
    }
    if ( v107 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v107)[2])(v107);
    goto LABEL_185;
  }
LABEL_68:
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl'::`2'::impl);
  GuidToServiceName(&v109);
  if ( v35 )
  {
    Trace::GuidToString::GuidToString((Trace::GuidToString *)v99, &v109);
    WUTrace(0, 0, 0x10000, 4, 0, L"ServiceID = {%ws} %ws, Final SessionData = %ws");
  }
  else
  {
    Trace::GuidToString::GuidToString((Trace::GuidToString *)v99, &v109);
    WUTrace(0, 0, 0x10000, 4, 0, L"ServiceID = {%ws} %ws");
  }
  *(struct _GUID *)(*(_QWORD *)(a1 + 600) + 8LL) = v109;
  *(_WORD *)(*(_QWORD *)(a1 + 448) + 16LL) = -1;
  v37 = *(unsigned int *)(a1 + 624);
  if ( (_DWORD)v37 )
  {
    if ( lpMem )
    {
      SusFree(lpMem);
      lpMem = 0;
    }
    lpMem = SafeSusAllocArray(v37, 0xE8u);
    v17 = lpMem == 0 ? 0x8007000E : 0;
    if ( !lpMem )
    {
      v41 = (unsigned int)v17;
      v42 = 353;
      goto LABEL_96;
    }
    v95 = &v100;
    v96 = &v102;
    p_lpMem = &lpMem;
    v98 = 1;
    v43 = *(unsigned int *)(a1 + 624);
    if ( (unsigned int)v43 < v101 )
    {
      v44 = *(void **)(a1 + 616);
      if ( v44 )
      {
        SusFree(v44);
        *(_QWORD *)(a1 + 616) = 0;
      }
      if ( (_DWORD)v43 )
      {
        v45 = SafeSusAllocArray(v43, 4u);
        *(_QWORD *)(a1 + 616) = v45;
        v17 = v45 == 0 ? 0x8007000E : 0;
        if ( !v45 )
        {
          v46 = (unsigned int)v17;
          v47 = 367;
LABEL_180:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v47,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\InstallationJob.cpp",
            (const char *)v46,
            v82);
          goto LABEL_182;
        }
      }
    }
    v100 = 0;
    if ( (int)v101 > 0 )
    {
      v48 = 0;
      while ( 1 )
      {
        v107 = 0;
        v105 = 0;
        v49 = 0;
        v106 = 0;
        v50 = 0;
        *(_QWORD *)&v110.Data1 = 0;
        memset_0(v111, 0, 0xE8u);
        v51 = *(_QWORD *)(a1 + 456);
        if ( v48 >= *(_DWORD *)(v51 + 100) )
          break;
        _mm_lfence();
        if ( !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v51 + 88) + 8LL * v48) + 24LL) )
        {
          v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)(*(_QWORD *)(a1 + 448) + 24LL) + 56LL))(
                  *(_QWORD *)(a1 + 448) + 24LL,
                  v100,
                  &v107);
          if ( v17 < 0 )
          {
            v62 = 390;
            goto LABEL_139;
          }
          v52 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v107;
          v53 = **v107;
          if ( v105 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
            v105 = 0;
          }
          v17 = v53(v52, &GUID_e5f74104_b7f7_4d6a_a70a_9d066c2b59e6, &v105);
          if ( v17 < 0 )
          {
            v62 = 391;
            goto LABEL_139;
          }
          v17 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v105 + 32LL))(v105, v111);
          if ( v17 < 0 )
          {
            v62 = 392;
            goto LABEL_139;
          }
          v17 = CopyMatchingUpdate(
                  (const struct tagMatchingUpdate *)v111,
                  (struct tagMatchingUpdate *)((char *)lpMem + 232 * v102));
          if ( v17 < 0 )
          {
            v62 = 395;
            goto LABEL_139;
          }
          v54 = *(_QWORD *)(a1 + 616);
          if ( v54 )
            *(_DWORD *)(v54 + 4LL * v102) = v100;
          v49 = SafeSusAllocArray(0x81u, 1u);
          v106 = v49;
          v17 = v49 == 0 ? 0x8007000E : 0;
          if ( !v49 )
          {
            v62 = 404;
            goto LABEL_139;
          }
          v50 = SafeSusAllocArray(0x81u, 1u);
          *(_QWORD *)&v110.Data1 = v50;
          v17 = v50 == 0 ? 0x8007000E : 0;
          if ( !v50 )
          {
            v62 = 405;
            goto LABEL_139;
          }
          v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, void *, void *))(*(_QWORD *)v105 + 56LL))(
                  v105,
                  *(_QWORD *)(a1 + 424),
                  v49,
                  v50);
          if ( v17 < 0 )
          {
            v62 = 409;
            goto LABEL_139;
          }
          v55 = v49;
          v49 = 0;
          v106 = 0;
          *((_QWORD *)lpMem + 29 * v102 + 22) = v55;
          v56 = v50;
          v50 = 0;
          *(_QWORD *)&v110.Data1 = 0;
          *((_QWORD *)lpMem + 29 * v102 + 23) = v56;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl'::`2'::impl)
            && v21 )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WUSAMultiMSURebase>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WUSAMultiMSURebase>::GetImpl'::`2'::impl) )
            {
              v57 = 232LL * (int)v100;
              v58 = (char *)lpMem;
              SusFree(*(void **)((char *)lpMem + v57 + 224));
              *(_QWORD *)&v58[v57 + 224] = 0;
            }
            v59 = DuplicateString<wchar_t *,wchar_t *>(v21, (char *)lpMem + 232 * v102 + 224);
            v17 = v59;
            if ( v59 < 0 )
            {
              v61 = (unsigned int)v59;
              v62 = 424;
              goto LABEL_140;
            }
          }
          ++v102;
          if ( v105 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
            v105 = 0;
          }
          if ( v107 )
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v107)[2])(v107);
        }
        v48 = v100 + 1;
        v100 = v48;
        if ( (int)v48 >= (int)v101 )
          goto LABEL_128;
      }
      v17 = -2145124345;
      v62 = 379;
LABEL_139:
      v61 = (unsigned int)v17;
LABEL_140:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v62,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\InstallationJob.cpp",
        (const char *)v61,
        v82);
      if ( v50 )
        SusFree(v50);
      if ( v49 )
        SusFree(v49);
      if ( v105 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
        v105 = 0;
      }
      if ( v107 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v107)[2])(v107);
      goto LABEL_182;
    }
LABEL_128:
    v60 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v94 + 120LL))(v94, &v108);
    v17 = v60;
    if ( v60 >= 0 )
    {
      v63 = *(_QWORD *)(a1 + 600);
      v64 = *(void **)(v63 + 40);
      if ( v64 )
      {
        SusFree(v64);
        *(_QWORD *)(v63 + 40) = 0;
      }
      v65 = DuplicateOptionalString<wchar_t const *,wchar_t *>(*(_QWORD *)&v88.Data1, v63 + 40);
      if ( v65 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x176,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\DeploymentMiscTelemetry.h",
          (const char *)(unsigned int)v65,
          v82);
      v66 = *(_QWORD *)(a1 + 600);
      switch ( a3 )
      {
        case 1:
          v67 = L"Install";
          break;
        case 2:
          v67 = L"Uninstall";
          break;
        case 4:
          v67 = L"Revert";
          break;
        case 8:
          v67 = L"Commit";
          break;
        default:
          v67 = L"Unknown";
          break;
      }
      v68 = *(void **)(v66 + 48);
      if ( v68 )
      {
        SusFree(v68);
        *(_QWORD *)(v66 + 48) = 0;
      }
      v69 = DuplicateOptionalString<wchar_t const *,wchar_t *>(v67, v66 + 48);
      if ( v69 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x185,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\DeploymentMiscTelemetry.h",
          (const char *)(unsigned int)v69,
          v82);
      v70 = *(void ***)(a1 + 600);
      v71 = *(_BYTE **)(a1 + 424);
      if ( v71 && *v71 )
      {
        if ( *v70 )
        {
          SusFree(*v70);
          *v70 = 0;
        }
        v72 = DuplicateString<char *,char *>(v71, v70);
        if ( v72 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x17E,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\DeploymentMiscTelemetry.h",
            (const char *)(unsigned int)v72,
            v82);
      }
      *(_DWORD *)(*(_QWORD *)(a1 + 600) + 28LL) = *(_DWORD *)(a1 + 624);
      *(_DWORD *)(a1 + 592) = a3;
      v88 = v109;
      v60 = CInstallationJob::OnDeploymentStarted(
              (CInstallationJob *)a1,
              &v88,
              *(_DWORD *)(a1 + 624),
              (const struct tagMatchingUpdate *const)lpMem);
      v17 = v60;
      if ( v60 >= 0 )
      {
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl'::`2'::impl);
        v74 = *(_DWORD *)(a1 + 608);
        v75 = *(_DWORD *)(a1 + 624);
        v76 = *(_DWORD *)(a1 + 592);
        v77 = *(_QWORD *)(v90 + 16);
        v88 = *(struct _GUID *)v90;
        v89 = v77;
        if ( IsEnabled )
        {
          v60 = CSusInternalWrapper::BeginDeployUpdates(
                  a1 + 40,
                  v76,
                  (__int64)v87,
                  (__int64)&v109,
                  v75,
                  (__int64)lpMem,
                  v74,
                  a4,
                  v108,
                  v93,
                  v92,
                  a7,
                  v86,
                  a1 + 632,
                  &v88);
          v17 = v60;
          if ( v60 < 0 )
          {
            v47 = 458;
            goto LABEL_179;
          }
        }
        else
        {
          v82 = v75;
          v60 = CSusInternalWrapper::BeginDeployUpdates_Legacy(a1 + 40, v76, v87, &v109);
          v17 = v60;
          if ( v60 < 0 )
          {
            v47 = 477;
            goto LABEL_179;
          }
        }
        *(_DWORD *)(a1 + 296) = 1;
        v17 = 0;
LABEL_182:
        v100 = 0;
        if ( v102 > 0 )
        {
          for ( i = 0; i < v102; v100 = i )
          {
            FreeObject((struct tagMatchingUpdate *)((char *)lpMem + 232 * i), 1);
            i = v100 + 1;
          }
        }
        goto LABEL_185;
      }
      v47 = 440;
    }
    else
    {
      v47 = 431;
    }
LABEL_179:
    v46 = (unsigned int)v60;
    goto LABEL_180;
  }
  v38 = v101;
  v39 = v14 == v101;
  if ( v14 == v101 )
  {
    WUTrace(
      0,
      0,
      0x10000,
      3,
      0,
      L"All updates have unaccepted EULAs. This usually means that an API caller did not call IUpdate::AcceptEula as required.");
    v38 = v101;
  }
  v40 = CInstallationJob::SignalProgressChangedForSkippedUpdates((CInstallationJob *)a1, 0, v38);
  v17 = v40;
  if ( v40 < 0 )
  {
    v41 = (unsigned int)v40;
    v42 = 341;
LABEL_96:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v42,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\InstallationJob.cpp",
      (const char *)v41,
      v82);
    goto LABEL_185;
  }
  (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)(a1 + 40) + 8LL))(v19, 4, 2149842978LL);
  if ( v39 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x159,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\InstallationJob.cpp",
      (const char *)0x80240023LL,
      v82);
    v17 = -2145124317;
  }
  else
  {
    v17 = 0;
  }
LABEL_185:
  if ( v21 )
    SusFree(v21);
LABEL_187:
  if ( lpMem )
    SusFree(lpMem);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18002327c  mov     [rsp-8+arg_10], rbx
0x180023281  push    rbp
0x180023282  push    rsi
0x180023283  push    rdi
0x180023284  push    r12
0x180023286  push    r13
0x180023288  push    r14
0x18002328a  push    r15
0x18002328c  lea     rbp, [rsp-1C0h]
0x180023294  sub     rsp, 2C0h
0x18002329b  mov     rax, cs:__security_cookie
0x1800232a2  xor     rax, rsp
0x1800232a5  mov     [rbp+1F0h+var_40], rax
0x1800232ac  mov     [rbp+1F0h+var_270], r9d
0x1800232b0  mov     r14d, r8d
0x1800232b3  mov     [rbp+1F0h+var_26C], r8d
0x1800232b7  mov     [rbp+1F0h+var_210], rdx
0x1800232bb  mov     r13, rcx
0x1800232be  mov     rax, [rbp+1F0h+arg_20]
0x1800232c5  mov     [rbp+1F0h+var_218], rax
0x1800232c9  mov     r12, [rbp+1F0h+arg_28]
0x1800232d0  mov     rdi, [rbp+1F0h+arg_38]
0x1800232d7  mov     qword ptr [rbp+1F0h+var_250.Data1], rdi
0x1800232db  mov     rax, [rbp+1F0h+arg_40]
0x1800232e2  mov     [rbp+1F0h+var_220], rax
0x1800232e6  mov     rax, [rbp+1F0h+arg_48]
0x1800232ed  mov     [rbp+1F0h+var_228], rax
0x1800232f1  mov     r8, [rbp+1F0h+arg_50]
0x1800232f8  mov     [rbp+1F0h+var_260], r8
0x1800232fc  mov     rax, [rbp+1F0h+arg_58]
0x180023303  mov     [rbp+1F0h+var_230], rax
0x180023307  xor     esi, esi
0x180023309  mov     [rbp+1F0h+var_18C], esi
0x18002330c  mov     r15d, esi
0x18002330f  mov     [rbp+1F0h+var_190], esi
0x180023312  mov     [rbp+1F0h+lpMem], rsi
0x180023316  mov     [rbp+1F0h+var_188], esi
0x180023319  movups  xmm0, cs:c_idSrvNone
0x180023320  movdqu  xmmword ptr [rbp+1F0h+var_150.Data1], xmm0
0x180023328  mov     [rbp+1F0h+var_158], esi
0x18002332e  test    rdi, rdi
0x180023331  jz      short loc_18002333E
0x180023333  cmp     [rdi], si
0x180023336  jz      short loc_18002333E
0x180023338  mov     [rbp+1F0h+var_258], rdi
0x18002333c  jmp     short loc_180023349
0x18002333e  mov     rax, qword ptr cs:xmmword_1800EF1F0+8
0x180023345  mov     [rbp+1F0h+var_258], rax
0x180023349  lea     rbx, [rcx+248h]
0x180023350  mov     rcx, [rbx]; lpMem
0x180023353  test    rcx, rcx
0x180023356  jz      short loc_180023360
0x180023358  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18002335d  mov     [rbx], rsi
0x180023360  mov     rdx, rbx
0x180023363  mov     rcx, rdi
0x180023366  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x18002336b  mov     esi, eax
0x18002336d  test    eax, eax
0x18002336f  jns     short loc_18002337B
0x180023371  mov     edx, 0D2h
0x180023376  jmp     loc_18002353D
0x18002337b  lea     rdi, [r13+28h]
0x18002337f  mov     rdx, [rdi+180h]
0x180023386  mov     r8, [rbx]
0x180023389  mov     ecx, r14d
0x18002338c  sub     ecx, 1
0x18002338f  jz      short loc_1800233C4
0x180023391  sub     ecx, 1
0x180023394  jz      short loc_1800233BB
0x180023396  sub     ecx, 2
0x180023399  jz      short loc_1800233B2
0x18002339b  cmp     ecx, 4
0x18002339e  jz      short loc_1800233A9
0x1800233a0  lea     rax, aUnknown_0; "Unknown"
0x1800233a7  jmp     short loc_1800233CB
0x1800233a9  lea     rax, aCommit; "Commit"
0x1800233b0  jmp     short loc_1800233CB
0x1800233b2  lea     rax, aRevert; "Revert"
0x1800233b9  jmp     short loc_1800233CB
0x1800233bb  lea     rax, aUninstall; "Uninstall"
0x1800233c2  jmp     short loc_1800233CB
0x1800233c4  lea     rax, aInstall; "Install"
0x1800233cb  mov     [rsp+2F0h+var_2A8], rdx
0x1800233d0  mov     esi, [rbp+1F0h+var_270]
0x1800233d3  mov     dword ptr [rsp+2F0h+var_2B0], esi
0x1800233d7  mov     [rsp+2F0h+var_2B8], r8
0x1800233dc  mov     [rsp+2F0h+var_2C0], rax
0x1800233e1  lea     rax, aStartWsClienti; "* START *   %ws ClientId = %ws, Flags: "...
0x1800233e8  mov     [rsp+2F0h+var_2C8], rax
0x1800233ed  xor     r14d, r14d
0x1800233f0  mov     qword ptr [rsp+2F0h+var_2D0], r14
0x1800233f5  xor     edx, edx
0x1800233f7  xor     ecx, ecx
0x1800233f9  lea     r9d, [r14+4]
0x1800233fd  mov     r8d, 10000h
0x180023403  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180023408  mov     rbx, [rbp+1F0h+var_228]
0x18002340c  test    rbx, rbx
0x18002340f  jz      short loc_180023451
0x180023411  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl(void)'::`2'::impl
0x180023418  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(void)
0x18002341d  mov     [rsp+2F0h+var_2C0], rbx
0x180023422  xor     edx, edx
0x180023424  xor     ecx, ecx
0x180023426  lea     r9d, [r14+4]
0x18002342a  mov     r8d, 10000h
0x180023430  test    al, al
0x180023432  lea     rax, aInstallerSessi; "Installer SessionData = %ws"
0x180023439  jnz     short loc_180023442
0x18002343b  lea     rax, aSessiondataWs; "SessionData = %ws"
0x180023442  mov     [rsp+2F0h+var_2C8], rax
0x180023447  mov     qword ptr [rsp+2F0h+var_2D0], r14
0x18002344c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180023451  mov     rax, [rbp+1F0h+var_260]
0x180023455  test    rax, rax
0x180023458  jz      short loc_180023483
0x18002345a  mov     [rsp+2F0h+var_2C0], rax
0x18002345f  lea     rax, aIntentpfansWs; "IntentPFaNs = %ws"
0x180023466  mov     [rsp+2F0h+var_2C8], rax
0x18002346b  mov     qword ptr [rsp+2F0h+var_2D0], r14
0x180023470  xor     edx, edx
0x180023472  xor     ecx, ecx
0x180023474  lea     r9d, [rdx+4]
0x180023478  mov     r8d, 10000h
0x18002347e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180023483  test    sil, 8
0x180023487  lea     r9, aYes; "Yes"
0x18002348e  lea     r8, aNo; "No"
0x180023495  mov     rdx, r8
0x180023498  cmovnz  rdx, r9
0x18002349c  test    sil, 2
0x1800234a0  mov     rcx, r8
0x1800234a3  cmovnz  rcx, r9
0x1800234a7  test    sil, 1
0x1800234ab  mov     rax, r8
0x1800234ae  cmovnz  rax, r9
0x1800234b2  test    sil, 40h
0x1800234b6  cmovz   r8, r9
0x1800234ba  mov     [rsp+2F0h+var_2A8], rdx
0x1800234bf  mov     [rsp+2F0h+var_2B0], rcx
0x1800234c4  mov     [rsp+2F0h+var_2B8], rax
0x1800234c9  mov     [rsp+2F0h+var_2C0], r8
0x1800234ce  lea     rax, aAllowSourcePro; "Allow source prompts: %ws; Forced: %ws;"...
0x1800234d5  mov     [rsp+2F0h+var_2C8], rax
0x1800234da  mov     qword ptr [rsp+2F0h+var_2D0], r14; int
0x1800234df  xor     edx, edx
0x1800234e1  xor     ecx, ecx
0x1800234e3  lea     r9d, [rdx+4]
0x1800234e7  mov     r8d, 10000h
0x1800234ed  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800234f2  mov     rax, [r12]
0x1800234f6  lea     rdx, [rbp+1F0h+var_18C]
0x1800234fa  mov     rcx, r12
0x1800234fd  mov     rax, [rax+50h]
0x180023501  call    _guard_dispatch_icall
0x180023506  mov     esi, eax
0x180023508  test    eax, eax
0x18002350a  jns     short loc_180023513
0x18002350c  mov     edx, 0F5h
0x180023511  jmp     short loc_18002353D
0x180023513  mov     edx, [rbp+1F0h+var_18C]; unsigned int
0x180023516  test    edx, edx
0x180023518  jg      short loc_180023526
0x18002351a  mov     esi, 80240024h
0x18002351f  mov     edx, 0F7h
0x180023524  jmp     short loc_18002353D
0x180023526  mov     rcx, [r13+1C8h]; this
0x18002352d  call    ?Initialize@CInstallationResult@@QEAAJK@Z; CInstallationResult::Initialize(ulong)
0x180023532  mov     esi, eax
0x180023534  test    eax, eax
0x180023536  jns     short loc_180023558
0x180023538  mov     edx, 0F9h; void *
0x18002353d  mov     rcx, [rbp+1F8h]; this
0x180023544  mov     r9d, esi; char *
0x180023547  lea     r8, aCW1SSrcClientC_9; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ins"...
0x18002354e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023553  jmp     loc_180024193
0x180023558  mov     eax, [rbp+1F0h+var_18C]
0x18002355b  mov     dword ptr [rsp+2F0h+var_2C0], eax
0x18002355f  lea     rax, aUpdatesInReque; "Updates in request: %ld"
0x180023566  mov     [rsp+2F0h+var_2C8], rax
0x18002356b  mov     qword ptr [rsp+2F0h+var_2D0], r14; int
0x180023570  xor     edx, edx
0x180023572  xor     ecx, ecx
0x180023574  lea     r9d, [rdx+4]
0x180023578  mov     r8d, 10000h
0x18002357e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180023583  mov     qword ptr [rbp+1F0h+var_268], r14
0x180023587  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetImpl(void)'::`2'::impl
0x18002358e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(void)
0x180023593  test    al, al
0x180023595  jz      short loc_1800235D8
0x180023597  lea     r8, [rbp+1F0h+var_268]; wchar_t *
0x18002359b  mov     rdx, rbx; struct IUpdateCollection *
0x18002359e  mov     rcx, r12; this
0x1800235a1  call    ?GetFinalSessionData@COMAPIHelper@@YAJPEAUIUpdateCollection@@PEB_WPEAPEA_W@Z; COMAPIHelper::GetFinalSessionData(IUpdateCollection *,wchar_t const *,wchar_t * *)
0x1800235a6  mov     esi, eax
0x1800235a8  xor     ebx, ebx
0x1800235aa  test    eax, eax
0x1800235ac  jns     short loc_1800235D2
0x1800235ae  mov     rcx, [rbp+1F8h]; this
0x1800235b5  mov     r9d, eax; char *
0x1800235b8  lea     r8, aCW1SSrcClientC_9; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ins"...
0x1800235bf  mov     edx, 101h; void *
0x1800235c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800235c9  mov     r14, qword ptr [rbp+1F0h+var_268]
0x1800235cd  jmp     loc_180024185
0x1800235d2  mov     r14, qword ptr [rbp+1F0h+var_268]
0x1800235d6  jmp     short loc_1800235DA
0x1800235d8  xor     ebx, ebx
0x1800235da  or      esi, 0FFFFFFFFh
0x1800235dd  cmp     [rbp+1F0h+var_18C], ebx
0x1800235e0  jle     loc_1800237F9
0x1800235e6  mov     ecx, ebx
0x1800235e8  mov     [rbp+1F0h+var_160], rbx
0x1800235ef  mov     [rbp+1F0h+var_168], rbx
0x1800235f6  mov     dword ptr [rbp+1F0h+var_170], ebx
0x1800235fc  xorps   xmm0, xmm0
0x1800235ff  movups  [rbp+1F0h+var_140], xmm0
0x180023606  mov     [rbp+1F0h+var_178], bx
0x18002360a  mov     rax, [r12]
0x18002360e  lea     r8, [rbp+1F0h+var_160]
0x180023615  mov     edx, ecx
0x180023617  mov     rcx, r12
0x18002361a  mov     rax, [rax+38h]
0x18002361e  call    _guard_dispatch_icall
0x180023623  mov     esi, eax
0x180023625  test    eax, eax
0x180023627  js      loc_1800238AA
0x18002362d  mov     rdx, [rbp+1F0h+var_160]
0x180023634  test    rdx, rdx
0x180023637  jz      loc_18002389E
0x18002363d  mov     rcx, [r13+1C0h]
0x180023644  add     rcx, 18h
0x180023648  mov     rax, [rcx]
0x18002364b  lea     r8, [rbp+1F0h+var_170]
0x180023652  mov     rax, [rax+60h]
0x180023656  call    _guard_dispatch_icall
0x18002365b  mov     esi, eax
0x18002365d  test    eax, eax
0x18002365f  js      loc_180023897
0x180023665  mov     rbx, [rbp+1F0h+var_160]
0x18002366c  mov     rax, [rbx]
0x18002366f  mov     rdi, [rax]
0x180023672  mov     rcx, [rbp+1F0h+var_168]
0x180023679  xor     esi, esi
0x18002367b  test    rcx, rcx
0x18002367e  jz      short loc_180023693
0x180023680  mov     rdx, [rcx]
0x180023683  mov     rax, [rdx+10h]
0x180023687  call    _guard_dispatch_icall
0x18002368c  mov     [rbp+1F0h+var_168], rsi
0x180023693  lea     r8, [rbp+1F0h+var_168]
0x18002369a  lea     rdx, _GUID_e5f74104_b7f7_4d6a_a70a_9d066c2b59e6
0x1800236a1  mov     rcx, rbx
0x1800236a4  mov     rax, rdi
0x1800236a7  call    _guard_dispatch_icall
0x1800236ac  mov     esi, eax
0x1800236ae  xor     ebx, ebx
0x1800236b0  test    eax, eax
0x1800236b2  js      loc_180023890
0x1800236b8  mov     rcx, [rbp+1F0h+var_160]
0x1800236bf  mov     rax, [rcx]
0x1800236c2  lea     rdx, [rbp+1F0h+var_178]
0x1800236c6  mov     rax, [rax+80h]
0x1800236cd  call    _guard_dispatch_icall
0x1800236d2  mov     esi, eax
0x1800236d4  test    eax, eax
0x1800236d6  js      loc_180023889
0x1800236dc  mov     rcx, [rbp+1F0h+var_168]
0x1800236e3  mov     rax, [rcx]
0x1800236e6  lea     rdx, [rbp+1F0h+var_140]
0x1800236ed  mov     rax, [rax+18h]
0x1800236f1  call    _guard_dispatch_icall
0x1800236f6  mov     esi, eax
0x1800236f8  test    eax, eax
0x1800236fa  js      loc_180023882
0x180023700  cmp     [rbp+1F0h+var_190], ebx
0x180023703  jnz     short loc_180023714
0x180023705  movaps  xmm0, [rbp+1F0h+var_140]
0x18002370c  movdqa  xmmword ptr [rbp+1F0h+var_150.Data1], xmm0
0x180023714  mov     rax, qword ptr [rbp+1F0h+var_150.Data1]
0x18002371b  cmp     eax, dword ptr [rbp+1F0h+var_140]
0x180023721  jnz     loc_180023876
0x180023727  shr     rax, 20h
0x18002372b  cmp     eax, dword ptr [rbp+1F0h+var_140+4]
0x180023731  jnz     loc_180023876
0x180023737  mov     rax, qword ptr [rbp+1F0h+var_150.Data4]
0x18002373e  cmp     eax, dword ptr [rbp+1F0h+var_140+8]
0x180023744  jnz     loc_180023876
0x18002374a  shr     rax, 20h
0x18002374e  cmp     eax, dword ptr [rbp+1F0h+var_140+0Ch]
0x180023754  jnz     loc_180023876
0x18002375a  or      esi, 0FFFFFFFFh
0x18002375d  cmp     si, [rbp+1F0h+var_178]
0x180023761  jnz     short loc_18002376C
0x180023763  inc     dword ptr [r13+270h]
0x18002376a  jmp     short loc_1800237AC
0x18002376c  inc     r15d
  ... truncated ...
```
