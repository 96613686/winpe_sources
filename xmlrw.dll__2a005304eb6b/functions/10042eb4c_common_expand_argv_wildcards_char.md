# common_expand_argv_wildcards_char_

- ea: `0x10042eb4c`
- end: `0x10042ed8d`
- name: `common_expand_argv_wildcards_char_`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x10042f318`

## callees

- `0x10042a5a0`
- `0x10042e5d8`
- `0x10042e5fc`
- `0x10042e738`
- `0x10042e7dc`
- `0x10042eb4c`
- `0x10042ed94`
- `0x10042ef20`
- `0x100433354`
- `0x1004334f0`

## pseudocode

```c
__int64 __fastcall common_expand_argv_wildcards_char_(const char **a1, __int64 *a2)
{
  const char **v3; // rbx
  const char *i; // rax
  char *v6; // rax
  char *v7; // rcx
  unsigned int v8; // esi
  __int64 buffer_for_argv; // rax
  __int64 v10; // rcx
  __int64 Control; // [rsp+98h] [rbp+48h] BYREF
  __int64 v12; // [rsp+A0h] [rbp+50h]
  __int64 v13; // [rsp+A8h] [rbp+58h]

  v3 = a1;
  if ( a2 )
  {
    *a2 = 0;
    for ( i = *a1; i; i = *v3 )
    {
      strcpy((char *)&Control, "*?");
      v6 = strpbrk(i, (const char *)&Control);
      v7 = (char *)*v3;
      if ( v6 )
      {
        v8 = expand_argument_wildcards_char_(v7);
        if ( v8 )
          goto LABEL_13;
      }
      else
      {
        v8 = copy_and_add_argument_to_buffer_char_(v7, 0, 0);
        if ( v8 )
          goto LABEL_13;
      }
      ++v3;
    }
    v12 = 0;
    buffer_for_argv = _acrt_allocate_buffer_for_argv(1, 0, 1);
    if ( !buffer_for_argv )
    {
      free_base(0);
      v8 = -1;
LABEL_13:
      free_base(0);
      return v8;
    }
    v10 = buffer_for_argv + 8;
    v13 = v10;
    *a2 = buffer_for_argv;
    free_base(0);
    free_base(0);
    return 0;
  }
  else
  {
    *errno() = 22;
    invalid_parameter_noinfo();
    return 22;
  }
}

```

## disassembly

```asm
0x10042eb4c  mov     [rsp-38h+arg_0], rbx
0x10042eb51  push    rbp
0x10042eb52  push    rsi
0x10042eb53  push    rdi
0x10042eb54  push    r12
0x10042eb56  push    r13
0x10042eb58  push    r14
0x10042eb5a  push    r15
0x10042eb5c  mov     rbp, rsp
0x10042eb5f  sub     rsp, 50h
0x10042eb63  xor     r15d, r15d
0x10042eb66  mov     r13, rdx
0x10042eb69  mov     rbx, rcx
0x10042eb6c  test    rdx, rdx
0x10042eb6f  jnz     short loc_10042EB88
0x10042eb71  call    _errno
0x10042eb76  lea     ebx, [r13+16h]
0x10042eb7a  mov     [rax], ebx
0x10042eb7c  call    _invalid_parameter_noinfo
0x10042eb81  mov     eax, ebx
0x10042eb83  jmp     loc_10042ED5F
0x10042eb88  xorps   xmm0, xmm0
0x10042eb8b  mov     [rdx], r15
0x10042eb8e  mov     rax, [rcx]
0x10042eb91  movdqu  xmmword ptr [rbp+Block], xmm0
0x10042eb96  mov     [rbp+var_10], r15
0x10042eb9a  test    rax, rax
0x10042eb9d  jz      loc_10042EC40
0x10042eba3  lea     rdx, [rbp+Control]; Control
0x10042eba7  mov     word ptr [rbp+Control], 3F2Ah
0x10042ebad  mov     rcx, rax; Str
0x10042ebb0  mov     byte ptr [rbp+Control+2], r15b
0x10042ebb4  call    strpbrk
0x10042ebb9  mov     rcx, [rbx]; char *
0x10042ebbc  test    rax, rax
0x10042ebbf  jnz     short loc_10042EBFD
0x10042ebc1  lea     r9, [rbp+Block]
0x10042ebc5  xor     r8d, r8d; MaxCount
0x10042ebc8  xor     edx, edx; char *
0x10042ebca  call    copy_and_add_argument_to_buffer_char_
0x10042ebcf  mov     esi, eax
0x10042ebd1  test    eax, eax
0x10042ebd3  jz      short loc_10042EC0F
0x10042ebd5  mov     rdi, [rbp+Block]
0x10042ebd9  mov     rbx, rdi
0x10042ebdc  cmp     rdi, [rbp+Block+8]
0x10042ebe0  jz      loc_10042ECC3
0x10042ebe6  mov     rcx, [rbx]; Block
0x10042ebe9  call    _free_base
0x10042ebee  add     rbx, 8
0x10042ebf2  cmp     rbx, [rbp+Block+8]
0x10042ebf6  jnz     short loc_10042EBE6
0x10042ebf8  jmp     loc_10042ECC3
0x10042ebfd  lea     r8, [rbp+Block]
0x10042ec01  mov     rdx, rax
0x10042ec04  call    expand_argument_wildcards_char_
0x10042ec09  mov     esi, eax
0x10042ec0b  test    eax, eax
0x10042ec0d  jnz     short loc_10042EC18
0x10042ec0f  add     rbx, 8
0x10042ec13  mov     rax, [rbx]
0x10042ec16  jmp     short loc_10042EB9A
0x10042ec18  mov     rdi, [rbp+Block]
0x10042ec1c  mov     rbx, rdi
0x10042ec1f  cmp     rdi, [rbp+Block+8]
0x10042ec23  jz      loc_10042ECC3
0x10042ec29  mov     rcx, [rbx]; Block
0x10042ec2c  call    _free_base
0x10042ec31  add     rbx, 8
0x10042ec35  cmp     rbx, [rbp+Block+8]
0x10042ec39  jnz     short loc_10042EC29
0x10042ec3b  jmp     loc_10042ECC3
0x10042ec40  mov     rdi, [rbp+Block]
0x10042ec44  or      r12, 0FFFFFFFFFFFFFFFFh
0x10042ec48  mov     rsi, [rbp+Block+8]
0x10042ec4c  mov     rdx, r15
0x10042ec4f  mov     r14, rsi
0x10042ec52  mov     [rbp+arg_10], rdx
0x10042ec56  sub     r14, rdi
0x10042ec59  mov     rax, rdi
0x10042ec5c  sar     r14, 3
0x10042ec60  inc     r14
0x10042ec63  cmp     rdi, rsi
0x10042ec66  jz      short loc_10042EC8A
0x10042ec68  mov     r8, [rax]
0x10042ec6b  mov     rcx, r12
0x10042ec6e  inc     rcx
0x10042ec71  cmp     [r8+rcx], r15b
0x10042ec75  jnz     short loc_10042EC6E
0x10042ec77  inc     rdx
0x10042ec7a  add     rax, 8
0x10042ec7e  add     rdx, rcx
0x10042ec81  cmp     rax, rsi
0x10042ec84  jnz     short loc_10042EC68
0x10042ec86  mov     [rbp+arg_10], rdx
0x10042ec8a  mov     r8d, 1
0x10042ec90  mov     rcx, r14
0x10042ec93  call    __acrt_allocate_buffer_for_argv
0x10042ec98  mov     rbx, rax
0x10042ec9b  test    rax, rax
0x10042ec9e  jnz     short loc_10042ECD2
0x10042eca0  xor     ecx, ecx; Block
0x10042eca2  call    _free_base
0x10042eca7  mov     rbx, rdi
0x10042ecaa  cmp     rdi, rsi
0x10042ecad  jz      short loc_10042ECC0
0x10042ecaf  mov     rcx, [rbx]; Block
0x10042ecb2  call    _free_base
0x10042ecb7  add     rbx, 8
0x10042ecbb  cmp     rbx, rsi
0x10042ecbe  jnz     short loc_10042ECAF
0x10042ecc0  mov     esi, r12d
0x10042ecc3  mov     rcx, rdi; Block
0x10042ecc6  call    _free_base
0x10042eccb  mov     eax, esi
0x10042eccd  jmp     loc_10042ED5F
0x10042ecd2  lea     rcx, [rax+r14*8]
0x10042ecd6  mov     r14, rdi
0x10042ecd9  mov     [rbp+arg_18], rcx
0x10042ecdd  mov     r12, rcx
0x10042ece0  cmp     rdi, rsi
0x10042ece3  jz      short loc_10042ED31
0x10042ece5  sub     rax, rdi
0x10042ece8  mov     [rbp+Control], rax
0x10042ecec  mov     r8, [r14]; Source
0x10042ecef  or      r15, 0FFFFFFFFFFFFFFFFh
0x10042ecf3  inc     r15
0x10042ecf6  cmp     byte ptr [r8+r15], 0
0x10042ecfb  jnz     short loc_10042ECF3
0x10042ecfd  mov     rdx, rcx
0x10042ed00  inc     r15
0x10042ed03  sub     rdx, r12
0x10042ed06  mov     r9, r15; MaxCount
0x10042ed09  add     rdx, [rbp+arg_10]; SizeInBytes
0x10042ed0d  mov     rcx, r12; Destination
0x10042ed10  call    strncpy_s
0x10042ed15  test    eax, eax
0x10042ed17  jnz     short loc_10042ED77
0x10042ed19  mov     rax, [rbp+Control]
0x10042ed1d  mov     rcx, [rbp+arg_18]
0x10042ed21  mov     [rax+r14], r12
0x10042ed25  add     r12, r15
0x10042ed28  add     r14, 8
0x10042ed2c  cmp     r14, rsi
0x10042ed2f  jnz     short loc_10042ECEC
0x10042ed31  xor     ecx, ecx; Block
0x10042ed33  mov     [r13+0], rbx
0x10042ed37  call    _free_base
0x10042ed3c  mov     rbx, rdi
0x10042ed3f  cmp     rdi, rsi
0x10042ed42  jz      short loc_10042ED55
0x10042ed44  mov     rcx, [rbx]; Block
0x10042ed47  call    _free_base
0x10042ed4c  add     rbx, 8
0x10042ed50  cmp     rbx, rsi
0x10042ed53  jnz     short loc_10042ED44
0x10042ed55  mov     rcx, rdi; Block
0x10042ed58  call    _free_base
0x10042ed5d  xor     eax, eax
0x10042ed5f  mov     rbx, [rsp+50h+arg_0]
0x10042ed67  add     rsp, 50h
0x10042ed6b  pop     r15
0x10042ed6d  pop     r14
0x10042ed6f  pop     r13
0x10042ed71  pop     r12
0x10042ed73  pop     rdi
0x10042ed74  pop     rsi
0x10042ed75  pop     rbp
0x10042ed76  retn
0x10042ed77  and     [rsp+50h+var_30], 0
0x10042ed7d  xor     r9d, r9d; LineNo
0x10042ed80  xor     r8d, r8d; FileName
0x10042ed83  xor     edx, edx; FunctionName
0x10042ed85  xor     ecx, ecx; Expression
0x10042ed87  call    _invoke_watson
```
