# TryGetHostNameAndPath(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x18002747c`
- end: `0x18002775e`
- name: `?TryGetHostNameAndPath@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z`
- size: `738`
- prototype: `__int64 __fastcall(HSTRING, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000f280`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x18002747c`
- `0x18008a030`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002770a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002770a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027575`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800275e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027621`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002762f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002772e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002773c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027539`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027575`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800275e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027621`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002762f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002772e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002773c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800274ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800274ca`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800274f3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800274f3`

## string_xrefs

- `0x1800274c3`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall TryGetHostNameAndPath(HSTRING a1, HSTRING *a2, HSTRING *a3)
{
  unsigned int v3; // ebx
  HRESULT v7; // eax
  HSTRING v8; // rbx
  int ActivationFactory; // eax
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  HSTRING v19; // rax
  HSTRING v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // [rsp+20h] [rbp-50h] BYREF
  HSTRING v27; // [rsp+28h] [rbp-48h] BYREF
  __int64 v28; // [rsp+30h] [rbp-40h] BYREF
  HSTRING v29; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  *a2 = 0;
  *a3 = 0;
  v26 = 0;
  string = 0;
  v7 = WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    RaiseException(v7, 1u, 0, 0);
    goto LABEL_25;
  }
  v8 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
  ActivationFactory = RoGetActivationFactory(v8, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v26);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF6,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v26);
    v23 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    return v3;
  }
  v28 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v26 + 48LL))(v26, a1, &v28);
  v3 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v10,
      v26);
    v24 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    return v3;
  }
  v27 = 0;
  v11 = v28;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 88LL);
  WindowsDeleteString(0);
  v27 = 0;
  v13 = v12(v11, &v27);
  v3 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFC,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v13,
      v26);
    WindowsDeleteString(v27);
    v27 = 0;
    v14 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    return v3;
  }
  v29 = 0;
  v17 = v28;
  v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 104LL);
  WindowsDeleteString(0);
  v29 = 0;
  v3 = v18(v17, &v29);
  if ( (v3 & 0x80000000) != 0 )
  {
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFF,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)v3,
      v26);
    WindowsDeleteString(v29);
    v29 = 0;
    WindowsDeleteString(v27);
    v27 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
    return v3;
  }
  v19 = v27;
  v27 = 0;
  *a2 = v19;
  v20 = v29;
  v29 = 0;
  *a3 = v20;
  WindowsDeleteString(0);
  v29 = 0;
  WindowsDeleteString(v27);
  v27 = 0;
  v21 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v22 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return 0;
}

```

## disassembly

```asm
0x18002747c  mov     [rsp-28h+arg_18], rbx
0x180027481  push    rbp
0x180027482  push    rsi
0x180027483  push    rdi
0x180027484  push    r14
0x180027486  push    r15
0x180027488  mov     rbp, rsp
0x18002748b  sub     rsp, 70h
0x18002748f  mov     rax, cs:__security_cookie
0x180027496  xor     rax, rsp
0x180027499  mov     [rbp+var_10], rax
0x18002749d  mov     r14, r8
0x1800274a0  mov     rsi, rdx
0x1800274a3  mov     rdi, rcx
0x1800274a6  xor     r15d, r15d
0x1800274a9  mov     [rdx], r15
0x1800274ac  mov     [r8], r15
0x1800274af  mov     [rbp+var_50], r15
0x1800274b3  mov     [rbp+string], r15
0x1800274b7  lea     r9, [rbp+string]; string
0x1800274bb  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800274bf  lea     edx, [r15+16h]; length
0x1800274c3  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1800274ca  call    cs:__imp_WindowsCreateStringReference
0x1800274d0  test    eax, eax
0x1800274d2  js      loc_1800276FE
0x1800274d8  mov     rbx, [rbp+string]
0x1800274dc  lea     rcx, [rbp+var_50]
0x1800274e0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800274e5  lea     r8, [rbp+var_50]
0x1800274e9  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x1800274f0  mov     rcx, rbx
0x1800274f3  call    cs:__imp_RoGetActivationFactory
0x1800274f9  mov     ebx, eax
0x1800274fb  test    eax, eax
0x1800274fd  js      loc_180027674
0x180027503  mov     [rbp+var_40], r15
0x180027507  mov     rcx, [rbp+var_50]
0x18002750b  mov     rax, [rcx]
0x18002750e  lea     r8, [rbp+var_40]
0x180027512  mov     rdx, rdi
0x180027515  mov     rax, [rax+30h]
0x180027519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002751e  mov     ebx, eax
0x180027520  test    eax, eax
0x180027522  js      loc_1800276AC
0x180027528  mov     [rbp+var_48], r15
0x18002752c  mov     rdi, [rbp+var_40]
0x180027530  mov     rax, [rdi]
0x180027533  mov     rbx, [rax+58h]
0x180027537  xor     ecx, ecx; string
0x180027539  call    cs:__imp_WindowsDeleteString
0x18002753f  mov     [rbp+var_48], r15
0x180027543  lea     rdx, [rbp+var_48]
0x180027547  mov     rcx, rdi
0x18002754a  mov     rax, rbx
0x18002754d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027552  mov     ebx, eax
0x180027554  test    eax, eax
0x180027556  jns     short loc_1800275D5
0x180027558  mov     rcx, [rbp+28h]; this
0x18002755c  mov     r9d, eax; char *
0x18002755f  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x180027566  mov     edx, 0FCh; void *
0x18002756b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027570  nop
0x180027571  mov     rcx, [rbp+var_48]; string
0x180027575  call    cs:__imp_WindowsDeleteString
0x18002757b  mov     [rbp+var_48], r15
0x18002757f  mov     rcx, [rbp+var_40]
0x180027583  test    rcx, rcx
0x180027586  jz      short loc_180027599
0x180027588  mov     [rbp+var_40], r15
0x18002758c  mov     rax, [rcx]
0x18002758f  mov     rax, [rax+10h]
0x180027593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027598  nop
0x180027599  mov     rcx, [rbp+var_50]
0x18002759d  test    rcx, rcx
0x1800275a0  jz      short loc_1800275B3
0x1800275a2  mov     [rbp+var_50], r15
0x1800275a6  mov     rax, [rcx]
0x1800275a9  mov     rax, [rax+10h]
0x1800275ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275b2  nop
0x1800275b3  mov     eax, ebx
0x1800275b5  mov     rcx, [rbp+var_10]
0x1800275b9  xor     rcx, rsp; StackCookie
0x1800275bc  call    __security_check_cookie
0x1800275c1  mov     rbx, [rsp+70h+arg_18]
0x1800275c9  add     rsp, 70h
0x1800275cd  pop     r15
0x1800275cf  pop     r14
0x1800275d1  pop     rdi
0x1800275d2  pop     rsi
0x1800275d3  pop     rbp
0x1800275d4  retn
0x1800275d5  mov     [rbp+var_38], r15
0x1800275d9  mov     rdi, [rbp+var_40]
0x1800275dd  mov     rax, [rdi]
0x1800275e0  mov     rbx, [rax+68h]
0x1800275e4  xor     ecx, ecx; string
0x1800275e6  call    cs:__imp_WindowsDeleteString
0x1800275ec  mov     [rbp+var_38], r15
0x1800275f0  lea     rdx, [rbp+var_38]
0x1800275f4  mov     rcx, rdi
0x1800275f7  mov     rax, rbx
0x1800275fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275ff  mov     ebx, eax
0x180027601  test    eax, eax
0x180027603  js      loc_180027711
0x180027609  mov     rax, [rbp+var_48]
0x18002760d  mov     [rbp+var_48], r15
0x180027611  mov     [rsi], rax
0x180027614  mov     rax, [rbp+var_38]
0x180027618  mov     [rbp+var_38], r15
0x18002761c  mov     [r14], rax
0x18002761f  xor     ecx, ecx; string
0x180027621  call    cs:__imp_WindowsDeleteString
0x180027627  mov     [rbp+var_38], r15
0x18002762b  mov     rcx, [rbp+var_48]; string
0x18002762f  call    cs:__imp_WindowsDeleteString
0x180027635  mov     [rbp+var_48], r15
0x180027639  mov     rcx, [rbp+var_40]
0x18002763d  test    rcx, rcx
0x180027640  jz      short loc_180027653
0x180027642  mov     [rbp+var_40], r15
0x180027646  mov     rax, [rcx]
0x180027649  mov     rax, [rax+10h]
0x18002764d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027652  nop
0x180027653  mov     rcx, [rbp+var_50]
0x180027657  test    rcx, rcx
0x18002765a  jz      short loc_18002766D
0x18002765c  mov     [rbp+var_50], r15
0x180027660  mov     rax, [rcx]
0x180027663  mov     rax, [rax+10h]
0x180027667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002766c  nop
0x18002766d  xor     eax, eax
0x18002766f  jmp     loc_1800275B5
0x180027674  mov     rcx, [rbp+28h]; this
0x180027678  mov     r9d, ebx; char *
0x18002767b  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x180027682  mov     edx, 0F6h; void *
0x180027687  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002768c  nop
0x18002768d  mov     rcx, [rbp+var_50]
0x180027691  test    rcx, rcx
0x180027694  jz      short loc_1800276A7
0x180027696  mov     [rbp+var_50], r15
0x18002769a  mov     rax, [rcx]
0x18002769d  mov     rax, [rax+10h]
0x1800276a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276a6  nop
0x1800276a7  jmp     loc_1800275B3
0x1800276ac  mov     rcx, [rbp+28h]; this
0x1800276b0  mov     r9d, ebx; char *
0x1800276b3  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x1800276ba  mov     edx, 0F9h; void *
0x1800276bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800276c4  nop
0x1800276c5  mov     rcx, [rbp+var_40]
0x1800276c9  test    rcx, rcx
0x1800276cc  jz      short loc_1800276DF
0x1800276ce  mov     [rbp+var_40], r15
0x1800276d2  mov     rax, [rcx]
0x1800276d5  mov     rax, [rax+10h]
0x1800276d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276de  nop
0x1800276df  mov     rcx, [rbp+var_50]
0x1800276e3  test    rcx, rcx
0x1800276e6  jz      short loc_1800276F9
0x1800276e8  mov     [rbp+var_50], r15
0x1800276ec  mov     rax, [rcx]
0x1800276ef  mov     rax, [rax+10h]
0x1800276f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276f8  nop
0x1800276f9  jmp     loc_1800275B3
0x1800276fe  xor     r9d, r9d; lpArguments
0x180027701  xor     r8d, r8d; nNumberOfArguments
0x180027704  lea     edx, [r9+1]; dwExceptionFlags
0x180027708  mov     ecx, eax; dwExceptionCode
0x18002770a  call    cs:__imp_RaiseException
0x180027710  nop
0x180027711  mov     rcx, [rbp+28h]; this
0x180027715  mov     r9d, ebx; char *
0x180027718  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18002771f  mov     edx, 0FFh; void *
0x180027724  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027729  nop
0x18002772a  mov     rcx, [rbp+var_38]; string
0x18002772e  call    cs:__imp_WindowsDeleteString
0x180027734  mov     [rbp+var_38], r15
0x180027738  mov     rcx, [rbp+var_48]; string
0x18002773c  call    cs:__imp_WindowsDeleteString
0x180027742  mov     [rbp+var_48], r15
0x180027746  lea     rcx, [rbp+var_40]
0x18002774a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002774f  nop
0x180027750  lea     rcx, [rbp+var_50]
0x180027754  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027759  jmp     loc_1800275B3
```
