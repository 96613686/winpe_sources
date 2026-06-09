# Wsp::Facade::StorageHealthFacade::S2DEnabled(Wsp::Facade::MaintenanceModeStruct &)

- ea: `0x1800691f0`
- end: `0x1800695dd`
- name: `?S2DEnabled@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEAUMaintenanceModeStruct@23@@Z`
- size: `1005`
- prototype: ``
- caller_count: `4`
- callee_count: `24`
- tags: ``

## callers

- `0x180060790`
- `0x180060f98`
- `0x180062184`
- `0x180062e00`

## callees

- `0x1800010f4`
- `0x1800013bc`
- `0x180001620`
- `0x180002ae0`
- `0x18000b8e4`
- `0x18000bf68`
- `0x18000c9a8`
- `0x18000c9f0`
- `0x18000d618`
- `0x18000d6dc`
- `0x18000e044`
- `0x18000eebc`
- `0x180010ca4`
- `0x18002c414`
- `0x1800336fc`
- `0x18003e7d0`
- `0x18003ed18`
- `0x18003f010`
- `0x18003f15c`
- `0x180040f28`
- `0x180041010`
- `0x180058a90`
- `0x1800691f0`
- `0x180080700`

## string_xrefs

- `0x180069414`: `S2DCacheDesiredState propertyNotFound`
- `0x1800693a0`: `S2DCacheDesiredState`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Wsp::Facade::StorageHealthFacade::S2DEnabled(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rax
  char v6; // bl
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  char *v10; // rbx
  bool v11; // al
  __int64 v12; // rax
  __int64 v13; // rax
  char v14; // bl
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  char *v18; // rbx
  int value; // eax
  struct cxl::TextWriter *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r10
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  char *v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  std::_Ref_count_base *v30; // rcx
  const char *v32; // [rsp+38h] [rbp-D0h] BYREF
  int v33; // [rsp+40h] [rbp-C8h]
  _BYTE v34[32]; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v35; // [rsp+70h] [rbp-98h]
  _BYTE v36[32]; // [rsp+80h] [rbp-88h] BYREF
  _OWORD v37[2]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v38[40]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v39[144]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v40[144]; // [rsp+178h] [rbp+70h] BYREF

  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    v33 = 3010;
    v32 = "Wsp::Facade::StorageHealthFacade::S2DEnabled";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (__int64)byte_1801295F3,
      a3,
      a4,
      &v32);
  }
  v35 = 0;
  v37[0] = 0;
  v37[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v37[0]) = 0;
  cxl::PropertyList::PropertyList((cxl::PropertyList *)v34);
  ClusApi::Facade::FacadeObject::GetProperties(*(_QWORD *)(a2 + 160), 15, v34);
  std::wstring::wstring(v38, L"S2DEnabled");
  cxl::PropertyList::find(v34, v39, v38);
  std::wstring::_Tidy_deallocate(v38);
  v5 = cxl::PropertyList::end(v34, v40);
  v6 = cxl::PropertyList::property_iterator::operator==(v39, v5);
  cxl::PropertyList::property_iterator::~property_iterator((cxl::PropertyList::property_iterator *)v40);
  if ( v6 )
  {
    std::wstring::wstring(v36, L"S2DEnabled property not found");
    if ( (unsigned int)dword_18014B6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014B6A8, 0x4000) )
    {
      v32 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v36);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        v7,
        (__int64)byte_180129621,
        v8,
        v9,
        &v32);
    }
    v10 = (char *)cxl::TraceManager::Instance() + 160;
    cxl::CxlTraits<std::wstring>::WriteTo(v10, v36);
    cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v10);
    std::wstring::_Tidy_deallocate(v36);
    v11 = 0;
  }
  else
  {
    v11 = (unsigned int)cxl::property_data_trait<unsigned long>::get_value(v39) != 0;
  }
  *(_BYTE *)(a2 + 155) = v11;
  std::wstring::wstring(v36, L"S2DCacheDesiredState");
  v12 = cxl::PropertyList::find(v34, v40, v36);
  cxl::PropertyList::property_iterator::operator=(v39, v12);
  cxl::PropertyList::property_iterator::~property_iterator((cxl::PropertyList::property_iterator *)v40);
  std::wstring::_Tidy_deallocate(v36);
  v13 = cxl::PropertyList::end(v34, v40);
  v14 = cxl::PropertyList::property_iterator::operator==(v39, v13);
  cxl::PropertyList::property_iterator::~property_iterator((cxl::PropertyList::property_iterator *)v40);
  if ( v14 )
  {
    std::wstring::wstring(v36, L"S2DCacheDesiredState propertyNotFound");
    if ( (unsigned int)dword_18014B6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014B6A8, 0x4000) )
    {
      v32 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v36);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        v15,
        (__int64)byte_180129641,
        v16,
        v17,
        &v32);
    }
    v18 = (char *)cxl::TraceManager::Instance() + 160;
    cxl::CxlTraits<std::wstring>::WriteTo(v18, v36);
    cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v18);
    std::wstring::_Tidy_deallocate(v36);
    value = 0;
  }
  else
  {
    value = cxl::property_data_trait<unsigned long>::get_value(v39);
  }
  *(_DWORD *)(a2 + 156) = value;
  v20 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v36, v37);
  cxl::TextWriter::Write<char,bool,enum S2DCacheMode>(v20, v21, a2 + 155, v22);
  std::wstring::wstring(v36, v37);
  if ( (unsigned int)dword_18014B6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014B6A8, 0x4000) )
  {
    v32 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v36);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v23,
      (__int64)qword_180129558,
      v24,
      v25,
      &v32);
  }
  v26 = (char *)cxl::TraceManager::Instance() + 160;
  cxl::CxlTraits<std::wstring>::WriteTo(v26, v36);
  cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v26);
  std::wstring::_Tidy_deallocate(v36);
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    v33 = 3044;
    v32 = "Wsp::Facade::StorageHealthFacade::S2DEnabled";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v27,
      (__int64)qword_180129578,
      v28,
      v29,
      &v32);
  }
  cxl::PropertyList::property_iterator::~property_iterator((cxl::PropertyList::property_iterator *)v39);
  cxl::PropertyList::~PropertyList((cxl::PropertyList *)v34);
  std::wstring::_Tidy_deallocate(v37);
  v30 = (std::_Ref_count_base *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v30 )
    std::_Ref_count_base::_Decref(v30);
  return 0;
}

```

## disassembly

```asm
0x1800691f0  mov     rax, rsp
0x1800691f3  push    rbp
0x1800691f4  push    rbx
0x1800691f5  push    rsi
0x1800691f6  push    rdi
0x1800691f7  push    r12
0x1800691f9  push    r14
0x1800691fb  lea     rbp, [rax-158h]
0x180069202  sub     rsp, 228h
0x180069209  movaps  xmmword ptr [rax-48h], xmm6
0x18006920d  mov     rax, cs:__security_cookie
0x180069214  xor     rax, rsp
0x180069217  mov     [rbp+150h+var_50], rax
0x18006921e  mov     rdi, rdx
0x180069221  mov     eax, cs:dword_18014B6A8
0x180069227  lea     r12, aWspFacadeStora_5; "Wsp::Facade::StorageHealthFacade::S2DEn"...
0x18006922e  cmp     eax, 5
0x180069231  jbe     short loc_180069260
0x180069233  mov     [rsp+250h+var_218], 0BC2h
0x18006923b  mov     [rsp+250h+var_220], r12
0x180069240  lea     rax, [rsp+250h+var_218]
0x180069245  mov     [rsp+250h+var_228], rax
0x18006924a  lea     rax, [rsp+250h+var_220]
0x18006924f  mov     [rsp+250h+var_230], rax
0x180069254  lea     rdx, byte_1801295F3
0x18006925b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180069260  xorps   xmm6, xmm6
0x180069263  movdqu  [rsp+250h+var_1F0+8], xmm6
0x180069269  xorps   xmm0, xmm0
0x18006926c  movups  [rbp+150h+var_1B8], xmm0
0x180069270  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180069278  movdqu  [rbp+150h+var_1A8], xmm1
0x18006927d  xor     eax, eax
0x18006927f  mov     word ptr [rbp+150h+var_1B8], ax
0x180069283  lea     rcx, [rsp+250h+var_210]; this
0x180069288  call    ??0PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::PropertyList(void)
0x18006928d  nop
0x18006928e  lea     r8, [rsp+250h+var_210]
0x180069293  mov     edx, 0Fh
0x180069298  mov     rcx, [rdi+0A0h]
0x18006929f  call    ?GetProperties@FacadeObject@Facade@ClusApi@@QEBAXW4_PropertyType@3@PEAVPropertyList@cxl@@@Z; ClusApi::Facade::FacadeObject::GetProperties(ClusApi::_PropertyType,cxl::PropertyList *)
0x1800692a4  lea     rdx, aS2denabled; "S2DEnabled"
0x1800692ab  lea     rcx, [rbp+150h+var_198]
0x1800692af  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800692b4  nop
0x1800692b5  lea     r8, [rbp+150h+var_198]
0x1800692b9  lea     rdx, [rbp+150h+var_170]
0x1800692bd  lea     rcx, [rsp+250h+var_210]
0x1800692c2  call    ?find@PropertyList@cxl@@QEAA?AVproperty_iterator@12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::PropertyList::find(std::wstring const &)
0x1800692c7  nop
0x1800692c8  lea     rcx, [rbp+150h+var_198]
0x1800692cc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800692d1  lea     rdx, [rbp+150h+var_E0]
0x1800692d5  lea     rcx, [rsp+250h+var_210]
0x1800692da  call    ?end@PropertyList@cxl@@QEAA?AVproperty_iterator@12@XZ; cxl::PropertyList::end(void)
0x1800692df  mov     rdx, rax
0x1800692e2  lea     rcx, [rbp+150h+var_170]
0x1800692e6  call    ??8property_iterator@PropertyList@cxl@@QEBA_NAEBV012@@Z; cxl::PropertyList::property_iterator::operator==(cxl::PropertyList::property_iterator const &)
0x1800692eb  mov     bl, al
0x1800692ed  lea     rcx, [rbp+150h+var_E0]; this
0x1800692f1  call    ??1property_iterator@PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::property_iterator::~property_iterator(void)
0x1800692f6  mov     r14d, 4000h
0x1800692fc  test    bl, bl
0x1800692fe  jz      loc_180069389
0x180069304  lea     rdx, aS2denabledProp; "S2DEnabled property not found"
0x18006930b  lea     rcx, [rsp+78h]
0x180069310  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180069315  nop
0x180069316  mov     eax, cs:dword_18014B6A8
0x18006931c  cmp     eax, 5
0x18006931f  jbe     short loc_180069359
0x180069321  mov     edx, r14d
0x180069324  lea     rcx, dword_18014B6A8
0x18006932b  call    _tlgKeywordOn
0x180069330  test    al, al
0x180069332  jz      short loc_180069359
0x180069334  lea     rcx, [rsp+78h]
0x180069339  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006933e  mov     [rsp+250h+var_220], rax
0x180069343  lea     rax, [rsp+250h+var_220]
0x180069348  mov     [rsp+250h+var_230], rax
0x18006934d  lea     rdx, byte_180129621
0x180069354  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180069359  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006935e  lea     rbx, [rax+0A0h]
0x180069365  lea     rdx, [rsp+78h]
0x18006936a  mov     rcx, rbx
0x18006936d  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x180069372  mov     rcx, rbx
0x180069375  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006937a  nop
0x18006937b  lea     rcx, [rsp+78h]
0x180069380  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180069385  xor     al, al
0x180069387  jmp     short loc_180069397
0x180069389  lea     rcx, [rbp+150h+var_170]
0x18006938d  call    ?get_value@?$property_data_trait@K@cxl@@SAKAEBV?$shared_ptr@UIValue@cxl@@@std@@@Z; cxl::property_data_trait<ulong>::get_value(std::shared_ptr<cxl::IValue> const &)
0x180069392  test    eax, eax
0x180069394  setnz   al
0x180069397  lea     rsi, [rdi+9Bh]
0x18006939e  mov     [rsi], al
0x1800693a0  lea     rdx, aS2dcachedesire; "S2DCacheDesiredState"
0x1800693a7  lea     rcx, [rsp+78h]
0x1800693ac  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800693b1  nop
0x1800693b2  lea     r8, [rsp+78h]
0x1800693b7  lea     rdx, [rbp+150h+var_E0]
0x1800693bb  lea     rcx, [rsp+250h+var_210]
0x1800693c0  call    ?find@PropertyList@cxl@@QEAA?AVproperty_iterator@12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::PropertyList::find(std::wstring const &)
0x1800693c5  nop
0x1800693c6  mov     rdx, rax
0x1800693c9  lea     rcx, [rbp+150h+var_170]
0x1800693cd  call    ??4property_iterator@PropertyList@cxl@@QEAAAEAV012@AEBV012@@Z; cxl::PropertyList::property_iterator::operator=(cxl::PropertyList::property_iterator const &)
0x1800693d2  nop
0x1800693d3  lea     rcx, [rbp+150h+var_E0]; this
0x1800693d7  call    ??1property_iterator@PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::property_iterator::~property_iterator(void)
0x1800693dc  nop
0x1800693dd  lea     rcx, [rsp+78h]
0x1800693e2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800693e7  lea     rdx, [rbp+150h+var_E0]
0x1800693eb  lea     rcx, [rsp+250h+var_210]
0x1800693f0  call    ?end@PropertyList@cxl@@QEAA?AVproperty_iterator@12@XZ; cxl::PropertyList::end(void)
0x1800693f5  mov     rdx, rax
0x1800693f8  lea     rcx, [rbp+150h+var_170]
0x1800693fc  call    ??8property_iterator@PropertyList@cxl@@QEBA_NAEBV012@@Z; cxl::PropertyList::property_iterator::operator==(cxl::PropertyList::property_iterator const &)
0x180069401  mov     bl, al
0x180069403  lea     rcx, [rbp+150h+var_E0]; this
0x180069407  call    ??1property_iterator@PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::property_iterator::~property_iterator(void)
0x18006940c  test    bl, bl
0x18006940e  jz      loc_180069499
0x180069414  lea     rdx, aS2dcachedesire_0; "S2DCacheDesiredState propertyNotFound"
0x18006941b  lea     rcx, [rsp+78h]
0x180069420  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180069425  nop
0x180069426  mov     eax, cs:dword_18014B6A8
0x18006942c  cmp     eax, 5
0x18006942f  jbe     short loc_180069469
0x180069431  mov     rdx, r14
0x180069434  lea     rcx, dword_18014B6A8
0x18006943b  call    _tlgKeywordOn
0x180069440  test    al, al
0x180069442  jz      short loc_180069469
0x180069444  lea     rcx, [rsp+78h]
0x180069449  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006944e  mov     [rsp+250h+var_220], rax
0x180069453  lea     rax, [rsp+250h+var_220]
0x180069458  mov     [rsp+250h+var_230], rax
0x18006945d  lea     rdx, byte_180129641
0x180069464  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180069469  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006946e  lea     rbx, [rax+0A0h]
0x180069475  lea     rdx, [rsp+78h]
0x18006947a  mov     rcx, rbx
0x18006947d  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x180069482  mov     rcx, rbx
0x180069485  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006948a  nop
0x18006948b  lea     rcx, [rsp+78h]
0x180069490  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180069495  xor     eax, eax
0x180069497  jmp     short loc_1800694A2
0x180069499  lea     rcx, [rbp+150h+var_170]
0x18006949d  call    ?get_value@?$property_data_trait@K@cxl@@SAKAEBV?$shared_ptr@UIValue@cxl@@@std@@@Z; cxl::property_data_trait<ulong>::get_value(std::shared_ptr<cxl::IValue> const &)
0x1800694a2  lea     r10, [rdi+9Ch]
0x1800694a9  mov     [r10], eax
0x1800694ac  lea     rdx, [rbp+150h+var_1B8]
0x1800694b0  lea     rcx, [rsp+78h]
0x1800694b5  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800694ba  nop
0x1800694bb  mov     r9, r10
0x1800694be  mov     r8, rsi
0x1800694c1  mov     rcx, rax; struct cxl::TextWriter *
0x1800694c4  call    ??$Write@D_NW4S2DCacheMode@@@TextWriter@cxl@@QEAAXPEBDAEB_NAEBW4S2DCacheMode@@@Z; cxl::TextWriter::Write<char,bool,S2DCacheMode>(char const *,bool const &,S2DCacheMode const &)
0x1800694c9  nop
0x1800694ca  lea     rdx, [rbp+150h+var_1B8]
0x1800694ce  lea     rcx, [rsp+78h]
0x1800694d3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800694d8  nop
0x1800694d9  mov     eax, cs:dword_18014B6A8
0x1800694df  cmp     eax, 5
0x1800694e2  jbe     short loc_18006951C
0x1800694e4  mov     rdx, r14
0x1800694e7  lea     rcx, dword_18014B6A8
0x1800694ee  call    _tlgKeywordOn
0x1800694f3  test    al, al
0x1800694f5  jz      short loc_18006951C
0x1800694f7  lea     rcx, [rsp+78h]
0x1800694fc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180069501  mov     [rsp+250h+var_220], rax
0x180069506  lea     rax, [rsp+250h+var_220]
0x18006950b  mov     [rsp+250h+var_230], rax
0x180069510  lea     rdx, qword_180129558
0x180069517  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18006951c  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180069521  lea     rbx, [rax+0A0h]
0x180069528  lea     rdx, [rsp+78h]
0x18006952d  mov     rcx, rbx
0x180069530  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x180069535  mov     rcx, rbx
0x180069538  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006953d  nop
0x18006953e  lea     rcx, [rsp+78h]
0x180069543  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180069548  mov     eax, cs:dword_18014B6A8
0x18006954e  cmp     eax, 5
0x180069551  jbe     short loc_180069581
0x180069553  mov     [rsp+250h+var_218], 0BE4h
0x18006955b  mov     [rsp+250h+var_220], r12
0x180069560  lea     rax, [rsp+250h+var_218]
0x180069565  mov     [rsp+250h+var_228], rax
0x18006956a  lea     rax, [rsp+250h+var_220]
0x18006956f  mov     [rsp+250h+var_230], rax
0x180069574  lea     rdx, qword_180129578
0x18006957b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180069580  nop
0x180069581  lea     rcx, [rbp+150h+var_170]; this
0x180069585  call    ??1property_iterator@PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::property_iterator::~property_iterator(void)
0x18006958a  nop
0x18006958b  lea     rcx, [rsp+250h+var_210]; this
0x180069590  call    ??1PropertyList@cxl@@QEAA@XZ; cxl::PropertyList::~PropertyList(void)
0x180069595  nop
0x180069596  lea     rcx, [rbp+150h+var_1B8]
0x18006959a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006959f  nop
0x1800695a0  psrldq  xmm6, 8
0x1800695a5  movq    rcx, xmm6; this
0x1800695aa  test    rcx, rcx
0x1800695ad  jz      short loc_1800695B4
0x1800695af  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800695b4  xor     eax, eax
0x1800695b6  mov     rcx, [rbp+150h+var_50]
0x1800695bd  xor     rcx, rsp; StackCookie
0x1800695c0  call    __security_check_cookie
0x1800695c5  movaps  xmm6, [rsp+250h+var_48+8]
0x1800695cd  add     rsp, 228h
0x1800695d4  pop     r14
0x1800695d6  pop     r12
0x1800695d8  pop     rdi
0x1800695d9  pop     rsi
0x1800695da  pop     rbx
0x1800695db  pop     rbp
0x1800695dc  retn
```
