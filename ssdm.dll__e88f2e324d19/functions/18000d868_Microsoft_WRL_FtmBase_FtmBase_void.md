# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000d868`
- end: `0x18000d90c`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `164`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d780`
- `0x18000dd40`

## callees

- `0x18000d868`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000d899`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000d899`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  __int64 *v2; // rdi
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v5; // rcx
  LPUNKNOWN v6; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &Microsoft::WRL::FtmBase::`vftable';
  v2 = (__int64 *)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v5 = *v2;
    if ( *v2 )
    {
      *v2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, __int64 *))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v2);
  }
  v6 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v6->lpVtbl->Release)(v6);
  }
  return this;
}

```

## disassembly

```asm
0x18000d868  push    rbx
0x18000d86a  push    rbp
0x18000d86b  push    rsi
0x18000d86c  push    rdi
0x18000d86d  sub     rsp, 28h
0x18000d871  mov     rsi, rcx
0x18000d874  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000d87b  mov     [rcx], rax
0x18000d87e  lea     rdi, [rcx+18h]
0x18000d882  mov     qword ptr [rdi], 0
0x18000d889  mov     [rsp+48h+ppunkMarshal], 0
0x18000d892  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18000d897  xor     ecx, ecx; punkOuter
0x18000d899  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000d89f  test    eax, eax
0x18000d8a1  js      short loc_18000D8E0
0x18000d8a3  mov     rbx, [rsp+48h+ppunkMarshal]
0x18000d8a8  mov     rax, [rbx]
0x18000d8ab  mov     rbp, [rax]
0x18000d8ae  mov     rcx, [rdi]
0x18000d8b1  test    rcx, rcx
0x18000d8b4  jz      short loc_18000D8CA
0x18000d8b6  mov     qword ptr [rdi], 0
0x18000d8bd  mov     rdx, [rcx]
0x18000d8c0  mov     rax, [rdx+10h]
0x18000d8c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8c9  nop
0x18000d8ca  mov     r8, rdi
0x18000d8cd  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000d8d4  mov     rcx, rbx
0x18000d8d7  mov     rax, rbp
0x18000d8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8df  nop
0x18000d8e0  mov     rcx, [rsp+48h+ppunkMarshal]
0x18000d8e5  test    rcx, rcx
0x18000d8e8  jz      short loc_18000D900
0x18000d8ea  mov     [rsp+48h+ppunkMarshal], 0
0x18000d8f3  mov     rax, [rcx]
0x18000d8f6  mov     rax, [rax+10h]
0x18000d8fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8ff  nop
0x18000d900  mov     rax, rsi
0x18000d903  add     rsp, 28h
0x18000d907  pop     rdi
0x18000d908  pop     rsi
0x18000d909  pop     rbp
0x18000d90a  pop     rbx
0x18000d90b  retn
```
