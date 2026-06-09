# InitializeComTasksLib$catch$6

- ea: `0x14000a4c0`
- end: `0x14000a4e8`
- name: `InitializeComTasksLib$catch$6`
- size: `40`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 __fastcall InitializeComTasksLib_catch_6(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = *(_DWORD *)(*(_QWORD *)(a2 + 40) + 8LL);
  return 0;
}

```

## disassembly

```asm
0x14000a4c0  mov     [rsp+arg_8], rdx
0x14000a4c5  push    rbp
0x14000a4c6  sub     rsp, 20h
0x14000a4ca  mov     rbp, rdx
0x14000a4cd  mov     rax, [rbp+28h]
0x14000a4d1  mov     ecx, [rax+8]
0x14000a4d4  mov     [rbp+48h], ecx
0x14000a4d7  mov     rax, 0
0x14000a4e1  add     rsp, 20h
0x14000a4e5  pop     rbp
0x14000a4e6  retn
```
