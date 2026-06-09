# __acrt_update_thread_locale_data

- ea: `0x100432e50`
- end: `0x100432ebe`
- name: `__acrt_update_thread_locale_data`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x10043195c`
- `0x100431994`

## callees

- `0x10042b134`
- `0x10042dd4c`
- `0x10042e130`
- `0x10042e190`
- `0x100432e50`
- `0x100432ec4`

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
0x100432e50  mov     [rsp+arg_0], rbx
0x100432e55  push    rdi
0x100432e56  sub     rsp, 20h
0x100432e5a  call    __acrt_getptd
0x100432e5f  lea     rdi, [rax+90h]
0x100432e66  mov     ecx, [rax+3A8h]
0x100432e6c  mov     eax, cs:__globallocalestatus
0x100432e72  test    eax, ecx
0x100432e74  jz      short loc_100432E7E
0x100432e76  mov     rbx, [rdi]
0x100432e79  test    rbx, rbx
0x100432e7c  jnz     short loc_100432EAA
0x100432e7e  mov     ecx, 4
0x100432e83  call    __acrt_lock
0x100432e88  nop
0x100432e89  mov     rdx, cs:__acrt_current_locale_data
0x100432e90  mov     rcx, rdi
0x100432e93  call    _updatetlocinfoEx_nolock
0x100432e98  mov     rbx, rax
0x100432e9b  mov     ecx, 4
0x100432ea0  call    __acrt_unlock
0x100432ea5  test    rbx, rbx
0x100432ea8  jz      short loc_100432EB8
0x100432eaa  mov     rax, rbx
0x100432ead  mov     rbx, [rsp+28h+arg_0]
0x100432eb2  add     rsp, 20h
0x100432eb6  pop     rdi
0x100432eb7  retn
0x100432eb8  call    abort
0x10043ac77  push    rbp
0x10043ac79  sub     rsp, 20h
0x10043ac7d  mov     rbp, rdx
0x10043ac80  mov     ecx, 4
0x10043ac85  add     rsp, 20h
0x10043ac89  pop     rbp
0x10043ac8a  jmp     __acrt_unlock
```
