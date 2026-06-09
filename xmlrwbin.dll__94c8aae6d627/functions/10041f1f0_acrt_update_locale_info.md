# __acrt_update_locale_info

- ea: `0x10041f1f0`
- end: `0x10041f221`
- name: `__acrt_update_locale_info`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x10041cce4`

## callees

- `0x10041f1f0`
- `0x10041f8a0`

## pseudocode

```c
__int64 __fastcall _acrt_update_locale_info(__int64 a1, __int64 *a2)
{
  __int64 result; // rax

  result = _acrt_current_locale_data;
  if ( *a2 != _acrt_current_locale_data )
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
0x10041f1f0  push    rbx
0x10041f1f2  sub     rsp, 20h
0x10041f1f6  mov     rax, cs:__acrt_current_locale_data
0x10041f1fd  mov     rbx, rdx
0x10041f200  cmp     [rdx], rax
0x10041f203  jz      short loc_10041F21B
0x10041f205  mov     eax, [rcx+3A8h]
0x10041f20b  test    cs:__globallocalestatus, eax
0x10041f211  jnz     short loc_10041F21B
0x10041f213  call    __acrt_update_thread_locale_data
0x10041f218  mov     [rbx], rax
0x10041f21b  add     rsp, 20h
0x10041f21f  pop     rbx
0x10041f220  retn
```
