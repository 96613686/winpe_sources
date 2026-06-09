# CEventBroker::SetDATASRCListener(DATASRCListener *)

- ea: `0x18000e990`
- end: `0x18000e9cd`
- name: `?SetDATASRCListener@CEventBroker@@UEAAJPEAUDATASRCListener@@@Z`
- size: `61`
- prototype: `__int64 __fastcall(CEventBroker *__hidden this, struct DATASRCListener *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003f70`
- `0x18000e990`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CEventBroker::SetDATASRCListener(struct IUnknown **this, struct DATASRCListener *a2)
{
  _QWORD *v2; // rdi

  v2 = this + 4;
  ClearInterfaceFn(this + 4);
  if ( a2 )
  {
    *v2 = a2;
    (*(void (__fastcall **)(struct DATASRCListener *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e990  mov     [rsp+arg_0], rbx
0x18000e995  push    rdi
0x18000e996  sub     rsp, 20h
0x18000e99a  lea     rdi, [rcx+20h]
0x18000e99e  mov     rbx, rdx
0x18000e9a1  mov     rcx, rdi; struct IUnknown **
0x18000e9a4  call    ?ClearInterfaceFn@@YAXPEAPEAUIUnknown@@@Z; ClearInterfaceFn(IUnknown * *)
0x18000e9a9  test    rbx, rbx
0x18000e9ac  jz      short loc_18000E9C0
0x18000e9ae  mov     [rdi], rbx
0x18000e9b1  mov     rcx, rbx
0x18000e9b4  mov     rax, [rbx]
0x18000e9b7  mov     rax, [rax+8]
0x18000e9bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9c0  mov     rbx, [rsp+28h+arg_0]
0x18000e9c5  xor     eax, eax
0x18000e9c7  add     rsp, 20h
0x18000e9cb  pop     rdi
0x18000e9cc  retn
```
