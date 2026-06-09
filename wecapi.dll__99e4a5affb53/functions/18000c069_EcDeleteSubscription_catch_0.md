# EcDeleteSubscription$catch$0

- ea: `0x18000c069`
- end: `0x18000c09c`
- name: `EcDeleteSubscription$catch$0`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall EcDeleteSubscription_catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 200) = (***(__int64 (__fastcall ****)(_QWORD))(a2 + 48))(*(_QWORD *)(a2 + 48));
  return 0;
}

```

## disassembly

```asm
0x18000c069  mov     [rsp+arg_8], rdx
0x18000c06e  push    rbp
0x18000c06f  sub     rsp, 30h
0x18000c073  mov     rbp, rdx
0x18000c076  mov     rcx, [rbp+30h]
0x18000c07a  mov     rax, [rcx]
0x18000c07d  mov     rax, [rax]
0x18000c080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c085  mov     [rbp+0C8h], eax
0x18000c08b  mov     rax, 0
0x18000c095  add     rsp, 30h
0x18000c099  pop     rbp
0x18000c09a  retn
```
