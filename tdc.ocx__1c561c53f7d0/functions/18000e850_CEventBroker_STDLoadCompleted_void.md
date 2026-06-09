# CEventBroker::STDLoadCompleted(void)

- ea: `0x18000e850`
- end: `0x18000e8a0`
- name: `?STDLoadCompleted@CEventBroker@@UEAAJXZ`
- size: `80`
- prototype: `__int64 __fastcall(CEventBroker *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e850`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CEventBroker::STDLoadCompleted(CEventBroker *this)
{
  unsigned int v1; // edi
  __int64 v3; // rcx

  v1 = 0;
  *((_QWORD *)this + 1) = 0;
  v3 = *((_QWORD *)this + 5);
  if ( v3 )
    v1 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 80LL))(v3, 0);
  (*(void (__fastcall **)(CEventBroker *, __int64))(*(_QWORD *)this + 160LL))(this, 4);
  return v1;
}

```

## disassembly

```asm
0x18000e850  mov     [rsp+arg_0], rbx
0x18000e855  push    rdi
0x18000e856  sub     rsp, 20h
0x18000e85a  xor     edi, edi
0x18000e85c  mov     rbx, rcx
0x18000e85f  mov     [rcx+8], rdi
0x18000e863  mov     rcx, [rcx+28h]
0x18000e867  test    rcx, rcx
0x18000e86a  jz      short loc_18000E87C
0x18000e86c  mov     rax, [rcx]
0x18000e86f  xor     edx, edx
0x18000e871  mov     rax, [rax+50h]
0x18000e875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e87a  mov     edi, eax
0x18000e87c  mov     rcx, [rbx]
0x18000e87f  mov     edx, 4
0x18000e884  mov     rax, [rcx+0A0h]
0x18000e88b  mov     rcx, rbx
0x18000e88e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e893  mov     rbx, [rsp+28h+arg_0]
0x18000e898  mov     eax, edi
0x18000e89a  add     rsp, 20h
0x18000e89e  pop     rdi
0x18000e89f  retn
```
