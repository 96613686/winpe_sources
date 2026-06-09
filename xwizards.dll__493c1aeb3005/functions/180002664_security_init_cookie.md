# __security_init_cookie

- ea: `0x180002664`
- end: `0x180002741`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001de0`

## callees

- `0x180002664`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800026ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800026ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800026b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800026b7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800026ee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800026ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800026c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800026d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800026c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800026d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000269d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000269d`

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
0x180002664  mov     [rsp-8+arg_18], rbx
0x180002669  push    rbp
0x18000266a  mov     rbp, rsp
0x18000266d  sub     rsp, 20h
0x180002671  xor     eax, eax
0x180002673  mov     rbx, 2B992DDFA232h
0x18000267d  mov     [rbp+arg_0], rax
0x180002681  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002685  mov     qword ptr [rbp+PerformanceCount], rax
0x180002689  mov     rax, cs:__security_cookie
0x180002690  cmp     rax, rbx
0x180002693  jnz     loc_18000272C
0x180002699  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000269d  call    cs:__imp_GetSystemTimeAsFileTime
0x1800026a3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800026a7  mov     [rbp+arg_0], rax
0x1800026ab  call    cs:__imp_GetCurrentProcessId
0x1800026b1  mov     eax, eax
0x1800026b3  xor     [rbp+arg_0], rax
0x1800026b7  call    cs:__imp_GetCurrentThreadId
0x1800026bd  mov     eax, eax
0x1800026bf  xor     [rbp+arg_0], rax
0x1800026c3  call    cs:__imp_GetTickCount
0x1800026c9  mov     eax, eax
0x1800026cb  shl     rax, 18h
0x1800026cf  xor     [rbp+arg_0], rax
0x1800026d3  call    cs:__imp_GetTickCount
0x1800026d9  mov     eax, eax
0x1800026db  lea     rcx, [rbp+arg_0]
0x1800026df  xor     rax, [rbp+arg_0]
0x1800026e3  xor     rax, rcx
0x1800026e6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800026ea  mov     [rbp+arg_0], rax
0x1800026ee  call    cs:__imp_QueryPerformanceCounter
0x1800026f4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800026f7  mov     rcx, 0FFFFFFFFFFFFh
0x180002701  shl     rax, 20h
0x180002705  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002709  xor     rax, [rbp+arg_0]
0x18000270d  and     rax, rcx
0x180002710  mov     rcx, rax
0x180002713  cmp     rax, rbx
0x180002716  jnz     short loc_180002725
0x180002718  mov     rax, 2B992DDFA233h
0x180002722  mov     rcx, rax
0x180002725  mov     cs:__security_cookie, rcx
0x18000272c  mov     rbx, [rsp+20h+arg_18]
0x180002731  not     rax
0x180002734  mov     cs:__security_cookie_complement, rax
0x18000273b  add     rsp, 20h
0x18000273f  pop     rbp
0x180002740  retn
```
