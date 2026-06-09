# __security_init_cookie

- ea: `0x180001644`
- end: `0x180001721`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800012d0`

## callees

- `0x180001644`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000168b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000168b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001697`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001697`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800016ce`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800016ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800016a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800016b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800016a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800016b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000167d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000167d`

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
0x180001644  mov     [rsp-8+arg_18], rbx
0x180001649  push    rbp
0x18000164a  mov     rbp, rsp
0x18000164d  sub     rsp, 20h
0x180001651  xor     eax, eax
0x180001653  mov     rbx, 2B992DDFA232h
0x18000165d  mov     [rbp+arg_0], rax
0x180001661  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001665  mov     qword ptr [rbp+PerformanceCount], rax
0x180001669  mov     rax, cs:__security_cookie
0x180001670  cmp     rax, rbx
0x180001673  jnz     loc_18000170C
0x180001679  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000167d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001683  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001687  mov     [rbp+arg_0], rax
0x18000168b  call    cs:__imp_GetCurrentProcessId
0x180001691  mov     eax, eax
0x180001693  xor     [rbp+arg_0], rax
0x180001697  call    cs:__imp_GetCurrentThreadId
0x18000169d  mov     eax, eax
0x18000169f  xor     [rbp+arg_0], rax
0x1800016a3  call    cs:__imp_GetTickCount
0x1800016a9  mov     eax, eax
0x1800016ab  shl     rax, 18h
0x1800016af  xor     [rbp+arg_0], rax
0x1800016b3  call    cs:__imp_GetTickCount
0x1800016b9  mov     eax, eax
0x1800016bb  lea     rcx, [rbp+arg_0]
0x1800016bf  xor     rax, [rbp+arg_0]
0x1800016c3  xor     rax, rcx
0x1800016c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800016ca  mov     [rbp+arg_0], rax
0x1800016ce  call    cs:__imp_QueryPerformanceCounter
0x1800016d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800016d7  mov     rcx, 0FFFFFFFFFFFFh
0x1800016e1  shl     rax, 20h
0x1800016e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800016e9  xor     rax, [rbp+arg_0]
0x1800016ed  and     rax, rcx
0x1800016f0  mov     rcx, rax
0x1800016f3  cmp     rax, rbx
0x1800016f6  jnz     short loc_180001705
0x1800016f8  mov     rax, 2B992DDFA233h
0x180001702  mov     rcx, rax
0x180001705  mov     cs:__security_cookie, rcx
0x18000170c  mov     rbx, [rsp+20h+arg_18]
0x180001711  not     rax
0x180001714  mov     cs:__security_cookie_complement, rax
0x18000171b  add     rsp, 20h
0x18000171f  pop     rbp
0x180001720  retn
```
