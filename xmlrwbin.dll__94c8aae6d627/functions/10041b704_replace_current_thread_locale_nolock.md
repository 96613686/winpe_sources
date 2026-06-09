# replace_current_thread_locale_nolock

- ea: `0x10041b704`
- end: `0x10041b76b`
- name: `replace_current_thread_locale_nolock`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x10041b40c`
- `0x10041b450`

## callees

- `0x10041b704`
- `0x10041f544`
- `0x10041f5d8`
- `0x10041f7f0`

## pseudocode

```c
wchar_t **__fastcall replace_current_thread_locale_nolock(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  wchar_t **result; // rax
  __int64 v6; // rcx

  v4 = *(_QWORD *)(a1 + 144);
  if ( v4 )
  {
    result = (wchar_t **)_acrt_release_locale_ref(v4);
    v6 = *(_QWORD *)(a1 + 144);
    if ( v6 != _acrt_current_locale_data )
    {
      result = &_acrt_initial_locale_data;
      if ( (wchar_t **)v6 != &_acrt_initial_locale_data && !*(_DWORD *)(v6 + 16) )
        result = (wchar_t **)_acrt_free_locale(v6);
    }
  }
  *(_QWORD *)(a1 + 144) = a2;
  if ( a2 )
    return (wchar_t **)_acrt_add_locale_ref(a2);
  return result;
}

```

## disassembly

```asm
0x10041b704  mov     [rsp+arg_0], rbx
0x10041b709  push    rdi
0x10041b70a  sub     rsp, 20h
0x10041b70e  mov     rdi, rcx
0x10041b711  mov     rbx, rdx
0x10041b714  mov     rcx, [rcx+90h]
0x10041b71b  test    rcx, rcx
0x10041b71e  jz      short loc_10041B74C
0x10041b720  call    __acrt_release_locale_ref
0x10041b725  mov     rcx, [rdi+90h]
0x10041b72c  cmp     rcx, cs:__acrt_current_locale_data
0x10041b733  jz      short loc_10041B74C
0x10041b735  lea     rax, __acrt_initial_locale_data
0x10041b73c  cmp     rcx, rax
0x10041b73f  jz      short loc_10041B74C
0x10041b741  cmp     dword ptr [rcx+10h], 0
0x10041b745  jnz     short loc_10041B74C
0x10041b747  call    __acrt_free_locale
0x10041b74c  mov     [rdi+90h], rbx
0x10041b753  test    rbx, rbx
0x10041b756  jz      short loc_10041B760
0x10041b758  mov     rcx, rbx
0x10041b75b  call    __acrt_add_locale_ref
0x10041b760  mov     rbx, [rsp+28h+arg_0]
0x10041b765  add     rsp, 20h
0x10041b769  pop     rdi
0x10041b76a  retn
```
