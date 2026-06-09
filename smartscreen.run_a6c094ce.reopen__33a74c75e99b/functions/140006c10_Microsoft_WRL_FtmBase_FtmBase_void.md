# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x140006c10`
- end: `0x140006cdd`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `205`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `10`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006144`
- `0x140006610`
- `0x140006900`
- `0x140007138`
- `0x14000ef5c`
- `0x14001ccbc`
- `0x14001ce18`
- `0x140031f44`
- `0x140032010`
- `0x14003812c`

## callees

- `0x140006c10`
- `0x140026c20`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140006c51`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140006c51`

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
0x140006c10  mov     [rsp+arg_8], rbx
0x140006c15  mov     [rsp+arg_10], rbp
0x140006c1a  push    rsi
0x140006c1b  push    rdi
0x140006c1c  push    r14
0x140006c1e  sub     rsp, 30h
0x140006c22  mov     rax, cs:__security_cookie
0x140006c29  xor     rax, rsp
0x140006c2c  mov     [rsp+48h+var_20], rax
0x140006c31  mov     rsi, rcx
0x140006c34  lea     rax, ??_7?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x140006c3b  mov     [rcx], rax
0x140006c3e  xor     r14d, r14d
0x140006c41  mov     [rcx+18h], r14
0x140006c45  mov     [rsp+48h+ppunkMarshal], r14
0x140006c4a  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x140006c4f  xor     ecx, ecx; punkOuter
0x140006c51  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x140006c58  nop     dword ptr [rax+rax+00h]
0x140006c5d  test    eax, eax
0x140006c5f  js      short loc_140006C9D
0x140006c61  mov     rbx, [rsp+48h+ppunkMarshal]
0x140006c66  mov     rax, [rbx]
0x140006c69  mov     rbp, [rax]
0x140006c6c  mov     rcx, [rsi+18h]
0x140006c70  test    rcx, rcx
0x140006c73  jz      short loc_140006C86
0x140006c75  mov     [rsi+18h], r14
0x140006c79  mov     rdx, [rcx]
0x140006c7c  mov     rax, [rdx+10h]
0x140006c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c85  nop
0x140006c86  lea     r8, [rsi+18h]
0x140006c8a  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x140006c91  mov     rcx, rbx
0x140006c94  mov     rax, rbp
0x140006c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c9c  nop
0x140006c9d  mov     rcx, [rsp+48h+ppunkMarshal]
0x140006ca2  test    rcx, rcx
0x140006ca5  jz      short loc_140006CB9
0x140006ca7  mov     [rsp+48h+ppunkMarshal], r14
0x140006cac  mov     rdx, [rcx]
0x140006caf  mov     rax, [rdx+10h]
0x140006cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006cb8  nop
0x140006cb9  mov     rax, rsi
0x140006cbc  mov     rcx, [rsp+48h+var_20]
0x140006cc1  xor     rcx, rsp; StackCookie
0x140006cc4  call    __security_check_cookie
0x140006cc9  mov     rbx, [rsp+48h+arg_8]
0x140006cce  mov     rbp, [rsp+48h+arg_10]
0x140006cd3  add     rsp, 30h
0x140006cd7  pop     r14
0x140006cd9  pop     rdi
0x140006cda  pop     rsi
0x140006cdb  retn
```
