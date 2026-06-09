# replace_current_thread_locale_nolock

- ea: `0x10042dc94`
- end: `0x10042dcfb`
- name: `replace_current_thread_locale_nolock`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x10042d99c`
- `0x10042d9e0`

## callees

- `0x10042dc94`
- `0x100432af4`
- `0x100432b88`
- `0x100432da0`

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
0x10042dc94  mov     [rsp+arg_0], rbx
0x10042dc99  push    rdi
0x10042dc9a  sub     rsp, 20h
0x10042dc9e  mov     rdi, rcx
0x10042dca1  mov     rbx, rdx
0x10042dca4  mov     rcx, [rcx+90h]
0x10042dcab  test    rcx, rcx
0x10042dcae  jz      short loc_10042DCDC
0x10042dcb0  call    __acrt_release_locale_ref
0x10042dcb5  mov     rcx, [rdi+90h]
0x10042dcbc  cmp     rcx, cs:__acrt_current_locale_data
0x10042dcc3  jz      short loc_10042DCDC
0x10042dcc5  lea     rax, __acrt_initial_locale_data
0x10042dccc  cmp     rcx, rax
0x10042dccf  jz      short loc_10042DCDC
0x10042dcd1  cmp     dword ptr [rcx+10h], 0
0x10042dcd5  jnz     short loc_10042DCDC
0x10042dcd7  call    __acrt_free_locale
0x10042dcdc  mov     [rdi+90h], rbx
0x10042dce3  test    rbx, rbx
0x10042dce6  jz      short loc_10042DCF0
0x10042dce8  mov     rcx, rbx
0x10042dceb  call    __acrt_add_locale_ref
0x10042dcf0  mov     rbx, [rsp+28h+arg_0]
0x10042dcf5  add     rsp, 20h
0x10042dcf9  pop     rdi
0x10042dcfa  retn
```
