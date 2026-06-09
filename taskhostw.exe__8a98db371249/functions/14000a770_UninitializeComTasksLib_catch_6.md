# UninitializeComTasksLib$catch$6

- ea: `0x14000a770`
- end: `0x14000a7ac`
- name: `UninitializeComTasksLib$catch$6`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000a770`
- `0x14000c010`

## pseudocode

```c
__int64 __fastcall UninitializeComTasksLib_catch_6(__int64 a1, __int64 a2)
{
  signed int v3; // eax

  v3 = (***(__int64 (__fastcall ****)(_QWORD))(a2 + 40))(*(_QWORD *)(a2 + 40));
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  *(_DWORD *)(a2 + 64) = v3;
  return 0;
}

```

## disassembly

```asm
0x14000a770  mov     [rsp+arg_8], rdx
0x14000a775  push    rbp
0x14000a776  sub     rsp, 20h
0x14000a77a  mov     rbp, rdx
0x14000a77d  mov     rcx, [rbp+28h]
0x14000a781  mov     rax, [rcx]
0x14000a784  mov     rax, [rax]
0x14000a787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a78c  test    eax, eax
0x14000a78e  jle     short loc_14000A798
0x14000a790  movzx   eax, ax
0x14000a793  or      eax, 80070000h
0x14000a798  mov     [rbp+40h], eax
0x14000a79b  mov     rax, 0
0x14000a7a5  add     rsp, 20h
0x14000a7a9  pop     rbp
0x14000a7aa  retn
```
