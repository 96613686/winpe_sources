# StateRepositoryFileTypeAssocReader::GetFileTypeAssoc(IInspectable * *)

- ea: `0x180154898`
- end: `0x180154d29`
- name: `?GetFileTypeAssoc@StateRepositoryFileTypeAssocReader@@AEAAJPEAPEAUIInspectable@@@Z`
- size: `1169`
- prototype: `int(StateRepositoryFileTypeAssocReader *__hidden this, struct IInspectable **)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18015474c`
- `0x1805d9f04`

## callees

- `0x18000d6cc`
- `0x180026fc4`
- `0x1800432f0`
- `0x180154898`
- `0x1801f85b0`
- `0x1803a4cb0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801548ff`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801548ff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180154ab6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180154ab6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180154c88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180154cd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180154c88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180154cd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801548e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801548e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180154a99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180154a99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180154a4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180154ac8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180154af6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180154a4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180154ac8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180154af6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180154a81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180154a81`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180154921`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180154921`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x180154c2c`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x180154c2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall StateRepositoryFileTypeAssocReader::GetFileTypeAssoc(HSTRING *this, struct IInspectable **a2)
{
  HRESULT v4; // eax
  HSTRING v5; // rbx
  int ActivationFactory; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING, __int64 *); // rbx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdx
  char v15; // r14
  unsigned int i; // esi
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64 *); // rbx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  HRESULT v21; // eax
  const WCHAR *StringRawBuffer; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, __int64 **); // rbx
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  const unsigned __int16 *v32; // r8
  __int64 v33; // rdx
  void *v34; // rcx
  void *v35; // rcx
  void **bIgnoreCase; // [rsp+20h] [rbp-59h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-49h] BYREF
  HSTRING string; // [rsp+48h] [rbp-31h] BYREF
  __int64 v39; // [rsp+50h] [rbp-29h] BYREF
  HSTRING string1; // [rsp+58h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-19h] BYREF
  __int64 v42; // [rsp+68h] [rbp-11h] BYREF
  __int64 *v43; // [rsp+70h] [rbp-9h] BYREF
  __int64 v44; // [rsp+78h] [rbp-1h] BYREF
  StateRepoHelpers *v45; // [rsp+80h] [rbp+7h] BYREF
  unsigned int v46; // [rsp+88h] [rbp+Fh] BYREF
  INT32 result; // [rsp+8Ch] [rbp+13h] BYREF
  unsigned int v48; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *a2 = 0;
  v42 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.FileTypeAssociation",
         0x34u,
         &hstringHeader,
         &string);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    __debugbreak();
  }
  v5 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_8645456f_d9a2_4b82_afec_58f0e8df0acf, &v42);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\assocutil.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)bIgnoreCase);
    v8 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return v7;
  }
  v44 = 0;
  v10 = v42;
  v11 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v42 + 200LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  v12 = v11(v10, *this, &v44);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\assocutil.cpp",
      (const char *)(unsigned int)v12,
      (int)bIgnoreCase);
    goto LABEL_47;
  }
  v39 = 0;
  v46 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v44 + 56LL))(v44, &v46);
  v7 = v13;
  if ( v13 < 0 )
  {
    v14 = 63;
    goto LABEL_11;
  }
  v15 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= v46 )
    {
      if ( !v15 )
      {
        v24 = v39;
        if ( v39 )
        {
          v39 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        }
        v25 = v44;
        if ( v44 )
        {
          v44 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        }
        v26 = v42;
        if ( v42 )
        {
          v42 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
        return 0;
      }
LABEL_34:
      v43 = 0;
      v27 = v39;
      v28 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v39 + 96LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      v29 = v28(v27, &v43);
      v7 = v29;
      if ( v29 >= 0 )
      {
        v48 = 0;
        pv = 0;
        v30 = *v43;
        hstringHeader.Reserved.Reserved1 = &pv;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
        hstringHeader.Reserved.Reserved2[16] = 1;
        v7 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, char *))(v30 + 512))(
               v43,
               &v48,
               &hstringHeader.Reserved.Reserved2[8]);
        wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&hstringHeader);
        if ( (v7 & 0x80000000) == 0 )
        {
          v45 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
          v31 = SRDictionaryToPropertySet(v48, pv, &v45);
          v7 = v31;
          if ( v31 >= 0 )
          {
            v31 = StateRepoHelpers::LookupInPropertySet(
                    v45,
                    (struct IInspectable *)&stru_18073ADA0,
                    v32,
                    (const struct _GUID *)a2,
                    bIgnoreCase);
            v7 = v31;
            if ( v31 >= 0 )
            {
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
              v35 = pv;
              pv = 0;
              if ( v35 )
                CoTaskMemFree(v35);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
              return 0;
            }
            v33 = 102;
          }
          else
          {
            v33 = 99;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v33,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\assocutil.cpp",
            (const char *)(unsigned int)v31,
            (int)bIgnoreCase);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x61,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\assocutil.cpp",
            (const char *)v7,
            (int)bIgnoreCase);
        }
        v34 = pv;
        pv = 0;
        if ( v34 )
          CoTaskMemFree(v34);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5D,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\assocutil.cpp",
          (const char *)(unsigned int)v29,
          (int)bIgnoreCase);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      goto LABEL_46;
    }
    if ( v15 )
      goto LABEL_34;
    v17 = v44;
    v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v44 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    v13 = v18(v17, i, &v39);
    v7 = v13;
    if ( v13 < 0 )
      break;
    string1 = 0;
    v19 = v39;
    v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 64LL);
    WindowsDeleteString(0);
    string1 = 0;
    v21 = v20(v19, &string1);
    v7 = v21;
    if ( v21 < 0 )
    {
      v23 = 74;
      goto LABEL_23;
    }
    result = 0;
    v21 = WindowsCompareStringOrdinal(string1, this[1], &result);
    v7 = v21;
    if ( v21 < 0 )
    {
      v23 = 77;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\assocutil.cpp",
        (const char *)(unsigned int)v21,
        (int)bIgnoreCase);
      WindowsDeleteString(string1);
      string1 = 0;
      goto LABEL_46;
    }
    if ( !result
      || (StringRawBuffer = WindowsGetStringRawBuffer(string1, 0),
          CompareStringOrdinal(L"*", -1, StringRawBuffer, -1, 0) == 2) )
    {
      v15 = 1;
    }
    WindowsDeleteString(string1);
    string1 = 0;
  }
  v14 = 70;
LABEL_11:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\assocutil.cpp",
    (const char *)(unsigned int)v13,
    (int)bIgnoreCase);
LABEL_46:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
LABEL_47:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  return v7;
}

```

## disassembly

```asm
0x180154898  mov     [rsp-8+arg_10], rbx
0x18015489d  push    rbp
0x18015489e  push    rsi
0x18015489f  push    rdi
0x1801548a0  push    r12
0x1801548a2  push    r13
0x1801548a4  push    r14
0x1801548a6  push    r15
0x1801548a8  lea     rbp, [rsp-27h]
0x1801548ad  sub     rsp, 0A0h
0x1801548b4  mov     rax, cs:__security_cookie
0x1801548bb  xor     rax, rsp
0x1801548be  mov     [rbp+57h+var_38], rax
0x1801548c2  mov     r12, rdx
0x1801548c5  mov     r15, rcx
0x1801548c8  xor     r13d, r13d
0x1801548cb  mov     [rdx], r13
0x1801548ce  mov     [rbp+57h+var_68], r13
0x1801548d2  mov     [rbp+57h+string], r13
0x1801548d6  lea     r9, [rbp+57h+string]; string
0x1801548da  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1801548de  lea     edx, [r13+34h]; length
0x1801548e2  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_FileTypeAssociation@@3QBGB; "Windows.Internal.StateRepository.FileTy"...
0x1801548e9  call    cs:__imp_WindowsCreateStringReference
0x1801548ef  test    eax, eax
0x1801548f1  jns     short loc_180154906
0x1801548f3  xor     r9d, r9d; lpArguments
0x1801548f6  xor     r8d, r8d; nNumberOfArguments
0x1801548f9  lea     edx, [r13+1]; dwExceptionFlags
0x1801548fd  mov     ecx, eax; dwExceptionCode
0x1801548ff  call    cs:__imp_RaiseException
0x180154905  int     3; Trap to Debugger
0x180154906  mov     rbx, [rbp+57h+string]
0x18015490a  lea     rcx, [rbp+57h+var_68]
0x18015490e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180154913  lea     r8, [rbp+57h+var_68]
0x180154917  lea     rdx, _GUID_8645456f_d9a2_4b82_afec_58f0e8df0acf
0x18015491e  mov     rcx, rbx
0x180154921  call    cs:__imp_RoGetActivationFactory
0x180154927  mov     ebx, eax
0x180154929  test    eax, eax
0x18015492b  jns     short loc_180154967
0x18015492d  mov     rcx, [rbp+5Fh]; this
0x180154931  mov     r9d, eax; char *
0x180154934  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\windows.storage\\sha"...
0x18015493b  mov     edx, 37h ; '7'; void *
0x180154940  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180154945  nop
0x180154946  mov     rcx, [rbp+57h+var_68]
0x18015494a  test    rcx, rcx
0x18015494d  jz      short loc_180154960
0x18015494f  mov     [rbp+57h+var_68], r13
0x180154953  mov     rax, [rcx]
0x180154956  mov     rax, [rax+10h]
0x18015495a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015495f  nop
0x180154960  mov     eax, ebx
0x180154962  jmp     loc_180154D02
0x180154967  mov     [rbp+57h+var_58], r13
0x18015496b  mov     rdi, [rbp+57h+var_68]
0x18015496f  mov     rax, [rdi]
0x180154972  mov     rbx, [rax+0C8h]
0x180154979  lea     rcx, [rbp+57h+var_58]
0x18015497d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180154982  lea     r8, [rbp+57h+var_58]
0x180154986  mov     rdx, [r15]
0x180154989  mov     rcx, rdi
0x18015498c  mov     rax, rbx
0x18015498f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154994  mov     ebx, eax
0x180154996  test    eax, eax
0x180154998  jns     short loc_1801549B7
0x18015499a  mov     rcx, [rbp+5Fh]; this
0x18015499e  mov     r9d, eax; char *
0x1801549a1  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\windows.storage\\sha"...
0x1801549a8  mov     edx, 3Bh ; ';'; void *
0x1801549ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801549b2  jmp     loc_180154CA3
0x1801549b7  mov     [rbp+57h+var_80], r13
0x1801549bb  mov     [rbp+57h+var_48], r13d
0x1801549bf  mov     rcx, [rbp+57h+var_58]
0x1801549c3  mov     rax, [rcx]
0x1801549c6  lea     rdx, [rbp+57h+var_48]
0x1801549ca  mov     rax, [rax+38h]
0x1801549ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801549d3  mov     ebx, eax
0x1801549d5  test    eax, eax
0x1801549d7  jns     short loc_1801549F6
0x1801549d9  mov     edx, 3Fh ; '?'; void *
0x1801549de  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\windows.storage\\sha"...
0x1801549e5  mov     r9d, eax; char *
0x1801549e8  mov     rcx, [rbp+5Fh]; this
0x1801549ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801549f1  jmp     loc_180154C99
0x1801549f6  mov     r14b, r13b
0x1801549f9  mov     esi, r13d
0x1801549fc  cmp     esi, [rbp+57h+var_48]
0x1801549ff  jnb     loc_180154B16
0x180154a05  test    r14b, r14b
0x180154a08  jnz     loc_180154B6E
0x180154a0e  mov     rdi, [rbp+57h+var_58]
0x180154a12  mov     rax, [rdi]
0x180154a15  mov     rbx, [rax+30h]
0x180154a19  lea     rcx, [rbp+57h+var_80]
0x180154a1d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180154a22  lea     r8, [rbp+57h+var_80]
0x180154a26  mov     edx, esi
0x180154a28  mov     rcx, rdi
0x180154a2b  mov     rax, rbx
0x180154a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154a33  mov     ebx, eax
0x180154a35  test    eax, eax
0x180154a37  js      loc_180154B0C
0x180154a3d  mov     [rbp+57h+string1], r13
0x180154a41  mov     rdi, [rbp+57h+var_80]
0x180154a45  mov     rax, [rdi]
0x180154a48  mov     rbx, [rax+40h]
0x180154a4c  xor     ecx, ecx; string
0x180154a4e  call    cs:__imp_WindowsDeleteString
0x180154a54  mov     [rbp+57h+string1], r13
0x180154a58  lea     rdx, [rbp+57h+string1]
0x180154a5c  mov     rcx, rdi
0x180154a5f  mov     rax, rbx
0x180154a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154a67  mov     ebx, eax
0x180154a69  test    eax, eax
0x180154a6b  js      loc_180154B05
0x180154a71  mov     [rbp+57h+result], r13d
0x180154a75  lea     r8, [rbp+57h+result]; result
0x180154a79  mov     rdx, [r15+8]; string2
0x180154a7d  mov     rcx, [rbp+57h+string1]; string1
0x180154a81  call    cs:__imp_WindowsCompareStringOrdinal
0x180154a87  mov     ebx, eax
0x180154a89  test    eax, eax
0x180154a8b  js      short loc_180154AD9
0x180154a8d  cmp     [rbp+57h+result], r13d
0x180154a91  jz      short loc_180154AC1
0x180154a93  xor     edx, edx; length
0x180154a95  mov     rcx, [rbp+57h+string1]; string
0x180154a99  call    cs:__imp_WindowsGetStringRawBuffer
0x180154a9f  mov     [rsp+0D0h+bIgnoreCase], r13d; bIgnoreCase
0x180154aa4  or      ebx, 0FFFFFFFFh
0x180154aa7  mov     r9d, ebx; cchCount2
0x180154aaa  mov     r8, rax; lpString2
0x180154aad  mov     edx, ebx; cchCount1
0x180154aaf  lea     rcx, asc_180709E7C; "*"
0x180154ab6  call    cs:__imp_CompareStringOrdinal
0x180154abc  cmp     eax, 2
0x180154abf  jnz     short loc_180154AC4
0x180154ac1  mov     r14b, 1
0x180154ac4  mov     rcx, [rbp+57h+string1]; string
0x180154ac8  call    cs:__imp_WindowsDeleteString
0x180154ace  mov     [rbp+57h+string1], r13
0x180154ad2  inc     esi
0x180154ad4  jmp     loc_1801549FC
0x180154ad9  mov     edx, 4Dh ; 'M'; void *
0x180154ade  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\windows.storage\\sha"...
0x180154ae5  mov     r9d, eax; char *
0x180154ae8  mov     rcx, [rbp+5Fh]; this
0x180154aec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180154af1  nop
0x180154af2  mov     rcx, [rbp+57h+string1]; string
0x180154af6  call    cs:__imp_WindowsDeleteString
0x180154afc  mov     [rbp+57h+string1], r13
0x180154b00  jmp     loc_180154C99
0x180154b05  mov     edx, 4Ah ; 'J'
0x180154b0a  jmp     short loc_180154ADE
0x180154b0c  mov     edx, 46h ; 'F'
0x180154b11  jmp     loc_1801549DE
0x180154b16  test    r14b, r14b
0x180154b19  jnz     short loc_180154B6E
0x180154b1b  mov     rcx, [rbp+57h+var_80]
0x180154b1f  test    rcx, rcx
0x180154b22  jz      short loc_180154B35
0x180154b24  mov     [rbp+57h+var_80], r13
0x180154b28  mov     rax, [rcx]
0x180154b2b  mov     rax, [rax+10h]
0x180154b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154b34  nop
0x180154b35  mov     rcx, [rbp+57h+var_58]
0x180154b39  test    rcx, rcx
0x180154b3c  jz      short loc_180154B4F
0x180154b3e  mov     [rbp+57h+var_58], r13
0x180154b42  mov     rax, [rcx]
0x180154b45  mov     rax, [rax+10h]
0x180154b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154b4e  nop
0x180154b4f  mov     rcx, [rbp+57h+var_68]
0x180154b53  test    rcx, rcx
0x180154b56  jz      short loc_180154B69
0x180154b58  mov     [rbp+57h+var_68], r13
0x180154b5c  mov     rax, [rcx]
0x180154b5f  mov     rax, [rax+10h]
0x180154b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154b68  nop
0x180154b69  jmp     loc_180154D00
0x180154b6e  mov     [rbp+57h+var_60], r13
0x180154b72  mov     rdi, [rbp+57h+var_80]
0x180154b76  mov     rax, [rdi]
0x180154b79  mov     rbx, [rax+60h]
0x180154b7d  lea     rcx, [rbp+57h+var_60]
0x180154b81  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180154b86  lea     rdx, [rbp+57h+var_60]
0x180154b8a  mov     rcx, rdi
0x180154b8d  mov     rax, rbx
0x180154b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154b95  mov     ebx, eax
0x180154b97  test    eax, eax
0x180154b99  jns     short loc_180154BB8
0x180154b9b  mov     rcx, [rbp+5Fh]; this
0x180154b9f  mov     r9d, eax; char *
0x180154ba2  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\windows.storage\\sha"...
0x180154ba9  mov     edx, 5Dh ; ']'; void *
0x180154bae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180154bb3  jmp     loc_180154C8F
0x180154bb8  mov     [rbp+57h+var_40], r13d
0x180154bbc  mov     [rbp+57h+pv], r13
0x180154bc0  mov     rcx, [rbp+57h+var_60]
0x180154bc4  mov     rax, [rcx]
0x180154bc7  lea     rdx, [rbp+57h+pv]
0x180154bcb  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rdx
0x180154bcf  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r13
0x180154bd3  mov     byte ptr [rbp+57h+hstringHeader.Reserved+10h], 1
0x180154bd7  lea     r8, [rbp+57h+hstringHeader.Reserved+8]
0x180154bdb  lea     rdx, [rbp+57h+var_40]
0x180154bdf  mov     rax, [rax+200h]
0x180154be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154beb  mov     ebx, eax
0x180154bed  lea     rcx, [rbp+57h+hstringHeader]
0x180154bf1  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180154bf6  test    ebx, ebx
0x180154bf8  jns     short loc_180154C14
0x180154bfa  mov     rcx, [rbp+5Fh]; this
0x180154bfe  mov     r9d, ebx; char *
0x180154c01  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\windows.storage\\sha"...
0x180154c08  mov     edx, 61h ; 'a'; void *
0x180154c0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180154c12  jmp     short loc_180154C7B
0x180154c14  mov     [rbp+57h+var_50], r13
0x180154c18  lea     rcx, [rbp+57h+var_50]
0x180154c1c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180154c21  lea     r8, [rbp+57h+var_50]
0x180154c25  mov     rdx, [rbp+57h+pv]
0x180154c29  mov     ecx, [rbp+57h+var_40]
0x180154c2c  call    cs:__imp_SRDictionaryToPropertySet
0x180154c32  mov     ebx, eax
0x180154c34  test    eax, eax
0x180154c36  jns     short loc_180154C3F
0x180154c38  mov     edx, 63h ; 'c'
0x180154c3d  jmp     short loc_180154C5D
0x180154c3f  mov     r9, r12; struct _GUID *
0x180154c42  lea     rdx, stru_18073ADA0; struct IInspectable *
0x180154c49  mov     rcx, [rbp+57h+var_50]; this
0x180154c4d  call    ?LookupInPropertySet@StateRepoHelpers@@YAJPEAUIInspectable@@PEBGAEBU_GUID@@PEAPEAX@Z; StateRepoHelpers::LookupInPropertySet(IInspectable *,ushort const *,_GUID const &,void * *)
0x180154c52  mov     ebx, eax
0x180154c54  test    eax, eax
0x180154c56  jns     short loc_180154CBB
0x180154c58  mov     edx, 66h ; 'f'; void *
0x180154c5d  mov     r9d, eax; char *
0x180154c60  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\windows.storage\\sha"...
0x180154c67  mov     rcx, [rbp+5Fh]; this
0x180154c6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180154c70  nop
0x180154c71  lea     rcx, [rbp+57h+var_50]
0x180154c75  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180154c7a  nop
0x180154c7b  mov     rcx, [rbp+57h+pv]; pv
0x180154c7f  mov     [rbp+57h+pv], r13
0x180154c83  test    rcx, rcx
0x180154c86  jz      short loc_180154C8F
0x180154c88  call    cs:__imp_CoTaskMemFree
0x180154c8e  nop
0x180154c8f  lea     rcx, [rbp+57h+var_60]
0x180154c93  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180154c98  nop
0x180154c99  lea     rcx, [rbp+57h+var_80]
0x180154c9d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180154ca2  nop
0x180154ca3  lea     rcx, [rbp+57h+var_58]
0x180154ca7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180154cac  nop
0x180154cad  lea     rcx, [rbp+57h+var_68]
0x180154cb1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180154cb6  jmp     loc_180154960
0x180154cbb  lea     rcx, [rbp+57h+var_50]
0x180154cbf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180154cc4  nop
0x180154cc5  mov     rcx, [rbp+57h+pv]; pv
0x180154cc9  mov     [rbp+57h+pv], r13
0x180154ccd  test    rcx, rcx
0x180154cd0  jz      short loc_180154CD9
0x180154cd2  call    cs:__imp_CoTaskMemFree
0x180154cd8  nop
0x180154cd9  lea     rcx, [rbp+57h+var_60]
0x180154cdd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180154ce2  nop
0x180154ce3  lea     rcx, [rbp+57h+var_80]
0x180154ce7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180154cec  nop
0x180154ced  lea     rcx, [rbp+57h+var_58]
  ... truncated ...
```
