# TbLogProvider::GetTokenForVailContainer::StartActivity(IUnknown *,Windows::Security::Authentication::Web::Core::IWebTokenRequest *)

- ea: `0x1800aff38`
- end: `0x1800b0226`
- name: `?StartActivity@GetTokenForVailContainer@TbLogProvider@@QEAAXPEAUIUnknown@@PEAUIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@Z`
- size: `750`
- prototype: `void(TbLogProvider::GetTokenForVailContainer *__hidden this, struct IUnknown *, struct Windows::Security::Authentication::Web::Core::IWebTokenRequest *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008d0b0`

## callees

- `0x180002fb4`
- `0x18000ac90`
- `0x18000f3f4`
- `0x18000fcf8`
- `0x1800455a4`
- `0x180063fc4`
- `0x18007f528`
- `0x1800a939c`
- `0x1800aff38`
- `0x1800b406c`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b0107`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b0107`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b0032`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b009d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b00b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b00ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b00dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b00f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b0032`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b009d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b00b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b00ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b00dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b00f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b01c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b01d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b01e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b01f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b020b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b01c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b01d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b01e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b01f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b020b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800b00f9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800b00f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall TbLogProvider::GetTokenForVailContainer::StartActivity(
        TbLogProvider::GetTokenForVailContainer *this,
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
  __int64 v28[4]; // [rsp+B8h] [rbp-20h] BYREF
  int v29; // [rsp+F0h] [rbp+18h] BYREF
  __int64 v30; // [rsp+F8h] [rbp+20h] BYREF

  try
  {
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
      v28[0] = 0x1000000;
      v15 = *((_QWORD *)this + 34);
      if ( !*(_BYTE *)(v15 + 4) || _tlgGuidIsZero((const struct _GUID *)(v15 + 24)) )
        v16 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)byte_1801471BB,
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
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x1800aff38  mov     r11, rsp
0x1800aff3b  mov     [r11+8], rbx
0x1800aff3f  push    rsi
0x1800aff40  push    rdi
0x1800aff41  push    r14
0x1800aff43  sub     rsp, 0C0h
0x1800aff4a  mov     rbx, r8
0x1800aff4d  mov     rsi, rdx
0x1800aff50  mov     r14, rcx
0x1800aff53  mov     qword ptr [r11-58h], 0
0x1800aff5b  mov     qword ptr [r11-60h], 0
0x1800aff63  mov     qword ptr [r11-68h], 0
0x1800aff6b  mov     dword ptr [r11+18h], 0
0x1800aff73  test    rbx, rbx
0x1800aff76  jz      loc_1800B0004
0x1800aff7c  mov     rax, [r8]
0x1800aff7f  mov     qword ptr [r11+20h], 0
0x1800aff87  lea     rdx, [r11+20h]
0x1800aff8b  mov     rcx, rbx
0x1800aff8e  mov     rax, [rax+30h]
0x1800aff92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aff97  test    eax, eax
0x1800aff99  js      short loc_1800AFFB7
0x1800aff9b  mov     rcx, [rsp+0D8h+arg_18]
0x1800affa3  mov     rax, [rcx]
0x1800affa6  lea     rdx, [rsp+0D8h+var_58]
0x1800affae  mov     rax, [rax+30h]
0x1800affb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800affb7  mov     rax, [rbx]
0x1800affba  lea     rdx, [rsp+0D8h+var_68]
0x1800affbf  mov     rcx, rbx
0x1800affc2  mov     rax, [rax+38h]
0x1800affc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800affcb  mov     rax, [rbx]
0x1800affce  lea     rdx, [rsp+0D8h+var_60]
0x1800affd3  mov     rcx, rbx
0x1800affd6  mov     rax, [rax+40h]
0x1800affda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800affdf  mov     rax, [rbx]
0x1800affe2  lea     rdx, [rsp+0D8h+arg_10]
0x1800affea  mov     rcx, rbx
0x1800affed  mov     rax, [rax+48h]
0x1800afff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afff6  nop
0x1800afff7  lea     rcx, [rsp+0D8h+arg_18]
0x1800affff  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x1800b0004  mov     [rsp+0D8h+string], 0
0x1800b000d  xor     edi, edi
0x1800b000f  mov     qword ptr [rsp+0D8h+var_50], rdi
0x1800b0017  lea     rdx, [rsp+0D8h+string]; struct IUnknown *
0x1800b001c  mov     rcx, rsi; this
0x1800b001f  call    ?GetCallingAppName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppName(IUnknown *,HSTRING__ * *)
0x1800b0024  mov     rbx, [rsp+0D8h+string]
0x1800b0029  test    eax, eax
0x1800b002b  js      short loc_1800B0053
0x1800b002d  xor     edx, edx; length
0x1800b002f  mov     rcx, rbx; string
0x1800b0032  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b0038  lea     r8, [rsp+0D8h+var_50]; unsigned __int16 *
0x1800b0040  mov     rdx, rax; struct IUnknown *
0x1800b0043  mov     rcx, rsi; this
0x1800b0046  call    ?GetCallingServiceName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEBGPEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingServiceName(IUnknown *,ushort const *,HSTRING__ * *)
0x1800b004b  mov     rdi, qword ptr [rsp+0D8h+var_50]
0x1800b0053  mov     rcx, r14
0x1800b0056  call    ?zInternalStart@?$ActivityBase@VTbLogProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800b005b  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x1800b0060  mov     rsi, rax
0x1800b0063  mov     ecx, [rax]
0x1800b0065  cmp     ecx, 5
0x1800b0068  jbe     loc_1800B01B5
0x1800b006e  mov     rdx, 400000000000h
0x1800b0078  mov     rcx, rax
0x1800b007b  call    _tlgKeywordOn
0x1800b0080  test    al, al
0x1800b0082  jz      loc_1800B01B5
0x1800b0088  mov     ecx, [rsp+0D8h+arg_10]
0x1800b008f  mov     dword ptr [rsp+0D8h+arg_18], ecx
0x1800b0096  xor     edx, edx; length
0x1800b0098  mov     rcx, [rsp+0D8h+var_60]; string
0x1800b009d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b00a3  mov     [rsp+0D8h+var_48], rax
0x1800b00ab  xor     edx, edx; length
0x1800b00ad  mov     rcx, [rsp+0D8h+var_68]; string
0x1800b00b2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b00b8  mov     [rsp+0D8h+var_40], rax
0x1800b00c0  xor     edx, edx; length
0x1800b00c2  mov     rcx, [rsp+0D8h+var_58]; string
0x1800b00ca  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b00d0  mov     [rsp+0D8h+var_38], rax
0x1800b00d8  xor     edx, edx; length
0x1800b00da  mov     rcx, rdi; string
0x1800b00dd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b00e3  mov     [rsp+0D8h+var_30], rax
0x1800b00eb  xor     edx, edx; length
0x1800b00ed  mov     rcx, rbx; string
0x1800b00f0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b00f6  mov     rcx, rax; pszPath
0x1800b00f9  call    cs:__imp_PathFindFileNameW
0x1800b00ff  mov     [rsp+0D8h+var_28], rax
0x1800b0107  call    cs:__imp_GetCurrentThreadId
0x1800b010d  mov     [rsp+0D8h+var_78], eax
0x1800b0111  mov     [rsp+0D8h+var_20], 1000000h
0x1800b011d  mov     r8, [r14+110h]
0x1800b0124  cmp     byte ptr [r8+4], 0
0x1800b0129  jz      short loc_1800B0138
0x1800b012b  lea     rcx, [r8+18h]; struct _GUID *
0x1800b012f  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800b0134  test    al, al
0x1800b0136  jz      short loc_1800B013A
0x1800b0138  xor     ecx, ecx
0x1800b013a  add     r8, 8
0x1800b013e  lea     rax, [rsp+0D8h+arg_18]
0x1800b0146  mov     [rsp+0D8h+var_80], rax
0x1800b014b  lea     rax, [rsp+0D8h+var_48]
0x1800b0153  mov     [rsp+0D8h+var_88], rax
0x1800b0158  lea     rax, [rsp+0D8h+var_40]
0x1800b0160  mov     [rsp+0D8h+var_90], rax
0x1800b0165  lea     rax, [rsp+0D8h+var_38]
0x1800b016d  mov     [rsp+0D8h+var_98], rax
0x1800b0172  lea     rax, [rsp+0D8h+var_30]
0x1800b017a  mov     [rsp+0D8h+var_A0], rax
0x1800b017f  lea     rax, [rsp+0D8h+var_28]
0x1800b0187  mov     [rsp+0D8h+var_A8], rax
0x1800b018c  lea     rax, [rsp+0D8h+var_78]
0x1800b0191  mov     [rsp+0D8h+var_B0], rax
0x1800b0196  lea     rax, [rsp+0D8h+var_20]
0x1800b019e  mov     [rsp+0D8h+var_B8], rax
0x1800b01a3  mov     r9, rcx
0x1800b01a6  lea     rdx, byte_1801471BB
0x1800b01ad  mov     rcx, rsi
0x1800b01b0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U3@U3@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@55554@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800b01b5  mov     rcx, r14
0x1800b01b8  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTbLogProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800b01bd  nop
0x1800b01be  test    rdi, rdi
0x1800b01c1  jz      short loc_1800B01CD
0x1800b01c3  mov     rcx, rdi; string
0x1800b01c6  call    cs:__imp_WindowsDeleteString
0x1800b01cc  nop
0x1800b01cd  test    rbx, rbx
0x1800b01d0  jz      short loc_1800B01DC
0x1800b01d2  mov     rcx, rbx; string
0x1800b01d5  call    cs:__imp_WindowsDeleteString
0x1800b01db  nop
0x1800b01dc  mov     rcx, [rsp+0D8h+var_68]; string
0x1800b01e1  test    rcx, rcx
0x1800b01e4  jz      short loc_1800B01ED
0x1800b01e6  call    cs:__imp_WindowsDeleteString
0x1800b01ec  nop
0x1800b01ed  mov     rcx, [rsp+0D8h+var_60]; string
0x1800b01f2  test    rcx, rcx
0x1800b01f5  jz      short loc_1800B01FE
0x1800b01f7  call    cs:__imp_WindowsDeleteString
0x1800b01fd  nop
0x1800b01fe  mov     rcx, [rsp+0D8h+var_58]; string
0x1800b0206  test    rcx, rcx
0x1800b0209  jz      short loc_1800B0212
0x1800b020b  call    cs:__imp_WindowsDeleteString
0x1800b0211  nop
0x1800b0212  mov     rbx, [rsp+0D8h+arg_0]
0x1800b021a  add     rsp, 0C0h
0x1800b0221  pop     r14
0x1800b0223  pop     rdi
0x1800b0224  pop     rsi
0x1800b0225  retn
```
