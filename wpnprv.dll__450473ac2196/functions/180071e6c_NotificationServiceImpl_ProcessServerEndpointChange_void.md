# NotificationServiceImpl::ProcessServerEndpointChange(void)

- ea: `0x180071e6c`
- end: `0x1800720f2`
- name: `?ProcessServerEndpointChange@NotificationServiceImpl@@AEAAXXZ`
- size: `646`
- prototype: `void __fastcall(NotificationServiceImpl *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180070300`

## callees

- `0x180001afc`
- `0x1800054d8`
- `0x180007440`
- `0x18000ba54`
- `0x18000fe0c`
- `0x180010650`
- `0x180010698`
- `0x180013294`
- `0x180013308`
- `0x18006eb14`
- `0x180071e6c`
- `0x180084774`
- `0x1800848e4`
- `0x1800849bc`
- `0x180096010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180071f9c`
- `ntdll!RtlPublishWnfStateData` at `0x180071f9c`

## string_xrefs

- `0x180072089`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18007209d`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800720b4`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800720cb`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800720df`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
void __fastcall NotificationServiceImpl::ProcessServerEndpointChange(NotificationServiceImpl *this)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v3)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // eax
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  char IsPPEEndpoint; // bl
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // eax
  int v16; // ebx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  const char *v24; // r9
  int v25; // [rsp+20h] [rbp-B8h]
  __int64 v26; // [rsp+40h] [rbp-98h] BYREF
  __int64 v27; // [rsp+48h] [rbp-90h] BYREF
  __int64 v28; // [rsp+50h] [rbp-88h] BYREF
  int v29; // [rsp+58h] [rbp-80h] BYREF
  __int64 v30; // [rsp+60h] [rbp-78h] BYREF
  _BYTE v31[32]; // [rsp+68h] [rbp-70h] BYREF
  _BYTE v32[32]; // [rsp+88h] [rbp-50h] BYREF
  _BYTE v33[32]; // [rsp+A8h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  try
  {
    GetPreviousEndpointFromRegistry(v33);
    v27 = 0;
    v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 14);
    v3 = **v2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27, v4, v5, v6);
    v7 = v3(v2, &GUID_4deb8736_5bdc_4e26_9595_d7003b0cd740, &v27);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD6B,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v7,
        v25);
    v26 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 184LL))(v27, &v26);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD6D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v8,
        v25);
    if ( !v26 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD6E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)0x8000FFFFLL,
        v25);
    v9 = -1;
    do
      ++v9;
    while ( *(_BYTE *)(v26 + v9) );
    if ( !v9 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD6F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)0x8000FFFFLL,
        v25);
    v10 = std::string::string(v32, v26);
    IsPPEEndpoint = NotificationServiceImpl::IsPPEEndpoint(v11, v10);
    v13 = std::string::string(v31, v33);
    if ( (unsigned __int8)NotificationServiceImpl::IsPPEEndpoint(v14, v13) == IsPPEEndpoint )
    {
      SetEndpointChangedStatusInRegistry(0);
      v16 = 1;
    }
    else
    {
      SetEndpointChangedStatusInRegistry(1);
      v15 = RtlPublishWnfStateData(WNF_WPN_CHANNELS_REVOKED, 0, 0, 0) | 0x10000000;
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD74,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
          (const char *)(unsigned int)v15,
          0);
      v16 = 0;
    }
    v17 = std::string::string(v31, v26);
    SetPreviousEndpointInRegistry(v17);
    if ( (unsigned int)dword_1800AF0C0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800AF0C0, 0x200000000000LL) )
    {
      v29 = v16;
      v30 = v26;
      v28 = std::_String_val<std::_Simple_types<char>>::_Myptr(v33);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v21,
        (unsigned int)&unk_1800A2CC0,
        v22,
        v23,
        (__int64)&v28,
        (__int64)&v30,
        (__int64)&v29);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27, v18, v19, v20);
    std::string::_Tidy_deallocate(v33);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xD84,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
      v24);
  }
}

```

## disassembly

```asm
0x180071e6c  mov     r11, rsp
0x180071e6f  mov     [r11+10h], rbx
0x180071e73  push    rdi
0x180071e74  sub     rsp, 0D0h
0x180071e7b  mov     rax, cs:__security_cookie
0x180071e82  xor     rax, rsp
0x180071e85  mov     [rsp+0D8h+var_10], rax
0x180071e8d  mov     rdi, rcx
0x180071e90  lea     rcx, [r11-30h]
0x180071e94  call    ?GetPreviousEndpointFromRegistry@@YA?BV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; GetPreviousEndpointFromRegistry(char const *)
0x180071e99  nop
0x180071e9a  mov     [rsp+0D8h+var_90], 0
0x180071ea3  mov     rdi, [rdi+70h]
0x180071ea7  mov     rax, [rdi]
0x180071eaa  mov     rbx, [rax]
0x180071ead  lea     rcx, [rsp+0D8h+var_90]
0x180071eb2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180071eb7  lea     r8, [rsp+0D8h+var_90]
0x180071ebc  lea     rdx, _GUID_4deb8736_5bdc_4e26_9595_d7003b0cd740
0x180071ec3  mov     rcx, rdi
0x180071ec6  mov     rax, rbx
0x180071ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ece  nop
0x180071ecf  mov     rcx, [rsp+0D8h]; this
0x180071ed7  test    eax, eax
0x180071ed9  js      loc_180072086
0x180071edf  mov     [rsp+0D8h+var_98], 0
0x180071ee8  mov     rcx, [rsp+0D8h+var_90]
0x180071eed  mov     rax, [rcx]
0x180071ef0  lea     rdx, [rsp+0D8h+var_98]
0x180071ef5  mov     rax, [rax+0B8h]
0x180071efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f01  mov     rcx, [rsp+0D8h]; this
0x180071f09  test    eax, eax
0x180071f0b  js      loc_18007209A
0x180071f11  mov     rcx, [rsp+0D8h]; this
0x180071f19  mov     rdx, [rsp+0D8h+var_98]
0x180071f1e  test    rdx, rdx
0x180071f21  jz      loc_1800720AE
0x180071f27  or      rax, 0FFFFFFFFFFFFFFFFh
0x180071f2b  inc     rax
0x180071f2e  cmp     byte ptr [rdx+rax], 0
0x180071f32  jnz     short loc_180071F2B
0x180071f34  mov     rcx, [rsp+0D8h]; this
0x180071f3c  test    rax, rax
0x180071f3f  jz      loc_1800720C5
0x180071f45  lea     rcx, [rsp+0D8h+var_50]
0x180071f4d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180071f52  mov     rdx, rax
0x180071f55  call    ?IsPPEEndpoint@NotificationServiceImpl@@AEAA_NV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; NotificationServiceImpl::IsPPEEndpoint(std::string)
0x180071f5a  mov     bl, al
0x180071f5c  lea     rdx, [rsp+0D8h+var_30]
0x180071f64  lea     rcx, [rsp+0D8h+var_70]
0x180071f69  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180071f6e  mov     rdx, rax
0x180071f71  call    ?IsPPEEndpoint@NotificationServiceImpl@@AEAA_NV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; NotificationServiceImpl::IsPPEEndpoint(std::string)
0x180071f76  cmp     al, bl
0x180071f78  jz      short loc_180071FB9
0x180071f7a  mov     ecx, 1; bool
0x180071f7f  call    ?SetEndpointChangedStatusInRegistry@@YAX_N@Z; SetEndpointChangedStatusInRegistry(bool)
0x180071f84  mov     qword ptr [rsp+0D8h+var_B8], 0; int
0x180071f8d  xor     r9d, r9d
0x180071f90  xor     r8d, r8d
0x180071f93  xor     edx, edx
0x180071f95  mov     rcx, cs:WNF_WPN_CHANNELS_REVOKED
0x180071f9c  call    cs:__imp_RtlPublishWnfStateData
0x180071fa2  or      eax, 10000000h
0x180071fa7  mov     rcx, [rsp+0D8h]; this
0x180071faf  jl      loc_1800720DC
0x180071fb5  xor     ebx, ebx
0x180071fb7  jmp     short loc_180071FC5
0x180071fb9  xor     ecx, ecx; bool
0x180071fbb  call    ?SetEndpointChangedStatusInRegistry@@YAX_N@Z; SetEndpointChangedStatusInRegistry(bool)
0x180071fc0  mov     ebx, 1
0x180071fc5  mov     rdx, [rsp+0D8h+var_98]
0x180071fca  lea     rcx, [rsp+0D8h+var_70]
0x180071fcf  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180071fd4  mov     rcx, rax
0x180071fd7  call    ?SetPreviousEndpointInRegistry@@YAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; SetPreviousEndpointInRegistry(std::string)
0x180071fdc  mov     eax, cs:dword_1800AF0C0
0x180071fe2  cmp     eax, 5
0x180071fe5  jbe     short loc_18007204C
0x180071fe7  mov     rdx, 200000000000h
0x180071ff1  lea     rcx, dword_1800AF0C0
0x180071ff8  call    _tlgKeywordOn
0x180071ffd  test    al, al
0x180071fff  jz      short loc_18007204C
0x180072001  mov     [rsp+0D8h+var_80], ebx
0x180072005  mov     rax, [rsp+0D8h+var_98]
0x18007200a  mov     [rsp+0D8h+var_78], rax
0x18007200f  lea     rcx, [rsp+0D8h+var_30]
0x180072017  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18007201c  mov     [rsp+0D8h+var_88], rax
0x180072021  lea     rax, [rsp+0D8h+var_80]
0x180072026  mov     [rsp+0D8h+var_A8], rax
0x18007202b  lea     rax, [rsp+0D8h+var_78]
0x180072030  mov     [rsp+0D8h+var_B0], rax
0x180072035  lea     rax, [rsp+0D8h+var_88]
0x18007203a  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18007203f  lea     rdx, unk_1800A2CC0
0x180072046  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007204b  nop
0x18007204c  lea     rcx, [rsp+0D8h+var_90]
0x180072051  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180072056  nop
0x180072057  lea     rcx, [rsp+0D8h+var_30]
0x18007205f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180072064  nop
0x180072065  mov     rcx, [rsp+0D8h+var_10]
0x18007206d  xor     rcx, rsp; StackCookie
0x180072070  call    __security_check_cookie
0x180072075  mov     rbx, [rsp+0D8h+arg_8]
0x18007207d  add     rsp, 0D0h
0x180072084  pop     rdi
0x180072085  retn
0x180072086  mov     r9d, eax; char *
0x180072089  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180072090  mov     edx, 0D6Bh; void *
0x180072095  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007209a  mov     r9d, eax; char *
0x18007209d  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800720a4  mov     edx, 0D6Dh; void *
0x1800720a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800720ae  mov     r9d, 8000FFFFh; char *
0x1800720b4  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800720bb  mov     edx, 0D6Eh; void *
0x1800720c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800720c5  mov     r9d, 8000FFFFh; char *
0x1800720cb  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800720d2  mov     edx, 0D6Fh; void *
0x1800720d7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800720dc  mov     r9d, eax; char *
0x1800720df  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800720e6  mov     edx, 0D74h; void *
0x1800720eb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
