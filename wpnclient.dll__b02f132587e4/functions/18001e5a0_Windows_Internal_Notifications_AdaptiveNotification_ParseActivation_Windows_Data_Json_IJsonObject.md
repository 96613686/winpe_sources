# Windows::Internal::Notifications::AdaptiveNotification::ParseActivation(Windows::Data::Json::IJsonObject *)

- ea: `0x18001e5a0`
- end: `0x18001e950`
- name: `?ParseActivation@AdaptiveNotification@Notifications@Internal@Windows@@AEAAXPEAUIJsonObject@Json@Data@4@@Z`
- size: `944`
- prototype: `void __fastcall(Windows::Internal::Notifications::AdaptiveNotification *__hidden this, struct Windows::Data::Json::IJsonObject *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dccc`

## callees

- `0x180005670`
- `0x180014740`
- `0x1800153b4`
- `0x18001a3c0`
- `0x18001b848`
- `0x18001e5a0`
- `0x18001e958`
- `0x18001ff00`
- `0x1800307b4`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e6f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e83e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e6f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e83e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e6b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e78e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e7c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e8c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e906`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e6b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e78e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e7c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e8c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e906`

## string_xrefs

- `0x18001e847`: `Action.OpenUrl`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Windows::Internal::Notifications::AdaptiveNotification::ParseActivation(
        HSTRING *this,
        struct Windows::Data::Json::IJsonObject *a2)
{
  int (__fastcall *v4)(struct Windows::Data::Json::IJsonObject *, _QWORD, __int64 *); // rbx
  _QWORD *v5; // rax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *); // rbx
  _QWORD *v11; // rax
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  const wchar_t *StringRawBuffer; // rax
  __int64 v17; // rdi
  int (__fastcall *v18)(__int64, _QWORD, __int64 **); // rbx
  _QWORD *v19; // rax
  HSTRING *v20; // rsi
  __int64 *v21; // rdi
  __int64 (__fastcall *v22)(__int64 *, __int64 *); // rbx
  int v23; // eax
  __int64 *v24; // rdi
  HSTRING v25; // rcx
  bool v26; // sf
  __int64 v27; // rax
  __int64 (__fastcall *v28)(__int64 *, HSTRING *); // rbx
  int v29; // eax
  __int64 (__fastcall *v30)(__int64 *, HSTRING *); // rbx
  int v31; // eax
  int v32; // eax
  const wchar_t *v33; // rax
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, _QWORD, __int64 **); // rbx
  _QWORD *v36; // rax
  int v37; // eax
  __int64 *v38; // rsi
  __int64 (__fastcall *v39)(__int64 *, HSTRING *); // rdi
  int v40; // eax
  __int64 *v41; // [rsp+20h] [rbp-60h] BYREF
  HSTRING string; // [rsp+28h] [rbp-58h] BYREF
  __int64 v43; // [rsp+30h] [rbp-50h] BYREF
  __int64 v44; // [rsp+38h] [rbp-48h] BYREF
  __int64 v45; // [rsp+40h] [rbp-40h] BYREF
  __int64 v46; // [rsp+48h] [rbp-38h] BYREF
  HSTRING v47[4]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v45 = 0;
  v4 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, _QWORD, __int64 *))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
  v5 = (_QWORD *)Windows::Internal::StringReference::StringReference(v47, L"selectAction");
  if ( v4(a2, *v5, &v45) >= 0 )
  {
    v43 = 0;
    v6 = v45;
    v7 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 96LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
    v8 = v7(v6, &v43);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
        (const char *)(unsigned int)v8,
        (int)v41);
    v44 = 0;
    v9 = v43;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v43 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
    v11 = (_QWORD *)Windows::Internal::StringReference::StringReference(v47, L"type");
    v12 = v10(v9, *v11, &v44);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
        (const char *)(unsigned int)v12,
        (int)v41);
    string = 0;
    v13 = v44;
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v44 + 64LL);
    WindowsDeleteString(0);
    string = 0;
    v15 = v14(v13, &string);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
        (const char *)(unsigned int)v15,
        (int)v41);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( !wcscmp_0(L"Action.Submit", StringRawBuffer) )
    {
      v41 = 0;
      v17 = v43;
      v18 = *(int (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v43 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
      v19 = (_QWORD *)Windows::Internal::StringReference::StringReference(v47, L"data");
      v20 = this + 11;
      if ( v18(v17, *v19, &v41) < 0 )
      {
        v32 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)(this + 11), &pwzBaseUrl, 0);
        if ( v32 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6A,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
            (const char *)(unsigned int)v32,
            (int)v41);
      }
      else
      {
        v46 = 0;
        v21 = v41;
        v22 = *(__int64 (__fastcall **)(__int64 *, __int64 *))(*v41 + 96);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
        v23 = v22(v21, &v46);
        v24 = v41;
        v25 = *v20;
        v26 = v23 < 0;
        v27 = *v41;
        if ( v26 )
        {
          v30 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(v27 + 64);
          WindowsDeleteString(v25);
          *v20 = 0;
          v31 = v30(v24, this + 11);
          if ( v31 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x65,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
              (const char *)(unsigned int)v31,
              (int)v41);
        }
        else
        {
          v28 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(v27 + 56);
          WindowsDeleteString(v25);
          *v20 = 0;
          v29 = v28(v24, this + 11);
          if ( v29 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x61,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
              (const char *)(unsigned int)v29,
              (int)v41);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
      }
    }
    else
    {
      v33 = WindowsGetStringRawBuffer(string, 0);
      if ( wcscmp_0(L"Action.OpenUrl", v33) )
      {
LABEL_25:
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        goto LABEL_26;
      }
      v41 = 0;
      v34 = v43;
      v35 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v43 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
      v36 = (_QWORD *)Windows::Internal::StringReference::StringReference(v47, L"url");
      v37 = v35(v34, *v36, &v41);
      if ( v37 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x70,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
          (const char *)(unsigned int)v37,
          (int)v41);
      v38 = v41;
      v39 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v41 + 64);
      WindowsDeleteString(this[12]);
      this[12] = 0;
      v40 = v39(v38, this + 12);
      if ( v40 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x71,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\adaptivenotification.cpp",
          (const char *)(unsigned int)v40,
          (int)v41);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    goto LABEL_25;
  }
LABEL_26:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
}

```

## disassembly

```asm
0x18001e5a0  mov     [rsp-28h+arg_10], rbx
0x18001e5a5  push    rbp
0x18001e5a6  push    rsi
0x18001e5a7  push    rdi
0x18001e5a8  push    r14
0x18001e5aa  push    r15
0x18001e5ac  mov     rbp, rsp
0x18001e5af  sub     rsp, 80h
0x18001e5b6  mov     rax, cs:__security_cookie
0x18001e5bd  xor     rax, rsp
0x18001e5c0  mov     [rbp+var_10], rax
0x18001e5c4  mov     rdi, rdx
0x18001e5c7  mov     r14, rcx
0x18001e5ca  xor     r15d, r15d
0x18001e5cd  mov     [rbp+var_40], r15
0x18001e5d1  mov     rax, [rdx]
0x18001e5d4  mov     rbx, [rax+30h]
0x18001e5d8  lea     rcx, [rbp+var_40]
0x18001e5dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e5e1  lea     rdx, aSelectaction; "selectAction"
0x18001e5e8  lea     rcx, [rbp+var_30]; string
0x18001e5ec  call    ??$?0$0N@@StringReference@Internal@Windows@@QEAA@AEAY0N@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[13])
0x18001e5f1  lea     r8, [rbp+var_40]
0x18001e5f5  mov     rdx, [rax]
0x18001e5f8  mov     rcx, rdi
0x18001e5fb  mov     rax, rbx
0x18001e5fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e603  test    eax, eax
0x18001e605  js      loc_18001E924
0x18001e60b  mov     [rbp+var_50], r15
0x18001e60f  mov     rdi, [rbp+var_40]
0x18001e613  mov     rax, [rdi]
0x18001e616  mov     rbx, [rax+60h]
0x18001e61a  lea     rcx, [rbp+var_50]
0x18001e61e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e623  lea     rdx, [rbp+var_50]
0x18001e627  mov     rcx, rdi
0x18001e62a  mov     rax, rbx
0x18001e62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e632  mov     rcx, [rbp+28h]; this
0x18001e636  test    eax, eax
0x18001e638  jns     short loc_18001E64E
0x18001e63a  mov     r9d, eax; char *
0x18001e63d  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e644  lea     edx, [r15+4Eh]; void *
0x18001e648  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e64e  mov     [rbp+var_48], r15
0x18001e652  mov     rdi, [rbp+var_50]
0x18001e656  mov     rax, [rdi]
0x18001e659  mov     rbx, [rax+30h]
0x18001e65d  lea     rcx, [rbp+var_48]
0x18001e661  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e666  lea     rdx, aType; "type"
0x18001e66d  lea     rcx, [rbp+var_30]; string
0x18001e671  call    ??$?0$04@StringReference@Internal@Windows@@QEAA@AEAY04$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[5])
0x18001e676  lea     r8, [rbp+var_48]
0x18001e67a  mov     rdx, [rax]
0x18001e67d  mov     rcx, rdi
0x18001e680  mov     rax, rbx
0x18001e683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e688  mov     rcx, [rbp+28h]; this
0x18001e68c  test    eax, eax
0x18001e68e  jns     short loc_18001E6A5
0x18001e690  mov     r9d, eax; char *
0x18001e693  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e69a  mov     edx, 51h ; 'Q'; void *
0x18001e69f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e6a5  mov     [rbp+string], r15
0x18001e6a9  mov     rdi, [rbp+var_48]
0x18001e6ad  mov     rax, [rdi]
0x18001e6b0  mov     rbx, [rax+40h]
0x18001e6b4  xor     ecx, ecx; string
0x18001e6b6  call    cs:__imp_WindowsDeleteString
0x18001e6bc  mov     [rbp+string], r15
0x18001e6c0  lea     rdx, [rbp+string]
0x18001e6c4  mov     rcx, rdi
0x18001e6c7  mov     rax, rbx
0x18001e6ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6cf  mov     rcx, [rbp+28h]; this
0x18001e6d3  test    eax, eax
0x18001e6d5  jns     short loc_18001E6EC
0x18001e6d7  mov     r9d, eax; char *
0x18001e6da  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e6e1  mov     edx, 54h ; 'T'; void *
0x18001e6e6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e6ec  xor     edx, edx; length
0x18001e6ee  mov     rcx, [rbp+string]; string
0x18001e6f2  call    cs:__imp_WindowsGetStringRawBuffer
0x18001e6f8  mov     rdx, rax; String2
0x18001e6fb  lea     rcx, aActionSubmit; "Action.Submit"
0x18001e702  call    wcscmp_0
0x18001e707  test    eax, eax
0x18001e709  jnz     loc_18001E838
0x18001e70f  mov     [rbp+var_60], r15
0x18001e713  mov     rdi, [rbp+var_50]
0x18001e717  mov     rax, [rdi]
0x18001e71a  mov     rbx, [rax+30h]
0x18001e71e  lea     rcx, [rbp+var_60]
0x18001e722  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e727  lea     rdx, aData; "data"
0x18001e72e  lea     rcx, [rbp+var_30]; string
0x18001e732  call    ??$?0$04@StringReference@Internal@Windows@@QEAA@AEAY04$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[5])
0x18001e737  lea     rsi, [r14+58h]
0x18001e73b  lea     r8, [rbp+var_60]
0x18001e73f  mov     rdx, [rax]
0x18001e742  mov     rcx, rdi
0x18001e745  mov     rax, rbx
0x18001e748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e74d  test    eax, eax
0x18001e74f  js      loc_18001E809
0x18001e755  mov     [rbp+var_38], r15
0x18001e759  mov     rdi, [rbp+var_60]
0x18001e75d  mov     rax, [rdi]
0x18001e760  mov     rbx, [rax+60h]
0x18001e764  lea     rcx, [rbp+var_38]
0x18001e768  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e76d  lea     rdx, [rbp+var_38]
0x18001e771  mov     rcx, rdi
0x18001e774  mov     rax, rbx
0x18001e777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e77c  mov     rdi, [rbp+var_60]
0x18001e780  mov     rcx, [rsi]; string
0x18001e783  test    eax, eax
0x18001e785  mov     rax, [rdi]
0x18001e788  js      short loc_18001E7C2
0x18001e78a  mov     rbx, [rax+38h]
0x18001e78e  call    cs:__imp_WindowsDeleteString
0x18001e794  mov     [rsi], r15
0x18001e797  mov     rdx, rsi
0x18001e79a  mov     rcx, rdi
0x18001e79d  mov     rax, rbx
0x18001e7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7a5  mov     rcx, [rbp+28h]; this
0x18001e7a9  test    eax, eax
0x18001e7ab  jns     short loc_18001E7FA
0x18001e7ad  mov     r9d, eax; char *
0x18001e7b0  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e7b7  mov     edx, 61h ; 'a'; void *
0x18001e7bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e7c2  mov     rbx, [rax+40h]
0x18001e7c6  call    cs:__imp_WindowsDeleteString
0x18001e7cc  mov     [rsi], r15
0x18001e7cf  mov     rdx, rsi
0x18001e7d2  mov     rcx, rdi
0x18001e7d5  mov     rax, rbx
0x18001e7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7dd  mov     rcx, [rbp+28h]; this
0x18001e7e1  test    eax, eax
0x18001e7e3  jns     short loc_18001E7FA
0x18001e7e5  mov     r9d, eax; char *
0x18001e7e8  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e7ef  mov     edx, 65h ; 'e'; void *
0x18001e7f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e7fa  lea     rcx, [rbp+var_38]
0x18001e7fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e803  nop
0x18001e804  jmp     loc_18001E8F8
0x18001e809  xor     r8d, r8d; unsigned int
0x18001e80c  lea     rdx, pwzBaseUrl; unsigned __int16 *
0x18001e813  mov     rcx, rsi; this
0x18001e816  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18001e81b  mov     rcx, [rbp+28h]; this
0x18001e81f  test    eax, eax
0x18001e821  jns     short loc_18001E804
0x18001e823  mov     r9d, eax; char *
0x18001e826  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e82d  mov     edx, 6Ah ; 'j'; void *
0x18001e832  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e838  xor     edx, edx; length
0x18001e83a  mov     rcx, [rbp+string]; string
0x18001e83e  call    cs:__imp_WindowsGetStringRawBuffer
0x18001e844  mov     rdx, rax; String2
0x18001e847  lea     rcx, aActionOpenurl; "Action.OpenUrl"
0x18001e84e  call    wcscmp_0
0x18001e853  test    eax, eax
0x18001e855  jnz     loc_18001E902
0x18001e85b  mov     [rbp+var_60], r15
0x18001e85f  mov     rdi, [rbp+var_50]
0x18001e863  mov     rax, [rdi]
0x18001e866  mov     rbx, [rax+30h]
0x18001e86a  lea     rcx, [rbp+var_60]
0x18001e86e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e873  lea     rdx, aUrl; "url"
0x18001e87a  lea     rcx, [rbp+var_30]; string
0x18001e87e  call    ??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[4])
0x18001e883  lea     r8, [rbp+var_60]
0x18001e887  mov     rdx, [rax]
0x18001e88a  mov     rcx, rdi
0x18001e88d  mov     rax, rbx
0x18001e890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e895  mov     rcx, [rbp+28h]; this
0x18001e899  test    eax, eax
0x18001e89b  jns     short loc_18001E8B2
0x18001e89d  mov     r9d, eax; char *
0x18001e8a0  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e8a7  mov     edx, 70h ; 'p'; void *
0x18001e8ac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e8b2  mov     rsi, [rbp+var_60]
0x18001e8b6  mov     rax, [rsi]
0x18001e8b9  mov     rdi, [rax+40h]
0x18001e8bd  lea     rbx, [r14+60h]
0x18001e8c1  mov     rcx, [rbx]; string
0x18001e8c4  call    cs:__imp_WindowsDeleteString
0x18001e8ca  mov     [rbx], r15
0x18001e8cd  mov     rdx, rbx
0x18001e8d0  mov     rcx, rsi
0x18001e8d3  mov     rax, rdi
0x18001e8d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8db  mov     rcx, [rbp+28h]; this
0x18001e8df  test    eax, eax
0x18001e8e1  jns     short loc_18001E8F8
0x18001e8e3  mov     r9d, eax; char *
0x18001e8e6  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e8ed  mov     edx, 71h ; 'q'; void *
0x18001e8f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001e8f8  lea     rcx, [rbp+var_60]
0x18001e8fc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e901  nop
0x18001e902  mov     rcx, [rbp+string]; string
0x18001e906  call    cs:__imp_WindowsDeleteString
0x18001e90c  mov     [rbp+string], r15
0x18001e910  lea     rcx, [rbp+var_48]
0x18001e914  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e919  nop
0x18001e91a  lea     rcx, [rbp+var_50]
0x18001e91e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e923  nop
0x18001e924  lea     rcx, [rbp+var_40]
0x18001e928  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e92d  mov     rcx, [rbp+var_10]
0x18001e931  xor     rcx, rsp; StackCookie
0x18001e934  call    __security_check_cookie
0x18001e939  mov     rbx, [rsp+80h+arg_10]
0x18001e941  add     rsp, 80h
0x18001e948  pop     r15
0x18001e94a  pop     r14
0x18001e94c  pop     rdi
0x18001e94d  pop     rsi
0x18001e94e  pop     rbp
0x18001e94f  retn
```
