# __security_init_cookie

- ea: `0x180002584`
- end: `0x180002661`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002210`

## callees

- `0x180002584`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800025cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800025cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800025d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800025d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800025bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800025bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800025e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800025f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800025e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800025f3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000260e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000260e`

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
0x180002584  mov     [rsp-8+arg_18], rbx
0x180002589  push    rbp
0x18000258a  mov     rbp, rsp
0x18000258d  sub     rsp, 20h
0x180002591  xor     eax, eax
0x180002593  mov     rbx, 2B992DDFA232h
0x18000259d  mov     [rbp+arg_0], rax
0x1800025a1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800025a5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800025a9  mov     rax, cs:__security_cookie
0x1800025b0  cmp     rax, rbx
0x1800025b3  jnz     loc_18000264C
0x1800025b9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800025bd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800025c3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800025c7  mov     [rbp+arg_0], rax
0x1800025cb  call    cs:__imp_GetCurrentProcessId
0x1800025d1  mov     eax, eax
0x1800025d3  xor     [rbp+arg_0], rax
0x1800025d7  call    cs:__imp_GetCurrentThreadId
0x1800025dd  mov     eax, eax
0x1800025df  xor     [rbp+arg_0], rax
0x1800025e3  call    cs:__imp_GetTickCount
0x1800025e9  mov     eax, eax
0x1800025eb  shl     rax, 18h
0x1800025ef  xor     [rbp+arg_0], rax
0x1800025f3  call    cs:__imp_GetTickCount
0x1800025f9  mov     eax, eax
0x1800025fb  lea     rcx, [rbp+arg_0]
0x1800025ff  xor     rax, [rbp+arg_0]
0x180002603  xor     rax, rcx
0x180002606  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000260a  mov     [rbp+arg_0], rax
0x18000260e  call    cs:__imp_QueryPerformanceCounter
0x180002614  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002617  mov     rcx, 0FFFFFFFFFFFFh
0x180002621  shl     rax, 20h
0x180002625  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002629  xor     rax, [rbp+arg_0]
0x18000262d  and     rax, rcx
0x180002630  mov     rcx, rax
0x180002633  cmp     rax, rbx
0x180002636  jnz     short loc_180002645
0x180002638  mov     rax, 2B992DDFA233h
0x180002642  mov     rcx, rax
0x180002645  mov     cs:__security_cookie, rcx
0x18000264c  mov     rbx, [rsp+20h+arg_18]
0x180002651  not     rax
0x180002654  mov     cs:__security_cookie_complement, rax
0x18000265b  add     rsp, 20h
0x18000265f  pop     rbp
0x180002660  retn
```
