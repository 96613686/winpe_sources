# __security_init_cookie

- ea: `0x100416c04`
- end: `0x100416cb0`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1004168f8`

## callees

- `0x100416c04`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100416c5a`
- `KERNEL32!QueryPerformanceCounter` at `0x100416c5a`
- `KERNEL32!GetCurrentProcessId` at `0x100416c4a`
- `KERNEL32!GetCurrentProcessId` at `0x100416c4a`
- `KERNEL32!GetCurrentThreadId` at `0x100416c3e`
- `KERNEL32!GetCurrentThreadId` at `0x100416c3e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100416c30`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x100416c30`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x100416c04  mov     [rsp-8+arg_18], rbx
0x100416c09  push    rbp
0x100416c0a  mov     rbp, rsp
0x100416c0d  sub     rsp, 20h
0x100416c11  mov     rax, cs:__security_cookie
0x100416c18  mov     rbx, 2B992DDFA232h
0x100416c22  cmp     rax, rbx
0x100416c25  jnz     short loc_100416C9B
0x100416c27  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x100416c2c  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x100416c30  call    cs:__imp_GetSystemTimeAsFileTime
0x100416c36  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x100416c3a  mov     [rbp+arg_0], rax
0x100416c3e  call    cs:__imp_GetCurrentThreadId
0x100416c44  mov     eax, eax
0x100416c46  xor     [rbp+arg_0], rax
0x100416c4a  call    cs:__imp_GetCurrentProcessId
0x100416c50  mov     eax, eax
0x100416c52  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x100416c56  xor     [rbp+arg_0], rax
0x100416c5a  call    cs:__imp_QueryPerformanceCounter
0x100416c60  mov     eax, dword ptr [rbp+PerformanceCount]
0x100416c63  lea     rcx, [rbp+arg_0]
0x100416c67  shl     rax, 20h
0x100416c6b  xor     rax, qword ptr [rbp+PerformanceCount]
0x100416c6f  xor     rax, [rbp+arg_0]
0x100416c73  xor     rax, rcx
0x100416c76  mov     rcx, 0FFFFFFFFFFFFh
0x100416c80  and     rax, rcx
0x100416c83  mov     rcx, 2B992DDFA233h
0x100416c8d  cmp     rax, rbx
0x100416c90  cmovz   rax, rcx
0x100416c94  mov     cs:__security_cookie, rax
0x100416c9b  mov     rbx, [rsp+20h+arg_18]
0x100416ca0  not     rax
0x100416ca3  mov     cs:__security_cookie_complement, rax
0x100416caa  add     rsp, 20h
0x100416cae  pop     rbp
0x100416caf  retn
```
