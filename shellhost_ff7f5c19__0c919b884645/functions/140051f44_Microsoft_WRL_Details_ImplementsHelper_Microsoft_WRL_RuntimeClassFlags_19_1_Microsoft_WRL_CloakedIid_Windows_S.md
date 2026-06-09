# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>(void)

- ea: `0x140051f44`
- end: `0x140051fd5`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140051dc8`

## callees

- `0x14000ae48`
- `0x140051f44`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140051f8b`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140051f8b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>(
        _QWORD *a1)
{
  _QWORD *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *a1 = &Windows::Storage::Streams::IBufferByteAccess::`vftable';
  a1[2] = &Microsoft::WRL::FtmBase::`vftable';
  v2 = a1 + 5;
  a1[5] = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, _QWORD *))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v2);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  return a1;
}

```

## disassembly

```asm
0x140051f44  push    rbx
0x140051f46  push    rsi
0x140051f47  push    rdi
0x140051f48  push    r14
0x140051f4a  sub     rsp, 28h
0x140051f4e  mov     rsi, rcx
0x140051f51  lea     rax, ??_7IBufferByteAccess@Streams@Storage@Windows@@6B@; const Windows::Storage::Streams::IBufferByteAccess::`vftable'
0x140051f58  mov     [rcx], rax
0x140051f5b  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x140051f62  mov     [rcx+10h], rax
0x140051f66  lea     r14, [rcx+28h]
0x140051f6a  mov     qword ptr [r14], 0
0x140051f71  mov     [rsp+48h+ppunkMarshal], 0
0x140051f7a  lea     rcx, [rsp+48h+ppunkMarshal]
0x140051f7f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140051f84  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x140051f89  xor     ecx, ecx; punkOuter
0x140051f8b  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x140051f91  test    eax, eax
0x140051f93  js      short loc_140051FBE
0x140051f95  mov     rbx, [rsp+48h+ppunkMarshal]
0x140051f9a  mov     rax, [rbx]
0x140051f9d  mov     rdi, [rax]
0x140051fa0  mov     rcx, r14
0x140051fa3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140051fa8  mov     r8, r14
0x140051fab  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x140051fb2  mov     rcx, rbx
0x140051fb5  mov     rax, rdi
0x140051fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051fbd  nop
0x140051fbe  lea     rcx, [rsp+48h+ppunkMarshal]
0x140051fc3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140051fc8  mov     rax, rsi
0x140051fcb  add     rsp, 28h
0x140051fcf  pop     r14
0x140051fd1  pop     rdi
0x140051fd2  pop     rsi
0x140051fd3  pop     rbx
0x140051fd4  retn
```
