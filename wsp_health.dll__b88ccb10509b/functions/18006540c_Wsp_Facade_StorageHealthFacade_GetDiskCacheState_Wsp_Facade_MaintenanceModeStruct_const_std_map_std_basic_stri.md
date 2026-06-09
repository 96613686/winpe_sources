# Wsp::Facade::StorageHealthFacade::GetDiskCacheState(Wsp::Facade::MaintenanceModeStruct const &,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,Wsp::Facade::MaintenanceDisk,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,Wsp::Facade::MaintenanceDisk>>> &,bool,mi::MiContext &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x18006540c`
- end: `0x180065716`
- name: `?GetDiskCacheState@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBUMaintenanceModeStruct@23@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@std@@_NAEAVMiContext@mi@@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@7@@Z`
- size: `778`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180060f98`
- `0x180062e00`

## callees

- `0x1800013bc`
- `0x180001620`
- `0x1800016b0`
- `0x180002ae0`
- `0x18000b800`
- `0x18000b8e4`
- `0x18000bf68`
- `0x18000c9f0`
- `0x18000d618`
- `0x18000d6dc`
- `0x18000e044`
- `0x18000eebc`
- `0x180018154`
- `0x180059aa4`
- `0x180059b08`
- `0x18006540c`
- `0x18006c26c`
- `0x18006ca10`
- `0x180080590`

## string_xrefs

- `0x1800654aa`: `Wsp::Facade::StorageHealthFacade::GetDiskCacheState`
- `0x18006552d`: `Wsp::Facade::StorageHealthFacade::GetDiskCacheState`
- `0x18006559a`: `Wsp::Facade::StorageHealthFacade::GetDiskCacheState`
- `0x18006548e`: `Failed to open the target node to get disk cache state`
- `0x180065514`: `Failed to open the target node to get disk cache state`
- `0x18006563b`: `No cache disks found so we are moving on`
- `0x180065566`: `Failed to open the local node to get disk cache state`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Wsp::Facade::StorageHealthFacade::GetDiskCacheState(
        int a1,
        __int64 a2,
        __int64 a3,
        char a4,
        __int64 a5,
        __int64 a6)
{
  __int64 Node; // rax
  unsigned int v11; // edi
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  struct cxl::TraceManager *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  struct cxl::TraceManager *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  char *v24; // rbx
  unsigned int v25; // eax
  int v27; // [rsp+40h] [rbp-59h] BYREF
  _DWORD v28[3]; // [rsp+44h] [rbp-55h] BYREF
  const char *v29; // [rsp+50h] [rbp-49h] BYREF
  std::_Ref_count_base *v30[2]; // [rsp+58h] [rbp-41h] BYREF
  __int64 v31; // [rsp+68h] [rbp-31h] BYREF
  std::_Ref_count_base *v32; // [rsp+70h] [rbp-29h]
  _BYTE v33[32]; // [rsp+88h] [rbp-11h] BYREF

  *(_OWORD *)v30 = 0;
  Node = ClusApi::Facade::ClusterFacade::GetNode(*(_QWORD *)(a2 + 160), &v31, a2 + 24);
  std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(v30, Node);
  if ( v32 )
    std::_Ref_count_base::_Decref(v32);
  if ( v30[0] )
  {
    v11 = 0;
LABEL_14:
    if ( *(_QWORD *)(a3 + 8) )
    {
      if ( a4 )
        v25 = Wsp::Facade::StorageHealthFacade::WaitForCacheEnable(a1, (unsigned int)v30, a3, a5, a6);
      else
        v25 = Wsp::Facade::StorageHealthFacade::WaitForCacheDrain(a1, (unsigned int)v30, a3, a5, a6);
      v11 = v25;
    }
    else
    {
      std::wstring::wstring(&v31, L"No cache disks found so we are moving on");
      if ( (unsigned int)dword_18014B6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014B6A8, 0x4000) )
      {
        *(_QWORD *)&v28[1] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v31);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
          v21,
          (__int64)&word_180129DEE,
          v22,
          v23,
          &v28[1]);
      }
      v24 = (char *)cxl::TraceManager::Instance() + 160;
      cxl::CxlTraits<std::wstring>::WriteTo(v24, &v31);
      cxl::TextWriter::operator<<<cxl::ENDL>((__int64)v24);
      std::wstring::_Tidy_deallocate(&v31);
    }
    goto LABEL_23;
  }
  std::wstring::wstring(&v31, L"Failed to open the target node to get disk cache state");
  v11 = 59000;
  if ( (unsigned int)dword_18014B6A8 > 2 )
  {
    v29 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v31);
    v27 = 59000;
    v28[0] = 2182;
    *(_QWORD *)&v28[1] = v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
      v13,
      (__int64)&byte_180129EBF,
      v14,
      v15,
      &v28[1],
      (__int64)v28,
      (__int64)&v27,
      &v29);
  }
  v16 = cxl::TraceManager::Instance();
  v28[0] = 59000;
  v27 = 2182;
  cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [55]>(
    (struct cxl::TraceManager *)((char *)v16 + 40),
    (__int64)v28,
    (__int64)L"Failed to open the target node to get disk cache state");
  std::wstring::_Tidy_deallocate(&v31);
  ClusApi::Facade::ClusterFacade::GetNode(*(_QWORD *)(a2 + 160), &v31, cxl::EmptyLiteral);
  if ( v31 )
  {
    std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(v30, &v31);
    if ( v32 )
      std::_Ref_count_base::_Decref(v32);
    goto LABEL_14;
  }
  std::wstring::wstring(v33, L"Failed to open the local node to get disk cache state");
  if ( (unsigned int)dword_18014B6A8 > 2 )
  {
    *(_QWORD *)&v28[1] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v33);
    v28[0] = 59000;
    v27 = 2189;
    v29 = "Wsp::Facade::StorageHealthFacade::GetDiskCacheState";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
      v17,
      (__int64)&byte_180129DAF,
      v18,
      v19,
      &v29,
      (__int64)&v27,
      (__int64)v28,
      &v28[1]);
  }
  v20 = cxl::TraceManager::Instance();
  v28[0] = 59000;
  v27 = 2189;
  cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [54]>(
    (struct cxl::TraceManager *)((char *)v20 + 40),
    (__int64)v28);
  std::wstring::_Tidy_deallocate(v33);
  if ( v32 )
    std::_Ref_count_base::_Decref(v32);
LABEL_23:
  if ( v30[1] )
    std::_Ref_count_base::_Decref(v30[1]);
  return v11;
}

```

## disassembly

```asm
0x18006540c  mov     [rsp-8+arg_18], rbx
0x180065411  push    rbp
0x180065412  push    rsi
0x180065413  push    rdi
0x180065414  push    r12
0x180065416  push    r13
0x180065418  push    r14
0x18006541a  push    r15
0x18006541c  lea     rbp, [rsp-17h]
0x180065421  sub     rsp, 0B0h
0x180065428  mov     rax, cs:__security_cookie
0x18006542f  xor     rax, rsp
0x180065432  mov     [rbp+47h+var_38], rax
0x180065436  mov     r12b, r9b
0x180065439  mov     rbx, r8
0x18006543c  mov     r13, rdx
0x18006543f  mov     rsi, rcx
0x180065442  mov     r14, [rbp+47h+arg_20]
0x180065446  mov     r15, [rbp+47h+arg_28]
0x18006544a  xorps   xmm0, xmm0
0x18006544d  movdqu  xmmword ptr [rbp+47h+var_88], xmm0
0x180065452  lea     r8, [rdx+18h]
0x180065456  lea     rdx, [rbp+47h+var_78]
0x18006545a  mov     rcx, [r13+0A0h]
0x180065461  call    ?GetNode@ClusterFacade@Facade@ClusApi@@QEAA?AV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; ClusApi::Facade::ClusterFacade::GetNode(std::wstring const &)
0x180065466  mov     rdx, rax
0x180065469  lea     rcx, [rbp+47h+var_88]
0x18006546d  call    ??4?$shared_ptr@$$CBVSPACES_VirtualDisk@mismpstorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(std::shared_ptr<mismpstorage::SPACES_VirtualDisk const> &&)
0x180065472  mov     rcx, [rbp+47h+var_70]; this
0x180065476  test    rcx, rcx
0x180065479  jz      short loc_180065480
0x18006547b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180065480  cmp     [rbp+47h+var_88], 0
0x180065485  jz      short loc_18006548E
0x180065487  xor     edi, edi
0x180065489  jmp     loc_180065634
0x18006548e  lea     rdx, aFailedToOpenTh_0; "Failed to open the target node to get d"...
0x180065495  lea     rcx, [rbp+47h+var_78]
0x180065499  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006549e  nop
0x18006549f  mov     eax, cs:dword_18014B6A8
0x1800654a5  mov     edi, 0E678h
0x1800654aa  lea     rdx, aWspFacadeStora_21; "Wsp::Facade::StorageHealthFacade::GetDi"...
0x1800654b1  cmp     eax, 2
0x1800654b4  jbe     short loc_180065501
0x1800654b6  lea     rcx, [rbp+47h+var_78]
0x1800654ba  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800654bf  mov     [rbp+47h+var_90], rax
0x1800654c3  mov     [rbp+47h+var_A0], edi
0x1800654c6  mov     dword ptr [rbp+47h+var_9C], 886h
0x1800654cd  mov     qword ptr [rbp+47h+var_9C+4], rdx
0x1800654d1  lea     rax, [rbp+47h+var_90]
0x1800654d5  mov     [rsp+0E0h+var_A8], rax
0x1800654da  lea     rax, [rbp+47h+var_A0]
0x1800654de  mov     [rsp+0E0h+var_B0], rax
0x1800654e3  lea     rax, [rbp+47h+var_9C]
0x1800654e7  mov     [rsp+0E0h+var_B8], rax
0x1800654ec  lea     rax, [rbp+47h+var_9C+4]
0x1800654f0  mov     [rsp+0E0h+var_C0], rax
0x1800654f5  lea     rdx, byte_180129EBF
0x1800654fc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180065501  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180065506  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x18006550a  mov     dword ptr [rbp+47h+var_9C], edi
0x18006550d  mov     [rbp+47h+var_A0], 886h
0x180065514  lea     rax, aFailedToOpenTh_0; "Failed to open the target node to get d"...
0x18006551b  mov     [rsp+0E0h+var_B8], rax; __int64
0x180065520  lea     rax, [rbp+47h+var_9C]
0x180065524  mov     [rsp+0E0h+var_C0], rax; __int64
0x180065529  lea     r9, [rbp+47h+var_A0]
0x18006552d  lea     r8, aWspFacadeStora_21; "Wsp::Facade::StorageHealthFacade::GetDi"...
0x180065534  call    ??$WriteLine@_W$$BY0DE@DHH$$BY0DH@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DE@$$CBDAEBH2AEAY0DH@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [55]>(wchar_t const *,char const (&)[52],int const &,int const &,wchar_t const (&)[55])
0x180065539  nop
0x18006553a  lea     rcx, [rbp+47h+var_78]
0x18006553e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180065543  lea     r8, ?EmptyLiteral@cxl@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const cxl::EmptyLiteral
0x18006554a  lea     rdx, [rbp+47h+var_78]
0x18006554e  mov     rcx, [r13+0A0h]
0x180065555  call    ?GetNode@ClusterFacade@Facade@ClusApi@@QEAA?AV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; ClusApi::Facade::ClusterFacade::GetNode(std::wstring const &)
0x18006555a  nop
0x18006555b  cmp     [rbp+47h+var_78], 0
0x180065560  jnz     loc_180065618
0x180065566  lea     rdx, aFailedToOpenTh; "Failed to open the local node to get di"...
0x18006556d  lea     rcx, [rbp+47h+var_58]
0x180065571  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180065576  nop
0x180065577  mov     eax, cs:dword_18014B6A8
0x18006557d  mov     ebx, 88Dh
0x180065582  cmp     eax, 2
0x180065585  jbe     short loc_1800655D5
0x180065587  lea     rcx, [rbp+47h+var_58]
0x18006558b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180065590  mov     qword ptr [rbp+47h+var_9C+4], rax
0x180065594  mov     dword ptr [rbp+47h+var_9C], edi
0x180065597  mov     [rbp+47h+var_A0], ebx
0x18006559a  lea     rax, aWspFacadeStora_21; "Wsp::Facade::StorageHealthFacade::GetDi"...
0x1800655a1  mov     [rbp+47h+var_90], rax
0x1800655a5  lea     rax, [rbp+47h+var_9C+4]
0x1800655a9  mov     [rsp+0E0h+var_A8], rax
0x1800655ae  lea     rax, [rbp+47h+var_9C]
0x1800655b2  mov     [rsp+0E0h+var_B0], rax
0x1800655b7  lea     rax, [rbp+47h+var_A0]
0x1800655bb  mov     [rsp+0E0h+var_B8], rax
0x1800655c0  lea     rax, [rbp+47h+var_90]
0x1800655c4  mov     [rsp+0E0h+var_C0], rax
0x1800655c9  lea     rdx, byte_180129DAF
0x1800655d0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1800655d5  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x1800655da  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x1800655de  mov     dword ptr [rbp+47h+var_9C], edi
0x1800655e1  mov     [rbp+47h+var_A0], ebx
0x1800655e4  lea     rax, [rbp+47h+var_9C]
0x1800655e8  mov     [rsp+0E0h+var_C0], rax; __int64
0x1800655ed  lea     r9, [rbp+47h+var_A0]
0x1800655f1  call    ??$WriteLine@_W$$BY0DE@DHH$$BY0DG@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DE@$$CBDAEBH2AEAY0DG@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [54]>(wchar_t const *,char const (&)[52],int const &,int const &,wchar_t const (&)[54])
0x1800655f6  nop
0x1800655f7  lea     rcx, [rbp+47h+var_58]
0x1800655fb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180065600  nop
0x180065601  mov     rcx, [rbp+47h+var_70]; this
0x180065605  test    rcx, rcx
0x180065608  jz      loc_1800656DF
0x18006560e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180065613  jmp     loc_1800656DF
0x180065618  lea     rdx, [rbp+47h+var_78]
0x18006561c  lea     rcx, [rbp+47h+var_88]
0x180065620  call    ??4?$shared_ptr@VCacheObject@DataStore@ClusWmi@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(std::shared_ptr<ClusWmi::DataStore::CacheObject> const &)
0x180065625  nop
0x180065626  mov     rcx, [rbp+47h+var_70]; this
0x18006562a  test    rcx, rcx
0x18006562d  jz      short loc_180065634
0x18006562f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180065634  cmp     qword ptr [rbx+8], 0
0x180065639  jnz     short loc_1800656BA
0x18006563b  lea     rdx, aNoCacheDisksFo; "No cache disks found so we are moving o"...
0x180065642  lea     rcx, [rbp+47h+var_78]
0x180065646  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006564b  nop
0x18006564c  mov     eax, cs:dword_18014B6A8
0x180065652  cmp     eax, 5
0x180065655  jbe     short loc_18006568E
0x180065657  mov     edx, 4000h
0x18006565c  lea     rcx, dword_18014B6A8
0x180065663  call    _tlgKeywordOn
0x180065668  test    al, al
0x18006566a  jz      short loc_18006568E
0x18006566c  lea     rcx, [rbp+47h+var_78]
0x180065670  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180065675  mov     qword ptr [rbp+47h+var_9C+4], rax
0x180065679  lea     rax, [rbp+47h+var_9C+4]
0x18006567d  mov     [rsp+0E0h+var_C0], rax
0x180065682  lea     rdx, word_180129DEE
0x180065689  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18006568e  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180065693  lea     rbx, [rax+0A0h]
0x18006569a  lea     rdx, [rbp+47h+var_78]
0x18006569e  mov     rcx, rbx
0x1800656a1  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x1800656a6  mov     rcx, rbx
0x1800656a9  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x1800656ae  nop
0x1800656af  lea     rcx, [rbp+47h+var_78]
0x1800656b3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800656b8  jmp     short loc_1800656DF
0x1800656ba  mov     [rsp+0E0h+var_C0], r15
0x1800656bf  mov     r9, r14
0x1800656c2  mov     r8, rbx
0x1800656c5  lea     rdx, [rbp+47h+var_88]
0x1800656c9  mov     rcx, rsi
0x1800656cc  test    r12b, r12b
0x1800656cf  jz      short loc_1800656D8
0x1800656d1  call    ?WaitForCacheEnable@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@6@AEAVMiContext@mi@@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z; Wsp::Facade::StorageHealthFacade::WaitForCacheEnable(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,std::map<std::wstring,Wsp::Facade::MaintenanceDisk> &,mi::MiContext &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)
0x1800656d6  jmp     short loc_1800656DD
0x1800656d8  call    ?WaitForCacheDrain@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@6@AEAVMiContext@mi@@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z; Wsp::Facade::StorageHealthFacade::WaitForCacheDrain(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,std::map<std::wstring,Wsp::Facade::MaintenanceDisk> &,mi::MiContext &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)
0x1800656dd  mov     edi, eax
0x1800656df  mov     rcx, [rbp+47h+var_88+8]; this
0x1800656e3  test    rcx, rcx
0x1800656e6  jz      short loc_1800656ED
0x1800656e8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800656ed  mov     eax, edi
0x1800656ef  mov     rcx, [rbp+47h+var_38]
0x1800656f3  xor     rcx, rsp; StackCookie
0x1800656f6  call    __security_check_cookie
0x1800656fb  mov     rbx, [rsp+0E0h+arg_18]
0x180065703  add     rsp, 0B0h
0x18006570a  pop     r15
0x18006570c  pop     r14
0x18006570e  pop     r13
0x180065710  pop     r12
0x180065712  pop     rdi
0x180065713  pop     rsi
0x180065714  pop     rbp
0x180065715  retn
```
