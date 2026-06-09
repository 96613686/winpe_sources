# StartComTask$catch$6

- ea: `0x14000aa70`
- end: `0x14000aa98`
- name: `StartComTask$catch$6`
- size: `40`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 __fastcall StartComTask_catch_6(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 64) = *(_DWORD *)(*(_QWORD *)(a2 + 80) + 8LL);
  return 0;
}

```

## disassembly

```asm
0x14000aa70  mov     [rsp+arg_8], rdx
0x14000aa75  push    rbp
0x14000aa76  sub     rsp, 40h
0x14000aa7a  mov     rbp, rdx
0x14000aa7d  mov     rax, [rbp+50h]
0x14000aa81  mov     ecx, [rax+8]
0x14000aa84  mov     [rbp+40h], ecx
0x14000aa87  mov     rax, 0
0x14000aa91  add     rsp, 40h
0x14000aa95  pop     rbp
0x14000aa96  retn
```
