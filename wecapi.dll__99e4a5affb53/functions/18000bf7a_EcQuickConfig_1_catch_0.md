# _EcQuickConfig_::_1_::catch$0

- ea: `0x18000bf7a`
- end: `0x18000bfaa`
- name: `_EcQuickConfig_::_1_::catch$0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall EcQuickConfig_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 64) = (***(__int64 (__fastcall ****)(_QWORD))(a2 + 32))(*(_QWORD *)(a2 + 32));
  return 0;
}

```

## disassembly

```asm
0x18000bf7a  mov     [rsp+arg_8], rdx
0x18000bf7f  push    rbp
0x18000bf80  sub     rsp, 20h
0x18000bf84  mov     rbp, rdx
0x18000bf87  mov     rcx, [rbp+20h]
0x18000bf8b  mov     rax, [rcx]
0x18000bf8e  mov     rax, [rax]
0x18000bf91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf96  mov     [rbp+40h], eax
0x18000bf99  mov     rax, 0
0x18000bfa3  add     rsp, 20h
0x18000bfa7  pop     rbp
0x18000bfa8  retn
```
