# QueryStateRepositoryForAppUriHandlerSupport(Windows::Foundation::IUriRuntimeClass *,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IVectorView<HSTRING__ *> * *,Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *> * *)

- ea: `0x180028e3c`
- end: `0x180029136`
- name: `?QueryStateRepositoryForAppUriHandlerSupport@@YAJPEAUIUriRuntimeClass@Foundation@Windows@@PEAUHSTRING__@@1PEAPEAU?$IVectorView@PEAUHSTRING__@@@Collections@23@PEAPEAU?$IVectorView@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@623@@Z`
- size: `762`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180028c30`
- `0x180078f20`
- `0x1800d1090`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180028e3c`
- `0x180029184`
- `0x18006fba0`
- `0x18008a030`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028eaa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028eaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028f13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028f41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029005`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029013`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002908d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002909b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800290c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800290cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028f13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028f41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029005`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029013`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002908d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002909b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800290c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800290cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028e94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028e94`

## string_xrefs

- `0x180028e8d`: `Windows.Internal.StateRepository.AppUriHandler`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall QueryStateRepositoryForAppUriHandlerSupport(
        struct Windows::Foundation::IUriRuntimeClass *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  HRESULT v7; // eax
  int v8; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 (__fastcall *v12)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  __int64 (__fastcall *v13)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  int v14; // eax
  _QWORD *v15; // rdi
  __int64 v16; // rax
  __int64 (__fastcall *v17)(_QWORD *, _QWORD, HSTRING, HSTRING); // rbx
  int v18; // eax
  __int64 v19; // rdx
  __int64 (__fastcall *v20)(_QWORD *, _QWORD, HSTRING, HSTRING); // rbx
  int v21; // eax
  __int64 v22; // rcx
  _QWORD *v23; // rcx
  __int64 v24; // rcx
  _QWORD *v25; // rcx
  int v26; // [rsp+20h] [rbp-51h]
  int v27; // [rsp+20h] [rbp-51h]
  HSTRING v28; // [rsp+40h] [rbp-31h] BYREF
  HSTRING v29; // [rsp+48h] [rbp-29h] BYREF
  int v30[2]; // [rsp+50h] [rbp-21h] BYREF
  _QWORD *v31; // [rsp+58h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-11h] BYREF
  HSTRING string; // [rsp+78h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  *a5 = 0;
  v31 = 0;
  string = 0;
  v7 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.AppUriHandler", 0x2Eu, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    RaiseException(v7, 1u, 0, 0);
    __debugbreak();
  }
  v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IAppUriHandlerStatics>>(
         string,
         &v31);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43B,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v8,
      v26);
    v10 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
    }
    return v9;
  }
  *(_QWORD *)v30 = 0;
  v29 = 0;
  v28 = 0;
  v12 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a1 + 88LL);
  WindowsDeleteString(0);
  v29 = 0;
  v9 = v12(a1, &v29);
  if ( (v9 & 0x80000000) != 0 )
  {
LABEL_22:
    WindowsDeleteString(v28);
    v28 = 0;
    WindowsDeleteString(v29);
    v29 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    return v9;
  }
  v13 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a1 + 104LL);
  WindowsDeleteString(v28);
  v28 = 0;
  v14 = v13(a1, &v28);
  if ( v14 < 0 )
  {
    v9 = v14;
    goto LABEL_22;
  }
  v15 = v31;
  v16 = *v31;
  if ( a2 )
  {
    v17 = *(__int64 (__fastcall **)(_QWORD *, _QWORD, HSTRING, HSTRING))(v16 + 192);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
    v27 = a2;
    v18 = v17(v15, 0, v29, v28);
    v9 = v18;
    if ( v18 < 0 )
    {
      v19 = 1092;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v18,
        v27);
      goto LABEL_22;
    }
  }
  else
  {
    v20 = *(__int64 (__fastcall **)(_QWORD *, _QWORD, HSTRING, HSTRING))(v16 + 184);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
    v21 = v20(v15, 0, v29, v28);
    v9 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x448,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v21,
        (int)v30);
      WindowsDeleteString(v28);
      v28 = 0;
      WindowsDeleteString(v29);
      v29 = 0;
      v22 = *(_QWORD *)v30;
      if ( *(_QWORD *)v30 )
      {
        *(_QWORD *)v30 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      v23 = v31;
      if ( v31 )
      {
        v31 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
      }
      return v9;
    }
  }
  v18 = PopulateAppUriHandlers(a1, (__int64)a5);
  v9 = v18;
  if ( v18 < 0 )
  {
    v19 = 1099;
    goto LABEL_21;
  }
  WindowsDeleteString(v28);
  v28 = 0;
  WindowsDeleteString(v29);
  v29 = 0;
  v24 = *(_QWORD *)v30;
  if ( *(_QWORD *)v30 )
  {
    *(_QWORD *)v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v25 + 16LL))(v25);
  }
  return 0;
}

```

## disassembly

```asm
0x180028e3c  mov     [rsp-8+arg_18], rbx
0x180028e41  push    rbp
0x180028e42  push    rsi
0x180028e43  push    rdi
0x180028e44  push    r12
0x180028e46  push    r13
0x180028e48  push    r14
0x180028e4a  push    r15
0x180028e4c  lea     rbp, [rsp-1Fh]
0x180028e51  sub     rsp, 90h
0x180028e58  mov     rax, cs:__security_cookie
0x180028e5f  xor     rax, rsp
0x180028e62  mov     [rbp+4Fh+var_40], rax
0x180028e66  mov     r12, r8
0x180028e69  mov     r14, rdx
0x180028e6c  mov     rsi, rcx
0x180028e6f  mov     r15, qword ptr [rbp+4Fh+arg_20]
0x180028e73  xor     r13d, r13d
0x180028e76  mov     [r15], r13
0x180028e79  mov     [rbp+4Fh+var_68], r13
0x180028e7d  mov     [rbp+4Fh+string], r13
0x180028e81  lea     r9, [rbp+4Fh+string]; string
0x180028e85  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x180028e89  lea     edx, [r13+2Eh]; length
0x180028e8d  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_AppUriHandler@@3QBGB; "Windows.Internal.StateRepository.AppUri"...
0x180028e94  call    cs:__imp_WindowsCreateStringReference
0x180028e9a  test    eax, eax
0x180028e9c  jns     short loc_180028EB1
0x180028e9e  xor     r9d, r9d; lpArguments
0x180028ea1  xor     r8d, r8d; nNumberOfArguments
0x180028ea4  lea     edx, [r13+1]; dwExceptionFlags
0x180028ea8  mov     ecx, eax; dwExceptionCode
0x180028eaa  call    cs:__imp_RaiseException
0x180028eb0  int     3; Trap to Debugger
0x180028eb1  lea     rdx, [rbp+4Fh+var_68]
0x180028eb5  mov     rcx, [rbp+4Fh+string]
0x180028eb9  call    ??$GetActivationFactory@V?$ComPtr@UIAppUriHandlerStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAppUriHandlerStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IAppUriHandlerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IAppUriHandlerStatics>>)
0x180028ebe  mov     ebx, eax
0x180028ec0  test    eax, eax
0x180028ec2  jns     short loc_180028EFE
0x180028ec4  mov     rcx, [rbp+57h]; this
0x180028ec8  mov     r9d, eax; char *
0x180028ecb  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x180028ed2  mov     edx, 43Bh; void *
0x180028ed7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028edc  nop
0x180028edd  mov     rcx, [rbp+4Fh+var_68]
0x180028ee1  test    rcx, rcx
0x180028ee4  jz      short loc_180028EF7
0x180028ee6  mov     [rbp+4Fh+var_68], r13
0x180028eea  mov     rax, [rcx]
0x180028eed  mov     rax, [rax+10h]
0x180028ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ef6  nop
0x180028ef7  mov     eax, ebx
0x180028ef9  jmp     loc_18002910F
0x180028efe  mov     qword ptr [rbp+4Fh+var_70], r13
0x180028f02  mov     [rbp+4Fh+var_78], r13
0x180028f06  mov     [rbp+4Fh+var_80], r13
0x180028f0a  mov     rax, [rsi]
0x180028f0d  mov     rbx, [rax+58h]
0x180028f11  xor     ecx, ecx; string
0x180028f13  call    cs:__imp_WindowsDeleteString
0x180028f19  mov     [rbp+4Fh+var_78], r13
0x180028f1d  lea     rdx, [rbp+4Fh+var_78]
0x180028f21  mov     rcx, rsi
0x180028f24  mov     rax, rbx
0x180028f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f2c  mov     ebx, eax
0x180028f2e  test    eax, eax
0x180028f30  js      loc_180029089
0x180028f36  mov     rax, [rsi]
0x180028f39  mov     rbx, [rax+68h]
0x180028f3d  mov     rcx, [rbp+4Fh+var_80]; string
0x180028f41  call    cs:__imp_WindowsDeleteString
0x180028f47  mov     [rbp+4Fh+var_80], r13
0x180028f4b  lea     rdx, [rbp+4Fh+var_80]
0x180028f4f  mov     rcx, rsi
0x180028f52  mov     rax, rbx
0x180028f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f5a  test    eax, eax
0x180028f5c  jns     short loc_180028F65
0x180028f5e  mov     ebx, eax
0x180028f60  jmp     loc_180029089
0x180028f65  mov     rdi, [rbp+4Fh+var_68]
0x180028f69  lea     rcx, [rbp+4Fh+var_70]
0x180028f6d  mov     rax, [rdi]
0x180028f70  test    r14, r14
0x180028f73  jz      short loc_180028FB8
0x180028f75  mov     rbx, [rax+0C0h]
0x180028f7c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028f81  lea     rax, [rbp+4Fh+var_70]
0x180028f85  mov     [rsp+0C0h+var_98], rax
0x180028f8a  mov     qword ptr [rsp+0C0h+var_A0], r14
0x180028f8f  mov     r9, [rbp+4Fh+var_80]
0x180028f93  mov     r8, [rbp+4Fh+var_78]
0x180028f97  xor     edx, edx
0x180028f99  mov     rcx, rdi
0x180028f9c  mov     rax, rbx
0x180028f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fa4  mov     ebx, eax
0x180028fa6  test    eax, eax
0x180028fa8  jns     loc_180029056
0x180028fae  mov     edx, 444h
0x180028fb3  jmp     loc_180029075
0x180028fb8  mov     rbx, [rax+0B8h]
0x180028fbf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028fc4  lea     rax, [rbp+4Fh+var_70]
0x180028fc8  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180028fcd  mov     r9, [rbp+4Fh+var_80]
0x180028fd1  mov     r8, [rbp+4Fh+var_78]
0x180028fd5  xor     edx, edx
0x180028fd7  mov     rcx, rdi
0x180028fda  mov     rax, rbx
0x180028fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fe2  mov     ebx, eax
0x180028fe4  test    eax, eax
0x180028fe6  jns     short loc_180029056
0x180028fe8  mov     rcx, [rbp+57h]; this
0x180028fec  mov     r9d, eax; char *
0x180028fef  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x180028ff6  mov     edx, 448h; void *
0x180028ffb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029000  nop
0x180029001  mov     rcx, [rbp+4Fh+var_80]; string
0x180029005  call    cs:__imp_WindowsDeleteString
0x18002900b  mov     [rbp+4Fh+var_80], r13
0x18002900f  mov     rcx, [rbp+4Fh+var_78]; string
0x180029013  call    cs:__imp_WindowsDeleteString
0x180029019  mov     [rbp+4Fh+var_78], r13
0x18002901d  mov     rcx, qword ptr [rbp+4Fh+var_70]
0x180029021  test    rcx, rcx
0x180029024  jz      short loc_180029037
0x180029026  mov     qword ptr [rbp+4Fh+var_70], r13
0x18002902a  mov     rax, [rcx]
0x18002902d  mov     rax, [rax+10h]
0x180029031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029036  nop
0x180029037  mov     rcx, [rbp+4Fh+var_68]
0x18002903b  test    rcx, rcx
0x18002903e  jz      short loc_180029051
0x180029040  mov     [rbp+4Fh+var_68], r13
0x180029044  mov     rax, [rcx]
0x180029047  mov     rax, [rax+10h]
0x18002904b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029050  nop
0x180029051  jmp     loc_180028EF7
0x180029056  mov     qword ptr [rsp+0C0h+var_A0], r15; int
0x18002905b  mov     r8, r12
0x18002905e  mov     rdx, qword ptr [rbp+4Fh+var_70]
0x180029062  mov     rcx, rsi
0x180029065  call    ?PopulateAppUriHandlers@@YAJPEAUIUriRuntimeClass@Foundation@Windows@@PEAU?$IVectorView@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@Collections@23@PEAUHSTRING__@@PEAPEAU?$IVectorView@PEAUHSTRING__@@@523@PEAPEAU4523@@Z; PopulateAppUriHandlers(Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *> *,HSTRING__ *,Windows::Foundation::Collections::IVectorView<HSTRING__ *> * *,Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *> * *)
0x18002906a  mov     ebx, eax
0x18002906c  test    eax, eax
0x18002906e  jns     short loc_1800290BD
0x180029070  mov     edx, 44Bh; void *
0x180029075  mov     r9d, eax; char *
0x180029078  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18002907f  mov     rcx, [rbp+57h]; this
0x180029083  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029088  nop
0x180029089  mov     rcx, [rbp+4Fh+var_80]; string
0x18002908d  call    cs:__imp_WindowsDeleteString
0x180029093  mov     [rbp+4Fh+var_80], r13
0x180029097  mov     rcx, [rbp+4Fh+var_78]; string
0x18002909b  call    cs:__imp_WindowsDeleteString
0x1800290a1  mov     [rbp+4Fh+var_78], r13
0x1800290a5  lea     rcx, [rbp+4Fh+var_70]
0x1800290a9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800290ae  nop
0x1800290af  lea     rcx, [rbp+4Fh+var_68]
0x1800290b3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800290b8  jmp     loc_180028EF7
0x1800290bd  mov     rcx, [rbp+4Fh+var_80]; string
0x1800290c1  call    cs:__imp_WindowsDeleteString
0x1800290c7  mov     [rbp+4Fh+var_80], r13
0x1800290cb  mov     rcx, [rbp+4Fh+var_78]; string
0x1800290cf  call    cs:__imp_WindowsDeleteString
0x1800290d5  mov     [rbp+4Fh+var_78], r13
0x1800290d9  mov     rcx, qword ptr [rbp+4Fh+var_70]
0x1800290dd  test    rcx, rcx
0x1800290e0  jz      short loc_1800290F3
0x1800290e2  mov     qword ptr [rbp+4Fh+var_70], r13
0x1800290e6  mov     rax, [rcx]
0x1800290e9  mov     rax, [rax+10h]
0x1800290ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290f2  nop
0x1800290f3  mov     rcx, [rbp+4Fh+var_68]
0x1800290f7  test    rcx, rcx
0x1800290fa  jz      short loc_18002910D
0x1800290fc  mov     [rbp+4Fh+var_68], r13
0x180029100  mov     rax, [rcx]
0x180029103  mov     rax, [rax+10h]
0x180029107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002910c  nop
0x18002910d  xor     eax, eax
0x18002910f  mov     rcx, [rbp+4Fh+var_40]
0x180029113  xor     rcx, rsp; StackCookie
0x180029116  call    __security_check_cookie
0x18002911b  mov     rbx, [rsp+0C0h+arg_18]
0x180029123  add     rsp, 90h
0x18002912a  pop     r15
0x18002912c  pop     r14
0x18002912e  pop     r13
0x180029130  pop     r12
0x180029132  pop     rdi
0x180029133  pop     rsi
0x180029134  pop     rbp
0x180029135  retn
```
