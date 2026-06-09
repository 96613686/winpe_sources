# GetAccountLastSyncTime(PhoneInternal::Experiences::Sync::IAccount *,_FILETIME *,_FILETIME *)

- ea: `0x18002b908`
- end: `0x18002c01d`
- name: `?GetAccountLastSyncTime@@YAJPEAUIAccount@Sync@Experiences@PhoneInternal@@PEAU_FILETIME@@1@Z`
- size: `1813`
- prototype: `__int64 __fastcall(struct PhoneInternal::Experiences::Sync::IAccount *, struct _FILETIME *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002c570`

## callees

- `0x180004658`
- `0x180008f0c`
- `0x18002b908`
- `0x18002c060`
- `0x18002c1c4`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002bf19`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002bf19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b959`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b959`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b9a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b9d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bd17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bd25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bdd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bde4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002be69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002be77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b9a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b9d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bd17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bd25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bdd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bde4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002be69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002be77`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b982`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b982`

## string_xrefs

- `0x18002bd80`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x18002be0d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x18002bea7`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x18002bf26`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x18002bf4b`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x18002bf71`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x18002bf9f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x18002bfbd`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`

## pseudocode

```c
__int64 __fastcall GetAccountLastSyncTime(
        struct PhoneInternal::Experiences::Sync::IAccount *a1,
        struct _FILETIME *a2,
        struct _FILETIME *a3)
{
  HRESULT v6; // eax
  HSTRING v7; // rbx
  int ActivationFactory; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  __int64 v15; // rcx
  int v16; // eax
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall *v18)(_QWORD, GUID *, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v23)(_QWORD, GUID *, __int64 *); // rdi
  int v24; // eax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING, _QWORD); // rbx
  int v27; // eax
  __int64 (__fastcall ***v28)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v29)(_QWORD, GUID *, __int64 *); // rdi
  DWORD v30; // rax^4
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, HSTRING, _QWORD); // rbx
  __int64 (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v34)(_QWORD, GUID *, __int64 *); // rdi
  int v35; // eax
  DWORD v36; // rax^4
  __int64 v37; // rcx
  __int64 (__fastcall ***v38)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v39; // rcx
  __int64 (__fastcall ***v40)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v44; // r9
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 (__fastcall ***v47)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v48)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 (__fastcall ***v52)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v53; // rcx
  __int64 v54; // r9
  __int64 v55; // r9
  __int64 v56; // r9
  HSTRING v57; // [rsp+30h] [rbp-69h] BYREF
  HSTRING v58; // [rsp+38h] [rbp-61h] BYREF
  __int64 (__fastcall ***v59)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-59h] BYREF
  __int64 v60; // [rsp+48h] [rbp-51h] BYREF
  __int64 v61; // [rsp+50h] [rbp-49h] BYREF
  __int64 (__fastcall ***v62)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-41h] BYREF
  __int64 v63; // [rsp+60h] [rbp-39h] BYREF
  __int64 (__fastcall ***v64)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-31h] BYREF
  __int64 v65; // [rsp+70h] [rbp-29h] BYREF
  __int64 v66; // [rsp+78h] [rbp-21h] BYREF
  struct PhoneInternal::Experiences::Sync::IAccount *v67; // [rsp+80h] [rbp-19h] BYREF
  __int64 (__fastcall *v68)(); // [rsp+88h] [rbp-11h] BYREF
  __int64 v69; // [rsp+90h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-1h] BYREF
  HSTRING string; // [rsp+B0h] [rbp+17h] BYREF

  v65 = 0;
  string = 0;
  v6 = WindowsCreateStringReference(L"PhoneInternal.Experiences.Sync.AccountProperties", 0x30u, &hstringHeader, &string);
  if ( v6 < 0 )
  {
    RaiseException(v6, 1u, 0, 0);
    __debugbreak();
  }
  v7 = string;
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v65);
  ActivationFactory = RoGetActivationFactory(v7, &GUID_6e9ae4b1_61fd_4978_b813_82bc96870769, &v65);
  v9 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    Log_HREvent(
      (unsigned int)ActivationFactory,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
      76);
    goto LABEL_45;
  }
  v10 = v65;
  v58 = 0;
  v57 = 0;
  v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v65 + 80LL);
  WindowsDeleteString(0);
  v58 = 0;
  v12 = v11(v10, &v58);
  v9 = v12;
  if ( v12 < 0 )
  {
    v54 = 81;
LABEL_67:
    Log_HREvent(
      (unsigned int)v12,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
      v54);
    goto LABEL_44;
  }
  v13 = v65;
  v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v65 + 88LL);
  WindowsDeleteString(v57);
  v57 = 0;
  v12 = v14(v13, &v57);
  v9 = v12;
  if ( v12 < 0 )
  {
    v54 = 82;
    goto LABEL_67;
  }
  v64 = 0;
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v64);
  v16 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
          v15,
          &v64);
  v9 = v16;
  if ( v16 < 0 )
  {
    v55 = 85;
LABEL_70:
    Log_HREvent(
      (unsigned int)v16,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
      v55);
    goto LABEL_43;
  }
  v17 = v64;
  v16 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), HSTRING))(*v64)[13])(v64, v58);
  v9 = v16;
  if ( v16 < 0 )
  {
    v55 = 87;
    goto LABEL_70;
  }
  v16 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), HSTRING))(*v17)[13])(v17, v57);
  v9 = v16;
  if ( v16 < 0 )
  {
    v55 = 88;
    goto LABEL_70;
  }
  v60 = 0;
  v18 = **v17;
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v60);
  v19 = v18(v17, &GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e, &v60);
  v9 = v19;
  if ( v19 < 0 )
  {
    v56 = 91;
LABEL_74:
    Log_HREvent(
      (unsigned int)v19,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
      v56);
LABEL_42:
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v60);
LABEL_43:
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v64);
LABEL_44:
    WindowsDeleteString(v57);
    v57 = 0;
    WindowsDeleteString(v58);
    v58 = 0;
LABEL_45:
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v65);
    return v9;
  }
  v69 = v60;
  v68 =  PhoneInternal::Experiences::Sync::IAccount::`vcall'{184,{flat}};
  hstringHeader.Reserved.Reserved1 = &v67;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v68;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = &v69;
  v67 = a1;
  v19 = AwaitActionHelper<_lambda_82912b960cd7550f8286aff6609e2f4b_>(&hstringHeader);
  v9 = v19;
  if ( v19 < 0 )
  {
    v56 = 93;
    goto LABEL_74;
  }
  v20 = *(_QWORD *)a1;
  v59 = 0;
  v21 = (*(__int64 (__fastcall **)(struct PhoneInternal::Experiences::Sync::IAccount *, __int64, _QWORD))(v20 + 192))(
          a1,
          v60,
          &v59);
  v9 = v21;
  if ( v21 < 0 )
  {
    Log_HREvent(
      (unsigned int)v21,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
      96);
LABEL_48:
    v48 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
    if ( v59 )
    {
      v59 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v48)[2])(v48);
    }
    v49 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    }
    if ( v17 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v17)[2])(v17);
    WindowsDeleteString(v57);
    v57 = 0;
    WindowsDeleteString(v58);
    v50 = v65;
    v58 = 0;
    if ( v65 )
    {
      v65 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    }
    return v9;
  }
  v22 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
  v63 = 0;
  v23 = **v59;
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v63);
  v24 = v23(v22, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v63);
  v9 = v24;
  if ( v24 < 0 )
  {
    Log_HREvent(
      (unsigned int)v24,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
      99);
LABEL_40:
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v63);
    v47 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
    if ( v59 )
    {
      v59 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v47)[2])(v47);
    }
    goto LABEL_42;
  }
  v25 = v63;
  v62 = 0;
  v61 = 0;
  v66 = 0;
  v26 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v63 + 48LL);
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v62);
  v27 = v26(v25, v58, &v62);
  v9 = v27;
  if ( v27 < 0 )
  {
    v44 = 105;
LABEL_78:
    v46 = (unsigned int)v27;
LABEL_85:
    v45 = 1;
    goto LABEL_39;
  }
  v28 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v62;
  if ( !v62 )
  {
    v44 = 106;
    goto LABEL_38;
  }
  v29 = **v62;
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v61);
  v27 = v29(v28, &GUID_5541d8a7_497c_5aa4_86fc_7713adbf2a2c, &v61);
  v9 = v27;
  if ( v27 < 0 )
  {
    v44 = 107;
    goto LABEL_78;
  }
  v27 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 48LL))(v61, &v66);
  v9 = v27;
  if ( v27 < 0 )
  {
    v44 = 108;
    goto LABEL_78;
  }
  v30 = HIDWORD(v66);
  if ( v66 < 0 )
  {
    v44 = 110;
    goto LABEL_84;
  }
  v31 = v63;
  a2->dwLowDateTime = v66;
  a2->dwHighDateTime = v30;
  v32 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v31 + 48LL);
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v62);
  v27 = v32(v31, v57, &v62);
  v9 = v27;
  if ( v27 < 0 )
  {
    v44 = 112;
    goto LABEL_78;
  }
  v33 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v62;
  if ( !v62 )
  {
    v44 = 113;
LABEL_38:
    v9 = -2147023728;
    v45 = 0;
    v46 = 2147943568LL;
LABEL_39:
    Log_HREvent(
      v46,
      v45,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
      v44);
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v61);
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v62);
    goto LABEL_40;
  }
  v34 = **v62;
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v61);
  v27 = v34(v33, &GUID_5541d8a7_497c_5aa4_86fc_7713adbf2a2c, &v61);
  v9 = v27;
  if ( v27 < 0 )
  {
    v44 = 114;
    goto LABEL_78;
  }
  v35 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 48LL))(v61, &v66);
  v9 = v35;
  if ( v35 < 0 )
  {
    Log_HREvent(
      (unsigned int)v35,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\onesynchelper.cpp",
      115);
    v51 = v61;
    if ( v61 )
    {
      v61 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
    v52 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v62;
    if ( v62 )
    {
      v62 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v52)[2])(v52);
    }
    v53 = v63;
    if ( v63 )
    {
      v63 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    }
    goto LABEL_48;
  }
  v36 = HIDWORD(v66);
  if ( v66 < 0 )
  {
    v44 = 117;
LABEL_84:
    v9 = -2147483637;
    v46 = 2147483659LL;
    goto LABEL_85;
  }
  v37 = v61;
  a3->dwLowDateTime = v66;
  a3->dwHighDateTime = v36;
  if ( v37 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  v38 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v62;
  if ( v62 )
  {
    v62 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v38)[2])(v38);
  }
  v39 = v63;
  if ( v63 )
  {
    v63 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
  v40 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
  if ( v59 )
  {
    v59 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v40)[2])(v40);
  }
  v41 = v60;
  if ( v60 )
  {
    v60 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  if ( v17 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v17)[2])(v17);
  WindowsDeleteString(v57);
  v57 = 0;
  WindowsDeleteString(v58);
  v42 = v65;
  v58 = 0;
  if ( v65 )
  {
    v65 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  }
  return 0;
}

```

## disassembly

```asm
0x18002b908  mov     [rsp-8+arg_18], rbx
0x18002b90d  push    rbp
0x18002b90e  push    rsi
0x18002b90f  push    rdi
0x18002b910  push    r12
0x18002b912  push    r13
0x18002b914  push    r14
0x18002b916  push    r15
0x18002b918  lea     rbp, [rsp-27h]
0x18002b91d  sub     rsp, 0C0h
0x18002b924  mov     rax, cs:__security_cookie
0x18002b92b  xor     rax, rsp
0x18002b92e  mov     [rbp+57h+var_38], rax
0x18002b932  xor     r13d, r13d
0x18002b935  lea     r9, [rbp+57h+string]; string
0x18002b939  mov     r15, r8
0x18002b93c  mov     [rbp+57h+var_80], r13
0x18002b940  mov     r12, rdx
0x18002b943  mov     [rbp+57h+string], r13
0x18002b947  mov     r14, rcx
0x18002b94a  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18002b94e  lea     edx, [r13+30h]; length
0x18002b952  lea     rcx, ?RuntimeClass_PhoneInternal_Experiences_Sync_AccountProperties@@3QBGB; "PhoneInternal.Experiences.Sync.AccountP"...
0x18002b959  call    cs:__imp_WindowsCreateStringReference
0x18002b95f  test    eax, eax
0x18002b961  js      loc_18002BF0D
0x18002b967  mov     rbx, [rbp+57h+string]
0x18002b96b  lea     rcx, [rbp+57h+var_80]
0x18002b96f  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x18002b974  lea     r8, [rbp+57h+var_80]
0x18002b978  mov     rcx, rbx
0x18002b97b  lea     rdx, _GUID_6e9ae4b1_61fd_4978_b813_82bc96870769
0x18002b982  call    cs:__imp_RoGetActivationFactory
0x18002b988  mov     ebx, eax
0x18002b98a  test    eax, eax
0x18002b98c  js      loc_18002BF20
0x18002b992  mov     rdi, [rbp+57h+var_80]
0x18002b996  xor     ecx, ecx; string
0x18002b998  mov     [rbp+57h+var_B8], r13
0x18002b99c  mov     [rbp+57h+var_C0], r13
0x18002b9a0  mov     rax, [rdi]
0x18002b9a3  mov     rbx, [rax+50h]
0x18002b9a7  call    cs:__imp_WindowsDeleteString
0x18002b9ad  lea     rdx, [rbp+57h+var_B8]
0x18002b9b1  mov     [rbp+57h+var_B8], r13
0x18002b9b5  mov     rcx, rdi
0x18002b9b8  mov     rax, rbx
0x18002b9bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9c0  mov     ebx, eax
0x18002b9c2  test    eax, eax
0x18002b9c4  js      loc_18002BF3D
0x18002b9ca  mov     rdi, [rbp+57h+var_80]
0x18002b9ce  mov     rcx, [rbp+57h+var_C0]; string
0x18002b9d2  mov     rax, [rdi]
0x18002b9d5  mov     rbx, [rax+58h]
0x18002b9d9  call    cs:__imp_WindowsDeleteString
0x18002b9df  lea     rdx, [rbp+57h+var_C0]
0x18002b9e3  mov     [rbp+57h+var_C0], r13
0x18002b9e7  mov     rcx, rdi
0x18002b9ea  mov     rax, rbx
0x18002b9ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9f2  mov     ebx, eax
0x18002b9f4  test    eax, eax
0x18002b9f6  js      loc_18002BF45
0x18002b9fc  lea     rcx, [rbp+57h+var_88]
0x18002ba00  mov     [rbp+57h+var_88], r13
0x18002ba04  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x18002ba09  lea     rdx, [rbp+57h+var_88]
0x18002ba0d  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x18002ba12  mov     ebx, eax
0x18002ba14  test    eax, eax
0x18002ba16  js      loc_18002BF63
0x18002ba1c  mov     rsi, [rbp+57h+var_88]
0x18002ba20  mov     rdx, [rbp+57h+var_B8]
0x18002ba24  mov     rcx, rsi
0x18002ba27  mov     rax, [rsi]
0x18002ba2a  mov     rax, [rax+68h]
0x18002ba2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba33  mov     ebx, eax
0x18002ba35  test    eax, eax
0x18002ba37  js      loc_18002BF89
0x18002ba3d  mov     rax, [rsi]
0x18002ba40  mov     rcx, rsi
0x18002ba43  mov     rdx, [rbp+57h+var_C0]
0x18002ba47  mov     rax, [rax+68h]
0x18002ba4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba50  mov     ebx, eax
0x18002ba52  test    eax, eax
0x18002ba54  js      loc_18002BF6B
0x18002ba5a  mov     [rbp+57h+var_A8], r13
0x18002ba5e  lea     rcx, [rbp+57h+var_A8]
0x18002ba62  mov     rax, [rsi]
0x18002ba65  mov     rbx, [rax]
0x18002ba68  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x18002ba6d  lea     r8, [rbp+57h+var_A8]
0x18002ba71  mov     rcx, rsi
0x18002ba74  lea     rdx, _GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e
0x18002ba7b  mov     rax, rbx
0x18002ba7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba83  mov     ebx, eax
0x18002ba85  test    eax, eax
0x18002ba87  js      loc_18002BF91
0x18002ba8d  mov     rax, [rbp+57h+var_A8]
0x18002ba91  lea     rcx, [rbp+57h+hstringHeader]
0x18002ba95  mov     [rbp+57h+var_60], rax
0x18002ba99  lea     rax, ??_9IAccount@Sync@Experiences@PhoneInternal@@$BLI@AA; [thunk]: PhoneInternal::Experiences::Sync::IAccount::`vcall'{184,{flat}}
0x18002baa0  mov     [rbp+57h+var_68], rax
0x18002baa4  lea     rax, [rbp+57h+var_70]
0x18002baa8  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18002baac  lea     rax, [rbp+57h+var_68]
0x18002bab0  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rax
0x18002bab4  lea     rax, [rbp+57h+var_60]
0x18002bab8  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], rax
0x18002babc  mov     [rbp+57h+var_70], r14
0x18002bac0  call    ??$AwaitActionHelper@V_lambda_82912b960cd7550f8286aff6609e2f4b_@@@@YAJAEBV_lambda_82912b960cd7550f8286aff6609e2f4b_@@@Z; AwaitActionHelper<_lambda_82912b960cd7550f8286aff6609e2f4b_>(_lambda_82912b960cd7550f8286aff6609e2f4b_ const &)
0x18002bac5  mov     ebx, eax
0x18002bac7  test    eax, eax
0x18002bac9  js      loc_18002BF99
0x18002bacf  mov     rax, [r14]
0x18002bad2  lea     r8, [rbp+57h+var_B0]
0x18002bad6  mov     rdx, [rbp+57h+var_A8]
0x18002bada  mov     rcx, r14
0x18002badd  mov     [rbp+57h+var_B0], r13
0x18002bae1  mov     rax, [rax+0C0h]
0x18002bae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002baed  mov     ebx, eax
0x18002baef  test    eax, eax
0x18002baf1  js      loc_18002BE07
0x18002baf7  mov     rbx, [rbp+57h+var_B0]
0x18002bafb  lea     rcx, [rbp+57h+var_90]
0x18002baff  mov     [rbp+57h+var_90], r13
0x18002bb03  mov     rax, [rbx]
0x18002bb06  mov     rdi, [rax]
0x18002bb09  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x18002bb0e  lea     r8, [rbp+57h+var_90]
0x18002bb12  mov     rcx, rbx
0x18002bb15  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18002bb1c  mov     rax, rdi
0x18002bb1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb24  mov     ebx, eax
0x18002bb26  test    eax, eax
0x18002bb28  js      loc_18002BFB7
0x18002bb2e  mov     rdi, [rbp+57h+var_90]
0x18002bb32  lea     rcx, [rbp+57h+var_98]
0x18002bb36  mov     [rbp+57h+var_98], r13
0x18002bb3a  mov     [rbp+57h+var_A0], r13
0x18002bb3e  mov     [rbp+57h+var_78], r13
0x18002bb42  mov     rax, [rdi]
0x18002bb45  mov     rbx, [rax+30h]
0x18002bb49  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x18002bb4e  mov     rdx, [rbp+57h+var_B8]
0x18002bb52  lea     r8, [rbp+57h+var_98]
0x18002bb56  mov     rcx, rdi
0x18002bb59  mov     rax, rbx
0x18002bb5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb61  mov     ebx, eax
0x18002bb63  test    eax, eax
0x18002bb65  js      loc_18002BFD4
0x18002bb6b  mov     rbx, [rbp+57h+var_98]
0x18002bb6f  test    rbx, rbx
0x18002bb72  jz      loc_18002BDFC
0x18002bb78  mov     rax, [rbx]
0x18002bb7b  lea     rcx, [rbp+57h+var_A0]
0x18002bb7f  mov     rdi, [rax]
0x18002bb82  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x18002bb87  lea     r8, [rbp+57h+var_A0]
0x18002bb8b  mov     rcx, rbx
0x18002bb8e  lea     rdx, _GUID_5541d8a7_497c_5aa4_86fc_7713adbf2a2c
0x18002bb95  mov     rax, rdi
0x18002bb98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb9d  mov     ebx, eax
0x18002bb9f  test    eax, eax
0x18002bba1  js      loc_18002BFE6
0x18002bba7  mov     rcx, [rbp+57h+var_A0]
0x18002bbab  lea     rdx, [rbp+57h+var_78]
0x18002bbaf  mov     rax, [rcx]
0x18002bbb2  mov     rax, [rax+30h]
0x18002bbb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbbb  mov     ebx, eax
0x18002bbbd  test    eax, eax
0x18002bbbf  js      loc_18002BFEE
0x18002bbc5  mov     rax, [rbp+57h+var_78]
0x18002bbc9  test    rax, rax
0x18002bbcc  js      loc_18002C006
0x18002bbd2  mov     rdi, [rbp+57h+var_90]
0x18002bbd6  lea     rcx, [rbp+57h+var_98]
0x18002bbda  mov     [r12], eax
0x18002bbde  sar     rax, 20h
0x18002bbe2  mov     [r12+4], eax
0x18002bbe7  mov     rax, [rdi]
0x18002bbea  mov     rbx, [rax+30h]
0x18002bbee  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x18002bbf3  mov     rdx, [rbp+57h+var_C0]
0x18002bbf7  lea     r8, [rbp+57h+var_98]
0x18002bbfb  mov     rcx, rdi
0x18002bbfe  mov     rax, rbx
0x18002bc01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc06  mov     ebx, eax
0x18002bc08  test    eax, eax
0x18002bc0a  js      loc_18002BFF6
0x18002bc10  mov     rbx, [rbp+57h+var_98]
0x18002bc14  test    rbx, rbx
0x18002bc17  jz      loc_18002BD71
0x18002bc1d  mov     rax, [rbx]
0x18002bc20  lea     rcx, [rbp+57h+var_A0]
0x18002bc24  mov     rdi, [rax]
0x18002bc27  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x18002bc2c  lea     r8, [rbp+57h+var_A0]
0x18002bc30  mov     rcx, rbx
0x18002bc33  lea     rdx, _GUID_5541d8a7_497c_5aa4_86fc_7713adbf2a2c
0x18002bc3a  mov     rax, rdi
0x18002bc3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc42  mov     ebx, eax
0x18002bc44  test    eax, eax
0x18002bc46  js      loc_18002BFDC
0x18002bc4c  mov     rcx, [rbp+57h+var_A0]
0x18002bc50  lea     rdx, [rbp+57h+var_78]
0x18002bc54  mov     rax, [rcx]
0x18002bc57  mov     rax, [rax+30h]
0x18002bc5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc60  mov     ebx, eax
0x18002bc62  test    eax, eax
0x18002bc64  js      loc_18002BEA1
0x18002bc6a  mov     rax, [rbp+57h+var_78]
0x18002bc6e  test    rax, rax
0x18002bc71  js      loc_18002BFFE
0x18002bc77  mov     rcx, [rbp+57h+var_A0]
0x18002bc7b  mov     [r15], eax
0x18002bc7e  sar     rax, 20h
0x18002bc82  mov     [r15+4], eax
0x18002bc86  test    rcx, rcx
0x18002bc89  jz      short loc_18002BC9B
0x18002bc8b  mov     [rbp+57h+var_A0], r13
0x18002bc8f  mov     rax, [rcx]
0x18002bc92  mov     rax, [rax+10h]
0x18002bc96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc9b  mov     rcx, [rbp+57h+var_98]
0x18002bc9f  test    rcx, rcx
0x18002bca2  jz      short loc_18002BCB4
0x18002bca4  mov     [rbp+57h+var_98], r13
0x18002bca8  mov     rax, [rcx]
0x18002bcab  mov     rax, [rax+10h]
0x18002bcaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcb4  mov     rcx, [rbp+57h+var_90]
0x18002bcb8  test    rcx, rcx
0x18002bcbb  jz      short loc_18002BCCD
0x18002bcbd  mov     [rbp+57h+var_90], r13
0x18002bcc1  mov     rax, [rcx]
0x18002bcc4  mov     rax, [rax+10h]
0x18002bcc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bccd  mov     rcx, [rbp+57h+var_B0]
0x18002bcd1  test    rcx, rcx
0x18002bcd4  jz      short loc_18002BCE6
0x18002bcd6  mov     [rbp+57h+var_B0], r13
0x18002bcda  mov     rax, [rcx]
0x18002bcdd  mov     rax, [rax+10h]
0x18002bce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bce6  mov     rcx, [rbp+57h+var_A8]
0x18002bcea  test    rcx, rcx
0x18002bced  jz      short loc_18002BCFF
0x18002bcef  mov     [rbp+57h+var_A8], r13
0x18002bcf3  mov     rax, [rcx]
0x18002bcf6  mov     rax, [rax+10h]
0x18002bcfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcff  test    rsi, rsi
0x18002bd02  jz      short loc_18002BD13
0x18002bd04  mov     rax, [rsi]
0x18002bd07  mov     rcx, rsi
0x18002bd0a  mov     rax, [rax+10h]
0x18002bd0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd13  mov     rcx, [rbp+57h+var_C0]; string
0x18002bd17  call    cs:__imp_WindowsDeleteString
0x18002bd1d  mov     rcx, [rbp+57h+var_B8]; string
0x18002bd21  mov     [rbp+57h+var_C0], r13
0x18002bd25  call    cs:__imp_WindowsDeleteString
0x18002bd2b  mov     rcx, [rbp+57h+var_80]
0x18002bd2f  mov     [rbp+57h+var_B8], r13
0x18002bd33  test    rcx, rcx
0x18002bd36  jz      short loc_18002BD48
0x18002bd38  mov     [rbp+57h+var_80], r13
0x18002bd3c  mov     rax, [rcx]
0x18002bd3f  mov     rax, [rax+10h]
0x18002bd43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd48  xor     eax, eax
0x18002bd4a  mov     rcx, [rbp+57h+var_38]
0x18002bd4e  xor     rcx, rsp; StackCookie
0x18002bd51  call    __security_check_cookie
0x18002bd56  mov     rbx, [rsp+0F0h+arg_18]
0x18002bd5e  add     rsp, 0C0h
0x18002bd65  pop     r15
0x18002bd67  pop     r14
0x18002bd69  pop     r13
0x18002bd6b  pop     r12
0x18002bd6d  pop     rdi
0x18002bd6e  pop     rsi
0x18002bd6f  pop     rbp
0x18002bd70  retn
0x18002bd71  mov     r9d, 71h ; 'q'
0x18002bd77  mov     ebx, 80070490h
0x18002bd7c  xor     edx, edx
  ... truncated ...
```
