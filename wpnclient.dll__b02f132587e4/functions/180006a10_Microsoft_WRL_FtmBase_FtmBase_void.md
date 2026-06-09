# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180006a10`
- end: `0x180006ac4`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `180`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005e20`
- `0x180005e98`
- `0x1800066c0`
- `0x1800068f0`
- `0x1800162c8`
- `0x18001839c`
- `0x180023488`
- `0x180024b78`
- `0x1800279ec`

## callees

- `0x180005670`
- `0x180006a10`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180006a4c`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180006a4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  LPUNKNOWN v2; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v4; // rcx
  LPUNKNOWN v5; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &CActivatedEventArgsBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
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
0x180006a10  mov     [rsp+arg_8], rbx
0x180006a15  mov     [rsp+arg_10], rbp
0x180006a1a  push    rsi
0x180006a1b  push    rdi
0x180006a1c  push    r14
0x180006a1e  sub     rsp, 20h
0x180006a22  mov     rsi, rcx
0x180006a25  lea     rax, ??_7CActivatedEventArgsBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CActivatedEventArgsBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180006a2c  mov     [rcx], rax
0x180006a2f  xor     r14d, r14d
0x180006a32  mov     [rcx+18h], r14
0x180006a36  mov     [rsp+38h+ppunkMarshal], r14
0x180006a3b  lea     rcx, [rsp+38h+ppunkMarshal]
0x180006a40  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006a45  lea     rdx, [rsp+38h+ppunkMarshal]; ppunkMarshal
0x180006a4a  xor     ecx, ecx; punkOuter
0x180006a4c  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180006a52  test    eax, eax
0x180006a54  js      short loc_180006A92
0x180006a56  mov     rbx, [rsp+38h+ppunkMarshal]
0x180006a5b  mov     rax, [rbx]
0x180006a5e  mov     rbp, [rax]
0x180006a61  mov     rcx, [rsi+18h]
0x180006a65  test    rcx, rcx
0x180006a68  jz      short loc_180006A7B
0x180006a6a  mov     [rsi+18h], r14
0x180006a6e  mov     rdx, [rcx]
0x180006a71  mov     rax, [rdx+10h]
0x180006a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a7a  nop
0x180006a7b  lea     r8, [rsi+18h]
0x180006a7f  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180006a86  mov     rcx, rbx
0x180006a89  mov     rax, rbp
0x180006a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a91  nop
0x180006a92  mov     rcx, [rsp+38h+ppunkMarshal]
0x180006a97  test    rcx, rcx
0x180006a9a  jz      short loc_180006AAE
0x180006a9c  mov     [rsp+38h+ppunkMarshal], r14
0x180006aa1  mov     rax, [rcx]
0x180006aa4  mov     rax, [rax+10h]
0x180006aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aad  nop
0x180006aae  mov     rax, rsi
0x180006ab1  mov     rbx, [rsp+38h+arg_8]
0x180006ab6  mov     rbp, [rsp+38h+arg_10]
0x180006abb  add     rsp, 20h
0x180006abf  pop     r14
0x180006ac1  pop     rdi
0x180006ac2  pop     rsi
0x180006ac3  retn
```
