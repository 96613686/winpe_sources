# InitializeComTasksLib$catch$0

- ea: `0x14000a380`
- end: `0x14000a3bc`
- name: `InitializeComTasksLib$catch$0`
- size: `60`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000a380`
- `0x14000c010`

## pseudocode

```c
__int64 __fastcall InitializeComTasksLib_catch_0(__int64 a1, __int64 a2)
{
  signed int v3; // eax

  v3 = (***(__int64 (__fastcall ****)(_QWORD))(a2 + 32))(*(_QWORD *)(a2 + 32));
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  *(_DWORD *)(a2 + 72) = v3;
  return 0;
}

```

## disassembly

```asm
0x14000a380  mov     [rsp+arg_8], rdx
0x14000a385  push    rbp
0x14000a386  sub     rsp, 20h
0x14000a38a  mov     rbp, rdx
0x14000a38d  mov     rcx, [rbp+20h]
0x14000a391  mov     rax, [rcx]
0x14000a394  mov     rax, [rax]
0x14000a397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a39c  test    eax, eax
0x14000a39e  jle     short loc_14000A3A8
0x14000a3a0  movzx   eax, ax
0x14000a3a3  or      eax, 80070000h
0x14000a3a8  mov     [rbp+48h], eax
0x14000a3ab  mov     rax, 0
0x14000a3b5  add     rsp, 20h
0x14000a3b9  pop     rbp
0x14000a3ba  retn
```
