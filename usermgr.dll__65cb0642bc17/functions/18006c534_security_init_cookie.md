# __security_init_cookie

- ea: `0x18006c534`
- end: `0x18006c611`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006be30`

## callees

- `0x18006c534`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006c57b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006c57b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006c587`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006c587`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006c56d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006c56d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006c593`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006c5a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006c593`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006c5a3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18006c5be`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18006c5be`

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
0x18006c534  mov     [rsp-8+arg_18], rbx
0x18006c539  push    rbp
0x18006c53a  mov     rbp, rsp
0x18006c53d  sub     rsp, 20h
0x18006c541  xor     eax, eax
0x18006c543  mov     rbx, 2B992DDFA232h
0x18006c54d  mov     [rbp+arg_0], rax
0x18006c551  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18006c555  mov     qword ptr [rbp+PerformanceCount], rax
0x18006c559  mov     rax, cs:__security_cookie
0x18006c560  cmp     rax, rbx
0x18006c563  jnz     loc_18006C5FC
0x18006c569  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006c56d  call    cs:__imp_GetSystemTimeAsFileTime
0x18006c573  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18006c577  mov     [rbp+arg_0], rax
0x18006c57b  call    cs:__imp_GetCurrentProcessId
0x18006c581  mov     eax, eax
0x18006c583  xor     [rbp+arg_0], rax
0x18006c587  call    cs:__imp_GetCurrentThreadId
0x18006c58d  mov     eax, eax
0x18006c58f  xor     [rbp+arg_0], rax
0x18006c593  call    cs:__imp_GetTickCount
0x18006c599  mov     eax, eax
0x18006c59b  shl     rax, 18h
0x18006c59f  xor     [rbp+arg_0], rax
0x18006c5a3  call    cs:__imp_GetTickCount
0x18006c5a9  mov     eax, eax
0x18006c5ab  lea     rcx, [rbp+arg_0]
0x18006c5af  xor     rax, [rbp+arg_0]
0x18006c5b3  xor     rax, rcx
0x18006c5b6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18006c5ba  mov     [rbp+arg_0], rax
0x18006c5be  call    cs:__imp_QueryPerformanceCounter
0x18006c5c4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18006c5c7  mov     rcx, 0FFFFFFFFFFFFh
0x18006c5d1  shl     rax, 20h
0x18006c5d5  xor     rax, qword ptr [rbp+PerformanceCount]
0x18006c5d9  xor     rax, [rbp+arg_0]
0x18006c5dd  and     rax, rcx
0x18006c5e0  mov     rcx, rax
0x18006c5e3  cmp     rax, rbx
0x18006c5e6  jnz     short loc_18006C5F5
0x18006c5e8  mov     rax, 2B992DDFA233h
0x18006c5f2  mov     rcx, rax
0x18006c5f5  mov     cs:__security_cookie, rcx
0x18006c5fc  mov     rbx, [rsp+20h+arg_18]
0x18006c601  not     rax
0x18006c604  mov     cs:__security_cookie_complement, rax
0x18006c60b  add     rsp, 20h
0x18006c60f  pop     rbp
0x18006c610  retn
```
