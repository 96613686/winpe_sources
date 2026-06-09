# _RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter25debug_tuple_field1_finish

- ea: `0x140005d80`
- end: `0x140005f34`
- name: `_RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter25debug_tuple_field1_finish`
- size: `436`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000f450`
- `0x14000fb30`
- `0x140013200`

## callees

- `0x140005d80`
- `0x140017a10`
- `0x140017a50`

## pseudocode

```c
__int64 __fastcall RNvMsa_NtCs9MWeMO1rkJG_4core3fmtNtB5_9Formatter25debug_tuple_field1_finish(
        char *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  unsigned int v5; // ebx
  __int64 v9; // r15
  __int64 v10; // rbp
  unsigned __int8 (__fastcall *v11)(__int64, char *, __int64); // r12
  __int64 v13; // [rsp+0h] [rbp-A8h] BYREF
  char v14; // [rsp+2Fh] [rbp-79h] BYREF
  _QWORD v15[3]; // [rsp+30h] [rbp-78h] BYREF
  _QWORD *v16; // [rsp+48h] [rbp-60h] BYREF
  __int64 *v17; // [rsp+50h] [rbp-58h]
  __int64 v18; // [rsp+58h] [rbp-50h]
  __int64 v19; // [rsp+60h] [rbp-48h]

  v9 = *(_QWORD *)a1;
  v10 = *((_QWORD *)a1 + 1);
  v11 = *(unsigned __int8 (__fastcall **)(__int64, char *, __int64))(v10 + 24);
  LOBYTE(v5) = 1;
  if ( !((unsigned __int8 (__fastcall *)(_QWORD))v11)(*(_QWORD *)a1) )
  {
    if ( a1[18] < 0 )
    {
      if ( v11(v9, byte_14001C8A1, 2) )
        goto LABEL_2;
      v14 = 1;
      v15[0] = v9;
      v15[1] = v10;
      v15[2] = &v14;
      v18 = *((_QWORD *)a1 + 2);
      v16 = v15;
      v17 = &qword_14001B188;
      if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD **))(a5 + 24))(a4, &v16)
        || ((unsigned __int8 (__fastcall *)(_QWORD *, __int16 *, __int64))v17[3])(v16, &word_14001C89E, 2) )
      {
        goto LABEL_2;
      }
    }
    else if ( v11(v9, &byte_14001C8A0, 1) || (*(unsigned __int8 (__fastcall **)(__int64, char *))(a5 + 24))(a4, a1) )
    {
      goto LABEL_2;
    }
    if ( a3
      || a1[18] < 0
      || !(*(unsigned __int8 (__fastcall **)(_QWORD, char *, __int64))(*((_QWORD *)a1 + 1) + 24LL))(
            *(_QWORD *)a1,
            &byte_14001C8A5,
            1) )
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64))(*((_QWORD *)a1 + 1) + 24LL))(
             *(_QWORD *)a1,
             &byte_14001C8A4,
             1);
    }
  }
LABEL_2:
  if ( _security_cookie != ((unsigned __int64)&v13 ^ v19) )
    JUMPOUT(0x140005F33LL);
  return v5;
}

```

## disassembly

```asm
0x140005d80  push    r15
0x140005d82  push    r14
0x140005d84  push    r13
0x140005d86  push    r12
0x140005d88  push    rsi
0x140005d89  push    rdi
0x140005d8a  push    rbp
0x140005d8b  push    rbx
0x140005d8c  sub     rsp, 68h
0x140005d90  mov     r14, r9
0x140005d93  mov     rdi, r8
0x140005d96  mov     rsi, rcx
0x140005d99  mov     rax, cs:__security_cookie
0x140005da0  xor     rax, rsp
0x140005da3  mov     [rsp+0A8h+var_48], rax
0x140005da8  mov     r15, [rcx]
0x140005dab  mov     rbp, [rcx+8]
0x140005daf  mov     r12, [rbp+18h]
0x140005db3  mov     rcx, r15
0x140005db6  mov     rax, r12
0x140005db9  call    cs:__guard_dispatch_icall_fptr
0x140005dbf  mov     bl, 1
0x140005dc1  test    al, al
0x140005dc3  jz      short loc_140005DF0
0x140005dc5  mov     rax, [rsp+0A8h+var_48]
0x140005dca  xor     rax, rsp
0x140005dcd  mov     rcx, cs:__security_cookie
0x140005dd4  cmp     rcx, rax
0x140005dd7  jnz     loc_140005F26
0x140005ddd  mov     eax, ebx
0x140005ddf  add     rsp, 68h
0x140005de3  pop     rbx
0x140005de4  pop     rbp
0x140005de5  pop     rdi
0x140005de6  pop     rsi
0x140005de7  pop     r12
0x140005de9  pop     r13
0x140005deb  pop     r14
0x140005ded  pop     r15
0x140005def  retn
0x140005df0  mov     r13, [rsp+0A8h+arg_20]
0x140005df8  test    byte ptr [rsi+12h], 80h
0x140005dfc  jnz     short loc_140005E34
0x140005dfe  lea     rdx, byte_14001C8A0
0x140005e05  mov     r8d, 1
0x140005e0b  mov     rcx, r15
0x140005e0e  mov     rax, r12
0x140005e11  call    cs:__guard_dispatch_icall_fptr
0x140005e17  test    al, al
0x140005e19  jnz     short loc_140005DC5
0x140005e1b  mov     rax, [r13+18h]
0x140005e1f  mov     rcx, r14
0x140005e22  mov     rdx, rsi
0x140005e25  call    cs:__guard_dispatch_icall_fptr
0x140005e2b  test    al, al
0x140005e2d  jnz     short loc_140005DC5
0x140005e2f  jmp     loc_140005ED0
0x140005e34  lea     rdx, byte_14001C8A1
0x140005e3b  mov     r8d, 2
0x140005e41  mov     rcx, r15
0x140005e44  mov     rax, r12
0x140005e47  call    cs:__guard_dispatch_icall_fptr
0x140005e4d  test    al, al
0x140005e4f  jnz     loc_140005DC5
0x140005e55  mov     [rsp+0A8h+var_79], 1
0x140005e5a  mov     [rsp+0A8h+var_78], r15
0x140005e5f  mov     [rsp+0A8h+var_70], rbp
0x140005e64  lea     rax, [rsp+0A8h+var_79]
0x140005e69  mov     [rsp+0A8h+var_68], rax
0x140005e6e  mov     rax, [rsi+10h]
0x140005e72  mov     [rsp+0A8h+var_50], rax
0x140005e77  lea     rax, [rsp+0A8h+var_78]
0x140005e7c  mov     [rsp+0A8h+var_60], rax
0x140005e81  lea     rax, qword_14001B188
0x140005e88  mov     [rsp+0A8h+var_58], rax
0x140005e8d  mov     rax, [r13+18h]
0x140005e91  lea     rdx, [rsp+0A8h+var_60]
0x140005e96  mov     rcx, r14
0x140005e99  call    cs:__guard_dispatch_icall_fptr
0x140005e9f  test    al, al
0x140005ea1  jnz     loc_140005DC5
0x140005ea7  mov     rcx, [rsp+0A8h+var_60]
0x140005eac  mov     rax, [rsp+0A8h+var_58]
0x140005eb1  mov     rax, [rax+18h]
0x140005eb5  lea     rdx, word_14001C89E
0x140005ebc  mov     r8d, 2
0x140005ec2  call    cs:__guard_dispatch_icall_fptr
0x140005ec8  test    al, al
0x140005eca  jnz     loc_140005DC5
0x140005ed0  test    rdi, rdi
0x140005ed3  jnz     short loc_140005F01
0x140005ed5  test    byte ptr [rsi+12h], 80h
0x140005ed9  jnz     short loc_140005F01
0x140005edb  mov     rcx, [rsi]
0x140005ede  mov     rax, [rsi+8]
0x140005ee2  mov     rax, [rax+18h]
0x140005ee6  lea     rdx, byte_14001C8A5
0x140005eed  mov     r8d, 1
0x140005ef3  call    cs:__guard_dispatch_icall_fptr
0x140005ef9  test    al, al
0x140005efb  jnz     loc_140005DC5
0x140005f01  mov     rcx, [rsi]
0x140005f04  mov     rax, [rsi+8]
0x140005f08  mov     rax, [rax+18h]
0x140005f0c  lea     rdx, byte_14001C8A4
0x140005f13  mov     r8d, 1
0x140005f19  call    cs:__guard_dispatch_icall_fptr
0x140005f1f  mov     ebx, eax
0x140005f21  jmp     loc_140005DC5
0x140005f26  mov     rcx, [rsp+0A8h+var_48]
0x140005f2b  xor     rcx, rsp; StackCookie
0x140005f2e  call    __security_check_cookie
```
