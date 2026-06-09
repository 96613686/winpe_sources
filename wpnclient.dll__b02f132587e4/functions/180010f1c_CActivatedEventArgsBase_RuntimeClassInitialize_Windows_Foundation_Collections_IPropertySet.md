# CActivatedEventArgsBase::RuntimeClassInitialize(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180010f1c`
- end: `0x1800119a9`
- name: `?RuntimeClassInitialize@CActivatedEventArgsBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `2701`
- prototype: `__int64 __fastcall(CActivatedEventArgsBase *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180010a54`

## callees

- `0x180005670`
- `0x1800070e8`
- `0x180010f1c`
- `0x180014440`
- `0x18001478c`
- `0x18001ff00`
- `0x18002eb18`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010fdf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010fdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010fc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010fc9`

## pseudocode

```c
__int64 __fastcall CActivatedEventArgsBase::RuntimeClassInitialize(
        CActivatedEventArgsBase *this,
        __int64 (__fastcall ***a2)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 **))
{
  __int64 (__fastcall **v2)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 **); // rax
  __int64 (__fastcall *v5)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 **); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 *v8; // rbx
  __int64 v9; // rdi
  HRESULT v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  __int64 *v14; // rdi
  int v15; // r15d
  __int64 (__fastcall *v16)(__int64 *, HSTRING, __int64 *); // rbx
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  __int64 *v20; // rdi
  int v21; // r14d
  __int64 (__fastcall *v22)(__int64 *, HSTRING, __int64 *); // rbx
  int v23; // eax
  int v24; // eax
  __int64 v25; // rdx
  __int64 *v26; // rdi
  int (__fastcall *v27)(__int64 *, HSTRING, _QWORD); // rbx
  __int64 (__fastcall ***v28)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v29)(_QWORD, GUID *, __int64 *); // rdi
  int v30; // eax
  __int64 *v31; // rdi
  int (__fastcall *v32)(__int64 *, HSTRING, _QWORD); // rbx
  __int64 (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v34)(_QWORD, GUID *, __int64 *); // rdi
  int v35; // eax
  __int64 *v36; // rdi
  __int64 (__fastcall *v37)(__int64 *, HSTRING, __int64 *); // rbx
  int v38; // eax
  int v39; // eax
  __int64 v40; // rdx
  __int64 *v41; // rdi
  __int64 (__fastcall *v42)(__int64 *, HSTRING, __int64 *); // rbx
  int v43; // eax
  int v44; // eax
  __int64 v45; // rdx
  __int64 *v46; // rdi
  __int64 (__fastcall *v47)(__int64 *, HSTRING, __int64 *); // rbx
  int v48; // eax
  int v49; // eax
  __int64 v50; // rdx
  __int64 *v51; // rdi
  __int64 (__fastcall *v52)(__int64 *, HSTRING, __int64 *); // rbx
  int v53; // eax
  int v54; // eax
  __int64 v55; // rdx
  __int64 *v56; // rdi
  __int64 (__fastcall *v57)(__int64 *, HSTRING, __int64 *); // rbx
  int v58; // eax
  int v59; // eax
  __int64 v60; // rdx
  __int64 v62; // rbx
  __int64 v63; // rbx
  bool v64; // zf
  __int128 v65; // xmm0
  int v66[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v67; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v68; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v69; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v70; // [rsp+40h] [rbp-C0h] BYREF
  char v71; // [rsp+48h] [rbp-B8h] BYREF
  char v72; // [rsp+49h] [rbp-B7h] BYREF
  _BYTE v73[6]; // [rsp+4Ah] [rbp-B6h] BYREF
  __int64 v74; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v75; // [rsp+58h] [rbp-A8h] BYREF
  __int64 (__fastcall ***v76)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-A0h] BYREF
  __int64 v77; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall ***v78)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-90h] BYREF
  __int64 v79; // [rsp+78h] [rbp-88h] BYREF
  __int64 v80; // [rsp+80h] [rbp-80h] BYREF
  __int64 v81; // [rsp+88h] [rbp-78h] BYREF
  __int64 v82; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v83; // [rsp+98h] [rbp-68h] BYREF
  __int64 v84; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v85; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v86; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v87; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v88; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v89; // [rsp+C8h] [rbp-38h] BYREF
  int v90; // [rsp+D0h] [rbp-30h] BYREF
  int v91; // [rsp+D4h] [rbp-2Ch] BYREF
  __int64 v92; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v93; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v94; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING string; // [rsp+108h] [rbp+8h] BYREF
  __int128 v97; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v2 = *a2;
  v83 = 0;
  v5 = *v2;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83);
  v6 = v5((struct Windows::Foundation::Collections::IPropertySet *)a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v83);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v6,
      v66[0]);
LABEL_84:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83);
    return v7;
  }
  v8 = v83;
  *(_QWORD *)v66 = 0;
  v9 = *v83;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v66);
  string = 0;
  v10 = WindowsCreateStringReference(L"ActivationKind", 0xEu, &hstringHeader, &string);
  if ( v10 < 0 )
  {
    RaiseException(v10, 1u, 0, 0);
    __debugbreak();
  }
  v11 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, int *))(v9 + 48))(v8, string, v66);
  v7 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v11,
      v66[0]);
LABEL_83:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v66);
    goto LABEL_84;
  }
  v67 = 0;
  v12 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(v66, &v67);
  v7 = v12;
  if ( v12 < 0 )
  {
    v13 = 201;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v12,
      v66[0]);
LABEL_82:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67);
    goto LABEL_83;
  }
  v90 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v67 + 96LL))(v67, &v90);
  v7 = v12;
  if ( v12 < 0 )
  {
    v13 = 203;
    goto LABEL_9;
  }
  v14 = v83;
  v15 = v90;
  v68 = 0;
  v16 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(*v83 + 48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"PreviousExecutionState", 0x17u, 0x16u);
  v17 = v16(v14, string, &v68);
  v7 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v17,
      v66[0]);
LABEL_81:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
    goto LABEL_82;
  }
  v69 = 0;
  v18 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v68, &v69);
  v7 = v18;
  if ( v18 < 0 )
  {
    v19 = 210;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v18,
      v66[0]);
LABEL_80:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
    goto LABEL_81;
  }
  v91 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v69 + 96LL))(v69, &v91);
  v7 = v18;
  if ( v18 < 0 )
  {
    v19 = 212;
    goto LABEL_16;
  }
  v20 = v83;
  v21 = v91;
  v93 = 0;
  v70 = 0;
  v22 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(*v83 + 48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UserContext", 0xCu, 0xBu);
  v23 = v22(v20, string, &v70);
  v7 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v23,
      v66[0]);
LABEL_79:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
    goto LABEL_80;
  }
  v74 = 0;
  v24 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v70, &v74);
  v7 = v24;
  if ( v24 < 0 )
  {
    v25 = 219;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v24,
      v66[0]);
LABEL_78:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
    goto LABEL_79;
  }
  v24 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v74 + 112LL))(v74, &v93);
  v7 = v24;
  if ( v24 < 0 )
  {
    v25 = 220;
    goto LABEL_23;
  }
  v26 = v83;
  v76 = 0;
  v75 = 0;
  v27 = *(int (__fastcall **)(__int64 *, HSTRING, _QWORD))(*v83 + 48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76);
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"SplashScreen", 0xDu, 0xCu);
  if ( v27(v26, string, &v76) >= 0 )
  {
    v28 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v76;
    v29 = **v76;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
    v30 = v29(v28, &GUID_ca4d975c_d4d6_43f0_97c0_0833c6391c24, &v75);
    v7 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE2,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
        (const char *)(unsigned int)v30,
        v66[0]);
LABEL_77:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76);
      goto LABEL_78;
    }
  }
  v31 = v83;
  v78 = 0;
  v77 = 0;
  v32 = *(int (__fastcall **)(__int64 *, HSTRING, _QWORD))(*v83 + 48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78);
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"ActivationValueSetReference",
    0x1Cu,
    0x1Bu);
  if ( v32(v31, string, &v78) >= 0 )
  {
    v33 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v78;
    v34 = **v78;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
    v35 = v34(v33, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, &v77);
    v7 = v35;
    if ( v35 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE9,
        (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
        (const char *)(unsigned int)v35,
        v66[0]);
LABEL_76:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78);
      goto LABEL_77;
    }
  }
  v36 = v83;
  v71 = 1;
  v79 = 0;
  v37 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(*v83 + 48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IsForeground", 0xDu, 0xCu);
  v38 = v37(v36, string, &v79);
  v7 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v38,
      v66[0]);
LABEL_75:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
    goto LABEL_76;
  }
  v80 = 0;
  v39 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v79, &v80);
  v7 = v39;
  if ( v39 < 0 )
  {
    v40 = 240;
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v40,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v39,
      v66[0]);
LABEL_74:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v80);
    goto LABEL_75;
  }
  v39 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v80 + 144LL))(v80, &v71);
  v7 = v39;
  if ( v39 < 0 )
  {
    v40 = 241;
    goto LABEL_36;
  }
  v41 = v83;
  v72 = 0;
  v81 = 0;
  v42 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(*v83 + 48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IsHolographic", 0xEu, 0xDu);
  v43 = v42(v41, string, &v81);
  v7 = v43;
  if ( v43 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v43,
      v66[0]);
LABEL_73:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
    goto LABEL_74;
  }
  v82 = 0;
  v44 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v81, &v82);
  v7 = v44;
  if ( v44 < 0 )
  {
    v45 = 247;
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v45,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v44,
      v66[0]);
LABEL_72:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
    goto LABEL_73;
  }
  v44 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v82 + 144LL))(v82, &v72);
  v7 = v44;
  if ( v44 < 0 )
  {
    v45 = 248;
    goto LABEL_43;
  }
  v46 = v83;
  v73[0] = 0;
  v84 = 0;
  v47 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(*v83 + 48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IsInitialized", 0xEu, 0xDu);
  v48 = v47(v46, string, &v84);
  v7 = v48;
  if ( v48 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFC,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v48,
      v66[0]);
LABEL_71:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
    goto LABEL_72;
  }
  v85 = 0;
  v49 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v84, &v85);
  v7 = v49;
  if ( v49 < 0 )
  {
    v50 = 254;
LABEL_50:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v50,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v49,
      v66[0]);
LABEL_70:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
    goto LABEL_71;
  }
  v49 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v85 + 144LL))(v85, v73);
  v7 = v49;
  if ( v49 < 0 )
  {
    v50 = 255;
    goto LABEL_50;
  }
  v51 = v83;
  v94 = 0;
  v86 = 0;
  v52 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(*v83 + 48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v86);
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AamActivationId", 0x10u, 0xFu);
  v53 = v52(v51, string, &v86);
  v7 = v53;
  if ( v53 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x103,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v53,
      v66[0]);
LABEL_69:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v86);
    goto LABEL_70;
  }
  v87 = 0;
  v54 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v86, &v87);
  v7 = v54;
  if ( v54 < 0 )
  {
    v55 = 261;
LABEL_57:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v55,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v54,
      v66[0]);
LABEL_68:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v87);
    goto LABEL_69;
  }
  v54 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v87 + 112LL))(v87, &v94);
  v7 = v54;
  if ( v54 < 0 )
  {
    v55 = 262;
    goto LABEL_57;
  }
  v56 = v83;
  v88 = 0;
  v97 = 0;
  v57 = *(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(*v83 + 48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v88);
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AamActivityId", 0xEu, 0xDu);
  v58 = v57(v56, string, &v88);
  v7 = v58;
  if ( v58 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10A,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v58,
      v66[0]);
LABEL_67:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v88);
    goto LABEL_68;
  }
  v92 = 0;
  v59 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v88, &v92);
  v7 = v59;
  if ( v59 < 0 )
  {
    v60 = 268;
LABEL_66:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v60,
      (unsigned int)"onecoreuap\\shell\\lib\\activationevents\\src\\activatedeventargsbase.cpp",
      (const char *)(unsigned int)v59,
      v66[0]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
    goto LABEL_67;
  }
  v59 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v92 + 160LL))(v92, &v97);
  v7 = v59;
  if ( v59 < 0 )
  {
    v60 = 269;
    goto LABEL_66;
  }
  v62 = v75;
  *((_QWORD *)this + 13) = v93;
  *((_DWORD *)this + 19) = v21;
  *((_DWORD *)this + 18) = v15;
  if ( *((_QWORD *)this + 11) != v62 )
  {
    v89 = v62;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v89);
    v89 = *((_QWORD *)this + 11);
    *((_QWORD *)this + 11) = v62;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89);
  }
  v63 = v77;
  if ( *((_QWORD *)this + 10) != v77 )
  {
    v89 = v77;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v89);
    v89 = *((_QWORD *)this + 10);
    *((_QWORD *)this + 10) = v63;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89);
  }
  v64 = v73[0] == 0;
  v65 = v97;
  *((_BYTE *)this + 102) = v71;
  *((_BYTE *)this + 112) = v72;
  *((_BYTE *)this + 101) = !v64;
  *((_QWORD *)this + 15) = v94;
  *((_OWORD *)this + 8) = v65;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v88);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v87);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v86);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v80);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v66);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83);
  return 0;
}

```

## disassembly

```asm
0x180010f1c  mov     [rsp-8+arg_10], rbx
0x180010f21  push    rbp
0x180010f22  push    rsi
0x180010f23  push    rdi
0x180010f24  push    r12
0x180010f26  push    r13
0x180010f28  push    r14
0x180010f2a  push    r15
0x180010f2c  lea     rbp, [rsp-30h]
0x180010f31  sub     rsp, 130h
0x180010f38  mov     rax, cs:__security_cookie
0x180010f3f  xor     rax, rsp
0x180010f42  mov     [rbp+60h+var_40], rax
0x180010f46  mov     rax, [rdx]
0x180010f49  mov     rsi, rcx
0x180010f4c  xor     r12d, r12d
0x180010f4f  lea     rcx, [rbp+60h+var_C8]
0x180010f53  mov     rdi, rdx
0x180010f56  mov     [rbp+60h+var_C8], r12
0x180010f5a  mov     rbx, [rax]
0x180010f5d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010f62  lea     r8, [rbp+60h+var_C8]
0x180010f66  mov     rcx, rdi
0x180010f69  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180010f70  mov     rax, rbx
0x180010f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f78  mov     ebx, eax
0x180010f7a  test    eax, eax
0x180010f7c  jns     short loc_180010F9B
0x180010f7e  mov     rcx, [rbp+68h]; this
0x180010f82  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180010f89  mov     r9d, eax; char *
0x180010f8c  mov     edx, 0C3h; void *
0x180010f91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010f96  jmp     loc_180011811
0x180010f9b  mov     rbx, [rbp+60h+var_C8]
0x180010f9f  lea     rcx, [rsp+160h+var_140]
0x180010fa4  mov     qword ptr [rsp+160h+var_140], r12; int
0x180010fa9  mov     rdi, [rbx]
0x180010fac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010fb1  lea     r9, [rbp+60h+string]; string
0x180010fb5  mov     [rbp+60h+string], r12
0x180010fb9  lea     r8, [rbp+60h+hstringHeader]; hstringHeader
0x180010fbd  mov     edx, 0Eh; length
0x180010fc2  lea     rcx, aActivationkind; "ActivationKind"
0x180010fc9  call    cs:__imp_WindowsCreateStringReference
0x180010fcf  test    eax, eax
0x180010fd1  jns     short loc_180010FE6
0x180010fd3  xor     r9d, r9d; lpArguments
0x180010fd6  xor     r8d, r8d; nNumberOfArguments
0x180010fd9  mov     ecx, eax; dwExceptionCode
0x180010fdb  lea     edx, [r9+1]; dwExceptionFlags
0x180010fdf  call    cs:__imp_RaiseException
0x180010fe5  int     3; Trap to Debugger
0x180010fe6  mov     rdx, [rbp+60h+string]
0x180010fea  lea     r8, [rsp+160h+var_140]
0x180010fef  mov     rax, [rdi+30h]
0x180010ff3  mov     rcx, rbx
0x180010ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ffb  mov     ebx, eax
0x180010ffd  test    eax, eax
0x180010fff  jns     short loc_18001101E
0x180011001  mov     rcx, [rbp+68h]; this
0x180011005  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x18001100c  mov     r9d, eax; char *
0x18001100f  mov     edx, 0C7h; void *
0x180011014  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011019  jmp     loc_180011807
0x18001101e  lea     rdx, [rsp+160h+var_138]
0x180011023  mov     [rsp+160h+var_138], r12
0x180011028  lea     rcx, [rsp+160h+var_140]
0x18001102d  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x180011032  mov     ebx, eax
0x180011034  test    eax, eax
0x180011036  jns     short loc_180011055
0x180011038  mov     edx, 0C9h; void *
0x18001103d  mov     rcx, [rbp+68h]; this
0x180011041  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180011048  mov     r9d, eax; char *
0x18001104b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011050  jmp     loc_1800117FD
0x180011055  mov     rcx, [rsp+160h+var_138]
0x18001105a  lea     rdx, [rbp+60h+var_90]
0x18001105e  mov     [rbp+60h+var_90], r12d
0x180011062  mov     rax, [rcx]
0x180011065  mov     rax, [rax+60h]
0x180011069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001106e  mov     ebx, eax
0x180011070  test    eax, eax
0x180011072  jns     short loc_18001107B
0x180011074  mov     edx, 0CBh
0x180011079  jmp     short loc_18001103D
0x18001107b  mov     rdi, [rbp+60h+var_C8]
0x18001107f  lea     rcx, [rsp+160h+var_130]
0x180011084  mov     r15d, [rbp+60h+var_90]
0x180011088  mov     [rsp+160h+var_130], r12
0x18001108d  mov     rax, [rdi]
0x180011090  mov     rbx, [rax+30h]
0x180011094  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011099  mov     r9d, 16h; unsigned int
0x18001109f  mov     [rbp+60h+string], r12
0x1800110a3  lea     rdx, aPreviousexecut; "PreviousExecutionState"
0x1800110aa  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x1800110ae  lea     r8d, [r9+1]; unsigned int
0x1800110b2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800110b7  mov     rdx, [rbp+60h+string]
0x1800110bb  lea     r8, [rsp+160h+var_130]
0x1800110c0  mov     rcx, rdi
0x1800110c3  mov     rax, rbx
0x1800110c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110cb  mov     ebx, eax
0x1800110cd  test    eax, eax
0x1800110cf  jns     short loc_1800110EE
0x1800110d1  mov     rcx, [rbp+68h]; this
0x1800110d5  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800110dc  mov     r9d, eax; char *
0x1800110df  mov     edx, 0D0h; void *
0x1800110e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800110e9  jmp     loc_1800117F3
0x1800110ee  lea     rdx, [rsp+160h+var_128]
0x1800110f3  mov     [rsp+160h+var_128], r12
0x1800110f8  lea     rcx, [rsp+160h+var_130]
0x1800110fd  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x180011102  mov     ebx, eax
0x180011104  test    eax, eax
0x180011106  jns     short loc_180011125
0x180011108  mov     edx, 0D2h; void *
0x18001110d  mov     rcx, [rbp+68h]; this
0x180011111  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180011118  mov     r9d, eax; char *
0x18001111b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011120  jmp     loc_1800117E9
0x180011125  mov     rcx, [rsp+160h+var_128]
0x18001112a  lea     rdx, [rbp+60h+var_8C]
0x18001112e  mov     [rbp+60h+var_8C], r12d
0x180011132  mov     rax, [rcx]
0x180011135  mov     rax, [rax+60h]
0x180011139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001113e  mov     ebx, eax
0x180011140  test    eax, eax
0x180011142  jns     short loc_18001114B
0x180011144  mov     edx, 0D4h
0x180011149  jmp     short loc_18001110D
0x18001114b  mov     rdi, [rbp+60h+var_C8]
0x18001114f  lea     rcx, [rsp+160h+var_120]
0x180011154  mov     r14d, [rbp+60h+var_8C]
0x180011158  mov     [rbp+60h+var_80], r12
0x18001115c  mov     [rsp+160h+var_120], r12
0x180011161  mov     rax, [rdi]
0x180011164  mov     rbx, [rax+30h]
0x180011168  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001116d  mov     r9d, 0Bh; unsigned int
0x180011173  mov     [rbp+60h+string], r12
0x180011177  lea     rdx, aUsercontext; "UserContext"
0x18001117e  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x180011182  lea     r13d, [r9+1]
0x180011186  mov     r8d, r13d; unsigned int
0x180011189  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001118e  mov     rdx, [rbp+60h+string]
0x180011192  lea     r8, [rsp+160h+var_120]
0x180011197  mov     rcx, rdi
0x18001119a  mov     rax, rbx
0x18001119d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111a2  mov     ebx, eax
0x1800111a4  test    eax, eax
0x1800111a6  jns     short loc_1800111C5
0x1800111a8  mov     rcx, [rbp+68h]; this
0x1800111ac  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800111b3  mov     r9d, eax; char *
0x1800111b6  mov     edx, 0D9h; void *
0x1800111bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800111c0  jmp     loc_1800117DF
0x1800111c5  lea     rdx, [rsp+160h+var_110]
0x1800111ca  mov     [rsp+160h+var_110], r12
0x1800111cf  lea     rcx, [rsp+160h+var_120]
0x1800111d4  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x1800111d9  mov     ebx, eax
0x1800111db  test    eax, eax
0x1800111dd  jns     short loc_1800111FC
0x1800111df  mov     edx, 0DBh; void *
0x1800111e4  mov     rcx, [rbp+68h]; this
0x1800111e8  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800111ef  mov     r9d, eax; char *
0x1800111f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800111f7  jmp     loc_1800117D5
0x1800111fc  mov     rcx, [rsp+160h+var_110]
0x180011201  lea     rdx, [rbp+60h+var_80]
0x180011205  mov     rax, [rcx]
0x180011208  mov     rax, [rax+70h]
0x18001120c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011211  mov     ebx, eax
0x180011213  test    eax, eax
0x180011215  jns     short loc_18001121E
0x180011217  mov     edx, 0DCh
0x18001121c  jmp     short loc_1800111E4
0x18001121e  mov     rdi, [rbp+60h+var_C8]
0x180011222  lea     rcx, [rsp+160h+var_100]
0x180011227  mov     [rsp+160h+var_100], r12
0x18001122c  mov     [rsp+160h+var_108], r12
0x180011231  mov     rax, [rdi]
0x180011234  mov     rbx, [rax+30h]
0x180011238  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001123d  mov     r9d, r13d; unsigned int
0x180011240  mov     [rbp+60h+string], r12
0x180011244  mov     r13d, 0Dh
0x18001124a  lea     rdx, aSplashscreen; "SplashScreen"
0x180011251  mov     r8d, r13d; unsigned int
0x180011254  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x180011258  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001125d  mov     rdx, [rbp+60h+string]
0x180011261  lea     r8, [rsp+160h+var_100]
0x180011266  mov     rcx, rdi
0x180011269  mov     rax, rbx
0x18001126c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011271  test    eax, eax
0x180011273  js      short loc_1800112C4
0x180011275  mov     rbx, [rsp+160h+var_100]
0x18001127a  lea     rcx, [rsp+160h+var_108]
0x18001127f  mov     rax, [rbx]
0x180011282  mov     rdi, [rax]
0x180011285  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001128a  lea     r8, [rsp+160h+var_108]
0x18001128f  mov     rcx, rbx
0x180011292  lea     rdx, _GUID_ca4d975c_d4d6_43f0_97c0_0833c6391c24
0x180011299  mov     rax, rdi
0x18001129c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112a1  mov     ebx, eax
0x1800112a3  test    eax, eax
0x1800112a5  jns     short loc_1800112C4
0x1800112a7  mov     rcx, [rbp+68h]; this
0x1800112ab  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800112b2  mov     r9d, eax; char *
0x1800112b5  mov     edx, 0E2h; void *
0x1800112ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800112bf  jmp     loc_1800117C1
0x1800112c4  mov     rdi, [rbp+60h+var_C8]
0x1800112c8  lea     rcx, [rsp+160h+var_F0]
0x1800112cd  mov     [rsp+160h+var_F0], r12
0x1800112d2  mov     [rsp+160h+var_F8], r12
0x1800112d7  mov     rax, [rdi]
0x1800112da  mov     rbx, [rax+30h]
0x1800112de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800112e3  mov     r9d, 1Bh; unsigned int
0x1800112e9  mov     [rbp+60h+string], r12
0x1800112ed  lea     rdx, aActivationvalu; "ActivationValueSetReference"
0x1800112f4  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x1800112f8  lea     r8d, [r9+1]; unsigned int
0x1800112fc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180011301  mov     rdx, [rbp+60h+string]
0x180011305  lea     r8, [rsp+160h+var_F0]
0x18001130a  mov     rcx, rdi
0x18001130d  mov     rax, rbx
0x180011310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011315  test    eax, eax
0x180011317  js      short loc_180011368
0x180011319  mov     rbx, [rsp+160h+var_F0]
0x18001131e  lea     rcx, [rsp+160h+var_F8]
0x180011323  mov     rax, [rbx]
0x180011326  mov     rdi, [rax]
0x180011329  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001132e  lea     r8, [rsp+160h+var_F8]
0x180011333  mov     rcx, rbx
0x180011336  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18001133d  mov     rax, rdi
0x180011340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011345  mov     ebx, eax
0x180011347  test    eax, eax
0x180011349  jns     short loc_180011368
0x18001134b  mov     rcx, [rbp+68h]; this
0x18001134f  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x180011356  mov     r9d, eax; char *
0x180011359  mov     edx, 0E9h; void *
0x18001135e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011363  jmp     loc_1800117AD
0x180011368  mov     rdi, [rbp+60h+var_C8]
0x18001136c  lea     rcx, [rsp+160h+var_E8]
0x180011371  mov     [rsp+160h+var_118], 1
0x180011376  mov     [rsp+160h+var_E8], r12
0x18001137b  mov     rax, [rdi]
0x18001137e  mov     rbx, [rax+30h]
0x180011382  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011387  mov     r9d, 0Ch; unsigned int
0x18001138d  mov     [rbp+60h+string], r12
0x180011391  mov     r8d, r13d; unsigned int
0x180011394  lea     rdx, aIsforeground; "IsForeground"
0x18001139b  lea     rcx, [rbp+60h+hstringHeader]; hstringHeader
0x18001139f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800113a4  mov     rdx, [rbp+60h+string]
0x1800113a8  lea     r8, [rsp+160h+var_E8]
0x1800113ad  mov     rcx, rdi
0x1800113b0  mov     rax, rbx
0x1800113b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113b8  mov     ebx, eax
0x1800113ba  test    eax, eax
0x1800113bc  jns     short loc_1800113DB
0x1800113be  mov     rcx, [rbp+68h]; this
0x1800113c2  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\lib\\activationevent"...
0x1800113c9  mov     r9d, eax; char *
0x1800113cc  mov     edx, 0EEh; void *
0x1800113d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
