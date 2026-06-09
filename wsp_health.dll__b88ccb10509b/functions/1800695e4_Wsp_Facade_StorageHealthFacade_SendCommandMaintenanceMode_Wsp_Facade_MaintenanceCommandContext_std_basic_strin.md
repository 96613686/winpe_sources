# Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode(Wsp::Facade::MaintenanceCommandContext &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,WSP_OBJECT_TYPE const &,bool const &,bool const &,bool const &,bool const &,std::unique_ptr<uint,std::default_delete<uint>> const &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x1800695e4`
- end: `0x180069c1c`
- name: `?SendCommandMaintenanceMode@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEAUMaintenanceCommandContext@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBW4WSP_OBJECT_TYPE@@AEB_N333AEBV?$unique_ptr@IU?$default_delete@I@std@@@7@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@7@@Z`
- size: `1592`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x180060790`
- `0x180062184`

## callees

- `0x1800010f4`
- `0x18000119c`
- `0x1800013bc`
- `0x180001620`
- `0x180002ae0`
- `0x18000bf68`
- `0x18000c4c4`
- `0x18000c9a8`
- `0x18000c9f0`
- `0x18000d618`
- `0x18000d6dc`
- `0x18000e044`
- `0x18000eebc`
- `0x180010ca4`
- `0x180034360`
- `0x180058ec4`
- `0x180058f10`
- `0x18005a784`
- `0x18005bfe0`
- `0x18005ca14`
- `0x180067f80`
- `0x1800695e4`
- `0x180076e88`
- `0x18007a824`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800697fa`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800697fa`

## string_xrefs

- `0x180069632`: `Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode`
- `0x180069961`: `Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode`
- `0x180069999`: `Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode`
- `0x180069a0b`: `Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int *a4,
        _BYTE *a5,
        _BYTE *a6,
        _BYTE *a7,
        _BYTE *a8,
        _QWORD *a9)
{
  struct cxl::TextWriter *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  char *v18; // rbx
  __int64 v19; // rax
  const wchar_t *v20; // rbx
  const wchar_t *v21; // rdx
  const wchar_t *v22; // rdx
  const wchar_t *v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  int v29; // eax
  Wsp::Facade::StorageHealthFacade *v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  unsigned int v33; // edi
  struct cxl::TraceManager *v34; // rax
  unsigned __int16 *v35; // rbx
  unsigned int v36; // r14d
  struct cxl::TextWriter *v37; // rdi
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  int v41; // ebx
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // r9
  char *v45; // rbx
  __int64 *v47; // [rsp+28h] [rbp-D8h]
  int v48; // [rsp+30h] [rbp-D0h]
  __int64 v49; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v50; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v51; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v52; // [rsp+60h] [rbp-A0h]
  int v53; // [rsp+68h] [rbp-98h]
  const char *v54; // [rsp+70h] [rbp-90h] BYREF
  int v55; // [rsp+78h] [rbp-88h]
  _BYTE v56[32]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v57; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v58; // [rsp+B0h] [rbp-50h]
  __int64 v59; // [rsp+B8h] [rbp-48h]
  _BYTE v60[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v61[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v62[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v63[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v64[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v65[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v66[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v67[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v68[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v69[48]; // [rsp+1E0h] [rbp+E0h] BYREF

  v53 = 0;
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    LODWORD(v50) = 3075;
    v49 = (__int64)"Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode";
    v47 = &v50;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode",
      (__int64)byte_1801295C5,
      a3,
      (__int64)a4,
      &v49);
  }
  v57 = 0;
  v58 = 0;
  v59 = 7;
  LOWORD(v57) = 0;
  v12 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v68, &v57);
  cxl::TextWriter::Write<wchar_t,wchar_t [61],std::wstring>(v12, v13, v14, a3);
  std::wstring::wstring(v60, &v57);
  if ( (unsigned int)dword_18014B6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014B6A8, 0x4000) )
  {
    v49 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v60);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v15,
      (__int64)qword_180129538,
      v16,
      v17,
      &v49);
  }
  v18 = (char *)cxl::TraceManager::Instance() + 160;
  cxl::CxlTraits<std::wstring>::WriteTo(v18, v60);
  cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v18);
  std::wstring::_Tidy_deallocate(v60);
  v51 = 0;
  v52 = 0;
  std::wstring::wstring(v67, a3);
  v19 = Wsp::Health::WspTypeToHealthType(*a4);
  std::wstring::wstring(v66, v19);
  v20 = L"true";
  v21 = L"true";
  if ( !*a5 )
    v21 = L"false";
  std::wstring::wstring(v65, v21);
  std::wstring::wstring(v64, L"false");
  v22 = L"true";
  if ( !*a6 )
    v22 = L"false";
  std::wstring::wstring(v63, v22);
  v23 = L"true";
  if ( !*a7 )
    v23 = L"false";
  std::wstring::wstring(v62, v23);
  if ( !*a8 )
    v20 = L"false";
  std::wstring::wstring(v61, v20);
  if ( *a9 )
    v24 = *(unsigned int *)*a9;
  else
    v24 = 0xFFFFFFFFLL;
  _o__ultow_s(v24, v69, 21);
  v49 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v66);
  std::vector<wchar_t const *>::emplace_back<wchar_t const *>(&v51, &v49);
  v49 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v67);
  std::vector<wchar_t const *>::emplace_back<wchar_t const *>(&v51, &v49);
  v49 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v65);
  std::vector<wchar_t const *>::emplace_back<wchar_t const *>(&v51, &v49);
  v49 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v64);
  std::vector<wchar_t const *>::emplace_back<wchar_t const *>(&v51, &v49);
  v49 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v63);
  std::vector<wchar_t const *>::emplace_back<wchar_t const *>(&v51, &v49);
  v49 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v62);
  std::vector<wchar_t const *>::emplace_back<wchar_t const *>(&v51, &v49);
  v49 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v61);
  std::vector<wchar_t const *>::emplace_back<wchar_t const *>(&v51, &v49);
  if ( *((_QWORD *)&v51 + 1) == v52 )
  {
    std::vector<wchar_t const *>::_Emplace_reallocate<wchar_t (&)[21]>(&v51, *((_QWORD *)&v51 + 1), v69);
  }
  else
  {
    **((_QWORD **)&v51 + 1) = v69;
    *((_QWORD *)&v51 + 1) += 8LL;
  }
  v25 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(qword_180157A60);
  v29 = Wsp::Health2::HealthSendCommand::SendCommand(v26, v25, v27, v28, v27, (int)v47, v48, a2);
  v33 = v29;
  if ( v29 >= 0 )
  {
    v35 = (unsigned __int16 *)(a2 + 4);
    if ( *(_DWORD *)(a2 + 4) )
    {
      if ( *(int *)(a2 + 4) > 0 )
        v33 = *v35 | 0x80070000;
      else
        v33 = *(_DWORD *)v35;
    }
    else if ( *(_QWORD *)(a2 + 24) || *a6 )
    {
      if ( !*a5 || !*a6 )
        v33 = Wsp::Facade::StorageHealthFacade::MonitorAction(v30, (struct Wsp::Facade::MaintenanceCommandContext *)a2);
    }
    else
    {
      v33 = -2147023537;
    }
  }
  else
  {
    LODWORD(v50) = v29;
    if ( (unsigned int)dword_18014B6A8 > 2 )
    {
      v55 = v50;
      LODWORD(v49) = 3125;
      v54 = "Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)v50,
        (__int64)byte_1801294D3,
        v31,
        v32,
        &v54);
    }
    v34 = cxl::TraceManager::Instance();
    LODWORD(v49) = 3125;
    cxl::TextWriter::WriteLine<wchar_t,char [61],int,long>(
      (struct cxl::TraceManager *)((char *)v34 + 40),
      (__int64)&v50);
    v35 = (unsigned __int16 *)(a2 + 4);
  }
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    LODWORD(v49) = 3144;
    v54 = "Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)v30,
      (__int64)byte_18012950B,
      v31,
      v32,
      &v54);
  }
  v36 = *(_DWORD *)v35;
  if ( !*(_DWORD *)v35 )
    v36 = Wsp::MiSpaceAdapter::SmRCFromHResult(v33);
  v58 = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v57) = 0;
  v37 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v56, &v57);
  LODWORD(v49) = v36;
  if ( *(_QWORD *)(a2 + 24) )
  {
    v38 = std::wstring::wstring(v60, a2 + 8);
    v41 = 2;
  }
  else
  {
    v38 = std::wstring::wstring(v68, L"N/A");
    v41 = 1;
  }
  v53 = v41;
  cxl::TextWriter::Write<wchar_t,wchar_t [61],std::wstring,unsigned long>(v37, v39, v40, v38, (__int64)&v49);
  if ( (v41 & 2) != 0 )
  {
    LOBYTE(v41) = v41 & 0xFD;
    std::wstring::_Tidy_deallocate(v60);
  }
  if ( (v41 & 1) != 0 )
    std::wstring::_Tidy_deallocate(v68);
  std::wstring::wstring(v60, &v57);
  if ( (unsigned int)dword_18014B6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014B6A8, 0x4000) )
  {
    v54 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v60);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v42,
      (__int64)byte_1801294B3,
      v43,
      v44,
      &v54);
  }
  v45 = (char *)cxl::TraceManager::Instance() + 160;
  cxl::CxlTraits<std::wstring>::WriteTo(v45, v60);
  cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v45);
  std::wstring::_Tidy_deallocate(v60);
  std::wstring::_Tidy_deallocate(v61);
  std::wstring::_Tidy_deallocate(v62);
  std::wstring::_Tidy_deallocate(v63);
  std::wstring::_Tidy_deallocate(v64);
  std::wstring::_Tidy_deallocate(v65);
  std::wstring::_Tidy_deallocate(v66);
  std::wstring::_Tidy_deallocate(v67);
  if ( (_QWORD)v51 )
  {
    std::_Deallocate<16>((void *)v51, (v52 - v51) & 0xFFFFFFFFFFFFFFF8uLL);
    v51 = 0;
    v52 = 0;
  }
  std::wstring::_Tidy_deallocate(&v57);
  return v36;
}

```

## disassembly

```asm
0x1800695e4  mov     [rsp-8+arg_0], rbx
0x1800695e9  push    rbp
0x1800695ea  push    rsi
0x1800695eb  push    rdi
0x1800695ec  push    r12
0x1800695ee  push    r13
0x1800695f0  push    r14
0x1800695f2  push    r15
0x1800695f4  lea     rbp, [rsp-120h]
0x1800695fc  sub     rsp, 220h
0x180069603  mov     rax, cs:__security_cookie
0x18006960a  xor     rax, rsp
0x18006960d  mov     [rbp+150h+var_40], rax
0x180069614  mov     r14, r9
0x180069617  mov     rdi, r8
0x18006961a  mov     rsi, rdx
0x18006961d  mov     r15, [rbp+150h+arg_40]
0x180069624  xor     r13d, r13d
0x180069627  mov     [rsp+250h+var_1E8], r13d
0x18006962c  mov     eax, cs:dword_18014B6A8
0x180069632  lea     rcx, aWspFacadeStora_15; "Wsp::Facade::StorageHealthFacade::SendC"...
0x180069639  cmp     eax, 5
0x18006963c  jbe     short loc_18006966B
0x18006963e  mov     dword ptr [rsp+250h+var_208], 0C03h
0x180069646  mov     [rsp+250h+var_210], rcx
0x18006964b  lea     rax, [rsp+250h+var_208]
0x180069650  mov     [rsp+250h+var_228], rax
0x180069655  lea     rax, [rsp+250h+var_210]
0x18006965a  mov     [rsp+250h+var_230], rax
0x18006965f  lea     rdx, byte_1801295C5
0x180069666  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006966b  xorps   xmm0, xmm0
0x18006966e  movups  [rbp+150h+var_1B0], xmm0
0x180069672  mov     [rbp+150h+var_1A0], r13
0x180069676  mov     [rbp+150h+var_198], 7
0x18006967e  mov     word ptr [rbp+150h+var_1B0], r13w
0x180069683  lea     rdx, [rbp+150h+var_1B0]
0x180069687  lea     rcx, [rbp+150h+var_90]
0x18006968e  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180069693  nop
0x180069694  mov     r9, rdi
0x180069697  mov     rcx, rax; struct cxl::TextWriter *
0x18006969a  call    ??$Write@_W$$BY0DN@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEB_WAEAY0DN@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<wchar_t,wchar_t [61],std::wstring>(wchar_t const *,wchar_t const (&)[61],std::wstring const &)
0x18006969f  nop
0x1800696a0  lea     rdx, [rbp+150h+var_1B0]
0x1800696a4  lea     rcx, [rbp+150h+var_190]
0x1800696a8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800696ad  nop
0x1800696ae  mov     eax, cs:dword_18014B6A8
0x1800696b4  cmp     eax, 5
0x1800696b7  jbe     short loc_1800696F2
0x1800696b9  mov     edx, 4000h
0x1800696be  lea     rcx, dword_18014B6A8
0x1800696c5  call    _tlgKeywordOn
0x1800696ca  test    al, al
0x1800696cc  jz      short loc_1800696F2
0x1800696ce  lea     rcx, [rbp+150h+var_190]
0x1800696d2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800696d7  mov     [rsp+250h+var_210], rax
0x1800696dc  lea     rax, [rsp+250h+var_210]
0x1800696e1  mov     [rsp+250h+var_230], rax
0x1800696e6  lea     rdx, qword_180129538
0x1800696ed  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1800696f2  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800696f7  lea     rbx, [rax+0A0h]
0x1800696fe  lea     rdx, [rbp+150h+var_190]
0x180069702  mov     rcx, rbx
0x180069705  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x18006970a  mov     rcx, rbx
0x18006970d  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x180069712  nop
0x180069713  lea     rcx, [rbp+150h+var_190]
0x180069717  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006971c  xorps   xmm0, xmm0
0x18006971f  movdqu  [rsp+250h+var_200], xmm0
0x180069725  mov     [rsp+250h+var_1F0], r13
0x18006972a  mov     rdx, rdi
0x18006972d  lea     rcx, [rbp+150h+var_B0]
0x180069734  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180069739  nop
0x18006973a  mov     ecx, [r14]
0x18006973d  call    ?WspTypeToHealthType@Health@Wsp@@YAPEB_WW4WSP_OBJECT_TYPE@@@Z; Wsp::Health::WspTypeToHealthType(WSP_OBJECT_TYPE)
0x180069742  mov     rdx, rax
0x180069745  lea     rcx, [rbp+150h+var_D0]
0x18006974c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180069751  nop
0x180069752  mov     r12, [rbp+150h+arg_20]
0x180069759  lea     rdi, aFalse_0; "false"
0x180069760  lea     rbx, aTrue; "true"
0x180069767  mov     rdx, rbx
0x18006976a  cmp     [r12], r13b
0x18006976e  cmovz   rdx, rdi
0x180069772  lea     rcx, [rbp+150h+var_F0]
0x180069776  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006977b  nop
0x18006977c  mov     rdx, rdi
0x18006977f  lea     rcx, [rbp+150h+var_110]
0x180069783  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180069788  nop
0x180069789  mov     r14, [rbp+150h+arg_28]
0x180069790  mov     rdx, rbx
0x180069793  cmp     [r14], r13b
0x180069796  cmovz   rdx, rdi
0x18006979a  lea     rcx, [rbp+150h+var_130]
0x18006979e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800697a3  nop
0x1800697a4  mov     rax, [rbp+150h+arg_30]
0x1800697ab  mov     rdx, rbx
0x1800697ae  cmp     [rax], r13b
0x1800697b1  cmovz   rdx, rdi
0x1800697b5  lea     rcx, [rbp+150h+var_150]
0x1800697b9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800697be  nop
0x1800697bf  mov     rax, [rbp+150h+arg_38]
0x1800697c6  cmp     [rax], r13b
0x1800697c9  cmovz   rbx, rdi
0x1800697cd  mov     rdx, rbx
0x1800697d0  lea     rcx, [rbp+150h+var_170]
0x1800697d4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800697d9  nop
0x1800697da  mov     rcx, [r15]
0x1800697dd  mov     r9d, 0Ah
0x1800697e3  lea     r8d, [r9+0Bh]
0x1800697e7  lea     rdx, [rbp+150h+var_70]
0x1800697ee  test    rcx, rcx
0x1800697f1  jz      short loc_1800697F7
0x1800697f3  mov     ecx, [rcx]
0x1800697f5  jmp     short loc_1800697FA
0x1800697f7  or      ecx, 0FFFFFFFFh
0x1800697fa  call    cs:__imp__o__ultow_s
0x180069800  lea     rcx, [rbp+150h+var_D0]
0x180069807  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006980c  mov     [rsp+250h+var_210], rax
0x180069811  lea     rdx, [rsp+250h+var_210]
0x180069816  lea     rcx, [rsp+250h+var_200]
0x18006981b  call    ??$emplace_back@PEB_W@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::vector<wchar_t const *>::emplace_back<wchar_t const *>(wchar_t const * &&)
0x180069820  lea     rcx, [rbp+150h+var_B0]
0x180069827  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006982c  mov     [rsp+250h+var_210], rax
0x180069831  lea     rdx, [rsp+250h+var_210]
0x180069836  lea     rcx, [rsp+250h+var_200]
0x18006983b  call    ??$emplace_back@PEB_W@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::vector<wchar_t const *>::emplace_back<wchar_t const *>(wchar_t const * &&)
0x180069840  lea     rcx, [rbp+150h+var_F0]
0x180069844  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180069849  mov     [rsp+250h+var_210], rax
0x18006984e  lea     rdx, [rsp+250h+var_210]
0x180069853  lea     rcx, [rsp+250h+var_200]
0x180069858  call    ??$emplace_back@PEB_W@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::vector<wchar_t const *>::emplace_back<wchar_t const *>(wchar_t const * &&)
0x18006985d  lea     rcx, [rbp+150h+var_110]
0x180069861  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180069866  mov     [rsp+250h+var_210], rax
0x18006986b  lea     rdx, [rsp+250h+var_210]
0x180069870  lea     rcx, [rsp+250h+var_200]
0x180069875  call    ??$emplace_back@PEB_W@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::vector<wchar_t const *>::emplace_back<wchar_t const *>(wchar_t const * &&)
0x18006987a  lea     rcx, [rbp+150h+var_130]
0x18006987e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180069883  mov     [rsp+250h+var_210], rax
0x180069888  lea     rdx, [rsp+250h+var_210]
0x18006988d  lea     rcx, [rsp+250h+var_200]
0x180069892  call    ??$emplace_back@PEB_W@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::vector<wchar_t const *>::emplace_back<wchar_t const *>(wchar_t const * &&)
0x180069897  lea     rcx, [rbp+150h+var_150]
0x18006989b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800698a0  mov     [rsp+250h+var_210], rax
0x1800698a5  lea     rdx, [rsp+250h+var_210]
0x1800698aa  lea     rcx, [rsp+250h+var_200]
0x1800698af  call    ??$emplace_back@PEB_W@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::vector<wchar_t const *>::emplace_back<wchar_t const *>(wchar_t const * &&)
0x1800698b4  lea     rcx, [rbp+150h+var_170]
0x1800698b8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800698bd  mov     [rsp+250h+var_210], rax
0x1800698c2  lea     rdx, [rsp+250h+var_210]
0x1800698c7  lea     rcx, [rsp+250h+var_200]
0x1800698cc  call    ??$emplace_back@PEB_W@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::vector<wchar_t const *>::emplace_back<wchar_t const *>(wchar_t const * &&)
0x1800698d1  mov     rdx, qword ptr [rsp+250h+var_200+8]
0x1800698d6  cmp     rdx, [rsp+250h+var_1F0]
0x1800698db  jz      short loc_1800698F7
0x1800698dd  lea     rax, [rbp+150h+var_70]
0x1800698e4  mov     [rdx], rax
0x1800698e7  mov     r8, qword ptr [rsp+250h+var_200+8]
0x1800698ec  add     r8, 8
0x1800698f0  mov     qword ptr [rsp+250h+var_200+8], r8
0x1800698f5  jmp     short loc_18006990D
0x1800698f7  lea     r8, [rbp+150h+var_70]
0x1800698fe  lea     rcx, [rsp+250h+var_200]
0x180069903  call    ??$_Emplace_reallocate@AEAY0BF@_W@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@AEAAPEAPEB_WQEAPEB_WAEAY0BF@_W@Z; std::vector<wchar_t const *>::_Emplace_reallocate<wchar_t (&)[21]>(wchar_t const * * const,wchar_t (&)[21])
0x180069908  mov     r8, qword ptr [rsp+250h+var_200+8]
0x18006990d  mov     r9, qword ptr [rsp+250h+var_200]
0x180069912  sub     r8, r9
0x180069915  sar     r8, 3
0x180069919  lea     rcx, qword_180157A60
0x180069920  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180069925  mov     rdx, rax
0x180069928  mov     [rsp+250h+var_218], rsi
0x18006992d  mov     dword ptr [rsp+250h+var_230], r8d
0x180069932  call    ?SendCommand@HealthSendCommand@Health2@Wsp@@QEAAJPEB_WW4HEALTH_PLUGIN_COMMAND_FLAGS@@PEAPEB_WKIP6AXKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@Z4@Z; Wsp::Health2::HealthSendCommand::SendCommand(wchar_t const *,HEALTH_PLUGIN_COMMAND_FLAGS,wchar_t const * *,ulong,uint,void (*)(ulong,std::wstring const &,void *),void *)
0x180069937  mov     edi, eax
0x180069939  test    eax, eax
0x18006993b  jns     loc_1800699CA
0x180069941  mov     dword ptr [rsp+250h+var_208], eax
0x180069945  mov     ecx, cs:dword_18014B6A8
0x18006994b  mov     ebx, 0C35h
0x180069950  cmp     ecx, 2
0x180069953  jbe     short loc_180069999
0x180069955  mov     ecx, dword ptr [rsp+250h+var_208]
0x180069959  mov     [rsp+250h+var_1D8], ecx
0x18006995d  mov     dword ptr [rsp+250h+var_210], ebx
0x180069961  lea     r14, aWspFacadeStora_15; "Wsp::Facade::StorageHealthFacade::SendC"...
0x180069968  mov     [rsp+250h+var_1E0], r14
0x18006996d  lea     rax, [rsp+250h+var_1D8]
0x180069972  mov     [rsp+250h+var_220], rax
0x180069977  lea     rax, [rsp+250h+var_210]
0x18006997c  mov     [rsp+250h+var_228], rax
0x180069981  lea     rax, [rsp+250h+var_1E0]
0x180069986  mov     [rsp+250h+var_230], rax
0x18006998b  lea     rdx, byte_1801294D3
0x180069992  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180069997  jmp     short loc_1800699A0
0x180069999  lea     r14, aWspFacadeStora_15; "Wsp::Facade::StorageHealthFacade::SendC"...
0x1800699a0  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800699a5  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x1800699a9  mov     dword ptr [rsp+250h+var_210], ebx
0x1800699ad  lea     rax, [rsp+250h+var_208]
0x1800699b2  mov     [rsp+250h+var_230], rax; __int64
0x1800699b7  lea     r9, [rsp+250h+var_210]
0x1800699bc  mov     r8, r14
0x1800699bf  call    ??$WriteLine@_W$$BY0DN@DHJ@TextWriter@cxl@@QEAAXPEB_WAEAY0DN@$$CBDAEBHAEBJ@Z; cxl::TextWriter::WriteLine<wchar_t,char [61],int,long>(wchar_t const *,char const (&)[61],int const &,long const &)
0x1800699c4  lea     rbx, [rsi+4]
0x1800699c8  jmp     short loc_180069A12
0x1800699ca  lea     rbx, [rsi+4]
0x1800699ce  cmp     [rbx], r13d
0x1800699d1  jz      short loc_1800699E4
0x1800699d3  jg      short loc_1800699D9
0x1800699d5  mov     edi, [rbx]
0x1800699d7  jmp     short loc_180069A0B
0x1800699d9  movzx   edi, word ptr [rbx]
0x1800699dc  or      edi, 80070000h
0x1800699e2  jmp     short loc_180069A0B
0x1800699e4  cmp     [rsi+18h], r13
0x1800699e8  jnz     short loc_1800699F6
0x1800699ea  cmp     [r14], r13b
0x1800699ed  jnz     short loc_1800699F6
0x1800699ef  mov     edi, 8007054Fh
0x1800699f4  jmp     short loc_180069A0B
0x1800699f6  cmp     [r12], r13b
0x1800699fa  jz      short loc_180069A01
0x1800699fc  cmp     [r14], r13b
0x1800699ff  jnz     short loc_180069A0B
0x180069a01  mov     rdx, rsi; struct Wsp::Facade::MaintenanceCommandContext *
0x180069a04  call    ?MonitorAction@StorageHealthFacade@Facade@Wsp@@AEAAJAEAUMaintenanceCommandContext@23@@Z; Wsp::Facade::StorageHealthFacade::MonitorAction(Wsp::Facade::MaintenanceCommandContext &)
0x180069a09  mov     edi, eax
0x180069a0b  lea     r14, aWspFacadeStora_15; "Wsp::Facade::StorageHealthFacade::SendC"...
0x180069a12  mov     eax, cs:dword_18014B6A8
0x180069a18  cmp     eax, 5
0x180069a1b  jbe     short loc_180069A4A
0x180069a1d  mov     dword ptr [rsp+250h+var_210], 0C48h
0x180069a25  mov     [rsp+250h+var_1E0], r14
0x180069a2a  lea     rax, [rsp+250h+var_210]
0x180069a2f  mov     [rsp+250h+var_228], rax
0x180069a34  lea     rax, [rsp+250h+var_1E0]
0x180069a39  mov     [rsp+250h+var_230], rax
0x180069a3e  lea     rdx, byte_18012950B
0x180069a45  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180069a4a  mov     r14d, [rbx]
0x180069a4d  test    r14d, r14d
0x180069a50  jnz     short loc_180069A5C
0x180069a52  mov     ecx, edi
0x180069a54  call    ?SmRCFromHResult@MiSpaceAdapter@Wsp@@SA?AW4SM_RETURN_CODE@@J@Z; Wsp::MiSpaceAdapter::SmRCFromHResult(long)
0x180069a59  mov     r14d, eax
0x180069a5c  mov     [rbp+150h+var_1A0], r13
0x180069a60  lea     rcx, [rbp+150h+var_1B0]
0x180069a64  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180069a69  mov     [rax], r13w
0x180069a6d  lea     rdx, [rbp+150h+var_1B0]
0x180069a71  lea     rcx, [rbp+150h+var_1D0]
0x180069a75  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180069a7a  mov     rdi, rax
0x180069a7d  mov     dword ptr [rsp+250h+var_210], r14d
0x180069a82  lea     rdx, [rsi+8]
0x180069a86  cmp     [rdx+10h], r13
0x180069a8a  jnz     short loc_180069AA7
0x180069a8c  lea     rdx, aNA; "N/A"
0x180069a93  lea     rcx, [rbp+150h+var_90]
0x180069a9a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180069a9f  nop
0x180069aa0  mov     ebx, 1
0x180069aa5  jmp     short loc_180069AB6
0x180069aa7  lea     rcx, [rbp+150h+var_190]
0x180069aab  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180069ab0  nop
0x180069ab1  mov     ebx, 2
0x180069ab6  mov     [rsp+250h+var_1E8], ebx
0x180069aba  lea     rcx, [rsp+250h+var_210]
0x180069abf  mov     [rsp+250h+var_230], rcx; __int64
0x180069ac4  mov     r9, rax
0x180069ac7  mov     rcx, rdi; struct cxl::TextWriter *
0x180069aca  call    ??$Write@_W$$BY0DN@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@TextWriter@cxl@@QEAAXPEB_WAEAY0DN@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBK@Z; cxl::TextWriter::Write<wchar_t,wchar_t [61],std::wstring,ulong>(wchar_t const *,wchar_t const (&)[61],std::wstring const &,ulong const &)
0x180069acf  nop
0x180069ad0  test    bl, 2
0x180069ad3  jz      short loc_180069AE2
0x180069ad5  and     ebx, 0FFFFFFFDh
0x180069ad8  lea     rcx, [rbp+150h+var_190]
  ... truncated ...
```
