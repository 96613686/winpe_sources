# StartComTask$catch$0

- ea: `0x14000a930`
- end: `0x14000a96c`
- name: `StartComTask$catch$0`
- size: `60`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000a930`
- `0x14000c010`

## pseudocode

```c
__int64 __fastcall StartComTask_catch_0(__int64 a1, __int64 a2)
{
  signed int v3; // eax

  v3 = (***(__int64 (__fastcall ****)(_QWORD))(a2 + 72))(*(_QWORD *)(a2 + 72));
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  *(_DWORD *)(a2 + 64) = v3;
  return 0;
}

```

## disassembly

```asm
0x14000a930  mov     [rsp+arg_8], rdx
0x14000a935  push    rbp
0x14000a936  sub     rsp, 40h
0x14000a93a  mov     rbp, rdx
0x14000a93d  mov     rcx, [rbp+48h]
0x14000a941  mov     rax, [rcx]
0x14000a944  mov     rax, [rax]
0x14000a947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a94c  test    eax, eax
0x14000a94e  jle     short loc_14000A958
0x14000a950  movzx   eax, ax
0x14000a953  or      eax, 80070000h
0x14000a958  mov     [rbp+40h], eax
0x14000a95b  mov     rax, 0
0x14000a965  add     rsp, 40h
0x14000a969  pop     rbp
0x14000a96a  retn
```
