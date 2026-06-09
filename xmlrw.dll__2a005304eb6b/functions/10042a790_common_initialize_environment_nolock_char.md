# common_initialize_environment_nolock_char_

- ea: `0x10042a790`
- end: `0x10042a803`
- name: `common_initialize_environment_nolock_char_`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x10042a9f8`

## callees

- `0x10042a790`
- `0x10042a80c`
- `0x10042e7dc`
- `0x10042fd90`
- `0x100430328`

## pseudocode

```c
__int64 common_initialize_environment_nolock_char_()
{
  unsigned int v0; // edi
  char *narrow_environment_from_os; // rax
  char *v3; // rbx
  void *environment_char; // rax

  v0 = 0;
  if ( environ_table )
    return 0;
  _acrt_initialize_multibyte();
  narrow_environment_from_os = (char *)_dcrt_get_narrow_environment_from_os();
  v3 = narrow_environment_from_os;
  if ( narrow_environment_from_os )
  {
    environment_char = create_environment_char_(narrow_environment_from_os);
    if ( environment_char )
    {
      _dcrt_initial_narrow_environment = environment_char;
      environ_table = (__int64)environment_char;
    }
    else
    {
      v0 = -1;
    }
    free_base(0);
    free_base(v3);
    return v0;
  }
  else
  {
    free_base(0);
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x10042a790  mov     [rsp+arg_0], rbx
0x10042a795  push    rdi
0x10042a796  sub     rsp, 20h
0x10042a79a  xor     edi, edi
0x10042a79c  cmp     cs:_environ_table, rdi
0x10042a7a3  jz      short loc_10042A7A9
0x10042a7a5  xor     eax, eax
0x10042a7a7  jmp     short loc_10042A7F8
0x10042a7a9  call    __acrt_initialize_multibyte
0x10042a7ae  call    __dcrt_get_narrow_environment_from_os
0x10042a7b3  mov     rbx, rax
0x10042a7b6  test    rax, rax
0x10042a7b9  jnz     short loc_10042A7C7
0x10042a7bb  xor     ecx, ecx; Block
0x10042a7bd  call    _free_base
0x10042a7c2  or      eax, 0FFFFFFFFh
0x10042a7c5  jmp     short loc_10042A7F8
0x10042a7c7  mov     rcx, rbx; Source
0x10042a7ca  call    create_environment_char_
0x10042a7cf  test    rax, rax
0x10042a7d2  jnz     short loc_10042A7D9
0x10042a7d4  or      edi, 0FFFFFFFFh
0x10042a7d7  jmp     short loc_10042A7E7
0x10042a7d9  mov     cs:__dcrt_initial_narrow_environment, rax
0x10042a7e0  mov     cs:_environ_table, rax
0x10042a7e7  xor     ecx, ecx; Block
0x10042a7e9  call    _free_base
0x10042a7ee  mov     rcx, rbx; Block
0x10042a7f1  call    _free_base
0x10042a7f6  mov     eax, edi
0x10042a7f8  mov     rbx, [rsp+28h+arg_0]
0x10042a7fd  add     rsp, 20h
0x10042a801  pop     rdi
0x10042a802  retn
```
