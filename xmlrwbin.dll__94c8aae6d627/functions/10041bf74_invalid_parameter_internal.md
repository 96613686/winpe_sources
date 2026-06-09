# _invalid_parameter_internal

- ea: `0x10041bf74`
- end: `0x10041c040`
- name: `_invalid_parameter_internal`
- size: `204`
- prototype: `__int64 __fastcall(wchar_t *Expression, wchar_t *FunctionName, wchar_t *FileName, unsigned int LineNo, uintptr_t, __crt_cached_ptd_host *)`
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x10041bed0`
- `0x100421754`
- `0x100421878`
- `0x10042232c`
- `0x1004223ac`
- `0x100422e88`

## callees

- `0x10041bc98`
- `0x10041bd08`
- `0x10041bf74`
- `0x10041c06c`
- `0x1004245a0`

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
                                                                                                   &qword_1004357E8,
                                                                                                   a6),
                                                                                      _security_cookie & 0x3F);
  if ( !v13 )
    invoke_watson(Expression, FunctionName, FileName, LineNo, Reserved);
  return v13(Expression, FunctionName, FileName, LineNo, Reserved);
}

```

## disassembly

```asm
0x10041bf74  mov     [rsp+arg_0], rbx
0x10041bf79  mov     [rsp+arg_8], rbp
0x10041bf7e  mov     [rsp+arg_10], rsi
0x10041bf83  push    rdi
0x10041bf84  sub     rsp, 30h
0x10041bf88  mov     rbp, rcx
0x10041bf8b  mov     ebx, r9d
0x10041bf8e  mov     rcx, [rsp+38h+arg_28]; this
0x10041bf93  mov     rdi, r8
0x10041bf96  mov     rsi, rdx
0x10041bf99  call    ?get_raw_ptd_noexit@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::get_raw_ptd_noexit(void)
0x10041bf9e  test    rax, rax
0x10041bfa1  jz      short loc_10041BFEA
0x10041bfa3  mov     rax, [rax+3B8h]
0x10041bfaa  test    rax, rax
0x10041bfad  jz      short loc_10041BFEA
0x10041bfaf  mov     r10, 0D6BC1F4834572A70h
0x10041bfb9  mov     rcx, [rsp+38h+arg_20]
0x10041bfbe  mov     rdx, rsi
0x10041bfc1  mov     [rsp+38h+Reserved], rcx
0x10041bfc6  mov     r8, rdi
0x10041bfc9  mov     rcx, rbp
0x10041bfcc  mov     r9d, ebx
0x10041bfcf  call    cs:__guard_xfg_dispatch_icall_fptr
0x10041bfd5  mov     rbx, [rsp+38h+arg_0]
0x10041bfda  mov     rbp, [rsp+38h+arg_8]
0x10041bfdf  mov     rsi, [rsp+38h+arg_10]
0x10041bfe4  add     rsp, 30h
0x10041bfe8  pop     rdi
0x10041bfe9  retn
0x10041bfea  mov     rdx, [rsp+38h+arg_28]
0x10041bfef  lea     rcx, qword_1004357E8
0x10041bff6  call    ?value@?$dual_state_global@P6AXPEB_W00I_K@Z@__crt_state_management@@QEAAAEAP6AXPEB_W00I_K@ZAEAV__crt_cached_ptd_host@@@Z; __crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,uint,unsigned __int64)>::value(__crt_cached_ptd_host &)
0x10041bffb  mov     r11, [rax]
0x10041bffe  mov     rax, cs:__security_cookie
0x10041c005  xor     r11, rax
0x10041c008  mov     ecx, eax
0x10041c00a  and     ecx, 3Fh
0x10041c00d  ror     r11, cl
0x10041c010  test    r11, r11
0x10041c013  jz      short loc_10041C024
0x10041c015  mov     r10, 0D6BC1F4834572A70h
0x10041c01f  mov     rax, r11
0x10041c022  jmp     short loc_10041BFB9
0x10041c024  mov     rax, [rsp+38h+arg_20]
0x10041c029  mov     r9d, ebx; LineNo
0x10041c02c  mov     r8, rdi; FileName
0x10041c02f  mov     [rsp+38h+Reserved], rax; Reserved
0x10041c034  mov     rdx, rsi; FunctionName
0x10041c037  mov     rcx, rbp; Expression
0x10041c03a  call    _invoke_watson
```
