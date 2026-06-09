# __security_init_cookie

- ea: `0x180001694`
- end: `0x180001749`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001620`
- `0x180002010`

## callees

- `0x180001694`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800016d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800016d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800016e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800016e3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800016f3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800016f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800016c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800016c9`

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
0x180001694  mov     [rsp-8+arg_10], rbx
0x180001699  push    rbp
0x18000169a  mov     rbp, rsp
0x18000169d  sub     rsp, 30h
0x1800016a1  mov     rax, cs:__security_cookie
0x1800016a8  mov     rbx, 2B992DDFA232h
0x1800016b2  cmp     rax, rbx
0x1800016b5  jnz     short loc_180001734
0x1800016b7  xor     eax, eax
0x1800016b9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800016bd  mov     [rbp+var_10], rax
0x1800016c1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800016c5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800016c9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800016cf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800016d3  mov     [rbp+var_10], rax
0x1800016d7  call    cs:__imp_GetCurrentThreadId
0x1800016dd  mov     eax, eax
0x1800016df  xor     [rbp+var_10], rax
0x1800016e3  call    cs:__imp_GetCurrentProcessId
0x1800016e9  mov     eax, eax
0x1800016eb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800016ef  xor     [rbp+var_10], rax
0x1800016f3  call    cs:__imp_QueryPerformanceCounter
0x1800016f9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800016fc  lea     rcx, [rbp+var_10]
0x180001700  shl     rax, 20h
0x180001704  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001708  xor     rax, [rbp+var_10]
0x18000170c  xor     rax, rcx
0x18000170f  mov     rcx, 0FFFFFFFFFFFFh
0x180001719  and     rax, rcx
0x18000171c  mov     rcx, 2B992DDFA233h
0x180001726  cmp     rax, rbx
0x180001729  cmovz   rax, rcx
0x18000172d  mov     cs:__security_cookie, rax
0x180001734  mov     rbx, [rsp+30h+arg_10]
0x180001739  not     rax
0x18000173c  mov     cs:__security_cookie_complement, rax
0x180001743  add     rsp, 30h
0x180001747  pop     rbp
0x180001748  retn
```
