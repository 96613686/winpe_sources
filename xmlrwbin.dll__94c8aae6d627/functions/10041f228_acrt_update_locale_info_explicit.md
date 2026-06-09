# __acrt_update_locale_info_explicit

- ea: `0x10041f228`
- end: `0x10041f25d`
- name: `__acrt_update_locale_info_explicit`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x10041b270`

## callees

- `0x10041f228`
- `0x10041f8a0`

## pseudocode

```c
__int64 __fastcall _acrt_update_locale_info_explicit(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 result; // rax

  result = _acrt_current_locale_data[a3];
  if ( *a2 != result )
  {
    result = *(unsigned int *)(a1 + 936);
    if ( ((unsigned int)result & _globallocalestatus) == 0 )
    {
      result = _acrt_update_thread_locale_data();
      *a2 = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10041f228  push    rbx
0x10041f22a  sub     rsp, 20h
0x10041f22e  lea     rax, __acrt_current_locale_data
0x10041f235  mov     rbx, rdx
0x10041f238  mov     rax, [rax+r8*8]
0x10041f23c  cmp     [rdx], rax
0x10041f23f  jz      short loc_10041F257
0x10041f241  mov     eax, [rcx+3A8h]
0x10041f247  test    cs:__globallocalestatus, eax
0x10041f24d  jnz     short loc_10041F257
0x10041f24f  call    __acrt_update_thread_locale_data
0x10041f254  mov     [rbx], rax
0x10041f257  add     rsp, 20h
0x10041f25b  pop     rbx
0x10041f25c  retn
```
