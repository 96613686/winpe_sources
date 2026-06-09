# Wsp::Facade::StorageHealthFacade::RemoveIntent(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiContext &)

- ea: `0x180068cf4`
- end: `0x18006902b`
- name: `?RemoveIntent@StorageHealthFacade@Facade@Wsp@@QEBAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVMiContext@mi@@@Z`
- size: `823`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x180052dbc`

## callees

- `0x1800010f4`
- `0x18000119c`
- `0x1800013bc`
- `0x180001620`
- `0x180002ae0`
- `0x180003520`
- `0x18000bf68`
- `0x18000c9a8`
- `0x18000c9f0`
- `0x18000d140`
- `0x18000d618`
- `0x18000d6dc`
- `0x18000e044`
- `0x18000eebc`
- `0x180010ca4`
- `0x18001de28`
- `0x180053624`
- `0x1800594d4`
- `0x180067ca8`
- `0x180068cf4`
- `0x18007765c`
- `0x180077720`

## string_xrefs

- `0x180068f3a`: `No connection to the Health Service.`
- `0x180068ff0`: `The Health Service is not online.`
- `0x180068da1`: `RemoveIntent on {0}`
- `0x180068d22`: `Wsp::Facade::StorageHealthFacade::RemoveIntent`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
double __fastcall Wsp::Facade::StorageHealthFacade::RemoveIntent(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  struct cxl::TextWriter *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  char *v10; // rbx
  const wchar_t *v11; // rax
  const wchar_t *v12; // rdx
  bool v13; // r9
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // ebx
  struct cxl::TraceManager *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  _BYTE v31[4]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v32[3]; // [rsp+44h] [rbp-BCh] BYREF
  const char *v33; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+58h] [rbp-A8h]
  _BYTE v35[32]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v36[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+A0h] [rbp-60h] BYREF

  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    v32[0] = 1044;
    *(_QWORD *)&v32[1] = "Wsp::Facade::StorageHealthFacade::RemoveIntent";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (__int64)byte_18012AE4D,
      a3,
      a4,
      &v32[1]);
  }
  if ( !(unsigned int)Wsp::Facade::StorageHealthFacade::GetSubsystemType(a1) )
  {
    v27 = std::wstring::wstring(v35, L"non highlyavailable subsystems are not supported");
    v28 = cxl::SMResult(&v33, 59001, v27);
    cxl::Error(pExceptionObject, v28);
    throw (cxl::Exception *)pExceptionObject;
  }
  Wsp::Health::HealthOperation::HealthOperation((Wsp::Health::HealthOperation *)v31);
  v36[0] = 0;
  v36[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v36[0]) = 0;
  v6 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v35, v36);
  cxl::TextWriter::Write<wchar_t,std::wstring,>(v6, (wchar_t *)L"RemoveIntent on {0}", a2);
  std::wstring::wstring(v35, v36);
  if ( (unsigned int)dword_18014B6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014B6A8, 0x4000) )
  {
    *(_QWORD *)&v32[1] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v35);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v7,
      (__int64)byte_18012AD1B,
      v8,
      v9,
      &v32[1]);
  }
  v10 = (char *)cxl::TraceManager::Instance() + 160;
  cxl::CxlTraits<std::wstring>::WriteTo(v10, v35);
  cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v10);
  std::wstring::_Tidy_deallocate(v35);
  v11 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
  v14 = Wsp::Health::HealthOperation::ClearOperation((Wsp::Health::HealthOperation *)v31, v12, v11, v13);
  v18 = v14;
  if ( v14 < 0 )
  {
    v32[0] = v14;
    if ( (unsigned int)dword_18014B6A8 > 2 )
    {
      v34 = v32[0];
      v32[1] = 1061;
      v33 = "Wsp::Facade::StorageHealthFacade::RemoveIntent";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v32[0],
        (__int64)byte_18012AD3B,
        v16,
        v17,
        &v33);
    }
    v19 = cxl::TraceManager::Instance();
    v32[1] = 1061;
    cxl::TextWriter::WriteLine<wchar_t,char [47],int,long>(
      (struct cxl::TraceManager *)((char *)v19 + 40),
      v20,
      v21,
      (__int64)&v32[1],
      (__int64)v32);
  }
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    v32[1] = 1067;
    v33 = "Wsp::Facade::StorageHealthFacade::RemoveIntent";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v15,
      (__int64)byte_18012AD73,
      v16,
      v17,
      &v33);
  }
  if ( v18 < 0 )
  {
    if ( v18 != -2147024786 )
    {
      if ( v18 == -2147019892 )
      {
        v29 = std::wstring::wstring(v35, L"The Health Service is not online.");
        v30 = cxl::SMResult(&v33, 59006, v29);
        cxl::Error(pExceptionObject, v30);
        throw (cxl::Exception *)pExceptionObject;
      }
      v25 = std::wstring::wstring(v35, L"The operation failed");
      v26 = cxl::SMResult(&v33, 4, v25);
      cxl::Error(pExceptionObject, v26);
      throw (cxl::Exception *)pExceptionObject;
    }
    v23 = std::wstring::wstring(v35, L"No connection to the Health Service.");
    v24 = cxl::SMResult(&v33, 59000, v23);
    cxl::Error(pExceptionObject, v24);
    throw (cxl::Exception *)pExceptionObject;
  }
  return std::wstring::_Tidy_deallocate(v36);
}

```

## disassembly

```asm
0x180068cf4  mov     [rsp-8+arg_10], rbx
0x180068cf9  push    rbp
0x180068cfa  push    rsi
0x180068cfb  push    rdi
0x180068cfc  lea     rbp, [rsp-20h]
0x180068d01  sub     rsp, 120h
0x180068d08  mov     rax, cs:__security_cookie
0x180068d0f  xor     rax, rsp
0x180068d12  mov     [rbp+30h+var_20], rax
0x180068d16  mov     rdi, rdx
0x180068d19  mov     rbx, rcx
0x180068d1c  mov     eax, cs:dword_18014B6A8
0x180068d22  lea     rsi, aWspFacadeStora_6; "Wsp::Facade::StorageHealthFacade::Remov"...
0x180068d29  cmp     eax, 5
0x180068d2c  jbe     short loc_180068D5B
0x180068d2e  mov     dword ptr [rsp+130h+var_EC], 414h
0x180068d36  mov     qword ptr [rsp+130h+var_EC+4], rsi
0x180068d3b  lea     rax, [rsp+130h+var_EC]
0x180068d40  mov     [rsp+130h+var_108], rax
0x180068d45  lea     rax, [rsp+130h+var_EC+4]
0x180068d4a  mov     [rsp+130h+var_110], rax
0x180068d4f  lea     rdx, byte_18012AE4D
0x180068d56  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180068d5b  mov     rcx, rbx
0x180068d5e  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x180068d63  test    eax, eax
0x180068d65  jz      loc_180068FB0
0x180068d6b  lea     rcx, [rsp+130h+var_F0]; this
0x180068d70  call    ??0HealthOperation@Health@Wsp@@QEAA@XZ; Wsp::Health::HealthOperation::HealthOperation(void)
0x180068d75  xorps   xmm0, xmm0
0x180068d78  movups  [rbp+30h+var_B0], xmm0
0x180068d7c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180068d84  movdqu  [rbp+30h+var_A0], xmm1
0x180068d89  xor     eax, eax
0x180068d8b  mov     word ptr [rbp+30h+var_B0], ax
0x180068d8f  lea     rdx, [rbp+30h+var_B0]
0x180068d93  lea     rcx, [rsp+130h+var_D0]
0x180068d98  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180068d9d  nop
0x180068d9e  mov     r8, rdi
0x180068da1  lea     rdx, aRemoveintentOn; "RemoveIntent on {0}"
0x180068da8  mov     rcx, rax; struct cxl::TextWriter *
0x180068dab  call    ??$Write@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@TextWriter@cxl@@QEAAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<wchar_t,std::wstring,>(wchar_t const *,std::wstring const &)
0x180068db0  nop
0x180068db1  lea     rdx, [rbp+30h+var_B0]
0x180068db5  lea     rcx, [rsp+130h+var_D0]
0x180068dba  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180068dbf  nop
0x180068dc0  mov     eax, cs:dword_18014B6A8
0x180068dc6  cmp     eax, 5
0x180068dc9  jbe     short loc_180068E05
0x180068dcb  mov     edx, 4000h
0x180068dd0  lea     rcx, dword_18014B6A8
0x180068dd7  call    _tlgKeywordOn
0x180068ddc  test    al, al
0x180068dde  jz      short loc_180068E05
0x180068de0  lea     rcx, [rsp+130h+var_D0]
0x180068de5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180068dea  mov     qword ptr [rsp+130h+var_EC+4], rax
0x180068def  lea     rax, [rsp+130h+var_EC+4]
0x180068df4  mov     [rsp+130h+var_110], rax
0x180068df9  lea     rdx, byte_18012AD1B
0x180068e00  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180068e05  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180068e0a  lea     rbx, [rax+0A0h]
0x180068e11  lea     rdx, [rsp+130h+var_D0]
0x180068e16  mov     rcx, rbx
0x180068e19  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x180068e1e  mov     rcx, rbx
0x180068e21  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x180068e26  nop
0x180068e27  lea     rcx, [rsp+130h+var_D0]
0x180068e2c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180068e31  mov     rcx, rdi
0x180068e34  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180068e39  mov     r8, rax; wchar_t *
0x180068e3c  lea     rcx, [rsp+130h+var_F0]; this
0x180068e41  call    ?ClearOperation@HealthOperation@Health@Wsp@@QEAAJQEB_W0_N@Z; Wsp::Health::HealthOperation::ClearOperation(wchar_t const * const,wchar_t const * const,bool)
0x180068e46  mov     ebx, eax
0x180068e48  test    eax, eax
0x180068e4a  jns     short loc_180068EBC
0x180068e4c  mov     dword ptr [rsp+130h+var_EC], eax
0x180068e50  mov     ecx, cs:dword_18014B6A8
0x180068e56  mov     edi, 425h
0x180068e5b  cmp     ecx, 2
0x180068e5e  jbe     short loc_180068E9B
0x180068e60  mov     ecx, dword ptr [rsp+130h+var_EC]
0x180068e64  mov     [rsp+130h+var_D8], ecx
0x180068e68  mov     dword ptr [rsp+130h+var_EC+4], edi
0x180068e6c  mov     [rsp+130h+var_E0], rsi
0x180068e71  lea     rax, [rsp+130h+var_D8]
0x180068e76  mov     [rsp+130h+var_100], rax
0x180068e7b  lea     rax, [rsp+130h+var_EC+4]
0x180068e80  mov     [rsp+130h+var_108], rax
0x180068e85  lea     rax, [rsp+130h+var_E0]
0x180068e8a  mov     [rsp+130h+var_110], rax
0x180068e8f  lea     rdx, byte_18012AD3B
0x180068e96  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180068e9b  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180068ea0  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180068ea4  mov     dword ptr [rsp+130h+var_EC+4], edi
0x180068ea8  lea     rax, [rsp+130h+var_EC]
0x180068ead  mov     [rsp+130h+var_110], rax; __int64
0x180068eb2  lea     r9, [rsp+130h+var_EC+4]
0x180068eb7  call    ??$WriteLine@_W$$BY0CP@DHJ@TextWriter@cxl@@QEAAXPEB_WAEAY0CP@$$CBDAEBHAEBJ@Z; cxl::TextWriter::WriteLine<wchar_t,char [47],int,long>(wchar_t const *,char const (&)[47],int const &,long const &)
0x180068ebc  mov     eax, cs:dword_18014B6A8
0x180068ec2  cmp     eax, 5
0x180068ec5  jbe     short loc_180068EF4
0x180068ec7  mov     dword ptr [rsp+130h+var_EC+4], 42Bh
0x180068ecf  mov     [rsp+130h+var_E0], rsi
0x180068ed4  lea     rax, [rsp+130h+var_EC+4]
0x180068ed9  mov     [rsp+130h+var_108], rax
0x180068ede  lea     rax, [rsp+130h+var_E0]
0x180068ee3  mov     [rsp+130h+var_110], rax
0x180068ee8  lea     rdx, byte_18012AD73
0x180068eef  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180068ef4  test    ebx, ebx
0x180068ef6  jns     short loc_180068F12
0x180068ef8  lea     rcx, [rsp+130h+var_D0]
0x180068efd  cmp     ebx, 8007006Eh
0x180068f03  jz      short loc_180068F3A
0x180068f05  cmp     ebx, 8007138Ch
0x180068f0b  jnz     short loc_180068F75
0x180068f0d  jmp     loc_180068FF0
0x180068f12  lea     rcx, [rbp+30h+var_B0]
0x180068f16  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180068f1b  mov     rcx, [rbp+30h+var_20]
0x180068f1f  xor     rcx, rsp; StackCookie
0x180068f22  call    __security_check_cookie
0x180068f27  mov     rbx, [rsp+130h+arg_10]
0x180068f2f  add     rsp, 120h
0x180068f36  pop     rdi
0x180068f37  pop     rsi
0x180068f38  pop     rbp
0x180068f39  retn
0x180068f3a  lea     rdx, aNoConnectionTo; "No connection to the Health Service."
0x180068f41  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180068f46  mov     r8, rax
0x180068f49  mov     edx, 0E678h
0x180068f4e  lea     rcx, [rsp+130h+var_E0]
0x180068f53  call    ?SMResult@cxl@@YA?AVErrorCode@1@H@Z; cxl::SMResult(int)
0x180068f58  mov     rdx, rax
0x180068f5b  lea     rcx, [rbp+30h+pExceptionObject]
0x180068f5f  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x180068f64  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180068f6b  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x180068f6f  call    _CxxThrowException_0
0x180068f75  lea     rdx, aTheOperationFa_0; "The operation failed"
0x180068f7c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180068f81  mov     r8, rax
0x180068f84  mov     edx, 4
0x180068f89  lea     rcx, [rsp+130h+var_E0]
0x180068f8e  call    ?SMResult@cxl@@YA?AVErrorCode@1@H@Z; cxl::SMResult(int)
0x180068f93  mov     rdx, rax
0x180068f96  lea     rcx, [rbp+30h+pExceptionObject]
0x180068f9a  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x180068f9f  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180068fa6  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x180068faa  call    _CxxThrowException_0
0x180068fb0  lea     rdx, aNonHighlyavail; "non highlyavailable subsystems are not "...
0x180068fb7  lea     rcx, [rsp+130h+var_D0]
0x180068fbc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180068fc1  mov     r8, rax
0x180068fc4  mov     edx, 0E679h
0x180068fc9  lea     rcx, [rsp+130h+var_E0]
0x180068fce  call    ?SMResult@cxl@@YA?AVErrorCode@1@H@Z; cxl::SMResult(int)
0x180068fd3  mov     rdx, rax
0x180068fd6  lea     rcx, [rbp+30h+pExceptionObject]
0x180068fda  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x180068fdf  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180068fe6  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x180068fea  call    _CxxThrowException_0
0x180068ff0  lea     rdx, aTheHealthServi; "The Health Service is not online."
0x180068ff7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180068ffc  mov     r8, rax
0x180068fff  mov     edx, 0E67Eh
0x180069004  lea     rcx, [rsp+130h+var_E0]
0x180069009  call    ?SMResult@cxl@@YA?AVErrorCode@1@H@Z; cxl::SMResult(int)
0x18006900e  mov     rdx, rax
0x180069011  lea     rcx, [rbp+30h+pExceptionObject]
0x180069015  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x18006901a  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180069021  lea     rcx, [rbp+30h+pExceptionObject]; pExceptionObject
0x180069025  call    _CxxThrowException_0
```
