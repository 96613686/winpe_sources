# BroadcastDVRComponent::LaunchGameOverlayWithStartupTipsFlag(HWND__ *,BroadcastDVRActiveAppInfo *)

- ea: `0x1801827b4`
- end: `0x180182b12`
- name: `?LaunchGameOverlayWithStartupTipsFlag@BroadcastDVRComponent@@AEAAJPEAUHWND__@@PEAUBroadcastDVRActiveAppInfo@@@Z`
- size: `862`
- prototype: `int(BroadcastDVRComponent *__hidden this, HWND, struct BroadcastDVRActiveAppInfo *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001eba0`

## callees

- `0x1800134f8`
- `0x180020328`
- `0x1800237c8`
- `0x1800f1dc0`
- `0x1801827b4`
- `0x1802b6978`
- `0x180356360`
- `0x180356edc`
- `0x180395f74`
- `0x1803980cc`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18018284b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18018284b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180182832`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180182a60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180182ac8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180182832`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180182a60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180182ac8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182904`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182959`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801829a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182a71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182904`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182959`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801829a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182a71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801829c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180182a47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180182ab1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801829c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180182a47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180182ab1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1801828a1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1801828a1`

## string_xrefs

- `0x180182870`: `pcshell\twinui\broadcastdvrcomponent\lib\broadcastdvrprovider.cpp`
- `0x1801828e8`: `pcshell\twinui\broadcastdvrcomponent\lib\broadcastdvrprovider.cpp`
- `0x180182988`: `pcshell\twinui\broadcastdvrcomponent\lib\broadcastdvrprovider.cpp`
- `0x18018282b`: `Windows.Foundation.Uri`
- `0x1801829fc`: `ms-gamingoverlay://startuptips?%ls=%ls&ProcessId=%lu&WindowId=%llu`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall BroadcastDVRComponent::LaunchGameOverlayWithStartupTipsFlag(
        BroadcastDVRComponent *this,
        HWND a2,
        struct BroadcastDVRActiveAppInfo *a3)
{
  HWND v4; // r14
  int v5; // eax
  unsigned int v6; // ebx
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rdi
  int v9; // eax
  __int64 v10; // rcx
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, HSTRING *); // rbx
  int v14; // eax
  PCWSTR v15; // rax
  const wchar_t *v16; // r8
  int v17; // eax
  const WCHAR *v18; // rax
  const WCHAR *StringRawBuffer; // rax
  __int64 v20; // rcx
  int v22; // [rsp+20h] [rbp-E0h]
  UINT32 v23; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwProcessId; // [rsp+34h] [rbp-CCh] BYREF
  HSTRING v25; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  UINT32 length; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, _QWORD, _QWORD); // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v32; // [rsp+80h] [rbp-80h] BYREF
  HSTRING_HEADER v33; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v34[512]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+3D8h]

  v4 = a2;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_UWPGameBar>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_UWPGameBar>::GetImpl'::`2'::impl,
    a2);
  v27 = 0;
  memset_0(v34, 0, sizeof(v34));
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)&v32,
    c_wzGameBarStartupTipsUri);
  if ( WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
         string,
         &v27);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD66,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\broadcastdvrprovider.cpp",
      (const char *)(unsigned int)v5,
      v22);
LABEL_31:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    return v6;
  }
  if ( !a3 )
  {
LABEL_28:
    v29 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v27;
    if ( v27 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v27)[1])(v27);
    string = 0;
    v23 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(v32, &v23);
    WindowsCreateStringReference(StringRawBuffer, v23, &hstringHeader, &string);
    BroadcastDVRComponent::LaunchGameOverlayWithUri(v20, &string, &v29);
    v6 = 0;
    goto LABEL_31;
  }
  v26 = 0;
  dwProcessId = 0;
  GetWindowThreadProcessId(v4, &dwProcessId);
  v25 = 0;
  v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v27;
  v8 = **v27;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
  v9 = v8(v7, &GUID_c1d432ba_c824_4452_a7fd_512bc3bbe9a1, &v26);
  v6 = v9;
  if ( v9 >= 0 )
  {
    v12 = v26;
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v26 + 56LL);
    WindowsDeleteString(v25);
    v25 = 0;
    v14 = v13(v12, *((_QWORD *)a3 + 6), &v25);
    v6 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD71,
        (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\broadcastdvrprovider.cpp",
        (const char *)(unsigned int)v14,
        v22);
      if ( v25 )
        WindowsDeleteString(v25);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
      goto LABEL_31;
    }
    length = 0;
    v15 = WindowsGetStringRawBuffer(v25, &length);
    if ( length )
    {
      v16 = L"AumId";
      if ( !*((_BYTE *)a3 + 19) )
        v16 = L"TitleId";
      v17 = swprintf_s<512>(
              v34,
              L"ms-gamingoverlay://startuptips?%ls=%ls&ProcessId=%lu&WindowId=%llu",
              v16,
              v15,
              dwProcessId,
              v4);
    }
    else
    {
      v17 = swprintf_s<512>(v34, L"ms-gamingoverlay://startuptips?pid=%lu&WindowId=%llu", dwProcessId, v4);
    }
    if ( v17 > 0 )
    {
      Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)&string, v34);
      v23 = 0;
      v18 = WindowsGetStringRawBuffer(string, &v23);
      v32 = 0;
      WindowsCreateStringReference(v18, v23, &v33, &v32);
    }
    if ( v25 )
      WindowsDeleteString(v25);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
    goto LABEL_28;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD70,
    (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\broadcastdvrprovider.cpp",
    (const char *)(unsigned int)v9,
    v22);
  if ( v25 )
    WindowsDeleteString(v25);
  v10 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v27;
  if ( v27 )
  {
    v27 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v11)[2])(v11);
  }
  return v6;
}

```

## disassembly

```asm
0x1801827b4  mov     [rsp-8+arg_0], rbx
0x1801827b9  push    rbp
0x1801827ba  push    rsi
0x1801827bb  push    rdi
0x1801827bc  push    r14
0x1801827be  push    r15
0x1801827c0  lea     rbp, [rsp-3B0h]
0x1801827c8  sub     rsp, 4B0h
0x1801827cf  mov     rax, cs:__security_cookie
0x1801827d6  xor     rax, rsp
0x1801827d9  mov     [rbp+3D0h+var_30], rax
0x1801827e0  mov     rsi, r8
0x1801827e3  mov     r14, rdx
0x1801827e6  mov     dl, 1
0x1801827e8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UWPGameBar@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UWPGameBar@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UWPGameBar> `wil::Feature<__WilFeatureTraits_Feature_UWPGameBar>::GetImpl(void)'::`2'::impl
0x1801827ef  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_UWPGameBar@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UWPGameBar>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1801827f4  xor     r15d, r15d
0x1801827f7  mov     [rsp+4D0h+var_488], r15
0x1801827fc  xor     edx, edx; Val
0x1801827fe  mov     r8d, 400h; Size
0x180182804  lea     rcx, [rbp+3D0h+var_430]; void *
0x180182808  call    memset_0
0x18018280d  mov     rdx, cs:?c_wzGameBarStartupTipsUri@@3PEBGEB; unsigned __int16 *
0x180182814  lea     rcx, [rbp+3D0h+var_450]; this
0x180182818  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18018281d  lea     r9, [rsp+4D0h+string]; string
0x180182822  lea     r8, [rsp+4D0h+hstringHeader]; hstringHeader
0x180182827  lea     edx, [r15+16h]; length
0x18018282b  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180182832  call    cs:__imp_WindowsCreateStringReference
0x180182838  test    eax, eax
0x18018283a  jns     short loc_180182851
0x18018283c  xor     r9d, r9d; lpArguments
0x18018283f  xor     r8d, r8d; nNumberOfArguments
0x180182842  lea     edx, [r15+1]; dwExceptionFlags
0x180182846  mov     ecx, 0C000000Dh; dwExceptionCode
0x18018284b  call    cs:__imp_RaiseException
0x180182851  lea     rdx, [rsp+4D0h+var_488]
0x180182856  mov     rcx, [rsp+4D0h+string]
0x18018285b  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x180182860  mov     ebx, eax
0x180182862  test    eax, eax
0x180182864  jns     short loc_180182886
0x180182866  mov     rcx, [rbp+3D8h]; this
0x18018286d  mov     r9d, eax; char *
0x180182870  lea     r8, aPcshellTwinuiB_2; "pcshell\\twinui\\broadcastdvrcomponent"...
0x180182877  mov     edx, 0D66h; void *
0x18018287c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180182881  jmp     loc_180182AE0
0x180182886  test    rsi, rsi
0x180182889  jz      loc_180182A82
0x18018288f  mov     [rsp+4D0h+var_490], r15
0x180182894  mov     [rsp+4D0h+dwProcessId], r15d
0x180182899  lea     rdx, [rsp+4D0h+dwProcessId]; lpdwProcessId
0x18018289e  mov     rcx, r14; hWnd
0x1801828a1  call    cs:__imp_GetWindowThreadProcessId
0x1801828a7  mov     [rsp+4D0h+var_498], r15
0x1801828ac  mov     rbx, [rsp+4D0h+var_488]
0x1801828b1  mov     rax, [rbx]
0x1801828b4  mov     rdi, [rax]
0x1801828b7  lea     rcx, [rsp+4D0h+var_490]
0x1801828bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801828c1  lea     r8, [rsp+4D0h+var_490]
0x1801828c6  lea     rdx, _GUID_c1d432ba_c824_4452_a7fd_512bc3bbe9a1
0x1801828cd  mov     rcx, rbx
0x1801828d0  mov     rax, rdi
0x1801828d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801828d8  mov     ebx, eax
0x1801828da  test    eax, eax
0x1801828dc  jns     short loc_180182948
0x1801828de  mov     rcx, [rbp+3D8h]; this
0x1801828e5  mov     r9d, eax; char *
0x1801828e8  lea     r8, aPcshellTwinuiB_2; "pcshell\\twinui\\broadcastdvrcomponent"...
0x1801828ef  mov     edx, 0D70h; void *
0x1801828f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801828f9  nop
0x1801828fa  mov     rcx, [rsp+4D0h+var_498]; string
0x1801828ff  test    rcx, rcx
0x180182902  jz      short loc_18018290B
0x180182904  call    cs:__imp_WindowsDeleteString
0x18018290a  nop
0x18018290b  mov     rcx, [rsp+4D0h+var_490]
0x180182910  test    rcx, rcx
0x180182913  jz      short loc_180182927
0x180182915  mov     [rsp+4D0h+var_490], r15
0x18018291a  mov     rax, [rcx]
0x18018291d  mov     rax, [rax+10h]
0x180182921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180182926  nop
0x180182927  mov     rcx, [rsp+4D0h+var_488]
0x18018292c  test    rcx, rcx
0x18018292f  jz      short loc_180182943
0x180182931  mov     [rsp+4D0h+var_488], r15
0x180182936  mov     rax, [rcx]
0x180182939  mov     rax, [rax+10h]
0x18018293d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180182942  nop
0x180182943  jmp     loc_180182AEA
0x180182948  mov     rdi, [rsp+4D0h+var_490]
0x18018294d  mov     rax, [rdi]
0x180182950  mov     rbx, [rax+38h]
0x180182954  mov     rcx, [rsp+4D0h+var_498]; string
0x180182959  call    cs:__imp_WindowsDeleteString
0x18018295f  mov     [rsp+4D0h+var_498], r15
0x180182964  lea     r8, [rsp+4D0h+var_498]
0x180182969  mov     rdx, [rsi+30h]
0x18018296d  mov     rcx, rdi
0x180182970  mov     rax, rbx
0x180182973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180182978  mov     ebx, eax
0x18018297a  test    eax, eax
0x18018297c  jns     short loc_1801829BA
0x18018297e  mov     rcx, [rbp+3D8h]; this
0x180182985  mov     r9d, eax; char *
0x180182988  lea     r8, aPcshellTwinuiB_2; "pcshell\\twinui\\broadcastdvrcomponent"...
0x18018298f  mov     edx, 0D71h; void *
0x180182994  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180182999  nop
0x18018299a  mov     rcx, [rsp+4D0h+var_498]; string
0x18018299f  test    rcx, rcx
0x1801829a2  jz      short loc_1801829AB
0x1801829a4  call    cs:__imp_WindowsDeleteString
0x1801829aa  nop
0x1801829ab  lea     rcx, [rsp+4D0h+var_490]
0x1801829b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801829b5  jmp     loc_180182AE0
0x1801829ba  mov     [rsp+4D0h+length], r15d
0x1801829bf  lea     rdx, [rsp+4D0h+length]; length
0x1801829c4  mov     rcx, [rsp+4D0h+var_498]; string
0x1801829c9  call    cs:__imp_WindowsGetStringRawBuffer
0x1801829cf  cmp     [rsp+4D0h+length], r15d
0x1801829d4  jbe     short loc_180182A0E
0x1801829d6  lea     rcx, aTitleid; "TitleId"
0x1801829dd  lea     r8, aAumid_1; "AumId"
0x1801829e4  cmp     [rsi+13h], r15b
0x1801829e8  cmovz   r8, rcx
0x1801829ec  mov     [rsp+4D0h+var_4A8], r14
0x1801829f1  mov     ecx, [rsp+4D0h+dwProcessId]
0x1801829f5  mov     [rsp+4D0h+var_4B0], ecx
0x1801829f9  mov     r9, rax
0x1801829fc  lea     rdx, aMsGamingoverla_1; "ms-gamingoverlay://startuptips?%ls=%ls&"...
0x180182a03  lea     rcx, [rbp+3D0h+var_430]
0x180182a07  call    ??$swprintf_s@$0CAA@@@YAHAEAY0CAA@GPEBGZZ; swprintf_s<512>(ushort (&)[512],ushort const *,...)
0x180182a0c  jmp     short loc_180182A26
0x180182a0e  mov     r9, r14
0x180182a11  mov     r8d, [rsp+4D0h+dwProcessId]
0x180182a16  lea     rdx, aMsGamingoverla_3; "ms-gamingoverlay://startuptips?pid=%lu&"...
0x180182a1d  lea     rcx, [rbp+3D0h+var_430]
0x180182a21  call    ??$swprintf_s@$0CAA@@@YAHAEAY0CAA@GPEBGZZ; swprintf_s<512>(ushort (&)[512],ushort const *,...)
0x180182a26  test    eax, eax
0x180182a28  jle     short loc_180182A67
0x180182a2a  lea     rdx, [rbp+3D0h+var_430]; unsigned __int16 *
0x180182a2e  lea     rcx, [rsp+4D0h+string]; this
0x180182a33  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180182a38  mov     [rsp+4D0h+var_4A0], r15d
0x180182a3d  lea     rdx, [rsp+4D0h+var_4A0]; length
0x180182a42  mov     rcx, [rsp+4D0h+string]; string
0x180182a47  call    cs:__imp_WindowsGetStringRawBuffer
0x180182a4d  mov     [rbp+3D0h+var_450], r15
0x180182a51  lea     r9, [rbp+3D0h+var_450]; string
0x180182a55  lea     r8, [rbp+3D0h+var_448]; hstringHeader
0x180182a59  mov     edx, [rsp+4D0h+var_4A0]; length
0x180182a5d  mov     rcx, rax; sourceString
0x180182a60  call    cs:__imp_WindowsCreateStringReference
0x180182a66  nop
0x180182a67  mov     rcx, [rsp+4D0h+var_498]; string
0x180182a6c  test    rcx, rcx
0x180182a6f  jz      short loc_180182A78
0x180182a71  call    cs:__imp_WindowsDeleteString
0x180182a77  nop
0x180182a78  lea     rcx, [rsp+4D0h+var_490]
0x180182a7d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180182a82  mov     rcx, [rsp+4D0h+var_488]
0x180182a87  mov     [rsp+4D0h+var_478], rcx
0x180182a8c  test    rcx, rcx
0x180182a8f  jz      short loc_180182A9E
0x180182a91  mov     rax, [rcx]
0x180182a94  mov     rax, [rax+8]
0x180182a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180182a9d  nop
0x180182a9e  mov     [rsp+4D0h+string], r15
0x180182aa3  mov     [rsp+4D0h+var_4A0], r15d
0x180182aa8  lea     rdx, [rsp+4D0h+var_4A0]; length
0x180182aad  mov     rcx, [rbp+3D0h+var_450]; string
0x180182ab1  call    cs:__imp_WindowsGetStringRawBuffer
0x180182ab7  lea     r9, [rsp+4D0h+string]; string
0x180182abc  lea     r8, [rsp+4D0h+hstringHeader]; hstringHeader
0x180182ac1  mov     edx, [rsp+4D0h+var_4A0]; length
0x180182ac5  mov     rcx, rax; sourceString
0x180182ac8  call    cs:__imp_WindowsCreateStringReference
0x180182ace  lea     r8, [rsp+4D0h+var_478]
0x180182ad3  lea     rdx, [rsp+4D0h+string]
0x180182ad8  call    ?LaunchGameOverlayWithUri@BroadcastDVRComponent@@AEAAJVStringReference@Internal@Windows@@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Z; BroadcastDVRComponent::LaunchGameOverlayWithUri(Windows::Internal::StringReference,Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>)
0x180182add  mov     ebx, r15d
0x180182ae0  lea     rcx, [rsp+4D0h+var_488]
0x180182ae5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180182aea  mov     eax, ebx
0x180182aec  mov     rcx, [rbp+3D0h+var_30]
0x180182af3  xor     rcx, rsp; StackCookie
0x180182af6  call    __security_check_cookie
0x180182afb  mov     rbx, [rsp+4D0h+arg_0]
0x180182b03  add     rsp, 4B0h
0x180182b0a  pop     r15
0x180182b0c  pop     r14
0x180182b0e  pop     rdi
0x180182b0f  pop     rsi
0x180182b10  pop     rbp
0x180182b11  retn
```
