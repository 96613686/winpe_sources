# __security_init_cookie

- ea: `0x180002654`
- end: `0x180002731`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001dc0`

## callees

- `0x180002654`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800026a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800026a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000269b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000269b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800026de`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800026de`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800026b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800026c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800026b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800026c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000268d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000268d`

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
0x180002654  mov     [rsp-8+arg_18], rbx
0x180002659  push    rbp
0x18000265a  mov     rbp, rsp
0x18000265d  sub     rsp, 20h
0x180002661  xor     eax, eax
0x180002663  mov     rbx, 2B992DDFA232h
0x18000266d  mov     [rbp+arg_0], rax
0x180002671  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002675  mov     qword ptr [rbp+PerformanceCount], rax
0x180002679  mov     rax, cs:__security_cookie
0x180002680  cmp     rax, rbx
0x180002683  jnz     loc_18000271C
0x180002689  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000268d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002693  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002697  mov     [rbp+arg_0], rax
0x18000269b  call    cs:__imp_GetCurrentProcessId
0x1800026a1  mov     eax, eax
0x1800026a3  xor     [rbp+arg_0], rax
0x1800026a7  call    cs:__imp_GetCurrentThreadId
0x1800026ad  mov     eax, eax
0x1800026af  xor     [rbp+arg_0], rax
0x1800026b3  call    cs:__imp_GetTickCount
0x1800026b9  mov     eax, eax
0x1800026bb  shl     rax, 18h
0x1800026bf  xor     [rbp+arg_0], rax
0x1800026c3  call    cs:__imp_GetTickCount
0x1800026c9  mov     eax, eax
0x1800026cb  lea     rcx, [rbp+arg_0]
0x1800026cf  xor     rax, [rbp+arg_0]
0x1800026d3  xor     rax, rcx
0x1800026d6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800026da  mov     [rbp+arg_0], rax
0x1800026de  call    cs:__imp_QueryPerformanceCounter
0x1800026e4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800026e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800026f1  shl     rax, 20h
0x1800026f5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800026f9  xor     rax, [rbp+arg_0]
0x1800026fd  and     rax, rcx
0x180002700  mov     rcx, rax
0x180002703  cmp     rax, rbx
0x180002706  jnz     short loc_180002715
0x180002708  mov     rax, 2B992DDFA233h
0x180002712  mov     rcx, rax
0x180002715  mov     cs:__security_cookie, rcx
0x18000271c  mov     rbx, [rsp+20h+arg_18]
0x180002721  not     rax
0x180002724  mov     cs:__security_cookie_complement, rax
0x18000272b  add     rsp, 20h
0x18000272f  pop     rbp
0x180002730  retn
```
