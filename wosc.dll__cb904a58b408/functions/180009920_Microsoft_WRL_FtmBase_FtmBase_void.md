# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x180009920`
- end: `0x1800099a6`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800094f4`
- `0x180013894`
- `0x18002f274`
- `0x18002f3b4`
- `0x18002f4f4`
- `0x18002f634`
- `0x18004a340`

## callees

- `0x180005f50`
- `0x180009920`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000995c`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000995c`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  char *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

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
0x180009920  push    rbx
0x180009922  push    rsi
0x180009923  push    rdi
0x180009924  push    r14
0x180009926  sub     rsp, 28h
0x18000992a  mov     rsi, rcx
0x18000992d  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180009934  mov     [rcx], rax
0x180009937  lea     r14, [rcx+18h]
0x18000993b  mov     qword ptr [r14], 0
0x180009942  mov     [rsp+48h+ppunkMarshal], 0
0x18000994b  lea     rcx, [rsp+48h+ppunkMarshal]
0x180009950  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180009955  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18000995a  xor     ecx, ecx; punkOuter
0x18000995c  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180009962  test    eax, eax
0x180009964  js      short loc_18000998F
0x180009966  mov     rbx, [rsp+48h+ppunkMarshal]
0x18000996b  mov     rax, [rbx]
0x18000996e  mov     rdi, [rax]
0x180009971  mov     rcx, r14
0x180009974  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180009979  mov     r8, r14
0x18000997c  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180009983  mov     rcx, rbx
0x180009986  mov     rax, rdi
0x180009989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000998e  nop
0x18000998f  lea     rcx, [rsp+48h+ppunkMarshal]
0x180009994  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180009999  mov     rax, rsi
0x18000999c  add     rsp, 28h
0x1800099a0  pop     r14
0x1800099a2  pop     rdi
0x1800099a3  pop     rsi
0x1800099a4  pop     rbx
0x1800099a5  retn
```
