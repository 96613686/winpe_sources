# EcOpenSubscription$catch$3

- ea: `0x18000c273`
- end: `0x18000c2b1`
- name: `EcOpenSubscription$catch$3`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall EcOpenSubscription_catch_3(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 320) = (***(__int64 (__fastcall ****)(_QWORD))(a2 + 40))(*(_QWORD *)(a2 + 40));
  *(_QWORD *)(a2 + 328) = 0;
  return 0;
}

```

## disassembly

```asm
0x18000c273  mov     [rsp+arg_8], rdx
0x18000c278  push    rbp
0x18000c279  sub     rsp, 20h
0x18000c27d  mov     rbp, rdx
0x18000c280  mov     rcx, [rbp+28h]
0x18000c284  mov     rax, [rcx]
0x18000c287  mov     rax, [rax]
0x18000c28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c28f  mov     [rbp+140h], eax
0x18000c295  mov     qword ptr [rbp+148h], 0
0x18000c2a0  mov     rax, 0
0x18000c2aa  add     rsp, 20h
0x18000c2ae  pop     rbp
0x18000c2af  retn
```
