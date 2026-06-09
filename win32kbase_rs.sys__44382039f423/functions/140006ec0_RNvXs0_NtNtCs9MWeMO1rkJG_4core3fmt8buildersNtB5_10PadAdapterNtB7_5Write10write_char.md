# _RNvXs0_NtNtCs9MWeMO1rkJG_4core3fmt8buildersNtB5_10PadAdapterNtB7_5Write10write_char

- ea: `0x140006ec0`
- end: `0x140006f24`
- name: `_RNvXs0_NtNtCs9MWeMO1rkJG_4core3fmt8buildersNtB5_10PadAdapterNtB7_5Write10write_char`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140006ec0`
- `0x140017a50`

## pseudocode

```c
char __fastcall RNvXs0_NtNtCs9MWeMO1rkJG_4core3fmt8buildersNtB5_10PadAdapterNtB7_5Write10write_char(_QWORD *a1, int a2)
{
  bool *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rbx
  int v5; // ebp
  char v6; // al

  v2 = (bool *)a1[2];
  v3 = *a1;
  v4 = a1[1];
  if ( *v2 )
  {
    v5 = a2;
    v6 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64))(v4 + 24))(*a1, byte_14001CC33, 4);
    a2 = v5;
    if ( v6 )
      return 1;
  }
  *v2 = a2 == 10;
  return (*(__int64 (__fastcall **)(__int64))(v4 + 32))(v3);
}

```

## disassembly

```asm
0x140006ec0  push    rsi
0x140006ec1  push    rdi
0x140006ec2  push    rbp
0x140006ec3  push    rbx
0x140006ec4  sub     rsp, 28h
0x140006ec8  mov     rdi, [rcx+10h]
0x140006ecc  mov     rsi, [rcx]
0x140006ecf  mov     rbx, [rcx+8]
0x140006ed3  cmp     byte ptr [rdi], 0
0x140006ed6  jz      short loc_140006F08
0x140006ed8  mov     rax, [rbx+18h]
0x140006edc  lea     r9, byte_14001CC33
0x140006ee3  mov     r8d, 4
0x140006ee9  mov     rcx, rsi
0x140006eec  mov     ebp, edx
0x140006eee  mov     rdx, r9
0x140006ef1  call    cs:__guard_dispatch_icall_fptr
0x140006ef7  mov     edx, ebp
0x140006ef9  test    al, al
0x140006efb  jz      short loc_140006F08
0x140006efd  mov     al, 1
0x140006eff  add     rsp, 28h
0x140006f03  pop     rbx
0x140006f04  pop     rbp
0x140006f05  pop     rdi
0x140006f06  pop     rsi
0x140006f07  retn
0x140006f08  cmp     edx, 0Ah
0x140006f0b  setz    byte ptr [rdi]
0x140006f0e  mov     rax, [rbx+20h]
0x140006f12  mov     rcx, rsi
0x140006f15  add     rsp, 28h
0x140006f19  pop     rbx
0x140006f1a  pop     rbp
0x140006f1b  pop     rdi
0x140006f1c  pop     rsi
0x140006f1d  jmp     cs:__guard_dispatch_icall_fptr
```
