# CSharedStorageAccessManagerStatics::AddFile(Windows::Storage::IStorageFile *,HSTRING__ * *)

- ea: `0x1802ede30`
- end: `0x1802ee3ec`
- name: `?AddFile@CSharedStorageAccessManagerStatics@@UEAAJPEAUIStorageFile@Storage@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `1468`
- prototype: `__int64 __fastcall(CSharedStorageAccessManagerStatics *__hidden this, struct Windows::Storage::IStorageFile *, HSTRING *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000d6cc`
- `0x1800144c4`
- `0x1800432f0`
- `0x1800d13a0`
- `0x1800f8ccc`
- `0x18014d1a0`
- `0x180281c70`
- `0x180283504`
- `0x1802ede30`
- `0x1802ee400`
- `0x18034c724`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802ee3e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802ee3e5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1802ede96`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1802ede96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ee128`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ee163`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ee128`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ee163`
- `dsclient!DSFreeString` at `0x1802ee30f`
- `dsclient!DSFreeString` at `0x1802ee395`
- `dsclient!DSFreeString` at `0x1802ee30f`
- `dsclient!DSFreeString` at `0x1802ee395`
- `dsclient!DSCreateSharedFileToken` at `0x1802ee22a`
- `dsclient!DSCreateSharedFileToken` at `0x1802ee268`
- `dsclient!DSCreateSharedFileToken` at `0x1802ee22a`
- `dsclient!DSCreateSharedFileToken` at `0x1802ee268`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802ee20c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802ee24a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802ee20c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802ee24a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802edf33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ee2ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ee346`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ee385`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ee3cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802edf33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ee2ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ee346`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ee385`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ee3cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1802edf85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1802edf85`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CSharedStorageAccessManagerStatics::AddFile(
        CSharedStorageAccessManagerStatics *this,
        struct IUnknown *a2,
        HSTRING *a3)
{
  int IsNonMUMA; // eax
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rdx
  int ValidatedStorageItemObject; // eax
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // r9
  __int64 v15; // rdx
  HRESULT v16; // eax
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v18)(_QWORD, GUID *, __int64 *); // rdi
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, int *, GUID *, __int64); // rbx
  __int64 v22; // rax
  int v23; // eax
  struct IShellItem *v24; // rcx
  __int64 v25; // rcx
  __int64 (__fastcall ***v26)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v27; // rdi
  void (__fastcall *v28)(__int64, __int64); // rbx
  __int64 v29; // rax
  int CurrentUserSidString; // eax
  char v31; // bl
  int v32; // eax
  PCWSTR StringRawBuffer; // rax
  int v34; // eax
  int v35; // edi
  PCWSTR v36; // rax
  int v37; // eax
  HSTRING v39; // rax
  int v40; // [rsp+20h] [rbp-E0h]
  int v41[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall ***v42)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-C8h] BYREF
  __int64 v43; // [rsp+40h] [rbp-C0h] BYREF
  struct IShellItem *v44; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  int v46; // [rsp+58h] [rbp-A8h] BYREF
  INT32 result[2]; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v48; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR StringSid; // [rsp+70h] [rbp-90h] BYREF
  __int64 v50; // [rsp+78h] [rbp-88h]
  __int64 v51; // [rsp+80h] [rbp-80h]
  _DWORD v52[6]; // [rsp+90h] [rbp-70h] BYREF
  LPWSTR v53; // [rsp+A8h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  string = 0;
  IsNonMUMA = EnsureCallerIsNonMUMA(L"AddFile");
  v6 = IsNonMUMA;
  if ( IsNonMUMA < 0 )
  {
    v7 = (unsigned int)IsNonMUMA;
    v8 = 76;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dswinrtwrappers.cpp",
      (const char *)v7,
      v40);
LABEL_47:
    WindowsDeleteString(string);
    return v6;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    RoOriginateError(2147942487LL, 0);
    v7 = 2147942487LL;
    v8 = 81;
    goto LABEL_5;
  }
  v42 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  ValidatedStorageItemObject = CStorageItem_GetValidatedStorageItemObject(a2);
  v6 = ValidatedStorageItemObject;
  if ( ValidatedStorageItemObject < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dswinrtwrappers.cpp",
      (const char *)(unsigned int)ValidatedStorageItemObject,
      v40);
    v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v42;
    if ( v42 )
    {
      v42 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v10)[2])(v10);
    }
    goto LABEL_47;
  }
  v11 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v42;
  v12 = (*v42)[12];
  WindowsDeleteString(string);
  string = 0;
  v13 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), HSTRING *))v12)(v11, &string);
  v6 = v13;
  if ( v13 < 0 )
  {
    v14 = (unsigned int)v13;
    v15 = 87;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dswinrtwrappers.cpp",
      (const char *)v14,
      v40);
LABEL_46:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    goto LABEL_47;
  }
  result[0] = 0;
  v16 = WindowsCompareStringOrdinal(string, 0, result);
  if ( v16 < 0 )
  {
    RaiseException(v16, 1u, 0, 0);
    JUMPOUT(0x1802EE3EBLL);
  }
  if ( !result[0] )
  {
    v6 = -2147024809;
    v14 = 2147942487LL;
    v15 = 89;
    goto LABEL_12;
  }
  v43 = 0;
  v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v42;
  v18 = **v42;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  v19 = v18(v17, &GUID_d75c13bb_3883_4bd2_9b7a_334ff6d83066, &v43);
  v6 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dswinrtwrappers.cpp",
      (const char *)(unsigned int)v19,
      v40);
LABEL_45:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    goto LABEL_46;
  }
  v46 = 0;
  v44 = 0;
  v20 = v43;
  v21 = *(__int64 (__fastcall **)(__int64, int *, GUID *, __int64))(*(_QWORD *)v43 + 40LL);
  v22 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(&v44);
  v23 = v21(v20, &v46, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v22);
  v6 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dswinrtwrappers.cpp",
      (const char *)(unsigned int)v23,
      v40);
    v24 = v44;
    if ( v44 )
    {
      v44 = 0;
      ((void (__fastcall *)(struct IShellItem *))v24->lpVtbl->Release)(v24);
    }
    v25 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v42;
    if ( v42 )
    {
      v42 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v26)[2])(v26);
    }
    goto LABEL_47;
  }
  if ( (v46 & 0x22000) == 0 )
  {
    *(_QWORD *)result = 0;
    v27 = v43;
    v28 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 48LL);
    v29 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(result);
    v28(v27, v29);
    if ( !IsShellItemValidForSearchScopeOrFileOperation(v44, *(const unsigned __int16 **)result) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\dswinrtwrappers.cpp",
        (const char *)0x80070005LL,
        v40);
      if ( *(_QWORD *)result )
        CoTaskMemFree(*(LPVOID *)result);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      v6 = -2147024891;
      goto LABEL_47;
    }
    if ( *(_QWORD *)result )
      CoTaskMemFree(*(LPVOID *)result);
  }
  StringSid = 0;
  v50 = 0;
  v51 = 0;
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&StringSid);
  v50 = -1;
  v51 = -1;
  CurrentUserSidString = GetCurrentUserSidString(&StringSid);
  v6 = CurrentUserSidString;
  if ( CurrentUserSidString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dswinrtwrappers.cpp",
      (const char *)(unsigned int)CurrentUserSidString,
      v40);
LABEL_44:
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&StringSid);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    goto LABEL_45;
  }
  v31 = v46;
  memset_0(v52, 0, 0x150u);
  v32 = v52[0];
  if ( (v31 & 0x40) == 0 )
    v32 = 2;
  v52[0] = v32;
  v52[1] = 7;
  v52[4] = 0;
  v53 = StringSid;
  v52[2] = 1;
  *(_QWORD *)v41 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v34 = DSCreateSharedFileToken(StringRawBuffer, v52, 1);
  v35 = v34;
  if ( (v31 & 0x40) == 0 && v34 == -2147024891 )
  {
    v52[0] = 0;
    v36 = WindowsGetStringRawBuffer(string, 0);
    v35 = DSCreateSharedFileToken(v36, v52, 1);
  }
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dswinrtwrappers.cpp",
      (const char *)(unsigned int)v35,
      (int)v41);
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&StringSid);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    v6 = v35;
    goto LABEL_47;
  }
  v48 = 0;
  v37 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v48, v41);
  v6 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dswinrtwrappers.cpp",
      (const char *)(unsigned int)v37,
      (int)v41);
    WindowsDeleteString(v48);
    v48 = 0;
    DSFreeString(*(_QWORD *)v41);
    goto LABEL_44;
  }
  v39 = v48;
  v48 = 0;
  *a3 = v39;
  WindowsDeleteString(0);
  v48 = 0;
  DSFreeString(*(_QWORD *)v41);
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&StringSid);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x1802ede30  mov     [rsp-8+arg_0], rbx
0x1802ede35  mov     [rsp-8+arg_18], rdi
0x1802ede3a  push    rbp
0x1802ede3b  push    r14
0x1802ede3d  push    r15
0x1802ede3f  lea     rbp, [rsp-0F0h]
0x1802ede47  sub     rsp, 1F0h
0x1802ede4e  mov     rax, cs:__security_cookie
0x1802ede55  xor     rax, rsp
0x1802ede58  mov     [rbp+100h+var_20], rax
0x1802ede5f  mov     r14, r8
0x1802ede62  mov     rdi, rdx
0x1802ede65  xor     r15d, r15d
0x1802ede68  mov     [rsp+200h+string], r15
0x1802ede6d  lea     rcx, aAddfile; "AddFile"
0x1802ede74  call    ?EnsureCallerIsNonMUMA@@YAJPEBG@Z; EnsureCallerIsNonMUMA(ushort const *)
0x1802ede79  mov     ebx, eax
0x1802ede7b  test    eax, eax
0x1802ede7d  jns     short loc_1802EDE88
0x1802ede7f  mov     r9d, eax
0x1802ede82  lea     edx, [r15+4Ch]
0x1802ede86  jmp     short loc_1802EDEA2
0x1802ede88  test    rdi, rdi
0x1802ede8b  jnz     short loc_1802EDEBA
0x1802ede8d  xor     edx, edx
0x1802ede8f  mov     ebx, 80070057h
0x1802ede94  mov     ecx, ebx
0x1802ede96  call    cs:__imp_RoOriginateError
0x1802ede9c  mov     r9d, ebx; char *
0x1802ede9f  lea     edx, [rdi+51h]; void *
0x1802edea2  lea     r8, aOnecoreuapShel_98; "onecoreuap\\shell\\windows.storage\\dsw"...
0x1802edea9  mov     rcx, [rbp+108h]; this
0x1802edeb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802edeb5  jmp     loc_1802EE341
0x1802edeba  mov     [rsp+200h+var_1C8], r15
0x1802edebf  lea     rcx, [rsp+200h+var_1C8]
0x1802edec4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802edec9  lea     r9, [rsp+200h+var_1C8]
0x1802edece  lea     r8, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x1802eded5  xor     edx, edx
0x1802eded7  mov     rcx, rdi; struct IUnknown *
0x1802ededa  call    CStorageItem_GetValidatedStorageItemObject
0x1802ededf  mov     ebx, eax
0x1802edee1  test    eax, eax
0x1802edee3  jns     short loc_1802EDF22
0x1802edee5  mov     rcx, [rbp+108h]; this
0x1802edeec  mov     r9d, eax; char *
0x1802edeef  lea     r8, aOnecoreuapShel_98; "onecoreuap\\shell\\windows.storage\\dsw"...
0x1802edef6  mov     edx, 56h ; 'V'; void *
0x1802edefb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802edf00  nop
0x1802edf01  mov     rcx, [rsp+200h+var_1C8]
0x1802edf06  test    rcx, rcx
0x1802edf09  jz      short loc_1802EDF1D
0x1802edf0b  mov     [rsp+200h+var_1C8], r15
0x1802edf10  mov     rax, [rcx]
0x1802edf13  mov     rax, [rax+10h]
0x1802edf17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802edf1c  nop
0x1802edf1d  jmp     loc_1802EE341
0x1802edf22  mov     rdi, [rsp+200h+var_1C8]
0x1802edf27  mov     rax, [rdi]
0x1802edf2a  mov     rbx, [rax+60h]
0x1802edf2e  mov     rcx, [rsp+200h+string]; string
0x1802edf33  call    cs:__imp_WindowsDeleteString
0x1802edf39  mov     [rsp+200h+string], r15
0x1802edf3e  lea     rdx, [rsp+200h+string]
0x1802edf43  mov     rcx, rdi
0x1802edf46  mov     rax, rbx
0x1802edf49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802edf4e  mov     ebx, eax
0x1802edf50  test    eax, eax
0x1802edf52  jns     short loc_1802EDF74
0x1802edf54  mov     r9d, eax; char *
0x1802edf57  mov     edx, 57h ; 'W'; void *
0x1802edf5c  lea     r8, aOnecoreuapShel_98; "onecoreuap\\shell\\windows.storage\\dsw"...
0x1802edf63  mov     rcx, [rbp+108h]; this
0x1802edf6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802edf6f  jmp     loc_1802EE336
0x1802edf74  mov     [rsp+200h+result], r15d
0x1802edf79  lea     r8, [rsp+200h+result]; result
0x1802edf7e  xor     edx, edx; string2
0x1802edf80  mov     rcx, [rsp+200h+string]; string1
0x1802edf85  call    cs:__imp_WindowsCompareStringOrdinal
0x1802edf8b  test    eax, eax
0x1802edf8d  js      loc_1802EE3D9
0x1802edf93  cmp     [rsp+200h+result], r15d
0x1802edf98  jnz     short loc_1802EDFA9
0x1802edf9a  mov     ebx, 80070057h
0x1802edf9f  mov     r9d, ebx
0x1802edfa2  mov     edx, 59h ; 'Y'
0x1802edfa7  jmp     short loc_1802EDF5C
0x1802edfa9  mov     [rsp+200h+var_1C0], r15
0x1802edfae  mov     rbx, [rsp+200h+var_1C8]
0x1802edfb3  mov     rax, [rbx]
0x1802edfb6  mov     rdi, [rax]
0x1802edfb9  lea     rcx, [rsp+200h+var_1C0]
0x1802edfbe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802edfc3  lea     r8, [rsp+200h+var_1C0]
0x1802edfc8  lea     rdx, _GUID_d75c13bb_3883_4bd2_9b7a_334ff6d83066
0x1802edfcf  mov     rcx, rbx
0x1802edfd2  mov     rax, rdi
0x1802edfd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802edfda  mov     ebx, eax
0x1802edfdc  test    eax, eax
0x1802edfde  jns     short loc_1802EE000
0x1802edfe0  mov     rcx, [rbp+108h]; this
0x1802edfe7  mov     r9d, eax; char *
0x1802edfea  lea     r8, aOnecoreuapShel_98; "onecoreuap\\shell\\windows.storage\\dsw"...
0x1802edff1  mov     edx, 6Bh ; 'k'; void *
0x1802edff6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802edffb  jmp     loc_1802EE32B
0x1802ee000  mov     [rsp+200h+var_1A8], r15d
0x1802ee005  mov     [rsp+200h+var_1B8], r15
0x1802ee00a  mov     rdi, [rsp+200h+var_1C0]
0x1802ee00f  mov     rax, [rdi]
0x1802ee012  mov     rbx, [rax+28h]
0x1802ee016  lea     rcx, [rsp+200h+var_1B8]
0x1802ee01b  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIPersistSerializedPropStoragePriv@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIPersistSerializedPropStoragePriv@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>)
0x1802ee020  mov     r9, rax
0x1802ee023  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x1802ee02a  lea     rdx, [rsp+200h+var_1A8]
0x1802ee02f  mov     rcx, rdi
0x1802ee032  mov     rax, rbx
0x1802ee035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802ee03a  mov     ebx, eax
0x1802ee03c  test    eax, eax
0x1802ee03e  jns     short loc_1802EE0B5
0x1802ee040  mov     rcx, [rbp+108h]; this
0x1802ee047  mov     r9d, eax; char *
0x1802ee04a  lea     r8, aOnecoreuapShel_98; "onecoreuap\\shell\\windows.storage\\dsw"...
0x1802ee051  mov     edx, 6Fh ; 'o'; void *
0x1802ee056  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802ee05b  nop
0x1802ee05c  mov     rcx, [rsp+200h+var_1B8]
0x1802ee061  test    rcx, rcx
0x1802ee064  jz      short loc_1802EE078
0x1802ee066  mov     [rsp+200h+var_1B8], r15
0x1802ee06b  mov     rax, [rcx]
0x1802ee06e  mov     rax, [rax+10h]
0x1802ee072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802ee077  nop
0x1802ee078  mov     rcx, [rsp+200h+var_1C0]
0x1802ee07d  test    rcx, rcx
0x1802ee080  jz      short loc_1802EE094
0x1802ee082  mov     [rsp+200h+var_1C0], r15
0x1802ee087  mov     rax, [rcx]
0x1802ee08a  mov     rax, [rax+10h]
0x1802ee08e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802ee093  nop
0x1802ee094  mov     rcx, [rsp+200h+var_1C8]
0x1802ee099  test    rcx, rcx
0x1802ee09c  jz      short loc_1802EE0B0
0x1802ee09e  mov     [rsp+200h+var_1C8], r15
0x1802ee0a3  mov     rax, [rcx]
0x1802ee0a6  mov     rax, [rax+10h]
0x1802ee0aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802ee0af  nop
0x1802ee0b0  jmp     loc_1802EE341
0x1802ee0b5  test    [rsp+200h+var_1A8], 22000h
0x1802ee0bd  jnz     loc_1802EE169
0x1802ee0c3  mov     qword ptr [rsp+200h+result], r15
0x1802ee0c8  mov     rdi, [rsp+200h+var_1C0]
0x1802ee0cd  mov     rax, [rdi]
0x1802ee0d0  mov     rbx, [rax+30h]
0x1802ee0d4  lea     rcx, [rsp+200h+result]
0x1802ee0d9  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1802ee0de  mov     rdx, rax
0x1802ee0e1  mov     rcx, rdi
0x1802ee0e4  mov     rax, rbx
0x1802ee0e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802ee0ec  mov     rdx, qword ptr [rsp+200h+result]; unsigned __int16 *
0x1802ee0f1  mov     rcx, [rsp+200h+var_1B8]; struct IShellItem *
0x1802ee0f6  call    ?IsShellItemValidForSearchScopeOrFileOperation@@YA_NPEAUIShellItem@@PEBG@Z; IsShellItemValidForSearchScopeOrFileOperation(IShellItem *,ushort const *)
0x1802ee0fb  test    al, al
0x1802ee0fd  jnz     short loc_1802EE159
0x1802ee0ff  mov     rcx, [rbp+108h]; this
0x1802ee106  mov     r9d, 80070005h; char *
0x1802ee10c  lea     r8, aOnecoreuapShel_98; "onecoreuap\\shell\\windows.storage\\dsw"...
0x1802ee113  mov     edx, 78h ; 'x'; void *
0x1802ee118  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802ee11d  nop
0x1802ee11e  mov     rcx, qword ptr [rsp+200h+result]; pv
0x1802ee123  test    rcx, rcx
0x1802ee126  jz      short loc_1802EE12F
0x1802ee128  call    cs:__imp_CoTaskMemFree
0x1802ee12e  nop
0x1802ee12f  lea     rcx, [rsp+200h+var_1B8]
0x1802ee134  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802ee139  nop
0x1802ee13a  lea     rcx, [rsp+200h+var_1C0]
0x1802ee13f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802ee144  nop
0x1802ee145  lea     rcx, [rsp+200h+var_1C8]
0x1802ee14a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802ee14f  mov     ebx, 80070005h
0x1802ee154  jmp     loc_1802EE341
0x1802ee159  mov     rcx, qword ptr [rsp+200h+result]; pv
0x1802ee15e  test    rcx, rcx
0x1802ee161  jz      short loc_1802EE169
0x1802ee163  call    cs:__imp_CoTaskMemFree
0x1802ee169  mov     [rsp+200h+StringSid], r15
0x1802ee16e  mov     [rsp+200h+var_188], r15
0x1802ee173  mov     [rbp+100h+var_180], r15
0x1802ee177  lea     rcx, [rsp+200h+StringSid]
0x1802ee17c  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1802ee181  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802ee185  mov     [rsp+200h+var_188], rax
0x1802ee18a  mov     [rbp+100h+var_180], rax
0x1802ee18e  lea     rcx, [rsp+200h+StringSid]; StringSid
0x1802ee193  call    ?GetCurrentUserSidString@@YAJPEAPEAG@Z; GetCurrentUserSidString(ushort * *)
0x1802ee198  mov     ebx, eax
0x1802ee19a  test    eax, eax
0x1802ee19c  jns     short loc_1802EE1BE
0x1802ee19e  mov     rcx, [rbp+108h]; this
0x1802ee1a5  mov     r9d, eax; char *
0x1802ee1a8  lea     r8, aOnecoreuapShel_98; "onecoreuap\\shell\\windows.storage\\dsw"...
0x1802ee1af  mov     edx, 7Eh ; '~'; void *
0x1802ee1b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802ee1b9  jmp     loc_1802EE315
0x1802ee1be  mov     ebx, [rsp+200h+var_1A8]
0x1802ee1c2  xor     edx, edx; Val
0x1802ee1c4  mov     r8d, 150h; Size
0x1802ee1ca  lea     rcx, [rbp+100h+var_170]; void *
0x1802ee1ce  call    memset_0
0x1802ee1d3  mov     eax, [rbp+100h+var_170]
0x1802ee1d6  mov     ecx, 2
0x1802ee1db  bt      ebx, 6
0x1802ee1df  cmovnb  eax, ecx
0x1802ee1e2  mov     [rbp+100h+var_170], eax
0x1802ee1e5  mov     [rbp+100h+var_16C], 7
0x1802ee1ec  mov     [rbp+100h+var_160], r15d
0x1802ee1f0  mov     rax, [rsp+200h+StringSid]
0x1802ee1f5  mov     [rbp+100h+var_158], rax
0x1802ee1f9  mov     [rbp+100h+var_168], 1
0x1802ee200  mov     qword ptr [rsp+200h+var_1D0], r15
0x1802ee205  xor     edx, edx; length
0x1802ee207  mov     rcx, [rsp+200h+string]; string
0x1802ee20c  call    cs:__imp_WindowsGetStringRawBuffer
0x1802ee212  lea     rcx, [rsp+200h+var_1D0]
0x1802ee217  mov     qword ptr [rsp+200h+var_1E0], rcx
0x1802ee21c  xor     r9d, r9d
0x1802ee21f  lea     r8d, [r9+1]
0x1802ee223  lea     rdx, [rbp+100h+var_170]
0x1802ee227  mov     rcx, rax
0x1802ee22a  call    cs:__imp_DSCreateSharedFileToken
0x1802ee230  mov     edi, eax
0x1802ee232  bt      ebx, 6
0x1802ee236  jb      short loc_1802EE270
0x1802ee238  cmp     eax, 80070005h
0x1802ee23d  jnz     short loc_1802EE270
0x1802ee23f  mov     [rbp+100h+var_170], r15d
0x1802ee243  xor     edx, edx; length
0x1802ee245  mov     rcx, [rsp+200h+string]; string
0x1802ee24a  call    cs:__imp_WindowsGetStringRawBuffer
0x1802ee250  lea     rcx, [rsp+200h+var_1D0]
0x1802ee255  mov     qword ptr [rsp+200h+var_1E0], rcx; int
0x1802ee25a  xor     r9d, r9d
0x1802ee25d  lea     r8d, [r9+1]
0x1802ee261  lea     rdx, [rbp+100h+var_170]
0x1802ee265  mov     rcx, rax
0x1802ee268  call    cs:__imp_DSCreateSharedFileToken
0x1802ee26e  mov     edi, eax
0x1802ee270  test    edi, edi
0x1802ee272  jns     short loc_1802EE2C1
0x1802ee274  mov     rcx, [rbp+108h]; this
0x1802ee27b  mov     r9d, edi; char *
0x1802ee27e  lea     r8, aOnecoreuapShel_98; "onecoreuap\\shell\\windows.storage\\dsw"...
0x1802ee285  mov     edx, 9Fh; void *
0x1802ee28a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802ee28f  lea     rcx, [rsp+200h+StringSid]
0x1802ee294  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1802ee299  nop
0x1802ee29a  lea     rcx, [rsp+200h+var_1B8]
0x1802ee29f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802ee2a4  nop
0x1802ee2a5  lea     rcx, [rsp+200h+var_1C0]
0x1802ee2aa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802ee2af  nop
0x1802ee2b0  lea     rcx, [rsp+200h+var_1C8]
0x1802ee2b5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802ee2ba  mov     ebx, edi
0x1802ee2bc  jmp     loc_1802EE341
0x1802ee2c1  mov     [rsp+200h+var_198], r15
0x1802ee2c6  lea     rdx, [rsp+200h+var_1D0]
0x1802ee2cb  lea     rcx, [rsp+200h+var_198]
0x1802ee2d0  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1802ee2d5  mov     ebx, eax
0x1802ee2d7  test    eax, eax
0x1802ee2d9  jns     loc_1802EE376
0x1802ee2df  mov     rcx, [rbp+108h]; this
0x1802ee2e6  mov     r9d, eax; char *
0x1802ee2e9  lea     r8, aOnecoreuapShel_98; "onecoreuap\\shell\\windows.storage\\dsw"...
0x1802ee2f0  mov     edx, 0A8h; void *
0x1802ee2f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802ee2fa  mov     rcx, [rsp+200h+var_198]; string
0x1802ee2ff  call    cs:__imp_WindowsDeleteString
0x1802ee305  mov     [rsp+200h+var_198], r15
0x1802ee30a  mov     rcx, qword ptr [rsp+200h+var_1D0]
0x1802ee30f  call    cs:__imp_DSFreeString
  ... truncated ...
```
