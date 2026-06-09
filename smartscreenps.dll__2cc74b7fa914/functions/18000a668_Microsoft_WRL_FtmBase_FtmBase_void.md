# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000a668`
- end: `0x18000a70a`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `162`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a710`

## callees

- `0x180001590`
- `0x18000871c`
- `0x18000a668`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000a6b3`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000a6b3`

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
0x18000a668  push    rbx
0x18000a66a  push    rsi
0x18000a66b  push    rdi
0x18000a66c  push    r14
0x18000a66e  sub     rsp, 38h
0x18000a672  mov     rax, cs:__security_cookie
0x18000a679  xor     rax, rsp
0x18000a67c  mov     [rsp+58h+var_30], rax
0x18000a681  mov     rsi, rcx
0x18000a684  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000a68b  mov     [rcx], rax
0x18000a68e  lea     r14, [rcx+18h]
0x18000a692  mov     qword ptr [r14], 0
0x18000a699  mov     [rsp+58h+ppunkMarshal], 0
0x18000a6a2  lea     rcx, [rsp+58h+ppunkMarshal]
0x18000a6a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a6ac  lea     rdx, [rsp+58h+ppunkMarshal]; ppunkMarshal
0x18000a6b1  xor     ecx, ecx; punkOuter
0x18000a6b3  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000a6b9  test    eax, eax
0x18000a6bb  js      short loc_18000A6E6
0x18000a6bd  mov     rbx, [rsp+58h+ppunkMarshal]
0x18000a6c2  mov     rax, [rbx]
0x18000a6c5  mov     rdi, [rax]
0x18000a6c8  mov     rcx, r14
0x18000a6cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a6d0  mov     r8, r14
0x18000a6d3  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000a6da  mov     rcx, rbx
0x18000a6dd  mov     rax, rdi
0x18000a6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6e5  nop
0x18000a6e6  lea     rcx, [rsp+58h+ppunkMarshal]
0x18000a6eb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a6f0  mov     rax, rsi
0x18000a6f3  mov     rcx, [rsp+58h+var_30]
0x18000a6f8  xor     rcx, rsp; StackCookie
0x18000a6fb  call    __security_check_cookie
0x18000a700  add     rsp, 38h
0x18000a704  pop     r14
0x18000a706  pop     rdi
0x18000a707  pop     rsi
0x18000a708  pop     rbx
0x18000a709  retn
```
