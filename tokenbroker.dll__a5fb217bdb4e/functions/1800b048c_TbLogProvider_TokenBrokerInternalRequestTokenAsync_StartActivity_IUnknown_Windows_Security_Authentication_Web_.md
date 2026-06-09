# TbLogProvider::TokenBrokerInternalRequestTokenAsync::StartActivity(IUnknown *,Windows::Security::Authentication::Web::Core::IWebTokenRequest *)

- ea: `0x1800b048c`
- end: `0x1800b077a`
- name: `?StartActivity@TokenBrokerInternalRequestTokenAsync@TbLogProvider@@QEAAXPEAUIUnknown@@PEAUIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@Z`
- size: `750`
- prototype: `void(TbLogProvider::TokenBrokerInternalRequestTokenAsync *__hidden this, struct IUnknown *, struct Windows::Security::Authentication::Web::Core::IWebTokenRequest *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800aef20`

## callees

- `0x180002fb4`
- `0x18000ac90`
- `0x18000f3f4`
- `0x18000fcf8`
- `0x1800455a4`
- `0x180063fc4`
- `0x18007f528`
- `0x1800a939c`
- `0x1800b048c`
- `0x1800b406c`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b065b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b065b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b0586`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b05f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b0606`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b061e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b0631`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b0644`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b0586`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b05f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b0606`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b061e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b0631`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b0644`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b071a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b0729`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b073a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b074b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b075f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b071a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b0729`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b073a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b074b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b075f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800b064d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800b064d`

## pseudocode

```c
void __fastcall TbLogProvider::TokenBrokerInternalRequestTokenAsync::StartActivity(
        TbLogProvider::TokenBrokerInternalRequestTokenAsync *this,
        struct IUnknown *a2,
        HSTRING *a3)
{
  HSTRING v6; // rax
  HSTRING v7; // rdi
  int CallingAppName; // eax
  HSTRING v9; // rbx
  struct IUnknown *StringRawBuffer; // rax
  HSTRING *v11; // r9
  const struct _tlgProvider_t *v12; // rax
  int v13; // esi
  const WCHAR *v14; // rax
  __int64 v15; // r8
  int v16; // ecx
  DWORD CurrentThreadId; // [rsp+60h] [rbp-78h] BYREF
  HSTRING string; // [rsp+68h] [rbp-70h] BYREF
  HSTRING v19; // [rsp+70h] [rbp-68h] BYREF
  HSTRING v20; // [rsp+78h] [rbp-60h] BYREF
  HSTRING v21; // [rsp+80h] [rbp-58h] BYREF
  unsigned __int16 v22[4]; // [rsp+88h] [rbp-50h] BYREF
  PCWSTR v23; // [rsp+90h] [rbp-48h] BYREF
  PCWSTR v24; // [rsp+98h] [rbp-40h] BYREF
  PCWSTR v25; // [rsp+A0h] [rbp-38h] BYREF
  PCWSTR v26; // [rsp+A8h] [rbp-30h] BYREF
  LPWSTR FileNameW; // [rsp+B0h] [rbp-28h] BYREF
  _QWORD v28[4]; // [rsp+B8h] [rbp-20h] BYREF
  int v29; // [rsp+F0h] [rbp+18h] BYREF
  __int64 v30; // [rsp+F8h] [rbp+20h] BYREF

  v21 = 0;
  v20 = 0;
  v19 = 0;
  v29 = 0;
  if ( a3 )
  {
    v6 = *a3;
    v30 = 0;
    if ( (*((int (__fastcall **)(HSTRING *, __int64 *))v6 + 6))(a3, &v30) >= 0 )
      (*(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 48LL))(v30, &v21);
    (*((void (__fastcall **)(HSTRING *, HSTRING *))*a3 + 7))(a3, &v19);
    (*((void (__fastcall **)(HSTRING *, HSTRING *))*a3 + 8))(a3, &v20);
    (*((void (__fastcall **)(HSTRING *, int *))*a3 + 9))(a3, &v29);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v30);
  }
  string = 0;
  v7 = 0;
  *(_QWORD *)v22 = 0;
  CallingAppName = Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppName(
                     (Windows::Internal::Security::Authentication::TokenBroker *)a2,
                     (struct IUnknown *)&string,
                     a3);
  v9 = string;
  if ( CallingAppName >= 0 )
  {
    StringRawBuffer = (struct IUnknown *)WindowsGetStringRawBuffer(string, 0);
    Windows::Internal::Security::Authentication::TokenBroker::GetCallingServiceName(
      (Windows::Internal::Security::Authentication::TokenBroker *)a2,
      StringRawBuffer,
      v22,
      v11);
    v7 = *(HSTRING *)v22;
  }
  wil::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
  v12 = TbLogProvider::Provider();
  v13 = (int)v12;
  if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL) )
  {
    LODWORD(v30) = v29;
    v23 = WindowsGetStringRawBuffer(v20, 0);
    v24 = WindowsGetStringRawBuffer(v19, 0);
    v25 = WindowsGetStringRawBuffer(v21, 0);
    v26 = WindowsGetStringRawBuffer(v7, 0);
    v14 = WindowsGetStringRawBuffer(v9, 0);
    FileNameW = PathFindFileNameW(v14);
    CurrentThreadId = GetCurrentThreadId();
    v28[0] = 0;
    v15 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v15 + 4) || _tlgGuidIsZero((const struct _GUID *)(v15 + 24)) )
      v16 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v13,
      (unsigned int)byte_1801473F9,
      v15 + 8,
      v16,
      (__int64)v28,
      (__int64)&CurrentThreadId,
      (__int64)&FileNameW,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v30);
  }
  wil::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
  if ( v7 )
    WindowsDeleteString(v7);
  if ( v9 )
    WindowsDeleteString(v9);
  if ( v19 )
    WindowsDeleteString(v19);
  if ( v20 )
    WindowsDeleteString(v20);
  if ( v21 )
    WindowsDeleteString(v21);
}

```

## disassembly

```asm
0x1800b048c  mov     r11, rsp
0x1800b048f  mov     [r11+8], rbx
0x1800b0493  push    rsi
0x1800b0494  push    rdi
0x1800b0495  push    r14
0x1800b0497  sub     rsp, 0C0h
0x1800b049e  mov     rbx, r8
0x1800b04a1  mov     rsi, rdx
0x1800b04a4  mov     r14, rcx
0x1800b04a7  mov     qword ptr [r11-58h], 0
0x1800b04af  mov     qword ptr [r11-60h], 0
0x1800b04b7  mov     qword ptr [r11-68h], 0
0x1800b04bf  mov     dword ptr [r11+18h], 0
0x1800b04c7  test    rbx, rbx
0x1800b04ca  jz      loc_1800B0558
0x1800b04d0  mov     rax, [r8]
0x1800b04d3  mov     qword ptr [r11+20h], 0
0x1800b04db  lea     rdx, [r11+20h]
0x1800b04df  mov     rcx, rbx
0x1800b04e2  mov     rax, [rax+30h]
0x1800b04e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b04eb  test    eax, eax
0x1800b04ed  js      short loc_1800B050B
0x1800b04ef  mov     rcx, [rsp+0D8h+arg_18]
0x1800b04f7  mov     rax, [rcx]
0x1800b04fa  lea     rdx, [rsp+0D8h+var_58]
0x1800b0502  mov     rax, [rax+30h]
0x1800b0506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b050b  mov     rax, [rbx]
0x1800b050e  lea     rdx, [rsp+0D8h+var_68]
0x1800b0513  mov     rcx, rbx
0x1800b0516  mov     rax, [rax+38h]
0x1800b051a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b051f  mov     rax, [rbx]
0x1800b0522  lea     rdx, [rsp+0D8h+var_60]
0x1800b0527  mov     rcx, rbx
0x1800b052a  mov     rax, [rax+40h]
0x1800b052e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0533  mov     rax, [rbx]
0x1800b0536  lea     rdx, [rsp+0D8h+arg_10]
0x1800b053e  mov     rcx, rbx
0x1800b0541  mov     rax, [rax+48h]
0x1800b0545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b054a  nop
0x1800b054b  lea     rcx, [rsp+0D8h+arg_18]
0x1800b0553  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x1800b0558  mov     [rsp+0D8h+string], 0
0x1800b0561  xor     edi, edi
0x1800b0563  mov     qword ptr [rsp+0D8h+var_50], rdi
0x1800b056b  lea     rdx, [rsp+0D8h+string]; struct IUnknown *
0x1800b0570  mov     rcx, rsi; this
0x1800b0573  call    ?GetCallingAppName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppName(IUnknown *,HSTRING__ * *)
0x1800b0578  mov     rbx, [rsp+0D8h+string]
0x1800b057d  test    eax, eax
0x1800b057f  js      short loc_1800B05A7
0x1800b0581  xor     edx, edx; length
0x1800b0583  mov     rcx, rbx; string
0x1800b0586  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b058c  lea     r8, [rsp+0D8h+var_50]; unsigned __int16 *
0x1800b0594  mov     rdx, rax; struct IUnknown *
0x1800b0597  mov     rcx, rsi; this
0x1800b059a  call    ?GetCallingServiceName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEBGPEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingServiceName(IUnknown *,ushort const *,HSTRING__ * *)
0x1800b059f  mov     rdi, qword ptr [rsp+0D8h+var_50]
0x1800b05a7  mov     rcx, r14
0x1800b05aa  call    ?zInternalStart@?$ActivityBase@VTbLogProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800b05af  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x1800b05b4  mov     rsi, rax
0x1800b05b7  mov     ecx, [rax]
0x1800b05b9  cmp     ecx, 5
0x1800b05bc  jbe     loc_1800B0709
0x1800b05c2  mov     rdx, 400000000000h
0x1800b05cc  mov     rcx, rax
0x1800b05cf  call    _tlgKeywordOn
0x1800b05d4  test    al, al
0x1800b05d6  jz      loc_1800B0709
0x1800b05dc  mov     ecx, [rsp+0D8h+arg_10]
0x1800b05e3  mov     dword ptr [rsp+0D8h+arg_18], ecx
0x1800b05ea  xor     edx, edx; length
0x1800b05ec  mov     rcx, [rsp+0D8h+var_60]; string
0x1800b05f1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b05f7  mov     [rsp+0D8h+var_48], rax
0x1800b05ff  xor     edx, edx; length
0x1800b0601  mov     rcx, [rsp+0D8h+var_68]; string
0x1800b0606  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b060c  mov     [rsp+0D8h+var_40], rax
0x1800b0614  xor     edx, edx; length
0x1800b0616  mov     rcx, [rsp+0D8h+var_58]; string
0x1800b061e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b0624  mov     [rsp+0D8h+var_38], rax
0x1800b062c  xor     edx, edx; length
0x1800b062e  mov     rcx, rdi; string
0x1800b0631  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b0637  mov     [rsp+0D8h+var_30], rax
0x1800b063f  xor     edx, edx; length
0x1800b0641  mov     rcx, rbx; string
0x1800b0644  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b064a  mov     rcx, rax; pszPath
0x1800b064d  call    cs:__imp_PathFindFileNameW
0x1800b0653  mov     [rsp+0D8h+var_28], rax
0x1800b065b  call    cs:__imp_GetCurrentThreadId
0x1800b0661  mov     [rsp+0D8h+var_78], eax
0x1800b0665  mov     [rsp+0D8h+var_20], 0
0x1800b0671  mov     r8, [r14+110h]
0x1800b0678  cmp     byte ptr [r8+4], 0
0x1800b067d  jz      short loc_1800B068C
0x1800b067f  lea     rcx, [r8+18h]; struct _GUID *
0x1800b0683  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800b0688  test    al, al
0x1800b068a  jz      short loc_1800B068E
0x1800b068c  xor     ecx, ecx
0x1800b068e  add     r8, 8
0x1800b0692  lea     rax, [rsp+0D8h+arg_18]
0x1800b069a  mov     [rsp+0D8h+var_80], rax
0x1800b069f  lea     rax, [rsp+0D8h+var_48]
0x1800b06a7  mov     [rsp+0D8h+var_88], rax
0x1800b06ac  lea     rax, [rsp+0D8h+var_40]
0x1800b06b4  mov     [rsp+0D8h+var_90], rax
0x1800b06b9  lea     rax, [rsp+0D8h+var_38]
0x1800b06c1  mov     [rsp+0D8h+var_98], rax
0x1800b06c6  lea     rax, [rsp+0D8h+var_30]
0x1800b06ce  mov     [rsp+0D8h+var_A0], rax
0x1800b06d3  lea     rax, [rsp+0D8h+var_28]
0x1800b06db  mov     [rsp+0D8h+var_A8], rax
0x1800b06e0  lea     rax, [rsp+0D8h+var_78]
0x1800b06e5  mov     [rsp+0D8h+var_B0], rax
0x1800b06ea  lea     rax, [rsp+0D8h+var_20]
0x1800b06f2  mov     [rsp+0D8h+var_B8], rax
0x1800b06f7  mov     r9, rcx
0x1800b06fa  lea     rdx, byte_1801473F9
0x1800b0701  mov     rcx, rsi
0x1800b0704  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U3@U3@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@55554@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800b0709  mov     rcx, r14
0x1800b070c  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTbLogProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800b0711  nop
0x1800b0712  test    rdi, rdi
0x1800b0715  jz      short loc_1800B0721
0x1800b0717  mov     rcx, rdi; string
0x1800b071a  call    cs:__imp_WindowsDeleteString
0x1800b0720  nop
0x1800b0721  test    rbx, rbx
0x1800b0724  jz      short loc_1800B0730
0x1800b0726  mov     rcx, rbx; string
0x1800b0729  call    cs:__imp_WindowsDeleteString
0x1800b072f  nop
0x1800b0730  mov     rcx, [rsp+0D8h+var_68]; string
0x1800b0735  test    rcx, rcx
0x1800b0738  jz      short loc_1800B0741
0x1800b073a  call    cs:__imp_WindowsDeleteString
0x1800b0740  nop
0x1800b0741  mov     rcx, [rsp+0D8h+var_60]; string
0x1800b0746  test    rcx, rcx
0x1800b0749  jz      short loc_1800B0752
0x1800b074b  call    cs:__imp_WindowsDeleteString
0x1800b0751  nop
0x1800b0752  mov     rcx, [rsp+0D8h+var_58]; string
0x1800b075a  test    rcx, rcx
0x1800b075d  jz      short loc_1800B0766
0x1800b075f  call    cs:__imp_WindowsDeleteString
0x1800b0765  nop
0x1800b0766  mov     rbx, [rsp+0D8h+arg_0]
0x1800b076e  add     rsp, 0C0h
0x1800b0775  pop     r14
0x1800b0777  pop     rdi
0x1800b0778  pop     rsi
0x1800b0779  retn
```
