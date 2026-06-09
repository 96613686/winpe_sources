# TbLogProvider::TokenBrokerInternalInvokePluginToGetSignInAccount::StartActivity(IUnknown *,Windows::Security::Credentials::IWebAccountProvider *)

- ea: `0x1800cf824`
- end: `0x1800cf9d4`
- name: `?StartActivity@TokenBrokerInternalInvokePluginToGetSignInAccount@TbLogProvider@@QEAAXPEAUIUnknown@@PEAUIWebAccountProvider@Credentials@Security@Windows@@@Z`
- size: `432`
- prototype: `void(TbLogProvider::TokenBrokerInternalInvokePluginToGetSignInAccount *__hidden this, struct IUnknown *, struct Windows::Security::Credentials::IWebAccountProvider *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800cd8f0`

## callees

- `0x180003a8c`
- `0x18000ac90`
- `0x18000f3f4`
- `0x18004384c`
- `0x1800455a4`
- `0x180045b10`
- `0x18007f528`
- `0x1800cf824`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf8ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf8ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf86c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf8c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf8d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf8f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf86c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf8c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf8d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf8f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf996`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf9a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf9b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf996`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf9a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf9b4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800cf8e2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800cf8e2`

## pseudocode

```c
void __fastcall TbLogProvider::TokenBrokerInternalInvokePluginToGetSignInAccount::StartActivity(
        TbLogProvider::TokenBrokerInternalInvokePluginToGetSignInAccount *this,
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
      (unsigned int)byte_18014F249,
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
0x1800cf824  mov     rax, rsp
0x1800cf827  mov     [rax+8], rbx
0x1800cf82b  mov     [rax+10h], rsi
0x1800cf82f  push    rdi
0x1800cf830  push    r14
0x1800cf832  push    r15
0x1800cf834  sub     rsp, 90h
0x1800cf83b  mov     rsi, r8
0x1800cf83e  mov     r15, rdx
0x1800cf841  mov     r14, rcx
0x1800cf844  mov     qword ptr [rax-58h], 0
0x1800cf84c  xor     edi, edi
0x1800cf84e  mov     [rax-48h], rdi
0x1800cf852  lea     rdx, [rax-58h]; struct IUnknown *
0x1800cf856  mov     rcx, r15; this
0x1800cf859  call    ?GetCallingAppName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppName(IUnknown *,HSTRING__ * *)
0x1800cf85e  mov     rbx, [rsp+0A8h+string]
0x1800cf863  test    eax, eax
0x1800cf865  js      short loc_1800CF887
0x1800cf867  xor     edx, edx; length
0x1800cf869  mov     rcx, rbx; string
0x1800cf86c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cf872  lea     r8, [rsp+0A8h+var_48]; unsigned __int16 *
0x1800cf877  mov     rdx, rax; struct IUnknown *
0x1800cf87a  mov     rcx, r15; this
0x1800cf87d  call    ?GetCallingServiceName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEBGPEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingServiceName(IUnknown *,ushort const *,HSTRING__ * *)
0x1800cf882  mov     rdi, qword ptr [rsp+0A8h+var_48]
0x1800cf887  mov     [rsp+0A8h+var_50], 0
0x1800cf890  test    rsi, rsi
0x1800cf893  jz      short loc_1800CF8A9
0x1800cf895  mov     rax, [rsi]
0x1800cf898  lea     rdx, [rsp+0A8h+var_50]
0x1800cf89d  mov     rcx, rsi
0x1800cf8a0  mov     rax, [rax+30h]
0x1800cf8a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf8a9  mov     rcx, r14
0x1800cf8ac  call    ?zInternalStart@?$ActivityBase@VTbLogProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TbLogProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800cf8b1  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x1800cf8b6  mov     rsi, rax
0x1800cf8b9  mov     ecx, [rax]
0x1800cf8bb  cmp     ecx, 5
0x1800cf8be  jbe     loc_1800CF983
0x1800cf8c4  xor     edx, edx; length
0x1800cf8c6  mov     rcx, rdi; string
0x1800cf8c9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cf8cf  mov     [rsp+0A8h+var_40], rax
0x1800cf8d4  xor     edx, edx; length
0x1800cf8d6  mov     rcx, rbx; string
0x1800cf8d9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cf8df  mov     rcx, rax; pszPath
0x1800cf8e2  call    cs:__imp_PathFindFileNameW
0x1800cf8e8  mov     [rsp+0A8h+var_38], rax
0x1800cf8ed  xor     edx, edx; length
0x1800cf8ef  mov     rcx, [rsp+0A8h+var_50]; string
0x1800cf8f4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cf8fa  mov     [rsp+0A8h+var_30], rax
0x1800cf8ff  call    cs:__imp_GetCurrentThreadId
0x1800cf905  mov     [rsp+0A8h+arg_18], eax
0x1800cf90c  mov     [rsp+0A8h+var_28], 0
0x1800cf918  mov     r8, [r14+110h]
0x1800cf91f  cmp     byte ptr [r8+4], 0
0x1800cf924  jz      short loc_1800CF933
0x1800cf926  lea     rcx, [r8+18h]; struct _GUID *
0x1800cf92a  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800cf92f  test    al, al
0x1800cf931  jz      short loc_1800CF935
0x1800cf933  xor     ecx, ecx
0x1800cf935  add     r8, 8
0x1800cf939  lea     rax, [rsp+0A8h+var_40]
0x1800cf93e  mov     [rsp+0A8h+var_68], rax
0x1800cf943  lea     rax, [rsp+0A8h+var_38]
0x1800cf948  mov     [rsp+0A8h+var_70], rax
0x1800cf94d  lea     rax, [rsp+0A8h+var_30]
0x1800cf952  mov     [rsp+0A8h+var_78], rax
0x1800cf957  lea     rax, [rsp+0A8h+arg_18]
0x1800cf95f  mov     [rsp+0A8h+var_80], rax
0x1800cf964  lea     rax, [rsp+0A8h+var_28]
0x1800cf96c  mov     [rsp+0A8h+var_88], rax
0x1800cf971  mov     r9, rcx
0x1800cf974  lea     rdx, byte_18014F249
0x1800cf97b  mov     rcx, rsi
0x1800cf97e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800cf983  mov     rcx, r14
0x1800cf986  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800cf98b  nop
0x1800cf98c  mov     rcx, [rsp+0A8h+var_50]; string
0x1800cf991  test    rcx, rcx
0x1800cf994  jz      short loc_1800CF99D
0x1800cf996  call    cs:__imp_WindowsDeleteString
0x1800cf99c  nop
0x1800cf99d  test    rdi, rdi
0x1800cf9a0  jz      short loc_1800CF9AC
0x1800cf9a2  mov     rcx, rdi; string
0x1800cf9a5  call    cs:__imp_WindowsDeleteString
0x1800cf9ab  nop
0x1800cf9ac  test    rbx, rbx
0x1800cf9af  jz      short loc_1800CF9BB
0x1800cf9b1  mov     rcx, rbx; string
0x1800cf9b4  call    cs:__imp_WindowsDeleteString
0x1800cf9ba  nop
0x1800cf9bb  lea     r11, [rsp+0A8h+var_18]
0x1800cf9c3  mov     rbx, [r11+20h]
0x1800cf9c7  mov     rsi, [r11+28h]
0x1800cf9cb  mov     rsp, r11
0x1800cf9ce  pop     r15
0x1800cf9d0  pop     r14
0x1800cf9d2  pop     rdi
0x1800cf9d3  retn
```
