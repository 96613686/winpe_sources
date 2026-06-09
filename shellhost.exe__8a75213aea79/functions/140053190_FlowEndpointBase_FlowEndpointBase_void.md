# FlowEndpointBase::~FlowEndpointBase(void)

- ea: `0x140053190`
- end: `0x140053242`
- name: `??1FlowEndpointBase@@UEAA@XZ`
- size: `178`
- prototype: `void __fastcall(FlowEndpointBase *__hidden this)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140006ab0`
- `0x140053148`
- `0x140053358`
- `0x1400548d0`
- `0x14005bd30`

## callees

- `0x14000b360`
- `0x140046a30`
- `0x140052bf8`
- `0x140052fbc`
- `0x14005303c`
- `0x1400530cc`
- `0x140053190`

## string_xrefs

- `0x1400531b8`: `shellcommon\internal\shell\inc\ValueSetChannel.h`

## pseudocode

```c
void __fastcall FlowEndpointBase::~FlowEndpointBase(FlowEndpointBase *this, __int64 a2, __int64 a3, const char *a4)
{
  bool v4; // zf
  _QWORD **v6; // rcx
  _QWORD *v7; // rsi
  _QWORD *v8; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *((_QWORD *)this + 1) == 0;
  *(_QWORD *)this = &FlowEndpointBase::`vftable';
  if ( !v4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x51,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\ValueSetChannel.h",
      a4);
  v6 = (_QWORD **)*((_QWORD *)this + 12);
  *v6[1] = 0;
  v7 = *v6;
  if ( *v6 )
  {
    do
    {
      v8 = (_QWORD *)*v7;
      winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)(v7 + 3));
      std::_Deallocate<16>(v7, 32);
      v7 = v8;
    }
    while ( v8 );
  }
  std::_Deallocate<16>(*((_QWORD *)this + 12), 32);
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((FlowEndpointBase *)((char *)this + 72));
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>((char *)this + 64);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 56);
  CImpWorkerWndProc::~CImpWorkerWndProc(this);
}

```

## disassembly

```asm
0x140053190  mov     [rsp+arg_0], rbx
0x140053195  mov     [rsp+arg_8], rsi
0x14005319a  push    rdi
0x14005319b  sub     rsp, 20h
0x14005319f  cmp     qword ptr [rcx+8], 0
0x1400531a4  lea     rax, ??_7FlowEndpointBase@@6B@; const FlowEndpointBase::`vftable'
0x1400531ab  mov     [rcx], rax
0x1400531ae  mov     rdi, rcx
0x1400531b1  jz      short loc_1400531CA
0x1400531b3  mov     rcx, [rsp+28h]; this
0x1400531b8  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\Valu"...
0x1400531bf  mov     edx, 51h ; 'Q'; void *
0x1400531c4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400531ca  mov     rcx, [rcx+60h]
0x1400531ce  mov     rax, [rcx+8]
0x1400531d2  mov     qword ptr [rax], 0
0x1400531d9  mov     rsi, [rcx]
0x1400531dc  test    rsi, rsi
0x1400531df  jz      short loc_140053202
0x1400531e1  mov     rbx, [rsi]
0x1400531e4  lea     rcx, [rsi+18h]; this
0x1400531e8  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x1400531ed  mov     edx, 20h ; ' '
0x1400531f2  mov     rcx, rsi
0x1400531f5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400531fa  mov     rsi, rbx
0x1400531fd  test    rbx, rbx
0x140053200  jnz     short loc_1400531E1
0x140053202  mov     rcx, [rdi+60h]
0x140053206  mov     edx, 20h ; ' '
0x14005320b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140053210  lea     rcx, [rdi+48h]; this
0x140053214  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x140053219  lea     rcx, [rdi+40h]
0x14005321d  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>(void)
0x140053222  lea     rcx, [rdi+38h]
0x140053226  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14005322b  mov     rcx, rdi; this
0x14005322e  mov     rbx, [rsp+28h+arg_0]
0x140053233  mov     rsi, [rsp+28h+arg_8]
0x140053238  add     rsp, 20h
0x14005323c  pop     rdi
0x14005323d  jmp     ??1CImpWorkerWndProc@@MEAA@XZ; CImpWorkerWndProc::~CImpWorkerWndProc(void)
```
