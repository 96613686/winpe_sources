# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x140006880`
- end: `0x140006946`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `198`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `10`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005dc4`
- `0x14000628c`
- `0x140006580`
- `0x140006d88`
- `0x14000e7cc`
- `0x14001bdbc`
- `0x14001bf0c`
- `0x140030ba0`
- `0x140030c64`
- `0x140036bf0`

## callees

- `0x140006880`
- `0x140025aa0`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1400068c1`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1400068c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  LPUNKNOWN v2; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v4; // rcx
  LPUNKNOWN v5; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+20h] [rbp-28h] BYREF

  *(_QWORD *)this = &Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v2 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v4 = *((_QWORD *)this + 3);
    if ( v4 )
    {
      *((_QWORD *)this + 3) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(
      v2,
      &GUID_00000003_0000_0000_c000_000000000046,
      (char *)this + 24);
  }
  v5 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v5->lpVtbl->Release)(v5);
  }
  return this;
}

```

## disassembly

```asm
0x140006880  mov     [rsp+arg_8], rbx
0x140006885  mov     [rsp+arg_10], rbp
0x14000688a  push    rsi
0x14000688b  push    rdi
0x14000688c  push    r14
0x14000688e  sub     rsp, 30h
0x140006892  mov     rax, cs:__security_cookie
0x140006899  xor     rax, rsp
0x14000689c  mov     [rsp+48h+var_20], rax
0x1400068a1  mov     rsi, rcx
0x1400068a4  lea     rax, ??_7?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1400068ab  mov     [rcx], rax
0x1400068ae  xor     r14d, r14d
0x1400068b1  mov     [rcx+18h], r14
0x1400068b5  mov     [rsp+48h+ppunkMarshal], r14
0x1400068ba  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1400068bf  xor     ecx, ecx; punkOuter
0x1400068c1  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1400068c7  test    eax, eax
0x1400068c9  js      short loc_140006907
0x1400068cb  mov     rbx, [rsp+48h+ppunkMarshal]
0x1400068d0  mov     rax, [rbx]
0x1400068d3  mov     rbp, [rax]
0x1400068d6  mov     rcx, [rsi+18h]
0x1400068da  test    rcx, rcx
0x1400068dd  jz      short loc_1400068F0
0x1400068df  mov     [rsi+18h], r14
0x1400068e3  mov     rdx, [rcx]
0x1400068e6  mov     rax, [rdx+10h]
0x1400068ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068ef  nop
0x1400068f0  lea     r8, [rsi+18h]
0x1400068f4  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1400068fb  mov     rcx, rbx
0x1400068fe  mov     rax, rbp
0x140006901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006906  nop
0x140006907  mov     rcx, [rsp+48h+ppunkMarshal]
0x14000690c  test    rcx, rcx
0x14000690f  jz      short loc_140006923
0x140006911  mov     [rsp+48h+ppunkMarshal], r14
0x140006916  mov     rdx, [rcx]
0x140006919  mov     rax, [rdx+10h]
0x14000691d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006922  nop
0x140006923  mov     rax, rsi
0x140006926  mov     rcx, [rsp+48h+var_20]
0x14000692b  xor     rcx, rsp; StackCookie
0x14000692e  call    __security_check_cookie
0x140006933  mov     rbx, [rsp+48h+arg_8]
0x140006938  mov     rbp, [rsp+48h+arg_10]
0x14000693d  add     rsp, 30h
0x140006941  pop     r14
0x140006943  pop     rdi
0x140006944  pop     rsi
0x140006945  retn
```
