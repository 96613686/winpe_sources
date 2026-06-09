# __acrt_update_multibyte_info_explicit

- ea: `0x10041f29c`
- end: `0x10041f2d1`
- name: `__acrt_update_multibyte_info_explicit`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x10041b270`

## callees

- `0x10041d868`
- `0x10041f29c`

## pseudocode

```c
volatile signed __int32 *__fastcall _acrt_update_multibyte_info_explicit(
        __int64 a1,
        volatile signed __int32 **a2,
        __int64 a3)
{
  volatile signed __int32 *result; // rax

  result = (volatile signed __int32 *)*(&_acrt_current_multibyte_data + a3);
  if ( *a2 != result )
  {
    result = (volatile signed __int32 *)*(unsigned int *)(a1 + 936);
    if ( ((unsigned int)result & _globallocalestatus) == 0 )
    {
      result = _acrt_update_thread_multibyte_data();
      *a2 = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10041f29c  push    rbx
0x10041f29e  sub     rsp, 20h
0x10041f2a2  lea     rax, __acrt_current_multibyte_data
0x10041f2a9  mov     rbx, rdx
0x10041f2ac  mov     rax, [rax+r8*8]
0x10041f2b0  cmp     [rdx], rax
0x10041f2b3  jz      short loc_10041F2CB
0x10041f2b5  mov     eax, [rcx+3A8h]
0x10041f2bb  test    cs:__globallocalestatus, eax
0x10041f2c1  jnz     short loc_10041F2CB
0x10041f2c3  call    __acrt_update_thread_multibyte_data
0x10041f2c8  mov     [rbx], rax
0x10041f2cb  add     rsp, 20h
0x10041f2cf  pop     rbx
0x10041f2d0  retn
```
