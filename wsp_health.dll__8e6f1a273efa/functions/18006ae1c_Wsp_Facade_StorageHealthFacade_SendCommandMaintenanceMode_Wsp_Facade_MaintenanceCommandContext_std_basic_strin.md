# Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode(Wsp::Facade::MaintenanceCommandContext &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,WSP_OBJECT_TYPE const &,bool const &,bool const &,bool const &,bool const &,std::unique_ptr<uint,std::default_delete<uint>> const &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x18006ae1c`
- end: `0x18006b45b`
- name: `?SendCommandMaintenanceMode@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEAUMaintenanceCommandContext@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBW4WSP_OBJECT_TYPE@@AEB_N333AEBV?$unique_ptr@IU?$default_delete@I@std@@@7@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@7@@Z`
- size: `1599`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x180061f90`
- `0x180063988`

## callees

- `0x1800010f8`
- `0x1800011a0`
- `0x1800013d0`
- `0x18000163c`
- `0x180002b50`
- `0x18000c2f8`
- `0x18000c85c`
- `0x18000cd54`
- `0x18000cd9c`
- `0x18000da34`
- `0x18000daf8`
- `0x18000e4b8`
- `0x18000f34c`
- `0x180011184`
- `0x1800354a4`
- `0x18005a638`
- `0x18005a684`
- `0x18005befc`
- `0x18005d758`
- `0x18005e1a0`
- `0x1800697b0`
- `0x18006ae1c`
- `0x180078d18`
- `0x18007c994`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18006b032`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x18006b032`

## string_xrefs

- `0x18006ae6a`: `Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode`
- `0x18006b19f`: `Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode`
- `0x18006b1d7`: `Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode`
- `0x18006b249`: `Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode`

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
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  char *v16; // rbx
  __int64 v17; // rax
  const wchar_t *v18; // rbx
  const wchar_t *v19; // rdx
  const wchar_t *v20; // rdx
  const wchar_t *v21; // rdx
  __int64 v22; // rcx
  int v23; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  int v27; // eax
  Wsp::Facade::StorageHealthFacade *v28; // rcx
  int v29; // r8d
  int v30; // r9d
  unsigned int v31; // edi
  struct cxl::TraceManager *v32; // rax
  unsigned __int16 *v33; // rbx
  unsigned int v34; // r14d
  struct cxl::TextWriter *v35; // rdi
  int v36; // ebx
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  char *v40; // rbx
  int v42; // [rsp+28h] [rbp-D8h]
  __int64 v43; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v44; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v45; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v46; // [rsp+60h] [rbp-A0h]
  int v47; // [rsp+68h] [rbp-98h]
  const char *v48; // [rsp+70h] [rbp-90h] BYREF
  int v49; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v50[32]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v51; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-50h]
  __int64 v53; // [rsp+B8h] [rbp-48h]
  _BYTE v54[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v55[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v56[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v57[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v58[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v59[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v60[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v61[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v62[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v63[48]; // [rsp+1E0h] [rbp+E0h] BYREF

  v47 = 0;
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    LODWORD(v44) = 3075;
    v43 = (__int64)"Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode",
      (unsigned int)qword_18012B540,
      a3,
      (_DWORD)a4,
      (__int64)&v43,
      (__int64)&v44);
  }
  v51 = 0;
  v52 = 0;
  v53 = 7;
  LOWORD(v51) = 0;
  v12 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v62, &v51);
  cxl::TextWriter::Write<wchar_t,wchar_t [61],std::wstring>(v12);
  std::wstring::wstring(v54, &v51);
  if ( (unsigned int)dword_18014D6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014D6A8, 0x4000) )
  {
    v43 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v54);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v13,
      (unsigned int)&word_18012B56E,
      v14,
      v15,
      (__int64)&v43);
  }
  v16 = (char *)cxl::TraceManager::Instance() + 160;
  cxl::CxlTraits<std::wstring>::WriteTo(v16, v54);
  cxl::TextWriter::operator<<<cxl::ENDL>(v16);
  std::wstring::_Tidy_deallocate(v54);
  v45 = 0;
  v46 = 0;
  std::wstring::wstring(v61, a3);
  v17 = Wsp::Health::WspTypeToHealthType(*a4);
  std::wstring::wstring(v60, v17);
  v18 = L"true";
  v19 = L"true";
  if ( !*a5 )
    v19 = L"false";
  std::wstring::wstring(v59, v19);
  std::wstring::wstring(v58, L"false");
  v20 = L"true";
  if ( !*a6 )
    v20 = L"false";
  std::wstring::wstring(v57, v20);
  v21 = L"true";
  if ( !*a7 )
    v21 = L"false";
  std::wstring::wstring(v56, v21);
  if ( !*a8 )
    v18 = L"false";
  std::wstring::wstring(v55, v18);
  if ( *a9 )
    v22 = *(unsigned int *)*a9;
  else
    v22 = 0xFFFFFFFFLL;
  _o__ultow_s(v22, v63, 21);
  v43 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v60);
  std::vector<wchar_t const *>::emplace_back<wchar_t const *>(&v45, &v43);
  v43 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v61);
  std::vector<wchar_t const *>::emplace_back<wchar_t const *>(&v45, &v43);
  v43 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v59);
  std::vector<wchar_t const *>::emplace_back<wchar_t const *>(&v45, &v43);
  v43 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v58);
  std::vector<wchar_t const *>::emplace_back<wchar_t const *>(&v45, &v43);
  v43 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v57);
  std::vector<wchar_t const *>::emplace_back<wchar_t const *>(&v45, &v43);
  v43 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v56);
  std::vector<wchar_t const *>::emplace_back<wchar_t const *>(&v45, &v43);
  v43 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v55);
  std::vector<wchar_t const *>::emplace_back<wchar_t const *>(&v45, &v43);
  if ( *((_QWORD *)&v45 + 1) == v46 )
  {
    std::vector<wchar_t const *>::_Emplace_reallocate<wchar_t (&)[21]>(&v45, *((_QWORD *)&v45 + 1), v63);
  }
  else
  {
    **((_QWORD **)&v45 + 1) = v63;
    *((_QWORD *)&v45 + 1) += 8LL;
  }
  v23 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(qword_180159B60);
  v27 = Wsp::Health2::HealthSendCommand::SendCommand(v24, v23, v25, v26, v25, v42);
  v31 = v27;
  if ( v27 >= 0 )
  {
    v33 = (unsigned __int16 *)(a2 + 4);
    if ( *(_DWORD *)(a2 + 4) )
    {
      if ( *(int *)(a2 + 4) > 0 )
        v31 = *v33 | 0x80070000;
      else
        v31 = *(_DWORD *)v33;
    }
    else if ( *(_QWORD *)(a2 + 24) || *a6 )
    {
      if ( !*a5 || !*a6 )
        v31 = Wsp::Facade::StorageHealthFacade::MonitorAction(v28, (struct Wsp::Facade::MaintenanceCommandContext *)a2);
    }
    else
    {
      v31 = -2147023537;
    }
  }
  else
  {
    LODWORD(v44) = v27;
    if ( (unsigned int)dword_18014D6A8 > 2 )
    {
      v49 = v44;
      LODWORD(v43) = 3125;
      v48 = "Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v44,
        (unsigned int)byte_18012B4DB,
        v29,
        v30,
        (__int64)&v48,
        (__int64)&v43,
        (__int64)&v49);
    }
    v32 = cxl::TraceManager::Instance();
    LODWORD(v43) = 3125;
    cxl::TextWriter::WriteLine<wchar_t,char [61],int,long>(
      (struct cxl::TraceManager *)((char *)v32 + 40),
      (__int64)&v44);
    v33 = (unsigned __int16 *)(a2 + 4);
  }
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    LODWORD(v43) = 3144;
    v48 = "Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)v28,
      (unsigned int)byte_18012B513,
      v29,
      v30,
      (__int64)&v48,
      (__int64)&v43);
  }
  v34 = *(_DWORD *)v33;
  if ( !*(_DWORD *)v33 )
    v34 = Wsp::MiSpaceAdapter::SmRCFromHResult(v31);
  v52 = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v51) = 0;
  v35 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v50, &v51);
  LODWORD(v43) = v34;
  if ( *(_QWORD *)(a2 + 24) )
  {
    std::wstring::wstring(v54, a2 + 8);
    v36 = 2;
  }
  else
  {
    std::wstring::wstring(v62, L"N/A");
    v36 = 1;
  }
  v47 = v36;
  cxl::TextWriter::Write<wchar_t,wchar_t [61],std::wstring,unsigned long>(v35, (__int64)&v43);
  if ( (v36 & 2) != 0 )
  {
    LOBYTE(v36) = v36 & 0xFD;
    std::wstring::_Tidy_deallocate(v54);
  }
  if ( (v36 & 1) != 0 )
    std::wstring::_Tidy_deallocate(v62);
  std::wstring::wstring(v54, &v51);
  if ( (unsigned int)dword_18014D6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014D6A8, 0x4000) )
  {
    v48 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v54);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v37,
      (unsigned int)byte_18012B4BB,
      v38,
      v39,
      (__int64)&v48);
  }
  v40 = (char *)cxl::TraceManager::Instance() + 160;
  cxl::CxlTraits<std::wstring>::WriteTo(v40, v54);
  cxl::TextWriter::operator<<<cxl::ENDL>(v40);
  std::wstring::_Tidy_deallocate(v54);
  std::wstring::_Tidy_deallocate(v55);
  std::wstring::_Tidy_deallocate(v56);
  std::wstring::_Tidy_deallocate(v57);
  std::wstring::_Tidy_deallocate(v58);
  std::wstring::_Tidy_deallocate(v59);
  std::wstring::_Tidy_deallocate(v60);
  std::wstring::_Tidy_deallocate(v61);
  if ( (_QWORD)v45 )
  {
    std::_Deallocate<16>(v45, (v46 - v45) & 0xFFFFFFFFFFFFFFF8uLL);
    v45 = 0;
    v46 = 0;
  }
  std::wstring::_Tidy_deallocate(&v51);
  return v34;
}

```

## disassembly

```asm
0x18006ae1c  mov     [rsp-8+arg_0], rbx
0x18006ae21  push    rbp
0x18006ae22  push    rsi
0x18006ae23  push    rdi
0x18006ae24  push    r12
0x18006ae26  push    r13
0x18006ae28  push    r14
0x18006ae2a  push    r15
0x18006ae2c  lea     rbp, [rsp-120h]
0x18006ae34  sub     rsp, 220h
0x18006ae3b  mov     rax, cs:__security_cookie
0x18006ae42  xor     rax, rsp
0x18006ae45  mov     [rbp+150h+var_40], rax
0x18006ae4c  mov     r14, r9
0x18006ae4f  mov     rdi, r8
0x18006ae52  mov     rsi, rdx
0x18006ae55  mov     r15, [rbp+150h+arg_40]
0x18006ae5c  xor     r13d, r13d
0x18006ae5f  mov     [rsp+250h+var_1E8], r13d
0x18006ae64  mov     eax, cs:dword_18014D6A8
0x18006ae6a  lea     rcx, aWspFacadeStora_15; "Wsp::Facade::StorageHealthFacade::SendC"...
0x18006ae71  cmp     eax, 5
0x18006ae74  jbe     short loc_18006AEA3
0x18006ae76  mov     dword ptr [rsp+250h+var_208], 0C03h
0x18006ae7e  mov     [rsp+250h+var_210], rcx
0x18006ae83  lea     rax, [rsp+250h+var_208]
0x18006ae88  mov     [rsp+250h+var_228], rax
0x18006ae8d  lea     rax, [rsp+250h+var_210]
0x18006ae92  mov     [rsp+250h+var_230], rax
0x18006ae97  lea     rdx, qword_18012B540
0x18006ae9e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006aea3  xorps   xmm0, xmm0
0x18006aea6  movups  [rbp+150h+var_1B0], xmm0
0x18006aeaa  mov     [rbp+150h+var_1A0], r13
0x18006aeae  mov     [rbp+150h+var_198], 7
0x18006aeb6  mov     word ptr [rbp+150h+var_1B0], r13w
0x18006aebb  lea     rdx, [rbp+150h+var_1B0]
0x18006aebf  lea     rcx, [rbp+150h+var_90]
0x18006aec6  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18006aecb  nop
0x18006aecc  mov     r9, rdi
0x18006aecf  mov     rcx, rax; struct cxl::TextWriter *
0x18006aed2  call    ??$Write@_W$$BY0DN@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEB_WAEAY0DN@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TextWriter::Write<wchar_t,wchar_t [61],std::wstring>(wchar_t const *,wchar_t const (&)[61],std::wstring const &)
0x18006aed7  nop
0x18006aed8  lea     rdx, [rbp+150h+var_1B0]
0x18006aedc  lea     rcx, [rbp+150h+var_190]
0x18006aee0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006aee5  nop
0x18006aee6  mov     eax, cs:dword_18014D6A8
0x18006aeec  cmp     eax, 5
0x18006aeef  jbe     short loc_18006AF2A
0x18006aef1  mov     edx, 4000h
0x18006aef6  lea     rcx, dword_18014D6A8
0x18006aefd  call    _tlgKeywordOn
0x18006af02  test    al, al
0x18006af04  jz      short loc_18006AF2A
0x18006af06  lea     rcx, [rbp+150h+var_190]
0x18006af0a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006af0f  mov     [rsp+250h+var_210], rax
0x18006af14  lea     rax, [rsp+250h+var_210]
0x18006af19  mov     [rsp+250h+var_230], rax
0x18006af1e  lea     rdx, word_18012B56E
0x18006af25  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18006af2a  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006af2f  lea     rbx, [rax+0A0h]
0x18006af36  lea     rdx, [rbp+150h+var_190]
0x18006af3a  mov     rcx, rbx
0x18006af3d  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x18006af42  mov     rcx, rbx
0x18006af45  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x18006af4a  nop
0x18006af4b  lea     rcx, [rbp+150h+var_190]
0x18006af4f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006af54  xorps   xmm0, xmm0
0x18006af57  movdqu  [rsp+250h+var_200], xmm0
0x18006af5d  mov     [rsp+250h+var_1F0], r13
0x18006af62  mov     rdx, rdi
0x18006af65  lea     rcx, [rbp+150h+var_B0]
0x18006af6c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006af71  nop
0x18006af72  mov     ecx, [r14]
0x18006af75  call    ?WspTypeToHealthType@Health@Wsp@@YAPEB_WW4WSP_OBJECT_TYPE@@@Z; Wsp::Health::WspTypeToHealthType(WSP_OBJECT_TYPE)
0x18006af7a  mov     rdx, rax
0x18006af7d  lea     rcx, [rbp+150h+var_D0]
0x18006af84  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006af89  nop
0x18006af8a  mov     r12, [rbp+150h+arg_20]
0x18006af91  lea     rdi, aFalse_0; "false"
0x18006af98  lea     rbx, aTrue; "true"
0x18006af9f  mov     rdx, rbx
0x18006afa2  cmp     [r12], r13b
0x18006afa6  cmovz   rdx, rdi
0x18006afaa  lea     rcx, [rbp+150h+var_F0]
0x18006afae  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006afb3  nop
0x18006afb4  mov     rdx, rdi
0x18006afb7  lea     rcx, [rbp+150h+var_110]
0x18006afbb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006afc0  nop
0x18006afc1  mov     r14, [rbp+150h+arg_28]
0x18006afc8  mov     rdx, rbx
0x18006afcb  cmp     [r14], r13b
0x18006afce  cmovz   rdx, rdi
0x18006afd2  lea     rcx, [rbp+150h+var_130]
0x18006afd6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006afdb  nop
0x18006afdc  mov     rax, [rbp+150h+arg_30]
0x18006afe3  mov     rdx, rbx
0x18006afe6  cmp     [rax], r13b
0x18006afe9  cmovz   rdx, rdi
0x18006afed  lea     rcx, [rbp+150h+var_150]
0x18006aff1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006aff6  nop
0x18006aff7  mov     rax, [rbp+150h+arg_38]
0x18006affe  cmp     [rax], r13b
0x18006b001  cmovz   rbx, rdi
0x18006b005  mov     rdx, rbx
0x18006b008  lea     rcx, [rbp+150h+var_170]
0x18006b00c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006b011  nop
0x18006b012  mov     rcx, [r15]
0x18006b015  mov     r9d, 0Ah
0x18006b01b  lea     r8d, [r9+0Bh]
0x18006b01f  lea     rdx, [rbp+150h+var_70]
0x18006b026  test    rcx, rcx
0x18006b029  jz      short loc_18006B02F
0x18006b02b  mov     ecx, [rcx]
0x18006b02d  jmp     short loc_18006B032
0x18006b02f  or      ecx, 0FFFFFFFFh
0x18006b032  call    cs:__imp__o__ultow_s
0x18006b039  nop     dword ptr [rax+rax+00h]
0x18006b03e  lea     rcx, [rbp+150h+var_D0]
0x18006b045  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006b04a  mov     [rsp+250h+var_210], rax
0x18006b04f  lea     rdx, [rsp+250h+var_210]
0x18006b054  lea     rcx, [rsp+250h+var_200]
0x18006b059  call    ??$emplace_back@PEB_W@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::vector<wchar_t const *>::emplace_back<wchar_t const *>(wchar_t const * &&)
0x18006b05e  lea     rcx, [rbp+150h+var_B0]
0x18006b065  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006b06a  mov     [rsp+250h+var_210], rax
0x18006b06f  lea     rdx, [rsp+250h+var_210]
0x18006b074  lea     rcx, [rsp+250h+var_200]
0x18006b079  call    ??$emplace_back@PEB_W@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::vector<wchar_t const *>::emplace_back<wchar_t const *>(wchar_t const * &&)
0x18006b07e  lea     rcx, [rbp+150h+var_F0]
0x18006b082  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006b087  mov     [rsp+250h+var_210], rax
0x18006b08c  lea     rdx, [rsp+250h+var_210]
0x18006b091  lea     rcx, [rsp+250h+var_200]
0x18006b096  call    ??$emplace_back@PEB_W@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::vector<wchar_t const *>::emplace_back<wchar_t const *>(wchar_t const * &&)
0x18006b09b  lea     rcx, [rbp+150h+var_110]
0x18006b09f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006b0a4  mov     [rsp+250h+var_210], rax
0x18006b0a9  lea     rdx, [rsp+250h+var_210]
0x18006b0ae  lea     rcx, [rsp+250h+var_200]
0x18006b0b3  call    ??$emplace_back@PEB_W@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::vector<wchar_t const *>::emplace_back<wchar_t const *>(wchar_t const * &&)
0x18006b0b8  lea     rcx, [rbp+150h+var_130]
0x18006b0bc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006b0c1  mov     [rsp+250h+var_210], rax
0x18006b0c6  lea     rdx, [rsp+250h+var_210]
0x18006b0cb  lea     rcx, [rsp+250h+var_200]
0x18006b0d0  call    ??$emplace_back@PEB_W@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::vector<wchar_t const *>::emplace_back<wchar_t const *>(wchar_t const * &&)
0x18006b0d5  lea     rcx, [rbp+150h+var_150]
0x18006b0d9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006b0de  mov     [rsp+250h+var_210], rax
0x18006b0e3  lea     rdx, [rsp+250h+var_210]
0x18006b0e8  lea     rcx, [rsp+250h+var_200]
0x18006b0ed  call    ??$emplace_back@PEB_W@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::vector<wchar_t const *>::emplace_back<wchar_t const *>(wchar_t const * &&)
0x18006b0f2  lea     rcx, [rbp+150h+var_170]
0x18006b0f6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006b0fb  mov     [rsp+250h+var_210], rax
0x18006b100  lea     rdx, [rsp+250h+var_210]
0x18006b105  lea     rcx, [rsp+250h+var_200]
0x18006b10a  call    ??$emplace_back@PEB_W@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@QEAAAEAPEB_W$$QEAPEB_W@Z; std::vector<wchar_t const *>::emplace_back<wchar_t const *>(wchar_t const * &&)
0x18006b10f  mov     rdx, qword ptr [rsp+250h+var_200+8]
0x18006b114  cmp     rdx, [rsp+250h+var_1F0]
0x18006b119  jz      short loc_18006B135
0x18006b11b  lea     rax, [rbp+150h+var_70]
0x18006b122  mov     [rdx], rax
0x18006b125  mov     r8, qword ptr [rsp+250h+var_200+8]
0x18006b12a  add     r8, 8
0x18006b12e  mov     qword ptr [rsp+250h+var_200+8], r8
0x18006b133  jmp     short loc_18006B14B
0x18006b135  lea     r8, [rbp+150h+var_70]
0x18006b13c  lea     rcx, [rsp+250h+var_200]
0x18006b141  call    ??$_Emplace_reallocate@AEAY0BF@_W@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@AEAAPEAPEB_WQEAPEB_WAEAY0BF@_W@Z; std::vector<wchar_t const *>::_Emplace_reallocate<wchar_t (&)[21]>(wchar_t const * * const,wchar_t (&)[21])
0x18006b146  mov     r8, qword ptr [rsp+250h+var_200+8]
0x18006b14b  mov     r9, qword ptr [rsp+250h+var_200]
0x18006b150  sub     r8, r9
0x18006b153  sar     r8, 3
0x18006b157  lea     rcx, qword_180159B60
0x18006b15e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006b163  mov     rdx, rax
0x18006b166  mov     [rsp+250h+var_218], rsi
0x18006b16b  mov     dword ptr [rsp+250h+var_230], r8d
0x18006b170  call    ?SendCommand@HealthSendCommand@Health2@Wsp@@QEAAJPEB_WW4HEALTH_PLUGIN_COMMAND_FLAGS@@PEAPEB_WKIP6AXKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@Z4@Z; Wsp::Health2::HealthSendCommand::SendCommand(wchar_t const *,HEALTH_PLUGIN_COMMAND_FLAGS,wchar_t const * *,ulong,uint,void (*)(ulong,std::wstring const &,void *),void *)
0x18006b175  mov     edi, eax
0x18006b177  test    eax, eax
0x18006b179  jns     loc_18006B208
0x18006b17f  mov     dword ptr [rsp+250h+var_208], eax
0x18006b183  mov     ecx, cs:dword_18014D6A8
0x18006b189  mov     ebx, 0C35h
0x18006b18e  cmp     ecx, 2
0x18006b191  jbe     short loc_18006B1D7
0x18006b193  mov     ecx, dword ptr [rsp+250h+var_208]
0x18006b197  mov     [rsp+250h+var_1D8], ecx
0x18006b19b  mov     dword ptr [rsp+250h+var_210], ebx
0x18006b19f  lea     r14, aWspFacadeStora_15; "Wsp::Facade::StorageHealthFacade::SendC"...
0x18006b1a6  mov     [rsp+250h+var_1E0], r14
0x18006b1ab  lea     rax, [rsp+250h+var_1D8]
0x18006b1b0  mov     [rsp+250h+var_220], rax
0x18006b1b5  lea     rax, [rsp+250h+var_210]
0x18006b1ba  mov     [rsp+250h+var_228], rax
0x18006b1bf  lea     rax, [rsp+250h+var_1E0]
0x18006b1c4  mov     [rsp+250h+var_230], rax
0x18006b1c9  lea     rdx, byte_18012B4DB
0x18006b1d0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006b1d5  jmp     short loc_18006B1DE
0x18006b1d7  lea     r14, aWspFacadeStora_15; "Wsp::Facade::StorageHealthFacade::SendC"...
0x18006b1de  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006b1e3  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x18006b1e7  mov     dword ptr [rsp+250h+var_210], ebx
0x18006b1eb  lea     rax, [rsp+250h+var_208]
0x18006b1f0  mov     [rsp+250h+var_230], rax; __int64
0x18006b1f5  lea     r9, [rsp+250h+var_210]
0x18006b1fa  mov     r8, r14
0x18006b1fd  call    ??$WriteLine@_W$$BY0DN@DHJ@TextWriter@cxl@@QEAAXPEB_WAEAY0DN@$$CBDAEBHAEBJ@Z; cxl::TextWriter::WriteLine<wchar_t,char [61],int,long>(wchar_t const *,char const (&)[61],int const &,long const &)
0x18006b202  lea     rbx, [rsi+4]
0x18006b206  jmp     short loc_18006B250
0x18006b208  lea     rbx, [rsi+4]
0x18006b20c  cmp     [rbx], r13d
0x18006b20f  jz      short loc_18006B222
0x18006b211  jg      short loc_18006B217
0x18006b213  mov     edi, [rbx]
0x18006b215  jmp     short loc_18006B249
0x18006b217  movzx   edi, word ptr [rbx]
0x18006b21a  or      edi, 80070000h
0x18006b220  jmp     short loc_18006B249
0x18006b222  cmp     [rsi+18h], r13
0x18006b226  jnz     short loc_18006B234
0x18006b228  cmp     [r14], r13b
0x18006b22b  jnz     short loc_18006B234
0x18006b22d  mov     edi, 8007054Fh
0x18006b232  jmp     short loc_18006B249
0x18006b234  cmp     [r12], r13b
0x18006b238  jz      short loc_18006B23F
0x18006b23a  cmp     [r14], r13b
0x18006b23d  jnz     short loc_18006B249
0x18006b23f  mov     rdx, rsi; struct Wsp::Facade::MaintenanceCommandContext *
0x18006b242  call    ?MonitorAction@StorageHealthFacade@Facade@Wsp@@AEAAJAEAUMaintenanceCommandContext@23@@Z; Wsp::Facade::StorageHealthFacade::MonitorAction(Wsp::Facade::MaintenanceCommandContext &)
0x18006b247  mov     edi, eax
0x18006b249  lea     r14, aWspFacadeStora_15; "Wsp::Facade::StorageHealthFacade::SendC"...
0x18006b250  mov     eax, cs:dword_18014D6A8
0x18006b256  cmp     eax, 5
0x18006b259  jbe     short loc_18006B288
0x18006b25b  mov     dword ptr [rsp+250h+var_210], 0C48h
0x18006b263  mov     [rsp+250h+var_1E0], r14
0x18006b268  lea     rax, [rsp+250h+var_210]
0x18006b26d  mov     [rsp+250h+var_228], rax
0x18006b272  lea     rax, [rsp+250h+var_1E0]
0x18006b277  mov     [rsp+250h+var_230], rax
0x18006b27c  lea     rdx, byte_18012B513
0x18006b283  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006b288  mov     r14d, [rbx]
0x18006b28b  test    r14d, r14d
0x18006b28e  jnz     short loc_18006B29A
0x18006b290  mov     ecx, edi
0x18006b292  call    ?SmRCFromHResult@MiSpaceAdapter@Wsp@@SA?AW4SM_RETURN_CODE@@J@Z; Wsp::MiSpaceAdapter::SmRCFromHResult(long)
0x18006b297  mov     r14d, eax
0x18006b29a  mov     [rbp+150h+var_1A0], r13
0x18006b29e  lea     rcx, [rbp+150h+var_1B0]
0x18006b2a2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006b2a7  mov     [rax], r13w
0x18006b2ab  lea     rdx, [rbp+150h+var_1B0]
0x18006b2af  lea     rcx, [rbp+150h+var_1D0]
0x18006b2b3  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18006b2b8  mov     rdi, rax
0x18006b2bb  mov     dword ptr [rsp+250h+var_210], r14d
0x18006b2c0  lea     rdx, [rsi+8]
0x18006b2c4  cmp     [rdx+10h], r13
0x18006b2c8  jnz     short loc_18006B2E5
0x18006b2ca  lea     rdx, aNA; "N/A"
0x18006b2d1  lea     rcx, [rbp+150h+var_90]
0x18006b2d8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006b2dd  nop
0x18006b2de  mov     ebx, 1
0x18006b2e3  jmp     short loc_18006B2F4
0x18006b2e5  lea     rcx, [rbp+150h+var_190]
0x18006b2e9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006b2ee  nop
0x18006b2ef  mov     ebx, 2
0x18006b2f4  mov     [rsp+250h+var_1E8], ebx
0x18006b2f8  lea     rcx, [rsp+250h+var_210]
0x18006b2fd  mov     [rsp+250h+var_230], rcx; __int64
0x18006b302  mov     r9, rax
0x18006b305  mov     rcx, rdi; struct cxl::TextWriter *
0x18006b308  call    ??$Write@_W$$BY0DN@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@TextWriter@cxl@@QEAAXPEB_WAEAY0DN@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBK@Z; cxl::TextWriter::Write<wchar_t,wchar_t [61],std::wstring,ulong>(wchar_t const *,wchar_t const (&)[61],std::wstring const &,ulong const &)
0x18006b30d  nop
0x18006b30e  test    bl, 2
0x18006b311  jz      short loc_18006B320
0x18006b313  and     ebx, 0FFFFFFFDh
  ... truncated ...
```
