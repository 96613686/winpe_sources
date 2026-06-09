# __security_init_cookie

- ea: `0x180002514`
- end: `0x1800025f1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001f30`

## callees

- `0x180002514`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002567`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002567`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000255b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000255b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000259e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000259e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000254d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000254d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002573`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002583`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002573`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002583`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180002514  mov     [rsp-8+arg_18], rbx
0x180002519  push    rbp
0x18000251a  mov     rbp, rsp
0x18000251d  sub     rsp, 20h
0x180002521  xor     eax, eax
0x180002523  mov     rbx, 2B992DDFA232h
0x18000252d  mov     [rbp+arg_0], rax
0x180002531  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002535  mov     qword ptr [rbp+PerformanceCount], rax
0x180002539  mov     rax, cs:__security_cookie
0x180002540  cmp     rax, rbx
0x180002543  jnz     loc_1800025DC
0x180002549  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000254d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002553  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002557  mov     [rbp+arg_0], rax
0x18000255b  call    cs:__imp_GetCurrentProcessId
0x180002561  mov     eax, eax
0x180002563  xor     [rbp+arg_0], rax
0x180002567  call    cs:__imp_GetCurrentThreadId
0x18000256d  mov     eax, eax
0x18000256f  xor     [rbp+arg_0], rax
0x180002573  call    cs:__imp_GetTickCount
0x180002579  mov     eax, eax
0x18000257b  shl     rax, 18h
0x18000257f  xor     [rbp+arg_0], rax
0x180002583  call    cs:__imp_GetTickCount
0x180002589  mov     eax, eax
0x18000258b  lea     rcx, [rbp+arg_0]
0x18000258f  xor     rax, [rbp+arg_0]
0x180002593  xor     rax, rcx
0x180002596  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000259a  mov     [rbp+arg_0], rax
0x18000259e  call    cs:__imp_QueryPerformanceCounter
0x1800025a4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800025a7  mov     rcx, 0FFFFFFFFFFFFh
0x1800025b1  shl     rax, 20h
0x1800025b5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800025b9  xor     rax, [rbp+arg_0]
0x1800025bd  and     rax, rcx
0x1800025c0  mov     rcx, rax
0x1800025c3  cmp     rax, rbx
0x1800025c6  jnz     short loc_1800025D5
0x1800025c8  mov     rax, 2B992DDFA233h
0x1800025d2  mov     rcx, rax
0x1800025d5  mov     cs:__security_cookie, rcx
0x1800025dc  mov     rbx, [rsp+20h+arg_18]
0x1800025e1  not     rax
0x1800025e4  mov     cs:__security_cookie_complement, rax
0x1800025eb  add     rsp, 20h
0x1800025ef  pop     rbp
0x1800025f0  retn
```
