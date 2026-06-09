# RtlWriteULongToUser

- ea: `0x14001452c`
- end: `0x14001456a`
- name: `RtlWriteULongToUser`
- size: `62`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x140009070`
- `0x1400154ac`
- `0x140015a70`
- `0x140015dc4`
- `0x140016734`
- `0x140016aa8`
- `0x140016d68`
- `0x14001771c`
- `0x1400179f4`
- `0x140030708`
- `0x140031e40`

## callees

- `0x14000403f`
- `0x14001452c`

## pseudocode

```c
void __fastcall RtlWriteULongToUser(_DWORD *a1, int a2)
{
  ProbeForRead_0(a1, 4u, 1u);
  *a1 = a2;
}

```

## disassembly

```asm
0x14001452c  mov     [rsp+arg_0], rbx
0x140014531  push    rdi
0x140014532  sub     rsp, 20h
0x140014536  mov     rax, cs:qword_140011800
0x14001453d  mov     edi, edx
0x14001453f  mov     rbx, rcx
0x140014542  test    rax, rax
0x140014545  jz      short loc_14001454E
0x140014547  call    rax ; qword_140011800
0x140014549  nop     dword ptr [rax]
0x14001454c  jmp     short loc_14001455E
0x14001454e  mov     edx, 4; Length
0x140014553  lea     r8d, [rdx-3]; Alignment
0x140014557  call    ProbeForRead_0
0x14001455c  mov     [rbx], edi
0x14001455e  mov     rbx, [rsp+28h+arg_0]
0x140014563  add     rsp, 20h
0x140014567  pop     rdi
0x140014568  retn
```
