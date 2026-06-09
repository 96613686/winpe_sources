# EcOpenSubscriptionEnum$catch$6

- ea: `0x18000c2ed`
- end: `0x18000c32b`
- name: `EcOpenSubscriptionEnum$catch$6`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall EcOpenSubscriptionEnum_catch_6(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 288) = (***(__int64 (__fastcall ****)(_QWORD))(a2 + 64))(*(_QWORD *)(a2 + 64));
  *(_QWORD *)(a2 + 296) = 0;
  return 0;
}

```

## disassembly

```asm
0x18000c2ed  mov     [rsp+arg_8], rdx
0x18000c2f2  push    rbp
0x18000c2f3  sub     rsp, 40h
0x18000c2f7  mov     rbp, rdx
0x18000c2fa  mov     rcx, [rbp+40h]
0x18000c2fe  mov     rax, [rcx]
0x18000c301  mov     rax, [rax]
0x18000c304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c309  mov     [rbp+120h], eax
0x18000c30f  mov     qword ptr [rbp+128h], 0
0x18000c31a  mov     rax, 0
0x18000c324  add     rsp, 40h
0x18000c328  pop     rbp
0x18000c329  retn
```
