# __crt_cached_ptd_host::get_raw_ptd_noexit(void)

- ea: `0x10041bc98`
- end: `0x10041bd02`
- name: `?get_raw_ptd_noexit@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ`
- size: `106`
- prototype: `struct __acrt_ptd *__fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x10041bf74`

## callees

- `0x10041ba10`
- `0x10041bc98`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10041bcb4`
- `KERNEL32!GetLastError` at `0x10041bcb4`
- `KERNEL32!SetLastError` at `0x10041bce9`
- `KERNEL32!SetLastError` at `0x10041bce9`

## pseudocode

```c
struct __acrt_ptd *__fastcall __crt_cached_ptd_host::get_raw_ptd_noexit(__crt_cached_ptd_host *this)
{
  __int64 v1; // rsi
  __int64 v3; // rax
  DWORD v4; // ecx
  DWORD dwErrCode; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(_QWORD *)this;
  if ( !*(_QWORD *)this )
  {
    dwErrCode = GetLastError();
    if ( !*((_BYTE *)this + 16) )
    {
      *((_QWORD *)this + 1) = 0;
      *((_BYTE *)this + 16) = 1;
    }
    v3 = _acrt_getptd_noexit_explicit(&dwErrCode);
    v4 = dwErrCode;
    v1 = v3;
    *(_QWORD *)this = v3;
    SetLastError(v4);
  }
  return (struct __acrt_ptd *)v1;
}

```

## disassembly

```asm
0x10041bc98  mov     [rsp+arg_8], rbx
0x10041bc9d  mov     [rsp+arg_10], rsi
0x10041bca2  push    rdi
0x10041bca3  sub     rsp, 20h
0x10041bca7  mov     rsi, [rcx]
0x10041bcaa  xor     edi, edi
0x10041bcac  mov     rbx, rcx
0x10041bcaf  test    rsi, rsi
0x10041bcb2  jnz     short loc_10041BCEF
0x10041bcb4  call    cs:__imp_GetLastError
0x10041bcba  mov     [rsp+28h+dwErrCode], eax
0x10041bcbe  cmp     [rbx+10h], dil
0x10041bcc2  jnz     short loc_10041BCCE
0x10041bcc4  mov     [rbx+8], rdi
0x10041bcc8  mov     byte ptr [rbx+10h], 1
0x10041bccc  jmp     short loc_10041BCD2
0x10041bcce  mov     rdi, [rbx+8]
0x10041bcd2  mov     rdx, rdi
0x10041bcd5  lea     rcx, [rsp+28h+dwErrCode]
0x10041bcda  call    __acrt_getptd_noexit_explicit
0x10041bcdf  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x10041bce3  mov     rsi, rax
0x10041bce6  mov     [rbx], rax
0x10041bce9  call    cs:__imp_SetLastError
0x10041bcef  mov     rbx, [rsp+28h+arg_8]
0x10041bcf4  mov     rax, rsi
0x10041bcf7  mov     rsi, [rsp+28h+arg_10]
0x10041bcfc  add     rsp, 20h
0x10041bd00  pop     rdi
0x10041bd01  retn
```
