# TbLogProvider::TokenBrokerInternalSetDefaultSignInAccount::StartActivity(IUnknown *,Windows::Security::Credentials::IWebAccountProvider *)

- ea: `0x1800cf9dc`
- end: `0x1800cfb8c`
- name: `?StartActivity@TokenBrokerInternalSetDefaultSignInAccount@TbLogProvider@@QEAAXPEAUIUnknown@@PEAUIWebAccountProvider@Credentials@Security@Windows@@@Z`
- size: `432`
- prototype: `void(TbLogProvider::TokenBrokerInternalSetDefaultSignInAccount *__hidden this, struct IUnknown *, struct Windows::Security::Credentials::IWebAccountProvider *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180082e10`

## callees

- `0x180003a8c`
- `0x18000ac90`
- `0x18000f3f4`
- `0x18004384c`
- `0x1800455a4`
- `0x180045b10`
- `0x18007f528`
- `0x1800cf9dc`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cfab7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cfab7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cfa24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cfa81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cfa91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cfaac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cfa24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cfa81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cfa91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cfaac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cfb4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cfb5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cfb6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cfb4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cfb5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cfb6c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800cfa9a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800cfa9a`

## pseudocode

```c
void __fastcall TbLogProvider::TokenBrokerInternalSetDefaultSignInAccount::StartActivity(
        TbLogProvider::TokenBrokerInternalSetDefaultSignInAccount *this,
        struct IUnknown *a2,
        HSTRING *a3)
{
  HSTRING v6; // rdi
  int CallingAppName; // eax
  HSTRING v8; // rbx
  struct IUnknown *StringRawBuffer; // rax
  HSTRING *v10; // r9
  const struct _tlgProvider_t *v11; // rax
  int v12; // esi
  const WCHAR *v13; // rax
  __int64 v14; // r8
  int v15; // ecx
  HSTRING string; // [rsp+50h] [rbp-58h] BYREF
  HSTRING v17; // [rsp+58h] [rbp-50h] BYREF
  unsigned __int16 v18[4]; // [rsp+60h] [rbp-48h] BYREF
  PCWSTR v19; // [rsp+68h] [rbp-40h] BYREF
  LPWSTR FileNameW; // [rsp+70h] [rbp-38h] BYREF
  PCWSTR v21; // [rsp+78h] [rbp-30h] BYREF
  __int64 v22; // [rsp+80h] [rbp-28h] BYREF
  DWORD CurrentThreadId; // [rsp+C8h] [rbp+20h] BYREF

  string = 0;
  v6 = 0;
  *(_QWORD *)v18 = 0;
  CallingAppName = Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppName(
                     (Windows::Internal::Security::Authentication::TokenBroker *)a2,
                     (struct IUnknown *)&string,
                     a3);
  v8 = string;
  if ( CallingAppName >= 0 )
  {
    StringRawBuffer = (struct IUnknown *)WindowsGetStringRawBuffer(string, 0);
    Windows::Internal::Security::Authentication::TokenBroker::GetCallingServiceName(
      (Windows::Internal::Security::Authentication::TokenBroker *)a2,
      StringRawBuffer,
      v18,
      v10);
    v6 = *(HSTRING *)v18;
  }
  v17 = 0;
  if ( a3 )
    (*((void (__fastcall **)(HSTRING *, HSTRING *))*a3 + 6))(a3, &v17);
  wil::ActivityBase<TbLogProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
  v11 = TbLogProvider::Provider();
  v12 = (int)v11;
  if ( *(_DWORD *)v11 > 5u )
  {
    v19 = WindowsGetStringRawBuffer(v6, 0);
    v13 = WindowsGetStringRawBuffer(v8, 0);
    FileNameW = PathFindFileNameW(v13);
    v21 = WindowsGetStringRawBuffer(v17, 0);
    CurrentThreadId = GetCurrentThreadId();
    v22 = 0;
    v14 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v14 + 4) || _tlgGuidIsZero((const struct _GUID *)(v14 + 24)) )
      v15 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v12,
      (unsigned int)&byte_18014F3A7,
      v14 + 8,
      v15,
      (__int64)&v22,
      (__int64)&CurrentThreadId,
      (__int64)&v21,
      (__int64)&FileNameW,
      (__int64)&v19);
  }
  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
  if ( v17 )
    WindowsDeleteString(v17);
  if ( v6 )
    WindowsDeleteString(v6);
  if ( v8 )
    WindowsDeleteString(v8);
}

```

## disassembly

```asm
0x1800cf9dc  mov     rax, rsp
0x1800cf9df  mov     [rax+8], rbx
0x1800cf9e3  mov     [rax+10h], rsi
0x1800cf9e7  push    rdi
0x1800cf9e8  push    r14
0x1800cf9ea  push    r15
0x1800cf9ec  sub     rsp, 90h
0x1800cf9f3  mov     rsi, r8
0x1800cf9f6  mov     r15, rdx
0x1800cf9f9  mov     r14, rcx
0x1800cf9fc  mov     qword ptr [rax-58h], 0
0x1800cfa04  xor     edi, edi
0x1800cfa06  mov     [rax-48h], rdi
0x1800cfa0a  lea     rdx, [rax-58h]; struct IUnknown *
0x1800cfa0e  mov     rcx, r15; this
0x1800cfa11  call    ?GetCallingAppName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppName(IUnknown *,HSTRING__ * *)
0x1800cfa16  mov     rbx, [rsp+0A8h+string]
0x1800cfa1b  test    eax, eax
0x1800cfa1d  js      short loc_1800CFA3F
0x1800cfa1f  xor     edx, edx; length
0x1800cfa21  mov     rcx, rbx; string
0x1800cfa24  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cfa2a  lea     r8, [rsp+0A8h+var_48]; unsigned __int16 *
0x1800cfa2f  mov     rdx, rax; struct IUnknown *
0x1800cfa32  mov     rcx, r15; this
0x1800cfa35  call    ?GetCallingServiceName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEBGPEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingServiceName(IUnknown *,ushort const *,HSTRING__ * *)
0x1800cfa3a  mov     rdi, qword ptr [rsp+0A8h+var_48]
0x1800cfa3f  mov     [rsp+0A8h+var_50], 0
0x1800cfa48  test    rsi, rsi
0x1800cfa4b  jz      short loc_1800CFA61
0x1800cfa4d  mov     rax, [rsi]
0x1800cfa50  lea     rdx, [rsp+0A8h+var_50]
0x1800cfa55  mov     rcx, rsi
0x1800cfa58  mov     rax, [rax+30h]
0x1800cfa5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cfa61  mov     rcx, r14
0x1800cfa64  call    ?zInternalStart@?$ActivityBase@VTbLogProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TbLogProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800cfa69  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x1800cfa6e  mov     rsi, rax
0x1800cfa71  mov     ecx, [rax]
0x1800cfa73  cmp     ecx, 5
0x1800cfa76  jbe     loc_1800CFB3B
0x1800cfa7c  xor     edx, edx; length
0x1800cfa7e  mov     rcx, rdi; string
0x1800cfa81  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cfa87  mov     [rsp+0A8h+var_40], rax
0x1800cfa8c  xor     edx, edx; length
0x1800cfa8e  mov     rcx, rbx; string
0x1800cfa91  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cfa97  mov     rcx, rax; pszPath
0x1800cfa9a  call    cs:__imp_PathFindFileNameW
0x1800cfaa0  mov     [rsp+0A8h+var_38], rax
0x1800cfaa5  xor     edx, edx; length
0x1800cfaa7  mov     rcx, [rsp+0A8h+var_50]; string
0x1800cfaac  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cfab2  mov     [rsp+0A8h+var_30], rax
0x1800cfab7  call    cs:__imp_GetCurrentThreadId
0x1800cfabd  mov     [rsp+0A8h+arg_18], eax
0x1800cfac4  mov     [rsp+0A8h+var_28], 0
0x1800cfad0  mov     r8, [r14+110h]
0x1800cfad7  cmp     byte ptr [r8+4], 0
0x1800cfadc  jz      short loc_1800CFAEB
0x1800cfade  lea     rcx, [r8+18h]; struct _GUID *
0x1800cfae2  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800cfae7  test    al, al
0x1800cfae9  jz      short loc_1800CFAED
0x1800cfaeb  xor     ecx, ecx
0x1800cfaed  add     r8, 8
0x1800cfaf1  lea     rax, [rsp+0A8h+var_40]
0x1800cfaf6  mov     [rsp+0A8h+var_68], rax
0x1800cfafb  lea     rax, [rsp+0A8h+var_38]
0x1800cfb00  mov     [rsp+0A8h+var_70], rax
0x1800cfb05  lea     rax, [rsp+0A8h+var_30]
0x1800cfb0a  mov     [rsp+0A8h+var_78], rax
0x1800cfb0f  lea     rax, [rsp+0A8h+arg_18]
0x1800cfb17  mov     [rsp+0A8h+var_80], rax
0x1800cfb1c  lea     rax, [rsp+0A8h+var_28]
0x1800cfb24  mov     [rsp+0A8h+var_88], rax
0x1800cfb29  mov     r9, rcx
0x1800cfb2c  lea     rdx, byte_18014F3A7
0x1800cfb33  mov     rcx, rsi
0x1800cfb36  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800cfb3b  mov     rcx, r14
0x1800cfb3e  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800cfb43  nop
0x1800cfb44  mov     rcx, [rsp+0A8h+var_50]; string
0x1800cfb49  test    rcx, rcx
0x1800cfb4c  jz      short loc_1800CFB55
0x1800cfb4e  call    cs:__imp_WindowsDeleteString
0x1800cfb54  nop
0x1800cfb55  test    rdi, rdi
0x1800cfb58  jz      short loc_1800CFB64
0x1800cfb5a  mov     rcx, rdi; string
0x1800cfb5d  call    cs:__imp_WindowsDeleteString
0x1800cfb63  nop
0x1800cfb64  test    rbx, rbx
0x1800cfb67  jz      short loc_1800CFB73
0x1800cfb69  mov     rcx, rbx; string
0x1800cfb6c  call    cs:__imp_WindowsDeleteString
0x1800cfb72  nop
0x1800cfb73  lea     r11, [rsp+0A8h+var_18]
0x1800cfb7b  mov     rbx, [r11+20h]
0x1800cfb7f  mov     rsi, [r11+28h]
0x1800cfb83  mov     rsp, r11
0x1800cfb86  pop     r15
0x1800cfb88  pop     r14
0x1800cfb8a  pop     rdi
0x1800cfb8b  retn
```
