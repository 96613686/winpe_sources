# EcRemoveObjectArrayElement$catch$1

- ea: `0x18000c219`
- end: `0x18000c249`
- name: `EcRemoveObjectArrayElement$catch$1`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall EcRemoveObjectArrayElement_catch_1(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 80) = (***(__int64 (__fastcall ****)(_QWORD))(a2 + 32))(*(_QWORD *)(a2 + 32));
  return 0;
}

```

## disassembly

```asm
0x18000c219  mov     [rsp+arg_8], rdx
0x18000c21e  push    rbp
0x18000c21f  sub     rsp, 20h
0x18000c223  mov     rbp, rdx
0x18000c226  mov     rcx, [rbp+20h]
0x18000c22a  mov     rax, [rcx]
0x18000c22d  mov     rax, [rax]
0x18000c230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c235  mov     [rbp+50h], eax
0x18000c238  mov     rax, 0
0x18000c242  add     rsp, 20h
0x18000c246  pop     rbp
0x18000c247  retn
```
