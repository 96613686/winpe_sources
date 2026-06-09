# core::fmt::impl$12::pad_integral::write_prefix

- ea: `0x140006e50`
- end: `0x140006eb3`
- name: `core::fmt::impl$12::pad_integral::write_prefix`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005870`

## callees

- `0x140006e50`
- `0x140017a50`

## pseudocode

```c
char __fastcall core::fmt::impl_12::pad_integral::write_prefix(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v7; // r14
  char v8; // al
  char v9; // dl
  char result; // al

  if ( a3 == 1114112
    || (v7 = a1, v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(a2 + 32))(a1, a3), a1 = v7, v9 = v8, result = 1, !v9) )
  {
    if ( a4 )
      return (*(__int64 (__fastcall **)(__int64, __int64, __int64))(a2 + 24))(a1, a4, a5);
    else
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140006e50  push    r14
0x140006e52  push    rsi
0x140006e53  push    rdi
0x140006e54  push    rbx
0x140006e55  sub     rsp, 28h
0x140006e59  mov     rsi, r9
0x140006e5c  mov     rbx, rdx
0x140006e5f  mov     rdi, [rsp+48h+arg_20]
0x140006e64  cmp     r8d, 110000h
0x140006e6b  jz      short loc_140006E88
0x140006e6d  mov     rax, [rbx+20h]
0x140006e71  mov     r14, rcx
0x140006e74  mov     edx, r8d
0x140006e77  call    cs:__guard_dispatch_icall_fptr
0x140006e7d  mov     rcx, r14
0x140006e80  mov     edx, eax
0x140006e82  mov     al, 1
0x140006e84  test    dl, dl
0x140006e86  jnz     short loc_140006EA9
0x140006e88  test    rsi, rsi
0x140006e8b  jz      short loc_140006EA7
0x140006e8d  mov     rax, [rbx+18h]
0x140006e91  mov     rdx, rsi
0x140006e94  mov     r8, rdi
0x140006e97  add     rsp, 28h
0x140006e9b  pop     rbx
0x140006e9c  pop     rdi
0x140006e9d  pop     rsi
0x140006e9e  pop     r14
0x140006ea0  jmp     cs:__guard_dispatch_icall_fptr
0x140006ea7  xor     eax, eax
0x140006ea9  add     rsp, 28h
0x140006ead  pop     rbx
0x140006eae  pop     rdi
0x140006eaf  pop     rsi
0x140006eb0  pop     r14
0x140006eb2  retn
```
