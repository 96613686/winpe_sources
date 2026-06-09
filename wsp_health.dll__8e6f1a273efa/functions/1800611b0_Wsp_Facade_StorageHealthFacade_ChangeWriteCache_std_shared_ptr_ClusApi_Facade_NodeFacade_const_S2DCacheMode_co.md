# Wsp::Facade::StorageHealthFacade::ChangeWriteCache(std::shared_ptr<ClusApi::Facade::NodeFacade> const &,S2DCacheMode const &,bool &,wchar_t const * const &,std::shared_ptr<Wsp::Facade::IExtendedStatus> &)

- ea: `0x1800611b0`
- end: `0x180061519`
- name: `?ChangeWriteCache@StorageHealthFacade@Facade@Wsp@@AEAA?AW4SM_RETURN_CODE@@AEBV?$shared_ptr@VNodeFacade@Facade@ClusApi@@@std@@AEBW4S2DCacheMode@@AEA_NAEBQEB_WAEAV?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@6@@Z`
- size: `873`
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
- `0x18005ad6c`
- `0x18005e154`
- `0x18005ec5c`
- `0x1800611b0`
- `0x180077038`
- `0x180077064`
- `0x18008e010`

## string_xrefs

- `0x1800611ed`: `Wsp::Facade::StorageHealthFacade::ChangeWriteCache`
- `0x180061354`: `Wsp::Facade::StorageHealthFacade::ChangeWriteCache`
- `0x180061391`: `Wsp::Facade::StorageHealthFacade::ChangeWriteCache`
- `0x1800613e1`: `Wsp::Facade::StorageHealthFacade::ChangeWriteCache`
- `0x18006141e`: `Wsp::Facade::StorageHealthFacade::ChangeWriteCache`
- `0x1800614b3`: `Wsp::Facade::StorageHealthFacade::ChangeWriteCache`
- `0x180061314`: `Failed to Change SBL Cache`
- `0x1800612c1`: `storagewmi!Wsp::Facade::StorageHealthFacade::ChangeWriteCache`

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
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  unsigned int v13; // edi
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  struct cxl::TraceManager *v17; // rax
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  Wsp::Facade::ResExtendedStatus *v21; // rbx
  __int64 v22; // rax
  __int64 v24; // [rsp+50h] [rbp-79h] BYREF
  const char *v25; // [rsp+58h] [rbp-71h] BYREF
  int v26; // [rsp+60h] [rbp-69h] BYREF
  Wsp::Facade::ResExtendedStatus *v27; // [rsp+68h] [rbp-61h] BYREF
  std::_Ref_count_base *v28; // [rsp+70h] [rbp-59h]
  __int128 v29; // [rsp+78h] [rbp-51h] BYREF
  __int64 v30; // [rsp+88h] [rbp-41h]
  _QWORD v31[2]; // [rsp+90h] [rbp-39h] BYREF
  _OWORD v32[2]; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v33; // [rsp+C0h] [rbp-9h]
  _BYTE v34[32]; // [rsp+C8h] [rbp-1h] BYREF

  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    LODWORD(v24) = 2049;
    v25 = "Wsp::Facade::StorageHealthFacade::ChangeWriteCache";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"Wsp::Facade::StorageHealthFacade::ChangeWriteCache",
      (unsigned int)&dword_18012C024,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)&v25,
      (__int64)&v24);
  }
  memset(v32, 0, sizeof(v32));
  v33 = 0;
  if ( *a5 )
  {
    std::wstring::wstring(v34, *a5);
    *(_OWORD *)((char *)v32 + 4) = *(_OWORD *)cxl::Guid::Guid(v31, v34);
    std::wstring::_Tidy_deallocate(v34);
    DWORD1(v32[1]) = 0;
  }
  else
  {
    *(_OWORD *)((char *)v32 + 4) = *(_OWORD *)cxl::Guid::EmptyGuid(v31);
    DWORD1(v32[1]) = 2;
  }
  if ( *a4 )
  {
    HIDWORD(v33) = 2;
    DWORD2(v32[1]) = *a3;
  }
  else
  {
    HIDWORD(v33) = 5;
    DWORD2(v32[1]) = 4;
  }
  LODWORD(v32[0]) = 1;
  LODWORD(v33) = 1;
  BYTE12(v32[1]) = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, _OWORD *, __int64, _QWORD, _DWORD, _QWORD, __int64, const wchar_t *))(**(_QWORD **)(*(_QWORD *)a2 + 40LL) + 40LL))(
         *(_QWORD *)(*(_QWORD *)a2 + 40LL),
         71311802,
         v32,
         40,
         0,
         0,
         0,
         *(_QWORD *)a2 + 40LL,
         L"storagewmi!Wsp::Facade::StorageHealthFacade::ChangeWriteCache");
  v13 = v9;
  if ( v9 < 0 )
  {
    LODWORD(v24) = v9;
    std::wstring::wstring(v34, L"Failed to Change SBL Cache");
    if ( (int)v24 >= 0 )
    {
      if ( (unsigned int)dword_18014D6A8 > 5 )
      {
        v31[0] = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v34);
        LODWORD(v25) = v24;
        v26 = 2091;
        v27 = (Wsp::Facade::ResExtendedStatus *)"Wsp::Facade::StorageHealthFacade::ChangeWriteCache";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v18,
          (unsigned int)&word_18012BF06,
          v19,
          v20,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&v25,
          (__int64)v31);
      }
    }
    else
    {
      if ( (unsigned int)dword_18014D6A8 > 2 )
      {
        v27 = (Wsp::Facade::ResExtendedStatus *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v34);
        v26 = v24;
        LODWORD(v25) = 2091;
        v31[0] = "Wsp::Facade::StorageHealthFacade::ChangeWriteCache";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          v14,
          (unsigned int)word_18012C052,
          v15,
          v16,
          (__int64)v31,
          (__int64)&v25,
          (__int64)&v26,
          (__int64)&v27);
      }
      v17 = cxl::TraceManager::Instance();
      LODWORD(v25) = 2091;
      cxl::TextWriter::WriteLine<wchar_t,char [51],int,long,wchar_t [27]>(
        (struct cxl::TraceManager *)((char *)v17 + 40),
        (__int64)&v24);
    }
    std::wstring::_Tidy_deallocate(v34);
    std::make_shared<Wsp::Facade::ResExtendedStatus,>(&v27);
    std::shared_ptr<Wsp::Facade::IExtendedStatus>::operator=<Wsp::Facade::ResExtendedStatus,0>(a6, &v27);
    v21 = v27;
    Wsp::Facade::ResExtendedStatus::SetMessageId(v27, 0x8065u);
    *((_WORD *)v21 + 76) = 1;
    if ( *a5 )
    {
      v29 = 0;
      v30 = 0;
      std::vector<std::wstring>::emplace_back<wchar_t * &>(&v29, a5);
      v22 = std::vector<std::wstring>::vector<std::wstring>(v34, &v29);
      Wsp::Facade::ResExtendedStatus::SetMessageArguments(v21, v22);
      std::vector<std::wstring>::_Tidy(&v29);
    }
    v10 = (int)v28;
    if ( v28 )
      std::_Ref_count_base::_Decref(v28);
  }
  if ( (unsigned int)dword_18014D6A8 > 5 )
  {
    LODWORD(v25) = 2106;
    v31[0] = "Wsp::Facade::StorageHealthFacade::ChangeWriteCache";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v10,
      (unsigned int)byte_18012BF49,
      v11,
      v12,
      (__int64)v31,
      (__int64)&v25);
  }
  return Wsp::MiSpaceAdapter::SmRCFromHResult(v13);
}

```

## disassembly

```asm
0x1800611b0  mov     [rsp-8+arg_0], rbx
0x1800611b5  push    rbp
0x1800611b6  push    rsi
0x1800611b7  push    rdi
0x1800611b8  push    r14
0x1800611ba  push    r15
0x1800611bc  lea     rbp, [rsp-27h]
0x1800611c1  sub     rsp, 0F0h
0x1800611c8  mov     rax, cs:__security_cookie
0x1800611cf  xor     rax, rsp
0x1800611d2  mov     [rbp+47h+var_28], rax
0x1800611d6  mov     rbx, r9
0x1800611d9  mov     rdi, r8
0x1800611dc  mov     r14, rdx
0x1800611df  mov     rsi, [rbp+47h+arg_20]
0x1800611e3  mov     r15, [rbp+47h+arg_28]
0x1800611e7  mov     eax, cs:dword_18014D6A8
0x1800611ed  lea     rcx, aWspFacadeStora_14; "Wsp::Facade::StorageHealthFacade::Chang"...
0x1800611f4  cmp     eax, 5
0x1800611f7  jbe     short loc_180061222
0x1800611f9  mov     dword ptr [rbp+47h+var_C0], 801h
0x180061200  mov     [rbp+47h+var_B8], rcx
0x180061204  lea     rax, [rbp+47h+var_C0]
0x180061208  mov     [rsp+110h+var_E8], rax
0x18006120d  lea     rax, [rbp+47h+var_B8]
0x180061211  mov     [rsp+110h+var_F0], rax
0x180061216  lea     rdx, dword_18012C024
0x18006121d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180061222  xorps   xmm0, xmm0
0x180061225  xor     eax, eax
0x180061227  movups  [rbp+47h+var_70], xmm0
0x18006122b  movups  [rbp+47h+var_60], xmm0
0x18006122f  mov     [rbp+47h+var_50], rax
0x180061233  mov     rdx, [rsi]
0x180061236  test    rdx, rdx
0x180061239  jz      short loc_18006126C
0x18006123b  lea     rcx, [rbp+47h+var_48]
0x18006123f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180061244  nop
0x180061245  lea     rdx, [rbp+47h+var_48]
0x180061249  lea     rcx, [rbp+47h+var_80]
0x18006124d  call    ??0Guid@cxl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Guid::Guid(std::wstring const &)
0x180061252  movups  xmm0, xmmword ptr [rax]
0x180061255  movdqu  [rbp+47h+var_70+4], xmm0
0x18006125a  lea     rcx, [rbp+47h+var_48]
0x18006125e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180061263  mov     dword ptr [rbp+47h+var_60+4], 0
0x18006126a  jmp     short loc_180061284
0x18006126c  lea     rcx, [rbp+47h+var_80]
0x180061270  call    ?EmptyGuid@Guid@cxl@@SA?AU12@XZ; cxl::Guid::EmptyGuid(void)
0x180061275  movups  xmm0, xmmword ptr [rax]
0x180061278  movdqu  [rbp+47h+var_70+4], xmm0
0x18006127d  mov     dword ptr [rbp+47h+var_60+4], 2
0x180061284  cmp     byte ptr [rbx], 0
0x180061287  jz      short loc_180061297
0x180061289  mov     dword ptr [rbp+47h+var_50+4], 2
0x180061290  mov     eax, [rdi]
0x180061292  mov     dword ptr [rbp+47h+var_60+8], eax
0x180061295  jmp     short loc_1800612A5
0x180061297  mov     dword ptr [rbp+47h+var_50+4], 5
0x18006129e  mov     dword ptr [rbp+47h+var_60+8], 4
0x1800612a5  mov     eax, 1
0x1800612aa  mov     dword ptr [rbp+47h+var_70], eax
0x1800612ad  mov     dword ptr [rbp+47h+var_50], eax
0x1800612b0  mov     byte ptr [rbp+47h+var_60+0Ch], 0
0x1800612b4  mov     rcx, [r14]
0x1800612b7  add     rcx, 28h ; '('
0x1800612bb  mov     r10, [rcx]
0x1800612be  mov     rax, [r10]
0x1800612c1  lea     rdx, aStoragewmiWspF_0; "storagewmi!Wsp::Facade::StorageHealthFa"...
0x1800612c8  mov     [rsp+110h+var_D0], rdx
0x1800612cd  mov     [rsp+110h+var_D8], rcx
0x1800612d2  mov     [rsp+110h+var_E0], 0
0x1800612db  mov     dword ptr [rsp+110h+var_E8], 0
0x1800612e3  mov     [rsp+110h+var_F0], 0
0x1800612ec  mov     r9d, 28h ; '('
0x1800612f2  lea     r8, [rbp+47h+var_70]
0x1800612f6  mov     edx, 44021BAh
0x1800612fb  mov     rcx, r10
0x1800612fe  mov     rax, [rax+28h]
0x180061302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061307  mov     edi, eax
0x180061309  test    eax, eax
0x18006130b  jns     loc_1800614B3
0x180061311  mov     dword ptr [rbp+47h+var_C0], eax
0x180061314  lea     rdx, aFailedToChange; "Failed to Change SBL Cache"
0x18006131b  lea     rcx, [rbp+47h+var_48]
0x18006131f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180061324  nop
0x180061325  cmp     dword ptr [rbp+47h+var_C0], 0
0x180061329  jge     loc_1800613BC
0x18006132f  mov     ecx, cs:dword_18014D6A8
0x180061335  cmp     ecx, 2
0x180061338  jbe     short loc_180061391
0x18006133a  lea     rcx, [rbp+47h+var_48]
0x18006133e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180061343  mov     [rbp+47h+var_A8], rax
0x180061347  mov     eax, dword ptr [rbp+47h+var_C0]
0x18006134a  mov     [rbp+47h+var_B0], eax
0x18006134d  mov     dword ptr [rbp+47h+var_B8], 82Bh
0x180061354  lea     r14, aWspFacadeStora_14; "Wsp::Facade::StorageHealthFacade::Chang"...
0x18006135b  mov     [rbp+47h+var_80], r14
0x18006135f  lea     rax, [rbp+47h+var_A8]
0x180061363  mov     [rsp+110h+var_D8], rax
0x180061368  lea     rax, [rbp+47h+var_B0]
0x18006136c  mov     [rsp+110h+var_E0], rax
0x180061371  lea     rax, [rbp+47h+var_B8]
0x180061375  mov     [rsp+110h+var_E8], rax
0x18006137a  lea     rax, [rbp+47h+var_80]
0x18006137e  mov     [rsp+110h+var_F0], rax
0x180061383  lea     rdx, word_18012C052
0x18006138a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x18006138f  jmp     short loc_180061398
0x180061391  lea     r14, aWspFacadeStora_14; "Wsp::Facade::StorageHealthFacade::Chang"...
0x180061398  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18006139d  lea     rcx, [rax+28h]; struct cxl::TextWriter *
0x1800613a1  mov     dword ptr [rbp+47h+var_B8], 82Bh
0x1800613a8  lea     rax, [rbp+47h+var_C0]
0x1800613ac  mov     [rsp+110h+var_F0], rax; __int64
0x1800613b1  lea     r9, [rbp+47h+var_B8]
0x1800613b5  call    ??$WriteLine@_W$$BY0DD@DHJ$$BY0BL@_W@TextWriter@cxl@@QEAAXPEB_WAEAY0DD@$$CBDAEBHAEBJAEAY0BL@$$CB_W@Z; cxl::TextWriter::WriteLine<wchar_t,char [51],int,long,wchar_t [27]>(wchar_t const *,char const (&)[51],int const &,long const &,wchar_t const (&)[27])
0x1800613ba  jmp     short loc_180061425
0x1800613bc  mov     eax, cs:dword_18014D6A8
0x1800613c2  cmp     eax, 5
0x1800613c5  jbe     short loc_18006141E
0x1800613c7  lea     rcx, [rbp+47h+var_48]
0x1800613cb  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800613d0  mov     [rbp+47h+var_80], rax
0x1800613d4  mov     eax, dword ptr [rbp+47h+var_C0]
0x1800613d7  mov     dword ptr [rbp+47h+var_B8], eax
0x1800613da  mov     [rbp+47h+var_B0], 82Bh
0x1800613e1  lea     r14, aWspFacadeStora_14; "Wsp::Facade::StorageHealthFacade::Chang"...
0x1800613e8  mov     [rbp+47h+var_A8], r14
0x1800613ec  lea     rax, [rbp+47h+var_80]
0x1800613f0  mov     [rsp+110h+var_D8], rax
0x1800613f5  lea     rax, [rbp+47h+var_B8]
0x1800613f9  mov     [rsp+110h+var_E0], rax
0x1800613fe  lea     rax, [rbp+47h+var_B0]
0x180061402  mov     [rsp+110h+var_E8], rax
0x180061407  lea     rax, [rbp+47h+var_A8]
0x18006140b  mov     [rsp+110h+var_F0], rax
0x180061410  lea     rdx, word_18012BF06
0x180061417  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x18006141c  jmp     short loc_180061425
0x18006141e  lea     r14, aWspFacadeStora_14; "Wsp::Facade::StorageHealthFacade::Chang"...
0x180061425  lea     rcx, [rbp+47h+var_48]
0x180061429  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006142e  lea     rcx, [rbp+47h+var_A8]
0x180061432  call    ??$make_shared@VResExtendedStatus@Facade@Wsp@@$$V@std@@YA?AV?$shared_ptr@VResExtendedStatus@Facade@Wsp@@@0@XZ; std::make_shared<Wsp::Facade::ResExtendedStatus,>(void)
0x180061437  nop
0x180061438  lea     rdx, [rbp+47h+var_A8]
0x18006143c  mov     rcx, r15
0x18006143f  call    ??$?4VResExtendedStatus@Facade@Wsp@@$0A@@?$shared_ptr@UIExtendedStatus@Facade@Wsp@@@std@@QEAAAEAV01@AEBV?$shared_ptr@VResExtendedStatus@Facade@Wsp@@@1@@Z; std::shared_ptr<Wsp::Facade::IExtendedStatus>::operator=<Wsp::Facade::ResExtendedStatus,0>(std::shared_ptr<Wsp::Facade::ResExtendedStatus> const &)
0x180061444  mov     edx, 8065h; unsigned int
0x180061449  mov     rbx, [rbp+47h+var_A8]
0x18006144d  mov     rcx, rbx; this
0x180061450  call    ?SetMessageId@ResExtendedStatus@Facade@Wsp@@QEAAXK@Z; Wsp::Facade::ResExtendedStatus::SetMessageId(ulong)
0x180061455  mov     word ptr [rbx+98h], 1
0x18006145e  cmp     qword ptr [rsi], 0
0x180061462  jz      short loc_1800614A3
0x180061464  xorps   xmm0, xmm0
0x180061467  movdqu  [rbp+47h+var_98], xmm0
0x18006146c  mov     [rbp+47h+var_88], 0
0x180061474  mov     rdx, rsi
0x180061477  lea     rcx, [rbp+47h+var_98]
0x18006147b  call    ??$emplace_back@AEAPEA_W@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAPEA_W@Z; std::vector<std::wstring>::emplace_back<wchar_t * &>(wchar_t * &)
0x180061480  lea     rdx, [rbp+47h+var_98]
0x180061484  lea     rcx, [rbp+47h+var_48]
0x180061488  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x18006148d  mov     rdx, rax
0x180061490  mov     rcx, rbx
0x180061493  call    ?SetMessageArguments@ResExtendedStatus@Facade@Wsp@@QEAAXV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z; Wsp::Facade::ResExtendedStatus::SetMessageArguments(std::vector<std::wstring>)
0x180061498  nop
0x180061499  lea     rcx, [rbp+47h+var_98]
0x18006149d  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800614a2  nop
0x1800614a3  mov     rcx, [rbp+47h+var_A0]; this
0x1800614a7  test    rcx, rcx
0x1800614aa  jz      short loc_1800614BA
0x1800614ac  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800614b1  jmp     short loc_1800614BA
0x1800614b3  lea     r14, aWspFacadeStora_14; "Wsp::Facade::StorageHealthFacade::Chang"...
0x1800614ba  mov     eax, cs:dword_18014D6A8
0x1800614c0  cmp     eax, 5
0x1800614c3  jbe     short loc_1800614EE
0x1800614c5  mov     dword ptr [rbp+47h+var_B8], 83Ah
0x1800614cc  mov     [rbp+47h+var_80], r14
0x1800614d0  lea     rax, [rbp+47h+var_B8]
0x1800614d4  mov     [rsp+110h+var_E8], rax
0x1800614d9  lea     rax, [rbp+47h+var_80]
0x1800614dd  mov     [rsp+110h+var_F0], rax
0x1800614e2  lea     rdx, byte_18012BF49
0x1800614e9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800614ee  mov     ecx, edi
0x1800614f0  call    ?SmRCFromHResult@MiSpaceAdapter@Wsp@@SA?AW4SM_RETURN_CODE@@J@Z; Wsp::MiSpaceAdapter::SmRCFromHResult(long)
0x1800614f5  mov     rcx, [rbp+47h+var_28]
0x1800614f9  xor     rcx, rsp; StackCookie
0x1800614fc  call    __security_check_cookie
0x180061501  mov     rbx, [rsp+110h+arg_0]
0x180061509  add     rsp, 0F0h
0x180061510  pop     r15
0x180061512  pop     r14
0x180061514  pop     rdi
0x180061515  pop     rsi
0x180061516  pop     rbp
0x180061517  retn
```
