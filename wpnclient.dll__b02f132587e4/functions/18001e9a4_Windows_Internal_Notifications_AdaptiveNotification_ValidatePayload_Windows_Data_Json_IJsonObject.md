# Windows::Internal::Notifications::AdaptiveNotification::ValidatePayload(Windows::Data::Json::IJsonObject *)

- ea: `0x18001e9a4`
- end: `0x18001eb94`
- name: `?ValidatePayload@AdaptiveNotification@Notifications@Internal@Windows@@AEAAXPEAUIJsonObject@Json@Data@4@@Z`
- size: `496`
- prototype: `void __fastcall(Windows::Internal::Notifications::AdaptiveNotification *__hidden this, struct Windows::Data::Json::IJsonObject *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dccc`

## callees

- `0x180005670`
- `0x180013f00`
- `0x180014740`
- `0x18001b848`
- `0x18001e9a4`
- `0x18001ff00`
- `0x1800307b4`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ea6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ea6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ea2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eb0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eb4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eb68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ea2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eb0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eb4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eb68`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Internal::Notifications::AdaptiveNotification::ValidatePayload(
        Windows::Internal::Notifications::AdaptiveNotification *this,
        struct Windows::Data::Json::IJsonObject *a2)
{
  __int64 (__fastcall *v3)(struct Windows::Data::Json::IJsonObject *, _QWORD, __int64 *); // rbx
  _QWORD *v4; // rax
  int v5; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  int v8; // eax
  const wchar_t *StringRawBuffer; // rax
  __int64 (__fastcall *v10)(struct Windows::Data::Json::IJsonObject *, _QWORD, __int64 *); // rbx
  _QWORD *v11; // rax
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  HSTRING string; // [rsp+20h] [rbp-58h] BYREF
  HSTRING v17; // [rsp+28h] [rbp-50h] BYREF
  __int64 v18; // [rsp+30h] [rbp-48h] BYREF
  __int64 v19; // [rsp+38h] [rbp-40h] BYREF
  HSTRING v20[4]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  v19 = 0;
  v3 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, _QWORD, __int64 *))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  v4 = (_QWORD *)Windows::Internal::StringReference::StringReference(v20, L"type");
  v5 = v3(a2, *v4, &v19);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
      (const char *)(unsigned int)v5,
      (int)string);
  string = 0;
  v6 = v19;
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 64LL);
  WindowsDeleteString(0);
  string = 0;
  v8 = v7(v6, &string);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
      (const char *)(unsigned int)v8,
      (int)string);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( wcscmp_0(L"AdaptiveCard", StringRawBuffer) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
      (const char *)0x80070057LL,
      (int)string);
  v18 = 0;
  v10 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, _QWORD, __int64 *))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  v11 = (_QWORD *)Windows::Internal::StringReference::StringReference(v20, L"version");
  v12 = v10(a2, *v11, &v18);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
      (const char *)(unsigned int)v12,
      (int)string);
  v17 = 0;
  v13 = v18;
  v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v18 + 64LL);
  WindowsDeleteString(0);
  v17 = 0;
  v15 = v14(v13, &v17);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
      (const char *)(unsigned int)v15,
      (int)string);
  WindowsDeleteString(v17);
  v17 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
}

```

## disassembly

```asm
0x18001e9a4  push    rbp
0x18001e9a6  push    rbx
0x18001e9a7  push    rsi
0x18001e9a8  push    rdi
0x18001e9a9  mov     rbp, rsp
0x18001e9ac  sub     rsp, 78h
0x18001e9b0  mov     rax, cs:__security_cookie
0x18001e9b7  xor     rax, rsp
0x18001e9ba  mov     [rbp+var_18], rax
0x18001e9be  mov     rsi, rdx
0x18001e9c1  mov     [rbp+var_40], 0
0x18001e9c9  mov     rax, [rdx]
0x18001e9cc  mov     rbx, [rax+30h]
0x18001e9d0  lea     rcx, [rbp+var_40]
0x18001e9d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e9d9  lea     rdx, aType; "type"
0x18001e9e0  lea     rcx, [rbp+var_38]; string
0x18001e9e4  call    ??$?0$04@StringReference@Internal@Windows@@QEAA@AEAY04$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[5])
0x18001e9e9  lea     r8, [rbp+var_40]
0x18001e9ed  mov     rdx, [rax]
0x18001e9f0  mov     rcx, rsi
0x18001e9f3  mov     rax, rbx
0x18001e9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9fb  mov     rcx, [rbp+20h]; this
0x18001e9ff  test    eax, eax
0x18001ea01  jns     short loc_18001EA18
0x18001ea03  mov     r9d, eax; char *
0x18001ea06  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ea0d  mov     edx, 3Eh ; '>'; void *
0x18001ea12  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ea18  mov     [rbp+string], 0
0x18001ea20  mov     rdi, [rbp+var_40]
0x18001ea24  mov     rax, [rdi]
0x18001ea27  mov     rbx, [rax+40h]
0x18001ea2b  xor     ecx, ecx; string
0x18001ea2d  call    cs:__imp_WindowsDeleteString
0x18001ea33  mov     [rbp+string], 0
0x18001ea3b  lea     rdx, [rbp+string]
0x18001ea3f  mov     rcx, rdi
0x18001ea42  mov     rax, rbx
0x18001ea45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea4a  mov     rcx, [rbp+20h]; this
0x18001ea4e  test    eax, eax
0x18001ea50  jns     short loc_18001EA67
0x18001ea52  mov     r9d, eax; char *
0x18001ea55  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ea5c  mov     edx, 40h ; '@'; void *
0x18001ea61  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ea67  xor     edx, edx; length
0x18001ea69  mov     rcx, [rbp+string]; string
0x18001ea6d  call    cs:__imp_WindowsGetStringRawBuffer
0x18001ea73  mov     rdx, rax; String2
0x18001ea76  lea     rcx, aAdaptivecard; "AdaptiveCard"
0x18001ea7d  call    wcscmp_0
0x18001ea82  mov     rcx, [rbp+20h]; this
0x18001ea86  test    eax, eax
0x18001ea88  jz      short loc_18001EAA2
0x18001ea8a  mov     r9d, 80070057h; char *
0x18001ea90  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ea97  mov     edx, 41h ; 'A'; void *
0x18001ea9c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001eaa2  mov     [rbp+var_48], 0
0x18001eaaa  mov     rax, [rsi]
0x18001eaad  mov     rbx, [rax+30h]
0x18001eab1  lea     rcx, [rbp+var_48]
0x18001eab5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001eaba  lea     rdx, aVersion; "version"
0x18001eac1  lea     rcx, [rbp+var_38]; string
0x18001eac5  call    ??$?0$07@StringReference@Internal@Windows@@QEAA@AEAY07$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[8])
0x18001eaca  lea     r8, [rbp+var_48]
0x18001eace  mov     rdx, [rax]
0x18001ead1  mov     rcx, rsi
0x18001ead4  mov     rax, rbx
0x18001ead7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eadc  mov     rcx, [rbp+20h]; this
0x18001eae0  test    eax, eax
0x18001eae2  jns     short loc_18001EAF9
0x18001eae4  mov     r9d, eax; char *
0x18001eae7  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001eaee  mov     edx, 43h ; 'C'; void *
0x18001eaf3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001eaf9  mov     [rbp+var_50], 0
0x18001eb01  mov     rdi, [rbp+var_48]
0x18001eb05  mov     rax, [rdi]
0x18001eb08  mov     rbx, [rax+40h]
0x18001eb0c  xor     ecx, ecx; string
0x18001eb0e  call    cs:__imp_WindowsDeleteString
0x18001eb14  mov     [rbp+var_50], 0
0x18001eb1c  lea     rdx, [rbp+var_50]
0x18001eb20  mov     rcx, rdi
0x18001eb23  mov     rax, rbx
0x18001eb26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb2b  mov     rcx, [rbp+20h]; this
0x18001eb2f  test    eax, eax
0x18001eb31  jns     short loc_18001EB48
0x18001eb33  mov     r9d, eax; char *
0x18001eb36  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001eb3d  mov     edx, 45h ; 'E'; void *
0x18001eb42  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001eb48  mov     rcx, [rbp+var_50]; string
0x18001eb4c  call    cs:__imp_WindowsDeleteString
0x18001eb52  mov     [rbp+var_50], 0
0x18001eb5a  lea     rcx, [rbp+var_48]
0x18001eb5e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001eb63  nop
0x18001eb64  mov     rcx, [rbp+string]; string
0x18001eb68  call    cs:__imp_WindowsDeleteString
0x18001eb6e  mov     [rbp+string], 0
0x18001eb76  lea     rcx, [rbp+var_40]
0x18001eb7a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001eb7f  mov     rcx, [rbp+var_18]
0x18001eb83  xor     rcx, rsp; StackCookie
0x18001eb86  call    __security_check_cookie
0x18001eb8b  add     rsp, 78h
0x18001eb8f  pop     rdi
0x18001eb90  pop     rsi
0x18001eb91  pop     rbx
0x18001eb92  pop     rbp
0x18001eb93  retn
```
