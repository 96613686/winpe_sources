# CEventBroker::SetDataSourceListener(DataSourceListener *)

- ea: `0x18000e9e0`
- end: `0x18000ea1d`
- name: `?SetDataSourceListener@CEventBroker@@UEAAJPEAUDataSourceListener@@@Z`
- size: `61`
- prototype: `__int64 __fastcall(CEventBroker *__hidden this, struct DataSourceListener *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003f70`
- `0x18000e9e0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CEventBroker::SetDataSourceListener(struct IUnknown **this, struct DataSourceListener *a2)
{
  _QWORD *v2; // rdi

  v2 = this + 3;
  ClearInterfaceFn(this + 3);
  if ( a2 )
  {
    *v2 = a2;
    ((void (__fastcall *)(struct DataSourceListener *))a2->lpVtbl->AddRef)(a2);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e9e0  mov     [rsp+arg_0], rbx
0x18000e9e5  push    rdi
0x18000e9e6  sub     rsp, 20h
0x18000e9ea  lea     rdi, [rcx+18h]
0x18000e9ee  mov     rbx, rdx
0x18000e9f1  mov     rcx, rdi; struct IUnknown **
0x18000e9f4  call    ?ClearInterfaceFn@@YAXPEAPEAUIUnknown@@@Z; ClearInterfaceFn(IUnknown * *)
0x18000e9f9  test    rbx, rbx
0x18000e9fc  jz      short loc_18000EA10
0x18000e9fe  mov     [rdi], rbx
0x18000ea01  mov     rcx, rbx
0x18000ea04  mov     rax, [rbx]
0x18000ea07  mov     rax, [rax+8]
0x18000ea0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea10  mov     rbx, [rsp+28h+arg_0]
0x18000ea15  xor     eax, eax
0x18000ea17  add     rsp, 20h
0x18000ea1b  pop     rdi
0x18000ea1c  retn
```
