# Windows::Internal::UI::StartScreen::JumpListBrokered::LoadJumpList(void)

- ea: `0x1800c4760`
- end: `0x1800c4f35`
- name: `?LoadJumpList@JumpListBrokered@StartScreen@UI@Internal@Windows@@AEAAJXZ`
- size: `2005`
- prototype: `__int64 __fastcall(Windows::Internal::UI::StartScreen::JumpListBrokered *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800a022c`

## callees

- `0x180008acc`
- `0x18000b7e8`
- `0x180011884`
- `0x180013a58`
- `0x180022c60`
- `0x180034518`
- `0x18003c5e4`
- `0x18008cdc4`
- `0x18008f4b0`
- `0x1800b720c`
- `0x1800c4760`
- `0x1800fa548`
- `0x18013d330`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4e95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4e95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c47e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c47e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c4b62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c4c1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c4b62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c4c1d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c47b8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c47b8`

## string_xrefs

- `0x1800c4800`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c4838`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c4881`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c48c0`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c491d`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c4971`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c4ba4`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c4bc8`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c4bf1`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c4c76`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c4dfe`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c4e3a`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c4e63`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall Windows::Internal::UI::StartScreen::JumpListBrokered::LoadJumpList(
        Windows::Internal::UI::StartScreen::JumpListBrokered *this)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  HSTRING v5; // rcx
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, PCWSTR); // rbx
  PCWSTR StringRawBuffer; // rax
  int v9; // eax
  const unsigned __int16 *v10; // rdx
  _QWORD *v11; // rax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING, _QWORD); // rbx
  int v16; // eax
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v18)(_QWORD, GUID *, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rdx
  unsigned int v21; // r15d
  unsigned int v22; // r14d
  int v23; // eax
  void *v24; // rcx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, _QWORD, GUID *, __int64); // rbx
  __int64 v27; // rax
  int v28; // eax
  unsigned int v29; // esi
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, _QWORD, GUID *, __int64); // rbx
  __int64 v32; // rax
  int v33; // eax
  int v34; // eax
  __int64 v35; // rdx
  LPVOID v36; // rdi
  __int64 (__fastcall *v37)(LPVOID, int *, GUID *, __int64 *); // rbx
  int v38; // eax
  __int64 v39; // rdx
  unsigned int v40; // esi
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, _QWORD, GUID *, __int64); // rbx
  __int64 v43; // rax
  int v44; // eax
  struct Windows::UI::StartScreen::IJumpListItem *v45; // rbx
  __int64 (__fastcall *v46)(struct Windows::UI::StartScreen::IJumpListItem *, GUID *, __int64 *); // rdi
  int v47; // eax
  __int64 v48; // rdx
  __int64 (__fastcall ***v49)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v50)(_QWORD, GUID *, __int64 *); // rdi
  int v51; // eax
  __int64 v52; // rdx
  __int64 v53; // rdx
  __int64 v54; // rsi
  __int64 (__fastcall *v55)(__int64, char *); // rdi
  int ppv; // [rsp+20h] [rbp-B9h]
  __int64 v58; // [rsp+30h] [rbp-A9h] BYREF
  __int64 (__fastcall ***v59)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-A1h] BYREF
  __int64 v60; // [rsp+40h] [rbp-99h] BYREF
  __int64 v61; // [rsp+48h] [rbp-91h] BYREF
  __int64 v62; // [rsp+50h] [rbp-89h] BYREF
  __int64 v63; // [rsp+58h] [rbp-81h] BYREF
  __int64 v64; // [rsp+60h] [rbp-79h] BYREF
  struct Windows::UI::StartScreen::IJumpListItem *v65; // [rsp+68h] [rbp-71h] BYREF
  unsigned int v66; // [rsp+70h] [rbp-69h] BYREF
  unsigned int v67; // [rsp+74h] [rbp-65h] BYREF
  unsigned int v68; // [rsp+78h] [rbp-61h] BYREF
  __int64 v69; // [rsp+80h] [rbp-59h] BYREF
  __int64 v70; // [rsp+88h] [rbp-51h] BYREF
  LPVOID v71; // [rsp+90h] [rbp-49h] BYREF
  struct Windows::UI::StartScreen::IJumpListItem *v72; // [rsp+98h] [rbp-41h] BYREF
  struct IUnknown *v73; // [rsp+A0h] [rbp-39h] BYREF
  struct IUnknown *v74; // [rsp+A8h] [rbp-31h] BYREF
  char v75; // [rsp+B0h] [rbp-29h]
  int v76; // [rsp+B8h] [rbp-21h] BYREF
  LPVOID pv[2]; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v78; // [rsp+D0h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v71 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
  v2 = CoCreateInstance(&CLSID_DestinationListBoth, 0, 3u, &GUID_6332debf_87b5_4670_90c0_5e57b408a49e, &v71);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 545;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)v2,
      ppv);
    goto LABEL_84;
  }
  v5 = (HSTRING)*((_QWORD *)this + 8);
  if ( v5 )
  {
    v6 = v71;
    v7 = *(__int64 (__fastcall **)(LPVOID, PCWSTR))(*(_QWORD *)v71 + 24LL);
    StringRawBuffer = WindowsGetStringRawBuffer(v5, 0);
    v2 = v7(v6, StringRawBuffer);
    v3 = v2;
    if ( v2 < 0 )
    {
      v4 = 549;
      goto LABEL_6;
    }
  }
  v58 = 0;
  v9 = Microsoft::WRL::ComPtr<ICustomDestinationList>::As<IInternalCustomDestinationList>(&v71, &v58);
  v3 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x229,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)v9,
      ppv);
    goto LABEL_9;
  }
  v60 = 0;
  v11 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                    (HSTRING *)pv,
                    (const unsigned __int16 (*)[32])v10);
  v12 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::StartScreen::IJumpListStatics>>(
          *v11,
          &v60);
  v3 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)v12,
      ppv);
    goto LABEL_12;
  }
  v62 = 0;
  v13 = Microsoft::WRL::ComPtr<Windows::UI::StartScreen::IJumpListStatics>::As<Windows::Internal::UI::StartScreen::IJumpListSerializationStatics>(
          &v60,
          &v62);
  v3 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)v13,
      ppv);
    goto LABEL_15;
  }
  v59 = 0;
  v14 = v62;
  v15 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v62 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
  v16 = v15(v14, string, &v59);
  v3 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)v16,
      ppv);
    goto LABEL_18;
  }
  v61 = 0;
  v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
  v18 = (*v59)[6];
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
  v19 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64 *))v18)(v17, &v61);
  v3 = v19;
  if ( v19 < 0 )
  {
    v20 = 565;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)v19,
      ppv);
    goto LABEL_22;
  }
  v67 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v58 + 48LL))(v58, &v67);
  v3 = v19;
  if ( v19 < 0 )
  {
    v20 = 570;
    goto LABEL_21;
  }
  v21 = 2;
  v22 = 0;
  if ( !v67 )
  {
LABEL_47:
    v19 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD))(*v59)[8])(v59, v21);
    v3 = v19;
    if ( v19 < 0 )
    {
      v20 = 621;
      goto LABEL_21;
    }
    v76 = 0;
    v63 = 0;
    v36 = v71;
    v37 = *(__int64 (__fastcall **)(LPVOID, int *, GUID *, __int64 *))(*(_QWORD *)v71 + 32LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v63);
    v38 = v37(v36, &v76, &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9, &v63);
    v3 = v38;
    if ( v38 >= 0 )
    {
      v68 = 0;
      v38 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v63 + 24LL))(v63, &v68);
      v3 = v38;
      if ( v38 >= 0 )
      {
        v40 = 0;
        if ( v68 )
        {
          while ( 1 )
          {
            v74 = 0;
            v41 = v63;
            v42 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64))(*(_QWORD *)v63 + 32LL);
            v43 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IClassFactory>>(&v74);
            v44 = v42(v41, v40, &GUID_00000000_0000_0000_c000_000000000046, v43);
            v3 = v44;
            if ( v44 < 0 )
              break;
            v65 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
            if ( (int)Windows::Internal::UI::StartScreen::JumpListBrokered::CreateJumpListItemForShellObject(
                        this,
                        v74,
                        &v65) >= 0 )
            {
              v69 = 0;
              v45 = v65;
              v46 = **(__int64 (__fastcall ***)(struct Windows::UI::StartScreen::IJumpListItem *, GUID *, __int64 *))v65;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
              v47 = v46(v45, &GUID_64384f1c_d1b5_43eb_a2b3_2befbde9a7a2, &v69);
              v3 = v47;
              if ( v47 < 0 )
              {
                v53 = 639;
                goto LABEL_78;
              }
              LOBYTE(v48) = 1;
              v47 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v69 + 48LL))(v69, v48);
              v3 = v47;
              if ( v47 < 0 )
              {
                v53 = 641;
                goto LABEL_78;
              }
              v47 = (*(__int64 (__fastcall **)(__int64, struct Windows::UI::StartScreen::IJumpListItem *))(*(_QWORD *)v61 + 104LL))(
                      v61,
                      v65);
              v3 = v47;
              if ( v47 < 0 )
              {
                v53 = 643;
LABEL_78:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v53,
                  (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
                  (const char *)(unsigned int)v47,
                  ppv);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
                goto LABEL_80;
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
            if ( ++v40 >= v68 )
              goto LABEL_72;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x279,
            (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
            (const char *)(unsigned int)v44,
            ppv);
LABEL_80:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
        }
        else
        {
LABEL_72:
          v70 = 0;
          v49 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
          v50 = **v59;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
          v51 = v50(v49, &GUID_fa29c8a5_125f_4162_806b_3a7ffdb40eed, &v70);
          v3 = v51;
          if ( v51 >= 0 )
          {
            v54 = v70;
            v55 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v70 + 48LL);
            WindowsDeleteString(*((HSTRING *)this + 10));
            *((_QWORD *)this + 10) = 0;
            v51 = v55(v54, (char *)this + 80);
            v3 = v51;
            if ( v51 >= 0 )
            {
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v63);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
              v3 = 0;
              goto LABEL_84;
            }
            v52 = 650;
          }
          else
          {
            v52 = 649;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v52,
            (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
            (const char *)(unsigned int)v51,
            ppv);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
        }
LABEL_61:
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v63);
        goto LABEL_22;
      }
      v39 = 629;
    }
    else
    {
      v39 = 625;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v39,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)v38,
      ppv);
    goto LABEL_61;
  }
  while ( 1 )
  {
    *(_OWORD *)pv = 0;
    v78 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, LPVOID *))(*(_QWORD *)v58 + 56LL))(v58, v22, 1, pv);
    v3 = v19;
    if ( v19 < 0 )
    {
      v20 = 574;
      goto LABEL_21;
    }
    v74 = (struct IUnknown *)pv;
    v75 = 1;
    v23 = (int)pv[0];
    if ( LODWORD(pv[0]) == 1 )
    {
      v24 = pv[1];
      switch ( LODWORD(pv[1]) )
      {
        case 2:
          v21 = (unsigned int)pv[1];
          break;
        case 1:
          v21 = 1;
          break;
        case 0xFFFFFFFF:
          v21 = 0;
          break;
      }
      goto LABEL_44;
    }
    if ( ((__int64)pv[0] & 0xFFFFFFFD) == 0 )
      break;
LABEL_43:
    v24 = pv[1];
LABEL_44:
    v75 = 0;
    if ( !v23 )
      CoTaskMemFree(v24);
    if ( ++v22 >= v67 )
      goto LABEL_47;
  }
  v64 = 0;
  v25 = v58;
  v26 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64))(*(_QWORD *)v58 + 72LL);
  v27 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(&v64);
  v28 = v26(v25, v22, &GUID_5632b1a4_e38a_400a_928a_d4cd63230295, v27);
  v3 = v28;
  if ( v28 < 0 )
  {
    v35 = 603;
    goto LABEL_54;
  }
  v66 = 0;
  v28 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v64 + 24LL))(v64, &v66);
  v3 = v28;
  if ( v28 < 0 )
  {
    v35 = 606;
LABEL_54:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)v28,
      ppv);
    goto LABEL_55;
  }
  v29 = 0;
  if ( !v66 )
  {
LABEL_42:
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v64);
    v23 = (int)pv[0];
    goto LABEL_43;
  }
  while ( 1 )
  {
    v73 = 0;
    v30 = v64;
    v31 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64))(*(_QWORD *)v64 + 32LL);
    v32 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IClassFactory>>(&v73);
    v33 = v31(v30, v29, &GUID_00000000_0000_0000_c000_000000000046, v32);
    v3 = v33;
    if ( v33 < 0 )
      break;
    v72 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
    if ( (int)Windows::Internal::UI::StartScreen::JumpListBrokered::CreateJumpListItemForShellObject(this, v73, &v72) >= 0 )
    {
      v34 = (*(__int64 (__fastcall **)(__int64, struct Windows::UI::StartScreen::IJumpListItem *))(*(_QWORD *)v61 + 104LL))(
              v61,
              v72);
      v3 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x267,
          (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
          (const char *)(unsigned int)v34,
          ppv);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
        goto LABEL_51;
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
    if ( ++v29 >= v66 )
      goto LABEL_42;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x262,
    (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
    (const char *)(unsigned int)v33,
    ppv);
LABEL_51:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
LABEL_55:
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v64);
  if ( !LODWORD(pv[0]) )
    CoTaskMemFree(pv[1]);
LABEL_22:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
LABEL_18:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
LABEL_15:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
LABEL_12:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
LABEL_9:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
LABEL_84:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
  return v3;
}

```

## disassembly

```asm
0x1800c4760  push    rbp
0x1800c4762  push    rbx
0x1800c4763  push    rsi
0x1800c4764  push    rdi
0x1800c4765  push    r12
0x1800c4767  push    r13
0x1800c4769  push    r14
0x1800c476b  push    r15
0x1800c476d  lea     rbp, [rsp-1Fh]
0x1800c4772  sub     rsp, 0F8h
0x1800c4779  mov     rax, cs:__security_cookie
0x1800c4780  xor     rax, rsp
0x1800c4783  mov     [rbp+57h+var_50], rax
0x1800c4787  mov     r13, rcx
0x1800c478a  xor     r12d, r12d
0x1800c478d  mov     [rbp+57h+var_A0], r12
0x1800c4791  lea     rcx, [rbp+57h+var_A0]
0x1800c4795  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c479a  lea     rax, [rbp+57h+var_A0]
0x1800c479e  mov     qword ptr [rsp+130h+ppv], rax; int
0x1800c47a3  lea     r9, _GUID_6332debf_87b5_4670_90c0_5e57b408a49e; riid
0x1800c47aa  xor     edx, edx; pUnkOuter
0x1800c47ac  lea     r8d, [r12+3]; dwClsContext
0x1800c47b1  lea     rcx, CLSID_DestinationListBoth; rclsid
0x1800c47b8  call    cs:__imp_CoCreateInstance
0x1800c47be  mov     ebx, eax
0x1800c47c0  test    eax, eax
0x1800c47c2  jns     short loc_1800C47CB
0x1800c47c4  mov     edx, 221h
0x1800c47c9  jmp     short loc_1800C4800
0x1800c47cb  mov     rcx, [r13+40h]; string
0x1800c47cf  test    rcx, rcx
0x1800c47d2  jz      short loc_1800C4818
0x1800c47d4  mov     rdi, [rbp+57h+var_A0]
0x1800c47d8  mov     rax, [rdi]
0x1800c47db  mov     rbx, [rax+18h]
0x1800c47df  xor     edx, edx; length
0x1800c47e1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c47e7  mov     rdx, rax
0x1800c47ea  mov     rcx, rdi
0x1800c47ed  mov     rax, rbx
0x1800c47f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c47f5  mov     ebx, eax
0x1800c47f7  test    eax, eax
0x1800c47f9  jns     short loc_1800C4818
0x1800c47fb  mov     edx, 225h; void *
0x1800c4800  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800c4807  mov     r9d, eax; char *
0x1800c480a  mov     rcx, [rbp+5Fh]; this
0x1800c480e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4813  jmp     loc_1800C4F0A
0x1800c4818  mov     [rsp+130h+var_100], r12
0x1800c481d  lea     rdx, [rsp+130h+var_100]
0x1800c4822  lea     rcx, [rbp+57h+var_A0]
0x1800c4826  call    ??$As@UIInternalCustomDestinationList@@@?$ComPtr@UICustomDestinationList@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInternalCustomDestinationList@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ICustomDestinationList>::As<IInternalCustomDestinationList>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInternalCustomDestinationList>>)
0x1800c482b  mov     ebx, eax
0x1800c482d  test    eax, eax
0x1800c482f  jns     short loc_1800C4859
0x1800c4831  mov     rcx, [rbp+5Fh]; this
0x1800c4835  mov     r9d, eax; char *
0x1800c4838  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800c483f  mov     edx, 229h; void *
0x1800c4844  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4849  nop
0x1800c484a  lea     rcx, [rsp+130h+var_100]
0x1800c484f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c4854  jmp     loc_1800C4F0A
0x1800c4859  mov     [rsp+130h+var_F0], r12
0x1800c485e  lea     rcx, [rbp+57h+pv]; string
0x1800c4862  call    ??$?0$0CA@@StringReference@Internal@Windows@@QEAA@AEAY0CA@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[32])
0x1800c4867  lea     rdx, [rsp+130h+var_F0]
0x1800c486c  mov     rcx, [rax]
0x1800c486f  call    ??$GetActivationFactory@V?$ComPtr@UIJumpListStatics@StartScreen@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJumpListStatics@StartScreen@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::StartScreen::IJumpListStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::StartScreen::IJumpListStatics>>)
0x1800c4874  mov     ebx, eax
0x1800c4876  test    eax, eax
0x1800c4878  jns     short loc_1800C489F
0x1800c487a  mov     rcx, [rbp+5Fh]; this
0x1800c487e  mov     r9d, eax; char *
0x1800c4881  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800c4888  mov     edx, 22Ch; void *
0x1800c488d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4892  nop
0x1800c4893  lea     rcx, [rsp+130h+var_F0]
0x1800c4898  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c489d  jmp     short loc_1800C484A
0x1800c489f  mov     [rsp+130h+var_E0], r12
0x1800c48a4  lea     rdx, [rsp+130h+var_E0]
0x1800c48a9  lea     rcx, [rsp+130h+var_F0]
0x1800c48ae  call    ??$As@UIJumpListSerializationStatics@StartScreen@UI@Internal@Windows@@@?$ComPtr@UIJumpListStatics@StartScreen@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJumpListSerializationStatics@StartScreen@UI@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::StartScreen::IJumpListStatics>::As<Windows::Internal::UI::StartScreen::IJumpListSerializationStatics>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::UI::StartScreen::IJumpListSerializationStatics>>)
0x1800c48b3  mov     ebx, eax
0x1800c48b5  test    eax, eax
0x1800c48b7  jns     short loc_1800C48DE
0x1800c48b9  mov     rcx, [rbp+5Fh]; this
0x1800c48bd  mov     r9d, eax; char *
0x1800c48c0  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800c48c7  mov     edx, 22Fh; void *
0x1800c48cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c48d1  nop
0x1800c48d2  lea     rcx, [rsp+130h+var_E0]
0x1800c48d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c48dc  jmp     short loc_1800C4893
0x1800c48de  mov     [rsp+130h+var_F8], r12
0x1800c48e3  mov     rdi, [rsp+130h+var_E0]
0x1800c48e8  mov     rax, [rdi]
0x1800c48eb  mov     rbx, [rax+30h]
0x1800c48ef  lea     rcx, [rsp+130h+var_F8]
0x1800c48f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c48f9  lea     r8, [rsp+130h+var_F8]
0x1800c48fe  mov     rdx, cs:string
0x1800c4905  mov     rcx, rdi
0x1800c4908  mov     rax, rbx
0x1800c490b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4910  mov     ebx, eax
0x1800c4912  test    eax, eax
0x1800c4914  jns     short loc_1800C493B
0x1800c4916  mov     rcx, [rbp+5Fh]; this
0x1800c491a  mov     r9d, eax; char *
0x1800c491d  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800c4924  mov     edx, 232h; void *
0x1800c4929  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c492e  nop
0x1800c492f  lea     rcx, [rsp+130h+var_F8]
0x1800c4934  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c4939  jmp     short loc_1800C48D2
0x1800c493b  mov     [rsp+130h+var_E8], r12
0x1800c4940  mov     rdi, [rsp+130h+var_F8]
0x1800c4945  mov     rax, [rdi]
0x1800c4948  mov     rbx, [rax+30h]
0x1800c494c  lea     rcx, [rsp+130h+var_E8]
0x1800c4951  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c4956  lea     rdx, [rsp+130h+var_E8]
0x1800c495b  mov     rcx, rdi
0x1800c495e  mov     rax, rbx
0x1800c4961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4966  mov     ebx, eax
0x1800c4968  test    eax, eax
0x1800c496a  jns     short loc_1800C4991
0x1800c496c  mov     edx, 235h; void *
0x1800c4971  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800c4978  mov     r9d, eax; char *
0x1800c497b  mov     rcx, [rbp+5Fh]; this
0x1800c497f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4984  nop
0x1800c4985  lea     rcx, [rsp+130h+var_E8]
0x1800c498a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c498f  jmp     short loc_1800C492F
0x1800c4991  mov     [rbp+57h+var_BC], r12d
0x1800c4995  mov     rcx, [rsp+130h+var_100]
0x1800c499a  mov     rax, [rcx]
0x1800c499d  lea     rdx, [rbp+57h+var_BC]
0x1800c49a1  mov     rax, [rax+30h]
0x1800c49a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c49aa  mov     ebx, eax
0x1800c49ac  test    eax, eax
0x1800c49ae  jns     short loc_1800C49B7
0x1800c49b0  mov     edx, 23Ah
0x1800c49b5  jmp     short loc_1800C4971
0x1800c49b7  mov     r15d, 2
0x1800c49bd  mov     r14d, r12d
0x1800c49c0  cmp     [rbp+57h+var_BC], r12d
0x1800c49c4  jbe     loc_1800C4B75
0x1800c49ca  xorps   xmm0, xmm0
0x1800c49cd  xor     eax, eax
0x1800c49cf  movups  xmmword ptr [rbp+57h+pv], xmm0
0x1800c49d3  mov     [rbp+57h+var_60], rax
0x1800c49d7  mov     rcx, [rsp+130h+var_100]
0x1800c49dc  mov     rax, [rcx]
0x1800c49df  lea     r9, [rbp+57h+pv]
0x1800c49e3  mov     r8d, 1
0x1800c49e9  mov     edx, r14d
0x1800c49ec  mov     rax, [rax+38h]
0x1800c49f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c49f5  mov     ebx, eax
0x1800c49f7  test    eax, eax
0x1800c49f9  js      loc_1800C4C28
0x1800c49ff  lea     rax, [rbp+57h+pv]
0x1800c4a03  mov     [rbp+57h+var_88], rax
0x1800c4a07  mov     [rbp+57h+var_80], 1
0x1800c4a0b  mov     eax, dword ptr [rbp+57h+pv]
0x1800c4a0e  cmp     eax, 1
0x1800c4a11  jnz     short loc_1800C4A42
0x1800c4a13  mov     rcx, [rbp+57h+pv+8]
0x1800c4a17  cmp     ecx, 2
0x1800c4a1a  jnz     short loc_1800C4A24
0x1800c4a1c  mov     r15d, ecx
0x1800c4a1f  jmp     loc_1800C4B5A
0x1800c4a24  cmp     ecx, 1
0x1800c4a27  jnz     short loc_1800C4A31
0x1800c4a29  mov     r15d, ecx
0x1800c4a2c  jmp     loc_1800C4B5A
0x1800c4a31  cmp     ecx, 0FFFFFFFFh
0x1800c4a34  jnz     loc_1800C4B5A
0x1800c4a3a  mov     r15d, r12d
0x1800c4a3d  jmp     loc_1800C4B5A
0x1800c4a42  test    eax, 0FFFFFFFDh
0x1800c4a47  jnz     loc_1800C4B56
0x1800c4a4d  mov     [rbp+57h+var_D0], r12
0x1800c4a51  mov     rdi, [rsp+130h+var_100]
0x1800c4a56  mov     rax, [rdi]
0x1800c4a59  mov     rbx, [rax+48h]
0x1800c4a5d  lea     rcx, [rbp+57h+var_D0]
0x1800c4a61  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IImmersiveMonitor>>)
0x1800c4a66  mov     r9, rax
0x1800c4a69  lea     r8, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295
0x1800c4a70  mov     edx, r14d
0x1800c4a73  mov     rcx, rdi
0x1800c4a76  mov     rax, rbx
0x1800c4a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4a7e  mov     ebx, eax
0x1800c4a80  test    eax, eax
0x1800c4a82  js      loc_1800C4BEC
0x1800c4a88  mov     [rbp+57h+var_C0], r12d
0x1800c4a8c  mov     rcx, [rbp+57h+var_D0]
0x1800c4a90  mov     rax, [rcx]
0x1800c4a93  lea     rdx, [rbp+57h+var_C0]
0x1800c4a97  mov     rax, [rax+18h]
0x1800c4a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4aa0  mov     ebx, eax
0x1800c4aa2  test    eax, eax
0x1800c4aa4  js      loc_1800C4BE5
0x1800c4aaa  mov     esi, r12d
0x1800c4aad  cmp     [rbp+57h+var_C0], r12d
0x1800c4ab1  jbe     loc_1800C4B4A
0x1800c4ab7  mov     [rbp+57h+var_90], r12
0x1800c4abb  mov     rdi, [rbp+57h+var_D0]
0x1800c4abf  mov     rax, [rdi]
0x1800c4ac2  mov     rbx, [rax+20h]
0x1800c4ac6  lea     rcx, [rbp+57h+var_90]
0x1800c4aca  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIClassFactory@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIClassFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IClassFactory>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IClassFactory>>)
0x1800c4acf  mov     r9, rax
0x1800c4ad2  lea     r8, _GUID_00000000_0000_0000_c000_000000000046
0x1800c4ad9  mov     edx, esi
0x1800c4adb  mov     rcx, rdi
0x1800c4ade  mov     rax, rbx
0x1800c4ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4ae6  mov     ebx, eax
0x1800c4ae8  test    eax, eax
0x1800c4aea  js      loc_1800C4BC1
0x1800c4af0  mov     [rbp+57h+var_98], r12
0x1800c4af4  lea     rcx, [rbp+57h+var_98]
0x1800c4af8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c4afd  lea     r8, [rbp+57h+var_98]; struct Windows::UI::StartScreen::IJumpListItem **
0x1800c4b01  mov     rdx, [rbp+57h+var_90]; struct IUnknown *
0x1800c4b05  mov     rcx, r13; this
0x1800c4b08  call    ?CreateJumpListItemForShellObject@JumpListBrokered@StartScreen@UI@Internal@Windows@@AEAAJPEAUIUnknown@@PEAPEAUIJumpListItem@235@@Z; Windows::Internal::UI::StartScreen::JumpListBrokered::CreateJumpListItemForShellObject(IUnknown *,Windows::UI::StartScreen::IJumpListItem * *)
0x1800c4b0d  test    eax, eax
0x1800c4b0f  js      short loc_1800C4B2C
0x1800c4b11  mov     rcx, [rsp+130h+var_E8]
0x1800c4b16  mov     rax, [rcx]
0x1800c4b19  mov     rdx, [rbp+57h+var_98]
0x1800c4b1d  mov     rax, [rax+68h]
0x1800c4b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4b26  mov     ebx, eax
0x1800c4b28  test    eax, eax
0x1800c4b2a  js      short loc_1800C4B9D
0x1800c4b2c  lea     rcx, [rbp+57h+var_98]
0x1800c4b30  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c4b35  nop
0x1800c4b36  lea     rcx, [rbp+57h+var_90]
0x1800c4b3a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c4b3f  inc     esi
0x1800c4b41  cmp     esi, [rbp+57h+var_C0]
0x1800c4b44  jb      loc_1800C4AB7
0x1800c4b4a  lea     rcx, [rbp+57h+var_D0]
0x1800c4b4e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800c4b53  mov     eax, dword ptr [rbp+57h+pv]
0x1800c4b56  mov     rcx, [rbp+57h+pv+8]; pv
0x1800c4b5a  mov     [rbp+57h+var_80], r12b
0x1800c4b5e  test    eax, eax
0x1800c4b60  jnz     short loc_1800C4B68
0x1800c4b62  call    cs:__imp_CoTaskMemFree
0x1800c4b68  inc     r14d
0x1800c4b6b  cmp     r14d, [rbp+57h+var_BC]
0x1800c4b6f  jb      loc_1800C49CA
0x1800c4b75  mov     rcx, [rsp+130h+var_F8]
0x1800c4b7a  mov     rax, [rcx]
0x1800c4b7d  mov     edx, r15d
0x1800c4b80  mov     rax, [rax+40h]
0x1800c4b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4b89  mov     ebx, eax
0x1800c4b8b  test    eax, eax
0x1800c4b8d  jns     loc_1800C4C32
0x1800c4b93  mov     edx, 26Dh
0x1800c4b98  jmp     loc_1800C4971
0x1800c4b9d  mov     rcx, [rbp+5Fh]; this
0x1800c4ba1  mov     r9d, eax; char *
0x1800c4ba4  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800c4bab  mov     edx, 267h; void *
0x1800c4bb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4bb5  nop
0x1800c4bb6  lea     rcx, [rbp+57h+var_98]
0x1800c4bba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c4bbf  jmp     short loc_1800C4BDA
0x1800c4bc1  mov     rcx, [rbp+5Fh]; this
0x1800c4bc5  mov     r9d, eax; char *
0x1800c4bc8  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800c4bcf  mov     edx, 262h; void *
0x1800c4bd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4bd9  nop
0x1800c4bda  lea     rcx, [rbp+57h+var_90]
  ... truncated ...
```
