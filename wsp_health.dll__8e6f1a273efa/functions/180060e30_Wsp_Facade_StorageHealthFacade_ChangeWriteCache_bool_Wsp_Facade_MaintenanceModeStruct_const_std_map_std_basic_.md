# Wsp::Facade::StorageHealthFacade::ChangeWriteCache(bool &,Wsp::Facade::MaintenanceModeStruct const &,std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,Wsp::Facade::MaintenanceDisk,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,Wsp::Facade::MaintenanceDisk>>> &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x180060e30`
- end: `0x1800611a9`
- name: `?ChangeWriteCache@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEA_NAEBUMaintenanceModeStruct@23@AEAV?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@2@@std@@AEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@7@@Z`
- size: `889`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: ``

## callers

- `0x180062798`
- `0x180064604`

## callees

- `0x1800016d0`
- `0x180002b50`
- `0x18000bb84`
- `0x18000bc64`
- `0x18000cd9c`
- `0x18000da34`
- `0x18000daf8`
- `0x18000e4b8`
- `0x180018af0`
- `0x18005aca4`
- `0x18005ad08`
- `0x180060414`
- `0x180060e30`
- `0x1800611b0`
- `0x180061a70`
- `0x180082960`

## string_xrefs

- `0x180060ec8`: `Wsp::Facade::StorageHealthFacade::ChangeWriteCache`
- `0x180060eac`: `Failed to open the target node to change the S2D write cache`
- `0x180060f71`: `Failed to open the local node to change the S2D write cache`

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
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  struct cxl::TraceManager *v13; // rax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  struct cxl::TraceManager *v17; // rax
  __int64 v19; // rcx
  unsigned int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rcx
  unsigned int v23; // eax
  __int64 v24; // rax
  __int64 v25; // rcx
  unsigned int v26; // eax
  int v27; // [rsp+40h] [rbp-51h] BYREF
  const char *v28; // [rsp+48h] [rbp-49h] BYREF
  __int64 i; // [rsp+50h] [rbp-41h] BYREF
  std::_Ref_count_base *v30[2]; // [rsp+58h] [rbp-39h] BYREF
  const char *v31; // [rsp+68h] [rbp-29h] BYREF
  __int64 v32; // [rsp+70h] [rbp-21h] BYREF
  std::_Ref_count_base *v33; // [rsp+78h] [rbp-19h]
  _BYTE v34[32]; // [rsp+90h] [rbp-1h] BYREF

  v8 = 0;
  *(_OWORD *)v30 = 0;
  Node = ClusApi::Facade::ClusterFacade::GetNode(*((_QWORD *)a3 + 20), &v32, a3 + 6);
  std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(v30, Node);
  if ( v33 )
    std::_Ref_count_base::_Decref(v33);
  if ( !v30[0] )
  {
    std::wstring::wstring(&v32, L"Failed to open the target node to change the S2D write cache");
    v8 = 59000;
    if ( (unsigned int)dword_18014D6A8 > 2 )
    {
      v31 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v32);
      v27 = 59000;
      LODWORD(i) = 1956;
      v28 = "Wsp::Facade::StorageHealthFacade::ChangeWriteCache";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v10,
        (unsigned int)qword_18012C0E0,
        v11,
        v12,
        (__int64)&v28,
        (__int64)&i,
        (__int64)&v27,
        (__int64)&v31);
    }
    v13 = cxl::TraceManager::Instance();
    LODWORD(i) = 59000;
    v27 = 1956;
    cxl::TextWriter::WriteLine<wchar_t,char [51],int,int,wchar_t [61]>(
      (struct cxl::TraceManager *)((char *)v13 + 40),
      (__int64)&i);
    std::wstring::_Tidy_deallocate(&v32);
    ClusApi::Facade::ClusterFacade::GetNode(*((_QWORD *)a3 + 20), &v32, cxl::EmptyLiteral);
    if ( !v32 )
    {
      std::wstring::wstring(v34, L"Failed to open the local node to change the S2D write cache");
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v28 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v34);
        LODWORD(i) = 59000;
        v27 = 1963;
        v31 = "Wsp::Facade::StorageHealthFacade::ChangeWriteCache";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v14,
          (unsigned int)byte_18012BFE5,
          v15,
          v16,
          (__int64)&v31,
          (__int64)&v27,
          (__int64)&i,
          (__int64)&v28);
      }
      v17 = cxl::TraceManager::Instance();
      LODWORD(i) = 59000;
      v27 = 1963;
      cxl::TextWriter::WriteLine<wchar_t,char [51],int,int,wchar_t [60]>(
        (struct cxl::TraceManager *)((char *)v17 + 40),
        (__int64)&i);
      std::wstring::_Tidy_deallocate(v34);
      if ( v33 )
        std::_Ref_count_base::_Decref(v33);
      goto LABEL_11;
    }
    std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(v30, &v32);
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
  }
  v19 = *a3;
  if ( (((_DWORD)v19 - 5) & 0xFFFFFFFB) != 0 )
  {
    if ( (_DWORD)v19 == 12 )
    {
      v28 = 0;
      if ( *a2 )
        v20 = Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag(12, (__int64)v30, &v28, a5);
      else
        v20 = Wsp::Facade::StorageHealthFacade::ChangeWriteCache(v19, (__int64)v30, a3 + 39, a2, &v28, a5);
      v8 = v20;
    }
  }
  else
  {
    v21 = **a4;
    i = v21;
    while ( !*(_BYTE *)(v21 + 25) )
    {
      if ( *(_BYTE *)(v21 + 224) )
      {
        v28 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v21 + 96);
        v23 = *a2
            ? Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag(v22, (__int64)v30, &v28, a5)
            : Wsp::Facade::StorageHealthFacade::ChangeWriteCache(v22, (__int64)v30, a3 + 39, a2, &v28, a5);
        v8 = v23;
        if ( v23 )
          goto LABEL_11;
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>>,std::_Iterator_base0>::operator++(&i);
      v21 = i;
    }
    v24 = **a4;
    for ( i = v24; !*(_BYTE *)(v24 + 25); v24 = i )
    {
      if ( !*(_BYTE *)(v24 + 224) )
      {
        v28 = (const char *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v24 + 96);
        v26 = *a2
            ? Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag(v25, (__int64)v30, &v28, a5)
            : Wsp::Facade::StorageHealthFacade::ChangeWriteCache(v25, (__int64)v30, a3 + 39, a2, &v28, a5);
        v8 = v26;
        if ( v26 )
          break;
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>>,std::_Iterator_base0>::operator++(&i);
    }
  }
LABEL_11:
  if ( v30[1] )
    std::_Ref_count_base::_Decref(v30[1]);
  return v8;
}

```

## disassembly

```asm
0x180060e30  mov     [rsp-8+arg_0], rbx
0x180060e35  mov     [rsp-8+arg_8], rsi
0x180060e3a  push    rbp
0x180060e3b  push    rdi
0x180060e3c  push    r13
0x180060e3e  push    r14
0x180060e40  push    r15
0x180060e42  lea     rbp, [rsp-2Fh]
0x180060e47  sub     rsp, 0C0h
0x180060e4e  mov     rax, cs:__security_cookie
0x180060e55  xor     rax, rsp
0x180060e58  mov     [rbp+4Fh+var_30], rax
0x180060e5c  mov     r15, r9
0x180060e5f  mov     r14, r8
0x180060e62  mov     rdi, rdx
0x180060e65  mov     rsi, [rbp+4Fh+arg_20]
0x180060e69  xor     ebx, ebx
0x180060e6b  xorps   xmm0, xmm0
0x180060e6e  movdqu  xmmword ptr [rbp+4Fh+var_88], xmm0
0x180060e73  add     r8, 18h
0x180060e77  lea     rdx, [rbp+4Fh+var_70]
0x180060e7b  mov     rcx, [r14+0A0h]
0x180060e82  call    ?GetNode@ClusterFacade@Facade@ClusApi@@QEAA?AV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; ClusApi::Facade::ClusterFacade::GetNode(std::wstring const &)
0x180060e87  mov     rdx, rax
0x180060e8a  lea     rcx, [rbp+4Fh+var_88]
0x180060e8e  call    ??4?$shared_ptr@$$CBVSPACES_VirtualDisk@mismpstorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<mismpstorage::SPACES_VirtualDisk const>::operator=(std::shared_ptr<mismpstorage::SPACES_VirtualDisk const> &&)
0x180060e93  mov     rcx, [rbp+4Fh+var_68]; this
0x180060e97  test    rcx, rcx
0x180060e9a  jz      short loc_180060EA1
0x180060e9c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180060ea1  cmp     [rbp+4Fh+var_88], 0
0x180060ea6  jnz     loc_180061069
0x180060eac  lea     rdx, aFailedToOpenTh_2; "Failed to open the target node to chang"...
0x180060eb3  lea     rcx, [rbp+4Fh+var_70]
0x180060eb7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180060ebc  nop
0x180060ebd  mov     eax, cs:dword_18014D6A8
0x180060ec3  mov     ebx, 0E678h
0x180060ec8  lea     r13, aWspFacadeStora_14; "Wsp::Facade::StorageHealthFacade::Chang"...
0x180060ecf  cmp     eax, 2
0x180060ed2  jbe     short loc_180060F1F
0x180060ed4  lea     rcx, [rbp+4Fh+var_70]
0x180060ed8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180060edd  mov     [rbp+4Fh+var_78], rax
0x180060ee1  mov     [rbp+4Fh+var_A0], ebx
0x180060ee4  mov     dword ptr [rbp+4Fh+var_90], 7A4h
0x180060eeb  mov     [rbp+4Fh+var_98], r13
0x180060eef  lea     rax, [rbp+4Fh+var_78]
0x180060ef3  mov     [rsp+0E0h+var_A8], rax
0x180060ef8  lea     rax, [rbp+4Fh+var_A0]
0x180060efc  mov     [rsp+0E0h+var_B0], rax
0x180060f01  lea     rax, [rbp+4Fh+var_90]
0x180060f05  mov     [rsp+0E0h+var_B8], rax
0x180060f0a  lea     rax, [rbp+4Fh+var_98]
0x180060f0e  mov     [rsp+0E0h+var_C0], rax
0x180060f13  lea     rdx, qword_18012C0E0
0x180060f1a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180060f1f  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180060f24  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180060f28  mov     dword ptr [rbp+4Fh+var_90], ebx
0x180060f2b  mov     [rbp+4Fh+var_A0], 7A4h
0x180060f32  lea     rax, [rbp+4Fh+var_90]
0x180060f36  mov     [rsp+0E0h+var_C0], rax; __int64
0x180060f3b  lea     r9, [rbp+4Fh+var_A0]
0x180060f3f  call    ??$WriteLine@_W$$BY0DD@DHH$$BY0DN@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DD@$$CBDAEBH2AEAY0DN@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [51],int,int,wchar_t [61]>(wchar_t const *,char const (&)[51],int const &,int const &,wchar_t const (&)[61])
0x180060f44  nop
0x180060f45  lea     rcx, [rbp+4Fh+var_70]
0x180060f49  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180060f4e  lea     r8, ?EmptyLiteral@cxl@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const cxl::EmptyLiteral
0x180060f55  lea     rdx, [rbp+4Fh+var_70]
0x180060f59  mov     rcx, [r14+0A0h]
0x180060f60  call    ?GetNode@ClusterFacade@Facade@ClusApi@@QEAA?AV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; ClusApi::Facade::ClusterFacade::GetNode(std::wstring const &)
0x180060f65  nop
0x180060f66  cmp     [rbp+4Fh+var_70], 0
0x180060f6b  jnz     loc_18006104D
0x180060f71  lea     rdx, aFailedToOpenTh_1; "Failed to open the local node to change"...
0x180060f78  lea     rcx, [rbp+4Fh+var_50]
0x180060f7c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180060f81  nop
0x180060f82  mov     eax, cs:dword_18014D6A8
0x180060f88  mov     edi, 7ABh
0x180060f8d  cmp     eax, 2
0x180060f90  jbe     short loc_180060FD9
0x180060f92  lea     rcx, [rbp+4Fh+var_50]
0x180060f96  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180060f9b  mov     [rbp+4Fh+var_98], rax
0x180060f9f  mov     dword ptr [rbp+4Fh+var_90], ebx
0x180060fa2  mov     [rbp+4Fh+var_A0], edi
0x180060fa5  mov     [rbp+4Fh+var_78], r13
0x180060fa9  lea     rax, [rbp+4Fh+var_98]
0x180060fad  mov     [rsp+0E0h+var_A8], rax
0x180060fb2  lea     rax, [rbp+4Fh+var_90]
0x180060fb6  mov     [rsp+0E0h+var_B0], rax
0x180060fbb  lea     rax, [rbp+4Fh+var_A0]
0x180060fbf  mov     [rsp+0E0h+var_B8], rax
0x180060fc4  lea     rax, [rbp+4Fh+var_78]
0x180060fc8  mov     [rsp+0E0h+var_C0], rax
0x180060fcd  lea     rdx, byte_18012BFE5
0x180060fd4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180060fd9  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180060fde  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180060fe2  mov     dword ptr [rbp+4Fh+var_90], ebx
0x180060fe5  mov     [rbp+4Fh+var_A0], edi
0x180060fe8  lea     rax, [rbp+4Fh+var_90]
0x180060fec  mov     [rsp+0E0h+var_C0], rax; __int64
0x180060ff1  lea     r9, [rbp+4Fh+var_A0]
0x180060ff5  call    ??$WriteLine@_W$$BY0DD@DHH$$BY0DM@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DD@$$CBDAEBH2AEAY0DM@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [51],int,int,wchar_t [60]>(wchar_t const *,char const (&)[51],int const &,int const &,wchar_t const (&)[60])
0x180060ffa  nop
0x180060ffb  lea     rcx, [rbp+4Fh+var_50]
0x180060fff  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180061004  nop
0x180061005  mov     rcx, [rbp+4Fh+var_68]; this
0x180061009  test    rcx, rcx
0x18006100c  jz      short loc_180061014
0x18006100e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180061013  nop
0x180061014  mov     rcx, [rbp+4Fh+var_88+8]; this
0x180061018  test    rcx, rcx
0x18006101b  jz      short loc_180061022
0x18006101d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180061022  mov     eax, ebx
0x180061024  mov     rcx, [rbp+4Fh+var_30]
0x180061028  xor     rcx, rsp; StackCookie
0x18006102b  call    __security_check_cookie
0x180061030  lea     r11, [rsp+0E0h+var_20]
0x180061038  mov     rbx, [r11+30h]
0x18006103c  mov     rsi, [r11+38h]
0x180061040  mov     rsp, r11
0x180061043  pop     r15
0x180061045  pop     r14
0x180061047  pop     r13
0x180061049  pop     rdi
0x18006104a  pop     rbp
0x18006104b  retn
0x18006104d  lea     rdx, [rbp+4Fh+var_70]
0x180061051  lea     rcx, [rbp+4Fh+var_88]
0x180061055  call    ??4?$shared_ptr@VCacheObject@DataStore@ClusWmi@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ClusWmi::DataStore::CacheObject>::operator=(std::shared_ptr<ClusWmi::DataStore::CacheObject> const &)
0x18006105a  nop
0x18006105b  mov     rcx, [rbp+4Fh+var_68]; this
0x18006105f  test    rcx, rcx
0x180061062  jz      short loc_180061069
0x180061064  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180061069  mov     ecx, [r14]
0x18006106c  lea     eax, [rcx-5]
0x18006106f  test    eax, 0FFFFFFFBh
0x180061074  jz      short loc_1800610BE
0x180061076  cmp     ecx, 0Ch
0x180061079  jnz     short loc_180061014
0x18006107b  mov     [rbp+4Fh+var_98], 0
0x180061083  lea     rdx, [rbp+4Fh+var_88]
0x180061087  cmp     byte ptr [rdi], 0
0x18006108a  jnz     short loc_1800610B0
0x18006108c  lea     r8, [r14+9Ch]
0x180061093  mov     [rsp+0E0h+var_B8], rsi
0x180061098  lea     rax, [rbp+4Fh+var_98]
0x18006109c  mov     [rsp+0E0h+var_C0], rax
0x1800610a1  mov     r9, rdi
0x1800610a4  call    ?ChangeWriteCache@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBW4S2DCacheMode@@AEA_NAEBQEB_WAEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z; Wsp::Facade::StorageHealthFacade::ChangeWriteCache(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,S2DCacheMode const &,bool &,wchar_t const * const &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)
0x1800610a9  mov     ebx, eax
0x1800610ab  jmp     loc_180061014
0x1800610b0  mov     r9, rsi
0x1800610b3  lea     r8, [rbp+4Fh+var_98]
0x1800610b7  call    ?ClearReadOnlyFlag@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBQEB_WAEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z; Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,wchar_t const * const &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)
0x1800610bc  jmp     short loc_1800610A9
0x1800610be  mov     rax, [r15]
0x1800610c1  mov     rax, [rax]
0x1800610c4  mov     [rbp+4Fh+var_90], rax
0x1800610c8  cmp     byte ptr [rax+19h], 0
0x1800610cc  jnz     short loc_180061131
0x1800610ce  cmp     byte ptr [rax+0E0h], 0
0x1800610d5  jz      short loc_180061122
0x1800610d7  lea     rcx, [rax+60h]
0x1800610db  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800610e0  mov     [rbp+4Fh+var_98], rax
0x1800610e4  lea     rdx, [rbp+4Fh+var_88]
0x1800610e8  cmp     byte ptr [rdi], 0
0x1800610eb  jnz     short loc_18006110C
0x1800610ed  lea     r8, [r14+9Ch]
0x1800610f4  mov     [rsp+0E0h+var_B8], rsi
0x1800610f9  lea     rax, [rbp+4Fh+var_98]
0x1800610fd  mov     [rsp+0E0h+var_C0], rax
0x180061102  mov     r9, rdi
0x180061105  call    ?ChangeWriteCache@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBW4S2DCacheMode@@AEA_NAEBQEB_WAEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z; Wsp::Facade::StorageHealthFacade::ChangeWriteCache(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,S2DCacheMode const &,bool &,wchar_t const * const &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)
0x18006110a  jmp     short loc_180061118
0x18006110c  mov     r9, rsi
0x18006110f  lea     r8, [rbp+4Fh+var_98]
0x180061113  call    ?ClearReadOnlyFlag@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBQEB_WAEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z; Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,wchar_t const * const &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)
0x180061118  mov     ebx, eax
0x18006111a  test    eax, eax
0x18006111c  jnz     loc_180061014
0x180061122  lea     rcx, [rbp+4Fh+var_90]
0x180061126  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>>,std::_Iterator_base0>::operator++(void)
0x18006112b  mov     rax, [rbp+4Fh+var_90]
0x18006112f  jmp     short loc_1800610C8
0x180061131  mov     rax, [r15]
0x180061134  mov     rax, [rax]
0x180061137  mov     [rbp+4Fh+var_90], rax
0x18006113b  cmp     byte ptr [rax+19h], 0
0x18006113f  jnz     loc_180061014
0x180061145  cmp     byte ptr [rax+0E0h], 0
0x18006114c  jnz     short loc_180061199
0x18006114e  lea     rcx, [rax+60h]
0x180061152  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180061157  mov     [rbp+4Fh+var_98], rax
0x18006115b  lea     rdx, [rbp+4Fh+var_88]
0x18006115f  cmp     byte ptr [rdi], 0
0x180061162  jnz     short loc_180061183
0x180061164  lea     r8, [r14+9Ch]
0x18006116b  mov     [rsp+0E0h+var_B8], rsi
0x180061170  lea     rax, [rbp+4Fh+var_98]
0x180061174  mov     [rsp+0E0h+var_C0], rax
0x180061179  mov     r9, rdi
0x18006117c  call    ?ChangeWriteCache@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBW4S2DCacheMode@@AEA_NAEBQEB_WAEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z; Wsp::Facade::StorageHealthFacade::ChangeWriteCache(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,S2DCacheMode const &,bool &,wchar_t const * const &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)
0x180061181  jmp     short loc_18006118F
0x180061183  mov     r9, rsi
0x180061186  lea     r8, [rbp+4Fh+var_98]
0x18006118a  call    ?ClearReadOnlyFlag@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBQEB_WAEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z; Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,wchar_t const * const &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)
0x18006118f  mov     ebx, eax
0x180061191  test    eax, eax
0x180061193  jnz     loc_180061014
0x180061199  lea     rcx, [rbp+4Fh+var_90]
0x18006119d  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UMaintenanceDisk@Facade@Wsp@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Wsp::Facade::MaintenanceDisk>>>,std::_Iterator_base0>::operator++(void)
0x1800611a2  mov     rax, [rbp+4Fh+var_90]
0x1800611a6  jmp     short loc_18006113B
```
