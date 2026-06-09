# StopComTask$catch$0

- ea: `0x14000a7c0`
- end: `0x14000a7fc`
- name: `StopComTask$catch$0`
- size: `60`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000a7c0`
- `0x14000c010`

## pseudocode

```c
__int64 __fastcall StopComTask_catch_0(__int64 a1, __int64 a2)
{
  signed int v3; // eax

  v3 = (***(__int64 (__fastcall ****)(_QWORD))(a2 + 48))(*(_QWORD *)(a2 + 48));
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  *(_DWORD *)(a2 + 88) = v3;
  return 0;
}

```

## disassembly

```asm
0x14000a7c0  mov     [rsp+arg_8], rdx
0x14000a7c5  push    rbp
0x14000a7c6  sub     rsp, 30h
0x14000a7ca  mov     rbp, rdx
0x14000a7cd  mov     rcx, [rbp+30h]
0x14000a7d1  mov     rax, [rcx]
0x14000a7d4  mov     rax, [rax]
0x14000a7d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7dc  test    eax, eax
0x14000a7de  jle     short loc_14000A7E8
0x14000a7e0  movzx   eax, ax
0x14000a7e3  or      eax, 80070000h
0x14000a7e8  mov     [rbp+58h], eax
0x14000a7eb  mov     rax, 0
0x14000a7f5  add     rsp, 30h
0x14000a7f9  pop     rbp
0x14000a7fa  retn
```
