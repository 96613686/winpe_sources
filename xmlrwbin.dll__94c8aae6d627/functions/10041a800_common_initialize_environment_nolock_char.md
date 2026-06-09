# common_initialize_environment_nolock_char_

- ea: `0x10041a800`
- end: `0x10041a873`
- name: `common_initialize_environment_nolock_char_`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x10041aa68`

## callees

- `0x10041a800`
- `0x10041a87c`
- `0x10041c24c`
- `0x10041d800`
- `0x10041dd98`

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
0x10041a800  mov     [rsp+arg_0], rbx
0x10041a805  push    rdi
0x10041a806  sub     rsp, 20h
0x10041a80a  xor     edi, edi
0x10041a80c  cmp     cs:_environ_table, rdi
0x10041a813  jz      short loc_10041A819
0x10041a815  xor     eax, eax
0x10041a817  jmp     short loc_10041A868
0x10041a819  call    __acrt_initialize_multibyte
0x10041a81e  call    __dcrt_get_narrow_environment_from_os
0x10041a823  mov     rbx, rax
0x10041a826  test    rax, rax
0x10041a829  jnz     short loc_10041A837
0x10041a82b  xor     ecx, ecx; Block
0x10041a82d  call    _free_base
0x10041a832  or      eax, 0FFFFFFFFh
0x10041a835  jmp     short loc_10041A868
0x10041a837  mov     rcx, rbx; Source
0x10041a83a  call    create_environment_char_
0x10041a83f  test    rax, rax
0x10041a842  jnz     short loc_10041A849
0x10041a844  or      edi, 0FFFFFFFFh
0x10041a847  jmp     short loc_10041A857
0x10041a849  mov     cs:__dcrt_initial_narrow_environment, rax
0x10041a850  mov     cs:_environ_table, rax
0x10041a857  xor     ecx, ecx; Block
0x10041a859  call    _free_base
0x10041a85e  mov     rcx, rbx; Block
0x10041a861  call    _free_base
0x10041a866  mov     eax, edi
0x10041a868  mov     rbx, [rsp+28h+arg_0]
0x10041a86d  add     rsp, 20h
0x10041a871  pop     rdi
0x10041a872  retn
```
