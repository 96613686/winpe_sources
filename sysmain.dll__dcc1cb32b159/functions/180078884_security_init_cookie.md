# __security_init_cookie

- ea: `0x180078884`
- end: `0x180078961`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180078070`

## callees

- `0x180078884`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800788e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800788f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800788e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800788f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800788bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800788bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800788d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800788d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800788cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800788cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18007890e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18007890e`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x180078884  mov     [rsp-8+arg_18], rbx
0x180078889  push    rbp
0x18007888a  mov     rbp, rsp
0x18007888d  sub     rsp, 20h
0x180078891  xor     eax, eax
0x180078893  mov     rbx, 2B992DDFA232h
0x18007889d  mov     [rbp+arg_0], rax
0x1800788a1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800788a5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800788a9  mov     rax, cs:__security_cookie
0x1800788b0  cmp     rax, rbx
0x1800788b3  jnz     loc_18007894C
0x1800788b9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800788bd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800788c3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800788c7  mov     [rbp+arg_0], rax
0x1800788cb  call    cs:__imp_GetCurrentProcessId
0x1800788d1  mov     eax, eax
0x1800788d3  xor     [rbp+arg_0], rax
0x1800788d7  call    cs:__imp_GetCurrentThreadId
0x1800788dd  mov     eax, eax
0x1800788df  xor     [rbp+arg_0], rax
0x1800788e3  call    cs:__imp_GetTickCount
0x1800788e9  mov     eax, eax
0x1800788eb  shl     rax, 18h
0x1800788ef  xor     [rbp+arg_0], rax
0x1800788f3  call    cs:__imp_GetTickCount
0x1800788f9  mov     eax, eax
0x1800788fb  lea     rcx, [rbp+arg_0]
0x1800788ff  xor     rax, [rbp+arg_0]
0x180078903  xor     rax, rcx
0x180078906  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18007890a  mov     [rbp+arg_0], rax
0x18007890e  call    cs:__imp_QueryPerformanceCounter
0x180078914  mov     eax, dword ptr [rbp+PerformanceCount]
0x180078917  mov     rcx, 0FFFFFFFFFFFFh
0x180078921  shl     rax, 20h
0x180078925  xor     rax, qword ptr [rbp+PerformanceCount]
0x180078929  xor     rax, [rbp+arg_0]
0x18007892d  and     rax, rcx
0x180078930  mov     rcx, rax
0x180078933  cmp     rax, rbx
0x180078936  jnz     short loc_180078945
0x180078938  mov     rax, 2B992DDFA233h
0x180078942  mov     rcx, rax
0x180078945  mov     cs:__security_cookie, rcx
0x18007894c  mov     rbx, [rsp+20h+arg_18]
0x180078951  not     rax
0x180078954  mov     cs:__security_cookie_complement, rax
0x18007895b  add     rsp, 20h
0x18007895f  pop     rbp
0x180078960  retn
```
