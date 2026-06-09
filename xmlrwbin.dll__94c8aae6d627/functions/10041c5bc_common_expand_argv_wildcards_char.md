# common_expand_argv_wildcards_char_

- ea: `0x10041c5bc`
- end: `0x10041c7fd`
- name: `common_expand_argv_wildcards_char_`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x10041cd88`

## callees

- `0x10041a610`
- `0x10041c048`
- `0x10041c06c`
- `0x10041c1a8`
- `0x10041c24c`
- `0x10041c5bc`
- `0x10041c804`
- `0x10041c990`
- `0x10041fda4`
- `0x10041ff40`

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
0x10041c5bc  mov     [rsp-38h+arg_0], rbx
0x10041c5c1  push    rbp
0x10041c5c2  push    rsi
0x10041c5c3  push    rdi
0x10041c5c4  push    r12
0x10041c5c6  push    r13
0x10041c5c8  push    r14
0x10041c5ca  push    r15
0x10041c5cc  mov     rbp, rsp
0x10041c5cf  sub     rsp, 50h
0x10041c5d3  xor     r15d, r15d
0x10041c5d6  mov     r13, rdx
0x10041c5d9  mov     rbx, rcx
0x10041c5dc  test    rdx, rdx
0x10041c5df  jnz     short loc_10041C5F8
0x10041c5e1  call    _errno
0x10041c5e6  lea     ebx, [r13+16h]
0x10041c5ea  mov     [rax], ebx
0x10041c5ec  call    _invalid_parameter_noinfo
0x10041c5f1  mov     eax, ebx
0x10041c5f3  jmp     loc_10041C7CF
0x10041c5f8  xorps   xmm0, xmm0
0x10041c5fb  mov     [rdx], r15
0x10041c5fe  mov     rax, [rcx]
0x10041c601  movdqu  xmmword ptr [rbp+Block], xmm0
0x10041c606  mov     [rbp+var_10], r15
0x10041c60a  test    rax, rax
0x10041c60d  jz      loc_10041C6B0
0x10041c613  lea     rdx, [rbp+Control]; Control
0x10041c617  mov     word ptr [rbp+Control], 3F2Ah
0x10041c61d  mov     rcx, rax; Str
0x10041c620  mov     byte ptr [rbp+Control+2], r15b
0x10041c624  call    strpbrk
0x10041c629  mov     rcx, [rbx]; char *
0x10041c62c  test    rax, rax
0x10041c62f  jnz     short loc_10041C66D
0x10041c631  lea     r9, [rbp+Block]
0x10041c635  xor     r8d, r8d; MaxCount
0x10041c638  xor     edx, edx; char *
0x10041c63a  call    copy_and_add_argument_to_buffer_char_
0x10041c63f  mov     esi, eax
0x10041c641  test    eax, eax
0x10041c643  jz      short loc_10041C67F
0x10041c645  mov     rdi, [rbp+Block]
0x10041c649  mov     rbx, rdi
0x10041c64c  cmp     rdi, [rbp+Block+8]
0x10041c650  jz      loc_10041C733
0x10041c656  mov     rcx, [rbx]; Block
0x10041c659  call    _free_base
0x10041c65e  add     rbx, 8
0x10041c662  cmp     rbx, [rbp+Block+8]
0x10041c666  jnz     short loc_10041C656
0x10041c668  jmp     loc_10041C733
0x10041c66d  lea     r8, [rbp+Block]
0x10041c671  mov     rdx, rax
0x10041c674  call    expand_argument_wildcards_char_
0x10041c679  mov     esi, eax
0x10041c67b  test    eax, eax
0x10041c67d  jnz     short loc_10041C688
0x10041c67f  add     rbx, 8
0x10041c683  mov     rax, [rbx]
0x10041c686  jmp     short loc_10041C60A
0x10041c688  mov     rdi, [rbp+Block]
0x10041c68c  mov     rbx, rdi
0x10041c68f  cmp     rdi, [rbp+Block+8]
0x10041c693  jz      loc_10041C733
0x10041c699  mov     rcx, [rbx]; Block
0x10041c69c  call    _free_base
0x10041c6a1  add     rbx, 8
0x10041c6a5  cmp     rbx, [rbp+Block+8]
0x10041c6a9  jnz     short loc_10041C699
0x10041c6ab  jmp     loc_10041C733
0x10041c6b0  mov     rdi, [rbp+Block]
0x10041c6b4  or      r12, 0FFFFFFFFFFFFFFFFh
0x10041c6b8  mov     rsi, [rbp+Block+8]
0x10041c6bc  mov     rdx, r15
0x10041c6bf  mov     r14, rsi
0x10041c6c2  mov     [rbp+arg_10], rdx
0x10041c6c6  sub     r14, rdi
0x10041c6c9  mov     rax, rdi
0x10041c6cc  sar     r14, 3
0x10041c6d0  inc     r14
0x10041c6d3  cmp     rdi, rsi
0x10041c6d6  jz      short loc_10041C6FA
0x10041c6d8  mov     r8, [rax]
0x10041c6db  mov     rcx, r12
0x10041c6de  inc     rcx
0x10041c6e1  cmp     [r8+rcx], r15b
0x10041c6e5  jnz     short loc_10041C6DE
0x10041c6e7  inc     rdx
0x10041c6ea  add     rax, 8
0x10041c6ee  add     rdx, rcx
0x10041c6f1  cmp     rax, rsi
0x10041c6f4  jnz     short loc_10041C6D8
0x10041c6f6  mov     [rbp+arg_10], rdx
0x10041c6fa  mov     r8d, 1
0x10041c700  mov     rcx, r14
0x10041c703  call    __acrt_allocate_buffer_for_argv
0x10041c708  mov     rbx, rax
0x10041c70b  test    rax, rax
0x10041c70e  jnz     short loc_10041C742
0x10041c710  xor     ecx, ecx; Block
0x10041c712  call    _free_base
0x10041c717  mov     rbx, rdi
0x10041c71a  cmp     rdi, rsi
0x10041c71d  jz      short loc_10041C730
0x10041c71f  mov     rcx, [rbx]; Block
0x10041c722  call    _free_base
0x10041c727  add     rbx, 8
0x10041c72b  cmp     rbx, rsi
0x10041c72e  jnz     short loc_10041C71F
0x10041c730  mov     esi, r12d
0x10041c733  mov     rcx, rdi; Block
0x10041c736  call    _free_base
0x10041c73b  mov     eax, esi
0x10041c73d  jmp     loc_10041C7CF
0x10041c742  lea     rcx, [rax+r14*8]
0x10041c746  mov     r14, rdi
0x10041c749  mov     [rbp+arg_18], rcx
0x10041c74d  mov     r12, rcx
0x10041c750  cmp     rdi, rsi
0x10041c753  jz      short loc_10041C7A1
0x10041c755  sub     rax, rdi
0x10041c758  mov     [rbp+Control], rax
0x10041c75c  mov     r8, [r14]; Source
0x10041c75f  or      r15, 0FFFFFFFFFFFFFFFFh
0x10041c763  inc     r15
0x10041c766  cmp     byte ptr [r8+r15], 0
0x10041c76b  jnz     short loc_10041C763
0x10041c76d  mov     rdx, rcx
0x10041c770  inc     r15
0x10041c773  sub     rdx, r12
0x10041c776  mov     r9, r15; MaxCount
0x10041c779  add     rdx, [rbp+arg_10]; SizeInBytes
0x10041c77d  mov     rcx, r12; Destination
0x10041c780  call    strncpy_s
0x10041c785  test    eax, eax
0x10041c787  jnz     short loc_10041C7E7
0x10041c789  mov     rax, [rbp+Control]
0x10041c78d  mov     rcx, [rbp+arg_18]
0x10041c791  mov     [rax+r14], r12
0x10041c795  add     r12, r15
0x10041c798  add     r14, 8
0x10041c79c  cmp     r14, rsi
0x10041c79f  jnz     short loc_10041C75C
0x10041c7a1  xor     ecx, ecx; Block
0x10041c7a3  mov     [r13+0], rbx
0x10041c7a7  call    _free_base
0x10041c7ac  mov     rbx, rdi
0x10041c7af  cmp     rdi, rsi
0x10041c7b2  jz      short loc_10041C7C5
0x10041c7b4  mov     rcx, [rbx]; Block
0x10041c7b7  call    _free_base
0x10041c7bc  add     rbx, 8
0x10041c7c0  cmp     rbx, rsi
0x10041c7c3  jnz     short loc_10041C7B4
0x10041c7c5  mov     rcx, rdi; Block
0x10041c7c8  call    _free_base
0x10041c7cd  xor     eax, eax
0x10041c7cf  mov     rbx, [rsp+50h+arg_0]
0x10041c7d7  add     rsp, 50h
0x10041c7db  pop     r15
0x10041c7dd  pop     r14
0x10041c7df  pop     r13
0x10041c7e1  pop     r12
0x10041c7e3  pop     rdi
0x10041c7e4  pop     rsi
0x10041c7e5  pop     rbp
0x10041c7e6  retn
0x10041c7e7  and     [rsp+50h+var_30], 0
0x10041c7ed  xor     r9d, r9d; LineNo
0x10041c7f0  xor     r8d, r8d; FileName
0x10041c7f3  xor     edx, edx; FunctionName
0x10041c7f5  xor     ecx, ecx; Expression
0x10041c7f7  call    _invoke_watson
```
