# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x1800144c8`
- end: `0x18001454e`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `134`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800147e4`
- `0x180020aa0`

## callees

- `0x1800067a0`
- `0x1800144c8`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180014504`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180014504`

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
0x1800144c8  push    rbx
0x1800144ca  push    rsi
0x1800144cb  push    rdi
0x1800144cc  push    r14
0x1800144ce  sub     rsp, 28h
0x1800144d2  mov     rsi, rcx
0x1800144d5  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800144dc  mov     [rcx], rax
0x1800144df  lea     r14, [rcx+18h]
0x1800144e3  mov     qword ptr [r14], 0
0x1800144ea  mov     [rsp+48h+ppunkMarshal], 0
0x1800144f3  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800144f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800144fd  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180014502  xor     ecx, ecx; punkOuter
0x180014504  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18001450a  test    eax, eax
0x18001450c  js      short loc_180014537
0x18001450e  mov     rbx, [rsp+48h+ppunkMarshal]
0x180014513  mov     rax, [rbx]
0x180014516  mov     rdi, [rax]
0x180014519  mov     rcx, r14
0x18001451c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014521  mov     r8, r14
0x180014524  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18001452b  mov     rcx, rbx
0x18001452e  mov     rax, rdi
0x180014531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014536  nop
0x180014537  lea     rcx, [rsp+48h+ppunkMarshal]
0x18001453c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014541  mov     rax, rsi
0x180014544  add     rsp, 28h
0x180014548  pop     r14
0x18001454a  pop     rdi
0x18001454b  pop     rsi
0x18001454c  pop     rbx
0x18001454d  retn
```
