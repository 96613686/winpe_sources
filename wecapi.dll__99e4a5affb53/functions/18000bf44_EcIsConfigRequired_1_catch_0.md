# _EcIsConfigRequired_::_1_::catch$0

- ea: `0x18000bf44`
- end: `0x18000bf74`
- name: `_EcIsConfigRequired_::_1_::catch$0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall EcIsConfigRequired_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 112) = (***(__int64 (__fastcall ****)(_QWORD))(a2 + 32))(*(_QWORD *)(a2 + 32));
  return 0;
}

```

## disassembly

```asm
0x18000bf44  mov     [rsp+arg_8], rdx
0x18000bf49  push    rbp
0x18000bf4a  sub     rsp, 20h
0x18000bf4e  mov     rbp, rdx
0x18000bf51  mov     rcx, [rbp+20h]
0x18000bf55  mov     rax, [rcx]
0x18000bf58  mov     rax, [rax]
0x18000bf5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf60  mov     [rbp+70h], eax
0x18000bf63  mov     rax, 0
0x18000bf6d  add     rsp, 20h
0x18000bf71  pop     rbp
0x18000bf72  retn
```
