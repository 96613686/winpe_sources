# __security_init_cookie

- ea: `0x180002944`
- end: `0x180002a21`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001fc0`

## callees

- `0x180002944`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000298b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000298b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002997`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002997`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000297d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000297d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800029a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800029b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800029a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800029b3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800029ce`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800029ce`

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
0x180002944  mov     [rsp-8+arg_18], rbx
0x180002949  push    rbp
0x18000294a  mov     rbp, rsp
0x18000294d  sub     rsp, 20h
0x180002951  xor     eax, eax
0x180002953  mov     rbx, 2B992DDFA232h
0x18000295d  mov     [rbp+arg_0], rax
0x180002961  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002965  mov     qword ptr [rbp+PerformanceCount], rax
0x180002969  mov     rax, cs:__security_cookie
0x180002970  cmp     rax, rbx
0x180002973  jnz     loc_180002A0C
0x180002979  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000297d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002983  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002987  mov     [rbp+arg_0], rax
0x18000298b  call    cs:__imp_GetCurrentProcessId
0x180002991  mov     eax, eax
0x180002993  xor     [rbp+arg_0], rax
0x180002997  call    cs:__imp_GetCurrentThreadId
0x18000299d  mov     eax, eax
0x18000299f  xor     [rbp+arg_0], rax
0x1800029a3  call    cs:__imp_GetTickCount
0x1800029a9  mov     eax, eax
0x1800029ab  shl     rax, 18h
0x1800029af  xor     [rbp+arg_0], rax
0x1800029b3  call    cs:__imp_GetTickCount
0x1800029b9  mov     eax, eax
0x1800029bb  lea     rcx, [rbp+arg_0]
0x1800029bf  xor     rax, [rbp+arg_0]
0x1800029c3  xor     rax, rcx
0x1800029c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800029ca  mov     [rbp+arg_0], rax
0x1800029ce  call    cs:__imp_QueryPerformanceCounter
0x1800029d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800029d7  mov     rcx, 0FFFFFFFFFFFFh
0x1800029e1  shl     rax, 20h
0x1800029e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800029e9  xor     rax, [rbp+arg_0]
0x1800029ed  and     rax, rcx
0x1800029f0  mov     rcx, rax
0x1800029f3  cmp     rax, rbx
0x1800029f6  jnz     short loc_180002A05
0x1800029f8  mov     rax, 2B992DDFA233h
0x180002a02  mov     rcx, rax
0x180002a05  mov     cs:__security_cookie, rcx
0x180002a0c  mov     rbx, [rsp+20h+arg_18]
0x180002a11  not     rax
0x180002a14  mov     cs:__security_cookie_complement, rax
0x180002a1b  add     rsp, 20h
0x180002a1f  pop     rbp
0x180002a20  retn
```
