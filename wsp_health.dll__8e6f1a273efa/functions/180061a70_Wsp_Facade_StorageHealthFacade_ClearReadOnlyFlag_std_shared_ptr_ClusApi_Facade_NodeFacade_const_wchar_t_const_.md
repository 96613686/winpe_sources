# Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,wchar_t const * const &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x180061a70`
- end: `0x180061d87`
- name: `?ClearReadOnlyFlag@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBQEB_WAEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z`
- size: `791`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: ``

## callers

- `0x180060e30`

## callees

- `0x1800010f8`
- `0x1800016d0`
- `0x180002b50`
- `0x18000bc64`
- `0x18000cd9c`
- `0x18000da34`
- `0x18000daf8`
- `0x18000e4b8`
- `0x180013810`
- `0x180014e00`
- `0x1800150f8`
- `0x1800354a4`
- `0x18003fc90`
- `0x180059104`
- `0x18005b400`
- `0x18005e154`
- `0x18005ec5c`
- `0x180061a70`
- `0x180077038`
- `0x180077064`
- `0x18008e010`

## string_xrefs

- `0x180061aa4`: `Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag`
- `0x180061bb4`: `Failed to change SBL cache`
- `0x180061b63`: `storagewmi!Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag(int a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  int v7; // eax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  unsigned int v11; // esi
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  struct cxl::TraceManager *v15; // rax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  Wsp::Facade::ResExtendedStatus *v19; // rbx
  __int64 v20; // rax
  __int64 v22; // [rsp+50h] [rbp-79h] BYREF
  const char *v23; // [rsp+58h] [rbp-71h] BYREF
  int v24; // [rsp+60h] [rbp-69h] BYREF
  Wsp::Facade::ResExtendedStatus *v25; // [rsp+68h] [rbp-61h] BYREF
  std::_Ref_count_base *v26; // [rsp+70h] [rbp-59h]
  __int128 v27; // [rsp+78h] [rbp-51h] BYREF
  __int64 v28; // [rsp+88h] [rbp-41h]
  _QWORD v29[2]; // [rsp+90h] [rbp-39h] BYREF
  _OWORD v30[2]; // [rsp+A0h] [rbp-29h] BYREF
  int v31; // [rsp+C0h] [rbp-9h]
  _BYTE v32[32]; // [rsp+C8h] [rbp-1h] BYREF

  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    LODWORD(v22) = 2116;
    v23 = "Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned int)&word_18012BF76,
      (_DWORD)a3,
      a4,
      (__int64)&v23,
      (__int64)&v22);
  }
  memset(v30, 0, sizeof(v30));
  v31 = 0;
  if ( *a3 )
  {
    std::wstring::wstring(v32, *a3);
    *(_OWORD *)((char *)v30 + 4) = *(_OWORD *)cxl::Guid::Guid(v29, v32);
    std::wstring::_Tidy_deallocate(v32);
    DWORD1(v30[1]) = 0;
  }
  else
  {
    *(_OWORD *)((char *)v30 + 4) = *(_OWORD *)cxl::Guid::EmptyGuid(v29);
    DWORD1(v30[1]) = 2;
  }
  *((_QWORD *)&v30[1] + 1) = 0x100000003LL;
  v31 = 16;
  LODWORD(v30[0]) = 1;
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, _OWORD *, __int64, _QWORD, _DWORD, _QWORD, __int64, const wchar_t *))(**(_QWORD **)(*(_QWORD *)a2 + 40LL) + 40LL))(
         *(_QWORD *)(*(_QWORD *)a2 + 40LL),
         71311798,
         v30,
         36,
         0,
         0,
         0,
         *(_QWORD *)a2 + 40LL,
         L"storagewmi!Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag");
  v11 = v7;
  if ( v7 < 0 )
  {
    LODWORD(v22) = v7;
    std::wstring::wstring(v32, L"Failed to change SBL cache");
    if ( (int)v22 >= 0 )
    {
      if ( (unsigned int)dword_18014D6A8 > 5 )
      {
        v29[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v32);
        LODWORD(v23) = v22;
        v24 = 2149;
        v25 = (Wsp::Facade::ResExtendedStatus *)"Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v16,
          (unsigned int)&byte_18012BE57,
          v17,
          v18,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v23,
          (__int64)v29);
      }
    }
    else
    {
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v25 = (Wsp::Facade::ResExtendedStatus *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v32);
        v24 = v22;
        LODWORD(v23) = 2149;
        v29[0] = "Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v12,
          (unsigned int)&dword_18012BFA4,
          v13,
          v14,
          (__int64)v29,
          (__int64)&v23,
          (__int64)&v24,
          (__int64)&v25);
      }
      v15 = cxl::TraceManager::Instance();
      LODWORD(v23) = 2149;
      cxl::TextWriter::WriteLine<wchar_t,char [52],int,long,wchar_t [27]>(
        (struct cxl::TraceManager *)((char *)v15 + 40),
        (__int64)&v22);
    }
    std::wstring::_Tidy_deallocate(v32);
    std::make_shared<Wsp::Facade::ResExtendedStatus,>(&v25);
    std::shared_ptr<Wsp::Facade::IExtendedStatus>::operator=<Wsp::Facade::ResExtendedStatus,0>(a4, &v25);
    v19 = v25;
    Wsp::Facade::ResExtendedStatus::SetMessageId(v25, 0x8065u);
    *((_WORD *)v19 + 76) = 1;
    if ( *a3 )
    {
      v27 = 0;
      v28 = 0;
      std::vector<std::wstring>::emplace_back<wchar_t * &>(&v27, a3);
      v20 = std::vector<std::wstring>::vector<std::wstring>(v32, &v27);
      Wsp::Facade::ResExtendedStatus::SetMessageArguments(v19, v20);
      std::vector<std::wstring>::_Tidy(&v27);
    }
    v8 = (int)v26;
    if ( v26 )
      std::_Ref_count_base::_Decref(v26);
  }
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    LODWORD(v23) = 2164;
    v29[0] = "Wsp::Facade::StorageHealthFacade::ClearReadOnlyFlag";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v8,
      (unsigned int)word_18012BE9A,
      v9,
      v10,
      (__int64)v29,
      (__int64)&v23);
  }
  return Wsp::MiSpaceAdapter::SmRCFromHResult(v11);
}

```

## disassembly

```asm
0x180061a70  push    rbp
0x180061a72  push    rbx
0x180061a73  push    rsi
0x180061a74  push    rdi
0x180061a75  push    r12
0x180061a77  push    r13
0x180061a79  push    r14
0x180061a7b  lea     rbp, [rsp-27h]
0x180061a80  sub     rsp, 0F0h
0x180061a87  mov     rax, cs:__security_cookie
0x180061a8e  xor     rax, rsp
0x180061a91  mov     [rbp+57h+var_38], rax
0x180061a95  mov     r14, r9
0x180061a98  mov     rdi, r8
0x180061a9b  mov     rbx, rdx
0x180061a9e  mov     eax, cs:dword_18014D6A8
0x180061aa4  lea     r12, aWspFacadeStora_2; "Wsp::Facade::StorageHealthFacade::Clear"...
0x180061aab  cmp     eax, 5
0x180061aae  jbe     short loc_180061AD9
0x180061ab0  mov     dword ptr [rbp+57h+var_D0], 844h
0x180061ab7  mov     [rbp+57h+var_C8], r12
0x180061abb  lea     rax, [rbp+57h+var_D0]
0x180061abf  mov     [rsp+120h+var_F8], rax
0x180061ac4  lea     rax, [rbp+57h+var_C8]
0x180061ac8  mov     [rsp+120h+var_100], rax
0x180061acd  lea     rdx, word_18012BF76
0x180061ad4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180061ad9  xorps   xmm0, xmm0
0x180061adc  xor     eax, eax
0x180061ade  movups  [rbp+57h+var_80], xmm0
0x180061ae2  movups  [rbp+57h+var_70], xmm0
0x180061ae6  mov     [rbp+57h+var_60], eax
0x180061ae9  mov     rdx, [rdi]
0x180061aec  test    rdx, rdx
0x180061aef  jz      short loc_180061B22
0x180061af1  lea     rcx, [rbp+57h+var_58]
0x180061af5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180061afa  nop
0x180061afb  lea     rdx, [rbp+57h+var_58]
0x180061aff  lea     rcx, [rbp+57h+var_90]
0x180061b03  call    ??0Guid@cxl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Guid::Guid(std::wstring const &)
0x180061b08  movups  xmm0, xmmword ptr [rax]
0x180061b0b  movdqu  [rbp+57h+var_80+4], xmm0
0x180061b10  lea     rcx, [rbp+57h+var_58]
0x180061b14  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180061b19  mov     dword ptr [rbp+57h+var_70+4], 0
0x180061b20  jmp     short loc_180061B3A
0x180061b22  lea     rcx, [rbp+57h+var_90]
0x180061b26  call    ?EmptyGuid@Guid@cxl@@SA?AU12@XZ; cxl::Guid::EmptyGuid(void)
0x180061b2b  movups  xmm0, xmmword ptr [rax]
0x180061b2e  movdqu  [rbp+57h+var_80+4], xmm0
0x180061b33  mov     dword ptr [rbp+57h+var_70+4], 2
0x180061b3a  mov     dword ptr [rbp+57h+var_70+8], 3
0x180061b41  mov     [rbp+57h+var_60], 10h
0x180061b48  mov     r13d, 1
0x180061b4e  mov     dword ptr [rbp+57h+var_80], r13d
0x180061b52  mov     dword ptr [rbp+57h+var_70+0Ch], r13d
0x180061b56  mov     rcx, [rbx]
0x180061b59  add     rcx, 28h ; '('
0x180061b5d  mov     r10, [rcx]
0x180061b60  mov     rax, [r10]
0x180061b63  lea     rdx, aStoragewmiWspF; "storagewmi!Wsp::Facade::StorageHealthFa"...
0x180061b6a  mov     [rsp+120h+var_E0], rdx
0x180061b6f  mov     [rsp+120h+var_E8], rcx
0x180061b74  mov     [rsp+120h+var_F0], 0
0x180061b7d  mov     dword ptr [rsp+120h+var_F8], 0
0x180061b85  mov     [rsp+120h+var_100], 0
0x180061b8e  lea     r9d, [r13+23h]
0x180061b92  lea     r8, [rbp+57h+var_80]
0x180061b96  mov     edx, 44021B6h
0x180061b9b  mov     rcx, r10
0x180061b9e  mov     rax, [rax+28h]
0x180061ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061ba7  mov     esi, eax
0x180061ba9  test    eax, eax
0x180061bab  jns     loc_180061D2D
0x180061bb1  mov     dword ptr [rbp+57h+var_D0], eax
0x180061bb4  lea     rdx, aFailedToChange_0; "Failed to change SBL cache"
0x180061bbb  lea     rcx, [rbp+57h+var_58]
0x180061bbf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180061bc4  nop
0x180061bc5  cmp     dword ptr [rbp+57h+var_D0], 0
0x180061bc9  jge     short loc_180061C48
0x180061bcb  mov     ecx, cs:dword_18014D6A8
0x180061bd1  cmp     ecx, 2
0x180061bd4  jbe     short loc_180061C24
0x180061bd6  lea     rcx, [rbp+57h+var_58]
0x180061bda  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180061bdf  mov     [rbp+57h+var_B8], rax
0x180061be3  mov     eax, dword ptr [rbp+57h+var_D0]
0x180061be6  mov     [rbp+57h+var_C0], eax
0x180061be9  mov     dword ptr [rbp+57h+var_C8], 865h
0x180061bf0  mov     [rbp+57h+var_90], r12
0x180061bf4  lea     rax, [rbp+57h+var_B8]
0x180061bf8  mov     [rsp+120h+var_E8], rax
0x180061bfd  lea     rax, [rbp+57h+var_C0]
0x180061c01  mov     [rsp+120h+var_F0], rax
0x180061c06  lea     rax, [rbp+57h+var_C8]
0x180061c0a  mov     [rsp+120h+var_F8], rax
0x180061c0f  lea     rax, [rbp+57h+var_90]
0x180061c13  mov     [rsp+120h+var_100], rax
0x180061c18  lea     rdx, dword_18012BFA4
0x180061c1f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180061c24  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180061c29  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x180061c2d  mov     dword ptr [rbp+57h+var_C8], 865h
0x180061c34  lea     rax, [rbp+57h+var_D0]
0x180061c38  mov     [rsp+120h+var_100], rax; __int64
0x180061c3d  lea     r9, [rbp+57h+var_C8]
0x180061c41  call    ??$WriteLine@_W$$BY0DE@DHJ$$BY0BL@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DE@$$CBDAEBHAEBJAEAY0BL@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [52],int,long,wchar_t [27]>(wchar_t const *,char const (&)[52],int const &,long const &,wchar_t const (&)[27])
0x180061c46  jmp     short loc_180061CA2
0x180061c48  mov     eax, cs:dword_18014D6A8
0x180061c4e  cmp     eax, 5
0x180061c51  jbe     short loc_180061CA2
0x180061c53  lea     rcx, [rbp+57h+var_58]
0x180061c57  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180061c5c  mov     [rbp+57h+var_90], rax
0x180061c60  mov     eax, dword ptr [rbp+57h+var_D0]
0x180061c63  mov     dword ptr [rbp+57h+var_C8], eax
0x180061c66  mov     [rbp+57h+var_C0], 865h
0x180061c6d  mov     [rbp+57h+var_B8], r12
0x180061c71  lea     rax, [rbp+57h+var_90]
0x180061c75  mov     [rsp+120h+var_E8], rax
0x180061c7a  lea     rax, [rbp+57h+var_C8]
0x180061c7e  mov     [rsp+120h+var_F0], rax
0x180061c83  lea     rax, [rbp+57h+var_C0]
0x180061c87  mov     [rsp+120h+var_F8], rax
0x180061c8c  lea     rax, [rbp+57h+var_B8]
0x180061c90  mov     [rsp+120h+var_100], rax
0x180061c95  lea     rdx, byte_18012BE57
0x180061c9c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x180061ca1  nop
0x180061ca2  lea     rcx, [rbp+57h+var_58]
0x180061ca6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180061cab  lea     rcx, [rbp+57h+var_B8]
0x180061caf  call    ??$make_shared@VResExtendedStatus@Facade@Wsp@@$$V@std@@YA?AV?$shared_ptr@VResExtendedStatus@Facade@Wsp@@@0@XZ; std::make_shared<Wsp::Facade::ResExtendedStatus,>(void)
0x180061cb4  nop
0x180061cb5  lea     rdx, [rbp+57h+var_B8]
0x180061cb9  mov     rcx, r14
0x180061cbc  call    ??$?4VResExtendedStatus@Facade@Wsp@@$0A@@?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@std@@QEAAAEAV01@AEBV?$shared_ptr@VResExtendedStatus@Facade@Wsp@@@1@@Z; std::shared_ptr<Wsp::Facade::IExtendedStatus>::operator=<Wsp::Facade::ResExtendedStatus,0>(std::shared_ptr<Wsp::Facade::ResExtendedStatus> const &)
0x180061cc1  mov     edx, 8065h; unsigned int
0x180061cc6  mov     rbx, [rbp+57h+var_B8]
0x180061cca  mov     rcx, rbx; this
0x180061ccd  call    ?SetMessageId@ResExtendedStatus@Facade@Wsp@@QEAAXK@Z; Wsp::Facade::ResExtendedStatus::SetMessageId(ulong)
0x180061cd2  mov     [rbx+98h], r13w
0x180061cda  cmp     qword ptr [rdi], 0
0x180061cde  jz      short loc_180061D1F
0x180061ce0  xorps   xmm0, xmm0
0x180061ce3  movdqu  [rbp+57h+var_A8], xmm0
0x180061ce8  mov     [rbp+57h+var_98], 0
0x180061cf0  mov     rdx, rdi
0x180061cf3  lea     rcx, [rbp+57h+var_A8]
0x180061cf7  call    ??$emplace_back@AEAPEA_W@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAPEA_W@Z; std::vector<std::wstring>::emplace_back<wchar_t * &>(wchar_t * &)
0x180061cfc  lea     rdx, [rbp+57h+var_A8]
0x180061d00  lea     rcx, [rbp+57h+var_58]
0x180061d04  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180061d09  mov     rdx, rax
0x180061d0c  mov     rcx, rbx
0x180061d0f  call    ?SetMessageArguments@ResExtendedStatus@Facade@Wsp@@QEAAXV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z; Wsp::Facade::ResExtendedStatus::SetMessageArguments(std::vector<std::wstring>)
0x180061d14  nop
0x180061d15  lea     rcx, [rbp+57h+var_A8]
0x180061d19  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180061d1e  nop
0x180061d1f  mov     rcx, [rbp+57h+var_B0]; this
0x180061d23  test    rcx, rcx
0x180061d26  jz      short loc_180061D2D
0x180061d28  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180061d2d  mov     eax, cs:dword_18014D6A8
0x180061d33  cmp     eax, 5
0x180061d36  jbe     short loc_180061D61
0x180061d38  mov     dword ptr [rbp+57h+var_C8], 874h
0x180061d3f  mov     [rbp+57h+var_90], r12
0x180061d43  lea     rax, [rbp+57h+var_C8]
0x180061d47  mov     [rsp+120h+var_F8], rax
0x180061d4c  lea     rax, [rbp+57h+var_90]
0x180061d50  mov     [rsp+120h+var_100], rax
0x180061d55  lea     rdx, word_18012BE9A
0x180061d5c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180061d61  mov     ecx, esi
0x180061d63  call    ?SmRCFromHResult@MiSpaceAdapter@Wsp@@SA?AW4SM_RETURN_CODE@@J@Z; Wsp::MiSpaceAdapter::SmRCFromHResult(long)
0x180061d68  mov     rcx, [rbp+57h+var_38]
0x180061d6c  xor     rcx, rsp; StackCookie
0x180061d6f  call    __security_check_cookie
0x180061d74  add     rsp, 0F0h
0x180061d7b  pop     r14
0x180061d7d  pop     r13
0x180061d7f  pop     r12
0x180061d81  pop     rdi
0x180061d82  pop     rsi
0x180061d83  pop     rbx
0x180061d84  pop     rbp
0x180061d85  retn
```
