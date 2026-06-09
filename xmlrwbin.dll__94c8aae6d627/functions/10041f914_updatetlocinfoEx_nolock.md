# _updatetlocinfoEx_nolock

- ea: `0x10041f914`
- end: `0x10041f979`
- name: `_updatetlocinfoEx_nolock`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x10041f488`
- `0x10041f8a0`

## callees

- `0x10041f544`
- `0x10041f5d8`
- `0x10041f7f0`
- `0x10041f914`

## pseudocode

```c
__int64 __fastcall updatetlocinfoEx_nolock(__int64 *a1, __int64 a2)
{
  __int64 v3; // rbx

  if ( !a2 || !a1 )
    return 0;
  v3 = *a1;
  if ( *a1 != a2 )
  {
    *a1 = a2;
    _acrt_add_locale_ref(a2);
    if ( v3 )
    {
      _acrt_release_locale_ref(v3);
      if ( !*(_DWORD *)(v3 + 16) && (wchar_t **)v3 != &_acrt_initial_locale_data )
        _acrt_free_locale(v3);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x10041f914  mov     [rsp+arg_0], rbx
0x10041f919  push    rdi
0x10041f91a  sub     rsp, 20h
0x10041f91e  mov     rdi, rdx
0x10041f921  test    rdx, rdx
0x10041f924  jz      short loc_10041F96C
0x10041f926  test    rcx, rcx
0x10041f929  jz      short loc_10041F96C
0x10041f92b  mov     rbx, [rcx]
0x10041f92e  cmp     rbx, rdx
0x10041f931  jnz     short loc_10041F938
0x10041f933  mov     rax, rdi
0x10041f936  jmp     short loc_10041F96E
0x10041f938  mov     [rcx], rdi
0x10041f93b  mov     rcx, rdi
0x10041f93e  call    __acrt_add_locale_ref
0x10041f943  test    rbx, rbx
0x10041f946  jz      short loc_10041F933
0x10041f948  mov     rcx, rbx
0x10041f94b  call    __acrt_release_locale_ref
0x10041f950  cmp     dword ptr [rbx+10h], 0
0x10041f954  jnz     short loc_10041F933
0x10041f956  lea     rax, __acrt_initial_locale_data
0x10041f95d  cmp     rbx, rax
0x10041f960  jz      short loc_10041F933
0x10041f962  mov     rcx, rbx
0x10041f965  call    __acrt_free_locale
0x10041f96a  jmp     short loc_10041F933
0x10041f96c  xor     eax, eax
0x10041f96e  mov     rbx, [rsp+28h+arg_0]
0x10041f973  add     rsp, 20h
0x10041f977  pop     rdi
0x10041f978  retn
```
