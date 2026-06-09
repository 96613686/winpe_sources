# __security_init_cookie

- ea: `0x1800232c4`
- end: `0x1800233a1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022c70`

## callees

- `0x1800232c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023317`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023317`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002330b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002330b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800232fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800232fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180023323`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180023333`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180023323`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180023333`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002334e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002334e`

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
0x1800232c4  mov     [rsp-8+arg_18], rbx
0x1800232c9  push    rbp
0x1800232ca  mov     rbp, rsp
0x1800232cd  sub     rsp, 20h
0x1800232d1  xor     eax, eax
0x1800232d3  mov     rbx, 2B992DDFA232h
0x1800232dd  mov     [rbp+arg_0], rax
0x1800232e1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800232e5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800232e9  mov     rax, cs:__security_cookie
0x1800232f0  cmp     rax, rbx
0x1800232f3  jnz     loc_18002338C
0x1800232f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800232fd  call    cs:__imp_GetSystemTimeAsFileTime
0x180023303  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180023307  mov     [rbp+arg_0], rax
0x18002330b  call    cs:__imp_GetCurrentProcessId
0x180023311  mov     eax, eax
0x180023313  xor     [rbp+arg_0], rax
0x180023317  call    cs:__imp_GetCurrentThreadId
0x18002331d  mov     eax, eax
0x18002331f  xor     [rbp+arg_0], rax
0x180023323  call    cs:__imp_GetTickCount
0x180023329  mov     eax, eax
0x18002332b  shl     rax, 18h
0x18002332f  xor     [rbp+arg_0], rax
0x180023333  call    cs:__imp_GetTickCount
0x180023339  mov     eax, eax
0x18002333b  lea     rcx, [rbp+arg_0]
0x18002333f  xor     rax, [rbp+arg_0]
0x180023343  xor     rax, rcx
0x180023346  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002334a  mov     [rbp+arg_0], rax
0x18002334e  call    cs:__imp_QueryPerformanceCounter
0x180023354  mov     eax, dword ptr [rbp+PerformanceCount]
0x180023357  mov     rcx, 0FFFFFFFFFFFFh
0x180023361  shl     rax, 20h
0x180023365  xor     rax, qword ptr [rbp+PerformanceCount]
0x180023369  xor     rax, [rbp+arg_0]
0x18002336d  and     rax, rcx
0x180023370  mov     rcx, rax
0x180023373  cmp     rax, rbx
0x180023376  jnz     short loc_180023385
0x180023378  mov     rax, 2B992DDFA233h
0x180023382  mov     rcx, rax
0x180023385  mov     cs:__security_cookie, rcx
0x18002338c  mov     rbx, [rsp+20h+arg_18]
0x180023391  not     rax
0x180023394  mov     cs:__security_cookie_complement, rax
0x18002339b  add     rsp, 20h
0x18002339f  pop     rbp
0x1800233a0  retn
```
