# _configure_narrow_argv

- ea: `0x10042a604`
- end: `0x10042a78a`
- name: `_configure_narrow_argv`
- size: `390`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100426d44`

## callees

- `0x10042a3d4`
- `0x10042a5a0`
- `0x10042a604`
- `0x10042e5d8`
- `0x10042e738`
- `0x10042e7dc`
- `0x10042f318`
- `0x10042f444`
- `0x10042fd90`

## pseudocode

```c
errno_t __cdecl configure_narrow_argv(_crt_argv_mode mode)
{
  errno_t v1; // edi
  errno_t v3; // ebx
  __int64 *v4; // rsi
  int v5; // r15d
  __int64 buffer_for_argv; // rax
  char **v7; // rbx
  char **v8; // rcx
  errno_t v9; // esi
  char **v10; // rdx
  int v11; // ecx
  _QWORD *i; // rax
  void *Block; // [rsp+68h] [rbp+38h] BYREF
  __int64 v15; // [rsp+70h] [rbp+40h] BYREF
  __int64 v16; // [rsp+78h] [rbp+48h] BYREF

  v1 = 0;
  if ( mode )
  {
    if ( (unsigned int)(mode - 1) <= 1 )
    {
      _acrt_initialize_multibyte();
      _acrt_GetModuleFileNameA(0, qword_1004513C0, 260);
      LODWORD(v4) = (_DWORD)acmdln;
      pgmptr = (char *)qword_1004513C0;
      if ( !acmdln || !*acmdln )
        v4 = qword_1004513C0;
      v15 = 0;
      v16 = 0;
      parse_command_line_char_((_DWORD)v4, 0, 0, (unsigned int)&v15, (__int64)&v16);
      v5 = v15;
      buffer_for_argv = _acrt_allocate_buffer_for_argv(v15, v16, 1);
      v7 = (char **)buffer_for_argv;
      if ( buffer_for_argv )
      {
        parse_command_line_char_(
          (_DWORD)v4,
          buffer_for_argv,
          buffer_for_argv + 8 * v5,
          (unsigned int)&v15,
          (__int64)&v16);
        if ( mode == _crt_argv_unexpanded_arguments )
        {
          _argv = v7;
          _argc = v15 - 1;
          v8 = 0;
        }
        else
        {
          Block = 0;
          v9 = _acrt_expand_narrow_argv_wildcards(v7, &Block);
          if ( v9 )
          {
            free_base(Block);
            Block = 0;
            free_base(v7);
            return v9;
          }
          v10 = (char **)Block;
          v11 = 0;
          for ( i = Block; *i; ++v11 )
            ++i;
          _argc = v11;
          Block = 0;
          _argv = v10;
          free_base(0);
          v8 = v7;
          Block = 0;
        }
        free_base(v8);
        return v1;
      }
      v3 = 12;
      *errno() = 12;
      free_base(0);
    }
    else
    {
      v3 = 22;
      *errno() = 22;
      invalid_parameter_noinfo();
    }
    return v3;
  }
  return v1;
}

```

## disassembly

```asm
0x10042a604  mov     [rsp-28h+arg_0], rbx
0x10042a609  push    rbp
0x10042a60a  push    rsi
0x10042a60b  push    rdi
0x10042a60c  push    r14
0x10042a60e  push    r15
0x10042a610  mov     rbp, rsp
0x10042a613  sub     rsp, 30h
0x10042a617  xor     edi, edi
0x10042a619  mov     r14d, ecx
0x10042a61c  test    ecx, ecx
0x10042a61e  jz      loc_10042A777
0x10042a624  lea     eax, [rcx-1]
0x10042a627  cmp     eax, 1
0x10042a62a  jbe     short loc_10042A642
0x10042a62c  call    _errno
0x10042a631  lea     ebx, [rdi+16h]
0x10042a634  mov     [rax], ebx
0x10042a636  call    _invalid_parameter_noinfo
0x10042a63b  mov     edi, ebx
0x10042a63d  jmp     loc_10042A777
0x10042a642  call    __acrt_initialize_multibyte
0x10042a647  lea     rbx, qword_1004513C0
0x10042a64e  mov     r8d, 104h
0x10042a654  mov     rdx, rbx
0x10042a657  xor     ecx, ecx
0x10042a659  call    __acrt_GetModuleFileNameA
0x10042a65e  mov     rsi, cs:_acmdln
0x10042a665  mov     cs:_pgmptr, rbx
0x10042a66c  test    rsi, rsi
0x10042a66f  jz      short loc_10042A676
0x10042a671  cmp     [rsi], dil
0x10042a674  jnz     short loc_10042A679
0x10042a676  mov     rsi, rbx
0x10042a679  lea     rax, [rbp+arg_18]
0x10042a67d  mov     [rbp+arg_10], rdi
0x10042a681  lea     r9, [rbp+arg_10]
0x10042a685  mov     [rsp+30h+var_10], rax
0x10042a68a  xor     r8d, r8d
0x10042a68d  mov     [rbp+arg_18], rdi
0x10042a691  xor     edx, edx
0x10042a693  mov     rcx, rsi
0x10042a696  call    parse_command_line_char_
0x10042a69b  mov     r15, [rbp+arg_10]
0x10042a69f  mov     r8d, 1
0x10042a6a5  mov     rdx, [rbp+arg_18]
0x10042a6a9  mov     rcx, r15
0x10042a6ac  call    __acrt_allocate_buffer_for_argv
0x10042a6b1  mov     rbx, rax
0x10042a6b4  test    rax, rax
0x10042a6b7  jnz     short loc_10042A6D1
0x10042a6b9  call    _errno
0x10042a6be  mov     ebx, 0Ch
0x10042a6c3  xor     ecx, ecx; Block
0x10042a6c5  mov     [rax], ebx
0x10042a6c7  call    _free_base
0x10042a6cc  jmp     loc_10042A63B
0x10042a6d1  lea     r8, [rax+r15*8]
0x10042a6d5  mov     rdx, rbx
0x10042a6d8  lea     rax, [rbp+arg_18]
0x10042a6dc  mov     rcx, rsi
0x10042a6df  lea     r9, [rbp+arg_10]
0x10042a6e3  mov     [rsp+30h+var_10], rax
0x10042a6e8  call    parse_command_line_char_
0x10042a6ed  cmp     r14d, 1
0x10042a6f1  jnz     short loc_10042A709
0x10042a6f3  mov     eax, dword ptr [rbp+arg_10]
0x10042a6f6  dec     eax
0x10042a6f8  mov     cs:__argv, rbx
0x10042a6ff  mov     cs:__argc, eax
0x10042a705  xor     ecx, ecx
0x10042a707  jmp     short loc_10042A772
0x10042a709  lea     rdx, [rbp+Block]
0x10042a70d  mov     [rbp+Block], rdi
0x10042a711  mov     rcx, rbx
0x10042a714  call    __acrt_expand_narrow_argv_wildcards
0x10042a719  mov     esi, eax
0x10042a71b  test    eax, eax
0x10042a71d  jz      short loc_10042A738
0x10042a71f  mov     rcx, [rbp+Block]; Block
0x10042a723  call    _free_base
0x10042a728  mov     rcx, rbx; Block
0x10042a72b  mov     [rbp+Block], rdi
0x10042a72f  call    _free_base
0x10042a734  mov     edi, esi
0x10042a736  jmp     short loc_10042A777
0x10042a738  mov     rdx, [rbp+Block]
0x10042a73c  mov     rcx, rdi
0x10042a73f  mov     rax, rdx
0x10042a742  cmp     [rdx], rdi
0x10042a745  jz      short loc_10042A753
0x10042a747  lea     rax, [rax+8]
0x10042a74b  inc     rcx
0x10042a74e  cmp     [rax], rdi
0x10042a751  jnz     short loc_10042A747
0x10042a753  mov     cs:__argc, ecx
0x10042a759  xor     ecx, ecx; Block
0x10042a75b  mov     [rbp+Block], rdi
0x10042a75f  mov     cs:__argv, rdx
0x10042a766  call    _free_base
0x10042a76b  mov     rcx, rbx; Block
0x10042a76e  mov     [rbp+Block], rdi
0x10042a772  call    _free_base
0x10042a777  mov     rbx, [rsp+30h+arg_0]
0x10042a77c  mov     eax, edi
0x10042a77e  add     rsp, 30h
0x10042a782  pop     r15
0x10042a784  pop     r14
0x10042a786  pop     rdi
0x10042a787  pop     rsi
0x10042a788  pop     rbp
0x10042a789  retn
```
