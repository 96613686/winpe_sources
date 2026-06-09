# Windows::Internal::Security::Authentication::Web::CTokenBrokerInternal::OnSystemEvent(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Storage::Streams::IBuffer *)

- ea: `0x180055574`
- end: `0x180055a28`
- name: `?OnSystemEvent@CTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@AEAAJPEAUITokenBrokerListenerInternal@23456@PEAUIBuffer@Streams@Storage@6@@Z`
- size: `1204`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::Web::CTokenBrokerInternal *__hidden this, struct Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *, struct Windows::Storage::Streams::IBuffer *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800554e0`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180023a80`
- `0x1800280b0`
- `0x18002ea84`
- `0x18003d810`
- `0x180042874`
- `0x180045a04`
- `0x180046a94`
- `0x180049ae4`
- `0x18004fdbc`
- `0x180055574`
- `0x18008e690`
- `0x1800c8bf0`
- `0x1800c8c64`
- `0x1800c8cd8`
- `0x1800c8d5c`
- `0x1800c8de0`
- `0x1800c8e54`
- `0x1800c8ec8`
- `0x1800ca2fc`
- `0x180113f50`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055718`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055739`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055755`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055718`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055739`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180055755`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055979`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055988`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055997`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055979`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055988`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055997`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800556fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180055725`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180055746`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800556fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180055725`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180055746`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800559a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800559a9`

## string_xrefs

- `0x18005560d`: `onecore\ds\security\tokenbroker\broker\lib\events.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CTokenBrokerInternal::OnSystemEvent(
        Windows::Internal::Security::Authentication::Web::CTokenBrokerInternal *this,
        struct Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *a2,
        struct Windows::Storage::Streams::IBuffer *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // r14d
  rsize_t v9; // r8
  __int64 v10; // rcx
  _BYTE *v11; // rax
  HSTRING v12; // rdi
  HSTRING v13; // rbx
  HSTRING v14; // rsi
  PCWSTR v15; // r14
  PCWSTR StringRawBuffer; // rax
  PCWSTR v17; // rax
  int v18; // r8d
  int v19; // r9d
  int v20; // eax
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  int v24; // [rsp+20h] [rbp-E0h]
  rsize_t SourceSize; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v27; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v28; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string2; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+68h] [rbp-98h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  char v32; // [rsp+78h] [rbp-88h]
  PCWSTR v33; // [rsp+80h] [rbp-80h] BYREF
  PCWSTR v34; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v35[1024]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v36; // [rsp+1090h] [rbp+F90h] BYREF
  __int64 v37; // [rsp+10A0h] [rbp+FA0h] BYREF
  _BYTE v38[24]; // [rsp+10A8h] [rbp+FA8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+10F8h] [rbp+FF8h]

  if ( (unsigned int)dword_180175000 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      &byte_18014ED1F,
      0,
      0);
  if ( !a3 )
    return 0;
  TokenHandle = 0;
  v32 = 0;
  v5 = Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(
         &TokenHandle,
         *((_QWORD *)this + 51));
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C0,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\events.cpp",
      (const char *)(unsigned int)v5,
      v24);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    return v6;
  }
  hMem = 0;
  LODWORD(SourceSize) = 0;
  v8 = Windows::Internal::Security::CPropertiesSerializer::BufferToBytes(
         a3,
         (unsigned __int8 **)&hMem,
         (unsigned int *)&SourceSize);
  if ( v8 >= 0 )
  {
    v9 = (unsigned int)SourceSize;
    if ( (_DWORD)SourceSize )
    {
      v36 = 0;
      v37 = 0;
      v10 = 4096;
      v11 = v35;
      do
      {
        *v11++ = 0;
        --v10;
      }
      while ( v10 );
      Windows::Internal::Security::Authentication::Web::SystemEventData::Initialize(
        (Windows::Internal::Security::Authentication::Web::SystemEventData *)v35,
        (union Windows::Internal::Security::Authentication::Web::SystemEventData::SystemEventDataPayload *)hMem,
        v9);
      v28 = 0;
      string2 = 0;
      string = 0;
      Windows::Internal::String::Initialize<unsigned short const *>(&v28, &v37);
      Windows::Internal::String::Initialize<unsigned short const *>(&string2, (char *)&v36 + 8);
      Windows::Internal::String::Initialize<unsigned short const *>(&string, v38);
      v12 = v28;
      v13 = string2;
      v14 = string;
      if ( (unsigned int)dword_180175000 > 5 )
      {
        v15 = L"null";
        if ( WindowsIsStringEmpty(string) )
          StringRawBuffer = L"null";
        else
          StringRawBuffer = WindowsGetStringRawBuffer(v14, 0);
        v33 = StringRawBuffer;
        if ( WindowsIsStringEmpty(v13) )
          v17 = L"null";
        else
          v17 = WindowsGetStringRawBuffer(v13, 0);
        v34 = v17;
        if ( !WindowsIsStringEmpty(v12) )
          v15 = WindowsGetStringRawBuffer(v12, 0);
        v27 = v15;
        LODWORD(SourceSize) = v35[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (unsigned int)&dword_180175000,
          (unsigned int)word_18014ECAA,
          v18,
          v19,
          (__int64)&SourceSize,
          (__int64)&v27,
          (__int64)&v34,
          (__int64)&v33);
      }
      if ( v35[0] == 1 )
      {
        SourceSize = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&SourceSize);
        v8 = InitializeProviderFromIdOnly(
               *((_QWORD *)this + 51),
               v13,
               (struct Windows::Security::Credentials::IWebAccountProvider **)&SourceSize);
        if ( v8 >= 0 )
          v8 = Windows::Internal::Security::Authentication::Web::CTokenBrokerInternal::SendEventInternalHardened<Windows::Internal::Security::Authentication::Web::CWebAccountProviderAddedEventArgs,Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountProviderAddedEventArgs *>,Windows::Security::Credentials::IWebAccountProvider *>(
                 this,
                 (char *)this + 328,
                 SourceSize);
      }
      else if ( v35[0] == 2 )
      {
        SourceSize = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&SourceSize);
        v8 = InitializeProviderFromIdOnly(
               *((_QWORD *)this + 51),
               v13,
               (struct Windows::Security::Credentials::IWebAccountProvider **)&SourceSize);
        if ( v8 >= 0 )
          v8 = Windows::Internal::Security::Authentication::Web::CTokenBrokerInternal::SendEventInternalHardened<Windows::Internal::Security::Authentication::Web::CWebAccountProviderChangedEventArgs,Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountProviderChangedEventArgs *>,Windows::Security::Credentials::IWebAccountProvider *>(
                 this,
                 (char *)this + 352,
                 SourceSize);
      }
      else
      {
        if ( v35[0] == 3 )
        {
          v20 = Windows::Internal::Security::Authentication::Web::CTokenBrokerInternal::SendEventInternalHardened<Windows::Internal::Security::Authentication::Web::CWebAccountProviderDeletedEventArgs,Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountProviderDeletedEventArgs *>,HSTRING__ *>(
                  this,
                  (char *)this + 376,
                  v13);
          goto LABEL_30;
        }
        if ( v35[0] == 4 )
        {
          SourceSize = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&SourceSize);
          v8 = InitializeAccountFromEventData(
                 *((_QWORD *)this + 51),
                 v12,
                 v13,
                 v14,
                 (struct Windows::Security::Credentials::IWebAccount **)&SourceSize);
          if ( v8 >= 0 )
            v8 = Windows::Internal::Security::Authentication::Web::CTokenBrokerInternal::SendEventInternalHardened<Windows::Internal::Security::Authentication::Web::CWebAccountAddedEventArgs,Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountAddedEventArgs *>,Windows::Security::Credentials::IWebAccount *>(
                   this,
                   (char *)this + 232,
                   SourceSize);
        }
        else
        {
          if ( v35[0] != 5 )
          {
            if ( v35[0] == 7 )
            {
              v20 = Windows::Internal::Security::Authentication::Web::CTokenBrokerInternal::SendEventInternalHardened<Windows::Internal::Security::Authentication::Web::CWebAccountDeletedEventArgs,Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletedEventArgs *>,HSTRING__ *,HSTRING__ *,HSTRING__ *>(
                      (_DWORD)this,
                      (int)this + 280,
                      (_DWORD)v12,
                      (_DWORD)v13,
                      (char)v14);
            }
            else
            {
              if ( v35[0] != 8 )
              {
                v8 = -2147024809;
LABEL_44:
                if ( v14 )
                  WindowsDeleteString(v14);
                if ( v13 )
                  WindowsDeleteString(v13);
                if ( v12 )
                  WindowsDeleteString(v12);
                goto LABEL_50;
              }
              v20 = Windows::Internal::Security::Authentication::Web::CTokenBrokerInternal::SendEventInternalHardened<Windows::Internal::Security::Authentication::Web::CWebAccountDeletePendingEventArgs,Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *>,HSTRING__ *,HSTRING__ *,HSTRING__ *>(
                      (_DWORD)this,
                      (int)this + 304,
                      (_DWORD)v12,
                      (_DWORD)v13,
                      (char)v14);
            }
LABEL_30:
            v8 = v20;
            goto LABEL_44;
          }
          SourceSize = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&SourceSize);
          v8 = InitializeAccountFromEventData(
                 *((_QWORD *)this + 51),
                 v12,
                 v13,
                 v14,
                 (struct Windows::Security::Credentials::IWebAccount **)&SourceSize);
          if ( v8 >= 0 )
            v8 = Windows::Internal::Security::Authentication::Web::CTokenBrokerInternal::SendEventInternalHardened<Windows::Internal::Security::Authentication::Web::CWebAccountChangedEventArgs,Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountChangedEventArgs *>,Windows::Security::Credentials::IWebAccount *>(
                   this,
                   (char *)this + 256,
                   SourceSize);
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&SourceSize);
      goto LABEL_44;
    }
  }
LABEL_50:
  if ( hMem )
    LocalFree(hMem);
  Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
  if ( v8 < 0 && (unsigned int)dword_180175000 > 2 )
  {
    v27 = L"Can't invoke event handlers";
    LODWORD(SourceSize) = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v21,
      (unsigned int)&dword_18014EC5C,
      v22,
      v23,
      (__int64)&SourceSize,
      (__int64)&v27);
  }
  return 0;
}

```

## disassembly

```asm
0x180055574  mov     [rsp-8+arg_8], rbx
0x180055579  mov     [rsp-8+arg_18], rsi
0x18005557e  push    rbp
0x18005557f  push    rdi
0x180055580  push    r13
0x180055582  push    r14
0x180055584  push    r15
0x180055586  lea     rbp, [rsp-0FD0h]
0x18005558e  mov     eax, 10D0h
0x180055593  call    _alloca_probe
0x180055598  sub     rsp, rax
0x18005559b  mov     rax, cs:__security_cookie
0x1800555a2  xor     rax, rsp
0x1800555a5  mov     [rbp+0FF0h+var_30], rax
0x1800555ac  mov     rdi, r8
0x1800555af  mov     r15, rcx
0x1800555b2  mov     eax, cs:dword_180175000
0x1800555b8  cmp     eax, 4
0x1800555bb  jbe     short loc_1800555D6
0x1800555bd  xor     r9d, r9d
0x1800555c0  xor     r8d, r8d
0x1800555c3  lea     rdx, byte_18014ED1F
0x1800555ca  lea     rcx, dword_180175000
0x1800555d1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800555d6  xor     r13d, r13d
0x1800555d9  test    rdi, rdi
0x1800555dc  jz      loc_1800559FB
0x1800555e2  mov     [rsp+10F0h+TokenHandle], r13
0x1800555e7  mov     [rsp+10F0h+var_1078], r13b
0x1800555ec  mov     rdx, [r15+198h]; unsigned __int64
0x1800555f3  lea     rcx, [rsp+10F0h+TokenHandle]; TokenHandle
0x1800555f8  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)
0x1800555fd  mov     ebx, eax
0x1800555ff  test    eax, eax
0x180055601  jns     short loc_180055630
0x180055603  mov     rcx, [rbp+0FF8h]; this
0x18005560a  mov     r9d, eax; char *
0x18005560d  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180055614  mov     edx, 3C0h; void *
0x180055619  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005561e  nop
0x18005561f  lea     rcx, [rsp+10F0h+TokenHandle]; this
0x180055624  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x180055629  mov     eax, ebx
0x18005562b  jmp     loc_1800559FD
0x180055630  mov     [rsp+10F0h+hMem], r13
0x180055635  mov     dword ptr [rsp+10F0h+SourceSize], r13d
0x18005563a  lea     r8, [rsp+10F0h+SourceSize]; unsigned int *
0x18005563f  lea     rdx, [rsp+10F0h+hMem]; unsigned __int8 **
0x180055644  mov     rcx, rdi; struct Windows::Storage::Streams::IBuffer *
0x180055647  call    ?BufferToBytes@CPropertiesSerializer@Security@Internal@Windows@@SAJPEAUIBuffer@Streams@Storage@4@PEAPEAEPEAK@Z; Windows::Internal::Security::CPropertiesSerializer::BufferToBytes(Windows::Storage::Streams::IBuffer *,uchar * *,ulong *)
0x18005564c  mov     r14d, eax
0x18005564f  test    eax, eax
0x180055651  js      loc_18005599D
0x180055657  mov     r8d, dword ptr [rsp+10F0h+SourceSize]; SourceSize
0x18005565c  test    r8d, r8d
0x18005565f  jz      loc_18005599D
0x180055665  xorps   xmm0, xmm0
0x180055668  movdqa  [rbp+0FF0h+var_60], xmm0
0x180055670  mov     [rbp+0FF0h+var_50], r13
0x180055677  mov     ecx, 1000h
0x18005567c  lea     rax, [rbp+0FF0h+var_1060]
0x180055680  mov     [rax], r13b
0x180055683  inc     rax
0x180055686  sub     rcx, 1
0x18005568a  jnz     short loc_180055680
0x18005568c  mov     rdx, [rsp+10F0h+hMem]; union Windows::Internal::Security::Authentication::Web::SystemEventData::SystemEventDataPayload *
0x180055691  lea     rcx, [rbp+0FF0h+var_1060]; this
0x180055695  call    ?Initialize@SystemEventData@Web@Authentication@Security@Internal@Windows@@QEAAJPEAEK@Z; Windows::Internal::Security::Authentication::Web::SystemEventData::Initialize(uchar *,ulong)
0x18005569a  mov     [rsp+10F0h+var_1098], r13
0x18005569f  mov     [rsp+10F0h+string2], r13
0x1800556a4  mov     [rsp+10F0h+string], r13
0x1800556a9  lea     rdx, [rbp+0FF0h+var_50]
0x1800556b0  lea     rcx, [rsp+10F0h+var_1098]
0x1800556b5  call    ??$Initialize@PEBG@String@Internal@Windows@@QEAAJAEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<ushort const *>(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x1800556ba  lea     rdx, [rbp+0FF0h+var_60+8]
0x1800556c1  lea     rcx, [rsp+10F0h+string2]
0x1800556c6  call    ??$Initialize@PEBG@String@Internal@Windows@@QEAAJAEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<ushort const *>(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x1800556cb  lea     rdx, [rbp+0FF0h+var_48]
0x1800556d2  lea     rcx, [rsp+10F0h+string]
0x1800556d7  call    ??$Initialize@PEBG@String@Internal@Windows@@QEAAJAEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<ushort const *>(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x1800556dc  mov     eax, cs:dword_180175000
0x1800556e2  mov     rdi, [rsp+10F0h+var_1098]
0x1800556e7  mov     rbx, [rsp+10F0h+string2]
0x1800556ec  mov     rsi, [rsp+10F0h+string]
0x1800556f1  cmp     eax, 5
0x1800556f4  jbe     loc_1800557A3
0x1800556fa  mov     rcx, rsi; string
0x1800556fd  call    cs:__imp_WindowsIsStringEmpty
0x180055703  lea     r14, aNull; "null"
0x18005570a  test    eax, eax
0x18005570c  jz      short loc_180055713
0x18005570e  mov     rax, r14
0x180055711  jmp     short loc_18005571E
0x180055713  xor     edx, edx; length
0x180055715  mov     rcx, rsi; string
0x180055718  call    cs:__imp_WindowsGetStringRawBuffer
0x18005571e  mov     [rbp+0FF0h+var_1070], rax
0x180055722  mov     rcx, rbx; string
0x180055725  call    cs:__imp_WindowsIsStringEmpty
0x18005572b  test    eax, eax
0x18005572d  jz      short loc_180055734
0x18005572f  mov     rax, r14
0x180055732  jmp     short loc_18005573F
0x180055734  xor     edx, edx; length
0x180055736  mov     rcx, rbx; string
0x180055739  call    cs:__imp_WindowsGetStringRawBuffer
0x18005573f  mov     [rbp+0FF0h+var_1068], rax
0x180055743  mov     rcx, rdi; string
0x180055746  call    cs:__imp_WindowsIsStringEmpty
0x18005574c  test    eax, eax
0x18005574e  jnz     short loc_18005575E
0x180055750  xor     edx, edx; length
0x180055752  mov     rcx, rdi; string
0x180055755  call    cs:__imp_WindowsGetStringRawBuffer
0x18005575b  mov     r14, rax
0x18005575e  mov     [rsp+10F0h+var_10A0], r14
0x180055763  mov     eax, [rbp+0FF0h+var_1060]
0x180055766  mov     dword ptr [rsp+10F0h+SourceSize], eax
0x18005576a  lea     rax, [rbp+0FF0h+var_1070]
0x18005576e  mov     [rsp+10F0h+var_10B8], rax
0x180055773  lea     rax, [rbp+0FF0h+var_1068]
0x180055777  mov     [rsp+10F0h+var_10C0], rax
0x18005577c  lea     rax, [rsp+10F0h+var_10A0]
0x180055781  mov     [rsp+10F0h+var_10C8], rax
0x180055786  lea     rax, [rsp+10F0h+SourceSize]
0x18005578b  mov     [rsp+10F0h+var_10D0], rax
0x180055790  lea     rdx, word_18014ECAA
0x180055797  lea     rcx, dword_180175000
0x18005579e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800557a3  mov     ecx, [rbp+0FF0h+var_1060]
0x1800557a6  sub     ecx, 1
0x1800557a9  jz      loc_180055925
0x1800557af  sub     ecx, 1
0x1800557b2  jz      loc_1800558E2
0x1800557b8  sub     ecx, 1
0x1800557bb  jz      loc_1800558CB
0x1800557c1  sub     ecx, 1
0x1800557c4  jz      loc_180055870
0x1800557ca  sub     ecx, 1
0x1800557cd  jz      short loc_180055822
0x1800557cf  sub     ecx, 2
0x1800557d2  jz      short loc_180055800
0x1800557d4  cmp     ecx, 1
0x1800557d7  jz      short loc_1800557E4
0x1800557d9  mov     r14d, 80070057h
0x1800557df  jmp     loc_180055971
0x1800557e4  lea     rdx, [r15+130h]
0x1800557eb  mov     [rsp+10F0h+var_10D0], rsi
0x1800557f0  mov     r9, rbx
0x1800557f3  mov     r8, rdi
0x1800557f6  mov     rcx, r15
0x1800557f9  call    ??$SendEventInternalHardened@VCWebAccountDeletePendingEventArgs@Web@Authentication@Security@Internal@Windows@@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountDeletePendingEventArgs@23456@@Foundation@6@PEAUHSTRING__@@PEAU9@PEAU9@@CTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@AEAAJAEAV?$AgileEventSource@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountDeletePendingEventArgs@23456@@Foundation@Windows@@U?$HardenedInvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@PEAUHSTRING__@@11@Z; Windows::Internal::Security::Authentication::Web::CTokenBrokerInternal::SendEventInternalHardened<Windows::Internal::Security::Authentication::Web::CWebAccountDeletePendingEventArgs,Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *>,HSTRING__ *,HSTRING__ *,HSTRING__ *>(Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *>,Microsoft::WRL::HardenedInvokeModeOptions<-2>> &,HSTRING__ *,HSTRING__ *,HSTRING__ *)
0x1800557fe  jmp     short loc_18005581A
0x180055800  lea     rdx, [r15+118h]
0x180055807  mov     [rsp+10F0h+var_10D0], rsi
0x18005580c  mov     r9, rbx
0x18005580f  mov     r8, rdi
0x180055812  mov     rcx, r15
0x180055815  call    ??$SendEventInternalHardened@VCWebAccountDeletedEventArgs@Web@Authentication@Security@Internal@Windows@@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountDeletedEventArgs@23456@@Foundation@6@PEAUHSTRING__@@PEAU9@PEAU9@@CTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@AEAAJAEAV?$AgileEventSource@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountDeletedEventArgs@23456@@Foundation@Windows@@U?$HardenedInvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@PEAUHSTRING__@@11@Z; Windows::Internal::Security::Authentication::Web::CTokenBrokerInternal::SendEventInternalHardened<Windows::Internal::Security::Authentication::Web::CWebAccountDeletedEventArgs,Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletedEventArgs *>,HSTRING__ *,HSTRING__ *,HSTRING__ *>(Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletedEventArgs *>,Microsoft::WRL::HardenedInvokeModeOptions<-2>> &,HSTRING__ *,HSTRING__ *,HSTRING__ *)
0x18005581a  mov     r14d, eax
0x18005581d  jmp     loc_180055971
0x180055822  mov     [rsp+10F0h+SourceSize], r13
0x180055827  lea     rcx, [rsp+10F0h+SourceSize]
0x18005582c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055831  lea     rax, [rsp+10F0h+SourceSize]
0x180055836  mov     [rsp+10F0h+var_10D0], rax; struct Windows::Security::Credentials::IWebAccount **
0x18005583b  mov     r9, rsi; HSTRING
0x18005583e  mov     r8, rbx; HSTRING
0x180055841  mov     rdx, rdi; HSTRING
0x180055844  mov     rcx, [r15+198h]; unsigned __int64
0x18005584b  call    ?InitializeAccountFromEventData@@YAJ_KPEAUHSTRING__@@11PEAPEAUIWebAccount@Credentials@Security@Windows@@@Z; InitializeAccountFromEventData(unsigned __int64,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Security::Credentials::IWebAccount * *)
0x180055850  mov     r14d, eax
0x180055853  test    eax, eax
0x180055855  js      short loc_18005586E
0x180055857  lea     rdx, [r15+100h]
0x18005585e  mov     r8, [rsp+10F0h+SourceSize]
0x180055863  mov     rcx, r15
0x180055866  call    ??$SendEventInternalHardened@VCWebAccountChangedEventArgs@Web@Authentication@Security@Internal@Windows@@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountChangedEventArgs@23456@@Foundation@6@PEAUIWebAccount@Credentials@46@@CTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@AEAAJAEAV?$AgileEventSource@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountChangedEventArgs@23456@@Foundation@Windows@@U?$HardenedInvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@PEAUIWebAccount@Credentials@35@@Z; Windows::Internal::Security::Authentication::Web::CTokenBrokerInternal::SendEventInternalHardened<Windows::Internal::Security::Authentication::Web::CWebAccountChangedEventArgs,Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountChangedEventArgs *>,Windows::Security::Credentials::IWebAccount *>(Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountChangedEventArgs *>,Microsoft::WRL::HardenedInvokeModeOptions<-2>> &,Windows::Security::Credentials::IWebAccount *)
0x18005586b  mov     r14d, eax
0x18005586e  jmp     short loc_1800558BC
0x180055870  mov     [rsp+10F0h+SourceSize], r13
0x180055875  lea     rcx, [rsp+10F0h+SourceSize]
0x18005587a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005587f  lea     rax, [rsp+10F0h+SourceSize]
0x180055884  mov     [rsp+10F0h+var_10D0], rax; struct Windows::Security::Credentials::IWebAccount **
0x180055889  mov     r9, rsi; HSTRING
0x18005588c  mov     r8, rbx; HSTRING
0x18005588f  mov     rdx, rdi; HSTRING
0x180055892  mov     rcx, [r15+198h]; unsigned __int64
0x180055899  call    ?InitializeAccountFromEventData@@YAJ_KPEAUHSTRING__@@11PEAPEAUIWebAccount@Credentials@Security@Windows@@@Z; InitializeAccountFromEventData(unsigned __int64,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Security::Credentials::IWebAccount * *)
0x18005589e  mov     r14d, eax
0x1800558a1  test    eax, eax
0x1800558a3  js      short loc_1800558BC
0x1800558a5  lea     rdx, [r15+0E8h]
0x1800558ac  mov     r8, [rsp+10F0h+SourceSize]
0x1800558b1  mov     rcx, r15
0x1800558b4  call    ??$SendEventInternalHardened@VCWebAccountAddedEventArgs@Web@Authentication@Security@Internal@Windows@@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountAddedEventArgs@23456@@Foundation@6@PEAUIWebAccount@Credentials@46@@CTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@AEAAJAEAV?$AgileEventSource@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountAddedEventArgs@23456@@Foundation@Windows@@U?$HardenedInvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@PEAUIWebAccount@Credentials@35@@Z; Windows::Internal::Security::Authentication::Web::CTokenBrokerInternal::SendEventInternalHardened<Windows::Internal::Security::Authentication::Web::CWebAccountAddedEventArgs,Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountAddedEventArgs *>,Windows::Security::Credentials::IWebAccount *>(Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountAddedEventArgs *>,Microsoft::WRL::HardenedInvokeModeOptions<-2>> &,Windows::Security::Credentials::IWebAccount *)
0x1800558b9  mov     r14d, eax
0x1800558bc  lea     rcx, [rsp+10F0h+SourceSize]
0x1800558c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800558c6  jmp     loc_180055971
0x1800558cb  lea     rdx, [r15+178h]
0x1800558d2  mov     r8, rbx
0x1800558d5  mov     rcx, r15
0x1800558d8  call    ??$SendEventInternalHardened@VCWebAccountProviderDeletedEventArgs@Web@Authentication@Security@Internal@Windows@@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountProviderDeletedEventArgs@23456@@Foundation@6@PEAUHSTRING__@@@CTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@AEAAJAEAV?$AgileEventSource@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountProviderDeletedEventArgs@23456@@Foundation@Windows@@U?$HardenedInvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@PEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::Web::CTokenBrokerInternal::SendEventInternalHardened<Windows::Internal::Security::Authentication::Web::CWebAccountProviderDeletedEventArgs,Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountProviderDeletedEventArgs *>,HSTRING__ *>(Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountProviderDeletedEventArgs *>,Microsoft::WRL::HardenedInvokeModeOptions<-2>> &,HSTRING__ *)
0x1800558dd  jmp     loc_18005581A
0x1800558e2  mov     [rsp+10F0h+SourceSize], r13
0x1800558e7  lea     rcx, [rsp+10F0h+SourceSize]
0x1800558ec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800558f1  lea     r8, [rsp+10F0h+SourceSize]; struct Windows::Security::Credentials::IWebAccountProvider **
0x1800558f6  mov     rdx, rbx; string2
0x1800558f9  mov     rcx, [r15+198h]; unsigned __int64
0x180055900  call    ?InitializeProviderFromIdOnly@@YAJ_KPEAUHSTRING__@@PEAPEAUIWebAccountProvider@Credentials@Security@Windows@@@Z; InitializeProviderFromIdOnly(unsigned __int64,HSTRING__ *,Windows::Security::Credentials::IWebAccountProvider * *)
0x180055905  mov     r14d, eax
0x180055908  test    eax, eax
0x18005590a  js      short loc_180055923
0x18005590c  lea     rdx, [r15+160h]
0x180055913  mov     r8, [rsp+10F0h+SourceSize]
0x180055918  mov     rcx, r15
0x18005591b  call    ??$SendEventInternalHardened@VCWebAccountProviderChangedEventArgs@Web@Authentication@Security@Internal@Windows@@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountProviderChangedEventArgs@23456@@Foundation@6@PEAUIWebAccountProvider@Credentials@46@@CTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@AEAAJAEAV?$AgileEventSource@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountProviderChangedEventArgs@23456@@Foundation@Windows@@U?$HardenedInvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@PEAUIWebAccountProvider@Credentials@35@@Z; Windows::Internal::Security::Authentication::Web::CTokenBrokerInternal::SendEventInternalHardened<Windows::Internal::Security::Authentication::Web::CWebAccountProviderChangedEventArgs,Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountProviderChangedEventArgs *>,Windows::Security::Credentials::IWebAccountProvider *>(Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountProviderChangedEventArgs *>,Microsoft::WRL::HardenedInvokeModeOptions<-2>> &,Windows::Security::Credentials::IWebAccountProvider *)
0x180055920  mov     r14d, eax
0x180055923  jmp     short loc_180055966
0x180055925  mov     [rsp+10F0h+SourceSize], r13
0x18005592a  lea     rcx, [rsp+10F0h+SourceSize]
0x18005592f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055934  lea     r8, [rsp+10F0h+SourceSize]; struct Windows::Security::Credentials::IWebAccountProvider **
0x180055939  mov     rdx, rbx; string2
0x18005593c  mov     rcx, [r15+198h]; unsigned __int64
0x180055943  call    ?InitializeProviderFromIdOnly@@YAJ_KPEAUHSTRING__@@PEAPEAUIWebAccountProvider@Credentials@Security@Windows@@@Z; InitializeProviderFromIdOnly(unsigned __int64,HSTRING__ *,Windows::Security::Credentials::IWebAccountProvider * *)
0x180055948  mov     r14d, eax
0x18005594b  test    eax, eax
0x18005594d  js      short loc_180055966
0x18005594f  lea     rdx, [r15+148h]
0x180055956  mov     r8, [rsp+10F0h+SourceSize]
0x18005595b  mov     rcx, r15
0x18005595e  call    ??$SendEventInternalHardened@VCWebAccountProviderAddedEventArgs@Web@Authentication@Security@Internal@Windows@@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountProviderAddedEventArgs@23456@@Foundation@6@PEAUIWebAccountProvider@Credentials@46@@CTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@AEAAJAEAV?$AgileEventSource@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountProviderAddedEventArgs@23456@@Foundation@Windows@@U?$HardenedInvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@PEAUIWebAccountProvider@Credentials@35@@Z; Windows::Internal::Security::Authentication::Web::CTokenBrokerInternal::SendEventInternalHardened<Windows::Internal::Security::Authentication::Web::CWebAccountProviderAddedEventArgs,Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountProviderAddedEventArgs *>,Windows::Security::Credentials::IWebAccountProvider *>(Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountProviderAddedEventArgs *>,Microsoft::WRL::HardenedInvokeModeOptions<-2>> &,Windows::Security::Credentials::IWebAccountProvider *)
0x180055963  mov     r14d, eax
0x180055966  lea     rcx, [rsp+10F0h+SourceSize]
0x18005596b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055970  nop
0x180055971  test    rsi, rsi
0x180055974  jz      short loc_180055980
0x180055976  mov     rcx, rsi; string
0x180055979  call    cs:__imp_WindowsDeleteString
0x18005597f  nop
0x180055980  test    rbx, rbx
0x180055983  jz      short loc_18005598F
0x180055985  mov     rcx, rbx; string
0x180055988  call    cs:__imp_WindowsDeleteString
0x18005598e  nop
0x18005598f  test    rdi, rdi
0x180055992  jz      short loc_18005599D
0x180055994  mov     rcx, rdi; string
0x180055997  call    cs:__imp_WindowsDeleteString
0x18005599d  cmp     [rsp+10F0h+hMem], r13
0x1800559a2  jz      short loc_1800559B0
0x1800559a4  mov     rcx, [rsp+10F0h+hMem]; hMem
0x1800559a9  call    cs:__imp_LocalFree
0x1800559af  nop
0x1800559b0  lea     rcx, [rsp+10F0h+TokenHandle]; this
0x1800559b5  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800559ba  test    r14d, r14d
0x1800559bd  jns     short loc_1800559FB
0x1800559bf  mov     eax, cs:dword_180175000
0x1800559c5  cmp     eax, 2
0x1800559c8  jbe     short loc_1800559FB
0x1800559ca  lea     rax, aCanTInvokeEven; "Can't invoke event handlers"
0x1800559d1  mov     [rsp+10F0h+var_10A0], rax
0x1800559d6  mov     dword ptr [rsp+10F0h+SourceSize], r14d
0x1800559db  lea     rax, [rsp+10F0h+var_10A0]
0x1800559e0  mov     [rsp+10F0h+var_10C8], rax
0x1800559e5  lea     rax, [rsp+10F0h+SourceSize]
0x1800559ea  mov     [rsp+10F0h+var_10D0], rax
0x1800559ef  lea     rdx, dword_18014EC5C
0x1800559f6  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800559fb  xor     eax, eax
0x1800559fd  mov     rcx, [rbp+0FF0h+var_30]
0x180055a04  xor     rcx, rsp; StackCookie
0x180055a07  call    __security_check_cookie
0x180055a0c  lea     r11, [rsp+10F0h+var_20]
0x180055a14  mov     rbx, [r11+38h]
0x180055a18  mov     rsi, [r11+48h]
0x180055a1c  mov     rsp, r11
0x180055a1f  pop     r15
0x180055a21  pop     r14
0x180055a23  pop     r13
0x180055a25  pop     rdi
0x180055a26  pop     rbp
0x180055a27  retn
```
