# _configure_narrow_argv

- ea: `0x10041a674`
- end: `0x10041a7fa`
- name: `_configure_narrow_argv`
- size: `390`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100416d64`

## callees

- `0x10041a444`
- `0x10041a610`
- `0x10041a674`
- `0x10041c048`
- `0x10041c1a8`
- `0x10041c24c`
- `0x10041cd88`
- `0x10041ceb4`
- `0x10041d800`

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
      _acrt_GetModuleFileNameA(0, qword_100435450, 260);
      LODWORD(v4) = (_DWORD)acmdln;
      pgmptr = (char *)qword_100435450;
      if ( !acmdln || !*acmdln )
        v4 = qword_100435450;
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
0x10041a674  mov     [rsp-28h+arg_0], rbx
0x10041a679  push    rbp
0x10041a67a  push    rsi
0x10041a67b  push    rdi
0x10041a67c  push    r14
0x10041a67e  push    r15
0x10041a680  mov     rbp, rsp
0x10041a683  sub     rsp, 30h
0x10041a687  xor     edi, edi
0x10041a689  mov     r14d, ecx
0x10041a68c  test    ecx, ecx
0x10041a68e  jz      loc_10041A7E7
0x10041a694  lea     eax, [rcx-1]
0x10041a697  cmp     eax, 1
0x10041a69a  jbe     short loc_10041A6B2
0x10041a69c  call    _errno
0x10041a6a1  lea     ebx, [rdi+16h]
0x10041a6a4  mov     [rax], ebx
0x10041a6a6  call    _invalid_parameter_noinfo
0x10041a6ab  mov     edi, ebx
0x10041a6ad  jmp     loc_10041A7E7
0x10041a6b2  call    __acrt_initialize_multibyte
0x10041a6b7  lea     rbx, qword_100435450
0x10041a6be  mov     r8d, 104h
0x10041a6c4  mov     rdx, rbx
0x10041a6c7  xor     ecx, ecx
0x10041a6c9  call    __acrt_GetModuleFileNameA
0x10041a6ce  mov     rsi, cs:_acmdln
0x10041a6d5  mov     cs:_pgmptr, rbx
0x10041a6dc  test    rsi, rsi
0x10041a6df  jz      short loc_10041A6E6
0x10041a6e1  cmp     [rsi], dil
0x10041a6e4  jnz     short loc_10041A6E9
0x10041a6e6  mov     rsi, rbx
0x10041a6e9  lea     rax, [rbp+arg_18]
0x10041a6ed  mov     [rbp+arg_10], rdi
0x10041a6f1  lea     r9, [rbp+arg_10]
0x10041a6f5  mov     [rsp+30h+var_10], rax
0x10041a6fa  xor     r8d, r8d
0x10041a6fd  mov     [rbp+arg_18], rdi
0x10041a701  xor     edx, edx
0x10041a703  mov     rcx, rsi
0x10041a706  call    parse_command_line_char_
0x10041a70b  mov     r15, [rbp+arg_10]
0x10041a70f  mov     r8d, 1
0x10041a715  mov     rdx, [rbp+arg_18]
0x10041a719  mov     rcx, r15
0x10041a71c  call    __acrt_allocate_buffer_for_argv
0x10041a721  mov     rbx, rax
0x10041a724  test    rax, rax
0x10041a727  jnz     short loc_10041A741
0x10041a729  call    _errno
0x10041a72e  mov     ebx, 0Ch
0x10041a733  xor     ecx, ecx; Block
0x10041a735  mov     [rax], ebx
0x10041a737  call    _free_base
0x10041a73c  jmp     loc_10041A6AB
0x10041a741  lea     r8, [rax+r15*8]
0x10041a745  mov     rdx, rbx
0x10041a748  lea     rax, [rbp+arg_18]
0x10041a74c  mov     rcx, rsi
0x10041a74f  lea     r9, [rbp+arg_10]
0x10041a753  mov     [rsp+30h+var_10], rax
0x10041a758  call    parse_command_line_char_
0x10041a75d  cmp     r14d, 1
0x10041a761  jnz     short loc_10041A779
0x10041a763  mov     eax, dword ptr [rbp+arg_10]
0x10041a766  dec     eax
0x10041a768  mov     cs:__argv, rbx
0x10041a76f  mov     cs:__argc, eax
0x10041a775  xor     ecx, ecx
0x10041a777  jmp     short loc_10041A7E2
0x10041a779  lea     rdx, [rbp+Block]
0x10041a77d  mov     [rbp+Block], rdi
0x10041a781  mov     rcx, rbx
0x10041a784  call    __acrt_expand_narrow_argv_wildcards
0x10041a789  mov     esi, eax
0x10041a78b  test    eax, eax
0x10041a78d  jz      short loc_10041A7A8
0x10041a78f  mov     rcx, [rbp+Block]; Block
0x10041a793  call    _free_base
0x10041a798  mov     rcx, rbx; Block
0x10041a79b  mov     [rbp+Block], rdi
0x10041a79f  call    _free_base
0x10041a7a4  mov     edi, esi
0x10041a7a6  jmp     short loc_10041A7E7
0x10041a7a8  mov     rdx, [rbp+Block]
0x10041a7ac  mov     rcx, rdi
0x10041a7af  mov     rax, rdx
0x10041a7b2  cmp     [rdx], rdi
0x10041a7b5  jz      short loc_10041A7C3
0x10041a7b7  lea     rax, [rax+8]
0x10041a7bb  inc     rcx
0x10041a7be  cmp     [rax], rdi
0x10041a7c1  jnz     short loc_10041A7B7
0x10041a7c3  mov     cs:__argc, ecx
0x10041a7c9  xor     ecx, ecx; Block
0x10041a7cb  mov     [rbp+Block], rdi
0x10041a7cf  mov     cs:__argv, rdx
0x10041a7d6  call    _free_base
0x10041a7db  mov     rcx, rbx; Block
0x10041a7de  mov     [rbp+Block], rdi
0x10041a7e2  call    _free_base
0x10041a7e7  mov     rbx, [rsp+30h+arg_0]
0x10041a7ec  mov     eax, edi
0x10041a7ee  add     rsp, 30h
0x10041a7f2  pop     r15
0x10041a7f4  pop     r14
0x10041a7f6  pop     rdi
0x10041a7f7  pop     rsi
0x10041a7f8  pop     rbp
0x10041a7f9  retn
```
