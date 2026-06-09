# ReadOneSettingsData

- ea: `0x18000c4e0`
- end: `0x18000c77b`
- name: `ReadOneSettingsData`
- size: `667`
- prototype: `__int64 __fastcall(char, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180004504`
- `0x1800051f0`
- `0x18000885c`
- `0x18000c4e0`
- `0x18001b150`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c6bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c6f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c74e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c6bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c6f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c74e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c70a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c70a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000c547`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000c5ec`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000c547`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000c5ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c72b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c72b`

## string_xrefs

- `0x18000c5ff`: `onecore\base\win32\winnls\tzautoupdate\api.cpp`
- `0x18000c6e3`: `onecore\base\win32\winnls\tzautoupdate\api.cpp`

## pseudocode

```c
__int64 __fastcall ReadOneSettingsData(char a1, _QWORD *a2)
{
  int ActivationFactory; // ebx
  HSTRING v4; // rbx
  __int64 (__fastcall *v5)(HSTRING, __int64, __int64 *); // rdi
  __int64 v6; // rcx
  int v7; // eax
  int v8; // ebx
  HSTRING v9; // rdi
  __int64 (__fastcall *v10)(HSTRING, __int64, __int64, __int64 *); // rsi
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  PCWSTR StringRawBuffer; // rax
  _WORD *v17; // rdi
  __int64 v18; // rdx
  _WORD *v19; // rax
  _WORD *v20; // rdx
  __int16 v21; // cx
  int v23; // [rsp+20h] [rbp-49h]
  HSTRING string; // [rsp+30h] [rbp-39h] BYREF
  __int64 v25; // [rsp+38h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-29h] BYREF
  __int64 v27; // [rsp+58h] [rbp-11h]
  HSTRING_HEADER v28; // [rsp+60h] [rbp-9h] BYREF
  __int64 v29; // [rsp+78h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v25 = 0;
  if ( !a1 )
  {
    string = 0;
    v27 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.Flighting.OneSettings.OneSettingsPayload",
      0x3Au,
      0x39u);
    ActivationFactory = RoGetActivationFactory(v27, &GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0, &string);
    if ( ActivationFactory >= 0 )
    {
      v4 = string;
      v5 = *(__int64 (__fastcall **)(HSTRING, __int64, __int64 *))(*(_QWORD *)string + 48LL);
      v6 = v25;
      v25 = 0;
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      v27 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"DSTSYNC", 8u, 7u);
      ActivationFactory = v5(v4, v27, &v25);
    }
    wil::com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>(&string);
    if ( ActivationFactory >= 0 )
      goto LABEL_12;
  }
  string = 0;
  v27 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Flighting.OneSettings.OneSettingsManager",
    0x3Au,
    0x39u);
  v7 = RoGetActivationFactory(v27, &GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017, &string);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x169,
      (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\api.cpp",
      (const char *)(unsigned int)v7,
      v23);
    wil::com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>(&string);
    goto LABEL_19;
  }
  v9 = string;
  v10 = *(__int64 (__fastcall **)(HSTRING, __int64, __int64, __int64 *))(*(_QWORD *)string + 56LL);
  v11 = v25;
  v25 = 0;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  v27 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"0.2", 4u, 3u);
  v12 = v27;
  v29 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v28, L"DSTSYNC", 8u, 7u);
  v8 = v10(v9, v29, v12, &v25);
  wil::com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>(&string);
  if ( v8 >= 0 )
  {
LABEL_12:
    string = 0;
    v13 = v25;
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 104LL);
    WindowsDeleteString(0);
    string = 0;
    v15 = v14(v13, &string);
    v8 = v15;
    if ( v15 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v17 = StringRawBuffer;
      v18 = -1;
      do
        ++v18;
      while ( StringRawBuffer[v18] );
      v19 = LocalAlloc(0, 2 * v18 + 2);
      v20 = v19;
      do
      {
        v21 = *v17;
        *v20++ = *v17++;
      }
      while ( v21 );
      *a2 = v19;
      WindowsDeleteString(string);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x175,
        (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\api.cpp",
        (const char *)(unsigned int)v15,
        v23);
      WindowsDeleteString(string);
      string = 0;
    }
  }
LABEL_19:
  wil::com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>(&v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000c4e0  push    rbp
0x18000c4e2  push    rbx
0x18000c4e3  push    rsi
0x18000c4e4  push    rdi
0x18000c4e5  push    r14
0x18000c4e7  push    r15
0x18000c4e9  lea     rbp, [rsp-2Fh]
0x18000c4ee  sub     rsp, 98h
0x18000c4f5  mov     rax, cs:__security_cookie
0x18000c4fc  xor     rax, rsp
0x18000c4ff  mov     [rbp+57h+var_40], rax
0x18000c503  mov     r14, rdx
0x18000c506  xor     r15d, r15d
0x18000c509  mov     [rbp+57h+var_88], r15
0x18000c50d  lea     esi, [r15+39h]
0x18000c511  test    cl, cl
0x18000c513  jnz     loc_18000C5BC
0x18000c519  mov     [rbp+57h+string], r15
0x18000c51d  mov     [rbp+57h+var_68], r15
0x18000c521  mov     r9d, esi; unsigned int
0x18000c524  lea     r8d, [r15+3Ah]; unsigned int
0x18000c528  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsPayload@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x18000c52f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18000c533  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000c538  lea     r8, [rbp+57h+string]
0x18000c53c  lea     rdx, _GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0
0x18000c543  mov     rcx, [rbp+57h+var_68]
0x18000c547  call    cs:__imp_RoGetActivationFactory
0x18000c54d  mov     ebx, eax
0x18000c54f  test    eax, eax
0x18000c551  js      short loc_18000C5AB
0x18000c553  mov     rbx, [rbp+57h+string]
0x18000c557  mov     rax, [rbx]
0x18000c55a  mov     rdi, [rax+30h]
0x18000c55e  mov     rcx, [rbp+57h+var_88]
0x18000c562  mov     [rbp+57h+var_88], r15
0x18000c566  test    rcx, rcx
0x18000c569  jz      short loc_18000C578
0x18000c56b  mov     rax, [rcx]
0x18000c56e  mov     rax, [rax+10h]
0x18000c572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c577  nop
0x18000c578  mov     [rbp+57h+var_68], r15
0x18000c57c  mov     r9d, 7; unsigned int
0x18000c582  lea     r8d, [r9+1]; unsigned int
0x18000c586  lea     rdx, sourceString; "DSTSYNC"
0x18000c58d  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18000c591  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000c596  lea     r8, [rbp+57h+var_88]
0x18000c59a  mov     rdx, [rbp+57h+var_68]
0x18000c59e  mov     rcx, rbx
0x18000c5a1  mov     rax, rdi
0x18000c5a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5a9  mov     ebx, eax
0x18000c5ab  lea     rcx, [rbp+57h+string]
0x18000c5af  call    ??1?$com_ptr_t@UIOneSettingsManager@OneSettings@Flighting@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>(void)
0x18000c5b4  test    ebx, ebx
0x18000c5b6  jns     loc_18000C6AC
0x18000c5bc  mov     [rbp+57h+string], r15
0x18000c5c0  mov     [rbp+57h+var_68], r15
0x18000c5c4  mov     r9d, esi; unsigned int
0x18000c5c7  mov     r8d, 3Ah ; ':'; unsigned int
0x18000c5cd  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsManager@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x18000c5d4  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18000c5d8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000c5dd  lea     r8, [rbp+57h+string]
0x18000c5e1  lea     rdx, _GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017
0x18000c5e8  mov     rcx, [rbp+57h+var_68]
0x18000c5ec  call    cs:__imp_RoGetActivationFactory
0x18000c5f2  mov     ebx, eax
0x18000c5f4  test    eax, eax
0x18000c5f6  jns     short loc_18000C61E
0x18000c5f8  mov     rcx, [rbp+5Fh]; this
0x18000c5fc  mov     r9d, eax; char *
0x18000c5ff  lea     r8, aOnecoreBaseWin_3; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000c606  mov     edx, 169h; void *
0x18000c60b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c610  lea     rcx, [rbp+57h+string]
0x18000c614  call    ??1?$com_ptr_t@UIOneSettingsManager@OneSettings@Flighting@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>(void)
0x18000c619  jmp     loc_18000C754
0x18000c61e  mov     rdi, [rbp+57h+string]
0x18000c622  mov     rax, [rdi]
0x18000c625  mov     rsi, [rax+38h]
0x18000c629  mov     rcx, [rbp+57h+var_88]
0x18000c62d  mov     [rbp+57h+var_88], r15
0x18000c631  test    rcx, rcx
0x18000c634  jz      short loc_18000C643
0x18000c636  mov     rax, [rcx]
0x18000c639  mov     rax, [rax+10h]
0x18000c63d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c642  nop
0x18000c643  mov     [rbp+57h+var_68], r15
0x18000c647  mov     r9d, 3; unsigned int
0x18000c64d  lea     r8d, [r9+1]; unsigned int
0x18000c651  lea     rdx, a02; "0.2"
0x18000c658  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18000c65c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000c661  mov     rbx, [rbp+57h+var_68]
0x18000c665  mov     [rbp+57h+var_48], r15
0x18000c669  mov     r9d, 7; unsigned int
0x18000c66f  lea     r8d, [r9+1]; unsigned int
0x18000c673  lea     rdx, sourceString; "DSTSYNC"
0x18000c67a  lea     rcx, [rbp+57h+var_60]; hstringHeader
0x18000c67e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000c683  lea     r9, [rbp+57h+var_88]
0x18000c687  mov     r8, rbx
0x18000c68a  mov     rdx, [rbp+57h+var_48]
0x18000c68e  mov     rcx, rdi
0x18000c691  mov     rax, rsi
0x18000c694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c699  mov     ebx, eax
0x18000c69b  lea     rcx, [rbp+57h+string]
0x18000c69f  call    ??1?$com_ptr_t@UIOneSettingsManager@OneSettings@Flighting@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>(void)
0x18000c6a4  test    ebx, ebx
0x18000c6a6  js      loc_18000C754
0x18000c6ac  mov     [rbp+57h+string], r15
0x18000c6b0  mov     rdi, [rbp+57h+var_88]
0x18000c6b4  mov     rax, [rdi]
0x18000c6b7  mov     rbx, [rax+68h]
0x18000c6bb  xor     ecx, ecx; string
0x18000c6bd  call    cs:__imp_WindowsDeleteString
0x18000c6c3  mov     [rbp+57h+string], r15
0x18000c6c7  lea     rdx, [rbp+57h+string]
0x18000c6cb  mov     rcx, rdi
0x18000c6ce  mov     rax, rbx
0x18000c6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6d6  mov     ebx, eax
0x18000c6d8  test    eax, eax
0x18000c6da  jns     short loc_18000C704
0x18000c6dc  mov     rcx, [rbp+5Fh]; this
0x18000c6e0  mov     r9d, eax; char *
0x18000c6e3  lea     r8, aOnecoreBaseWin_3; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x18000c6ea  mov     edx, 175h; void *
0x18000c6ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c6f4  mov     rcx, [rbp+57h+string]; string
0x18000c6f8  call    cs:__imp_WindowsDeleteString
0x18000c6fe  mov     [rbp+57h+string], r15
0x18000c702  jmp     short loc_18000C754
0x18000c704  xor     edx, edx; length
0x18000c706  mov     rcx, [rbp+57h+string]; string
0x18000c70a  call    cs:__imp_WindowsGetStringRawBuffer
0x18000c710  mov     rdi, rax
0x18000c713  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000c717  inc     rdx
0x18000c71a  cmp     [rax+rdx*2], r15w
0x18000c71f  jnz     short loc_18000C717
0x18000c721  lea     rdx, ds:2[rdx*2]; uBytes
0x18000c729  xor     ecx, ecx; uFlags
0x18000c72b  call    cs:__imp_LocalAlloc
0x18000c731  mov     rdx, rax
0x18000c734  movzx   ecx, word ptr [rdi]
0x18000c737  mov     [rdx], cx
0x18000c73a  lea     rdi, [rdi+2]
0x18000c73e  lea     rdx, [rdx+2]
0x18000c742  test    cx, cx
0x18000c745  jnz     short loc_18000C734
0x18000c747  mov     [r14], rax
0x18000c74a  mov     rcx, [rbp+57h+string]; string
0x18000c74e  call    cs:__imp_WindowsDeleteString
0x18000c754  lea     rcx, [rbp+57h+var_88]
0x18000c758  call    ??1?$com_ptr_t@UIOneSettingsManager@OneSettings@Flighting@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsManager,wil::err_returncode_policy>(void)
0x18000c75d  mov     eax, ebx
0x18000c75f  mov     rcx, [rbp+57h+var_40]
0x18000c763  xor     rcx, rsp; StackCookie
0x18000c766  call    __security_check_cookie
0x18000c76b  add     rsp, 98h
0x18000c772  pop     r15
0x18000c774  pop     r14
0x18000c776  pop     rdi
0x18000c777  pop     rsi
0x18000c778  pop     rbx
0x18000c779  pop     rbp
0x18000c77a  retn
```
