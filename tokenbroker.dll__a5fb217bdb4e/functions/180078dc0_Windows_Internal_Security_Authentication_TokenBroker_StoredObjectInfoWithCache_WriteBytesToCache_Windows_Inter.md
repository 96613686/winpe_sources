# Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache::WriteBytesToCache(Windows::Internal::Security::Authentication::Web::IWamObjectStore *,uchar *,ulong)

- ea: `0x180078dc0`
- end: `0x180079132`
- name: `?WriteBytesToCache@StoredObjectInfoWithCache@TokenBroker@Authentication@Security@Internal@Windows@@AEBAJPEAUIWamObjectStore@Web@3456@PEAEK@Z`
- size: `882`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache *__hidden this, struct Windows::Internal::Security::Authentication::Web::IWamObjectStore *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004c520`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18000d250`
- `0x18001a510`
- `0x18003df30`
- `0x180040980`
- `0x180043370`
- `0x180047334`
- `0x18004d3a4`
- `0x18004d844`
- `0x180055498`
- `0x180060750`
- `0x180078dc0`
- `0x18008e690`
- `0x180110ba8`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007902d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007902d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078e1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078ec4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078e1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078ec4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078fa1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800790fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078fa1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800790fe`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180078f2a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180078f2a`
- `ext-ms-win-kernel32-package-l1-1-0!AppContainerDeriveSidFromMoniker` at `0x180078ed1`
- `ext-ms-win-kernel32-package-l1-1-0!AppContainerDeriveSidFromMoniker` at `0x180078ed1`

## string_xrefs

- `0x180078fc6`: `Windows.Storage.Streams.DataWriter`
- `0x180078e93`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180078ee8`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180078f62`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180078ff0`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfoWithCache::WriteBytesToCache(
        HSTRING *this,
        struct Windows::Internal::Security::Authentication::Web::IWamObjectStore *a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  HSTRING v8; // rbx
  int v9; // r9d
  const struct Windows::Internal::String *v10; // rax
  int v11; // eax
  unsigned int v12; // edi
  PCWSTR StringRawBuffer; // rax
  int v14; // eax
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  int v17; // eax
  HSTRING v18; // rcx
  _QWORD *v19; // rax
  int v20; // eax
  __int64 v21; // rdx
  signed int LastError; // eax
  int v24; // [rsp+20h] [rbp-79h]
  unsigned int v25; // [rsp+30h] [rbp-69h] BYREF
  unsigned int *v26; // [rsp+38h] [rbp-61h] BYREF
  char v27; // [rsp+40h] [rbp-59h]
  __int64 v28; // [rsp+48h] [rbp-51h] BYREF
  HSTRING string; // [rsp+50h] [rbp-49h] BYREF
  PSID v30; // [rsp+58h] [rbp-41h] BYREF
  __int64 v31; // [rsp+60h] [rbp-39h] BYREF
  PSID Sid; // [rsp+68h] [rbp-31h] BYREF
  LPWSTR StringSid; // [rsp+70h] [rbp-29h] BYREF
  __int64 v34; // [rsp+78h] [rbp-21h] BYREF
  HSTRING v35[4]; // [rsp+80h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v25 = 0;
  v34 = 0;
  StringSid = 0;
  v8 = 0;
  string = 0;
  if ( (unsigned int)dword_180175000 > 4 )
  {
    Sid = (PSID)WindowsGetStringRawBuffer(this[13], 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (unsigned int)&dword_180175000,
      (unsigned int)word_1801593CA,
      0,
      v9,
      (__int64)&Sid);
  }
  v26 = &v25;
  v27 = 1;
  v10 = (const struct Windows::Internal::String *)Windows::Internal::StringReference::StringReference(
                                                    v35,
                                                    L"NO_APPLICATION");
  if ( !(unsigned int)Windows::Internal::StringReference::CompareOrdinal(
                        (Windows::Internal::StringReference *)(this + 9),
                        v10) )
  {
    v11 = Windows::Internal::String::Initialize((Windows::Internal::String *)&string, L"S-1-5-10", 8u);
    v12 = v11;
    v25 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8FA,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
        (const char *)(unsigned int)v11,
        v24);
      goto LABEL_13;
    }
    v8 = string;
LABEL_17:
    v28 = 0;
    v19 = (_QWORD *)Windows::Internal::StringReference::StringReference(v35, L"Windows.Storage.Streams.DataWriter");
    v20 = Windows::Foundation::ActivateInstance<Windows::Storage::Streams::IDataWriter>(*v19, &v28);
    v12 = v20;
    v25 = v20;
    if ( v20 >= 0 )
    {
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int8 *))(*(_QWORD *)v28 + 96LL))(v28, a4, a3);
      v12 = v20;
      v25 = v20;
      if ( v20 >= 0 )
      {
        v20 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 248LL))(v28, &v34);
        v12 = v20;
        v25 = v20;
        if ( v20 >= 0 )
        {
          v20 = (*(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWamObjectStore *, HSTRING, HSTRING, __int64))(*(_QWORD *)a2 + 56LL))(
                  a2,
                  this[13],
                  v8,
                  v34);
          v12 = v20;
          v25 = v20;
          if ( v20 >= 0 )
          {
            v25 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
            v27 = 0;
            lambda_06f54811cd422e8b164e4a7aa6efda6b_::operator()(&v26);
            if ( v8 )
              WindowsDeleteString(v8);
            v12 = 0;
            goto LABEL_34;
          }
          v21 = 2330;
        }
        else
        {
          v21 = 2328;
        }
      }
      else
      {
        v21 = 2327;
      }
    }
    else
    {
      v21 = 2326;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      (const char *)(unsigned int)v20,
      v24);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    v27 = 0;
    lambda_06f54811cd422e8b164e4a7aa6efda6b_::operator()(&v26);
    if ( !v8 )
      goto LABEL_34;
    v18 = v8;
    goto LABEL_14;
  }
  v31 = 0;
  Sid = 0;
  v30 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(this[9], 0);
  v14 = AppContainerDeriveSidFromMoniker(StringRawBuffer, &Sid);
  v12 = v14;
  v25 = v14;
  if ( v14 < 0 )
  {
    v15 = (unsigned int)v14;
    v16 = 2310;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
      (const char *)v15,
      v24);
    std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>::~unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>(&v30);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v31);
    v27 = 0;
    lambda_06f54811cd422e8b164e4a7aa6efda6b_::operator()(&v26);
    goto LABEL_34;
  }
  v30 = Sid;
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    v25 = v12;
    if ( (v12 & 0x80000000) != 0 )
    {
      v15 = v12;
      v16 = 2320;
      goto LABEL_9;
    }
LABEL_16:
    std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>::~unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>(&v30);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v31);
    goto LABEL_17;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &v31,
    StringSid);
  v17 = Windows::Internal::String::Initialize<unsigned short *>(&string, &StringSid);
  v12 = v17;
  v25 = v17;
  if ( v17 >= 0 )
  {
    v8 = string;
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x90C,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\filestore.cpp",
    (const char *)(unsigned int)v17,
    v24);
  std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>::~unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>(&v30);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v31);
LABEL_13:
  v27 = 0;
  lambda_06f54811cd422e8b164e4a7aa6efda6b_::operator()(&v26);
  v18 = string;
  if ( string )
LABEL_14:
    WindowsDeleteString(v18);
LABEL_34:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  return v12;
}

```

## disassembly

```asm
0x180078dc0  push    rbp
0x180078dc2  push    rbx
0x180078dc3  push    rsi
0x180078dc4  push    rdi
0x180078dc5  push    r12
0x180078dc7  push    r13
0x180078dc9  push    r14
0x180078dcb  push    r15
0x180078dcd  lea     rbp, [rsp-1Fh]
0x180078dd2  sub     rsp, 0B8h
0x180078dd9  mov     rax, cs:__security_cookie
0x180078de0  xor     rax, rsp
0x180078de3  mov     [rbp+57h+var_50], rax
0x180078de7  mov     r12d, r9d
0x180078dea  mov     r15, r8
0x180078ded  mov     r14, rdx
0x180078df0  mov     rsi, rcx
0x180078df3  xor     r13d, r13d
0x180078df6  mov     [rbp+57h+var_C0], r13d
0x180078dfa  mov     [rbp+57h+var_78], r13
0x180078dfe  mov     [rbp+57h+StringSid], r13
0x180078e02  mov     ebx, r13d
0x180078e05  mov     [rbp+57h+string], rbx
0x180078e09  mov     eax, cs:dword_180175000
0x180078e0f  cmp     eax, 4
0x180078e12  jbe     short loc_180078E43
0x180078e14  xor     edx, edx; length
0x180078e16  mov     rcx, [rcx+68h]; string
0x180078e1a  call    cs:__imp_WindowsGetStringRawBuffer
0x180078e20  mov     [rbp+57h+Sid], rax
0x180078e24  lea     rax, [rbp+57h+Sid]
0x180078e28  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180078e2d  xor     r8d, r8d
0x180078e30  lea     rdx, word_1801593CA
0x180078e37  lea     rcx, dword_180175000
0x180078e3e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180078e43  lea     rax, [rbp+57h+var_C0]
0x180078e47  mov     [rbp+57h+var_B8], rax
0x180078e4b  mov     [rbp+57h+var_B0], 1
0x180078e4f  lea     rdx, aNoApplication; "NO_APPLICATION"
0x180078e56  lea     rcx, [rbp+57h+var_70]; string
0x180078e5a  call    ??$?0$0P@@StringReference@Internal@Windows@@QEAA@AEAY0P@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[15])
0x180078e5f  mov     rdx, rax; struct Windows::Internal::String *
0x180078e62  lea     rcx, [rsi+48h]; this
0x180078e66  call    ?CompareOrdinal@StringReference@Internal@Windows@@QEBAHAEBVString@23@@Z; Windows::Internal::StringReference::CompareOrdinal(Windows::Internal::String const &)
0x180078e6b  test    eax, eax
0x180078e6d  jnz     short loc_180078EB2
0x180078e6f  lea     r8d, [rax+8]; unsigned int
0x180078e73  lea     rdx, aS1510; "S-1-5-10"
0x180078e7a  lea     rcx, [rbp+57h+string]; this
0x180078e7e  call    ?Initialize@String@Internal@Windows@@QEAAJPEBGI@Z; Windows::Internal::String::Initialize(ushort const *,uint)
0x180078e83  mov     edi, eax
0x180078e85  mov     [rbp+57h+var_C0], eax
0x180078e88  test    eax, eax
0x180078e8a  jns     short loc_180078EA9
0x180078e8c  mov     rcx, [rbp+5Fh]; this
0x180078e90  mov     r9d, eax; char *
0x180078e93  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180078e9a  mov     edx, 8FAh; void *
0x180078e9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078ea4  jmp     loc_180078F86
0x180078ea9  mov     rbx, [rbp+57h+string]
0x180078ead  jmp     loc_180078FC2
0x180078eb2  mov     [rbp+57h+var_90], r13
0x180078eb6  mov     [rbp+57h+Sid], r13
0x180078eba  mov     [rbp+57h+var_98], r13
0x180078ebe  xor     edx, edx; length
0x180078ec0  mov     rcx, [rsi+48h]; string
0x180078ec4  call    cs:__imp_WindowsGetStringRawBuffer
0x180078eca  lea     rdx, [rbp+57h+Sid]
0x180078ece  mov     rcx, rax
0x180078ed1  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x180078ed7  mov     edi, eax
0x180078ed9  mov     [rbp+57h+var_C0], eax
0x180078edc  test    eax, eax
0x180078ede  jns     short loc_180078F1E
0x180078ee0  mov     r9d, eax; char *
0x180078ee3  mov     edx, 906h; void *
0x180078ee8  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180078eef  mov     rcx, [rbp+5Fh]; this
0x180078ef3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078ef8  lea     rcx, [rbp+57h+var_98]
0x180078efc  call    ??1?$unique_ptr@PEAXUSidDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@QEAA@XZ; std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>::~unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>(void)
0x180078f01  lea     rcx, [rbp+57h+var_90]
0x180078f05  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180078f0a  nop
0x180078f0b  mov     [rbp+57h+var_B0], r13b
0x180078f0f  lea     rcx, [rbp+57h+var_B8]
0x180078f13  call    _lambda_06f54811cd422e8b164e4a7aa6efda6b___operator__
0x180078f18  nop
0x180078f19  jmp     loc_180079107
0x180078f1e  mov     rcx, [rbp+57h+Sid]; Sid
0x180078f22  mov     [rbp+57h+var_98], rcx
0x180078f26  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180078f2a  call    cs:__imp_ConvertSidToStringSidW
0x180078f30  test    eax, eax
0x180078f32  jz      loc_18007902D
0x180078f38  mov     rdx, [rbp+57h+StringSid]
0x180078f3c  lea     rcx, [rbp+57h+var_90]
0x180078f40  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180078f45  lea     rdx, [rbp+57h+StringSid]
0x180078f49  lea     rcx, [rbp+57h+string]
0x180078f4d  call    ??$Initialize@PEAG@String@Internal@Windows@@QEAAJAEBQEAGUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<ushort *>(ushort * const &,Windows::Internal::_StringDetail::dummy_t)
0x180078f52  mov     edi, eax
0x180078f54  mov     [rbp+57h+var_C0], eax
0x180078f57  test    eax, eax
0x180078f59  jns     short loc_180078FAC
0x180078f5b  mov     rcx, [rbp+5Fh]; this
0x180078f5f  mov     r9d, eax; char *
0x180078f62  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180078f69  mov     edx, 90Ch; void *
0x180078f6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078f73  lea     rcx, [rbp+57h+var_98]
0x180078f77  call    ??1?$unique_ptr@PEAXUSidDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@QEAA@XZ; std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>::~unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>(void)
0x180078f7c  lea     rcx, [rbp+57h+var_90]
0x180078f80  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180078f85  nop
0x180078f86  mov     [rbp+57h+var_B0], r13b
0x180078f8a  lea     rcx, [rbp+57h+var_B8]
0x180078f8e  call    _lambda_06f54811cd422e8b164e4a7aa6efda6b___operator__
0x180078f93  nop
0x180078f94  mov     rcx, [rbp+57h+string]; string
0x180078f98  test    rcx, rcx
0x180078f9b  jz      loc_180079107
0x180078fa1  call    cs:__imp_WindowsDeleteString
0x180078fa7  jmp     loc_180079107
0x180078fac  mov     rbx, [rbp+57h+string]
0x180078fb0  lea     rcx, [rbp+57h+var_98]
0x180078fb4  call    ??1?$unique_ptr@PEAXUSidDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@QEAA@XZ; std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>::~unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::SidDeleter>(void)
0x180078fb9  lea     rcx, [rbp+57h+var_90]
0x180078fbd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180078fc2  mov     [rbp+57h+var_A8], r13
0x180078fc6  lea     rdx, ?RuntimeClass_Windows_Storage_Streams_DataWriter@@3QBGB; "Windows.Storage.Streams.DataWriter"
0x180078fcd  lea     rcx, [rbp+57h+var_70]; string
0x180078fd1  call    ??$?0$0CD@@StringReference@Internal@Windows@@QEAA@AEAY0CD@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[35])
0x180078fd6  lea     rdx, [rbp+57h+var_A8]
0x180078fda  mov     rcx, [rax]
0x180078fdd  call    ??$ActivateInstance@UIDataWriter@Streams@Storage@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIDataWriter@Streams@Storage@1@@Z; Windows::Foundation::ActivateInstance<Windows::Storage::Streams::IDataWriter>(HSTRING__ *,Windows::Storage::Streams::IDataWriter * *)
0x180078fe2  mov     edi, eax
0x180078fe4  mov     [rbp+57h+var_C0], eax
0x180078fe7  test    eax, eax
0x180078fe9  jns     short loc_18007905A
0x180078feb  mov     edx, 916h; void *
0x180078ff0  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180078ff7  mov     r9d, eax; char *
0x180078ffa  mov     rcx, [rbp+5Fh]; this
0x180078ffe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079003  nop
0x180079004  lea     rcx, [rbp+57h+var_A8]
0x180079008  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007900d  nop
0x18007900e  mov     [rbp+57h+var_B0], r13b
0x180079012  lea     rcx, [rbp+57h+var_B8]
0x180079016  call    _lambda_06f54811cd422e8b164e4a7aa6efda6b___operator__
0x18007901b  nop
0x18007901c  test    rbx, rbx
0x18007901f  jz      loc_180079107
0x180079025  mov     rcx, rbx
0x180079028  jmp     loc_180078FA1
0x18007902d  call    cs:__imp_GetLastError
0x180079033  mov     edi, eax
0x180079035  test    eax, eax
0x180079037  jle     short loc_180079042
0x180079039  movzx   edi, ax
0x18007903c  or      edi, 80070000h
0x180079042  mov     [rbp+57h+var_C0], edi
0x180079045  test    edi, edi
0x180079047  jns     loc_180078FB0
0x18007904d  mov     r9d, edi
0x180079050  mov     edx, 910h
0x180079055  jmp     loc_180078EE8
0x18007905a  mov     rcx, [rbp+57h+var_A8]
0x18007905e  mov     rax, [rcx]
0x180079061  mov     r8, r15
0x180079064  mov     edx, r12d
0x180079067  mov     rax, [rax+60h]
0x18007906b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079070  mov     edi, eax
0x180079072  mov     [rbp+57h+var_C0], eax
0x180079075  test    eax, eax
0x180079077  jns     short loc_180079083
0x180079079  mov     edx, 917h
0x18007907e  jmp     loc_180078FF0
0x180079083  mov     rcx, [rbp+57h+var_A8]
0x180079087  mov     rax, [rcx]
0x18007908a  lea     rdx, [rbp+57h+var_78]
0x18007908e  mov     rax, [rax+0F8h]
0x180079095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007909a  mov     edi, eax
0x18007909c  mov     [rbp+57h+var_C0], eax
0x18007909f  test    eax, eax
0x1800790a1  jns     short loc_1800790AD
0x1800790a3  mov     edx, 918h
0x1800790a8  jmp     loc_180078FF0
0x1800790ad  mov     rax, [r14]
0x1800790b0  mov     r9, [rbp+57h+var_78]
0x1800790b4  mov     r8, rbx
0x1800790b7  mov     rdx, [rsi+68h]
0x1800790bb  mov     rcx, r14
0x1800790be  mov     rax, [rax+38h]
0x1800790c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800790c7  mov     edi, eax
0x1800790c9  mov     [rbp+57h+var_C0], eax
0x1800790cc  test    eax, eax
0x1800790ce  jns     short loc_1800790DA
0x1800790d0  mov     edx, 91Ah
0x1800790d5  jmp     loc_180078FF0
0x1800790da  mov     [rbp+57h+var_C0], r13d
0x1800790de  lea     rcx, [rbp+57h+var_A8]
0x1800790e2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800790e7  nop
0x1800790e8  mov     [rbp+57h+var_B0], r13b
0x1800790ec  lea     rcx, [rbp+57h+var_B8]
0x1800790f0  call    _lambda_06f54811cd422e8b164e4a7aa6efda6b___operator__
0x1800790f5  nop
0x1800790f6  test    rbx, rbx
0x1800790f9  jz      short loc_180079104
0x1800790fb  mov     rcx, rbx; string
0x1800790fe  call    cs:__imp_WindowsDeleteString
0x180079104  mov     edi, r13d
0x180079107  lea     rcx, [rbp+57h+var_78]
0x18007910b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079110  mov     eax, edi
0x180079112  mov     rcx, [rbp+57h+var_50]
0x180079116  xor     rcx, rsp; StackCookie
0x180079119  call    __security_check_cookie
0x18007911e  add     rsp, 0B8h
0x180079125  pop     r15
0x180079127  pop     r14
0x180079129  pop     r13
0x18007912b  pop     r12
0x18007912d  pop     rdi
0x18007912e  pop     rsi
0x18007912f  pop     rbx
0x180079130  pop     rbp
0x180079131  retn
```
