# CEventBroker::STDLoadedHeader(void)

- ea: `0x18000e940`
- end: `0x18000e982`
- name: `?STDLoadedHeader@CEventBroker@@UEAAJXZ`
- size: `66`
- prototype: `__int64 __fastcall(CEventBroker *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall CEventBroker::STDLoadedHeader(CEventBroker *this)
{
  unsigned int v2; // ebx

  v2 = (*(__int64 (__fastcall **)(CEventBroker *))(*(_QWORD *)this + 144LL))(this);
  (*(void (__fastcall **)(CEventBroker *, __int64))(*(_QWORD *)this + 160LL))(this, 3);
  return v2;
}

```

## disassembly

```asm
0x18000e940  mov     [rsp+arg_0], rbx
0x18000e945  push    rdi
0x18000e946  sub     rsp, 20h
0x18000e94a  mov     rax, [rcx]
0x18000e94d  mov     rdi, rcx
0x18000e950  mov     rax, [rax+90h]
0x18000e957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e95c  mov     rdx, [rdi]
0x18000e95f  mov     ebx, eax
0x18000e961  mov     rcx, rdi
0x18000e964  mov     rax, [rdx+0A0h]
0x18000e96b  mov     edx, 3
0x18000e970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e975  mov     eax, ebx
0x18000e977  mov     rbx, [rsp+28h+arg_0]
0x18000e97c  add     rsp, 20h
0x18000e980  pop     rdi
0x18000e981  retn
```
