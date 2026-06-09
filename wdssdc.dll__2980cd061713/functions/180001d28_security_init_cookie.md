# __security_init_cookie

- ea: `0x180001d28`
- end: `0x180001ddf`
- name: `__security_init_cookie`
- size: `183`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001550`

## callees

- `0x180001d28`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001d5f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001d5f`
- `KERNEL32!GetCurrentThreadId` at `0x180001d6d`
- `KERNEL32!GetCurrentThreadId` at `0x180001d6d`
- `KERNEL32!GetCurrentProcessId` at `0x180001d79`
- `KERNEL32!GetCurrentProcessId` at `0x180001d79`
- `KERNEL32!QueryPerformanceCounter` at `0x180001d89`
- `KERNEL32!QueryPerformanceCounter` at `0x180001d89`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
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
0x180001d28  mov     [rsp-8+arg_10], rbx
0x180001d2d  push    rbp
0x180001d2e  mov     rbp, rsp
0x180001d31  sub     rsp, 30h
0x180001d35  mov     rax, cs:__security_cookie
0x180001d3c  mov     rbx, 2B992DDFA232h
0x180001d46  cmp     rax, rbx
0x180001d49  jnz     short loc_180001DCA
0x180001d4b  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001d4f  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180001d57  mov     qword ptr [rbp+PerformanceCount], 0
0x180001d5f  call    cs:__imp_GetSystemTimeAsFileTime
0x180001d65  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001d69  mov     [rbp+var_10], rax
0x180001d6d  call    cs:__imp_GetCurrentThreadId
0x180001d73  mov     eax, eax
0x180001d75  xor     [rbp+var_10], rax
0x180001d79  call    cs:__imp_GetCurrentProcessId
0x180001d7f  mov     eax, eax
0x180001d81  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001d85  xor     [rbp+var_10], rax
0x180001d89  call    cs:__imp_QueryPerformanceCounter
0x180001d8f  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001d92  lea     rcx, [rbp+var_10]
0x180001d96  shl     rax, 20h
0x180001d9a  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001d9e  xor     rax, [rbp+var_10]
0x180001da2  xor     rax, rcx
0x180001da5  mov     rcx, 0FFFFFFFFFFFFh
0x180001daf  and     rax, rcx
0x180001db2  mov     rcx, 2B992DDFA233h
0x180001dbc  cmp     rax, rbx
0x180001dbf  cmovz   rax, rcx
0x180001dc3  mov     cs:__security_cookie, rax
0x180001dca  mov     rbx, [rsp+30h+arg_10]
0x180001dcf  not     rax
0x180001dd2  mov     cs:__security_cookie_complement, rax
0x180001dd9  add     rsp, 30h
0x180001ddd  pop     rbp
0x180001dde  retn
```
