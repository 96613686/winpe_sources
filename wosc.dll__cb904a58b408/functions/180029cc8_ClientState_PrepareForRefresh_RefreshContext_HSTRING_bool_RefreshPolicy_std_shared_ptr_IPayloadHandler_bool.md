# ClientState::PrepareForRefresh(RefreshContext *,HSTRING__ *,bool,RefreshPolicy *,std::shared_ptr<IPayloadHandler>,bool)

- ea: `0x180029cc8`
- end: `0x180029f0a`
- name: `?PrepareForRefresh@ClientState@@QEAA_NPEAVRefreshContext@@PEAUHSTRING__@@_NPEAVRefreshPolicy@@V?$shared_ptr@VIPayloadHandler@@@std@@2@Z`
- size: `578`
- prototype: `__int64 __usercall@<rax>(ClientState *this@<rcx>, struct RefreshContext *@<rdx>, HSTRING@<r8>, __int64, __int64, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180018684`

## callees

- `0x180003110`
- `0x180005f50`
- `0x18000b0bc`
- `0x18000fe24`
- `0x1800101fc`
- `0x180013620`
- `0x180024f08`
- `0x180024f98`
- `0x1800267bc`
- `0x180029cc8`
- `0x18002aee0`
- `0x18002b3a0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029d82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029e5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029d82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029e5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029d46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029e21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029e30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029d46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029e21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029e30`

## string_xrefs

- `0x180029d9e`: `Windows.Data.Json.JsonObject`
- `0x180029ee3`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180029ef8`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall ClientState::PrepareForRefresh(
        ClientState *this,
        struct RefreshContext *a2,
        HSTRING a3,
        bool a4,
        struct RefreshPolicy *a5,
        _QWORD *a6,
        bool a7)
{
  bool ShouldRefresh; // bl
  HSTRING v11; // r12
  int v12; // eax
  PCWSTR v13; // rdi
  __int64 (__fastcall *v14)(PCWSTR, HSTRING, __int64 *, char *); // rbx
  int v15; // eax
  std::_Ref_count_base *v16; // rcx
  int v18; // [rsp+20h] [rbp-61h]
  char v19; // [rsp+30h] [rbp-51h] BYREF
  bool v20; // [rsp+31h] [rbp-50h]
  PCWSTR v21; // [rsp+38h] [rbp-49h] BYREF
  __int64 v22; // [rsp+40h] [rbp-41h] BYREF
  PCWSTR StringRawBuffer; // [rsp+48h] [rbp-39h] BYREF
  PCWSTR v24; // [rsp+50h] [rbp-31h] BYREF
  struct RefreshPolicy *v25; // [rsp+58h] [rbp-29h]
  _QWORD *v26; // [rsp+60h] [rbp-21h]
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-19h] BYREF
  __int64 v28; // [rsp+80h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]

  v20 = a4;
  v25 = a5;
  v26 = a6;
  if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*a6 + 64LL))(*a6) )
    goto LABEL_11;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*a6 + 56LL))(*a6) )
  {
    StringRawBuffer = 0;
    v11 = (HSTRING)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a6 + 16LL))(*a6);
    WindowsDeleteString(0);
    StringRawBuffer = (PCWSTR)v11;
    v21 = 0;
    v28 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    v12 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
            v28,
            (__int64)&v21);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15B,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)v12,
        v18);
    v19 = 0;
    v22 = 0;
    v13 = v21;
    v14 = *(__int64 (__fastcall **)(PCWSTR, HSTRING, __int64 *, char *))(*(_QWORD *)v21 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    v15 = v14(v13, v11, &v22, &v19);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)v15,
        v18);
    ShouldRefresh = 0;
    if ( !v19 )
    {
      ShouldRefresh = 1;
      ClientState::SetETag(this, 0);
      StringRawBuffer = WindowsGetStringRawBuffer(v11, 0);
      v24 = WindowsGetStringRawBuffer(a3, 0);
      OneSettingsClientTelemetry::PayloadFileCorrupted<unsigned short const *,unsigned short const *>(
        &v24,
        &StringRawBuffer);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    WindowsDeleteString(v11);
    if ( ShouldRefresh )
      goto LABEL_12;
LABEL_11:
    ShouldRefresh = ClientState::CalculateShouldRefresh(this, a2, a3, v20, v25, a7);
    if ( !ShouldRefresh )
      goto LABEL_14;
    goto LABEL_12;
  }
  if ( *((_QWORD *)this + 9) )
  {
    v21 = WindowsGetStringRawBuffer(a3, 0);
    OneSettingsClientTelemetry::PayloadFileNotFound<unsigned short const *>(&v21);
  }
  ShouldRefresh = 1;
  ClientState::SetETag(this, 0);
LABEL_12:
  if ( !*((_QWORD *)this + 30) )
    ClientState::UpdateQueryParams(this, a2, a3);
LABEL_14:
  v16 = (std::_Ref_count_base *)a6[1];
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  return ShouldRefresh;
}

```

## disassembly

```asm
0x180029cc8  mov     [rsp-8+arg_18], rbx
0x180029ccd  push    rbp
0x180029cce  push    rsi
0x180029ccf  push    rdi
0x180029cd0  push    r12
0x180029cd2  push    r13
0x180029cd4  push    r14
0x180029cd6  push    r15
0x180029cd8  lea     rbp, [rsp-0Fh]
0x180029cdd  sub     rsp, 90h
0x180029ce4  mov     rax, cs:__security_cookie
0x180029ceb  xor     rax, rsp
0x180029cee  mov     [rbp+3Fh+var_38], rax
0x180029cf2  mov     [rbp+3Fh+var_8F], r9b
0x180029cf6  mov     r14, r8
0x180029cf9  mov     r13, rdx
0x180029cfc  mov     rsi, rcx
0x180029cff  mov     rax, [rbp+3Fh+arg_20]
0x180029d03  mov     [rbp+3Fh+var_68], rax
0x180029d07  mov     r15, [rbp+3Fh+arg_28]
0x180029d0b  mov     [rbp+3Fh+var_60], r15
0x180029d0f  mov     rcx, [r15]
0x180029d12  mov     rax, [rcx]
0x180029d15  mov     rax, [rax+40h]
0x180029d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d1e  xor     edi, edi
0x180029d20  test    eax, eax
0x180029d22  jnz     loc_180029E69
0x180029d28  mov     rcx, [r15]
0x180029d2b  mov     rax, [rcx]
0x180029d2e  mov     rax, [rax+38h]
0x180029d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d37  test    al, al
0x180029d39  jnz     short loc_180029D6A
0x180029d3b  cmp     [rsi+48h], rdi
0x180029d3f  jz      short loc_180029D59
0x180029d41  xor     edx, edx; length
0x180029d43  mov     rcx, r14; string
0x180029d46  call    cs:__imp_WindowsGetStringRawBuffer
0x180029d4c  mov     [rbp+3Fh+var_88], rax
0x180029d50  lea     rcx, [rbp+3Fh+var_88]
0x180029d54  call    ??$PayloadFileNotFound@PEBG@OneSettingsClientTelemetry@@SAX$$QEAPEBG@Z; OneSettingsClientTelemetry::PayloadFileNotFound<ushort const *>(ushort const * &&)
0x180029d59  mov     bl, 1
0x180029d5b  xor     edx, edx; unsigned __int16 *
0x180029d5d  mov     rcx, rsi; this
0x180029d60  call    ?SetETag@ClientState@@QEAAXPEBG@Z; ClientState::SetETag(ushort const *)
0x180029d65  jmp     loc_180029E91
0x180029d6a  mov     [rbp+3Fh+var_78], rdi
0x180029d6e  mov     rcx, [r15]
0x180029d71  mov     rax, [rcx]
0x180029d74  mov     rax, [rax+10h]
0x180029d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d7d  mov     r12, rax
0x180029d80  xor     ecx, ecx; string
0x180029d82  call    cs:__imp_WindowsDeleteString
0x180029d88  mov     [rbp+3Fh+var_78], r12
0x180029d8c  mov     [rbp+3Fh+var_88], rdi
0x180029d90  mov     [rbp+3Fh+var_40], rdi
0x180029d94  mov     r9d, 1Ch; unsigned int
0x180029d9a  lea     r8d, [r9+1]; unsigned int
0x180029d9e  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180029da5  lea     rcx, [rbp+3Fh+hstringHeader]; hstringHeader
0x180029da9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180029dae  lea     rdx, [rbp+3Fh+var_88]
0x180029db2  mov     rcx, [rbp+3Fh+var_40]
0x180029db6  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x180029dbb  mov     rcx, [rbp+47h]; this
0x180029dbf  test    eax, eax
0x180029dc1  js      loc_180029EF5
0x180029dc7  mov     [rbp+3Fh+var_90], dil
0x180029dcb  mov     [rbp+3Fh+var_80], rdi
0x180029dcf  mov     rdi, [rbp+3Fh+var_88]
0x180029dd3  mov     rax, [rdi]
0x180029dd6  mov     rbx, [rax+38h]
0x180029dda  lea     rcx, [rbp+3Fh+var_80]
0x180029dde  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029de3  lea     r9, [rbp+3Fh+var_90]
0x180029de7  lea     r8, [rbp+3Fh+var_80]
0x180029deb  mov     rdx, r12
0x180029dee  mov     rcx, rdi
0x180029df1  mov     rax, rbx
0x180029df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029df9  mov     rcx, [rbp+47h]; this
0x180029dfd  xor     edi, edi
0x180029dff  test    eax, eax
0x180029e01  js      loc_180029EE0
0x180029e07  mov     bl, dil
0x180029e0a  cmp     [rbp+3Fh+var_90], dil
0x180029e0e  jnz     short loc_180029E48
0x180029e10  mov     bl, 1
0x180029e12  xor     edx, edx; unsigned __int16 *
0x180029e14  mov     rcx, rsi; this
0x180029e17  call    ?SetETag@ClientState@@QEAAXPEBG@Z; ClientState::SetETag(ushort const *)
0x180029e1c  xor     edx, edx; length
0x180029e1e  mov     rcx, r12; string
0x180029e21  call    cs:__imp_WindowsGetStringRawBuffer
0x180029e27  mov     [rbp+3Fh+var_78], rax
0x180029e2b  xor     edx, edx; length
0x180029e2d  mov     rcx, r14; string
0x180029e30  call    cs:__imp_WindowsGetStringRawBuffer
0x180029e36  mov     [rbp+3Fh+var_70], rax
0x180029e3a  lea     rdx, [rbp+3Fh+var_78]
0x180029e3e  lea     rcx, [rbp+3Fh+var_70]
0x180029e42  call    ??$PayloadFileCorrupted@PEBGPEBG@OneSettingsClientTelemetry@@SAX$$QEAPEBG0@Z; OneSettingsClientTelemetry::PayloadFileCorrupted<ushort const *,ushort const *>(ushort const * &&,ushort const * &&)
0x180029e47  nop
0x180029e48  lea     rcx, [rbp+3Fh+var_80]
0x180029e4c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029e51  nop
0x180029e52  lea     rcx, [rbp+3Fh+var_88]
0x180029e56  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029e5b  nop
0x180029e5c  mov     rcx, r12; string
0x180029e5f  call    cs:__imp_WindowsDeleteString
0x180029e65  test    bl, bl
0x180029e67  jnz     short loc_180029E91
0x180029e69  mov     al, [rbp+3Fh+arg_30]
0x180029e6c  mov     [rsp+0C0h+var_98], al; bool
0x180029e70  mov     rax, [rbp+3Fh+var_68]
0x180029e74  mov     [rsp+0C0h+var_A0], rax; struct RefreshPolicy *
0x180029e79  mov     r9b, [rbp+3Fh+var_8F]; bool
0x180029e7d  mov     r8, r14; HSTRING
0x180029e80  mov     rdx, r13; struct RefreshContext *
0x180029e83  mov     rcx, rsi; this
0x180029e86  call    ?CalculateShouldRefresh@ClientState@@AEAA_NPEAVRefreshContext@@PEAUHSTRING__@@_NPEAVRefreshPolicy@@2@Z; ClientState::CalculateShouldRefresh(RefreshContext *,HSTRING__ *,bool,RefreshPolicy *,bool)
0x180029e8b  mov     bl, al
0x180029e8d  test    al, al
0x180029e8f  jz      short loc_180029EA9
0x180029e91  cmp     [rsi+0F0h], rdi
0x180029e98  jnz     short loc_180029EA9
0x180029e9a  mov     r8, r14; HSTRING
0x180029e9d  mov     rdx, r13; struct RefreshContext *
0x180029ea0  mov     rcx, rsi; this
0x180029ea3  call    ?UpdateQueryParams@ClientState@@AEAAXPEAVRefreshContext@@PEAUHSTRING__@@@Z; ClientState::UpdateQueryParams(RefreshContext *,HSTRING__ *)
0x180029ea8  nop
0x180029ea9  mov     rcx, [r15+8]; this
0x180029ead  test    rcx, rcx
0x180029eb0  jz      short loc_180029EB7
0x180029eb2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029eb7  mov     al, bl
0x180029eb9  mov     rcx, [rbp+3Fh+var_38]
0x180029ebd  xor     rcx, rsp; StackCookie
0x180029ec0  call    __security_check_cookie
0x180029ec5  mov     rbx, [rsp+0C0h+arg_18]
0x180029ecd  add     rsp, 90h
0x180029ed4  pop     r15
0x180029ed6  pop     r14
0x180029ed8  pop     r13
0x180029eda  pop     r12
0x180029edc  pop     rdi
0x180029edd  pop     rsi
0x180029ede  pop     rbp
0x180029edf  retn
0x180029ee0  mov     r9d, eax; char *
0x180029ee3  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x180029eea  mov     edx, 161h; void *
0x180029eef  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029ef5  mov     r9d, eax; char *
0x180029ef8  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x180029eff  mov     edx, 15Bh; void *
0x180029f04  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
