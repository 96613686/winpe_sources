# __crt_cached_ptd_host::update_locale_slow(void)

- ea: `0x10041b270`
- end: `0x10041b2e6`
- name: `?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ`
- size: `118`
- prototype: `void __fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x10041f2d8`
- `0x100420f38`
- `0x100421878`

## callees

- `0x10041b200`
- `0x10041b270`
- `0x10041f228`
- `0x10041f29c`

## pseudocode

```c
void __fastcall __crt_cached_ptd_host::update_locale_slow(__crt_cached_ptd_host *this)
{
  struct __acrt_ptd *raw_ptd; // rsi
  int v3; // eax

  raw_ptd = __crt_cached_ptd_host::get_raw_ptd(this);
  *((_QWORD *)this + 3) = *((_QWORD *)raw_ptd + 18);
  *((_QWORD *)this + 4) = *((_QWORD *)raw_ptd + 17);
  _acrt_update_locale_info_explicit(raw_ptd, (char *)this + 24, *((_QWORD *)this + 1));
  _acrt_update_multibyte_info_explicit(raw_ptd, (char *)this + 32, *((_QWORD *)this + 1));
  v3 = *((_DWORD *)raw_ptd + 234);
  if ( (v3 & 2) == 0 )
  {
    *((_DWORD *)raw_ptd + 234) = v3 | 2;
    *((_BYTE *)this + 40) = 2;
  }
}

```

## disassembly

```asm
0x10041b270  mov     [rsp+arg_0], rbx
0x10041b275  mov     [rsp+arg_8], rsi
0x10041b27a  push    rdi
0x10041b27b  sub     rsp, 20h
0x10041b27f  mov     rdi, rcx
0x10041b282  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x10041b287  lea     rdx, [rdi+18h]
0x10041b28b  mov     rcx, rax
0x10041b28e  mov     rsi, rax
0x10041b291  mov     r8, [rax+90h]
0x10041b298  mov     [rdx], r8
0x10041b29b  mov     r8, [rax+88h]
0x10041b2a2  mov     [rdi+20h], r8
0x10041b2a6  mov     r8, [rdi+8]
0x10041b2aa  call    __acrt_update_locale_info_explicit
0x10041b2af  mov     r8, [rdi+8]
0x10041b2b3  lea     rdx, [rdi+20h]
0x10041b2b7  mov     rcx, rsi
0x10041b2ba  call    __acrt_update_multibyte_info_explicit
0x10041b2bf  mov     eax, [rsi+3A8h]
0x10041b2c5  test    al, 2
0x10041b2c7  jnz     short loc_10041B2D6
0x10041b2c9  or      eax, 2
0x10041b2cc  mov     [rsi+3A8h], eax
0x10041b2d2  mov     byte ptr [rdi+28h], 2
0x10041b2d6  mov     rbx, [rsp+28h+arg_0]
0x10041b2db  mov     rsi, [rsp+28h+arg_8]
0x10041b2e0  add     rsp, 20h
0x10041b2e4  pop     rdi
0x10041b2e5  retn
```
