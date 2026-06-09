# TbLogProvider::UpdateWebAccountPictureAsync::StartActivity(IUnknown *,Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ *)

- ea: `0x1800c42c8`
- end: `0x1800c44aa`
- name: `?StartActivity@UpdateWebAccountPictureAsync@TbLogProvider@@QEAAXPEAUIUnknown@@PEAUIWebAccountProvider@Credentials@Security@Windows@@PEAUHSTRING__@@@Z`
- size: `482`
- prototype: `void(TbLogProvider::UpdateWebAccountPictureAsync *__hidden this, struct IUnknown *, struct Windows::Security::Credentials::IWebAccountProvider *, HSTRING)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18008c7d0`

## callees

- `0x180003bb8`
- `0x18000ac90`
- `0x18000f3f4`
- `0x1800455a4`
- `0x180063fc4`
- `0x18007f528`
- `0x1800a939c`
- `0x1800b406c`
- `0x1800c42c8`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c43d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c43d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4310`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4387`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4397`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c43b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c43c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4310`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4387`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4397`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c43b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c43c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4474`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4483`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4492`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4474`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4483`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4492`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800c43a0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800c43a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall TbLogProvider::UpdateWebAccountPictureAsync::StartActivity(
        TbLogProvider::UpdateWebAccountPictureAsync *this,
        struct IUnknown *a2,
        HSTRING *a3,
        HSTRING a4)
{
  HSTRING v8; // rdi
  int CallingAppName; // eax
  HSTRING v10; // rbx
  struct IUnknown *StringRawBuffer; // rax
  HSTRING *v12; // r9
  const struct _tlgProvider_t *v13; // rax
  int v14; // esi
  const WCHAR *v15; // rax
  __int64 v16; // r8
  int v17; // ecx
  DWORD CurrentThreadId; // [rsp+50h] [rbp-88h] BYREF
  HSTRING string; // [rsp+58h] [rbp-80h] BYREF
  HSTRING v20; // [rsp+60h] [rbp-78h] BYREF
  unsigned __int16 v21[4]; // [rsp+68h] [rbp-70h] BYREF
  PCWSTR v22; // [rsp+70h] [rbp-68h] BYREF
  LPWSTR FileNameW; // [rsp+78h] [rbp-60h] BYREF
  PCWSTR v24; // [rsp+80h] [rbp-58h] BYREF
  PCWSTR v25; // [rsp+88h] [rbp-50h] BYREF
  __int64 v26[9]; // [rsp+90h] [rbp-48h] BYREF

  string = 0;
  v8 = 0;
  *(_QWORD *)v21 = 0;
  try
  {
    CallingAppName = Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppName(
                       (Windows::Internal::Security::Authentication::TokenBroker *)a2,
                       (struct IUnknown *)&string,
                       a3);
    v10 = string;
    if ( CallingAppName >= 0 )
    {
      StringRawBuffer = (struct IUnknown *)WindowsGetStringRawBuffer(string, 0);
      Windows::Internal::Security::Authentication::TokenBroker::GetCallingServiceName(
        (Windows::Internal::Security::Authentication::TokenBroker *)a2,
        StringRawBuffer,
        v21,
        v12);
      v8 = *(HSTRING *)v21;
    }
    v20 = 0;
    if ( a3 )
      (*((void (__fastcall **)(HSTRING *, HSTRING *))*a3 + 6))(a3, &v20);
    wil::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
    v13 = TbLogProvider::Provider();
    v14 = (int)v13;
    if ( *(_DWORD *)v13 > 5u && (unsigned __int8)tlgKeywordOn(v13, 0x400000000000LL) )
    {
      v22 = WindowsGetStringRawBuffer(v8, 0);
      v15 = WindowsGetStringRawBuffer(v10, 0);
      FileNameW = PathFindFileNameW(v15);
      v24 = WindowsGetStringRawBuffer(a4, 0);
      v25 = WindowsGetStringRawBuffer(v20, 0);
      CurrentThreadId = GetCurrentThreadId();
      v26[0] = 0x1000000;
      v16 = *((_QWORD *)this + 34);
      if ( !*(_BYTE *)(v16 + 4) || _tlgGuidIsZero((const struct _GUID *)(v16 + 24)) )
        v17 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v14,
        (unsigned int)word_18014CEB2,
        v16 + 8,
        v17,
        (__int64)v26,
        (__int64)&CurrentThreadId,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&FileNameW,
        (__int64)&v22);
    }
    wil::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
    if ( v20 )
      WindowsDeleteString(v20);
    if ( v8 )
      WindowsDeleteString(v8);
    if ( v10 )
      WindowsDeleteString(v10);
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x1800c42c8  push    rbx
0x1800c42ca  push    rsi
0x1800c42cb  push    rdi
0x1800c42cc  push    r12
0x1800c42ce  push    r14
0x1800c42d0  push    r15
0x1800c42d2  sub     rsp, 0A8h
0x1800c42d9  mov     r12, r9
0x1800c42dc  mov     rsi, r8
0x1800c42df  mov     r15, rdx
0x1800c42e2  mov     r14, rcx
0x1800c42e5  mov     [rsp+0D8h+string], 0
0x1800c42ee  xor     edi, edi
0x1800c42f0  mov     qword ptr [rsp+0D8h+var_70], rdi
0x1800c42f5  lea     rdx, [rsp+0D8h+string]; struct IUnknown *
0x1800c42fa  mov     rcx, r15; this
0x1800c42fd  call    ?GetCallingAppName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppName(IUnknown *,HSTRING__ * *)
0x1800c4302  mov     rbx, [rsp+0D8h+string]
0x1800c4307  test    eax, eax
0x1800c4309  js      short loc_1800C432B
0x1800c430b  xor     edx, edx; length
0x1800c430d  mov     rcx, rbx; string
0x1800c4310  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c4316  lea     r8, [rsp+0D8h+var_70]; unsigned __int16 *
0x1800c431b  mov     rdx, rax; struct IUnknown *
0x1800c431e  mov     rcx, r15; this
0x1800c4321  call    ?GetCallingServiceName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEBGPEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingServiceName(IUnknown *,ushort const *,HSTRING__ * *)
0x1800c4326  mov     rdi, qword ptr [rsp+0D8h+var_70]
0x1800c432b  mov     [rsp+0D8h+var_78], 0
0x1800c4334  test    rsi, rsi
0x1800c4337  jz      short loc_1800C434D
0x1800c4339  mov     rax, [rsi]
0x1800c433c  lea     rdx, [rsp+0D8h+var_78]
0x1800c4341  mov     rcx, rsi
0x1800c4344  mov     rax, [rax+30h]
0x1800c4348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c434d  mov     rcx, r14
0x1800c4350  call    ?zInternalStart@?$ActivityBase@VTbLogProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800c4355  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x1800c435a  mov     rsi, rax
0x1800c435d  mov     ecx, [rax]
0x1800c435f  cmp     ecx, 5
0x1800c4362  jbe     loc_1800C4461
0x1800c4368  mov     rdx, 400000000000h
0x1800c4372  mov     rcx, rax
0x1800c4375  call    _tlgKeywordOn
0x1800c437a  test    al, al
0x1800c437c  jz      loc_1800C4461
0x1800c4382  xor     edx, edx; length
0x1800c4384  mov     rcx, rdi; string
0x1800c4387  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c438d  mov     [rsp+0D8h+var_68], rax
0x1800c4392  xor     edx, edx; length
0x1800c4394  mov     rcx, rbx; string
0x1800c4397  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c439d  mov     rcx, rax; pszPath
0x1800c43a0  call    cs:__imp_PathFindFileNameW
0x1800c43a6  mov     [rsp+0D8h+var_60], rax
0x1800c43ab  xor     edx, edx; length
0x1800c43ad  mov     rcx, r12; string
0x1800c43b0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c43b6  mov     [rsp+0D8h+var_58], rax
0x1800c43be  xor     edx, edx; length
0x1800c43c0  mov     rcx, [rsp+0D8h+var_78]; string
0x1800c43c5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c43cb  mov     [rsp+0D8h+var_50], rax
0x1800c43d3  call    cs:__imp_GetCurrentThreadId
0x1800c43d9  mov     [rsp+0D8h+var_88], eax
0x1800c43dd  mov     [rsp+0D8h+var_48], 1000000h
0x1800c43e9  mov     r8, [r14+110h]
0x1800c43f0  cmp     byte ptr [r8+4], 0
0x1800c43f5  jz      short loc_1800C4404
0x1800c43f7  lea     rcx, [r8+18h]; struct _GUID *
0x1800c43fb  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800c4400  test    al, al
0x1800c4402  jz      short loc_1800C4406
0x1800c4404  xor     ecx, ecx
0x1800c4406  add     r8, 8
0x1800c440a  lea     rax, [rsp+0D8h+var_68]
0x1800c440f  mov     [rsp+0D8h+var_90], rax
0x1800c4414  lea     rax, [rsp+0D8h+var_60]
0x1800c4419  mov     [rsp+0D8h+var_98], rax
0x1800c441e  lea     rax, [rsp+0D8h+var_58]
0x1800c4426  mov     [rsp+0D8h+var_A0], rax
0x1800c442b  lea     rax, [rsp+0D8h+var_50]
0x1800c4433  mov     [rsp+0D8h+var_A8], rax
0x1800c4438  lea     rax, [rsp+0D8h+var_88]
0x1800c443d  mov     [rsp+0D8h+var_B0], rax
0x1800c4442  lea     rax, [rsp+0D8h+var_48]
0x1800c444a  mov     [rsp+0D8h+var_B8], rax
0x1800c444f  mov     r9, rcx
0x1800c4452  lea     rdx, word_18014CEB2
0x1800c4459  mov     rcx, rsi
0x1800c445c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800c4461  mov     rcx, r14
0x1800c4464  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTbLogProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800c4469  nop
0x1800c446a  mov     rcx, [rsp+0D8h+var_78]; string
0x1800c446f  test    rcx, rcx
0x1800c4472  jz      short loc_1800C447B
0x1800c4474  call    cs:__imp_WindowsDeleteString
0x1800c447a  nop
0x1800c447b  test    rdi, rdi
0x1800c447e  jz      short loc_1800C448A
0x1800c4480  mov     rcx, rdi; string
0x1800c4483  call    cs:__imp_WindowsDeleteString
0x1800c4489  nop
0x1800c448a  test    rbx, rbx
0x1800c448d  jz      short loc_1800C4499
0x1800c448f  mov     rcx, rbx; string
0x1800c4492  call    cs:__imp_WindowsDeleteString
0x1800c4498  nop
0x1800c4499  add     rsp, 0A8h
0x1800c44a0  pop     r15
0x1800c44a2  pop     r14
0x1800c44a4  pop     r12
0x1800c44a6  pop     rdi
0x1800c44a7  pop     rsi
0x1800c44a8  pop     rbx
0x1800c44a9  retn
```
