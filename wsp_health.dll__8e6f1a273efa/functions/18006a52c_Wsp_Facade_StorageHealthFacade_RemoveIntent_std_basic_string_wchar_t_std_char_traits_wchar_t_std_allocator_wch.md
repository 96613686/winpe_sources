# Wsp::Facade::StorageHealthFacade::RemoveIntent(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiContext &)

- ea: `0x18006a52c`
- end: `0x18006a864`
- name: `?RemoveIntent@StorageHealthFacade@Facade@Wsp@@QEBAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVMiContext@mi@@@Z`
- size: `824`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800547b8`

## callees

- `0x1800010f8`
- `0x1800011a0`
- `0x1800013d0`
- `0x18000163c`
- `0x180002b50`
- `0x1800035c0`
- `0x18000c2f8`
- `0x18000cd54`
- `0x18000cd9c`
- `0x18000d524`
- `0x18000da34`
- `0x18000daf8`
- `0x18000e4b8`
- `0x18000f34c`
- `0x180011184`
- `0x18001e9e0`
- `0x180055020`
- `0x18005ac4c`
- `0x1800694d4`
- `0x18006a52c`
- `0x180079510`
- `0x1800795d8`

## string_xrefs

- `0x18006a773`: `No connection to the Health Service.`
- `0x18006a829`: `The Health Service is not online.`
- `0x18006a5d9`: `RemoveIntent on {0}`
- `0x18006a55a`: `Wsp::Facade::StorageHealthFacade::RemoveIntent`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
double __fastcall Wsp::Facade::StorageHealthFacade::RemoveIntent(__int64 a1, __int64 a2, int a3, int a4)
{
  struct cxl::TextWriter *v6; // rax
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  char *v10; // rbx
  const wchar_t *v11; // rax
  const wchar_t *v12; // rdx
  bool v13; // r9
  int v14; // eax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int v18; // ebx
  struct cxl::TraceManager *v19; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  _BYTE v29[4]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v30[3]; // [rsp+44h] [rbp-BCh] BYREF
  const char *v31; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v33[32]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v34[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+A0h] [rbp-60h] BYREF

  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    v30[0] = 1044;
    *(_QWORD *)&v30[1] = "Wsp::Facade::StorageHealthFacade::RemoveIntent";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned int)byte_18012CE55,
      a3,
      a4,
      (__int64)&v30[1],
      (__int64)v30);
  }
  if ( !(unsigned int)Wsp::Facade::StorageHealthFacade::GetSubsystemType(a1) )
  {
    v25 = std::wstring::wstring(v33, L"non highlyavailable subsystems are not supported");
    v26 = cxl::SMResult(&v31, 59001, v25);
    cxl::Error(pExceptionObject, v26);
    throw (cxl::Exception *)pExceptionObject;
  }
  Wsp::Health::HealthOperation::HealthOperation((Wsp::Health::HealthOperation *)v29);
  v34[0] = 0;
  v34[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v34[0]) = 0;
  v6 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v33, v34);
  cxl::TextWriter::Write<wchar_t,std::wstring,>(v6, (wchar_t *)L"RemoveIntent on {0}");
  std::wstring::wstring(v33, v34);
  if ( (unsigned int)dword_18014D6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014D6A8, 0x4000) )
  {
    *(_QWORD *)&v30[1] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v33);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v7,
      (unsigned int)qword_18012CD50,
      v8,
      v9,
      (__int64)&v30[1]);
  }
  v10 = (char *)cxl::TraceManager::Instance() + 160;
  cxl::CxlTraits<std::wstring>::WriteTo(v10, v33);
  cxl::TextWriter::operator<<<cxl::ENDL>(v10);
  std::wstring::_Tidy_deallocate(v33);
  v11 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
  v14 = Wsp::Health::HealthOperation::ClearOperation((Wsp::Health::HealthOperation *)v29, v12, v11, v13);
  v18 = v14;
  if ( v14 < 0 )
  {
    v30[0] = v14;
    if ( (unsigned int)dword_18014D6A8 > 2 )
    {
      v32 = v30[0];
      v30[1] = 1061;
      v31 = "Wsp::Facade::StorageHealthFacade::RemoveIntent";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v30[0],
        (unsigned int)&unk_18012CD70,
        v16,
        v17,
        (__int64)&v31,
        (__int64)&v30[1],
        (__int64)&v32);
    }
    v19 = cxl::TraceManager::Instance();
    v30[1] = 1061;
    cxl::TextWriter::WriteLine<wchar_t,char [47],int,long>((struct cxl::TraceManager *)((char *)v19 + 40), (__int64)v30);
  }
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    v30[1] = 1067;
    v31 = "Wsp::Facade::StorageHealthFacade::RemoveIntent";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v15,
      (unsigned int)byte_18012CCF5,
      v16,
      v17,
      (__int64)&v31,
      (__int64)&v30[1]);
  }
  if ( v18 < 0 )
  {
    if ( v18 != -2147024786 )
    {
      if ( v18 == -2147019892 )
      {
        v27 = std::wstring::wstring(v33, L"The Health Service is not online.");
        v28 = cxl::SMResult(&v31, 59006, v27);
        cxl::Error(pExceptionObject, v28);
        throw (cxl::Exception *)pExceptionObject;
      }
      v23 = std::wstring::wstring(v33, L"The operation failed");
      v24 = cxl::SMResult(&v31, 4, v23);
      cxl::Error(pExceptionObject, v24);
      throw (cxl::Exception *)pExceptionObject;
    }
    v21 = std::wstring::wstring(v33, L"No connection to the Health Service.");
    v22 = cxl::SMResult(&v31, 59000, v21);
    cxl::Error(pExceptionObject, v22);
    throw (cxl::Exception *)pExceptionObject;
  }
  return std::wstring::_Tidy_deallocate(v34);
}

```

## disassembly

```asm
0x18006a52c  mov     [rsp-8+arg_10], rbx
0x18006a531  push    rbp
0x18006a532  push    rsi
0x18006a533  push    rdi
0x18006a534  lea     rbp, [rsp-20h]
0x18006a539  sub     rsp, 120h
0x18006a540  mov     rax, cs:__security_cookie
0x18006a547  xor     rax, rsp
0x18006a54a  mov     [rbp+30h+var_20], rax
0x18006a54e  mov     rdi, rdx
0x18006a551  mov     rbx, rcx
0x18006a554  mov     eax, cs:dword_18014D6A8
0x18006a55a  lea     rsi, aWspFacadeStora_6; "Wsp::Facade::StorageHealthFacade::Remov"...
0x18006a561  cmp     eax, 5
0x18006a564  jbe     short loc_18006A593
0x18006a566  mov     dword ptr [rsp+130h+var_EC], 414h
0x18006a56e  mov     qword ptr [rsp+130h+var_EC+4], rsi
0x18006a573  lea     rax, [rsp+130h+var_EC]
0x18006a578  mov     [rsp+130h+var_108], rax
0x18006a57d  lea     rax, [rsp+130h+var_EC+4]
0x18006a582  mov     [rsp+130h+var_110], rax
0x18006a587  lea     rdx, byte_18012CE55
0x18006a58e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006a593  mov     rcx, rbx
0x18006a596  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x18006a59b  test    eax, eax
0x18006a59d  jz      loc_18006A7E9
0x18006a5a3  lea     rcx, [rsp+130h+var_F0]; this
0x18006a5a8  call    ??0HealthOperation@Health@Wsp@@QEAA@XZ; Wsp::Health::HealthOperation::HealthOperation(void)
0x18006a5ad  xorps   xmm0, xmm0
0x18006a5b0  movups  [rbp+30h+var_B0], xmm0
0x18006a5b4  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18006a5bc  movdqu  [rbp+30h+var_A0], xmm1
0x18006a5c1  xor     eax, eax
0x18006a5c3  mov     word ptr [rbp+30h+var_B0], ax
0x18006a5c7  lea     rdx, [rbp+30h+var_B0]
0x18006a5cb  lea     rcx, [rsp+130h+var_D0]
0x18006a5d0  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18006a5d5  nop
0x18006a5d6  mov     r8, rdi
0x18006a5d9  lea     rdx, aRemoveintentOn; "RemoveIntent on {0}"
0x18006a5e0  mov     rcx, rax; struct cxl::TextWriter *
0x18006a5e3  call    ??$Write@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<wchar_t,std::wstring,>(wchar_t const *,std::wstring const &)
0x18006a5e8  nop
0x18006a5e9  lea     rdx, [rbp+30h+var_B0]
0x18006a5ed  lea     rcx, [rsp+130h+var_D0]
0x18006a5f2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006a5f7  nop
0x18006a5f8  mov     eax, cs:dword_18014D6A8
0x18006a5fe  cmp     eax, 5
0x18006a601  jbe     short loc_18006A63D
0x18006a603  mov     edx, 4000h
0x18006a608  lea     rcx, dword_18014D6A8
0x18006a60f  call    _tlgKeywordOn
0x18006a614  test    al, al
0x18006a616  jz      short loc_18006A63D
0x18006a618  lea     rcx, [rsp+130h+var_D0]
0x18006a61d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006a622  mov     qword ptr [rsp+130h+var_EC+4], rax
0x18006a627  lea     rax, [rsp+130h+var_EC+4]
0x18006a62c  mov     [rsp+130h+var_110], rax
0x18006a631  lea     rdx, qword_18012CD50
0x18006a638  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18006a63d  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006a642  lea     rbx, [rax+0A0h]
0x18006a649  lea     rdx, [rsp+130h+var_D0]
0x18006a64e  mov     rcx, rbx
0x18006a651  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x18006a656  mov     rcx, rbx
0x18006a659  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006a65e  nop
0x18006a65f  lea     rcx, [rsp+130h+var_D0]
0x18006a664  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006a669  mov     rcx, rdi
0x18006a66c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006a671  mov     r8, rax; wchar_t *
0x18006a674  lea     rcx, [rsp+130h+var_F0]; this
0x18006a679  call    ?ClearOperation@HealthOperation@Health@Wsp@@QEAAJQEB_W0_N@Z; Wsp::Health::HealthOperation::ClearOperation(wchar_t const * const,wchar_t const * const,bool)
0x18006a67e  mov     ebx, eax
0x18006a680  test    eax, eax
0x18006a682  jns     short loc_18006A6F4
0x18006a684  mov     dword ptr [rsp+130h+var_EC], eax
0x18006a688  mov     ecx, cs:dword_18014D6A8
0x18006a68e  mov     edi, 425h
0x18006a693  cmp     ecx, 2
0x18006a696  jbe     short loc_18006A6D3
0x18006a698  mov     ecx, dword ptr [rsp+130h+var_EC]
0x18006a69c  mov     [rsp+130h+var_D8], ecx
0x18006a6a0  mov     dword ptr [rsp+130h+var_EC+4], edi
0x18006a6a4  mov     [rsp+130h+var_E0], rsi
0x18006a6a9  lea     rax, [rsp+130h+var_D8]
0x18006a6ae  mov     [rsp+130h+var_100], rax
0x18006a6b3  lea     rax, [rsp+130h+var_EC+4]
0x18006a6b8  mov     [rsp+130h+var_108], rax
0x18006a6bd  lea     rax, [rsp+130h+var_E0]
0x18006a6c2  mov     [rsp+130h+var_110], rax
0x18006a6c7  lea     rdx, unk_18012CD70
0x18006a6ce  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006a6d3  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006a6d8  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x18006a6dc  mov     dword ptr [rsp+130h+var_EC+4], edi
0x18006a6e0  lea     rax, [rsp+130h+var_EC]
0x18006a6e5  mov     [rsp+130h+var_110], rax; __int64
0x18006a6ea  lea     r9, [rsp+130h+var_EC+4]
0x18006a6ef  call    ??$WriteLine@_W$$BY0CP@DHJ@TextWriter@cxl@@QEAAXPEB_WAEAY0CP@$$CBDAEBHAEBJ@Z; cxl::TextWriter::WriteLine<wchar_t,char [47],int,long>(wchar_t const *,char const (&)[47],int const &,long const &)
0x18006a6f4  mov     eax, cs:dword_18014D6A8
0x18006a6fa  cmp     eax, 5
0x18006a6fd  jbe     short loc_18006A72C
0x18006a6ff  mov     dword ptr [rsp+130h+var_EC+4], 42Bh
0x18006a707  mov     [rsp+130h+var_E0], rsi
0x18006a70c  lea     rax, [rsp+130h+var_EC+4]
0x18006a711  mov     [rsp+130h+var_108], rax
0x18006a716  lea     rax, [rsp+130h+var_E0]
0x18006a71b  mov     [rsp+130h+var_110], rax
0x18006a720  lea     rdx, byte_18012CCF5
0x18006a727  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006a72c  test    ebx, ebx
0x18006a72e  jns     short loc_18006A74A
0x18006a730  lea     rcx, [rsp+130h+var_D0]
0x18006a735  cmp     ebx, 8007006Eh
0x18006a73b  jz      short loc_18006A773
0x18006a73d  cmp     ebx, 8007138Ch
0x18006a743  jnz     short loc_18006A7AE
0x18006a745  jmp     loc_18006A829
0x18006a74a  lea     rcx, [rbp+30h+var_B0]
0x18006a74e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006a753  mov     rcx, [rbp+30h+var_20]
0x18006a757  xor     rcx, rsp; StackCookie
0x18006a75a  call    __security_check_cookie
0x18006a75f  mov     rbx, [rsp+130h+arg_10]
0x18006a767  add     rsp, 120h
0x18006a76e  pop     rdi
0x18006a76f  pop     rsi
0x18006a770  pop     rbp
0x18006a771  retn
0x18006a773  lea     rdx, aNoConnectionTo; "No connection to the Health Service."
0x18006a77a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006a77f  mov     r8, rax
0x18006a782  mov     edx, 0E678h
0x18006a787  lea     rcx, [rsp+130h+var_E0]
0x18006a78c  call    ?SMResult@cxl@@YA?AVErrorCode@1@H@Z; cxl::SMResult(int)
0x18006a791  mov     rdx, rax
0x18006a794  lea     rcx, [rbp+30h+pExceptionObject]
0x18006a798  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x18006a79d  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006a7a4  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x18006a7a8  call    _CxxThrowException_0
0x18006a7ae  lea     rdx, aTheOperationFa_0; "The operation failed"
0x18006a7b5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006a7ba  mov     r8, rax
0x18006a7bd  mov     edx, 4
0x18006a7c2  lea     rcx, [rsp+130h+var_E0]
0x18006a7c7  call    ?SMResult@cxl@@YA?AVErrorCode@1@H@Z; cxl::SMResult(int)
0x18006a7cc  mov     rdx, rax
0x18006a7cf  lea     rcx, [rbp+30h+pExceptionObject]
0x18006a7d3  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x18006a7d8  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006a7df  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x18006a7e3  call    _CxxThrowException_0
0x18006a7e9  lea     rdx, aNonHighlyavail; "non highlyavailable subsystems are not "...
0x18006a7f0  lea     rcx, [rsp+130h+var_D0]
0x18006a7f5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006a7fa  mov     r8, rax
0x18006a7fd  mov     edx, 0E679h
0x18006a802  lea     rcx, [rsp+130h+var_E0]
0x18006a807  call    ?SMResult@cxl@@YA?AVErrorCode@1@H@Z; cxl::SMResult(int)
0x18006a80c  mov     rdx, rax
0x18006a80f  lea     rcx, [rbp+30h+pExceptionObject]
0x18006a813  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x18006a818  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006a81f  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x18006a823  call    _CxxThrowException_0
0x18006a829  lea     rdx, aTheHealthServi; "The Health Service is not online."
0x18006a830  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006a835  mov     r8, rax
0x18006a838  mov     edx, 0E67Eh
0x18006a83d  lea     rcx, [rsp+130h+var_E0]
0x18006a842  call    ?SMResult@cxl@@YA?AVErrorCode@1@H@Z; cxl::SMResult(int)
0x18006a847  mov     rdx, rax
0x18006a84a  lea     rcx, [rbp+30h+pExceptionObject]
0x18006a84e  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x18006a853  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006a85a  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x18006a85e  call    _CxxThrowException_0
```
