# Wsp::Facade::StorageHealthFacade::GetDiskCacheState(Wsp::Facade::MaintenanceModeStruct const &,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,Wsp::Facade::MaintenanceDisk,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,Wsp::Facade::MaintenanceDisk>>> &,bool,mi::MiContext &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x180066c34`
- end: `0x180066f3f`
- name: `?GetDiskCacheState@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBUMaintenanceModeStruct@23@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@std@@_NAEAVMiContext@mi@@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@7@@Z`
- size: `779`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180062798`
- `0x180064604`

## callees

- `0x1800013d0`
- `0x18000163c`
- `0x1800016d0`
- `0x180002b50`
- `0x18000bb84`
- `0x18000bc64`
- `0x18000c2f8`
- `0x18000cd9c`
- `0x18000da34`
- `0x18000daf8`
- `0x18000e4b8`
- `0x18000f34c`
- `0x180018af0`
- `0x18005b21c`
- `0x18005b280`
- `0x180066c34`
- `0x18006dab4`
- `0x18006e26c`
- `0x180082960`

## string_xrefs

- `0x180066cd2`: `Wsp::Facade::StorageHealthFacade::GetDiskCacheState`
- `0x180066d55`: `Wsp::Facade::StorageHealthFacade::GetDiskCacheState`
- `0x180066dc2`: `Wsp::Facade::StorageHealthFacade::GetDiskCacheState`
- `0x180066cb6`: `Failed to open the target node to get disk cache state`
- `0x180066d3c`: `Failed to open the target node to get disk cache state`
- `0x180066e63`: `No cache disks found so we are moving on`
- `0x180066d8e`: `Failed to open the local node to get disk cache state`

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
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  struct cxl::TraceManager *v16; // rax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  struct cxl::TraceManager *v20; // rax
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
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
      if ( (unsigned int)dword_18014D6A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18014D6A8, 0x4000) )
      {
        *(_QWORD *)&v28[1] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v31);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
          v21,
          (unsigned int)&byte_18012BE37,
          v22,
          v23,
          (__int64)&v28[1]);
      }
      v24 = (char *)cxl::TraceManager::Instance() + 160;
      cxl::CxlTraits<std::wstring>::WriteTo(v24, &v31);
      cxl::TextWriter::operator<<<cxl::ENDL>(v24);
      std::wstring::_Tidy_deallocate(&v31);
    }
    goto LABEL_23;
  }
  std::wstring::wstring(&v31, L"Failed to open the target node to get disk cache state");
  v11 = 59000;
  if ( (unsigned int)dword_18014D6A8 > 2 )
  {
    v29 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v31);
    v27 = 59000;
    v28[0] = 2182;
    *(_QWORD *)&v28[1] = v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
      v13,
      (unsigned int)&byte_18012BEC7,
      v14,
      v15,
      (__int64)&v28[1],
      (__int64)v28,
      (__int64)&v27,
      (__int64)&v29);
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
  if ( (unsigned int)dword_18014D6A8 > 2 )
  {
    *(_QWORD *)&v28[1] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v33);
    v28[0] = 59000;
    v27 = 2189;
    v29 = "Wsp::Facade::StorageHealthFacade::GetDiskCacheState";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
      v17,
      (unsigned int)qword_18012BDF8,
      v18,
      v19,
      (__int64)&v29,
      (__int64)&v27,
      (__int64)v28,
      (__int64)&v28[1]);
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
0x180066c34  mov     [rsp-8+arg_18], rbx
0x180066c39  push    rbp
0x180066c3a  push    rsi
0x180066c3b  push    rdi
0x180066c3c  push    r12
0x180066c3e  push    r13
0x180066c40  push    r14
0x180066c42  push    r15
0x180066c44  lea     rbp, [rsp-17h]
0x180066c49  sub     rsp, 0B0h
0x180066c50  mov     rax, cs:__security_cookie
0x180066c57  xor     rax, rsp
0x180066c5a  mov     [rbp+47h+var_38], rax
0x180066c5e  mov     r12b, r9b
0x180066c61  mov     rbx, r8
0x180066c64  mov     r13, rdx
0x180066c67  mov     rsi, rcx
0x180066c6a  mov     r14, [rbp+47h+arg_20]
0x180066c6e  mov     r15, [rbp+47h+arg_28]
0x180066c72  xorps   xmm0, xmm0
0x180066c75  movdqu  xmmword ptr [rbp+47h+var_88], xmm0
0x180066c7a  lea     r8, [rdx+18h]
0x180066c7e  lea     rdx, [rbp+47h+var_78]
0x180066c82  mov     rcx, [r13+0A0h]
0x180066c89  call    ?GetNode@ClusterFacade@Facade@ClusApi@@QEAA?AV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; ClusApi::Facade::ClusterFacade::GetNode(std::wstring const &)
0x180066c8e  mov     rdx, rax
0x180066c91  lea     rcx, [rbp+47h+var_88]
0x180066c95  call    ??4?$shared_ptr@$$CBVSPACES_VirtualDisk@mismpstorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(std::shared_ptr<mismpstorage::SPACES_VirtualDisk const> &&)
0x180066c9a  mov     rcx, [rbp+47h+var_70]; this
0x180066c9e  test    rcx, rcx
0x180066ca1  jz      short loc_180066CA8
0x180066ca3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180066ca8  cmp     [rbp+47h+var_88], 0
0x180066cad  jz      short loc_180066CB6
0x180066caf  xor     edi, edi
0x180066cb1  jmp     loc_180066E5C
0x180066cb6  lea     rdx, aFailedToOpenTh_0; "Failed to open the target node to get d"...
0x180066cbd  lea     rcx, [rbp+47h+var_78]
0x180066cc1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180066cc6  nop
0x180066cc7  mov     eax, cs:dword_18014D6A8
0x180066ccd  mov     edi, 0E678h
0x180066cd2  lea     rdx, aWspFacadeStora_21; "Wsp::Facade::StorageHealthFacade::GetDi"...
0x180066cd9  cmp     eax, 2
0x180066cdc  jbe     short loc_180066D29
0x180066cde  lea     rcx, [rbp+47h+var_78]
0x180066ce2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180066ce7  mov     [rbp+47h+var_90], rax
0x180066ceb  mov     [rbp+47h+var_A0], edi
0x180066cee  mov     dword ptr [rbp+47h+var_9C], 886h
0x180066cf5  mov     qword ptr [rbp+47h+var_9C+4], rdx
0x180066cf9  lea     rax, [rbp+47h+var_90]
0x180066cfd  mov     [rsp+0E0h+var_A8], rax
0x180066d02  lea     rax, [rbp+47h+var_A0]
0x180066d06  mov     [rsp+0E0h+var_B0], rax
0x180066d0b  lea     rax, [rbp+47h+var_9C]
0x180066d0f  mov     [rsp+0E0h+var_B8], rax
0x180066d14  lea     rax, [rbp+47h+var_9C+4]
0x180066d18  mov     [rsp+0E0h+var_C0], rax
0x180066d1d  lea     rdx, byte_18012BEC7
0x180066d24  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180066d29  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180066d2e  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180066d32  mov     dword ptr [rbp+47h+var_9C], edi
0x180066d35  mov     [rbp+47h+var_A0], 886h
0x180066d3c  lea     rax, aFailedToOpenTh_0; "Failed to open the target node to get d"...
0x180066d43  mov     [rsp+0E0h+var_B8], rax; __int64
0x180066d48  lea     rax, [rbp+47h+var_9C]
0x180066d4c  mov     [rsp+0E0h+var_C0], rax; __int64
0x180066d51  lea     r9, [rbp+47h+var_A0]
0x180066d55  lea     r8, aWspFacadeStora_21; "Wsp::Facade::StorageHealthFacade::GetDi"...
0x180066d5c  call    ??$WriteLine@_W$$BY0DE@DHH$$BY0DH@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DE@$$CBDAEBH2AEAY0DH@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [55]>(wchar_t const *,char const (&)[52],int const &,int const &,wchar_t const (&)[55])
0x180066d61  nop
0x180066d62  lea     rcx, [rbp+47h+var_78]
0x180066d66  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066d6b  lea     r8, ?EmptyLiteral@cxl@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const cxl::EmptyLiteral
0x180066d72  lea     rdx, [rbp+47h+var_78]
0x180066d76  mov     rcx, [r13+0A0h]
0x180066d7d  call    ?GetNode@ClusterFacade@Facade@ClusApi@@QEAA?AV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; ClusApi::Facade::ClusterFacade::GetNode(std::wstring const &)
0x180066d82  nop
0x180066d83  cmp     [rbp+47h+var_78], 0
0x180066d88  jnz     loc_180066E40
0x180066d8e  lea     rdx, aFailedToOpenTh; "Failed to open the local node to get di"...
0x180066d95  lea     rcx, [rbp+47h+var_58]
0x180066d99  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180066d9e  nop
0x180066d9f  mov     eax, cs:dword_18014D6A8
0x180066da5  mov     ebx, 88Dh
0x180066daa  cmp     eax, 2
0x180066dad  jbe     short loc_180066DFD
0x180066daf  lea     rcx, [rbp+47h+var_58]
0x180066db3  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180066db8  mov     qword ptr [rbp+47h+var_9C+4], rax
0x180066dbc  mov     dword ptr [rbp+47h+var_9C], edi
0x180066dbf  mov     [rbp+47h+var_A0], ebx
0x180066dc2  lea     rax, aWspFacadeStora_21; "Wsp::Facade::StorageHealthFacade::GetDi"...
0x180066dc9  mov     [rbp+47h+var_90], rax
0x180066dcd  lea     rax, [rbp+47h+var_9C+4]
0x180066dd1  mov     [rsp+0E0h+var_A8], rax
0x180066dd6  lea     rax, [rbp+47h+var_9C]
0x180066dda  mov     [rsp+0E0h+var_B0], rax
0x180066ddf  lea     rax, [rbp+47h+var_A0]
0x180066de3  mov     [rsp+0E0h+var_B8], rax
0x180066de8  lea     rax, [rbp+47h+var_90]
0x180066dec  mov     [rsp+0E0h+var_C0], rax
0x180066df1  lea     rdx, qword_18012BDF8
0x180066df8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180066dfd  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180066e02  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180066e06  mov     dword ptr [rbp+47h+var_9C], edi
0x180066e09  mov     [rbp+47h+var_A0], ebx
0x180066e0c  lea     rax, [rbp+47h+var_9C]
0x180066e10  mov     [rsp+0E0h+var_C0], rax; __int64
0x180066e15  lea     r9, [rbp+47h+var_A0]
0x180066e19  call    ??$WriteLine@_W$$BY0DE@DHH$$BY0DG@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DE@$$CBDAEBH2AEAY0DG@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [52],int,int,wchar_t [54]>(wchar_t const *,char const (&)[52],int const &,int const &,wchar_t const (&)[54])
0x180066e1e  nop
0x180066e1f  lea     rcx, [rbp+47h+var_58]
0x180066e23  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066e28  nop
0x180066e29  mov     rcx, [rbp+47h+var_70]; this
0x180066e2d  test    rcx, rcx
0x180066e30  jz      loc_180066F07
0x180066e36  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180066e3b  jmp     loc_180066F07
0x180066e40  lea     rdx, [rbp+47h+var_78]
0x180066e44  lea     rcx, [rbp+47h+var_88]
0x180066e48  call    ??4?$shared_ptr@VCacheObject@DataStore@ClusWmi@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(std::shared_ptr<ClusWmi::DataStore::CacheObject> const &)
0x180066e4d  nop
0x180066e4e  mov     rcx, [rbp+47h+var_70]; this
0x180066e52  test    rcx, rcx
0x180066e55  jz      short loc_180066E5C
0x180066e57  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180066e5c  cmp     qword ptr [rbx+8], 0
0x180066e61  jnz     short loc_180066EE2
0x180066e63  lea     rdx, aNoCacheDisksFo; "No cache disks found so we are moving o"...
0x180066e6a  lea     rcx, [rbp+47h+var_78]
0x180066e6e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180066e73  nop
0x180066e74  mov     eax, cs:dword_18014D6A8
0x180066e7a  cmp     eax, 5
0x180066e7d  jbe     short loc_180066EB6
0x180066e7f  mov     edx, 4000h
0x180066e84  lea     rcx, dword_18014D6A8
0x180066e8b  call    _tlgKeywordOn
0x180066e90  test    al, al
0x180066e92  jz      short loc_180066EB6
0x180066e94  lea     rcx, [rbp+47h+var_78]
0x180066e98  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180066e9d  mov     qword ptr [rbp+47h+var_9C+4], rax
0x180066ea1  lea     rax, [rbp+47h+var_9C+4]
0x180066ea5  mov     [rsp+0E0h+var_C0], rax
0x180066eaa  lea     rdx, byte_18012BE37
0x180066eb1  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180066eb6  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180066ebb  lea     rbx, [rax+0A0h]
0x180066ec2  lea     rdx, [rbp+47h+var_78]
0x180066ec6  mov     rcx, rbx
0x180066ec9  call    ?WriteTo@?$CxlTraits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@SAXAEAVTextWriter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUFormat@2@@Z; cxl::CxlTraits<std::wstring>::WriteTo(cxl::TextWriter &,std::wstring const &,cxl::Format const &)
0x180066ece  mov     rcx, rbx
0x180066ed1  call    ??$?6UENDL@cxl@@@TextWriter@cxl@@QEAAAEAV01@AEBUENDL@1@@Z; cxl::TextWriter::operator<<<cxl::ENDL>(cxl::ENDL const &)
0x180066ed6  nop
0x180066ed7  lea     rcx, [rbp+47h+var_78]
0x180066edb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066ee0  jmp     short loc_180066F07
0x180066ee2  mov     [rsp+0E0h+var_C0], r15
0x180066ee7  mov     r9, r14
0x180066eea  mov     r8, rbx
0x180066eed  lea     rdx, [rbp+47h+var_88]
0x180066ef1  mov     rcx, rsi
0x180066ef4  test    r12b, r12b
0x180066ef7  jz      short loc_180066F00
0x180066ef9  call    ?WaitForCacheEnable@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@6@AEAVMiContext@mi@@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z; Wsp::Facade::StorageHealthFacade::WaitForCacheEnable(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,std::map<std::wstring,Wsp::Facade::MaintenanceDisk> &,mi::MiContext &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)
0x180066efe  jmp     short loc_180066F05
0x180066f00  call    ?WaitForCacheDrain@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@6@AEAVMiContext@mi@@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z; Wsp::Facade::StorageHealthFacade::WaitForCacheDrain(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,std::map<std::wstring,Wsp::Facade::MaintenanceDisk> &,mi::MiContext &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)
0x180066f05  mov     edi, eax
0x180066f07  mov     rcx, [rbp+47h+var_88+8]; this
0x180066f0b  test    rcx, rcx
0x180066f0e  jz      short loc_180066F15
0x180066f10  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180066f15  mov     eax, edi
0x180066f17  mov     rcx, [rbp+47h+var_38]
0x180066f1b  xor     rcx, rsp; StackCookie
0x180066f1e  call    __security_check_cookie
0x180066f23  mov     rbx, [rsp+0E0h+arg_18]
0x180066f2b  add     rsp, 0B0h
0x180066f32  pop     r15
0x180066f34  pop     r14
0x180066f36  pop     r13
0x180066f38  pop     r12
0x180066f3a  pop     rdi
0x180066f3b  pop     rsi
0x180066f3c  pop     rbp
0x180066f3d  retn
```
