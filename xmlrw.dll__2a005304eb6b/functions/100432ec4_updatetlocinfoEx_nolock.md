# _updatetlocinfoEx_nolock

- ea: `0x100432ec4`
- end: `0x100432f29`
- name: `_updatetlocinfoEx_nolock`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x100432a38`
- `0x100432e50`

## callees

- `0x100432af4`
- `0x100432b88`
- `0x100432da0`
- `0x100432ec4`

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
0x100432ec4  mov     [rsp+arg_0], rbx
0x100432ec9  push    rdi
0x100432eca  sub     rsp, 20h
0x100432ece  mov     rdi, rdx
0x100432ed1  test    rdx, rdx
0x100432ed4  jz      short loc_100432F1C
0x100432ed6  test    rcx, rcx
0x100432ed9  jz      short loc_100432F1C
0x100432edb  mov     rbx, [rcx]
0x100432ede  cmp     rbx, rdx
0x100432ee1  jnz     short loc_100432EE8
0x100432ee3  mov     rax, rdi
0x100432ee6  jmp     short loc_100432F1E
0x100432ee8  mov     [rcx], rdi
0x100432eeb  mov     rcx, rdi
0x100432eee  call    __acrt_add_locale_ref
0x100432ef3  test    rbx, rbx
0x100432ef6  jz      short loc_100432EE3
0x100432ef8  mov     rcx, rbx
0x100432efb  call    __acrt_release_locale_ref
0x100432f00  cmp     dword ptr [rbx+10h], 0
0x100432f04  jnz     short loc_100432EE3
0x100432f06  lea     rax, __acrt_initial_locale_data
0x100432f0d  cmp     rbx, rax
0x100432f10  jz      short loc_100432EE3
0x100432f12  mov     rcx, rbx
0x100432f15  call    __acrt_free_locale
0x100432f1a  jmp     short loc_100432EE3
0x100432f1c  xor     eax, eax
0x100432f1e  mov     rbx, [rsp+28h+arg_0]
0x100432f23  add     rsp, 20h
0x100432f27  pop     rdi
0x100432f28  retn
```
