# __crt_cached_ptd_host::get_raw_ptd(void)

- ea: `0x10041b200`
- end: `0x10041b267`
- name: `?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ`
- size: `103`
- prototype: `struct __acrt_ptd *__fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x10041b270`
- `0x10041bed0`
- `0x10041eedc`
- `0x100422458`

## callees

- `0x10041b1a4`
- `0x10041b200`
- `0x10041ba10`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10041b214`
- `KERNEL32!GetLastError` at `0x10041b214`
- `KERNEL32!SetLastError` at `0x10041b248`
- `KERNEL32!SetLastError` at `0x10041b248`

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
0x10041b200  push    rdi
0x10041b202  sub     rsp, 20h
0x10041b206  cmp     qword ptr [rcx], 0
0x10041b20a  mov     rdi, rcx
0x10041b20d  jnz     short loc_10041B258
0x10041b20f  mov     [rsp+28h+arg_8], rbx
0x10041b214  call    cs:__imp_GetLastError
0x10041b21a  cmp     byte ptr [rdi+10h], 0
0x10041b21e  mov     [rsp+28h+dwErrCode], eax
0x10041b222  jnz     short loc_10041B230
0x10041b224  xor     edx, edx
0x10041b226  mov     byte ptr [rdi+10h], 1
0x10041b22a  mov     [rdi+8], rdx
0x10041b22e  jmp     short loc_10041B234
0x10041b230  mov     rdx, [rdi+8]
0x10041b234  lea     rcx, [rsp+28h+dwErrCode]
0x10041b239  call    __acrt_getptd_noexit_explicit
0x10041b23e  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x10041b242  mov     rbx, rax
0x10041b245  mov     [rdi], rax
0x10041b248  call    cs:__imp_SetLastError
0x10041b24e  test    rbx, rbx
0x10041b251  mov     rbx, [rsp+28h+arg_8]
0x10041b256  jz      short loc_10041B261
0x10041b258  mov     rax, [rdi]
0x10041b25b  add     rsp, 20h
0x10041b25f  pop     rdi
0x10041b260  retn
0x10041b261  call    abort
```
