# _invalid_parameter_internal

- ea: `0x10042e504`
- end: `0x10042e5d0`
- name: `_invalid_parameter_internal`
- size: `204`
- prototype: `__int64 __fastcall(wchar_t *Expression, wchar_t *FunctionName, wchar_t *FileName, unsigned int LineNo, uintptr_t, __crt_cached_ptd_host *)`
- caller_count: `18`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x10042b338`
- `0x10042bab4`
- `0x10042bcc4`
- `0x10042bed4`
- `0x10042c654`
- `0x10042c930`
- `0x10042d310`
- `0x10042d618`
- `0x10042e460`
- `0x100431a44`
- `0x100431ee8`
- `0x10043257c`
- `0x100434d04`
- `0x100434e28`
- `0x100435374`
- `0x1004372b4`
- `0x100437334`
- `0x100438338`

## callees

- `0x10042e228`
- `0x10042e298`
- `0x10042e504`
- `0x10042e5fc`
- `0x100439e10`

## pseudocode

```c
__int64 __fastcall invalid_parameter_internal(
        wchar_t *Expression,
        wchar_t *FunctionName,
        wchar_t *FileName,
        unsigned int LineNo,
        uintptr_t Reserved,
        __crt_cached_ptd_host *a6)
{
  struct __acrt_ptd *raw_ptd_noexit; // rax
  __int64 (__fastcall *v11)(wchar_t *, wchar_t *, wchar_t *, _QWORD, uintptr_t); // rax
  __int64 (__fastcall *v13)(wchar_t *, wchar_t *, wchar_t *, _QWORD, uintptr_t); // r11

  raw_ptd_noexit = __crt_cached_ptd_host::get_raw_ptd_noexit(a6);
  if ( raw_ptd_noexit )
  {
    v11 = (__int64 (__fastcall *)(wchar_t *, wchar_t *, wchar_t *, _QWORD, uintptr_t))*((_QWORD *)raw_ptd_noexit + 119);
    if ( v11 )
      return v11(Expression, FunctionName, FileName, LineNo, Reserved);
  }
  v13 = (__int64 (__fastcall *)(wchar_t *, wchar_t *, wchar_t *, _QWORD, uintptr_t))__ROR8__(
                                                                                      _security_cookie
                                                                                    ^ *(_QWORD *)__crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,unsigned int,unsigned __int64)>::value(
                                                                                                   &qword_100451758,
                                                                                                   a6),
                                                                                      _security_cookie & 0x3F);
  if ( !v13 )
    invoke_watson(Expression, FunctionName, FileName, LineNo, Reserved);
  return v13(Expression, FunctionName, FileName, LineNo, Reserved);
}

```

## disassembly

```asm
0x10042e504  mov     [rsp+arg_0], rbx
0x10042e509  mov     [rsp+arg_8], rbp
0x10042e50e  mov     [rsp+arg_10], rsi
0x10042e513  push    rdi
0x10042e514  sub     rsp, 30h
0x10042e518  mov     rbp, rcx
0x10042e51b  mov     ebx, r9d
0x10042e51e  mov     rcx, [rsp+38h+arg_28]; this
0x10042e523  mov     rdi, r8
0x10042e526  mov     rsi, rdx
0x10042e529  call    ?get_raw_ptd_noexit@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd_noexit(void)
0x10042e52e  test    rax, rax
0x10042e531  jz      short loc_10042E57A
0x10042e533  mov     rax, [rax+3B8h]
0x10042e53a  test    rax, rax
0x10042e53d  jz      short loc_10042E57A
0x10042e53f  mov     r10, 0D6BC1F4834572A70h
0x10042e549  mov     rcx, [rsp+38h+arg_20]
0x10042e54e  mov     rdx, rsi
0x10042e551  mov     [rsp+38h+Reserved], rcx
0x10042e556  mov     r8, rdi
0x10042e559  mov     rcx, rbp
0x10042e55c  mov     r9d, ebx
0x10042e55f  call    cs:__guard_xfg_dispatch_icall_fptr
0x10042e565  mov     rbx, [rsp+38h+arg_0]
0x10042e56a  mov     rbp, [rsp+38h+arg_8]
0x10042e56f  mov     rsi, [rsp+38h+arg_10]
0x10042e574  add     rsp, 30h
0x10042e578  pop     rdi
0x10042e579  retn
0x10042e57a  mov     rdx, [rsp+38h+arg_28]
0x10042e57f  lea     rcx, qword_100451758
0x10042e586  call    ?value@?$dual_state_global@P6AXPEB_W00I_K@Z@__crt_state_management@@QEAAAEAP6AXPEB_W00I_K@ZAEAV__crt_cached_ptd_host@@@Z; __crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,uint,unsigned __int64)>::value(__crt_cached_ptd_host &)
0x10042e58b  mov     r11, [rax]
0x10042e58e  mov     rax, cs:__security_cookie
0x10042e595  xor     r11, rax
0x10042e598  mov     ecx, eax
0x10042e59a  and     ecx, 3Fh
0x10042e59d  ror     r11, cl
0x10042e5a0  test    r11, r11
0x10042e5a3  jz      short loc_10042E5B4
0x10042e5a5  mov     r10, 0D6BC1F4834572A70h
0x10042e5af  mov     rax, r11
0x10042e5b2  jmp     short loc_10042E549
0x10042e5b4  mov     rax, [rsp+38h+arg_20]
0x10042e5b9  mov     r9d, ebx; LineNo
0x10042e5bc  mov     r8, rdi; FileName
0x10042e5bf  mov     [rsp+38h+Reserved], rax; Reserved
0x10042e5c4  mov     rdx, rsi; FunctionName
0x10042e5c7  mov     rcx, rbp; Expression
0x10042e5ca  call    _invoke_watson
```
