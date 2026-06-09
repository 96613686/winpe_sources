# ClientState::UpdateJsonString(Windows::Data::Json::IJsonObject *,Microsoft::WRL::Wrappers::HString &)

- ea: `0x18002b29c`
- end: `0x18002b399`
- name: `?UpdateJsonString@ClientState@@CAXPEAUIJsonObject@Json@Data@Windows@@AEAVHString@Wrappers@WRL@Microsoft@@@Z`
- size: `253`
- prototype: `static void(struct Windows::Data::Json::IJsonObject *, struct Microsoft::WRL::Wrappers::HString *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180018684`

## callees

- `0x180005f50`
- `0x1800101fc`
- `0x1800133c4`
- `0x180017dec`
- `0x18002ade8`
- `0x18002b29c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b30b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b30b`

## string_xrefs

- `0x18002b2ea`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002b332`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002b387`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ClientState::UpdateJsonString(struct Windows::Data::Json::IJsonObject *a1, HSTRING *a2)
{
  int v3; // eax
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, HSTRING *); // rbx
  int v6; // eax
  int v7; // eax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64); // [rsp+40h] [rbp+18h] BYREF

  if ( a1 )
  {
    v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a1;
    Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::OneSettingsPayload>::InternalAddRef(&v11);
    v10 = 0;
    v3 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(
           &v11,
           (__int64)&v10);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x47E,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)v3,
        v8);
    v4 = v10;
    v5 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v10 + 56LL);
    WindowsDeleteString(*a2);
    *a2 = 0;
    v6 = v5(v4, a2);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x481,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)v6,
        v8);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
  }
  else
  {
    v7 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)a2, &String1, 0);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x486,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)v7,
        v8);
  }
}

```

## disassembly

```asm
0x18002b29c  mov     rax, rsp
0x18002b29f  mov     [rax+10h], rbx
0x18002b2a3  mov     [rax+20h], rsi
0x18002b2a7  push    rdi; int
0x18002b2a8  sub     rsp, 20h
0x18002b2ac  mov     rsi, rdx
0x18002b2af  test    rcx, rcx
0x18002b2b2  jz      loc_18002B369
0x18002b2b8  mov     [rax+18h], rcx
0x18002b2bc  lea     rcx, [rax+18h]
0x18002b2c0  call    ?InternalAddRef@?$ComPtr@VOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::OneSettingsPayload>::InternalAddRef(void)
0x18002b2c5  nop
0x18002b2c6  mov     [rsp+28h+arg_0], 0
0x18002b2cf  lea     rdx, [rsp+28h+arg_0]
0x18002b2d4  lea     rcx, [rsp+28h+arg_10]
0x18002b2d9  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18002b2de  mov     rcx, [rsp+28h]; this
0x18002b2e3  test    eax, eax
0x18002b2e5  jns     short loc_18002B2FC
0x18002b2e7  mov     r9d, eax; char *
0x18002b2ea  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002b2f1  mov     edx, 47Eh; void *
0x18002b2f6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b2fc  mov     rdi, [rsp+28h+arg_0]
0x18002b301  mov     rax, [rdi]
0x18002b304  mov     rbx, [rax+38h]
0x18002b308  mov     rcx, [rsi]; string
0x18002b30b  call    cs:__imp_WindowsDeleteString
0x18002b311  mov     qword ptr [rsi], 0
0x18002b318  mov     rdx, rsi
0x18002b31b  mov     rcx, rdi
0x18002b31e  mov     rax, rbx
0x18002b321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b326  mov     rcx, [rsp+28h]; this
0x18002b32b  test    eax, eax
0x18002b32d  jns     short loc_18002B344
0x18002b32f  mov     r9d, eax; char *
0x18002b332  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002b339  mov     edx, 481h; void *
0x18002b33e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b344  lea     rcx, [rsp+28h+arg_0]
0x18002b349  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b34e  nop
0x18002b34f  lea     rcx, [rsp+28h+arg_10]
0x18002b354  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b359  mov     rbx, [rsp+28h+arg_8]
0x18002b35e  mov     rsi, [rsp+28h+arg_18]
0x18002b363  add     rsp, 20h
0x18002b367  pop     rdi
0x18002b368  retn
0x18002b369  xor     r8d, r8d; unsigned int
0x18002b36c  lea     rdx, String1; unsigned __int16 *
0x18002b373  mov     rcx, rsi; this
0x18002b376  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18002b37b  test    eax, eax
0x18002b37d  jns     short loc_18002B359
0x18002b37f  mov     rcx, [rsp+28h]; this
0x18002b384  mov     r9d, eax; char *
0x18002b387  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002b38e  mov     edx, 486h; void *
0x18002b393  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
