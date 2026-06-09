# CEventBroker::~CEventBroker(void)

- ea: `0x18000e700`
- end: `0x18000e733`
- name: `??1CEventBroker@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(CEventBroker *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e790`

## callees

- `0x180003f70`

## pseudocode

```c
void __fastcall CEventBroker::~CEventBroker(struct IUnknown **this)
{
  *this = (struct IUnknown *)&CEventBroker::`vftable';
  ClearInterfaceFn(this + 3);
  ClearInterfaceFn(this + 4);
  ClearInterfaceFn(this + 5);
}

```

## disassembly

```asm
0x18000e700  push    rbx
0x18000e702  sub     rsp, 20h
0x18000e706  lea     rax, ??_7CEventBroker@@6B@; const CEventBroker::`vftable'
0x18000e70d  mov     rbx, rcx
0x18000e710  mov     [rcx], rax
0x18000e713  add     rcx, 18h; struct IUnknown **
0x18000e717  call    ?ClearInterfaceFn@@YAXPEAPEAUIUnknown@@@Z; ClearInterfaceFn(IUnknown * *)
0x18000e71c  lea     rcx, [rbx+20h]; struct IUnknown **
0x18000e720  call    ?ClearInterfaceFn@@YAXPEAPEAUIUnknown@@@Z; ClearInterfaceFn(IUnknown * *)
0x18000e725  lea     rcx, [rbx+28h]; struct IUnknown **
0x18000e729  add     rsp, 20h
0x18000e72d  pop     rbx
0x18000e72e  jmp     ?ClearInterfaceFn@@YAXPEAPEAUIUnknown@@@Z; ClearInterfaceFn(IUnknown * *)
```
