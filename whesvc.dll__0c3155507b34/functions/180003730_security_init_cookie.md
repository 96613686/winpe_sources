# __security_init_cookie

- ea: `0x180003730`
- end: `0x1800037e5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003290`

## callees

- `0x180003730`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000377f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000377f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003773`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003773`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000378f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000378f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003765`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003765`

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
0x180003730  mov     [rsp-8+arg_10], rbx
0x180003735  push    rbp
0x180003736  mov     rbp, rsp
0x180003739  sub     rsp, 30h
0x18000373d  mov     rax, cs:__security_cookie
0x180003744  mov     rbx, 2B992DDFA232h
0x18000374e  cmp     rax, rbx
0x180003751  jnz     short loc_1800037D0
0x180003753  xor     eax, eax
0x180003755  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003759  mov     [rbp+var_10], rax
0x18000375d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003761  mov     qword ptr [rbp+PerformanceCount], rax
0x180003765  call    cs:__imp_GetSystemTimeAsFileTime
0x18000376b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000376f  mov     [rbp+var_10], rax
0x180003773  call    cs:__imp_GetCurrentThreadId
0x180003779  mov     eax, eax
0x18000377b  xor     [rbp+var_10], rax
0x18000377f  call    cs:__imp_GetCurrentProcessId
0x180003785  mov     eax, eax
0x180003787  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000378b  xor     [rbp+var_10], rax
0x18000378f  call    cs:__imp_QueryPerformanceCounter
0x180003795  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003798  lea     rcx, [rbp+var_10]
0x18000379c  shl     rax, 20h
0x1800037a0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800037a4  xor     rax, [rbp+var_10]
0x1800037a8  xor     rax, rcx
0x1800037ab  mov     rcx, 0FFFFFFFFFFFFh
0x1800037b5  and     rax, rcx
0x1800037b8  mov     rcx, 2B992DDFA233h
0x1800037c2  cmp     rax, rbx
0x1800037c5  cmovz   rax, rcx
0x1800037c9  mov     cs:__security_cookie, rax
0x1800037d0  mov     rbx, [rsp+30h+arg_10]
0x1800037d5  not     rax
0x1800037d8  mov     cs:__security_cookie_complement, rax
0x1800037df  add     rsp, 30h
0x1800037e3  pop     rbp
0x1800037e4  retn
```
