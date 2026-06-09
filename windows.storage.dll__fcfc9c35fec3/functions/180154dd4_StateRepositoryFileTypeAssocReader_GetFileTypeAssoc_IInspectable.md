# StateRepositoryFileTypeAssocReader::GetFileTypeAssoc(IInspectable * *)

- ea: `0x180154dd4`
- end: `0x18015529d`
- name: `?GetFileTypeAssoc@StateRepositoryFileTypeAssocReader@@AEAAJPEAPEAUIInspectable@@@Z`
- size: `1225`
- prototype: `__int64 __fastcall(StateRepositoryFileTypeAssocReader *__hidden this, struct IInspectable **)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180154c70`
- `0x1805f8b40`

## callees

- `0x180009fc0`
- `0x180038f50`
- `0x180154dd4`
- `0x180174344`
- `0x18020eb30`
- `0x180356c84`
- `0x1803b1f60`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180155005`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180155005`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801551ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015523f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801551ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015523f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180154e25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180154e25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180154fe2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180154fe2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180154f8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015501d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180155051`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180154f8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015501d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180155051`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180154fc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180154fc4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180154e58`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180154e58`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x18015518d`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x18015518d`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall StateRepositoryFileTypeAssocReader::GetFileTypeAssoc(HSTRING *this, struct IInspectable **a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  HSTRING v7; // rbx
  int ActivationFactory; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING, __int64 *); // rbx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdx
  char v17; // r14
  unsigned int i; // esi
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64 *); // rbx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  HRESULT v23; // eax
  const WCHAR *StringRawBuffer; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64 **); // rbx
  int v31; // eax
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // r8
  __int64 v35; // rdx
  void *v36; // rcx
  void *v37; // rcx
  void **bIgnoreCase; // [rsp+20h] [rbp-59h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-49h] BYREF
  HSTRING string; // [rsp+48h] [rbp-31h] BYREF
  __int64 v41; // [rsp+50h] [rbp-29h] BYREF
  HSTRING string1; // [rsp+58h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-19h] BYREF
  __int64 v44; // [rsp+68h] [rbp-11h] BYREF
  __int64 *v45; // [rsp+70h] [rbp-9h] BYREF
  __int64 v46; // [rsp+78h] [rbp-1h] BYREF
  StateRepoHelpers *v47; // [rsp+80h] [rbp+7h] BYREF
  unsigned int v48; // [rsp+88h] [rbp+Fh] BYREF
  INT32 result; // [rsp+8Ch] [rbp+13h] BYREF
  unsigned int v50; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *a2 = 0;
  v44 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.FileTypeAssociation",
         0x34u,
         &hstringHeader,
         &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    __debugbreak();
  }
  v7 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  ActivationFactory = RoGetActivationFactory(v7, &GUID_8645456f_d9a2_4b82_afec_58f0e8df0acf, &v44);
  v9 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\assocutil.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)bIgnoreCase);
    v10 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return v9;
  }
  v46 = 0;
  v12 = v44;
  v13 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v44 + 200LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  v14 = v13(v12, *this, &v46);
  v9 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\assocutil.cpp",
      (const char *)(unsigned int)v14,
      (int)bIgnoreCase);
    goto LABEL_47;
  }
  v41 = 0;
  v48 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v46 + 56LL))(v46, &v48);
  v9 = v15;
  if ( v15 < 0 )
  {
    v16 = 63;
    goto LABEL_11;
  }
  v17 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= v48 )
    {
      if ( !v17 )
      {
        v26 = v41;
        if ( v41 )
        {
          v41 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
        v27 = v46;
        if ( v46 )
        {
          v46 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        v28 = v44;
        if ( v44 )
        {
          v44 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        }
        return 0;
      }
LABEL_34:
      v45 = 0;
      v29 = v41;
      v30 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v41 + 96LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      v31 = v30(v29, &v45);
      v9 = v31;
      if ( v31 >= 0 )
      {
        v50 = 0;
        pv = 0;
        v32 = *v45;
        hstringHeader.Reserved.Reserved1 = &pv;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
        hstringHeader.Reserved.Reserved2[16] = 1;
        v9 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, char *))(v32 + 512))(
               v45,
               &v50,
               &hstringHeader.Reserved.Reserved2[8]);
        wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&hstringHeader);
        if ( (v9 & 0x80000000) == 0 )
        {
          v47 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
          v33 = SRDictionaryToPropertySet(v50, pv, &v47);
          v9 = v33;
          if ( v33 >= 0 )
          {
            v33 = StateRepoHelpers::LookupInPropertySet(
                    v47,
                    (struct IInspectable *)&stru_18075EA58,
                    v34,
                    (const struct _GUID *)a2,
                    bIgnoreCase);
            v9 = v33;
            if ( v33 >= 0 )
            {
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
              v37 = pv;
              pv = 0;
              if ( v37 )
                CoTaskMemFree(v37);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
              return 0;
            }
            v35 = 102;
          }
          else
          {
            v35 = 99;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v35,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\assocutil.cpp",
            (const char *)(unsigned int)v33,
            (int)bIgnoreCase);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x61,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\assocutil.cpp",
            (const char *)v9,
            (int)bIgnoreCase);
        }
        v36 = pv;
        pv = 0;
        if ( v36 )
          CoTaskMemFree(v36);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5D,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\assocutil.cpp",
          (const char *)(unsigned int)v31,
          (int)bIgnoreCase);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      goto LABEL_46;
    }
    if ( v17 )
      goto LABEL_34;
    v19 = v46;
    v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v46 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
    v15 = v20(v19, i, &v41);
    v9 = v15;
    if ( v15 < 0 )
      break;
    string1 = 0;
    v21 = v41;
    v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v41 + 64LL);
    WindowsDeleteString(0);
    string1 = 0;
    v23 = v22(v21, &string1);
    v9 = v23;
    if ( v23 < 0 )
    {
      v25 = 74;
      goto LABEL_23;
    }
    result = 0;
    v23 = WindowsCompareStringOrdinal(string1, this[1], &result);
    v9 = v23;
    if ( v23 < 0 )
    {
      v25 = 77;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\assocutil.cpp",
        (const char *)(unsigned int)v23,
        (int)bIgnoreCase);
      WindowsDeleteString(string1);
      string1 = 0;
      goto LABEL_46;
    }
    if ( !result
      || (StringRawBuffer = WindowsGetStringRawBuffer(string1, 0),
          CompareStringOrdinal(L"*", -1, StringRawBuffer, -1, 0) == 2) )
    {
      v17 = 1;
    }
    WindowsDeleteString(string1);
    string1 = 0;
  }
  v16 = 70;
LABEL_11:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\sharedstoragesources\\assocutil.cpp",
    (const char *)(unsigned int)v15,
    (int)bIgnoreCase);
LABEL_46:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
LABEL_47:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  return v9;
}

```

## disassembly

```asm
0x180154dd4  mov     [rsp-8+arg_10], rbx
0x180154dd9  push    rbp
0x180154dda  push    rsi
0x180154ddb  push    rdi
0x180154ddc  push    r12
0x180154dde  push    r13
0x180154de0  push    r14
0x180154de2  push    r15
0x180154de4  lea     rbp, [rsp-27h]
0x180154de9  sub     rsp, 0A0h
0x180154df0  mov     rax, cs:__security_cookie
0x180154df7  xor     rax, rsp
0x180154dfa  mov     [rbp+57h+var_38], rax
0x180154dfe  mov     r12, rdx
0x180154e01  mov     r15, rcx
0x180154e04  xor     r13d, r13d
0x180154e07  mov     [rdx], r13
0x180154e0a  mov     [rbp+57h+var_68], r13
0x180154e0e  mov     [rbp+57h+string], r13
0x180154e12  lea     r9, [rbp+57h+string]; string
0x180154e16  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180154e1a  lea     edx, [r13+34h]; length
0x180154e1e  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_FileTypeAssociation@@3QBGB; "Windows.Internal.StateRepository.FileTy"...
0x180154e25  call    cs:__imp_WindowsCreateStringReference
0x180154e2c  nop     dword ptr [rax+rax+00h]
0x180154e31  test    eax, eax
0x180154e33  jns     short loc_180154E3D
0x180154e35  mov     ecx, eax; this
0x180154e37  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180154e3c  int     3; Trap to Debugger
0x180154e3d  mov     rbx, [rbp+57h+string]
0x180154e41  lea     rcx, [rbp+57h+var_68]
0x180154e45  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180154e4a  lea     r8, [rbp+57h+var_68]
0x180154e4e  lea     rdx, _GUID_8645456f_d9a2_4b82_afec_58f0e8df0acf
0x180154e55  mov     rcx, rbx
0x180154e58  call    cs:__imp_RoGetActivationFactory
0x180154e5f  nop     dword ptr [rax+rax+00h]
0x180154e64  mov     ebx, eax
0x180154e66  test    eax, eax
0x180154e68  jns     short loc_180154EA4
0x180154e6a  mov     rcx, [rbp+5Fh]; this
0x180154e6e  mov     r9d, eax; char *
0x180154e71  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\windows.storage\\sha"...
0x180154e78  mov     edx, 37h ; '7'; void *
0x180154e7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180154e82  nop
0x180154e83  mov     rcx, [rbp+57h+var_68]
0x180154e87  test    rcx, rcx
0x180154e8a  jz      short loc_180154E9D
0x180154e8c  mov     [rbp+57h+var_68], r13
0x180154e90  mov     rax, [rcx]
0x180154e93  mov     rax, [rax+10h]
0x180154e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154e9c  nop
0x180154e9d  mov     eax, ebx
0x180154e9f  jmp     loc_180155275
0x180154ea4  mov     [rbp+57h+var_58], r13
0x180154ea8  mov     rdi, [rbp+57h+var_68]
0x180154eac  mov     rax, [rdi]
0x180154eaf  mov     rbx, [rax+0C8h]
0x180154eb6  lea     rcx, [rbp+57h+var_58]
0x180154eba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180154ebf  lea     r8, [rbp+57h+var_58]
0x180154ec3  mov     rdx, [r15]
0x180154ec6  mov     rcx, rdi
0x180154ec9  mov     rax, rbx
0x180154ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154ed1  mov     ebx, eax
0x180154ed3  test    eax, eax
0x180154ed5  jns     short loc_180154EF4
0x180154ed7  mov     rcx, [rbp+5Fh]; this
0x180154edb  mov     r9d, eax; char *
0x180154ede  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\windows.storage\\sha"...
0x180154ee5  mov     edx, 3Bh ; ';'; void *
0x180154eea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180154eef  jmp     loc_180155210
0x180154ef4  mov     [rbp+57h+var_80], r13
0x180154ef8  mov     [rbp+57h+var_48], r13d
0x180154efc  mov     rcx, [rbp+57h+var_58]
0x180154f00  mov     rax, [rcx]
0x180154f03  lea     rdx, [rbp+57h+var_48]
0x180154f07  mov     rax, [rax+38h]
0x180154f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154f10  mov     ebx, eax
0x180154f12  test    eax, eax
0x180154f14  jns     short loc_180154F33
0x180154f16  mov     edx, 3Fh ; '?'; void *
0x180154f1b  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\windows.storage\\sha"...
0x180154f22  mov     r9d, eax; char *
0x180154f25  mov     rcx, [rbp+5Fh]; this
0x180154f29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180154f2e  jmp     loc_180155206
0x180154f33  mov     r14b, r13b
0x180154f36  mov     esi, r13d
0x180154f39  cmp     esi, [rbp+57h+var_48]
0x180154f3c  jnb     loc_180155077
0x180154f42  test    r14b, r14b
0x180154f45  jnz     loc_1801550CF
0x180154f4b  mov     rdi, [rbp+57h+var_58]
0x180154f4f  mov     rax, [rdi]
0x180154f52  mov     rbx, [rax+30h]
0x180154f56  lea     rcx, [rbp+57h+var_80]
0x180154f5a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180154f5f  lea     r8, [rbp+57h+var_80]
0x180154f63  mov     edx, esi
0x180154f65  mov     rcx, rdi
0x180154f68  mov     rax, rbx
0x180154f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154f70  mov     ebx, eax
0x180154f72  test    eax, eax
0x180154f74  js      loc_18015506D
0x180154f7a  mov     [rbp+57h+string1], r13
0x180154f7e  mov     rdi, [rbp+57h+var_80]
0x180154f82  mov     rax, [rdi]
0x180154f85  mov     rbx, [rax+40h]
0x180154f89  xor     ecx, ecx; string
0x180154f8b  call    cs:__imp_WindowsDeleteString
0x180154f92  nop     dword ptr [rax+rax+00h]
0x180154f97  mov     [rbp+57h+string1], r13
0x180154f9b  lea     rdx, [rbp+57h+string1]
0x180154f9f  mov     rcx, rdi
0x180154fa2  mov     rax, rbx
0x180154fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154faa  mov     ebx, eax
0x180154fac  test    eax, eax
0x180154fae  js      loc_180155066
0x180154fb4  mov     [rbp+57h+result], r13d
0x180154fb8  lea     r8, [rbp+57h+result]; result
0x180154fbc  mov     rdx, [r15+8]; string2
0x180154fc0  mov     rcx, [rbp+57h+string1]; string1
0x180154fc4  call    cs:__imp_WindowsCompareStringOrdinal
0x180154fcb  nop     dword ptr [rax+rax+00h]
0x180154fd0  mov     ebx, eax
0x180154fd2  test    eax, eax
0x180154fd4  js      short loc_180155034
0x180154fd6  cmp     [rbp+57h+result], r13d
0x180154fda  jz      short loc_180155016
0x180154fdc  xor     edx, edx; length
0x180154fde  mov     rcx, [rbp+57h+string1]; string
0x180154fe2  call    cs:__imp_WindowsGetStringRawBuffer
0x180154fe9  nop     dword ptr [rax+rax+00h]
0x180154fee  mov     [rsp+0D0h+bIgnoreCase], r13d; bIgnoreCase
0x180154ff3  or      ebx, 0FFFFFFFFh
0x180154ff6  mov     r9d, ebx; cchCount2
0x180154ff9  mov     r8, rax; lpString2
0x180154ffc  mov     edx, ebx; cchCount1
0x180154ffe  lea     rcx, String1; "*"
0x180155005  call    cs:__imp_CompareStringOrdinal
0x18015500c  nop     dword ptr [rax+rax+00h]
0x180155011  cmp     eax, 2
0x180155014  jnz     short loc_180155019
0x180155016  mov     r14b, 1
0x180155019  mov     rcx, [rbp+57h+string1]; string
0x18015501d  call    cs:__imp_WindowsDeleteString
0x180155024  nop     dword ptr [rax+rax+00h]
0x180155029  mov     [rbp+57h+string1], r13
0x18015502d  inc     esi
0x18015502f  jmp     loc_180154F39
0x180155034  mov     edx, 4Dh ; 'M'; void *
0x180155039  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\windows.storage\\sha"...
0x180155040  mov     r9d, eax; char *
0x180155043  mov     rcx, [rbp+5Fh]; this
0x180155047  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015504c  nop
0x18015504d  mov     rcx, [rbp+57h+string1]; string
0x180155051  call    cs:__imp_WindowsDeleteString
0x180155058  nop     dword ptr [rax+rax+00h]
0x18015505d  mov     [rbp+57h+string1], r13
0x180155061  jmp     loc_180155206
0x180155066  mov     edx, 4Ah ; 'J'
0x18015506b  jmp     short loc_180155039
0x18015506d  mov     edx, 46h ; 'F'
0x180155072  jmp     loc_180154F1B
0x180155077  test    r14b, r14b
0x18015507a  jnz     short loc_1801550CF
0x18015507c  mov     rcx, [rbp+57h+var_80]
0x180155080  test    rcx, rcx
0x180155083  jz      short loc_180155096
0x180155085  mov     [rbp+57h+var_80], r13
0x180155089  mov     rax, [rcx]
0x18015508c  mov     rax, [rax+10h]
0x180155090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155095  nop
0x180155096  mov     rcx, [rbp+57h+var_58]
0x18015509a  test    rcx, rcx
0x18015509d  jz      short loc_1801550B0
0x18015509f  mov     [rbp+57h+var_58], r13
0x1801550a3  mov     rax, [rcx]
0x1801550a6  mov     rax, [rax+10h]
0x1801550aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801550af  nop
0x1801550b0  mov     rcx, [rbp+57h+var_68]
0x1801550b4  test    rcx, rcx
0x1801550b7  jz      short loc_1801550CA
0x1801550b9  mov     [rbp+57h+var_68], r13
0x1801550bd  mov     rax, [rcx]
0x1801550c0  mov     rax, [rax+10h]
0x1801550c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801550c9  nop
0x1801550ca  jmp     loc_180155273
0x1801550cf  mov     [rbp+57h+var_60], r13
0x1801550d3  mov     rdi, [rbp+57h+var_80]
0x1801550d7  mov     rax, [rdi]
0x1801550da  mov     rbx, [rax+60h]
0x1801550de  lea     rcx, [rbp+57h+var_60]
0x1801550e2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801550e7  lea     rdx, [rbp+57h+var_60]
0x1801550eb  mov     rcx, rdi
0x1801550ee  mov     rax, rbx
0x1801550f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801550f6  mov     ebx, eax
0x1801550f8  test    eax, eax
0x1801550fa  jns     short loc_180155119
0x1801550fc  mov     rcx, [rbp+5Fh]; this
0x180155100  mov     r9d, eax; char *
0x180155103  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\windows.storage\\sha"...
0x18015510a  mov     edx, 5Dh ; ']'; void *
0x18015510f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180155114  jmp     loc_1801551FC
0x180155119  mov     [rbp+57h+var_40], r13d
0x18015511d  mov     [rbp+57h+pv], r13
0x180155121  mov     rcx, [rbp+57h+var_60]
0x180155125  mov     rax, [rcx]
0x180155128  lea     rdx, [rbp+57h+pv]
0x18015512c  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rdx
0x180155130  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r13
0x180155134  mov     byte ptr [rbp+57h+hstringHeader.Reserved+10h], 1
0x180155138  lea     r8, [rbp+57h+hstringHeader.Reserved+8]
0x18015513c  lea     rdx, [rbp+57h+var_40]
0x180155140  mov     rax, [rax+200h]
0x180155147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015514c  mov     ebx, eax
0x18015514e  lea     rcx, [rbp+57h+hstringHeader]
0x180155152  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180155157  test    ebx, ebx
0x180155159  jns     short loc_180155175
0x18015515b  mov     rcx, [rbp+5Fh]; this
0x18015515f  mov     r9d, ebx; char *
0x180155162  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\windows.storage\\sha"...
0x180155169  mov     edx, 61h ; 'a'; void *
0x18015516e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180155173  jmp     short loc_1801551E2
0x180155175  mov     [rbp+57h+var_50], r13
0x180155179  lea     rcx, [rbp+57h+var_50]
0x18015517d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180155182  lea     r8, [rbp+57h+var_50]
0x180155186  mov     rdx, [rbp+57h+pv]
0x18015518a  mov     ecx, [rbp+57h+var_40]
0x18015518d  call    cs:__imp_SRDictionaryToPropertySet
0x180155194  nop     dword ptr [rax+rax+00h]
0x180155199  mov     ebx, eax
0x18015519b  test    eax, eax
0x18015519d  jns     short loc_1801551A6
0x18015519f  mov     edx, 63h ; 'c'
0x1801551a4  jmp     short loc_1801551C4
0x1801551a6  mov     r9, r12; struct _GUID *
0x1801551a9  lea     rdx, stru_18075EA58; struct IInspectable *
0x1801551b0  mov     rcx, [rbp+57h+var_50]; this
0x1801551b4  call    ?LookupInPropertySet@StateRepoHelpers@@YAJPEAUIInspectable@@PEBGAEBU_GUID@@PEAPEAX@Z; StateRepoHelpers::LookupInPropertySet(IInspectable *,ushort const *,_GUID const &,void * *)
0x1801551b9  mov     ebx, eax
0x1801551bb  test    eax, eax
0x1801551bd  jns     short loc_180155228
0x1801551bf  mov     edx, 66h ; 'f'; void *
0x1801551c4  mov     r9d, eax; char *
0x1801551c7  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\windows.storage\\sha"...
0x1801551ce  mov     rcx, [rbp+5Fh]; this
0x1801551d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801551d7  nop
0x1801551d8  lea     rcx, [rbp+57h+var_50]
0x1801551dc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801551e1  nop
0x1801551e2  mov     rcx, [rbp+57h+pv]; pv
0x1801551e6  mov     [rbp+57h+pv], r13
0x1801551ea  test    rcx, rcx
0x1801551ed  jz      short loc_1801551FC
0x1801551ef  call    cs:__imp_CoTaskMemFree
0x1801551f6  nop     dword ptr [rax+rax+00h]
0x1801551fb  nop
0x1801551fc  lea     rcx, [rbp+57h+var_60]
0x180155200  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180155205  nop
0x180155206  lea     rcx, [rbp+57h+var_80]
0x18015520a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18015520f  nop
0x180155210  lea     rcx, [rbp+57h+var_58]
0x180155214  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180155219  nop
0x18015521a  lea     rcx, [rbp+57h+var_68]
0x18015521e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180155223  jmp     loc_180154E9D
0x180155228  lea     rcx, [rbp+57h+var_50]
0x18015522c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180155231  nop
0x180155232  mov     rcx, [rbp+57h+pv]; pv
0x180155236  mov     [rbp+57h+pv], r13
0x18015523a  test    rcx, rcx
0x18015523d  jz      short loc_18015524C
0x18015523f  call    cs:__imp_CoTaskMemFree
0x180155246  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
