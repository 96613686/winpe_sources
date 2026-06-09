# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000a8dc`
- end: `0x18000a985`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `169`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a98c`

## callees

- `0x180001590`
- `0x180008828`
- `0x18000a8dc`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000a927`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000a927`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  char *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+20h] [rbp-38h] BYREF

  *(_QWORD *)this = &Microsoft::WRL::FtmBase::`vftable';
  v2 = (char *)this + 24;
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(v3, &GUID_00000003_0000_0000_c000_000000000046, v2);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  return this;
}

```

## disassembly

```asm
0x18000a8dc  push    rbx
0x18000a8de  push    rsi
0x18000a8df  push    rdi
0x18000a8e0  push    r14
0x18000a8e2  sub     rsp, 38h
0x18000a8e6  mov     rax, cs:__security_cookie
0x18000a8ed  xor     rax, rsp
0x18000a8f0  mov     [rsp+58h+var_30], rax
0x18000a8f5  mov     rsi, rcx
0x18000a8f8  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000a8ff  mov     [rcx], rax
0x18000a902  lea     r14, [rcx+18h]
0x18000a906  mov     qword ptr [r14], 0
0x18000a90d  mov     [rsp+58h+ppunkMarshal], 0
0x18000a916  lea     rcx, [rsp+58h+ppunkMarshal]
0x18000a91b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a920  lea     rdx, [rsp+58h+ppunkMarshal]; ppunkMarshal
0x18000a925  xor     ecx, ecx; punkOuter
0x18000a927  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000a92e  nop     dword ptr [rax+rax+00h]
0x18000a933  test    eax, eax
0x18000a935  js      short loc_18000A960
0x18000a937  mov     rbx, [rsp+58h+ppunkMarshal]
0x18000a93c  mov     rax, [rbx]
0x18000a93f  mov     rdi, [rax]
0x18000a942  mov     rcx, r14
0x18000a945  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a94a  mov     r8, r14
0x18000a94d  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000a954  mov     rcx, rbx
0x18000a957  mov     rax, rdi
0x18000a95a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a95f  nop
0x18000a960  lea     rcx, [rsp+58h+ppunkMarshal]
0x18000a965  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a96a  mov     rax, rsi
0x18000a96d  mov     rcx, [rsp+58h+var_30]
0x18000a972  xor     rcx, rsp; StackCookie
0x18000a975  call    __security_check_cookie
0x18000a97a  add     rsp, 38h
0x18000a97e  pop     r14
0x18000a980  pop     rdi
0x18000a981  pop     rsi
0x18000a982  pop     rbx
0x18000a983  retn
```
