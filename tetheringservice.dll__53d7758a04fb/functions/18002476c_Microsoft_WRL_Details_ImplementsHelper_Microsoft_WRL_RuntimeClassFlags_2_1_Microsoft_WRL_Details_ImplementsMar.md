# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)

- ea: `0x18002476c`
- end: `0x180024810`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `164`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800241b4`
- `0x180024490`

## callees

- `0x18002476c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18002479d`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18002479d`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(
        _QWORD *a1)
{
  __int64 *v2; // rdi
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v5; // rcx
  LPUNKNOWN v6; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *a1 = &Microsoft::WRL::FtmBase::`vftable';
  v2 = a1 + 3;
  a1[3] = 0;
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
  return a1;
}

```

## disassembly

```asm
0x18002476c  push    rbx
0x18002476e  push    rbp
0x18002476f  push    rsi
0x180024770  push    rdi
0x180024771  sub     rsp, 28h
0x180024775  mov     rsi, rcx
0x180024778  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18002477f  mov     [rcx], rax
0x180024782  lea     rdi, [rcx+18h]
0x180024786  mov     qword ptr [rdi], 0
0x18002478d  mov     [rsp+48h+ppunkMarshal], 0
0x180024796  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18002479b  xor     ecx, ecx; punkOuter
0x18002479d  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800247a3  test    eax, eax
0x1800247a5  js      short loc_1800247E4
0x1800247a7  mov     rbx, [rsp+48h+ppunkMarshal]
0x1800247ac  mov     rax, [rbx]
0x1800247af  mov     rbp, [rax]
0x1800247b2  mov     rcx, [rdi]
0x1800247b5  test    rcx, rcx
0x1800247b8  jz      short loc_1800247CE
0x1800247ba  mov     qword ptr [rdi], 0
0x1800247c1  mov     rdx, [rcx]
0x1800247c4  mov     rax, [rdx+10h]
0x1800247c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247cd  nop
0x1800247ce  mov     r8, rdi
0x1800247d1  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800247d8  mov     rcx, rbx
0x1800247db  mov     rax, rbp
0x1800247de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247e3  nop
0x1800247e4  mov     rcx, [rsp+48h+ppunkMarshal]
0x1800247e9  test    rcx, rcx
0x1800247ec  jz      short loc_180024804
0x1800247ee  mov     [rsp+48h+ppunkMarshal], 0
0x1800247f7  mov     rax, [rcx]
0x1800247fa  mov     rax, [rax+10h]
0x1800247fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024803  nop
0x180024804  mov     rax, rsi
0x180024807  add     rsp, 28h
0x18002480b  pop     rdi
0x18002480c  pop     rsi
0x18002480d  pop     rbp
0x18002480e  pop     rbx
0x18002480f  retn
```
