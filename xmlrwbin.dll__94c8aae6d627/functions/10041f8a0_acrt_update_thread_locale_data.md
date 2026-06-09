# __acrt_update_thread_locale_data

- ea: `0x10041f8a0`
- end: `0x10041f90e`
- name: `__acrt_update_thread_locale_data`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x10041f1f0`
- `0x10041f228`

## callees

- `0x10041b1a4`
- `0x10041b7bc`
- `0x10041bba0`
- `0x10041bc00`
- `0x10041f8a0`
- `0x10041f914`

## pseudocode

```c
__int64 _acrt_update_thread_locale_data()
{
  __int64 v0; // rax
  __int64 *v1; // rdi
  __int64 v2; // rbx

  v0 = _acrt_getptd();
  v1 = (__int64 *)(v0 + 144);
  if ( (*(_DWORD *)(v0 + 936) & _globallocalestatus) == 0 || (v2 = *v1) == 0 )
  {
    _acrt_lock(4);
    v2 = updatetlocinfoEx_nolock(v1, _acrt_current_locale_data);
    _acrt_unlock(4);
    if ( !v2 )
      abort();
  }
  return v2;
}

```

## disassembly

```asm
0x10041f8a0  mov     [rsp+arg_0], rbx
0x10041f8a5  push    rdi
0x10041f8a6  sub     rsp, 20h
0x10041f8aa  call    __acrt_getptd
0x10041f8af  lea     rdi, [rax+90h]
0x10041f8b6  mov     ecx, [rax+3A8h]
0x10041f8bc  mov     eax, cs:__globallocalestatus
0x10041f8c2  test    eax, ecx
0x10041f8c4  jz      short loc_10041F8CE
0x10041f8c6  mov     rbx, [rdi]
0x10041f8c9  test    rbx, rbx
0x10041f8cc  jnz     short loc_10041F8FA
0x10041f8ce  mov     ecx, 4
0x10041f8d3  call    __acrt_lock
0x10041f8d8  nop
0x10041f8d9  mov     rdx, cs:__acrt_current_locale_data
0x10041f8e0  mov     rcx, rdi
0x10041f8e3  call    _updatetlocinfoEx_nolock
0x10041f8e8  mov     rbx, rax
0x10041f8eb  mov     ecx, 4
0x10041f8f0  call    __acrt_unlock
0x10041f8f5  test    rbx, rbx
0x10041f8f8  jz      short loc_10041F908
0x10041f8fa  mov     rax, rbx
0x10041f8fd  mov     rbx, [rsp+28h+arg_0]
0x10041f902  add     rsp, 20h
0x10041f906  pop     rdi
0x10041f907  retn
0x10041f908  call    abort
0x100425487  push    rbp
0x100425489  sub     rsp, 20h
0x10042548d  mov     rbp, rdx
0x100425490  mov     ecx, 4
0x100425495  add     rsp, 20h
0x100425499  pop     rbp
0x10042549a  jmp     __acrt_unlock
```
