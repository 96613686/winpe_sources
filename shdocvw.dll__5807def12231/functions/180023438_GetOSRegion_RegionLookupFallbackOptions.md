# GetOSRegion(RegionLookupFallbackOptions)

- ea: `0x180023438`
- end: `0x18002364f`
- name: `?GetOSRegion@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4RegionLookupFallbackOptions@@@Z`
- size: `535`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021b00`
- `0x180021e84`

## callees

- `0x180006750`
- `0x180006b34`
- `0x180006db4`
- `0x180008320`
- `0x18001a610`
- `0x180021590`
- `0x180023438`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180023539`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800235c6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180023539`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800235c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002351a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002359f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800235f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002351a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002359f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800235f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800234d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023559`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023609`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800234d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023559`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023609`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall GetOSRegion(__int64 a1)
{
  int v2; // eax
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rbx
  int v5; // eax
  const WCHAR *StringRawBuffer; // rax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  int v9; // eax
  const WCHAR *v10; // rax
  PCWSTR v11; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-68h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-68h]
  BOOL bIgnoreCaseb; // [rsp+20h] [rbp-68h]
  HSTRING string; // [rsp+30h] [rbp-58h] BYREF
  _QWORD v17[3]; // [rsp+38h] [rbp-50h] BYREF
  HSTRING_HEADER v18; // [rsp+50h] [rbp-38h] BYREF
  __int64 v19; // [rsp+68h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v17[1] = a1;
  v17[0] = 0;
  v19 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v18,
    L"Windows.Globalization.GeographicRegion",
    0x27u,
    0x26u);
  v2 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Globalization::IGeographicRegion>>(
         v19,
         v17);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x103,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v2,
      bIgnoreCase);
  string = 0;
  v3 = v17[0];
  v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17[0] + 56LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(v3, &string);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x106,
      (unsigned int)"shell\\shdocvw\\smartinst.cpp",
      (const char *)(unsigned int)v5,
      bIgnoreCase);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"ZZ", -1, 0) == 2 )
  {
    v7 = v17[0];
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17[0] + 72LL);
    WindowsDeleteString(string);
    string = 0;
    v9 = v8(v7, &string);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"shell\\shdocvw\\smartinst.cpp",
        (const char *)(unsigned int)v9,
        bIgnoreCasea);
    v10 = WindowsGetStringRawBuffer(string, 0);
    if ( CompareStringOrdinal(v10, -1, L"999", -1, 0) == 2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10F,
        (unsigned int)"shell\\shdocvw\\smartinst.cpp",
        (const char *)0x80004005LL,
        bIgnoreCaseb);
  }
  v11 = WindowsGetStringRawBuffer(string, 0);
  std::wstring::wstring(a1, v11);
  WindowsDeleteString(string);
  string = 0;
  _InternalRelease___ComPtr_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__WRL_Microsoft__IEAAKXZ(v17);
  return a1;
}

```

## disassembly

```asm
0x180023438  mov     r11, rsp
0x18002343b  mov     [r11+10h], rbx
0x18002343f  mov     [r11+18h], rsi
0x180023443  push    rdi
0x180023444  sub     rsp, 80h
0x18002344b  mov     rax, cs:__security_cookie
0x180023452  xor     rax, rsp
0x180023455  mov     [rsp+88h+var_18], rax
0x18002345a  mov     rsi, rcx
0x18002345d  mov     [rsp+88h+var_48], rcx
0x180023462  mov     qword ptr [r11-50h], 0
0x18002346a  mov     qword ptr [r11-20h], 0
0x180023472  mov     r9d, 26h ; '&'; unsigned int
0x180023478  lea     r8d, [r9+1]; unsigned int
0x18002347c  lea     rdx, ?RuntimeClass_Windows_Globalization_GeographicRegion@@3QBGB; "Windows.Globalization.GeographicRegion"
0x180023483  lea     rcx, [r11-38h]; hstringHeader
0x180023487  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002348c  nop
0x18002348d  lea     rdx, [rsp+88h+var_50]
0x180023492  mov     rcx, [rsp+88h+var_20]
0x180023497  call    ??$ActivateInstance@V?$ComPtr@UIGeographicRegion@Globalization@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIGeographicRegion@Globalization@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Globalization::IGeographicRegion>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Globalization::IGeographicRegion>>)
0x18002349c  mov     rcx, [rsp+88h]; this
0x1800234a4  test    eax, eax
0x1800234a6  jns     short loc_1800234BD
0x1800234a8  mov     r9d, eax; char *
0x1800234ab  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x1800234b2  mov     edx, 103h; void *
0x1800234b7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800234bd  mov     [rsp+88h+string], 0
0x1800234c6  mov     rdi, [rsp+88h+var_50]
0x1800234cb  mov     rax, [rdi]
0x1800234ce  mov     rbx, [rax+38h]
0x1800234d2  xor     ecx, ecx; string
0x1800234d4  call    cs:__imp_WindowsDeleteString
0x1800234da  mov     [rsp+88h+string], 0
0x1800234e3  lea     rdx, [rsp+88h+string]
0x1800234e8  mov     rcx, rdi
0x1800234eb  mov     rax, rbx
0x1800234ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234f3  mov     rcx, [rsp+88h]; this
0x1800234fb  test    eax, eax
0x1800234fd  jns     short loc_180023513
0x1800234ff  mov     r9d, eax; char *
0x180023502  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x180023509  mov     edx, 106h; void *
0x18002350e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180023513  xor     edx, edx; length
0x180023515  mov     rcx, [rsp+88h+string]; string
0x18002351a  call    cs:__imp_WindowsGetStringRawBuffer
0x180023520  mov     [rsp+88h+bIgnoreCase], 0; int
0x180023528  or      r9d, 0FFFFFFFFh; cchCount2
0x18002352c  lea     r8, aZz; "ZZ"
0x180023533  or      edx, r9d; cchCount1
0x180023536  mov     rcx, rax; lpString1
0x180023539  call    cs:__imp_CompareStringOrdinal
0x18002353f  cmp     eax, 2
0x180023542  jnz     loc_1800235EB
0x180023548  mov     rdi, [rsp+88h+var_50]
0x18002354d  mov     rax, [rdi]
0x180023550  mov     rbx, [rax+48h]
0x180023554  mov     rcx, [rsp+88h+string]; string
0x180023559  call    cs:__imp_WindowsDeleteString
0x18002355f  mov     [rsp+88h+string], 0
0x180023568  lea     rdx, [rsp+88h+string]
0x18002356d  mov     rcx, rdi
0x180023570  mov     rax, rbx
0x180023573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023578  mov     rcx, [rsp+88h]; this
0x180023580  test    eax, eax
0x180023582  jns     short loc_180023598
0x180023584  mov     r9d, eax; char *
0x180023587  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x18002358e  mov     edx, 10Ch; void *
0x180023593  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180023598  xor     edx, edx; length
0x18002359a  mov     rcx, [rsp+88h+string]; string
0x18002359f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800235a5  mov     rbx, [rsp+88h]
0x1800235ad  mov     [rsp+88h+bIgnoreCase], 0; int
0x1800235b5  or      r9d, 0FFFFFFFFh; cchCount2
0x1800235b9  lea     r8, a999; "999"
0x1800235c0  or      edx, r9d; cchCount1
0x1800235c3  mov     rcx, rax; lpString1
0x1800235c6  call    cs:__imp_CompareStringOrdinal
0x1800235cc  cmp     eax, 2
0x1800235cf  jnz     short loc_1800235EB
0x1800235d1  mov     r9d, 80004005h; char *
0x1800235d7  lea     r8, aShellShdocvwSm; "shell\\shdocvw\\smartinst.cpp"
0x1800235de  mov     edx, 10Fh; void *
0x1800235e3  mov     rcx, rbx; this
0x1800235e6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800235eb  xor     edx, edx; length
0x1800235ed  mov     rcx, [rsp+88h+string]; string
0x1800235f2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800235f8  mov     rdx, rax
0x1800235fb  mov     rcx, rsi
0x1800235fe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180023603  nop
0x180023604  mov     rcx, [rsp+88h+string]; string
0x180023609  call    cs:__imp_WindowsDeleteString
0x18002360f  mov     [rsp+88h+string], 0
0x180023618  lea     rcx, [rsp+88h+var_50]
0x18002361d  call    ?InternalRelease@?$ComPtr@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>::InternalRelease(void)
0x180023622  mov     rax, rsi
0x180023625  jmp     short loc_18002362C
0x180023627  mov     rax, [rsp+88h+var_48]
0x18002362c  mov     rcx, [rsp+88h+var_18]
0x180023631  xor     rcx, rsp; StackCookie
0x180023634  call    __security_check_cookie
0x180023639  lea     r11, [rsp+88h+var_8]
0x180023641  mov     rbx, [r11+18h]
0x180023645  mov     rsi, [r11+20h]
0x180023649  mov     rsp, r11
0x18002364c  pop     rdi
0x18002364d  retn
```
