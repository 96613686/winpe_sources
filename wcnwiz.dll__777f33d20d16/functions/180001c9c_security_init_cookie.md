# __security_init_cookie

- ea: `0x180001c9c`
- end: `0x180001d51`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800017c0`

## callees

- `0x180001c9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001ceb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001ceb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001cdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001cdf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001cd1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001cd1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001cfb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001cfb`

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
0x180001c9c  mov     [rsp-8+arg_10], rbx
0x180001ca1  push    rbp
0x180001ca2  mov     rbp, rsp
0x180001ca5  sub     rsp, 30h
0x180001ca9  mov     rax, cs:__security_cookie
0x180001cb0  mov     rbx, 2B992DDFA232h
0x180001cba  cmp     rax, rbx
0x180001cbd  jnz     short loc_180001D3C
0x180001cbf  xor     eax, eax
0x180001cc1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001cc5  mov     [rbp+var_10], rax
0x180001cc9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001ccd  mov     qword ptr [rbp+PerformanceCount], rax
0x180001cd1  call    cs:__imp_GetSystemTimeAsFileTime
0x180001cd7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001cdb  mov     [rbp+var_10], rax
0x180001cdf  call    cs:__imp_GetCurrentThreadId
0x180001ce5  mov     eax, eax
0x180001ce7  xor     [rbp+var_10], rax
0x180001ceb  call    cs:__imp_GetCurrentProcessId
0x180001cf1  mov     eax, eax
0x180001cf3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001cf7  xor     [rbp+var_10], rax
0x180001cfb  call    cs:__imp_QueryPerformanceCounter
0x180001d01  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001d04  lea     rcx, [rbp+var_10]
0x180001d08  shl     rax, 20h
0x180001d0c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001d10  xor     rax, [rbp+var_10]
0x180001d14  xor     rax, rcx
0x180001d17  mov     rcx, 0FFFFFFFFFFFFh
0x180001d21  and     rax, rcx
0x180001d24  mov     rcx, 2B992DDFA233h
0x180001d2e  cmp     rax, rbx
0x180001d31  cmovz   rax, rcx
0x180001d35  mov     cs:__security_cookie, rax
0x180001d3c  mov     rbx, [rsp+30h+arg_10]
0x180001d41  not     rax
0x180001d44  mov     cs:__security_cookie_complement, rax
0x180001d4b  add     rsp, 30h
0x180001d4f  pop     rbp
0x180001d50  retn
```
