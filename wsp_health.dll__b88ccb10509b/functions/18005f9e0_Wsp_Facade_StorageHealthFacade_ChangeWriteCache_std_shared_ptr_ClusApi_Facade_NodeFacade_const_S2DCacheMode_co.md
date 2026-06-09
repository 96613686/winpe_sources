# Wsp::Facade::StorageHealthFacade::ChangeWriteCache(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,S2DCacheMode const &,bool &,wchar_t const * const &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x18005f9e0`
- end: `0x18005fd48`
- name: `?ChangeWriteCache@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBW4S2DCacheMode@@AEA_NAEBQEB_WAEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z`
- size: `872`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: ``

## callers

- `0x18005f660`

## callees

- `0x1800010f4`
- `0x1800016b0`
- `0x180002ae0`
- `0x18000b8e4`
- `0x18000c9f0`
- `0x18000d618`
- `0x18000d6dc`
- `0x18000e044`
- `0x180013150`
- `0x18001465c`
- `0x180014954`
- `0x180034360`
- `0x18003e65c`
- `0x180057a0c`
- `0x1800595f4`
- `0x18005c9c8`
- `0x18005d4cc`
- `0x18005f9e0`
- `0x1800751e4`
- `0x180075210`
- `0x18008c010`

## string_xrefs

- `0x18005fa1d`: `Wsp::Facade::StorageHealthFacade::ChangeWriteCache`
- `0x18005fb84`: `Wsp::Facade::StorageHealthFacade::ChangeWriteCache`
- `0x18005fbc1`: `Wsp::Facade::StorageHealthFacade::ChangeWriteCache`
- `0x18005fc11`: `Wsp::Facade::StorageHealthFacade::ChangeWriteCache`
- `0x18005fc4e`: `Wsp::Facade::StorageHealthFacade::ChangeWriteCache`
- `0x18005fce3`: `Wsp::Facade::StorageHealthFacade::ChangeWriteCache`
- `0x18005fb44`: `Failed to Change SBL Cache`
- `0x18005faf1`: `storagewmi!Wsp::Facade::StorageHealthFacade::ChangeWriteCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Wsp::Facade::StorageHealthFacade::ChangeWriteCache(
        __int64 a1,
        __int64 a2,
        _DWORD *a3,
        _BYTE *a4,
        _QWORD *a5,
        __int64 a6)
{
  int v9; // eax
  std::_Ref_count_base *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // edi
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  struct cxl::TraceManager *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  Wsp::Facade::ResExtendedStatus *v23; // rbx
  __int64 v24; // rax
  __int64 *v26; // [rsp+28h] [rbp-A1h]
  __int64 v27; // [rsp+50h] [rbp-79h] BYREF
  const char *v28; // [rsp+58h] [rbp-71h] BYREF
  int v29; // [rsp+60h] [rbp-69h] BYREF
  Wsp::Facade::ResExtendedStatus *v30; // [rsp+68h] [rbp-61h] BYREF
  std::_Ref_count_base *v31; // [rsp+70h] [rbp-59h]
  __int128 v32; // [rsp+78h] [rbp-51h] BYREF
  __int64 v33; // [rsp+88h] [rbp-41h]
  _QWORD v34[2]; // [rsp+90h] [rbp-39h] BYREF
  _OWORD v35[2]; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v36; // [rsp+C0h] [rbp-9h]
  _BYTE v37[32]; // [rsp+C8h] [rbp-1h] BYREF

  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    LODWORD(v27) = 2049;
    v28 = "Wsp::Facade::StorageHealthFacade::ChangeWriteCache";
    v26 = &v27;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"Wsp::Facade::StorageHealthFacade::ChangeWriteCache",
      (__int64)&dword_18012A01C,
      (__int64)a3,
      (__int64)a4,
      &v28);
  }
  memset(v35, 0, sizeof(v35));
  v36 = 0;
  if ( *a5 )
  {
    std::wstring::wstring(v37, *a5);
    *(_OWORD *)((char *)v35 + 4) = *(_OWORD *)cxl::Guid::Guid(v34, v37);
    std::wstring::_Tidy_deallocate(v37);
    DWORD1(v35[1]) = 0;
  }
  else
  {
    *(_OWORD *)((char *)v35 + 4) = *(_OWORD *)cxl::Guid::EmptyGuid(v34);
    DWORD1(v35[1]) = 2;
  }
  if ( *a4 )
  {
    HIDWORD(v36) = 2;
    DWORD2(v35[1]) = *a3;
  }
  else
  {
    HIDWORD(v36) = 5;
    DWORD2(v35[1]) = 4;
  }
  LODWORD(v35[0]) = 1;
  LODWORD(v36) = 1;
  BYTE12(v35[1]) = 0;
  LODWORD(v26) = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, _OWORD *, __int64, _QWORD, __int64 *, _QWORD, __int64, const wchar_t *))(**(_QWORD **)(*(_QWORD *)a2 + 40LL) + 40LL))(
         *(_QWORD *)(*(_QWORD *)a2 + 40LL),
         71311802,
         v35,
         40,
         0,
         v26,
         0,
         *(_QWORD *)a2 + 40LL,
         L"storagewmi!Wsp::Facade::StorageHealthFacade::ChangeWriteCache");
  v13 = v9;
  if ( v9 < 0 )
  {
    LODWORD(v27) = v9;
    std::wstring::wstring(v37, L"Failed to Change SBL Cache");
    if ( (int)v27 >= 0 )
    {
      if ( (unsigned int)dword_18014B6A8 > 5 )
      {
        v34[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v37);
        LODWORD(v28) = v27;
        v29 = 2091;
        v30 = (Wsp::Facade::ResExtendedStatus *)"Wsp::Facade::StorageHealthFacade::ChangeWriteCache";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v20,
          (__int64)&word_180129EFE,
          v21,
          v22,
          &v30,
          (__int64)&v29,
          (__int64)&v28,
          v34);
      }
    }
    else
    {
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v30 = (Wsp::Facade::ResExtendedStatus *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v37);
        v29 = v27;
        LODWORD(v28) = 2091;
        v34[0] = "Wsp::Facade::StorageHealthFacade::ChangeWriteCache";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v14,
          (__int64)word_18012A04A,
          v15,
          v16,
          v34,
          (__int64)&v28,
          (__int64)&v29,
          &v30);
      }
      v17 = cxl::TraceManager::Instance();
      LODWORD(v28) = 2091;
      cxl::TextWriter::WriteLine<wchar_t,char [51],int,long,wchar_t [27]>(
        (struct cxl::TraceManager *)((char *)v17 + 40),
        v18,
        v19,
        (__int64)&v28,
        (__int64)&v27);
    }
    std::wstring::_Tidy_deallocate(v37);
    std::make_shared<Wsp::Facade::ResExtendedStatus,>(&v30);
    std::shared_ptr<Wsp::Facade::IExtendedStatus>::operator=<Wsp::Facade::ResExtendedStatus,0>(a6, &v30);
    v23 = v30;
    Wsp::Facade::ResExtendedStatus::SetMessageId(v30, 0x8065u);
    *((_WORD *)v23 + 76) = 1;
    if ( *a5 )
    {
      v32 = 0;
      v33 = 0;
      std::vector<std::wstring>::emplace_back<wchar_t * &>(&v32, a5);
      v24 = std::vector<std::wstring>::vector<std::wstring>(v37, &v32);
      Wsp::Facade::ResExtendedStatus::SetMessageArguments(v23, v24);
      std::vector<std::wstring>::_Tidy(&v32);
    }
    v10 = v31;
    if ( v31 )
      std::_Ref_count_base::_Decref(v31);
  }
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    LODWORD(v28) = 2106;
    v34[0] = "Wsp::Facade::StorageHealthFacade::ChangeWriteCache";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)v10,
      (__int64)byte_180129F41,
      v11,
      v12,
      v34);
  }
  return Wsp::MiSpaceAdapter::SmRCFromHResult(v13);
}

```

## disassembly

```asm
0x18005f9e0  mov     [rsp-8+arg_0], rbx
0x18005f9e5  push    rbp
0x18005f9e6  push    rsi
0x18005f9e7  push    rdi
0x18005f9e8  push    r14
0x18005f9ea  push    r15
0x18005f9ec  lea     rbp, [rsp-27h]
0x18005f9f1  sub     rsp, 0F0h
0x18005f9f8  mov     rax, cs:__security_cookie
0x18005f9ff  xor     rax, rsp
0x18005fa02  mov     [rbp+47h+var_28], rax
0x18005fa06  mov     rbx, r9
0x18005fa09  mov     rdi, r8
0x18005fa0c  mov     r14, rdx
0x18005fa0f  mov     rsi, [rbp+47h+arg_20]
0x18005fa13  mov     r15, [rbp+47h+arg_28]
0x18005fa17  mov     eax, cs:dword_18014B6A8
0x18005fa1d  lea     rcx, aWspFacadeStora_14; "Wsp::Facade::StorageHealthFacade::Chang"...
0x18005fa24  cmp     eax, 5
0x18005fa27  jbe     short loc_18005FA52
0x18005fa29  mov     dword ptr [rbp+47h+var_C0], 801h
0x18005fa30  mov     [rbp+47h+var_B8], rcx
0x18005fa34  lea     rax, [rbp+47h+var_C0]
0x18005fa38  mov     [rsp+110h+var_E8], rax
0x18005fa3d  lea     rax, [rbp+47h+var_B8]
0x18005fa41  mov     [rsp+110h+var_F0], rax
0x18005fa46  lea     rdx, dword_18012A01C
0x18005fa4d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005fa52  xorps   xmm0, xmm0
0x18005fa55  xor     eax, eax
0x18005fa57  movups  [rbp+47h+var_70], xmm0
0x18005fa5b  movups  [rbp+47h+var_60], xmm0
0x18005fa5f  mov     [rbp+47h+var_50], rax
0x18005fa63  mov     rdx, [rsi]
0x18005fa66  test    rdx, rdx
0x18005fa69  jz      short loc_18005FA9C
0x18005fa6b  lea     rcx, [rbp+47h+var_48]
0x18005fa6f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18005fa74  nop
0x18005fa75  lea     rdx, [rbp+47h+var_48]
0x18005fa79  lea     rcx, [rbp+47h+var_80]
0x18005fa7d  call    ??0Guid@cxl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Guid::Guid(std::wstring const &)
0x18005fa82  movups  xmm0, xmmword ptr [rax]
0x18005fa85  movdqu  [rbp+47h+var_70+4], xmm0
0x18005fa8a  lea     rcx, [rbp+47h+var_48]
0x18005fa8e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005fa93  mov     dword ptr [rbp+47h+var_60+4], 0
0x18005fa9a  jmp     short loc_18005FAB4
0x18005fa9c  lea     rcx, [rbp+47h+var_80]
0x18005faa0  call    ?EmptyGuid@Guid@cxl@@SA?AU12@XZ; cxl::Guid::EmptyGuid(void)
0x18005faa5  movups  xmm0, xmmword ptr [rax]
0x18005faa8  movdqu  [rbp+47h+var_70+4], xmm0
0x18005faad  mov     dword ptr [rbp+47h+var_60+4], 2
0x18005fab4  cmp     byte ptr [rbx], 0
0x18005fab7  jz      short loc_18005FAC7
0x18005fab9  mov     dword ptr [rbp+47h+var_50+4], 2
0x18005fac0  mov     eax, [rdi]
0x18005fac2  mov     dword ptr [rbp+47h+var_60+8], eax
0x18005fac5  jmp     short loc_18005FAD5
0x18005fac7  mov     dword ptr [rbp+47h+var_50+4], 5
0x18005face  mov     dword ptr [rbp+47h+var_60+8], 4
0x18005fad5  mov     eax, 1
0x18005fada  mov     dword ptr [rbp+47h+var_70], eax
0x18005fadd  mov     dword ptr [rbp+47h+var_50], eax
0x18005fae0  mov     byte ptr [rbp+47h+var_60+0Ch], 0
0x18005fae4  mov     rcx, [r14]
0x18005fae7  add     rcx, 28h ; '('
0x18005faeb  mov     r10, [rcx]
0x18005faee  mov     rax, [r10]
0x18005faf1  lea     rdx, aStoragewmiWspF_0; "storagewmi!Wsp::Facade::StorageHealthFa"...
0x18005faf8  mov     [rsp+110h+var_D0], rdx
0x18005fafd  mov     [rsp+110h+var_D8], rcx
0x18005fb02  mov     [rsp+110h+var_E0], 0
0x18005fb0b  mov     dword ptr [rsp+110h+var_E8], 0
0x18005fb13  mov     [rsp+110h+var_F0], 0
0x18005fb1c  mov     r9d, 28h ; '('
0x18005fb22  lea     r8, [rbp+47h+var_70]
0x18005fb26  mov     edx, 44021BAh
0x18005fb2b  mov     rcx, r10
0x18005fb2e  mov     rax, [rax+28h]
0x18005fb32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb37  mov     edi, eax
0x18005fb39  test    eax, eax
0x18005fb3b  jns     loc_18005FCE3
0x18005fb41  mov     dword ptr [rbp+47h+var_C0], eax
0x18005fb44  lea     rdx, aFailedToChange; "Failed to Change SBL Cache"
0x18005fb4b  lea     rcx, [rbp+47h+var_48]
0x18005fb4f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18005fb54  nop
0x18005fb55  cmp     dword ptr [rbp+47h+var_C0], 0
0x18005fb59  jge     loc_18005FBEC
0x18005fb5f  mov     ecx, cs:dword_18014B6A8
0x18005fb65  cmp     ecx, 2
0x18005fb68  jbe     short loc_18005FBC1
0x18005fb6a  lea     rcx, [rbp+47h+var_48]
0x18005fb6e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005fb73  mov     [rbp+47h+var_A8], rax
0x18005fb77  mov     eax, dword ptr [rbp+47h+var_C0]
0x18005fb7a  mov     [rbp+47h+var_B0], eax
0x18005fb7d  mov     dword ptr [rbp+47h+var_B8], 82Bh
0x18005fb84  lea     r14, aWspFacadeStora_14; "Wsp::Facade::StorageHealthFacade::Chang"...
0x18005fb8b  mov     [rbp+47h+var_80], r14
0x18005fb8f  lea     rax, [rbp+47h+var_A8]
0x18005fb93  mov     [rsp+110h+var_D8], rax
0x18005fb98  lea     rax, [rbp+47h+var_B0]
0x18005fb9c  mov     [rsp+110h+var_E0], rax
0x18005fba1  lea     rax, [rbp+47h+var_B8]
0x18005fba5  mov     [rsp+110h+var_E8], rax
0x18005fbaa  lea     rax, [rbp+47h+var_80]
0x18005fbae  mov     [rsp+110h+var_F0], rax
0x18005fbb3  lea     rdx, word_18012A04A
0x18005fbba  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x18005fbbf  jmp     short loc_18005FBC8
0x18005fbc1  lea     r14, aWspFacadeStora_14; "Wsp::Facade::StorageHealthFacade::Chang"...
0x18005fbc8  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18005fbcd  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x18005fbd1  mov     dword ptr [rbp+47h+var_B8], 82Bh
0x18005fbd8  lea     rax, [rbp+47h+var_C0]
0x18005fbdc  mov     [rsp+110h+var_F0], rax; __int64
0x18005fbe1  lea     r9, [rbp+47h+var_B8]
0x18005fbe5  call    ??$WriteLine@_W$$BY0DD@DHJ$$BY0BL@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DD@$$CBDAEBHAEBJAEAY0BL@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [51],int,long,wchar_t [27]>(wchar_t const *,char const (&)[51],int const &,long const &,wchar_t const (&)[27])
0x18005fbea  jmp     short loc_18005FC55
0x18005fbec  mov     eax, cs:dword_18014B6A8
0x18005fbf2  cmp     eax, 5
0x18005fbf5  jbe     short loc_18005FC4E
0x18005fbf7  lea     rcx, [rbp+47h+var_48]
0x18005fbfb  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005fc00  mov     [rbp+47h+var_80], rax
0x18005fc04  mov     eax, dword ptr [rbp+47h+var_C0]
0x18005fc07  mov     dword ptr [rbp+47h+var_B8], eax
0x18005fc0a  mov     [rbp+47h+var_B0], 82Bh
0x18005fc11  lea     r14, aWspFacadeStora_14; "Wsp::Facade::StorageHealthFacade::Chang"...
0x18005fc18  mov     [rbp+47h+var_A8], r14
0x18005fc1c  lea     rax, [rbp+47h+var_80]
0x18005fc20  mov     [rsp+110h+var_D8], rax
0x18005fc25  lea     rax, [rbp+47h+var_B8]
0x18005fc29  mov     [rsp+110h+var_E0], rax
0x18005fc2e  lea     rax, [rbp+47h+var_B0]
0x18005fc32  mov     [rsp+110h+var_E8], rax
0x18005fc37  lea     rax, [rbp+47h+var_A8]
0x18005fc3b  mov     [rsp+110h+var_F0], rax
0x18005fc40  lea     rdx, word_180129EFE
0x18005fc47  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x18005fc4c  jmp     short loc_18005FC55
0x18005fc4e  lea     r14, aWspFacadeStora_14; "Wsp::Facade::StorageHealthFacade::Chang"...
0x18005fc55  lea     rcx, [rbp+47h+var_48]
0x18005fc59  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005fc5e  lea     rcx, [rbp+47h+var_A8]
0x18005fc62  call    ??$make_shared@VResExtendedStatus@Facade@Wsp@@$$V@std@@YA?AV?$shared_ptr@VResExtendedStatus@Facade@Wsp@@@0@XZ; std::make_shared<Wsp::Facade::ResExtendedStatus,>(void)
0x18005fc67  nop
0x18005fc68  lea     rdx, [rbp+47h+var_A8]
0x18005fc6c  mov     rcx, r15
0x18005fc6f  call    ??$?4VResExtendedStatus@Facade@Wsp@@$0A@@?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@std@@QEAAAEAV01@AEBV?$shared_ptr@VResExtendedStatus@Facade@Wsp@@@1@@Z; std::shared_ptr<Wsp::Facade::IExtendedStatus>::operator=<Wsp::Facade::ResExtendedStatus,0>(std::shared_ptr<Wsp::Facade::ResExtendedStatus> const &)
0x18005fc74  mov     edx, 8065h; unsigned int
0x18005fc79  mov     rbx, [rbp+47h+var_A8]
0x18005fc7d  mov     rcx, rbx; this
0x18005fc80  call    ?SetMessageId@ResExtendedStatus@Facade@Wsp@@QEAAXK@Z; Wsp::Facade::ResExtendedStatus::SetMessageId(ulong)
0x18005fc85  mov     word ptr [rbx+98h], 1
0x18005fc8e  cmp     qword ptr [rsi], 0
0x18005fc92  jz      short loc_18005FCD3
0x18005fc94  xorps   xmm0, xmm0
0x18005fc97  movdqu  [rbp+47h+var_98], xmm0
0x18005fc9c  mov     [rbp+47h+var_88], 0
0x18005fca4  mov     rdx, rsi
0x18005fca7  lea     rcx, [rbp+47h+var_98]
0x18005fcab  call    ??$emplace_back@AEAPEA_W@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAPEA_W@Z; std::vector<std::wstring>::emplace_back<wchar_t * &>(wchar_t * &)
0x18005fcb0  lea     rdx, [rbp+47h+var_98]
0x18005fcb4  lea     rcx, [rbp+47h+var_48]
0x18005fcb8  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x18005fcbd  mov     rdx, rax
0x18005fcc0  mov     rcx, rbx
0x18005fcc3  call    ?SetMessageArguments@ResExtendedStatus@Facade@Wsp@@QEAAXV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z; Wsp::Facade::ResExtendedStatus::SetMessageArguments(std::vector<std::wstring>)
0x18005fcc8  nop
0x18005fcc9  lea     rcx, [rbp+47h+var_98]
0x18005fccd  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18005fcd2  nop
0x18005fcd3  mov     rcx, [rbp+47h+var_A0]; this
0x18005fcd7  test    rcx, rcx
0x18005fcda  jz      short loc_18005FCEA
0x18005fcdc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005fce1  jmp     short loc_18005FCEA
0x18005fce3  lea     r14, aWspFacadeStora_14; "Wsp::Facade::StorageHealthFacade::Chang"...
0x18005fcea  mov     eax, cs:dword_18014B6A8
0x18005fcf0  cmp     eax, 5
0x18005fcf3  jbe     short loc_18005FD1E
0x18005fcf5  mov     dword ptr [rbp+47h+var_B8], 83Ah
0x18005fcfc  mov     [rbp+47h+var_80], r14
0x18005fd00  lea     rax, [rbp+47h+var_B8]
0x18005fd04  mov     [rsp+110h+var_E8], rax
0x18005fd09  lea     rax, [rbp+47h+var_80]
0x18005fd0d  mov     [rsp+110h+var_F0], rax
0x18005fd12  lea     rdx, byte_180129F41
0x18005fd19  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005fd1e  mov     ecx, edi
0x18005fd20  call    ?SmRCFromHResult@MiSpaceAdapter@Wsp@@SA?AW4SM_RETURN_CODE@@J@Z; Wsp::MiSpaceAdapter::SmRCFromHResult(long)
0x18005fd25  mov     rcx, [rbp+47h+var_28]
0x18005fd29  xor     rcx, rsp; StackCookie
0x18005fd2c  call    __security_check_cookie
0x18005fd31  mov     rbx, [rsp+110h+arg_0]
0x18005fd39  add     rsp, 0F0h
0x18005fd40  pop     r15
0x18005fd42  pop     r14
0x18005fd44  pop     rdi
0x18005fd45  pop     rsi
0x18005fd46  pop     rbp
0x18005fd47  retn
```
