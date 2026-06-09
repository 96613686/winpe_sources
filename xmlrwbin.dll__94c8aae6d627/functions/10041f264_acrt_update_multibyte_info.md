# __acrt_update_multibyte_info

- ea: `0x10041f264`
- end: `0x10041f295`
- name: `__acrt_update_multibyte_info`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x10041cce4`

## callees

- `0x10041d868`
- `0x10041f264`

## pseudocode

```c
volatile signed __int32 *__fastcall _acrt_update_multibyte_info(__int64 a1, void **a2)
{
  volatile signed __int32 *result; // rax

  result = (volatile signed __int32 *)_acrt_current_multibyte_data;
  if ( *a2 != _acrt_current_multibyte_data )
  {
    result = (volatile signed __int32 *)*(unsigned int *)(a1 + 936);
    if ( ((unsigned int)result & _globallocalestatus) == 0 )
    {
      result = _acrt_update_thread_multibyte_data();
      *a2 = (void *)result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10041f264  push    rbx
0x10041f266  sub     rsp, 20h
0x10041f26a  mov     rax, cs:__acrt_current_multibyte_data
0x10041f271  mov     rbx, rdx
0x10041f274  cmp     [rdx], rax
0x10041f277  jz      short loc_10041F28F
0x10041f279  mov     eax, [rcx+3A8h]
0x10041f27f  test    cs:__globallocalestatus, eax
0x10041f285  jnz     short loc_10041F28F
0x10041f287  call    __acrt_update_thread_multibyte_data
0x10041f28c  mov     [rbx], rax
0x10041f28f  add     rsp, 20h
0x10041f293  pop     rbx
0x10041f294  retn
```
