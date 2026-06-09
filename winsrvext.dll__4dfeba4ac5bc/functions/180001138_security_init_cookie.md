# __security_init_cookie

- ea: `0x180001138`
- end: `0x18000120c`
- name: `__security_init_cookie`
- size: `212`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004c10`

## callees

- `0x180001138`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800011c7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800011c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001184`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001184`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001190`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001190`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000119c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800011ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000119c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800011ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001176`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001176`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rcx
  _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  v1 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  if ( !_security_cookie || _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v1);
    v1 = (_FILETIME)((unsigned __int64)&v1 ^ *(unsigned __int64 *)&v1 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = 0x2B992DDFA232LL;
    if ( ((*(_QWORD *)&v1
         ^ PerformanceCount.QuadPart
         ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
        & 0xFFFFFFFFFFFFLL) != 0 )
      v0 = (*(_QWORD *)&v1
          ^ PerformanceCount.QuadPart
          ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
         & 0xFFFFFFFFFFFFLL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180001138  mov     [rsp-8+arg_18], rbx
0x18000113d  push    rbp
0x18000113e  mov     rbp, rsp
0x180001141  sub     rsp, 20h
0x180001145  mov     rcx, cs:__security_cookie
0x18000114c  xor     eax, eax
0x18000114e  mov     [rbp+arg_0], rax
0x180001152  mov     rbx, 2B992DDFA232h
0x18000115c  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001160  mov     qword ptr [rbp+PerformanceCount], rax
0x180001164  test    rcx, rcx
0x180001167  jz      short loc_180001172
0x180001169  cmp     rcx, rbx
0x18000116c  jnz     loc_1800011F7
0x180001172  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001176  call    cs:__imp_GetSystemTimeAsFileTime
0x18000117c  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001180  mov     [rbp+arg_0], rax
0x180001184  call    cs:__imp_GetCurrentProcessId
0x18000118a  mov     eax, eax
0x18000118c  xor     [rbp+arg_0], rax
0x180001190  call    cs:__imp_GetCurrentThreadId
0x180001196  mov     eax, eax
0x180001198  xor     [rbp+arg_0], rax
0x18000119c  call    cs:__imp_GetTickCount
0x1800011a2  mov     eax, eax
0x1800011a4  shl     rax, 18h
0x1800011a8  xor     [rbp+arg_0], rax
0x1800011ac  call    cs:__imp_GetTickCount
0x1800011b2  mov     eax, eax
0x1800011b4  lea     rcx, [rbp+arg_0]
0x1800011b8  xor     rax, [rbp+arg_0]
0x1800011bc  xor     rax, rcx
0x1800011bf  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800011c3  mov     [rbp+arg_0], rax
0x1800011c7  call    cs:__imp_QueryPerformanceCounter
0x1800011cd  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800011d0  mov     rcx, 0FFFFFFFFFFFFh
0x1800011da  shl     rax, 20h
0x1800011de  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800011e2  xor     rax, [rbp+arg_0]
0x1800011e6  and     rax, rcx
0x1800011e9  mov     rcx, rbx
0x1800011ec  cmovnz  rcx, rax
0x1800011f0  mov     cs:__security_cookie, rcx
0x1800011f7  mov     rbx, [rsp+20h+arg_18]
0x1800011fc  not     rcx
0x1800011ff  mov     cs:__security_cookie_complement, rcx
0x180001206  add     rsp, 20h
0x18000120a  pop     rbp
0x18000120b  retn
```
