# Wsp::Facade::StorageHealthFacade::ChangeWriteCache(bool &,Wsp::Facade::MaintenanceModeStruct const &,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,Wsp::Facade::MaintenanceDisk,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,Wsp::Facade::MaintenanceDisk>>> &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x18005f660`
- end: `0x18005f9d8`
- name: `?ChangeWriteCache@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEA_NAEBUMaintenanceModeStruct@23@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@std@@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@7@@Z`
- size: `888`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: ``

## callers

- `0x180060f98`
- `0x180062e00`

## callees

- `0x1800016b0`
- `0x180002ae0`
- `0x18000b800`
- `0x18000b8e4`
- `0x18000c9f0`
- `0x18000d618`
- `0x18000d6dc`
- `0x18000e044`
- `0x180018154`
- `0x18005952c`
- `0x180059590`
- `0x18005ec50`
- `0x18005f660`
- `0x18005f9e0`
- `0x1800602a0`
- `0x180080590`

## string_xrefs

- `0x18005f6f8`: `Wsp::Facade::StorageHealthFacade::ChangeWriteCache`
- `0x18005f6dc`: `Failed to open the target node to change the S2D write cache`
- `0x18005f7a1`: `Failed to open the local node to change the S2D write cache`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Wsp::Facade::StorageHealthFacade::ChangeWriteCache(
        __int64 a1,
        _BYTE *a2,
        unsigned int *a3,
        __int64 **a4,
        __int64 a5)
{
  unsigned int v8; // ebx
  __int64 Node; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  struct cxl::TraceManager *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  struct cxl::TraceManager *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v23; // rcx
  unsigned int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rcx
  unsigned int v30; // eax
  int v31; // [rsp+40h] [rbp-51h] BYREF
  const char *v32; // [rsp+48h] [rbp-49h] BYREF
  __int64 i; // [rsp+50h] [rbp-41h] BYREF
  std::_Ref_count_base *v34[2]; // [rsp+58h] [rbp-39h] BYREF
  const char *v35; // [rsp+68h] [rbp-29h] BYREF
  __int64 v36; // [rsp+70h] [rbp-21h] BYREF
  std::_Ref_count_base *v37; // [rsp+78h] [rbp-19h]
  _BYTE v38[32]; // [rsp+90h] [rbp-1h] BYREF

  v8 = 0;
  *(_OWORD *)v34 = 0;
  Node = ClusApi::Facade::ClusterFacade::GetNode(*((_QWORD *)a3 + 20), &v36, a3 + 6);
  std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(v34, Node);
  if ( v37 )
    std::_Ref_count_base::_Decref(v37);
  if ( !v34[0] )
  {
    std::wstring::wstring(&v36, L"Failed to open the target node to change the S2D write cache");
    v8 = 59000;
    if ( (unsigned int)dword_18014B6A8 > 2 )
    {
      v35 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v36);
      v31 = 59000;
      LODWORD(i) = 1956;
      v32 = "Wsp::Facade::StorageHealthFacade::ChangeWriteCache";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v10,
        (__int64)qword_18012A0D8,
        v11,
        v12,
        &v32,
        (__int64)&i,
        (__int64)&v31,
        &v35);
    }
    v13 = cxl::TraceManager::Instance();
    LODWORD(i) = 59000;
    v31 = 1956;
    cxl::TextWriter::WriteLine<wchar_t,char [51],int,int,wchar_t [61]>(
      (struct cxl::TraceManager *)((char *)v13 + 40),
      v14,
      v15,
      (__int64)&v31,
      (__int64)&i);
    std::wstring::_Tidy_deallocate(&v36);
    ClusApi::Facade::ClusterFacade::GetNode(*((_QWORD *)a3 + 20), &v36, cxl::EmptyLiteral);
    if ( !v36 )
    {
      std::wstring::wstring(v38, L"Failed to open the local node to change the S2D write cache");
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v32 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v38);
        LODWORD(i) = 59000;
        v31 = 1963;
        v35 = "Wsp::Facade::StorageHealthFacade::ChangeWriteCache";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v16,
          (__int64)byte_180129FDD,
          v17,
          v18,
          &v35,
          (__int64)&v31,
          (__int64)&i,
          &v32);
      }
      v19 = cxl::TraceManager::Instance();
      LODWORD(i) = 59000;
      v31 = 1963;
      cxl::TextWriter::WriteLine<wchar_t,char [51],int,int,wchar_t [60]>(
        (struct cxl::TraceManager *)((char *)v19 + 40),
        v20,
        v21,
        (__int64)&v31,
        (__int64)&i);
      std::wstring::_Tidy_deallocate(v38);
      if ( v37 )
        std::_Ref_count_base::_Decref(v37);
      goto LABEL_11;
    }
    std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(v34, &v36);
    if ( v37 )
      std::_Ref_count_base::_Decref(v37);
  }
  v23 = *a3;
  if ( (((_DWORD)v23 - 5) & 0xFFFFFFFB) != 0 )
  {
    if ( (_DWORD)v23 == 12 )
    {
      v32 = 0;
      if ( *a2 )
        v24 = Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag(v23, (__int64)v34, &v32, a5);
      else
        v24 = Wsp::Facade::StorageHealthFacade::ChangeWriteCache(v23, (__int64)v34, a3 + 39, a2, &v32, a5);
      v8 = v24;
    }
  }
  else
  {
    v25 = **a4;
    i = v25;
    while ( !*(_BYTE *)(v25 + 25) )
    {
      if ( *(_BYTE *)(v25 + 224) )
      {
        v32 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v25 + 96);
        v27 = *a2
            ? Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag(v26, (__int64)v34, &v32, a5)
            : Wsp::Facade::StorageHealthFacade::ChangeWriteCache(v26, (__int64)v34, a3 + 39, a2, &v32, a5);
        v8 = v27;
        if ( v27 )
          goto LABEL_11;
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>>,std::_Iterator_base0>::operator++(&i);
      v25 = i;
    }
    v28 = **a4;
    for ( i = v28; !*(_BYTE *)(v28 + 25); v28 = i )
    {
      if ( !*(_BYTE *)(v28 + 224) )
      {
        v32 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v28 + 96);
        v30 = *a2
            ? Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag(v29, (__int64)v34, &v32, a5)
            : Wsp::Facade::StorageHealthFacade::ChangeWriteCache(v29, (__int64)v34, a3 + 39, a2, &v32, a5);
        v8 = v30;
        if ( v30 )
          break;
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>>,std::_Iterator_base0>::operator++(&i);
    }
  }
LABEL_11:
  if ( v34[1] )
    std::_Ref_count_base::_Decref(v34[1]);
  return v8;
}

```

## disassembly

```asm
0x18005f660  mov     [rsp-8+arg_0], rbx
0x18005f665  mov     [rsp-8+arg_8], rsi
0x18005f66a  push    rbp
0x18005f66b  push    rdi
0x18005f66c  push    r13
0x18005f66e  push    r14
0x18005f670  push    r15
0x18005f672  lea     rbp, [rsp-2Fh]
0x18005f677  sub     rsp, 0C0h
0x18005f67e  mov     rax, cs:__security_cookie
0x18005f685  xor     rax, rsp
0x18005f688  mov     [rbp+4Fh+var_30], rax
0x18005f68c  mov     r15, r9
0x18005f68f  mov     r14, r8
0x18005f692  mov     rdi, rdx
0x18005f695  mov     rsi, [rbp+4Fh+arg_20]
0x18005f699  xor     ebx, ebx
0x18005f69b  xorps   xmm0, xmm0
0x18005f69e  movdqu  xmmword ptr [rbp+4Fh+var_88], xmm0
0x18005f6a3  add     r8, 18h
0x18005f6a7  lea     rdx, [rbp+4Fh+var_70]
0x18005f6ab  mov     rcx, [r14+0A0h]
0x18005f6b2  call    ?GetNode@ClusterFacade@Facade@ClusApi@@QEAA?AV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; ClusApi::Facade::ClusterFacade::GetNode(std::wstring const &)
0x18005f6b7  mov     rdx, rax
0x18005f6ba  lea     rcx, [rbp+4Fh+var_88]
0x18005f6be  call    ??4?$shared_ptr@$$CBVSPACES_VirtualDisk@mismpstorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(std::shared_ptr<mismpstorage::SPACES_VirtualDisk const> &&)
0x18005f6c3  mov     rcx, [rbp+4Fh+var_68]; this
0x18005f6c7  test    rcx, rcx
0x18005f6ca  jz      short loc_18005F6D1
0x18005f6cc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005f6d1  cmp     [rbp+4Fh+var_88], 0
0x18005f6d6  jnz     loc_18005F898
0x18005f6dc  lea     rdx, aFailedToOpenTh_2; "Failed to open the target node to chang"...
0x18005f6e3  lea     rcx, [rbp+4Fh+var_70]
0x18005f6e7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18005f6ec  nop
0x18005f6ed  mov     eax, cs:dword_18014B6A8
0x18005f6f3  mov     ebx, 0E678h
0x18005f6f8  lea     r13, aWspFacadeStora_14; "Wsp::Facade::StorageHealthFacade::Chang"...
0x18005f6ff  cmp     eax, 2
0x18005f702  jbe     short loc_18005F74F
0x18005f704  lea     rcx, [rbp+4Fh+var_70]
0x18005f708  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005f70d  mov     [rbp+4Fh+var_78], rax
0x18005f711  mov     [rbp+4Fh+var_A0], ebx
0x18005f714  mov     dword ptr [rbp+4Fh+var_90], 7A4h
0x18005f71b  mov     [rbp+4Fh+var_98], r13
0x18005f71f  lea     rax, [rbp+4Fh+var_78]
0x18005f723  mov     [rsp+0E0h+var_A8], rax
0x18005f728  lea     rax, [rbp+4Fh+var_A0]
0x18005f72c  mov     [rsp+0E0h+var_B0], rax
0x18005f731  lea     rax, [rbp+4Fh+var_90]
0x18005f735  mov     [rsp+0E0h+var_B8], rax
0x18005f73a  lea     rax, [rbp+4Fh+var_98]
0x18005f73e  mov     [rsp+0E0h+var_C0], rax
0x18005f743  lea     rdx, qword_18012A0D8
0x18005f74a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x18005f74f  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18005f754  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x18005f758  mov     dword ptr [rbp+4Fh+var_90], ebx
0x18005f75b  mov     [rbp+4Fh+var_A0], 7A4h
0x18005f762  lea     rax, [rbp+4Fh+var_90]
0x18005f766  mov     [rsp+0E0h+var_C0], rax; __int64
0x18005f76b  lea     r9, [rbp+4Fh+var_A0]
0x18005f76f  call    ??$WriteLine@_W$$BY0DD@DHH$$BY0DN@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DD@$$CBDAEBH2AEAY0DN@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [51],int,int,wchar_t [61]>(wchar_t const *,char const (&)[51],int const &,int const &,wchar_t const (&)[61])
0x18005f774  nop
0x18005f775  lea     rcx, [rbp+4Fh+var_70]
0x18005f779  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005f77e  lea     r8, ?EmptyLiteral@cxl@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const cxl::EmptyLiteral
0x18005f785  lea     rdx, [rbp+4Fh+var_70]
0x18005f789  mov     rcx, [r14+0A0h]
0x18005f790  call    ?GetNode@ClusterFacade@Facade@ClusApi@@QEAA?AV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; ClusApi::Facade::ClusterFacade::GetNode(std::wstring const &)
0x18005f795  nop
0x18005f796  cmp     [rbp+4Fh+var_70], 0
0x18005f79b  jnz     loc_18005F87C
0x18005f7a1  lea     rdx, aFailedToOpenTh_1; "Failed to open the local node to change"...
0x18005f7a8  lea     rcx, [rbp+4Fh+var_50]
0x18005f7ac  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18005f7b1  nop
0x18005f7b2  mov     eax, cs:dword_18014B6A8
0x18005f7b8  mov     edi, 7ABh
0x18005f7bd  cmp     eax, 2
0x18005f7c0  jbe     short loc_18005F809
0x18005f7c2  lea     rcx, [rbp+4Fh+var_50]
0x18005f7c6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005f7cb  mov     [rbp+4Fh+var_98], rax
0x18005f7cf  mov     dword ptr [rbp+4Fh+var_90], ebx
0x18005f7d2  mov     [rbp+4Fh+var_A0], edi
0x18005f7d5  mov     [rbp+4Fh+var_78], r13
0x18005f7d9  lea     rax, [rbp+4Fh+var_98]
0x18005f7dd  mov     [rsp+0E0h+var_A8], rax
0x18005f7e2  lea     rax, [rbp+4Fh+var_90]
0x18005f7e6  mov     [rsp+0E0h+var_B0], rax
0x18005f7eb  lea     rax, [rbp+4Fh+var_A0]
0x18005f7ef  mov     [rsp+0E0h+var_B8], rax
0x18005f7f4  lea     rax, [rbp+4Fh+var_78]
0x18005f7f8  mov     [rsp+0E0h+var_C0], rax
0x18005f7fd  lea     rdx, byte_180129FDD
0x18005f804  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x18005f809  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18005f80e  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x18005f812  mov     dword ptr [rbp+4Fh+var_90], ebx
0x18005f815  mov     [rbp+4Fh+var_A0], edi
0x18005f818  lea     rax, [rbp+4Fh+var_90]
0x18005f81c  mov     [rsp+0E0h+var_C0], rax; __int64
0x18005f821  lea     r9, [rbp+4Fh+var_A0]
0x18005f825  call    ??$WriteLine@_W$$BY0DD@DHH$$BY0DM@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DD@$$CBDAEBH2AEAY0DM@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [51],int,int,wchar_t [60]>(wchar_t const *,char const (&)[51],int const &,int const &,wchar_t const (&)[60])
0x18005f82a  nop
0x18005f82b  lea     rcx, [rbp+4Fh+var_50]
0x18005f82f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005f834  nop
0x18005f835  mov     rcx, [rbp+4Fh+var_68]; this
0x18005f839  test    rcx, rcx
0x18005f83c  jz      short loc_18005F844
0x18005f83e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005f843  nop
0x18005f844  mov     rcx, [rbp+4Fh+var_88+8]; this
0x18005f848  test    rcx, rcx
0x18005f84b  jz      short loc_18005F852
0x18005f84d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005f852  mov     eax, ebx
0x18005f854  mov     rcx, [rbp+4Fh+var_30]
0x18005f858  xor     rcx, rsp; StackCookie
0x18005f85b  call    __security_check_cookie
0x18005f860  lea     r11, [rsp+0E0h+var_20]
0x18005f868  mov     rbx, [r11+30h]
0x18005f86c  mov     rsi, [r11+38h]
0x18005f870  mov     rsp, r11
0x18005f873  pop     r15
0x18005f875  pop     r14
0x18005f877  pop     r13
0x18005f879  pop     rdi
0x18005f87a  pop     rbp
0x18005f87b  retn
0x18005f87c  lea     rdx, [rbp+4Fh+var_70]
0x18005f880  lea     rcx, [rbp+4Fh+var_88]
0x18005f884  call    ??4?$shared_ptr@VCacheObject@DataStore@ClusWmi@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(std::shared_ptr<ClusWmi::DataStore::CacheObject> const &)
0x18005f889  nop
0x18005f88a  mov     rcx, [rbp+4Fh+var_68]; this
0x18005f88e  test    rcx, rcx
0x18005f891  jz      short loc_18005F898
0x18005f893  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005f898  mov     ecx, [r14]
0x18005f89b  lea     eax, [rcx-5]
0x18005f89e  test    eax, 0FFFFFFFBh
0x18005f8a3  jz      short loc_18005F8ED
0x18005f8a5  cmp     ecx, 0Ch
0x18005f8a8  jnz     short loc_18005F844
0x18005f8aa  mov     [rbp+4Fh+var_98], 0
0x18005f8b2  lea     rdx, [rbp+4Fh+var_88]
0x18005f8b6  cmp     byte ptr [rdi], 0
0x18005f8b9  jnz     short loc_18005F8DF
0x18005f8bb  lea     r8, [r14+9Ch]
0x18005f8c2  mov     [rsp+0E0h+var_B8], rsi
0x18005f8c7  lea     rax, [rbp+4Fh+var_98]
0x18005f8cb  mov     [rsp+0E0h+var_C0], rax
0x18005f8d0  mov     r9, rdi
0x18005f8d3  call    ?ChangeWriteCache@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBW4S2DCacheMode@@AEA_NAEBQEB_WAEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z; Wsp::Facade::StorageHealthFacade::ChangeWriteCache(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,S2DCacheMode const &,bool &,wchar_t const * const &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)
0x18005f8d8  mov     ebx, eax
0x18005f8da  jmp     loc_18005F844
0x18005f8df  mov     r9, rsi
0x18005f8e2  lea     r8, [rbp+4Fh+var_98]
0x18005f8e6  call    ?ClearReadOnlyFlag@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBQEB_WAEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z; Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,wchar_t const * const &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)
0x18005f8eb  jmp     short loc_18005F8D8
0x18005f8ed  mov     rax, [r15]
0x18005f8f0  mov     rax, [rax]
0x18005f8f3  mov     [rbp+4Fh+var_90], rax
0x18005f8f7  cmp     byte ptr [rax+19h], 0
0x18005f8fb  jnz     short loc_18005F960
0x18005f8fd  cmp     byte ptr [rax+0E0h], 0
0x18005f904  jz      short loc_18005F951
0x18005f906  lea     rcx, [rax+60h]
0x18005f90a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005f90f  mov     [rbp+4Fh+var_98], rax
0x18005f913  lea     rdx, [rbp+4Fh+var_88]
0x18005f917  cmp     byte ptr [rdi], 0
0x18005f91a  jnz     short loc_18005F93B
0x18005f91c  lea     r8, [r14+9Ch]
0x18005f923  mov     [rsp+0E0h+var_B8], rsi
0x18005f928  lea     rax, [rbp+4Fh+var_98]
0x18005f92c  mov     [rsp+0E0h+var_C0], rax
0x18005f931  mov     r9, rdi
0x18005f934  call    ?ChangeWriteCache@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBW4S2DCacheMode@@AEA_NAEBQEB_WAEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z; Wsp::Facade::StorageHealthFacade::ChangeWriteCache(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,S2DCacheMode const &,bool &,wchar_t const * const &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)
0x18005f939  jmp     short loc_18005F947
0x18005f93b  mov     r9, rsi
0x18005f93e  lea     r8, [rbp+4Fh+var_98]
0x18005f942  call    ?ClearReadOnlyFlag@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBQEB_WAEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z; Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,wchar_t const * const &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)
0x18005f947  mov     ebx, eax
0x18005f949  test    eax, eax
0x18005f94b  jnz     loc_18005F844
0x18005f951  lea     rcx, [rbp+4Fh+var_90]
0x18005f955  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>>,std::_Iterator_base0>::operator++(void)
0x18005f95a  mov     rax, [rbp+4Fh+var_90]
0x18005f95e  jmp     short loc_18005F8F7
0x18005f960  mov     rax, [r15]
0x18005f963  mov     rax, [rax]
0x18005f966  mov     [rbp+4Fh+var_90], rax
0x18005f96a  cmp     byte ptr [rax+19h], 0
0x18005f96e  jnz     loc_18005F844
0x18005f974  cmp     byte ptr [rax+0E0h], 0
0x18005f97b  jnz     short loc_18005F9C8
0x18005f97d  lea     rcx, [rax+60h]
0x18005f981  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005f986  mov     [rbp+4Fh+var_98], rax
0x18005f98a  lea     rdx, [rbp+4Fh+var_88]
0x18005f98e  cmp     byte ptr [rdi], 0
0x18005f991  jnz     short loc_18005F9B2
0x18005f993  lea     r8, [r14+9Ch]
0x18005f99a  mov     [rsp+0E0h+var_B8], rsi
0x18005f99f  lea     rax, [rbp+4Fh+var_98]
0x18005f9a3  mov     [rsp+0E0h+var_C0], rax
0x18005f9a8  mov     r9, rdi
0x18005f9ab  call    ?ChangeWriteCache@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBW4S2DCacheMode@@AEA_NAEBQEB_WAEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z; Wsp::Facade::StorageHealthFacade::ChangeWriteCache(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,S2DCacheMode const &,bool &,wchar_t const * const &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)
0x18005f9b0  jmp     short loc_18005F9BE
0x18005f9b2  mov     r9, rsi
0x18005f9b5  lea     r8, [rbp+4Fh+var_98]
0x18005f9b9  call    ?ClearReadOnlyFlag@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBQEB_WAEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z; Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,wchar_t const * const &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)
0x18005f9be  mov     ebx, eax
0x18005f9c0  test    eax, eax
0x18005f9c2  jnz     loc_18005F844
0x18005f9c8  lea     rcx, [rbp+4Fh+var_90]
0x18005f9cc  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>>,std::_Iterator_base0>::operator++(void)
0x18005f9d1  mov     rax, [rbp+4Fh+var_90]
0x18005f9d5  jmp     short loc_18005F96A
```
