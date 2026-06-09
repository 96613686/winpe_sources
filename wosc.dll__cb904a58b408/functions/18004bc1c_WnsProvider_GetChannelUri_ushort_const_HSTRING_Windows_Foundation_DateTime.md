# WnsProvider::GetChannelUri(ushort const *,HSTRING__ * *,Windows::Foundation::DateTime *)

- ea: `0x18004bc1c`
- end: `0x18004bec7`
- name: `?GetChannelUri@WnsProvider@@CAJPEBGPEAPEAUHSTRING__@@PEAUDateTime@Foundation@Windows@@@Z`
- size: `683`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HSTRING *, struct Windows::Foundation::DateTime *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004e774`
- `0x18004e95c`

## callees

- `0x180003110`
- `0x180005f50`
- `0x180006b9c`
- `0x180009384`
- `0x18000b0bc`
- `0x1800101fc`
- `0x18004a518`
- `0x18004bc1c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bd76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bdda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bd76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bdda`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004bc98`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004bc98`

## string_xrefs

- `0x18004be64`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall WnsProvider::GetChannelUri(
        const unsigned __int16 *a1,
        HSTRING *a2,
        struct Windows::Foundation::DateTime *a3)
{
  __int64 v5; // rbx
  int ActivationFactory; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, PVOID, _QWORD); // rbx
  HSTRING_HEADER *v9; // rax
  int v10; // eax
  DWORD v11; // edx
  int v12; // r8d
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdx
  const WCHAR *v16; // rbx
  __int64 (__fastcall *v17)(const WCHAR *, HSTRING *); // rdi
  int v18; // eax
  int v19; // eax
  HSTRING v20; // rax
  const char *v21; // r9
  __int64 result; // rax
  unsigned int v23; // eax
  HSTRING v24; // [rsp+28h] [rbp-70h] BYREF
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-68h] BYREF
  __int64 v26; // [rsp+38h] [rbp-60h] BYREF
  const WCHAR *v27; // [rsp+40h] [rbp-58h] BYREF
  const WCHAR *v28; // [rsp+48h] [rbp-50h]
  HSTRING_HEADER v29; // [rsp+50h] [rbp-48h] BYREF
  __int64 v30; // [rsp+68h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v27 = a1;
  v26 = 0;
  v30 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v29,
    L"Windows.Networking.PushNotifications.PushNotificationChannelManager",
    0x44u,
    0x43u);
  v5 = v30;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_8baf9b65_77a1_4588_bd19_861529a9dcf0, &v26);
  try
  {
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x275,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
        (const char *)(unsigned int)ActivationFactory,
        0);
    v25 = 0;
    v7 = v26;
    v8 = *(__int64 (__fastcall **)(__int64, PVOID, _QWORD))(*(_QWORD *)v26 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v29, &v27);
    v10 = v8(v7, v9[1].Reserved.Reserved1, &v25);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x279,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
        (const char *)(unsigned int)v10,
        0);
    v28 = 0;
    v13 = v25;
    v27 = 0;
    v14 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *>(
            v25,
            v11,
            v12);
    if ( v14 >= 0 )
      v14 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), const WCHAR **))(*v13)[8])(
              v13,
              &v27);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x71B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
        (const char *)(unsigned int)v14,
        1);
    v16 = v27;
    v28 = v27;
    if ( !v27 )
    {
      v23 = wil::verify_hresult<long>(2147549183LL, v15);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x27F,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
        (const char *)v23,
        1);
    }
    v24 = 0;
    v17 = *(__int64 (__fastcall **)(const WCHAR *, HSTRING *))(*(_QWORD *)v27 + 48LL);
    WindowsDeleteString(0);
    v24 = 0;
    v18 = v17(v16, &v24);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x283,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
        (const char *)(unsigned int)v18,
        1);
    v19 = (*(__int64 (__fastcall **)(const WCHAR *, struct Windows::Foundation::DateTime *))(*(_QWORD *)v16 + 56LL))(
            v16,
            a3);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x285,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
        (const char *)(unsigned int)v19,
        1);
    v20 = v24;
    v24 = 0;
    *a2 = v20;
    WindowsDeleteString(0);
    v24 = 0;
    (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v16 + 16LL))(v16);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x28B,
                           (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
                           v21);
  }
  return result;
}

```

## disassembly

```asm
0x18004bc1c  mov     r11, rsp
0x18004bc1f  mov     [r11+20h], rbx
0x18004bc23  push    rsi
0x18004bc24  push    rdi
0x18004bc25  push    r14
0x18004bc27  sub     rsp, 80h
0x18004bc2e  mov     rax, cs:__security_cookie
0x18004bc35  xor     rax, rsp
0x18004bc38  mov     [rsp+98h+var_28], rax
0x18004bc3d  mov     rsi, r8
0x18004bc40  mov     r14, rdx
0x18004bc43  mov     [r11-58h], rcx
0x18004bc47  mov     [rsp+98h+var_78], 0; int
0x18004bc4f  mov     qword ptr [r11-60h], 0
0x18004bc57  mov     qword ptr [r11-30h], 0
0x18004bc5f  mov     r9d, 43h ; 'C'; unsigned int
0x18004bc65  lea     r8d, [r9+1]; unsigned int
0x18004bc69  lea     rdx, ?RuntimeClass_Windows_Networking_PushNotifications_PushNotificationChannelManager@@3QBGB; "Windows.Networking.PushNotifications.Pu"...
0x18004bc70  lea     rcx, [r11-48h]; hstringHeader
0x18004bc74  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004bc79  nop
0x18004bc7a  mov     rbx, [rsp+98h+var_30]
0x18004bc7f  lea     rcx, [rsp+98h+var_60]
0x18004bc84  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004bc89  lea     r8, [rsp+98h+var_60]
0x18004bc8e  lea     rdx, _GUID_8baf9b65_77a1_4588_bd19_861529a9dcf0
0x18004bc95  mov     rcx, rbx
0x18004bc98  call    cs:__imp_RoGetActivationFactory
0x18004bc9e  mov     rcx, [rsp+98h]; this
0x18004bca6  test    eax, eax
0x18004bca8  js      loc_18004BE37
0x18004bcae  mov     [rsp+98h+var_68], 0
0x18004bcb7  mov     rdi, [rsp+98h+var_60]
0x18004bcbc  mov     rax, [rdi]
0x18004bcbf  mov     rbx, [rax+38h]
0x18004bcc3  lea     rcx, [rsp+98h+var_68]
0x18004bcc8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004bccd  lea     rdx, [rsp+98h+var_58]
0x18004bcd2  lea     rcx, [rsp+98h+var_48]
0x18004bcd7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004bcdc  nop
0x18004bcdd  lea     r8, [rsp+98h+var_68]
0x18004bce2  mov     rdx, [rax+18h]
0x18004bce6  mov     rcx, rdi
0x18004bce9  mov     rax, rbx
0x18004bcec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bcf1  mov     rcx, [rsp+98h]; this
0x18004bcf9  test    eax, eax
0x18004bcfb  js      loc_18004BE4C
0x18004bd01  mov     [rsp+98h+var_50], 0
0x18004bd0a  mov     rbx, [rsp+98h+var_68]
0x18004bd0f  mov     [rsp+98h+var_58], 0
0x18004bd18  mov     [rsp+98h+var_78], 1; int
0x18004bd20  mov     rcx, rbx
0x18004bd23  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18004bd28  test    eax, eax
0x18004bd2a  js      short loc_18004BD41
0x18004bd2c  mov     rax, [rbx]
0x18004bd2f  lea     rdx, [rsp+98h+var_58]
0x18004bd34  mov     rcx, rbx
0x18004bd37  mov     rax, [rax+40h]
0x18004bd3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd40  nop
0x18004bd41  mov     rcx, [rsp+98h]; this
0x18004bd49  test    eax, eax
0x18004bd4b  js      loc_18004BE61
0x18004bd51  mov     rbx, [rsp+98h+var_58]
0x18004bd56  mov     [rsp+98h+var_50], rbx
0x18004bd5b  test    rbx, rbx
0x18004bd5e  jz      loc_18004BE9F
0x18004bd64  mov     [rsp+98h+var_70], 0
0x18004bd6d  mov     rax, [rbx]
0x18004bd70  mov     rdi, [rax+30h]
0x18004bd74  xor     ecx, ecx; string
0x18004bd76  call    cs:__imp_WindowsDeleteString
0x18004bd7c  mov     [rsp+98h+var_70], 0
0x18004bd85  lea     rdx, [rsp+98h+var_70]
0x18004bd8a  mov     rcx, rbx
0x18004bd8d  mov     rax, rdi
0x18004bd90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd95  mov     rcx, [rsp+98h]; this
0x18004bd9d  test    eax, eax
0x18004bd9f  js      loc_18004BE76
0x18004bda5  mov     rax, [rbx]
0x18004bda8  mov     rdx, rsi
0x18004bdab  mov     rcx, rbx
0x18004bdae  mov     rax, [rax+38h]
0x18004bdb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bdb7  mov     rcx, [rsp+98h]; this
0x18004bdbf  test    eax, eax
0x18004bdc1  js      loc_18004BE8A
0x18004bdc7  mov     rax, [rsp+98h+var_70]
0x18004bdcc  mov     [rsp+98h+var_70], 0
0x18004bdd5  mov     [r14], rax
0x18004bdd8  xor     ecx, ecx; string
0x18004bdda  call    cs:__imp_WindowsDeleteString
0x18004bde0  mov     [rsp+98h+var_70], 0
0x18004bde9  mov     rax, [rbx]
0x18004bdec  mov     rcx, rbx
0x18004bdef  mov     rax, [rax+10h]
0x18004bdf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bdf8  nop
0x18004bdf9  lea     rcx, [rsp+98h+var_68]
0x18004bdfe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004be03  nop
0x18004be04  lea     rcx, [rsp+98h+var_60]
0x18004be09  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004be0e  xor     eax, eax
0x18004be10  jmp     short loc_18004BE16
0x18004be12  mov     eax, [rsp+98h+var_78]
0x18004be16  mov     rcx, [rsp+98h+var_28]
0x18004be1b  xor     rcx, rsp; StackCookie
0x18004be1e  call    __security_check_cookie
0x18004be23  mov     rbx, [rsp+98h+arg_18]
0x18004be2b  add     rsp, 80h
0x18004be32  pop     r14
0x18004be34  pop     rdi
0x18004be35  pop     rsi
0x18004be36  retn
0x18004be37  mov     r9d, eax; char *
0x18004be3a  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004be41  mov     edx, 275h; void *
0x18004be46  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004be4c  mov     r9d, eax; char *
0x18004be4f  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004be56  mov     edx, 279h; void *
0x18004be5b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004be61  mov     r9d, eax; char *
0x18004be64  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004be6b  mov     edx, 71Bh; void *
0x18004be70  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004be76  mov     r9d, eax; char *
0x18004be79  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004be80  mov     edx, 283h; void *
0x18004be85  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004be8a  mov     r9d, eax; char *
0x18004be8d  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004be94  mov     edx, 285h; void *
0x18004be99  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004be9f  mov     ecx, 8000FFFFh
0x18004bea4  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18004bea9  mov     r9d, eax; char *
0x18004beac  mov     rcx, [rsp+98h]; this
0x18004beb4  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\onesettings\\"...
0x18004bebb  mov     edx, 27Fh; void *
0x18004bec0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
