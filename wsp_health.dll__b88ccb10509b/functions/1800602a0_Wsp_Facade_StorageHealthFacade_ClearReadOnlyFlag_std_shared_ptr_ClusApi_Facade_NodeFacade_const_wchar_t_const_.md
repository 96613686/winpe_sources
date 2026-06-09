# Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,wchar_t const * const &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x1800602a0`
- end: `0x1800605b6`
- name: `?ClearReadOnlyFlag@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBQEB_WAEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z`
- size: `790`
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
- `0x180059c88`
- `0x18005c9c8`
- `0x18005d4cc`
- `0x1800602a0`
- `0x1800751e4`
- `0x180075210`
- `0x18008c010`

## string_xrefs

- `0x1800602d4`: `Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag`
- `0x1800603e4`: `Failed to change SBL cache`
- `0x180060393`: `storagewmi!Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  int v7; // eax
  std::_Ref_count_base *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // esi
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  struct cxl::TraceManager *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  Wsp::Facade::ResExtendedStatus *v19; // rbx
  __int64 v20; // rax
  __int64 *v22; // [rsp+28h] [rbp-A1h]
  __int64 v23; // [rsp+50h] [rbp-79h] BYREF
  const char *v24; // [rsp+58h] [rbp-71h] BYREF
  int v25; // [rsp+60h] [rbp-69h] BYREF
  Wsp::Facade::ResExtendedStatus *v26; // [rsp+68h] [rbp-61h] BYREF
  std::_Ref_count_base *v27; // [rsp+70h] [rbp-59h]
  __int128 v28; // [rsp+78h] [rbp-51h] BYREF
  __int64 v29; // [rsp+88h] [rbp-41h]
  _QWORD v30[2]; // [rsp+90h] [rbp-39h] BYREF
  _OWORD v31[2]; // [rsp+A0h] [rbp-29h] BYREF
  int v32; // [rsp+C0h] [rbp-9h]
  _BYTE v33[32]; // [rsp+C8h] [rbp-1h] BYREF

  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    LODWORD(v23) = 2116;
    v24 = "Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag";
    v22 = &v23;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (__int64)&word_180129F6E,
      (__int64)a3,
      a4,
      &v24);
  }
  memset(v31, 0, sizeof(v31));
  v32 = 0;
  if ( *a3 )
  {
    std::wstring::wstring(v33, *a3);
    *(_OWORD *)((char *)v31 + 4) = *(_OWORD *)cxl::Guid::Guid(v30, v33);
    std::wstring::_Tidy_deallocate(v33);
    DWORD1(v31[1]) = 0;
  }
  else
  {
    *(_OWORD *)((char *)v31 + 4) = *(_OWORD *)cxl::Guid::EmptyGuid(v30);
    DWORD1(v31[1]) = 2;
  }
  *((_QWORD *)&v31[1] + 1) = 0x100000003LL;
  v32 = 16;
  LODWORD(v31[0]) = 1;
  LODWORD(v22) = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, _OWORD *, __int64, _QWORD, __int64 *, _QWORD, __int64, const wchar_t *))(**(_QWORD **)(*(_QWORD *)a2 + 40LL) + 40LL))(
         *(_QWORD *)(*(_QWORD *)a2 + 40LL),
         71311798,
         v31,
         36,
         0,
         v22,
         0,
         *(_QWORD *)a2 + 40LL,
         L"storagewmi!Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag");
  v11 = v7;
  if ( v7 < 0 )
  {
    LODWORD(v23) = v7;
    std::wstring::wstring(v33, L"Failed to change SBL cache");
    if ( (int)v23 >= 0 )
    {
      if ( (unsigned int)dword_18014B6A8 > 5 )
      {
        v30[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v33);
        LODWORD(v24) = v23;
        v25 = 2149;
        v26 = (Wsp::Facade::ResExtendedStatus *)"Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v16,
          (__int64)&byte_180129E4F,
          v17,
          v18,
          &v26,
          (__int64)&v25,
          (__int64)&v24,
          v30);
      }
    }
    else
    {
      if ( (unsigned int)dword_18014B6A8 > 2 )
      {
        v26 = (Wsp::Facade::ResExtendedStatus *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v33);
        v25 = v23;
        LODWORD(v24) = 2149;
        v30[0] = "Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v12,
          (__int64)&dword_180129F9C,
          v13,
          v14,
          v30,
          (__int64)&v24,
          (__int64)&v25,
          &v26);
      }
      v15 = cxl::TraceManager::Instance();
      LODWORD(v24) = 2149;
      cxl::TextWriter::WriteLine<wchar_t,char [52],int,long,wchar_t [27]>(
        (struct cxl::TraceManager *)((char *)v15 + 40),
        (__int64)&v23);
    }
    std::wstring::_Tidy_deallocate(v33);
    std::make_shared<Wsp::Facade::ResExtendedStatus,>(&v26);
    std::shared_ptr<Wsp::Facade::IExtendedStatus>::operator=<Wsp::Facade::ResExtendedStatus,0>(a4, &v26);
    v19 = v26;
    Wsp::Facade::ResExtendedStatus::SetMessageId(v26, 0x8065u);
    *((_WORD *)v19 + 76) = 1;
    if ( *a3 )
    {
      v28 = 0;
      v29 = 0;
      std::vector<std::wstring>::emplace_back<wchar_t * &>(&v28, a3);
      v20 = std::vector<std::wstring>::vector<std::wstring>(v33, &v28);
      Wsp::Facade::ResExtendedStatus::SetMessageArguments(v19, v20);
      std::vector<std::wstring>::_Tidy(&v28);
    }
    v8 = v27;
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
  }
  if ( (unsigned int)dword_18014B6A8 > 5 )
  {
    LODWORD(v24) = 2164;
    v30[0] = "Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)v8,
      (__int64)word_180129E92,
      v9,
      v10,
      v30);
  }
  return Wsp::MiSpaceAdapter::SmRCFromHResult(v11);
}

```

## disassembly

```asm
0x1800602a0  push    rbp
0x1800602a2  push    rbx
0x1800602a3  push    rsi
0x1800602a4  push    rdi
0x1800602a5  push    r12
0x1800602a7  push    r13
0x1800602a9  push    r14
0x1800602ab  lea     rbp, [rsp-27h]
0x1800602b0  sub     rsp, 0F0h
0x1800602b7  mov     rax, cs:__security_cookie
0x1800602be  xor     rax, rsp
0x1800602c1  mov     [rbp+57h+var_38], rax
0x1800602c5  mov     r14, r9
0x1800602c8  mov     rdi, r8
0x1800602cb  mov     rbx, rdx
0x1800602ce  mov     eax, cs:dword_18014B6A8
0x1800602d4  lea     r12, aWspFacadeStora_2; "Wsp::Facade::StorageHealthFacade::Clear"...
0x1800602db  cmp     eax, 5
0x1800602de  jbe     short loc_180060309
0x1800602e0  mov     dword ptr [rbp+57h+var_D0], 844h
0x1800602e7  mov     [rbp+57h+var_C8], r12
0x1800602eb  lea     rax, [rbp+57h+var_D0]
0x1800602ef  mov     [rsp+120h+var_F8], rax
0x1800602f4  lea     rax, [rbp+57h+var_C8]
0x1800602f8  mov     [rsp+120h+var_100], rax
0x1800602fd  lea     rdx, word_180129F6E
0x180060304  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180060309  xorps   xmm0, xmm0
0x18006030c  xor     eax, eax
0x18006030e  movups  [rbp+57h+var_80], xmm0
0x180060312  movups  [rbp+57h+var_70], xmm0
0x180060316  mov     [rbp+57h+var_60], eax
0x180060319  mov     rdx, [rdi]
0x18006031c  test    rdx, rdx
0x18006031f  jz      short loc_180060352
0x180060321  lea     rcx, [rbp+57h+var_58]
0x180060325  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006032a  nop
0x18006032b  lea     rdx, [rbp+57h+var_58]
0x18006032f  lea     rcx, [rbp+57h+var_90]
0x180060333  call    ??0Guid@cxl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Guid::Guid(std::wstring const &)
0x180060338  movups  xmm0, xmmword ptr [rax]
0x18006033b  movdqu  [rbp+57h+var_80+4], xmm0
0x180060340  lea     rcx, [rbp+57h+var_58]
0x180060344  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180060349  mov     dword ptr [rbp+57h+var_70+4], 0
0x180060350  jmp     short loc_18006036A
0x180060352  lea     rcx, [rbp+57h+var_90]
0x180060356  call    ?EmptyGuid@Guid@cxl@@SA?AU12@XZ; cxl::Guid::EmptyGuid(void)
0x18006035b  movups  xmm0, xmmword ptr [rax]
0x18006035e  movdqu  [rbp+57h+var_80+4], xmm0
0x180060363  mov     dword ptr [rbp+57h+var_70+4], 2
0x18006036a  mov     dword ptr [rbp+57h+var_70+8], 3
0x180060371  mov     [rbp+57h+var_60], 10h
0x180060378  mov     r13d, 1
0x18006037e  mov     dword ptr [rbp+57h+var_80], r13d
0x180060382  mov     dword ptr [rbp+57h+var_70+0Ch], r13d
0x180060386  mov     rcx, [rbx]
0x180060389  add     rcx, 28h ; '('
0x18006038d  mov     r10, [rcx]
0x180060390  mov     rax, [r10]
0x180060393  lea     rdx, aStoragewmiWspF; "storagewmi!Wsp::Facade::StorageHealthFa"...
0x18006039a  mov     [rsp+120h+var_E0], rdx
0x18006039f  mov     [rsp+120h+var_E8], rcx
0x1800603a4  mov     [rsp+120h+var_F0], 0
0x1800603ad  mov     dword ptr [rsp+120h+var_F8], 0
0x1800603b5  mov     [rsp+120h+var_100], 0
0x1800603be  lea     r9d, [r13+23h]
0x1800603c2  lea     r8, [rbp+57h+var_80]
0x1800603c6  mov     edx, 44021B6h
0x1800603cb  mov     rcx, r10
0x1800603ce  mov     rax, [rax+28h]
0x1800603d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800603d7  mov     esi, eax
0x1800603d9  test    eax, eax
0x1800603db  jns     loc_18006055D
0x1800603e1  mov     dword ptr [rbp+57h+var_D0], eax
0x1800603e4  lea     rdx, aFailedToChange_0; "Failed to change SBL cache"
0x1800603eb  lea     rcx, [rbp+57h+var_58]
0x1800603ef  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800603f4  nop
0x1800603f5  cmp     dword ptr [rbp+57h+var_D0], 0
0x1800603f9  jge     short loc_180060478
0x1800603fb  mov     ecx, cs:dword_18014B6A8
0x180060401  cmp     ecx, 2
0x180060404  jbe     short loc_180060454
0x180060406  lea     rcx, [rbp+57h+var_58]
0x18006040a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006040f  mov     [rbp+57h+var_B8], rax
0x180060413  mov     eax, dword ptr [rbp+57h+var_D0]
0x180060416  mov     [rbp+57h+var_C0], eax
0x180060419  mov     dword ptr [rbp+57h+var_C8], 865h
0x180060420  mov     [rbp+57h+var_90], r12
0x180060424  lea     rax, [rbp+57h+var_B8]
0x180060428  mov     [rsp+120h+var_E8], rax
0x18006042d  lea     rax, [rbp+57h+var_C0]
0x180060431  mov     [rsp+120h+var_F0], rax
0x180060436  lea     rax, [rbp+57h+var_C8]
0x18006043a  mov     [rsp+120h+var_F8], rax
0x18006043f  lea     rax, [rbp+57h+var_90]
0x180060443  mov     [rsp+120h+var_100], rax
0x180060448  lea     rdx, dword_180129F9C
0x18006044f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180060454  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180060459  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x18006045d  mov     dword ptr [rbp+57h+var_C8], 865h
0x180060464  lea     rax, [rbp+57h+var_D0]
0x180060468  mov     [rsp+120h+var_100], rax; __int64
0x18006046d  lea     r9, [rbp+57h+var_C8]
0x180060471  call    ??$WriteLine@_W$$BY0DE@DHJ$$BY0BL@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DE@$$CBDAEBHAEBJAEAY0BL@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [52],int,long,wchar_t [27]>(wchar_t const *,char const (&)[52],int const &,long const &,wchar_t const (&)[27])
0x180060476  jmp     short loc_1800604D2
0x180060478  mov     eax, cs:dword_18014B6A8
0x18006047e  cmp     eax, 5
0x180060481  jbe     short loc_1800604D2
0x180060483  lea     rcx, [rbp+57h+var_58]
0x180060487  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006048c  mov     [rbp+57h+var_90], rax
0x180060490  mov     eax, dword ptr [rbp+57h+var_D0]
0x180060493  mov     dword ptr [rbp+57h+var_C8], eax
0x180060496  mov     [rbp+57h+var_C0], 865h
0x18006049d  mov     [rbp+57h+var_B8], r12
0x1800604a1  lea     rax, [rbp+57h+var_90]
0x1800604a5  mov     [rsp+120h+var_E8], rax
0x1800604aa  lea     rax, [rbp+57h+var_C8]
0x1800604ae  mov     [rsp+120h+var_F0], rax
0x1800604b3  lea     rax, [rbp+57h+var_C0]
0x1800604b7  mov     [rsp+120h+var_F8], rax
0x1800604bc  lea     rax, [rbp+57h+var_B8]
0x1800604c0  mov     [rsp+120h+var_100], rax
0x1800604c5  lea     rdx, byte_180129E4F
0x1800604cc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1800604d1  nop
0x1800604d2  lea     rcx, [rbp+57h+var_58]
0x1800604d6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800604db  lea     rcx, [rbp+57h+var_B8]
0x1800604df  call    ??$make_shared@VResExtendedStatus@Facade@Wsp@@$$V@std@@YA?AV?$shared_ptr@VResExtendedStatus@Facade@Wsp@@@0@XZ; std::make_shared<Wsp::Facade::ResExtendedStatus,>(void)
0x1800604e4  nop
0x1800604e5  lea     rdx, [rbp+57h+var_B8]
0x1800604e9  mov     rcx, r14
0x1800604ec  call    ??$?4VResExtendedStatus@Facade@Wsp@@$0A@@?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@std@@QEAAAEAV01@AEBV?$shared_ptr@VResExtendedStatus@Facade@Wsp@@@1@@Z; std::shared_ptr<Wsp::Facade::IExtendedStatus>::operator=<Wsp::Facade::ResExtendedStatus,0>(std::shared_ptr<Wsp::Facade::ResExtendedStatus> const &)
0x1800604f1  mov     edx, 8065h; unsigned int
0x1800604f6  mov     rbx, [rbp+57h+var_B8]
0x1800604fa  mov     rcx, rbx; this
0x1800604fd  call    ?SetMessageId@ResExtendedStatus@Facade@Wsp@@QEAAXK@Z; Wsp::Facade::ResExtendedStatus::SetMessageId(ulong)
0x180060502  mov     [rbx+98h], r13w
0x18006050a  cmp     qword ptr [rdi], 0
0x18006050e  jz      short loc_18006054F
0x180060510  xorps   xmm0, xmm0
0x180060513  movdqu  [rbp+57h+var_A8], xmm0
0x180060518  mov     [rbp+57h+var_98], 0
0x180060520  mov     rdx, rdi
0x180060523  lea     rcx, [rbp+57h+var_A8]
0x180060527  call    ??$emplace_back@AEAPEA_W@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAPEA_W@Z; std::vector<std::wstring>::emplace_back<wchar_t * &>(wchar_t * &)
0x18006052c  lea     rdx, [rbp+57h+var_A8]
0x180060530  lea     rcx, [rbp+57h+var_58]
0x180060534  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180060539  mov     rdx, rax
0x18006053c  mov     rcx, rbx
0x18006053f  call    ?SetMessageArguments@ResExtendedStatus@Facade@Wsp@@QEAAXV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z; Wsp::Facade::ResExtendedStatus::SetMessageArguments(std::vector<std::wstring>)
0x180060544  nop
0x180060545  lea     rcx, [rbp+57h+var_A8]
0x180060549  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18006054e  nop
0x18006054f  mov     rcx, [rbp+57h+var_B0]; this
0x180060553  test    rcx, rcx
0x180060556  jz      short loc_18006055D
0x180060558  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006055d  mov     eax, cs:dword_18014B6A8
0x180060563  cmp     eax, 5
0x180060566  jbe     short loc_180060591
0x180060568  mov     dword ptr [rbp+57h+var_C8], 874h
0x18006056f  mov     [rbp+57h+var_90], r12
0x180060573  lea     rax, [rbp+57h+var_C8]
0x180060577  mov     [rsp+120h+var_F8], rax
0x18006057c  lea     rax, [rbp+57h+var_90]
0x180060580  mov     [rsp+120h+var_100], rax
0x180060585  lea     rdx, word_180129E92
0x18006058c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180060591  mov     ecx, esi
0x180060593  call    ?SmRCFromHResult@MiSpaceAdapter@Wsp@@SA?AW4SM_RETURN_CODE@@J@Z; Wsp::MiSpaceAdapter::SmRCFromHResult(long)
0x180060598  mov     rcx, [rbp+57h+var_38]
0x18006059c  xor     rcx, rsp; StackCookie
0x18006059f  call    __security_check_cookie
0x1800605a4  add     rsp, 0F0h
0x1800605ab  pop     r14
0x1800605ad  pop     r13
0x1800605af  pop     r12
0x1800605b1  pop     rdi
0x1800605b2  pop     rsi
0x1800605b3  pop     rbx
0x1800605b4  pop     rbp
0x1800605b5  retn
```
