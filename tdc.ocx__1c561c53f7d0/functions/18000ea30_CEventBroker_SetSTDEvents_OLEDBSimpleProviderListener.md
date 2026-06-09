# CEventBroker::SetSTDEvents(OLEDBSimpleProviderListener *)

- ea: `0x18000ea30`
- end: `0x18000ea6d`
- name: `?SetSTDEvents@CEventBroker@@UEAAJPEAUOLEDBSimpleProviderListener@@@Z`
- size: `61`
- prototype: `__int64 __fastcall(CEventBroker *__hidden this, struct OLEDBSimpleProviderListener *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003f70`
- `0x18000ea30`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CEventBroker::SetSTDEvents(struct IUnknown **this, struct OLEDBSimpleProviderListener *a2)
{
  _QWORD *v2; // rdi

  v2 = this + 5;
  ClearInterfaceFn(this + 5);
  if ( a2 )
  {
    *v2 = a2;
    ((void (__fastcall *)(struct OLEDBSimpleProviderListener *))a2->lpVtbl->AddRef)(a2);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ea30  mov     [rsp+arg_0], rbx
0x18000ea35  push    rdi
0x18000ea36  sub     rsp, 20h
0x18000ea3a  lea     rdi, [rcx+28h]
0x18000ea3e  mov     rbx, rdx
0x18000ea41  mov     rcx, rdi; struct IUnknown **
0x18000ea44  call    ?ClearInterfaceFn@@YAXPEAPEAUIUnknown@@@Z; ClearInterfaceFn(IUnknown * *)
0x18000ea49  test    rbx, rbx
0x18000ea4c  jz      short loc_18000EA60
0x18000ea4e  mov     [rdi], rbx
0x18000ea51  mov     rcx, rbx
0x18000ea54  mov     rax, [rbx]
0x18000ea57  mov     rax, [rax+8]
0x18000ea5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea60  mov     rbx, [rsp+28h+arg_0]
0x18000ea65  xor     eax, eax
0x18000ea67  add     rsp, 20h
0x18000ea6b  pop     rdi
0x18000ea6c  retn
```
