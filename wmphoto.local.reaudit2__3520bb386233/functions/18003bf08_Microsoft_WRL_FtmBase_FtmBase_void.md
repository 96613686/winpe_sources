# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18003bf08`
- end: `0x18003bf95`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `141`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003be80`

## callees

- `0x180035a50`
- `0x18003bf08`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18003bf44`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18003bf44`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18003bf08  push    rbx
0x18003bf0a  push    rsi
0x18003bf0b  push    rdi
0x18003bf0c  push    r14
0x18003bf0e  sub     rsp, 28h
0x18003bf12  mov     rsi, rcx
0x18003bf15  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18003bf1c  mov     [rcx], rax
0x18003bf1f  lea     r14, [rcx+18h]
0x18003bf23  mov     qword ptr [r14], 0
0x18003bf2a  mov     [rsp+48h+ppunkMarshal], 0
0x18003bf33  lea     rcx, [rsp+48h+ppunkMarshal]
0x18003bf38  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003bf3d  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18003bf42  xor     ecx, ecx; punkOuter
0x18003bf44  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18003bf4b  nop     dword ptr [rax+rax+00h]
0x18003bf50  test    eax, eax
0x18003bf52  js      short loc_18003BF7D
0x18003bf54  mov     rbx, [rsp+48h+ppunkMarshal]
0x18003bf59  mov     rax, [rbx]
0x18003bf5c  mov     rdi, [rax]
0x18003bf5f  mov     rcx, r14
0x18003bf62  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003bf67  mov     r8, r14
0x18003bf6a  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18003bf71  mov     rcx, rbx
0x18003bf74  mov     rax, rdi
0x18003bf77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf7c  nop
0x18003bf7d  lea     rcx, [rsp+48h+ppunkMarshal]
0x18003bf82  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003bf87  mov     rax, rsi
0x18003bf8a  add     rsp, 28h
0x18003bf8e  pop     r14
0x18003bf90  pop     rdi
0x18003bf91  pop     rsi
0x18003bf92  pop     rbx
0x18003bf93  retn
```
