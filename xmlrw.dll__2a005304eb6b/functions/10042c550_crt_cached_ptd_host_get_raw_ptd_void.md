# __crt_cached_ptd_host::get_raw_ptd(void)

- ea: `0x10042c550`
- end: `0x10042c5b7`
- name: `?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ`
- size: `103`
- prototype: `struct __acrt_ptd *__fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x10042d4f0`
- `0x10042d618`
- `0x10042e460`
- `0x10043146c`
- `0x1004373e0`

## callees

- `0x10042b134`
- `0x10042c550`
- `0x10042dfa0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10042c564`
- `KERNEL32!GetLastError` at `0x10042c564`
- `KERNEL32!SetLastError` at `0x10042c598`
- `KERNEL32!SetLastError` at `0x10042c598`

## pseudocode

```c
struct __acrt_ptd *__fastcall __crt_cached_ptd_host::get_raw_ptd(__crt_cached_ptd_host *this)
{
  DWORD LastError; // eax
  bool v3; // zf
  __int64 v4; // rax
  DWORD v5; // ecx
  __int64 v6; // rbx
  DWORD dwErrCode; // [rsp+30h] [rbp+8h] BYREF

  if ( !*(_QWORD *)this )
  {
    LastError = GetLastError();
    v3 = *((_BYTE *)this + 16) == 0;
    dwErrCode = LastError;
    if ( v3 )
    {
      *((_BYTE *)this + 16) = 1;
      *((_QWORD *)this + 1) = 0;
    }
    v4 = _acrt_getptd_noexit_explicit(&dwErrCode);
    v5 = dwErrCode;
    v6 = v4;
    *(_QWORD *)this = v4;
    SetLastError(v5);
    if ( !v6 )
      abort();
  }
  return *(struct __acrt_ptd **)this;
}

```

## disassembly

```asm
0x10042c550  push    rdi
0x10042c552  sub     rsp, 20h
0x10042c556  cmp     qword ptr [rcx], 0
0x10042c55a  mov     rdi, rcx
0x10042c55d  jnz     short loc_10042C5A8
0x10042c55f  mov     [rsp+28h+arg_8], rbx
0x10042c564  call    cs:__imp_GetLastError
0x10042c56a  cmp     byte ptr [rdi+10h], 0
0x10042c56e  mov     [rsp+28h+dwErrCode], eax
0x10042c572  jnz     short loc_10042C580
0x10042c574  xor     edx, edx
0x10042c576  mov     byte ptr [rdi+10h], 1
0x10042c57a  mov     [rdi+8], rdx
0x10042c57e  jmp     short loc_10042C584
0x10042c580  mov     rdx, [rdi+8]
0x10042c584  lea     rcx, [rsp+28h+dwErrCode]
0x10042c589  call    __acrt_getptd_noexit_explicit
0x10042c58e  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x10042c592  mov     rbx, rax
0x10042c595  mov     [rdi], rax
0x10042c598  call    cs:__imp_SetLastError
0x10042c59e  test    rbx, rbx
0x10042c5a1  mov     rbx, [rsp+28h+arg_8]
0x10042c5a6  jz      short loc_10042C5B1
0x10042c5a8  mov     rax, [rdi]
0x10042c5ab  add     rsp, 20h
0x10042c5af  pop     rdi
0x10042c5b0  retn
0x10042c5b1  call    abort
```
