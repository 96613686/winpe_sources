# Wsp::Facade::StorageHealthFacade::S2DEnabled(Wsp::Facade::MaintenanceModeStruct &)

- ea: `0x18006aa28`
- end: `0x18006ae16`
- name: `?S2DEnabled@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEAUMaintenanceModeStruct@23@@Z`
- size: `1006`
- prototype: ``
- caller_count: `4`
- callee_count: `24`
- tags: ``

## callers

- `0x180061f90`
- `0x180062798`
- `0x180063988`
- `0x180064604`

## callees

- `0x1800010f8`
- `0x1800013d0`
- `0x18000163c`
- `0x180002b50`
- `0x18000bc64`
- `0x18000c2f8`
- `0x18000cd54`
- `0x18000cd9c`
- `0x18000da34`
- `0x18000daf8`
- `0x18000e4b8`
- `0x18000f34c`
- `0x180011184`
- `0x18002d290`
- `0x18003489c`
- `0x18003fe04`
- `0x18004035c`
- `0x18004065c`
- `0x1800407a8`
- `0x18004262c`
- `0x180042718`
- `0x18005a1fc`
- `0x18006aa28`
- `0x180082ad0`

## string_xrefs

- `0x18006ac4c`: `S2DCacheDesiredState propertyNotFound`
- `0x18006abd8`: `S2DCacheDesiredState`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Wsp::Facade::StorageHealthFacade::S2DEnabled(int a1, __int64 a2, int a3, int a4)
{
  __int64 v5; // rax
  char v6; // bl
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  char *v10; // rbx
  bool v11; // al
  __int64 v12; // rax
  __int64 v13; // rax
  char v14; // bl
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  char *v18; // rbx
  int value; // eax
  struct cxl::TextWriter *v20; // rax
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  char *v24; // rbx
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  std::_Ref_count_base *v28; // rcx
  const char *v30; // [rsp+38h] [rbp-D0h] BYREF
  int v31; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE v32[32]; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v33; // [rsp+70h] [rbp-98h]
  _BYTE v34[32]; // [rsp+80h] [rbp-88h] BYREF
  _OWORD v35[2]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v36[40]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v37[144]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v38[144]; // [rsp+178h] [rbp+70h] BYREF

  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    v31 = 3010;
    v30 = "Wsp::Facade::StorageHealthFacade::S2DEnabled";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned int)byte_18012B5FB,
      a3,
      a4,
      (__int64)&v30,
      (__int64)&v31);
  }
  v33 = 0;
  v35[0] = 0;
  v35[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v35[0]) = 0;
  cxl::PropertyList::PropertyList((cxl::PropertyList *)v32);
  ClusApi::Facade::FacadeObject::GetProperties(*(_QWORD *)(a2 + 160), 15, v32);
  std::wstring::wstring(v36, L"S2DEnabled");
  cxl::PropertyList::find(v32, v37, v36);
  std::wstring::_Tidy_deallocate(v36);
  v5 = cxl::PropertyList::end(v32, v38);
  v6 = cxl::PropertyList::property_iterator::operator==(v37, v5);
  cxl::PropertyList::property_iterator::~property_iterator((cxl::PropertyList::property_iterator *)v38);
  if ( v6 )
  {
    std::wstring::wstring(v34, L"S2DEnabled property not found");
    if ( (unsigned int)dword_18014D6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014D6A8, 0x4000) )
    {
      v30 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v34);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        v7,
        (unsigned int)byte_18012B629,
        v8,
        v9,
        (__int64)&v30);
    }
    v10 = (char *)cxl::TraceManager::Instance() + 160;
    cxl::CxlTraits<std::wstring>::WriteTo(v10, v34);
    cxl::TextWriter::operator<<<cxl::ENDL>(v10);
    std::wstring::_Tidy_deallocate(v34);
    v11 = 0;
  }
  else
  {
    v11 = (unsigned int)cxl::property_data_trait<unsigned long>::get_value(v37) != 0;
  }
  *(_BYTE *)(a2 + 155) = v11;
  std::wstring::wstring(v34, L"S2DCacheDesiredState");
  v12 = cxl::PropertyList::find(v32, v38, v34);
  cxl::PropertyList::property_iterator::operator=(v37, v12);
  cxl::PropertyList::property_iterator::~property_iterator((cxl::PropertyList::property_iterator *)v38);
  std::wstring::_Tidy_deallocate(v34);
  v13 = cxl::PropertyList::end(v32, v38);
  v14 = cxl::PropertyList::property_iterator::operator==(v37, v13);
  cxl::PropertyList::property_iterator::~property_iterator((cxl::PropertyList::property_iterator *)v38);
  if ( v14 )
  {
    std::wstring::wstring(v34, L"S2DCacheDesiredState propertyNotFound");
    if ( (unsigned int)dword_18014D6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014D6A8, 0x4000) )
    {
      v30 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v34);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        v15,
        (unsigned int)byte_18012B649,
        v16,
        v17,
        (__int64)&v30);
    }
    v18 = (char *)cxl::TraceManager::Instance() + 160;
    cxl::CxlTraits<std::wstring>::WriteTo(v18, v34);
    cxl::TextWriter::operator<<<cxl::ENDL>(v18);
    std::wstring::_Tidy_deallocate(v34);
    value = 0;
  }
  else
  {
    value = cxl::property_data_trait<unsigned long>::get_value(v37);
  }
  *(_DWORD *)(a2 + 156) = value;
  v20 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v34, v35);
  cxl::TextWriter::Write<char,bool,enum S2DCacheMode>(v20);
  std::wstring::wstring(v34, v35);
  if ( (unsigned int)dword_18014D6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014D6A8, 0x4000) )
  {
    v30 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v34);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v21,
      (unsigned int)&word_18012B58E,
      v22,
      v23,
      (__int64)&v30);
  }
  v24 = (char *)cxl::TraceManager::Instance() + 160;
  cxl::CxlTraits<std::wstring>::WriteTo(v24, v34);
  cxl::TextWriter::operator<<<cxl::ENDL>(v24);
  std::wstring::_Tidy_deallocate(v34);
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    v31 = 3044;
    v30 = "Wsp::Facade::StorageHealthFacade::S2DEnabled";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v25,
      (unsigned int)&word_18012B5AE,
      v26,
      v27,
      (__int64)&v30,
      (__int64)&v31);
  }
  cxl::PropertyList::property_iterator::~property_iterator((cxl::PropertyList::property_iterator *)v37);
  cxl::PropertyList::~PropertyList((cxl::PropertyList *)v32);
  std::wstring::_Tidy_deallocate(v35);
  v28 = (std::_Ref_count_base *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
  return 0;
}

```

## disassembly

```asm
0x18006aa28  mov     rax, rsp
0x18006aa2b  push    rbp
0x18006aa2c  push    rbx
0x18006aa2d  push    rsi
0x18006aa2e  push    rdi
0x18006aa2f  push    r12
0x18006aa31  push    r14
0x18006aa33  lea     rbp, [rax-158h]
0x18006aa3a  sub     rsp, 228h
0x18006aa41  movaps  xmmword ptr [rax-48h], xmm6
0x18006aa45  mov     rax, cs:__security_cookie
0x18006aa4c  xor     rax, rsp
0x18006aa4f  mov     [rbp+150h+var_50], rax
0x18006aa56  mov     rdi, rdx
0x18006aa59  mov     eax, cs:dword_18014D6A8
0x18006aa5f  lea     r12, aWspFacadeStora_5; "Wsp::Facade::StorageHealthFacade::S2DEn"...
0x18006aa66  cmp     eax, 5
0x18006aa69  jbe     short loc_18006AA98
0x18006aa6b  mov     [rsp+250h+var_218], 0BC2h
0x18006aa73  mov     [rsp+250h+var_220], r12
0x18006aa78  lea     rax, [rsp+250h+var_218]
0x18006aa7d  mov     [rsp+250h+var_228], rax
0x18006aa82  lea     rax, [rsp+250h+var_220]
0x18006aa87  mov     [rsp+250h+var_230], rax
0x18006aa8c  lea     rdx, byte_18012B5FB
0x18006aa93  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006aa98  xorps   xmm6, xmm6
0x18006aa9b  movdqu  [rsp+250h+var_1F0+8], xmm6
0x18006aaa1  xorps   xmm0, xmm0
0x18006aaa4  movups  [rbp+150h+var_1B8], xmm0
0x18006aaa8  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18006aab0  movdqu  [rbp+150h+var_1A8], xmm1
0x18006aab5  xor     eax, eax
0x18006aab7  mov     word ptr [rbp+150h+var_1B8], ax
0x18006aabb  lea     rcx, [rsp+250h+var_210]; this
0x18006aac0  call    ??0PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::PropertyList(void)
0x18006aac5  nop
0x18006aac6  lea     r8, [rsp+250h+var_210]
0x18006aacb  mov     edx, 0Fh
0x18006aad0  mov     rcx, [rdi+0A0h]
0x18006aad7  call    ?GetProperties@FacadeObject@Facade@ClusApi@@QEBAXW4_PropertyType@3@PEAVPropertyList@cxl@@@Z; ClusApi::Facade::FacadeObject::GetProperties(ClusApi::_PropertyType,cxl::PropertyList *)
0x18006aadc  lea     rdx, aS2denabled; "S2DEnabled"
0x18006aae3  lea     rcx, [rbp+150h+var_198]
0x18006aae7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006aaec  nop
0x18006aaed  lea     r8, [rbp+150h+var_198]
0x18006aaf1  lea     rdx, [rbp+150h+var_170]
0x18006aaf5  lea     rcx, [rsp+250h+var_210]
0x18006aafa  call    ?find@PropertyList@cxl@@QEAA?AVproperty_iterator@12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::PropertyList::find(std::wstring const &)
0x18006aaff  nop
0x18006ab00  lea     rcx, [rbp+150h+var_198]
0x18006ab04  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006ab09  lea     rdx, [rbp+150h+var_E0]
0x18006ab0d  lea     rcx, [rsp+250h+var_210]
0x18006ab12  call    ?end@PropertyList@cxl@@QEAA?AVproperty_iterator@12@XZ; cxl::PropertyList::end(void)
0x18006ab17  mov     rdx, rax
0x18006ab1a  lea     rcx, [rbp+150h+var_170]
0x18006ab1e  call    ??8property_iterator@PropertyList@cxl@@QEBA_NAEBV012@@Z; cxl::PropertyList::property_iterator::operator==(cxl::PropertyList::property_iterator const &)
0x18006ab23  mov     bl, al
0x18006ab25  lea     rcx, [rbp+150h+var_E0]; this
0x18006ab29  call    ??1property_iterator@PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::property_iterator::~property_iterator(void)
0x18006ab2e  mov     r14d, 4000h
0x18006ab34  test    bl, bl
0x18006ab36  jz      loc_18006ABC1
0x18006ab3c  lea     rdx, aS2denabledProp; "S2DEnabled property not found"
0x18006ab43  lea     rcx, [rsp+78h]
0x18006ab48  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006ab4d  nop
0x18006ab4e  mov     eax, cs:dword_18014D6A8
0x18006ab54  cmp     eax, 5
0x18006ab57  jbe     short loc_18006AB91
0x18006ab59  mov     edx, r14d
0x18006ab5c  lea     rcx, dword_18014D6A8
0x18006ab63  call    _tlgKeywordOn
0x18006ab68  test    al, al
0x18006ab6a  jz      short loc_18006AB91
0x18006ab6c  lea     rcx, [rsp+78h]
0x18006ab71  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006ab76  mov     [rsp+250h+var_220], rax
0x18006ab7b  lea     rax, [rsp+250h+var_220]
0x18006ab80  mov     [rsp+250h+var_230], rax
0x18006ab85  lea     rdx, byte_18012B629
0x18006ab8c  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18006ab91  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006ab96  lea     rbx, [rax+0A0h]
0x18006ab9d  lea     rdx, [rsp+78h]
0x18006aba2  mov     rcx, rbx
0x18006aba5  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x18006abaa  mov     rcx, rbx
0x18006abad  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006abb2  nop
0x18006abb3  lea     rcx, [rsp+78h]
0x18006abb8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006abbd  xor     al, al
0x18006abbf  jmp     short loc_18006ABCF
0x18006abc1  lea     rcx, [rbp+150h+var_170]
0x18006abc5  call    ?get_value@?$property_data_trait@K@cxl@@SAKAEBV?$shared_ptr@UIValue@cxl@@@std@@@Z; cxl::property_data_trait<ulong>::get_value(std::shared_ptr<cxl::IValue> const &)
0x18006abca  test    eax, eax
0x18006abcc  setnz   al
0x18006abcf  lea     rsi, [rdi+9Bh]
0x18006abd6  mov     [rsi], al
0x18006abd8  lea     rdx, aS2dcachedesire; "S2DCacheDesiredState"
0x18006abdf  lea     rcx, [rsp+78h]
0x18006abe4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006abe9  nop
0x18006abea  lea     r8, [rsp+78h]
0x18006abef  lea     rdx, [rbp+150h+var_E0]
0x18006abf3  lea     rcx, [rsp+250h+var_210]
0x18006abf8  call    ?find@PropertyList@cxl@@QEAA?AVproperty_iterator@12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::PropertyList::find(std::wstring const &)
0x18006abfd  nop
0x18006abfe  mov     rdx, rax
0x18006ac01  lea     rcx, [rbp+150h+var_170]
0x18006ac05  call    ??4property_iterator@PropertyList@cxl@@QEAAAEAV012@AEBV012@@Z; cxl::PropertyList::property_iterator::operator=(cxl::PropertyList::property_iterator const &)
0x18006ac0a  nop
0x18006ac0b  lea     rcx, [rbp+150h+var_E0]; this
0x18006ac0f  call    ??1property_iterator@PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::property_iterator::~property_iterator(void)
0x18006ac14  nop
0x18006ac15  lea     rcx, [rsp+78h]
0x18006ac1a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006ac1f  lea     rdx, [rbp+150h+var_E0]
0x18006ac23  lea     rcx, [rsp+250h+var_210]
0x18006ac28  call    ?end@PropertyList@cxl@@QEAA?AVproperty_iterator@12@XZ; cxl::PropertyList::end(void)
0x18006ac2d  mov     rdx, rax
0x18006ac30  lea     rcx, [rbp+150h+var_170]
0x18006ac34  call    ??8property_iterator@PropertyList@cxl@@QEBA_NAEBV012@@Z; cxl::PropertyList::property_iterator::operator==(cxl::PropertyList::property_iterator const &)
0x18006ac39  mov     bl, al
0x18006ac3b  lea     rcx, [rbp+150h+var_E0]; this
0x18006ac3f  call    ??1property_iterator@PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::property_iterator::~property_iterator(void)
0x18006ac44  test    bl, bl
0x18006ac46  jz      loc_18006ACD1
0x18006ac4c  lea     rdx, aS2dcachedesire_0; "S2DCacheDesiredState propertyNotFound"
0x18006ac53  lea     rcx, [rsp+78h]
0x18006ac58  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006ac5d  nop
0x18006ac5e  mov     eax, cs:dword_18014D6A8
0x18006ac64  cmp     eax, 5
0x18006ac67  jbe     short loc_18006ACA1
0x18006ac69  mov     rdx, r14
0x18006ac6c  lea     rcx, dword_18014D6A8
0x18006ac73  call    _tlgKeywordOn
0x18006ac78  test    al, al
0x18006ac7a  jz      short loc_18006ACA1
0x18006ac7c  lea     rcx, [rsp+78h]
0x18006ac81  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006ac86  mov     [rsp+250h+var_220], rax
0x18006ac8b  lea     rax, [rsp+250h+var_220]
0x18006ac90  mov     [rsp+250h+var_230], rax
0x18006ac95  lea     rdx, byte_18012B649
0x18006ac9c  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18006aca1  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006aca6  lea     rbx, [rax+0A0h]
0x18006acad  lea     rdx, [rsp+78h]
0x18006acb2  mov     rcx, rbx
0x18006acb5  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x18006acba  mov     rcx, rbx
0x18006acbd  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006acc2  nop
0x18006acc3  lea     rcx, [rsp+78h]
0x18006acc8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006accd  xor     eax, eax
0x18006accf  jmp     short loc_18006ACDA
0x18006acd1  lea     rcx, [rbp+150h+var_170]
0x18006acd5  call    ?get_value@?$property_data_trait@K@cxl@@SAKAEBV?$shared_ptr@UIValue@cxl@@@std@@@Z; cxl::property_data_trait<ulong>::get_value(std::shared_ptr<cxl::IValue> const &)
0x18006acda  lea     r10, [rdi+9Ch]
0x18006ace1  mov     [r10], eax
0x18006ace4  lea     rdx, [rbp+150h+var_1B8]
0x18006ace8  lea     rcx, [rsp+78h]
0x18006aced  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18006acf2  nop
0x18006acf3  mov     r9, r10
0x18006acf6  mov     r8, rsi
0x18006acf9  mov     rcx, rax; struct cxl::TextWriter *
0x18006acfc  call    ??$Write@D_NW4S2DCacheMode@@@TextWriter@cxl@@QEAAXPEBDAEB_NAEBW4S2DCacheMode@@@Z; cxl::TextWriter::Write<char,bool,S2DCacheMode>(char const *,bool const &,S2DCacheMode const &)
0x18006ad01  nop
0x18006ad02  lea     rdx, [rbp+150h+var_1B8]
0x18006ad06  lea     rcx, [rsp+78h]
0x18006ad0b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006ad10  nop
0x18006ad11  mov     eax, cs:dword_18014D6A8
0x18006ad17  cmp     eax, 5
0x18006ad1a  jbe     short loc_18006AD54
0x18006ad1c  mov     rdx, r14
0x18006ad1f  lea     rcx, dword_18014D6A8
0x18006ad26  call    _tlgKeywordOn
0x18006ad2b  test    al, al
0x18006ad2d  jz      short loc_18006AD54
0x18006ad2f  lea     rcx, [rsp+78h]
0x18006ad34  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006ad39  mov     [rsp+250h+var_220], rax
0x18006ad3e  lea     rax, [rsp+250h+var_220]
0x18006ad43  mov     [rsp+250h+var_230], rax
0x18006ad48  lea     rdx, word_18012B58E
0x18006ad4f  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18006ad54  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006ad59  lea     rbx, [rax+0A0h]
0x18006ad60  lea     rdx, [rsp+78h]
0x18006ad65  mov     rcx, rbx
0x18006ad68  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x18006ad6d  mov     rcx, rbx
0x18006ad70  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006ad75  nop
0x18006ad76  lea     rcx, [rsp+78h]
0x18006ad7b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006ad80  mov     eax, cs:dword_18014D6A8
0x18006ad86  cmp     eax, 5
0x18006ad89  jbe     short loc_18006ADB9
0x18006ad8b  mov     [rsp+250h+var_218], 0BE4h
0x18006ad93  mov     [rsp+250h+var_220], r12
0x18006ad98  lea     rax, [rsp+250h+var_218]
0x18006ad9d  mov     [rsp+250h+var_228], rax
0x18006ada2  lea     rax, [rsp+250h+var_220]
0x18006ada7  mov     [rsp+250h+var_230], rax
0x18006adac  lea     rdx, word_18012B5AE
0x18006adb3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006adb8  nop
0x18006adb9  lea     rcx, [rbp+150h+var_170]; this
0x18006adbd  call    ??1property_iterator@PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::property_iterator::~property_iterator(void)
0x18006adc2  nop
0x18006adc3  lea     rcx, [rsp+250h+var_210]; this
0x18006adc8  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x18006adcd  nop
0x18006adce  lea     rcx, [rbp+150h+var_1B8]
0x18006add2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006add7  nop
0x18006add8  psrldq  xmm6, 8
0x18006addd  movq    rcx, xmm6; this
0x18006ade2  test    rcx, rcx
0x18006ade5  jz      short loc_18006ADEC
0x18006ade7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006adec  xor     eax, eax
0x18006adee  mov     rcx, [rbp+150h+var_50]
0x18006adf5  xor     rcx, rsp; StackCookie
0x18006adf8  call    __security_check_cookie
0x18006adfd  movaps  xmm6, [rsp+250h+var_48+8]
0x18006ae05  add     rsp, 228h
0x18006ae0c  pop     r14
0x18006ae0e  pop     r12
0x18006ae10  pop     rdi
0x18006ae11  pop     rsi
0x18006ae12  pop     rbx
0x18006ae13  pop     rbp
0x18006ae14  retn
```
