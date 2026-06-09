# CSharedStorageAccessManagerStatics::AddFile(Windows::Storage::IStorageFile *,HSTRING__ * *)

- ea: `0x180300000`
- end: `0x1803005d5`
- name: `?AddFile@CSharedStorageAccessManagerStatics@@UEAAJPEAUIStorageFile@Storage@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `1493`
- prototype: `__int64 __fastcall(CSharedStorageAccessManagerStatics *__hidden this, struct Windows::Storage::IStorageFile *, HSTRING *)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180009fc0`
- `0x1800304e0`
- `0x180038f50`
- `0x180063050`
- `0x1800c7ce8`
- `0x1801720d0`
- `0x1801e4b9c`
- `0x18028f3e8`
- `0x180293094`
- `0x180300000`
- `0x1803005e0`
- `0x180356c84`
- `0x18035d818`
- `0x18036e64c`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180300065`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180300065`
- `dsclient!DSFreeString` at `0x1803004e5`
- `dsclient!DSFreeString` at `0x18030057d`
- `dsclient!DSFreeString` at `0x1803004e5`
- `dsclient!DSFreeString` at `0x18030057d`
- `dsclient!DSCreateSharedFileToken` at `0x1803003e8`
- `dsclient!DSCreateSharedFileToken` at `0x180300432`
- `dsclient!DSCreateSharedFileToken` at `0x1803003e8`
- `dsclient!DSCreateSharedFileToken` at `0x180300432`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803003c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18030040e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803003c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18030040e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180300108`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803004cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180300522`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180300567`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803005ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180300108`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803004cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180300522`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180300567`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803005ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180300160`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180300160`

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
  __int64 v10; // rcx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  __int64 v14; // r9
  __int64 v15; // rdx
  HRESULT v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, int *, GUID *, __int64); // rbx
  __int64 v22; // rax
  int v23; // eax
  struct IShellItem *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
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
  __int64 v42; // [rsp+38h] [rbp-C8h] BYREF
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
LABEL_44:
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
    v10 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    goto LABEL_44;
  }
  v11 = v42;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v42 + 96LL);
  WindowsDeleteString(string);
  string = 0;
  v13 = v12(v11, &string);
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
LABEL_43:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    goto LABEL_44;
  }
  result[0] = 0;
  v16 = WindowsCompareStringOrdinal(string, 0, result);
  if ( v16 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
    JUMPOUT(0x1803005D4LL);
  }
  if ( !result[0] )
  {
    v6 = -2147024809;
    v14 = 2147942487LL;
    v15 = 89;
    goto LABEL_12;
  }
  v43 = 0;
  v19 = Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem>::As<IStorageItemInternalAvailableCrossProcess>(
          &v42,
          &v43);
  v6 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\dswinrtwrappers.cpp",
      (const char *)(unsigned int)v19,
      v40);
LABEL_42:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    goto LABEL_43;
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
    v26 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    goto LABEL_44;
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
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(result);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      v6 = -2147024891;
      goto LABEL_44;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(result);
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
LABEL_41:
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&StringSid);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    goto LABEL_42;
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
    goto LABEL_44;
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
    goto LABEL_41;
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
0x180300000  mov     [rsp-8+arg_0], rbx
0x180300005  mov     [rsp-8+arg_18], rsi
0x18030000a  push    rbp
0x18030000b  push    rdi
0x18030000c  push    r14
0x18030000e  lea     rbp, [rsp-0F0h]
0x180300016  sub     rsp, 1F0h
0x18030001d  mov     rax, cs:__security_cookie
0x180300024  xor     rax, rsp
0x180300027  mov     [rbp+100h+var_20], rax
0x18030002e  mov     rsi, r8
0x180300031  mov     rdi, rdx
0x180300034  xor     r14d, r14d
0x180300037  mov     [rsp+200h+string], r14
0x18030003c  lea     rcx, aAddfile; "AddFile"
0x180300043  call    ?EnsureCallerIsNonMUMA@@YAJPEBG@Z; EnsureCallerIsNonMUMA(ushort const *)
0x180300048  mov     ebx, eax
0x18030004a  test    eax, eax
0x18030004c  jns     short loc_180300057
0x18030004e  mov     r9d, eax
0x180300051  lea     edx, [r14+4Ch]
0x180300055  jmp     short loc_180300077
0x180300057  test    rdi, rdi
0x18030005a  jnz     short loc_18030008F
0x18030005c  xor     edx, edx
0x18030005e  mov     ebx, 80070057h
0x180300063  mov     ecx, ebx
0x180300065  call    cs:__imp_RoOriginateError
0x18030006c  nop     dword ptr [rax+rax+00h]
0x180300071  mov     r9d, ebx; char *
0x180300074  lea     edx, [rdi+51h]; void *
0x180300077  lea     r8, aOnecoreuapShel_98; "onecoreuap\\shell\\windows.storage\\dsw"...
0x18030007e  mov     rcx, [rbp+108h]; this
0x180300085  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18030008a  jmp     loc_18030051D
0x18030008f  mov     [rsp+200h+var_1C8], r14
0x180300094  lea     rcx, [rsp+200h+var_1C8]
0x180300099  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18030009e  lea     r9, [rsp+200h+var_1C8]
0x1803000a3  lea     r8, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x1803000aa  xor     edx, edx
0x1803000ac  mov     rcx, rdi; struct IUnknown *
0x1803000af  call    CStorageItem_GetValidatedStorageItemObject
0x1803000b4  mov     ebx, eax
0x1803000b6  test    eax, eax
0x1803000b8  jns     short loc_1803000F7
0x1803000ba  mov     rcx, [rbp+108h]; this
0x1803000c1  mov     r9d, eax; char *
0x1803000c4  lea     r8, aOnecoreuapShel_98; "onecoreuap\\shell\\windows.storage\\dsw"...
0x1803000cb  mov     edx, 56h ; 'V'; void *
0x1803000d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803000d5  nop
0x1803000d6  mov     rcx, [rsp+200h+var_1C8]
0x1803000db  test    rcx, rcx
0x1803000de  jz      short loc_1803000F2
0x1803000e0  mov     [rsp+200h+var_1C8], r14
0x1803000e5  mov     rax, [rcx]
0x1803000e8  mov     rax, [rax+10h]
0x1803000ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803000f1  nop
0x1803000f2  jmp     loc_18030051D
0x1803000f7  mov     rdi, [rsp+200h+var_1C8]
0x1803000fc  mov     rax, [rdi]
0x1803000ff  mov     rbx, [rax+60h]
0x180300103  mov     rcx, [rsp+200h+string]; string
0x180300108  call    cs:__imp_WindowsDeleteString
0x18030010f  nop     dword ptr [rax+rax+00h]
0x180300114  mov     [rsp+200h+string], r14
0x180300119  lea     rdx, [rsp+200h+string]
0x18030011e  mov     rcx, rdi
0x180300121  mov     rax, rbx
0x180300124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180300129  mov     ebx, eax
0x18030012b  test    eax, eax
0x18030012d  jns     short loc_18030014F
0x18030012f  mov     r9d, eax; char *
0x180300132  mov     edx, 57h ; 'W'; void *
0x180300137  lea     r8, aOnecoreuapShel_98; "onecoreuap\\shell\\windows.storage\\dsw"...
0x18030013e  mov     rcx, [rbp+108h]; this
0x180300145  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18030014a  jmp     loc_180300512
0x18030014f  mov     [rsp+200h+result], r14d
0x180300154  lea     r8, [rsp+200h+result]; result
0x180300159  xor     edx, edx; string2
0x18030015b  mov     rcx, [rsp+200h+string]; string1
0x180300160  call    cs:__imp_WindowsCompareStringOrdinal
0x180300167  nop     dword ptr [rax+rax+00h]
0x18030016c  test    eax, eax
0x18030016e  js      loc_1803005CD
0x180300174  cmp     [rsp+200h+result], r14d
0x180300179  jnz     short loc_18030018A
0x18030017b  mov     ebx, 80070057h
0x180300180  mov     r9d, ebx
0x180300183  mov     edx, 59h ; 'Y'
0x180300188  jmp     short loc_180300137
0x18030018a  mov     [rsp+200h+var_1C0], r14
0x18030018f  lea     rdx, [rsp+200h+var_1C0]
0x180300194  lea     rcx, [rsp+200h+var_1C8]
0x180300199  call    ??$As@UIStorageItemInternalAvailableCrossProcess@@@?$ComPtr@UIStorageItem@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIStorageItemInternalAvailableCrossProcess@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem>::As<IStorageItemInternalAvailableCrossProcess>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IStorageItemInternalAvailableCrossProcess>>)
0x18030019e  mov     ebx, eax
0x1803001a0  test    eax, eax
0x1803001a2  jns     short loc_1803001C4
0x1803001a4  mov     rcx, [rbp+108h]; this
0x1803001ab  mov     r9d, eax; char *
0x1803001ae  lea     r8, aOnecoreuapShel_98; "onecoreuap\\shell\\windows.storage\\dsw"...
0x1803001b5  mov     edx, 6Bh ; 'k'; void *
0x1803001ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803001bf  jmp     loc_180300507
0x1803001c4  mov     [rsp+200h+var_1A8], r14d
0x1803001c9  mov     [rsp+200h+var_1B8], r14
0x1803001ce  mov     rdi, [rsp+200h+var_1C0]
0x1803001d3  mov     rax, [rdi]
0x1803001d6  mov     rbx, [rax+28h]
0x1803001da  lea     rcx, [rsp+200h+var_1B8]
0x1803001df  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIPersistSerializedPropStoragePriv@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIPersistSerializedPropStoragePriv@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>)
0x1803001e4  mov     r9, rax
0x1803001e7  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x1803001ee  lea     rdx, [rsp+200h+var_1A8]
0x1803001f3  mov     rcx, rdi
0x1803001f6  mov     rax, rbx
0x1803001f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803001fe  mov     ebx, eax
0x180300200  test    eax, eax
0x180300202  jns     short loc_180300279
0x180300204  mov     rcx, [rbp+108h]; this
0x18030020b  mov     r9d, eax; char *
0x18030020e  lea     r8, aOnecoreuapShel_98; "onecoreuap\\shell\\windows.storage\\dsw"...
0x180300215  mov     edx, 6Fh ; 'o'; void *
0x18030021a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18030021f  nop
0x180300220  mov     rcx, [rsp+200h+var_1B8]
0x180300225  test    rcx, rcx
0x180300228  jz      short loc_18030023C
0x18030022a  mov     [rsp+200h+var_1B8], r14
0x18030022f  mov     rax, [rcx]
0x180300232  mov     rax, [rax+10h]
0x180300236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030023b  nop
0x18030023c  mov     rcx, [rsp+200h+var_1C0]
0x180300241  test    rcx, rcx
0x180300244  jz      short loc_180300258
0x180300246  mov     [rsp+200h+var_1C0], r14
0x18030024b  mov     rax, [rcx]
0x18030024e  mov     rax, [rax+10h]
0x180300252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180300257  nop
0x180300258  mov     rcx, [rsp+200h+var_1C8]
0x18030025d  test    rcx, rcx
0x180300260  jz      short loc_180300274
0x180300262  mov     [rsp+200h+var_1C8], r14
0x180300267  mov     rax, [rcx]
0x18030026a  mov     rax, [rax+10h]
0x18030026e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180300273  nop
0x180300274  jmp     loc_18030051D
0x180300279  test    [rsp+200h+var_1A8], 22000h
0x180300281  jnz     loc_180300321
0x180300287  mov     qword ptr [rsp+200h+result], r14
0x18030028c  mov     rdi, [rsp+200h+var_1C0]
0x180300291  mov     rax, [rdi]
0x180300294  mov     rbx, [rax+30h]
0x180300298  lea     rcx, [rsp+200h+result]
0x18030029d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1803002a2  mov     rdx, rax
0x1803002a5  mov     rcx, rdi
0x1803002a8  mov     rax, rbx
0x1803002ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803002b0  mov     rdx, qword ptr [rsp+200h+result]; unsigned __int16 *
0x1803002b5  mov     rcx, [rsp+200h+var_1B8]; struct IShellItem *
0x1803002ba  call    ?IsShellItemValidForSearchScopeOrFileOperation@@YA_NPEAUIShellItem@@PEBG@Z; IsShellItemValidForSearchScopeOrFileOperation(IShellItem *,ushort const *)
0x1803002bf  test    al, al
0x1803002c1  jnz     short loc_180300317
0x1803002c3  mov     rcx, [rbp+108h]; this
0x1803002ca  mov     r9d, 80070005h; char *
0x1803002d0  lea     r8, aOnecoreuapShel_98; "onecoreuap\\shell\\windows.storage\\dsw"...
0x1803002d7  mov     edx, 78h ; 'x'; void *
0x1803002dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803002e1  nop
0x1803002e2  lea     rcx, [rsp+200h+result]; void *
0x1803002e7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1803002ec  nop
0x1803002ed  lea     rcx, [rsp+200h+var_1B8]
0x1803002f2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803002f7  nop
0x1803002f8  lea     rcx, [rsp+200h+var_1C0]
0x1803002fd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180300302  nop
0x180300303  lea     rcx, [rsp+200h+var_1C8]
0x180300308  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18030030d  mov     ebx, 80070005h
0x180300312  jmp     loc_18030051D
0x180300317  lea     rcx, [rsp+200h+result]; void *
0x18030031c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180300321  mov     [rsp+200h+StringSid], r14
0x180300326  mov     [rsp+200h+var_188], r14
0x18030032b  mov     [rbp+100h+var_180], r14
0x18030032f  lea     rcx, [rsp+200h+StringSid]
0x180300334  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180300339  or      rax, 0FFFFFFFFFFFFFFFFh
0x18030033d  mov     [rsp+200h+var_188], rax
0x180300342  mov     [rbp+100h+var_180], rax
0x180300346  lea     rcx, [rsp+200h+StringSid]; StringSid
0x18030034b  call    ?GetCurrentUserSidString@@YAJPEAPEAG@Z; GetCurrentUserSidString(ushort * *)
0x180300350  mov     ebx, eax
0x180300352  test    eax, eax
0x180300354  jns     short loc_180300376
0x180300356  mov     rcx, [rbp+108h]; this
0x18030035d  mov     r9d, eax; char *
0x180300360  lea     r8, aOnecoreuapShel_98; "onecoreuap\\shell\\windows.storage\\dsw"...
0x180300367  mov     edx, 7Eh ; '~'; void *
0x18030036c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180300371  jmp     loc_1803004F1
0x180300376  mov     ebx, [rsp+200h+var_1A8]
0x18030037a  xor     edx, edx; Val
0x18030037c  mov     r8d, 150h; Size
0x180300382  lea     rcx, [rbp+100h+var_170]; void *
0x180300386  call    memset_0
0x18030038b  mov     eax, [rbp+100h+var_170]
0x18030038e  mov     ecx, 2
0x180300393  bt      ebx, 6
0x180300397  cmovnb  eax, ecx
0x18030039a  mov     [rbp+100h+var_170], eax
0x18030039d  mov     [rbp+100h+var_16C], 7
0x1803003a4  mov     [rbp+100h+var_160], r14d
0x1803003a8  mov     rax, [rsp+200h+StringSid]
0x1803003ad  mov     [rbp+100h+var_158], rax
0x1803003b1  mov     [rbp+100h+var_168], 1
0x1803003b8  mov     qword ptr [rsp+200h+var_1D0], r14
0x1803003bd  xor     edx, edx; length
0x1803003bf  mov     rcx, [rsp+200h+string]; string
0x1803003c4  call    cs:__imp_WindowsGetStringRawBuffer
0x1803003cb  nop     dword ptr [rax+rax+00h]
0x1803003d0  lea     rcx, [rsp+200h+var_1D0]
0x1803003d5  mov     qword ptr [rsp+200h+var_1E0], rcx
0x1803003da  xor     r9d, r9d
0x1803003dd  lea     r8d, [r9+1]
0x1803003e1  lea     rdx, [rbp+100h+var_170]
0x1803003e5  mov     rcx, rax
0x1803003e8  call    cs:__imp_DSCreateSharedFileToken
0x1803003ef  nop     dword ptr [rax+rax+00h]
0x1803003f4  mov     edi, eax
0x1803003f6  bt      ebx, 6
0x1803003fa  jb      short loc_180300440
0x1803003fc  cmp     eax, 80070005h
0x180300401  jnz     short loc_180300440
0x180300403  mov     [rbp+100h+var_170], r14d
0x180300407  xor     edx, edx; length
0x180300409  mov     rcx, [rsp+200h+string]; string
0x18030040e  call    cs:__imp_WindowsGetStringRawBuffer
0x180300415  nop     dword ptr [rax+rax+00h]
0x18030041a  lea     rcx, [rsp+200h+var_1D0]
0x18030041f  mov     qword ptr [rsp+200h+var_1E0], rcx; int
0x180300424  xor     r9d, r9d
0x180300427  lea     r8d, [r9+1]
0x18030042b  lea     rdx, [rbp+100h+var_170]
0x18030042f  mov     rcx, rax
0x180300432  call    cs:__imp_DSCreateSharedFileToken
0x180300439  nop     dword ptr [rax+rax+00h]
0x18030043e  mov     edi, eax
0x180300440  test    edi, edi
0x180300442  jns     short loc_180300491
0x180300444  mov     rcx, [rbp+108h]; this
0x18030044b  mov     r9d, edi; char *
0x18030044e  lea     r8, aOnecoreuapShel_98; "onecoreuap\\shell\\windows.storage\\dsw"...
0x180300455  mov     edx, 9Fh; void *
0x18030045a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18030045f  lea     rcx, [rsp+200h+StringSid]
0x180300464  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180300469  nop
0x18030046a  lea     rcx, [rsp+200h+var_1B8]
0x18030046f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180300474  nop
0x180300475  lea     rcx, [rsp+200h+var_1C0]
0x18030047a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18030047f  nop
0x180300480  lea     rcx, [rsp+200h+var_1C8]
0x180300485  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18030048a  mov     ebx, edi
0x18030048c  jmp     loc_18030051D
0x180300491  mov     [rsp+200h+var_198], r14
0x180300496  lea     rdx, [rsp+200h+var_1D0]
0x18030049b  lea     rcx, [rsp+200h+var_198]
0x1803004a0  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1803004a5  mov     ebx, eax
0x1803004a7  test    eax, eax
0x1803004a9  jns     loc_180300558
0x1803004af  mov     rcx, [rbp+108h]; this
0x1803004b6  mov     r9d, eax; char *
0x1803004b9  lea     r8, aOnecoreuapShel_98; "onecoreuap\\shell\\windows.storage\\dsw"...
0x1803004c0  mov     edx, 0A8h; void *
0x1803004c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803004ca  mov     rcx, [rsp+200h+var_198]; string
0x1803004cf  call    cs:__imp_WindowsDeleteString
0x1803004d6  nop     dword ptr [rax+rax+00h]
0x1803004db  mov     [rsp+200h+var_198], r14
0x1803004e0  mov     rcx, qword ptr [rsp+200h+var_1D0]
0x1803004e5  call    cs:__imp_DSFreeString
0x1803004ec  nop     dword ptr [rax+rax+00h]
0x1803004f1  lea     rcx, [rsp+200h+StringSid]
0x1803004f6  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
  ... truncated ...
```
