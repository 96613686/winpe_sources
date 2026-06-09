# ValueSetUtils::DeserializeBase64ValueSet(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)

- ea: `0x1400550d0`
- end: `0x1400551be`
- name: `?DeserializeBase64ValueSet@ValueSetUtils@@YAXAEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@@Z`
- size: `238`
- prototype: `void __fastcall(ValueSetUtils *__hidden this, const struct winrt::hstring *, const struct winrt::Windows::Foundation::Collections::ValueSet *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140057e34`

## callees

- `0x14004eb14`
- `0x14004edbc`
- `0x140052bf8`
- `0x140053b2c`
- `0x140055088`
- `0x1400550d0`
- `0x14005d1a8`
- `0x14005fcdc`

## import_xrefs

- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x14005514d`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x14005514d`

## string_xrefs

- `0x14005515e`: `shellcommon\internal\shell\inc\ValueSetUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ValueSetUtils::DeserializeBase64ValueSet(
        ValueSetUtils *this,
        const struct winrt::hstring *a2,
        const struct winrt::Windows::Foundation::Collections::ValueSet *a3)
{
  int v4; // eax
  __int64 v5; // [rsp+20h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  __int64 *v7; // [rsp+50h] [rbp+10h] BYREF
  char v8; // [rsp+60h] [rbp+20h] BYREF
  __int64 *v9; // [rsp+68h] [rbp+28h] BYREF

  v5 = *(_QWORD *)this;
  v7 = &v5;
  v9 = &qword_1400839D8;
  _InterlockedIncrement64(&qword_1400839D8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics> )
  {
    _lambda_12918d939973c46c384f4162aa40ffe3_::operator()(
      &v7,
      &v8,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>);
    _InterlockedDecrement64(&qword_1400839D8);
  }
  else
  {
    _InterlockedDecrement64(&qword_1400839D8);
    winrt::impl::factory_cache_entry<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>::call<_lambda_12918d939973c46c384f4162aa40ffe3_ &>(
      this,
      &v8,
      &v7);
  }
  v7 = 0;
  v4 = RoCreatePropertySetSerializer(&v7);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\ValueSetUtils.h",
      (const char *)(unsigned int)v4,
      v5);
  winrt::com_ptr<Windows::Storage::Streams::IPropertySetSerializer>::as<winrt::Windows::Storage::Streams::IPropertySetSerializer>(
    &v7,
    &v9);
  winrt::impl::consume_Windows_Storage_Streams_IPropertySetSerializer<winrt::Windows::Storage::Streams::IPropertySetSerializer>::Deserialize(
    &v9,
    a2,
    &v8);
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v9);
  if ( v7 )
    winrt::com_ptr<IUnknown>::unconditional_release_ref(&v7);
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v8);
}

```

## disassembly

```asm
0x1400550d0  mov     [rsp-8+arg_8], rbx
0x1400550d5  push    rbp
0x1400550d6  mov     rbp, rsp
0x1400550d9  sub     rsp, 40h
0x1400550dd  mov     rbx, rdx
0x1400550e0  mov     rax, [rcx]
0x1400550e3  mov     [rbp+var_20], rax
0x1400550e7  lea     rax, [rbp+var_20]
0x1400550eb  mov     [rbp+arg_0], rax
0x1400550ef  lea     rax, qword_1400839D8
0x1400550f6  mov     [rbp+arg_18], rax
0x1400550fa  lock inc cs:qword_1400839D8
0x140055102  cmp     cs:??$factory_cache_entry_v@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@12@A, 0; factory_cache_entry<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>::winrt::factory_cache_entry<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>
0x14005510a  jz      short loc_14005512B
0x14005510c  lea     r8, ??$factory_cache_entry_v@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>::winrt::factory_cache_entry<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Cryptography::CryptographicBuffer,winrt::Windows::Security::Cryptography::ICryptographicBufferStatics>
0x140055113  lea     rdx, [rbp+arg_10]
0x140055117  lea     rcx, [rbp+arg_0]
0x14005511b  call    ??R_lambda_12918d939973c46c384f4162aa40ffe3_@@QEBA@AEBUICryptographicBufferStatics@Cryptography@Security@Windows@winrt@@@Z; _lambda_12918d939973c46c384f4162aa40ffe3_::operator()(winrt::Windows::Security::Cryptography::ICryptographicBufferStatics const &)
0x140055120  nop
0x140055121  lock dec cs:qword_1400839D8
0x140055129  jmp     short loc_140055141
0x14005512b  lock dec cs:qword_1400839D8
0x140055133  lea     r8, [rbp+arg_0]
0x140055137  lea     rdx, [rbp+arg_10]
0x14005513b  call    ??$call@AEAV_lambda_12918d939973c46c384f4162aa40ffe3_@@@?$factory_cache_entry@UCryptographicBuffer@Cryptography@Security@Windows@winrt@@UICryptographicBufferStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_12918d939973c46c384f4162aa40ffe3_@@@Z
0x140055140  nop
0x140055141  mov     [rbp+arg_0], 0
0x140055149  lea     rcx, [rbp+arg_0]
0x14005514d  call    cs:__imp_RoCreatePropertySetSerializer
0x140055153  mov     rcx, [rbp+8]; this
0x140055157  test    eax, eax
0x140055159  jns     short loc_140055170
0x14005515b  mov     r9d, eax; char *
0x14005515e  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Valu"...
0x140055165  mov     edx, 0B3h; void *
0x14005516a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140055170  lea     rdx, [rbp+arg_18]
0x140055174  lea     rcx, [rbp+arg_0]
0x140055178  call    ??$as@UIPropertySetSerializer@Streams@Storage@Windows@winrt@@@?$com_ptr@UIPropertySetSerializer@Streams@Storage@Windows@@@winrt@@QEBA?A_PXZ
0x14005517d  nop
0x14005517e  lea     r8, [rbp+arg_10]
0x140055182  mov     rdx, rbx
0x140055185  lea     rcx, [rbp+arg_18]
0x140055189  call    ?Deserialize@?$consume_Windows_Storage_Streams_IPropertySetSerializer@UIPropertySetSerializer@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@AEBUIPropertySet@Collections@Foundation@Windows@3@AEBUIBuffer@Streams@Storage@73@@Z; winrt::impl::consume_Windows_Storage_Streams_IPropertySetSerializer<winrt::Windows::Storage::Streams::IPropertySetSerializer>::Deserialize(winrt::Windows::Foundation::Collections::IPropertySet const &,winrt::Windows::Storage::Streams::IBuffer const &)
0x14005518e  nop
0x14005518f  lea     rcx, [rbp+arg_18]; this
0x140055193  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x140055198  nop
0x140055199  cmp     [rbp+arg_0], 0
0x14005519e  jz      short loc_1400551AA
0x1400551a0  lea     rcx, [rbp+arg_0]
0x1400551a4  call    ?unconditional_release_ref@?$com_ptr@UIUnknown@@@winrt@@AEAAXXZ; winrt::com_ptr<IUnknown>::unconditional_release_ref(void)
0x1400551a9  nop
0x1400551aa  lea     rcx, [rbp+arg_10]; this
0x1400551ae  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x1400551b3  mov     rbx, [rsp+40h+arg_8]
0x1400551b8  add     rsp, 40h
0x1400551bc  pop     rbp
0x1400551bd  retn
```
