# ValueSetUtils::details::InsertManifestPropertyValuesRecursive(winrt::Windows::Foundation::Collections::ValueSet const &,winrt::Windows::Foundation::Collections::IPropertySet const &)

- ea: `0x140057a74`
- end: `0x140057d54`
- name: `?InsertManifestPropertyValuesRecursive@details@ValueSetUtils@@YAXAEBUValueSet@Collections@Foundation@Windows@winrt@@AEBUIPropertySet@4567@@Z`
- size: `736`
- prototype: `void __fastcall(ValueSetUtils::details *__hidden this, const struct winrt::Windows::Foundation::Collections::ValueSet *, const struct winrt::Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140057a74`
- `0x14005b8bc`

## callees

- `0x14000a310`
- `0x14004fd98`
- `0x140052594`
- `0x140052978`
- `0x140052bf8`
- `0x140053948`
- `0x1400579a8`
- `0x140057a74`
- `0x14005bc68`
- `0x14005d654`
- `0x14005e8fc`
- `0x14005fcbc`
- `0x140067010`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall ValueSetUtils::details::InsertManifestPropertyValuesRecursive(
        ValueSetUtils::details *this,
        const struct winrt::Windows::Foundation::Collections::ValueSet *a2,
        const struct winrt::Windows::Foundation::Collections::IPropertySet *a3)
{
  unsigned int v4; // r15d
  __int64 v5; // rsi
  struct IUnknown *v6; // rdx
  int v7; // r15d
  __int64 (__fastcall *v8)(__int64, void **); // rbx
  void **v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // r15d
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64 *); // rbx
  unsigned int v14; // eax
  unsigned int v15; // r15d
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, void **); // rbx
  struct IUnknown *v18; // rdx
  void **v19; // rax
  unsigned int v20; // eax
  __int64 v21; // rax
  const struct winrt::Windows::Foundation::Collections::IPropertySet *v22; // r8
  unsigned int v23; // eax
  __int64 v24; // [rsp+20h] [rbp-89h] BYREF
  void (__fastcall ***v25)(_QWORD, __int64 *, __int64 *); // [rsp+28h] [rbp-81h] BYREF
  __int64 v26; // [rsp+30h] [rbp-79h] BYREF
  __int64 v27; // [rsp+38h] [rbp-71h] BYREF
  __int64 v28; // [rsp+40h] [rbp-69h] BYREF
  __int64 v29; // [rsp+48h] [rbp-61h] BYREF
  _BYTE v30[8]; // [rsp+50h] [rbp-59h] BYREF
  __int64 v31; // [rsp+58h] [rbp-51h] BYREF
  __int128 v32; // [rsp+60h] [rbp-49h]
  __int64 v33; // [rsp+78h] [rbp-31h] BYREF
  _BYTE v34[4]; // [rsp+80h] [rbp-29h] BYREF
  _BYTE v35[4]; // [rsp+84h] [rbp-25h] BYREF
  _BYTE v36[32]; // [rsp+88h] [rbp-21h] BYREF
  _QWORD v37[11]; // [rsp+A8h] [rbp-1h] BYREF
  __int64 v38; // [rsp+118h] [rbp+6Fh] BYREF
  char v39; // [rsp+120h] [rbp+77h] BYREF
  char v40; // [rsp+128h] [rbp+7Fh] BYREF

  LODWORD(v38) = 0;
  winrt::impl::get_begin_iterator<winrt::Windows::Foundation::Collections::IPropertySet,0>(&v26, a2, a3);
  v4 = 1;
  v33 = 0;
  v5 = v26;
  while ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v26, &v33) )
  {
    v29 = 0;
    v7 = v4 | 4;
    LODWORD(v38) = v7;
    LODWORD(v31) = 0;
    v32 = 0;
    v8 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v5 + 48LL);
    v9 = winrt::put_abi((winrt *)&v29, v6);
    v10 = v8(v5, v9);
    winrt::check_hresult(&v39, v10, &v31);
    v24 = 0;
    v11 = v7 & 0xFFFFFFE9 | 0x12;
    LODWORD(v38) = v11;
    v12 = v29;
    LODWORD(v31) = 0;
    v32 = 0;
    v13 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 48LL);
    std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v24);
    v14 = v13(v12, &v24);
    winrt::check_hresult(&v40, v14, &v31);
    v25 = 0;
    v15 = v11 & 0xFFFFFFA7 | 0x48;
    LODWORD(v38) = v15;
    v16 = v29;
    LODWORD(v31) = 0;
    v32 = 0;
    v17 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v29 + 56LL);
    v19 = winrt::put_abi((winrt *)&v25, v18);
    v20 = v17(v16, v19);
    winrt::check_hresult(v34, v20, &v31);
    LODWORD(v38) = v15 & 0xFFFFFFBF;
    v4 = v15 & 0xFFFFFF9F | 0x20;
    if ( v25 )
    {
      v38 = 0;
      (**v25)(v25, winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IPropertySet>, &v38);
      v21 = v38;
      v28 = v38;
    }
    else
    {
      v28 = 0;
      v21 = 0;
    }
    if ( v21 )
    {
      winrt::param::hstring::hstring((winrt::param::hstring *)v36, L"#text");
      winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(
        &v28,
        &v27,
        v36);
      if ( v27 )
      {
        v37[0] = v24;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          this,
          v37,
          &v27);
      }
      else
      {
        winrt::Windows::Foundation::Collections::ValueSet::ValueSet((winrt::Windows::Foundation::Collections::ValueSet *)v30);
        ValueSetUtils::details::InsertManifestPropertyValuesRecursive(
          (ValueSetUtils::details *)v30,
          (const struct winrt::Windows::Foundation::Collections::ValueSet *)&v28,
          v22);
        v31 = v24;
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          this,
          &v31,
          v30);
        winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)v30);
      }
      if ( v27 )
        winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v27);
    }
    else
    {
      v31 = v24;
      winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
        this,
        &v31,
        &v25);
    }
    winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v28);
    if ( v25 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref((__int64 *)&v25);
    std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v24);
    winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v29);
    LOBYTE(v38) = 0;
    LODWORD(v31) = 0;
    v32 = 0;
    v23 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 64LL))(v5, &v38);
    winrt::check_hresult(v35, v23, &v31);
    if ( !(_BYTE)v38 )
    {
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v26);
      v38 = 0;
      v5 = 0;
      v26 = 0;
      winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v38);
    }
  }
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v33);
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v26);
}

```

## disassembly

```asm
0x140057a74  push    rbp
0x140057a76  push    rbx
0x140057a77  push    rsi
0x140057a78  push    rdi
0x140057a79  push    r12
0x140057a7b  push    r14
0x140057a7d  push    r15
0x140057a7f  lea     rbp, [rsp-27h]
0x140057a84  sub     rsp, 0D0h
0x140057a8b  mov     r14, rcx
0x140057a8e  xor     r12d, r12d
0x140057a91  mov     dword ptr [rbp+57h+arg_8], r12d
0x140057a95  lea     rcx, [rbp+57h+var_D0]
0x140057a99  call    ??$get_begin_iterator@UIPropertySet@Collections@Foundation@Windows@winrt@@$0A@@impl@winrt@@YA?AU?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@1@AEBUIPropertySet@3451@@Z; winrt::impl::get_begin_iterator<winrt::Windows::Foundation::Collections::IPropertySet,0>(winrt::Windows::Foundation::Collections::IPropertySet const &)
0x140057a9e  lea     r15d, [r12+1]
0x140057aa3  mov     [rbp+57h+var_88], r12
0x140057aa7  mov     rsi, [rbp+57h+var_D0]
0x140057aab  lea     rdx, [rbp+57h+var_88]
0x140057aaf  lea     rcx, [rbp+57h+var_D0]
0x140057ab3  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x140057ab8  test    al, al
0x140057aba  jnz     loc_140057D2F
0x140057ac0  mov     [rbp+57h+var_B8], r12
0x140057ac4  or      r15d, 4
0x140057ac8  mov     dword ptr [rbp+57h+arg_8], r15d
0x140057acc  mov     dword ptr [rbp+57h+var_A8], r12d
0x140057ad0  xorps   xmm0, xmm0
0x140057ad3  movdqu  [rbp+57h+var_A0], xmm0
0x140057ad8  mov     rax, [rsi]
0x140057adb  mov     rbx, [rax+30h]
0x140057adf  lea     rcx, [rbp+57h+var_B8]; this
0x140057ae3  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x140057ae8  mov     rdx, rax
0x140057aeb  mov     rcx, rsi
0x140057aee  mov     rax, rbx
0x140057af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057af6  lea     r8, [rbp+57h+var_A8]
0x140057afa  mov     edx, eax
0x140057afc  lea     rcx, [rbp+57h+arg_10]
0x140057b00  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x140057b05  and     r15d, 0FFFFFFFBh
0x140057b09  or      r15d, 2
0x140057b0d  mov     [rsp+100h+var_E0], r12
0x140057b12  or      r15d, 10h
0x140057b16  mov     dword ptr [rbp+57h+arg_8], r15d
0x140057b1a  mov     rdi, [rbp+57h+var_B8]
0x140057b1e  mov     dword ptr [rbp+57h+var_A8], r12d
0x140057b22  xorps   xmm0, xmm0
0x140057b25  movdqu  [rbp+57h+var_A0], xmm0
0x140057b2a  mov     rax, [rdi]
0x140057b2d  mov     rbx, [rax+30h]
0x140057b31  lea     rcx, [rsp+100h+var_E0]
0x140057b36  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x140057b3b  lea     rdx, [rsp+100h+var_E0]
0x140057b40  mov     rcx, rdi
0x140057b43  mov     rax, rbx
0x140057b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057b4b  lea     r8, [rbp+57h+var_A8]
0x140057b4f  mov     edx, eax
0x140057b51  lea     rcx, [rbp+57h+arg_18]
0x140057b55  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x140057b5a  and     r15d, 0FFFFFFEFh
0x140057b5e  or      r15d, 8
0x140057b62  mov     [rsp+100h+var_D8], r12
0x140057b67  or      r15d, 40h
0x140057b6b  mov     dword ptr [rbp+57h+arg_8], r15d
0x140057b6f  mov     rdi, [rbp+57h+var_B8]
0x140057b73  mov     dword ptr [rbp+57h+var_A8], r12d
0x140057b77  xorps   xmm0, xmm0
0x140057b7a  movdqu  [rbp+57h+var_A0], xmm0
0x140057b7f  mov     rax, [rdi]
0x140057b82  mov     rbx, [rax+38h]
0x140057b86  lea     rcx, [rsp+100h+var_D8]; this
0x140057b8b  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x140057b90  mov     rdx, rax
0x140057b93  mov     rcx, rdi
0x140057b96  mov     rax, rbx
0x140057b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057b9e  lea     r8, [rbp+57h+var_A8]
0x140057ba2  mov     edx, eax
0x140057ba4  lea     rcx, [rbp+57h+var_80]
0x140057ba8  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x140057bad  and     r15d, 0FFFFFFBFh
0x140057bb1  mov     dword ptr [rbp+57h+arg_8], r15d
0x140057bb5  or      r15d, 20h
0x140057bb9  mov     rcx, [rsp+100h+var_D8]
0x140057bbe  test    rcx, rcx
0x140057bc1  jnz     short loc_140057BCC
0x140057bc3  mov     [rbp+57h+var_C0], r12
0x140057bc7  mov     rax, r12
0x140057bca  jmp     short loc_140057BEE
0x140057bcc  mov     [rbp+57h+arg_8], r12
0x140057bd0  mov     rax, [rcx]
0x140057bd3  lea     r8, [rbp+57h+arg_8]
0x140057bd7  lea     rdx, ??$guid_v@UIPropertySet@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IPropertySet>
0x140057bde  mov     rax, [rax]
0x140057be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057be6  mov     rax, [rbp+57h+arg_8]
0x140057bea  mov     [rbp+57h+var_C0], rax
0x140057bee  test    rax, rax
0x140057bf1  jz      loc_140057C86
0x140057bf7  lea     rdx, aText_0; "#text"
0x140057bfe  lea     rcx, [rbp+57h+var_78]; this
0x140057c02  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x140057c07  lea     r8, [rbp+57h+var_78]
0x140057c0b  lea     rdx, [rbp+57h+var_C8]
0x140057c0f  lea     rcx, [rbp+57h+var_C0]
0x140057c13  call    ?TryLookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::TryLookup(winrt::param::hstring const &)
0x140057c18  nop
0x140057c19  cmp     [rbp+57h+var_C8], r12
0x140057c1d  jz      short loc_140057C3A
0x140057c1f  mov     rax, [rsp+100h+var_E0]
0x140057c24  mov     [rbp+57h+var_58], rax
0x140057c28  lea     r8, [rbp+57h+var_C8]
0x140057c2c  lea     rdx, [rbp+57h+var_58]
0x140057c30  mov     rcx, r14
0x140057c33  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x140057c38  jmp     short loc_140057C75
0x140057c3a  lea     rcx, [rbp+57h+var_B0]; this
0x140057c3e  call    ??0ValueSet@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::ValueSet::ValueSet(void)
0x140057c43  nop
0x140057c44  lea     rdx, [rbp+57h+var_C0]; struct winrt::Windows::Foundation::Collections::ValueSet *
0x140057c48  lea     rcx, [rbp+57h+var_B0]; this
0x140057c4c  call    ?InsertManifestPropertyValuesRecursive@details@ValueSetUtils@@YAXAEBUValueSet@Collections@Foundation@Windows@winrt@@AEBUIPropertySet@4567@@Z; ValueSetUtils::details::InsertManifestPropertyValuesRecursive(winrt::Windows::Foundation::Collections::ValueSet const &,winrt::Windows::Foundation::Collections::IPropertySet const &)
0x140057c51  mov     rax, [rsp+100h+var_E0]
0x140057c56  mov     [rbp+57h+var_A8], rax
0x140057c5a  lea     r8, [rbp+57h+var_B0]
0x140057c5e  lea     rdx, [rbp+57h+var_A8]
0x140057c62  mov     rcx, r14
0x140057c65  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x140057c6a  nop
0x140057c6b  lea     rcx, [rbp+57h+var_B0]; this
0x140057c6f  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x140057c74  nop
0x140057c75  cmp     [rbp+57h+var_C8], r12
0x140057c79  jz      short loc_140057CA1
0x140057c7b  lea     rcx, [rbp+57h+var_C8]
0x140057c7f  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x140057c84  jmp     short loc_140057CA1
0x140057c86  mov     rax, [rsp+100h+var_E0]
0x140057c8b  mov     [rbp+57h+var_A8], rax
0x140057c8f  lea     r8, [rsp+100h+var_D8]
0x140057c94  lea     rdx, [rbp+57h+var_A8]
0x140057c98  mov     rcx, r14
0x140057c9b  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x140057ca0  nop
0x140057ca1  lea     rcx, [rbp+57h+var_C0]; this
0x140057ca5  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x140057caa  nop
0x140057cab  cmp     [rsp+100h+var_D8], r12
0x140057cb0  jz      short loc_140057CBD
0x140057cb2  lea     rcx, [rsp+100h+var_D8]
0x140057cb7  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x140057cbc  nop
0x140057cbd  lea     rcx, [rsp+100h+var_E0]
0x140057cc2  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x140057cc7  nop
0x140057cc8  lea     rcx, [rbp+57h+var_B8]; this
0x140057ccc  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x140057cd1  mov     byte ptr [rbp+57h+arg_8], r12b
0x140057cd5  mov     dword ptr [rbp+57h+var_A8], r12d
0x140057cd9  xorps   xmm0, xmm0
0x140057cdc  movdqu  [rbp+57h+var_A0], xmm0
0x140057ce1  mov     rax, [rsi]
0x140057ce4  lea     rdx, [rbp+57h+arg_8]
0x140057ce8  mov     rcx, rsi
0x140057ceb  mov     rax, [rax+40h]
0x140057cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057cf4  lea     r8, [rbp+57h+var_A8]
0x140057cf8  mov     edx, eax
0x140057cfa  lea     rcx, [rbp+57h+var_7C]
0x140057cfe  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x140057d03  cmp     byte ptr [rbp+57h+arg_8], r12b
0x140057d07  jnz     loc_140057AAB
0x140057d0d  lea     rcx, [rbp+57h+var_D0]
0x140057d11  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x140057d16  mov     [rbp+57h+arg_8], r12
0x140057d1a  mov     rsi, r12
0x140057d1d  mov     [rbp+57h+var_D0], r12
0x140057d21  lea     rcx, [rbp+57h+arg_8]; this
0x140057d25  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x140057d2a  jmp     loc_140057AAB
0x140057d2f  lea     rcx, [rbp+57h+var_88]; this
0x140057d33  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x140057d38  nop
0x140057d39  lea     rcx, [rbp+57h+var_D0]; this
0x140057d3d  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x140057d42  add     rsp, 0D0h
0x140057d49  pop     r15
0x140057d4b  pop     r14
0x140057d4d  pop     r12
0x140057d4f  pop     rdi
0x140057d50  pop     rsi
0x140057d51  pop     rbx
0x140057d52  pop     rbp
0x140057d53  retn
```
