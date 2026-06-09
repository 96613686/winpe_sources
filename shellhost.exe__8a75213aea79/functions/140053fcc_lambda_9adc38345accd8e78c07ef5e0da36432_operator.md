# _lambda_9adc38345accd8e78c07ef5e0da36432_::operator()

- ea: `0x140053fcc`
- end: `0x140054346`
- name: `_lambda_9adc38345accd8e78c07ef5e0da36432_::operator()`
- size: `890`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x14005cb50`

## callees

- `0x140009d6c`
- `0x14000a310`
- `0x14000a930`
- `0x14000b360`
- `0x14000b638`
- `0x14000c384`
- `0x14000cc98`
- `0x14000f7e0`
- `0x14004d0e4`
- `0x14004ebf4`
- `0x14004f020`
- `0x140052594`
- `0x140052978`
- `0x1400529c8`
- `0x140052bf8`
- `0x140053ce8`
- `0x140053fcc`
- `0x1400579a8`
- `0x140057e34`
- `0x14005d614`
- `0x14005fcbc`

## string_xrefs

- `0x14005406d`: `CommunicationHWND`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall lambda_9adc38345accd8e78c07ef5e0da36432_::operator()(__int64 **a1)
{
  __int64 v2; // rcx
  struct IInspectableVtbl *lpVtbl; // rbx
  __int64 v4; // r8
  __int64 v5; // rdx
  unsigned __int64 v6; // rax
  __int64 v7; // rsi
  __int64 v8; // rdi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rbx
  __int64 *v12; // rcx
  struct IInspectableVtbl *v13; // rbx
  __int64 v14; // rbx
  ValueSetUtils **v15; // rdi
  __int64 v16; // rsi
  ValueSetUtils *v17; // r14
  winrt::hstring *v18; // r15
  winrt::hstring *v19; // r12
  winrt::hstring *v20; // r13
  char v21[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v22; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v23[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h] BYREF
  __int128 v25; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+80h] [rbp-80h]
  __int64 v27; // [rsp+88h] [rbp-78h] BYREF
  __int64 v28; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v29[32]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v30[5]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v31[32]; // [rsp+E0h] [rbp-20h] BYREF

  winrt::Windows::Foundation::Collections::ValueSet::ValueSet((winrt::Windows::Foundation::Collections::ValueSet *)v23);
  v2 = **a1;
  v28 = v2;
  v22 = &v28;
  v30[4] = &qword_140083958;
  _InterlockedIncrement64(&qword_140083958);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> )
  {
    _lambda_31c76cf67978e40e190b18794b9e9852_::operator()(
      &v22,
      &v24,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>);
    _InterlockedDecrement64(&qword_140083958);
  }
  else
  {
    _InterlockedDecrement64(&qword_140083958);
    winrt::impl::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::call<_lambda_31c76cf67978e40e190b18794b9e9852_ &>(
      v2,
      &v24,
      &v22);
  }
  winrt::param::hstring::hstring((winrt::param::hstring *)v30, L"CommunicationHWND");
  winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
    v23,
    v30,
    &v24);
  if ( v24 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v24);
  v30[0] = *a1[1];
  lpVtbl = winrt::box_value((winrt *)&v22, (const struct winrt::param::hstring *)v30).lpVtbl;
  winrt::param::hstring::hstring((winrt::param::hstring *)v29, L"WindowingBehavior");
  winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
    v23,
    v29,
    lpVtbl);
  if ( v22 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v22);
  std::wstring::wstring(v31, *a1[2]);
  LOBYTE(v4) = 32;
  SplitString(&v25, v31, v4);
  v5 = v25;
  v6 = (__int64)(*((_QWORD *)&v25 + 1) - v25) >> 5;
  v7 = 6;
  if ( v6 > 6 && (v6 & 1) == 0 && v6 > 7 )
  {
    do
    {
      v8 = 32 * v7;
      v9 = (_QWORD *)(32 * v7 + v5);
      v10 = v9[2];
      if ( v9[3] > 7u )
        v9 = (_QWORD *)*v9;
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v9, v10, L"UseWinUI3", 9) )
      {
        v21[0] = 1;
        v11 = winrt::box_value<bool,0>(&v22, v21);
        winrt::param::hstring::hstring(v29, v8 + v25);
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          v23,
          v29,
          v11);
        if ( v22 )
        {
          v12 = (__int64 *)&v22;
LABEL_18:
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v12);
        }
      }
      else
      {
        winrt::param::hstring::hstring(v29, v8 + v25 + 32);
        v13 = winrt::box_value((winrt *)&v24, (const struct winrt::param::hstring *)v29).lpVtbl;
        winrt::param::hstring::hstring(v30, v8 + v25);
        winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
          v23,
          v30,
          v13);
        if ( v24 )
        {
          v12 = &v24;
          goto LABEL_18;
        }
      }
      v7 += 2;
      v5 = v25;
    }
    while ( v7 + 1 < (unsigned __int64)((__int64)(*((_QWORD *)&v25 + 1) - v25) >> 5) );
  }
  winrt::Windows::Foundation::Collections::ValueSet::ValueSet((winrt::Windows::Foundation::Collections::ValueSet *)&v27);
  winrt::param::hstring::hstring((winrt::param::hstring *)v29, L"InvocationProperties");
  winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
    &v27,
    v29,
    v23);
  v14 = (__int64)a1[9];
  v15 = (ValueSetUtils **)a1[8];
  v16 = (__int64)a1[7];
  v17 = (ValueSetUtils *)a1[6];
  v18 = (winrt::hstring *)a1[5];
  v19 = (winrt::hstring *)a1[4];
  v20 = (winrt::hstring *)a1[3];
  winrt::hstring::hstring((winrt::hstring *)&v22, &qword_14006BB60);
  LaunchUXFrameAndWait((struct winrt::hstring *)&v22, v20, v19, v18, v17, v16, v15, v14, (__int64)&v27);
  std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v22);
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v27);
  if ( (_QWORD)v25 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v25, *((_QWORD *)&v25 + 1));
    std::_Deallocate<16>(v25, (v26 - v25) & 0xFFFFFFFFFFFFFFE0uLL);
    v25 = 0;
    v26 = 0;
  }
  std::wstring::~wstring(v31);
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)v23);
}

```

## disassembly

```asm
0x140053fcc  push    rbp
0x140053fce  push    rbx
0x140053fcf  push    rsi
0x140053fd0  push    rdi
0x140053fd1  push    r12
0x140053fd3  push    r13
0x140053fd5  push    r14
0x140053fd7  push    r15
0x140053fd9  lea     rbp, [rsp-18h]
0x140053fde  sub     rsp, 118h
0x140053fe5  mov     rax, cs:__security_cookie
0x140053fec  xor     rax, rsp
0x140053fef  mov     [rbp+50h+var_50], rax
0x140053ff3  mov     r13, rcx
0x140053ff6  xor     r14d, r14d
0x140053ff9  lea     rcx, [rsp+150h+var_F0]; this
0x140053ffe  call    ??0ValueSet@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::ValueSet::ValueSet(void)
0x140054003  nop
0x140054004  mov     rax, [r13+0]
0x140054008  mov     rcx, [rax]
0x14005400b  mov     [rbp+50h+var_C0], rcx
0x14005400f  lea     rax, [rbp+50h+var_C0]
0x140054013  mov     [rsp+150h+var_F8], rax
0x140054018  lea     rax, qword_140083958
0x14005401f  mov     [rbp+50h+var_78], rax
0x140054023  lock inc cs:qword_140083958
0x14005402b  cmp     cs:??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A, r14; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x140054032  jz      short loc_140054055
0x140054034  lea     r8, ??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x14005403b  lea     rdx, [rsp+150h+var_E8]
0x140054040  lea     rcx, [rsp+150h+var_F8]
0x140054045  call    ??R_lambda_31c76cf67978e40e190b18794b9e9852_@@QEBA@AEBUIPropertyValueStatics@Foundation@Windows@winrt@@@Z; _lambda_31c76cf67978e40e190b18794b9e9852_::operator()(winrt::Windows::Foundation::IPropertyValueStatics const &)
0x14005404a  nop
0x14005404b  lock dec cs:qword_140083958
0x140054053  jmp     short loc_14005406D
0x140054055  lock dec cs:qword_140083958
0x14005405d  lea     r8, [rsp+150h+var_F8]
0x140054062  lea     rdx, [rsp+150h+var_E8]
0x140054067  call    ??$call@AEAV_lambda_31c76cf67978e40e190b18794b9e9852_@@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_31c76cf67978e40e190b18794b9e9852_@@@Z
0x14005406c  nop
0x14005406d  lea     rdx, aCommunicationh_0; "CommunicationHWND"
0x140054074  lea     rcx, [rbp+50h+var_98]; this
0x140054078  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x14005407d  lea     r8, [rsp+150h+var_E8]
0x140054082  lea     rdx, [rbp+50h+var_98]
0x140054086  lea     rcx, [rsp+150h+var_F0]
0x14005408b  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x140054090  nop
0x140054091  cmp     [rsp+150h+var_E8], r14
0x140054096  jz      short loc_1400540A2
0x140054098  lea     rcx, [rsp+150h+var_E8]
0x14005409d  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1400540a2  mov     rax, [r13+8]
0x1400540a6  mov     rcx, [rax]
0x1400540a9  mov     [rbp+50h+var_98], rcx
0x1400540ad  lea     rdx, [rbp+50h+var_98]; struct winrt::param::hstring *
0x1400540b1  lea     rcx, [rsp+150h+var_F8]; this
0x1400540b6  call    ?box_value@winrt@@YA?AUIInspectable@Foundation@Windows@1@AEBUhstring@param@1@@Z; winrt::box_value(winrt::param::hstring const &)
0x1400540bb  mov     rbx, rax
0x1400540be  lea     rdx, aWindowingbehav_0; "WindowingBehavior"
0x1400540c5  lea     rcx, [rbp+50h+var_B8]; this
0x1400540c9  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1400540ce  mov     r8, rbx
0x1400540d1  lea     rdx, [rbp+50h+var_B8]
0x1400540d5  lea     rcx, [rsp+150h+var_F0]
0x1400540da  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x1400540df  nop
0x1400540e0  cmp     [rsp+150h+var_F8], r14
0x1400540e5  jz      short loc_1400540F1
0x1400540e7  lea     rcx, [rsp+150h+var_F8]
0x1400540ec  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1400540f1  mov     rdx, [r13+10h]
0x1400540f5  mov     rdx, [rdx]
0x1400540f8  lea     rcx, [rbp+50h+var_70]
0x1400540fc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140054101  nop
0x140054102  mov     r8b, 20h ; ' '
0x140054105  lea     rdx, [rbp+50h+var_70]
0x140054109  lea     rcx, [rsp+150h+var_E0]
0x14005410e  call    ?SplitString@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@D@Z; SplitString(std::wstring const &,char)
0x140054113  nop
0x140054114  mov     rax, qword ptr [rsp+150h+var_E0+8]
0x140054119  mov     rdx, qword ptr [rsp+150h+var_E0]
0x14005411e  sub     rax, rdx
0x140054121  sar     rax, 5
0x140054125  mov     esi, 6
0x14005412a  cmp     rax, rsi
0x14005412d  jbe     loc_140054238
0x140054133  test    al, 1
0x140054135  jnz     loc_140054238
0x14005413b  cmp     rax, 7
0x14005413f  jbe     loc_140054238
0x140054145  mov     rdi, rsi
0x140054148  shl     rdi, 5
0x14005414c  lea     rcx, [rdi+rdx]
0x140054150  mov     rdx, [rcx+10h]
0x140054154  cmp     qword ptr [rcx+18h], 7
0x140054159  jbe     short loc_14005415E
0x14005415b  mov     rcx, [rcx]
0x14005415e  mov     r9d, 9
0x140054164  lea     r8, aUsewinui3; "UseWinUI3"
0x14005416b  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x140054170  test    al, al
0x140054172  jz      short loc_1400541BC
0x140054174  mov     [rsp+150h+var_100], 1
0x140054179  lea     rdx, [rsp+150h+var_100]
0x14005417e  lea     rcx, [rsp+150h+var_F8]
0x140054183  call    ??$box_value@_N$0A@@winrt@@YA?AUIInspectable@Foundation@Windows@0@AEB_N@Z; winrt::box_value<bool,0>(bool const &)
0x140054188  mov     rbx, rax
0x14005418b  mov     rdx, qword ptr [rsp+150h+var_E0]
0x140054190  add     rdx, rdi
0x140054193  lea     rcx, [rbp+50h+var_B8]
0x140054197  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x14005419c  mov     r8, rbx
0x14005419f  lea     rdx, [rbp+50h+var_B8]
0x1400541a3  lea     rcx, [rsp+150h+var_F0]
0x1400541a8  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x1400541ad  nop
0x1400541ae  cmp     [rsp+150h+var_F8], r14
0x1400541b3  jz      short loc_140054216
0x1400541b5  lea     rcx, [rsp+150h+var_F8]
0x1400541ba  jmp     short loc_140054211
0x1400541bc  mov     rdx, qword ptr [rsp+150h+var_E0]
0x1400541c1  add     rdx, 20h ; ' '
0x1400541c5  add     rdx, rdi
0x1400541c8  lea     rcx, [rbp+50h+var_B8]
0x1400541cc  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x1400541d1  lea     rdx, [rbp+50h+var_B8]; struct winrt::param::hstring *
0x1400541d5  lea     rcx, [rsp+150h+var_E8]; this
0x1400541da  call    ?box_value@winrt@@YA?AUIInspectable@Foundation@Windows@1@AEBUhstring@param@1@@Z; winrt::box_value(winrt::param::hstring const &)
0x1400541df  mov     rbx, rax
0x1400541e2  mov     rdx, qword ptr [rsp+150h+var_E0]
0x1400541e7  add     rdx, rdi
0x1400541ea  lea     rcx, [rbp+50h+var_98]
0x1400541ee  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x1400541f3  mov     r8, rbx
0x1400541f6  lea     rdx, [rbp+50h+var_98]
0x1400541fa  lea     rcx, [rsp+150h+var_F0]
0x1400541ff  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x140054204  nop
0x140054205  cmp     [rsp+150h+var_E8], r14
0x14005420a  jz      short loc_140054216
0x14005420c  lea     rcx, [rsp+150h+var_E8]
0x140054211  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x140054216  add     rsi, 2
0x14005421a  mov     rcx, qword ptr [rsp+150h+var_E0+8]
0x14005421f  mov     rdx, qword ptr [rsp+150h+var_E0]
0x140054224  sub     rcx, rdx
0x140054227  sar     rcx, 5
0x14005422b  lea     rax, [rsi+1]
0x14005422f  cmp     rax, rcx
0x140054232  jb      loc_140054145
0x140054238  lea     rcx, [rbp+50h+var_C8]; this
0x14005423c  call    ??0ValueSet@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::ValueSet::ValueSet(void)
0x140054241  nop
0x140054242  lea     rdx, aInvocationprop; "InvocationProperties"
0x140054249  lea     rcx, [rbp+50h+var_B8]; this
0x14005424d  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x140054252  lea     r8, [rsp+150h+var_F0]
0x140054257  lea     rdx, [rbp+50h+var_B8]
0x14005425b  lea     rcx, [rbp+50h+var_C8]
0x14005425f  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x140054264  mov     rbx, [r13+48h]
0x140054268  mov     rdi, [r13+40h]
0x14005426c  mov     rsi, [r13+38h]
0x140054270  mov     r14, [r13+30h]
0x140054274  mov     r15, [r13+28h]
0x140054278  mov     r12, [r13+20h]
0x14005427c  mov     r13, [r13+18h]
0x140054280  lea     rdx, qword_14006BB60; unsigned __int16 *
0x140054287  lea     rcx, [rsp+150h+var_F8]; this
0x14005428c  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x140054291  nop
0x140054292  lea     rax, [rbp+50h+var_C8]
0x140054296  mov     [rsp+150h+var_110], rax; __int64
0x14005429b  mov     [rsp+150h+var_118], rbx; __int64
0x1400542a0  mov     [rsp+150h+var_120], rdi; __int64
0x1400542a5  mov     [rsp+150h+var_128], rsi; __int64
0x1400542aa  mov     [rsp+150h+var_130], r14; ValueSetUtils *
0x1400542af  mov     r9, r15; winrt::hstring *
0x1400542b2  mov     r8, r12; winrt::hstring *
0x1400542b5  mov     rdx, r13; this
0x1400542b8  lea     rcx, [rsp+150h+var_F8]; struct winrt::hstring *
0x1400542bd  call    ?LaunchUXFrameAndWait@@YAXAEBUhstring@winrt@@AEAU12@111AEAV?$vector@U?$pair@Uhstring@winrt@@U12@@std@@V?$allocator@U?$pair@Uhstring@winrt@@U12@@std@@@2@@std@@AEAV?$vector@U?$pair@Uhstring@winrt@@H@std@@V?$allocator@U?$pair@Uhstring@winrt@@H@std@@@2@@4@AEAV?$vector@U?$pair@Uhstring@winrt@@_N@std@@V?$allocator@U?$pair@Uhstring@winrt@@_N@std@@@2@@4@AEBUValueSet@Collections@Foundation@Windows@2@@Z; LaunchUXFrameAndWait(winrt::hstring const &,winrt::hstring &,winrt::hstring &,winrt::hstring &,winrt::hstring &,std::vector<std::pair<winrt::hstring,winrt::hstring>> &,std::vector<std::pair<winrt::hstring,int>> &,std::vector<std::pair<winrt::hstring,bool>> &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x1400542c2  nop
0x1400542c3  lea     rcx, [rsp+150h+var_F8]
0x1400542c8  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x1400542cd  nop
0x1400542ce  lea     rcx, [rbp+50h+var_C8]; this
0x1400542d2  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x1400542d7  nop
0x1400542d8  mov     rcx, qword ptr [rsp+150h+var_E0]
0x1400542dd  test    rcx, rcx
0x1400542e0  jz      short loc_140054312
0x1400542e2  mov     rdx, qword ptr [rsp+150h+var_E0+8]
0x1400542e7  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1400542ec  mov     rcx, qword ptr [rsp+150h+var_E0]
0x1400542f1  mov     rdx, [rbp+50h+var_D0]
0x1400542f5  sub     rdx, rcx
0x1400542f8  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1400542fc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140054301  xorps   xmm0, xmm0
0x140054304  movdqu  [rsp+150h+var_E0], xmm0
0x14005430a  mov     [rbp+50h+var_D0], 0
0x140054312  lea     rcx, [rbp+50h+var_70]
0x140054316  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005431b  nop
0x14005431c  lea     rcx, [rsp+150h+var_F0]; this
0x140054321  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x140054326  mov     rcx, [rbp+50h+var_50]
0x14005432a  xor     rcx, rsp; StackCookie
0x14005432d  call    __security_check_cookie
0x140054332  add     rsp, 118h
0x140054339  pop     r15
0x14005433b  pop     r14
0x14005433d  pop     r13
0x14005433f  pop     r12
0x140054341  pop     rdi
0x140054342  pop     rsi
0x140054343  pop     rbx
0x140054344  pop     rbp
0x140054345  retn
```
