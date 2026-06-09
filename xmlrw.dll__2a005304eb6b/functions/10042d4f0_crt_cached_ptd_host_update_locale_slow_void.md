# __crt_cached_ptd_host::update_locale_slow(void)

- ea: `0x10042d4f0`
- end: `0x10042d566`
- name: `?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ`
- size: `118`
- prototype: `void __fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `10`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x10042cae4`
- `0x10042cfd4`
- `0x10042d244`
- `0x10042d470`
- `0x100431a44`
- `0x100431ee8`
- `0x1004321ac`
- `0x100432868`
- `0x1004344e8`
- `0x100434e28`

## callees

- `0x10042c550`
- `0x10042d4f0`
- `0x100431994`
- `0x100431a08`

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
0x10042d4f0  mov     [rsp+arg_0], rbx
0x10042d4f5  mov     [rsp+arg_8], rsi
0x10042d4fa  push    rdi
0x10042d4fb  sub     rsp, 20h
0x10042d4ff  mov     rdi, rcx
0x10042d502  call    ?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd(void)
0x10042d507  lea     rdx, [rdi+18h]
0x10042d50b  mov     rcx, rax
0x10042d50e  mov     rsi, rax
0x10042d511  mov     r8, [rax+90h]
0x10042d518  mov     [rdx], r8
0x10042d51b  mov     r8, [rax+88h]
0x10042d522  mov     [rdi+20h], r8
0x10042d526  mov     r8, [rdi+8]
0x10042d52a  call    __acrt_update_locale_info_explicit
0x10042d52f  mov     r8, [rdi+8]
0x10042d533  lea     rdx, [rdi+20h]
0x10042d537  mov     rcx, rsi
0x10042d53a  call    __acrt_update_multibyte_info_explicit
0x10042d53f  mov     eax, [rsi+3A8h]
0x10042d545  test    al, 2
0x10042d547  jnz     short loc_10042D556
0x10042d549  or      eax, 2
0x10042d54c  mov     [rsi+3A8h], eax
0x10042d552  mov     byte ptr [rdi+28h], 2
0x10042d556  mov     rbx, [rsp+28h+arg_0]
0x10042d55b  mov     rsi, [rsp+28h+arg_8]
0x10042d560  add     rsp, 20h
0x10042d564  pop     rdi
0x10042d565  retn
```
