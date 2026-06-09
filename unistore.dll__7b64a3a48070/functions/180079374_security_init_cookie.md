# __security_init_cookie

- ea: `0x180079374`
- end: `0x180079451`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180078d10`

## callees

- `0x180079374`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800793c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800793c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800793bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800793bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800793d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800793e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800793d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800793e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800793ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800793ad`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800793fe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800793fe`

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
0x180079374  mov     [rsp-8+arg_18], rbx
0x180079379  push    rbp
0x18007937a  mov     rbp, rsp
0x18007937d  sub     rsp, 20h
0x180079381  xor     eax, eax
0x180079383  mov     rbx, 2B992DDFA232h
0x18007938d  mov     [rbp+arg_0], rax
0x180079391  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180079395  mov     qword ptr [rbp+PerformanceCount], rax
0x180079399  mov     rax, cs:__security_cookie
0x1800793a0  cmp     rax, rbx
0x1800793a3  jnz     loc_18007943C
0x1800793a9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800793ad  call    cs:__imp_GetSystemTimeAsFileTime
0x1800793b3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800793b7  mov     [rbp+arg_0], rax
0x1800793bb  call    cs:__imp_GetCurrentProcessId
0x1800793c1  mov     eax, eax
0x1800793c3  xor     [rbp+arg_0], rax
0x1800793c7  call    cs:__imp_GetCurrentThreadId
0x1800793cd  mov     eax, eax
0x1800793cf  xor     [rbp+arg_0], rax
0x1800793d3  call    cs:__imp_GetTickCount
0x1800793d9  mov     eax, eax
0x1800793db  shl     rax, 18h
0x1800793df  xor     [rbp+arg_0], rax
0x1800793e3  call    cs:__imp_GetTickCount
0x1800793e9  mov     eax, eax
0x1800793eb  lea     rcx, [rbp+arg_0]
0x1800793ef  xor     rax, [rbp+arg_0]
0x1800793f3  xor     rax, rcx
0x1800793f6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800793fa  mov     [rbp+arg_0], rax
0x1800793fe  call    cs:__imp_QueryPerformanceCounter
0x180079404  mov     eax, dword ptr [rbp+PerformanceCount]
0x180079407  mov     rcx, 0FFFFFFFFFFFFh
0x180079411  shl     rax, 20h
0x180079415  xor     rax, qword ptr [rbp+PerformanceCount]
0x180079419  xor     rax, [rbp+arg_0]
0x18007941d  and     rax, rcx
0x180079420  mov     rcx, rax
0x180079423  cmp     rax, rbx
0x180079426  jnz     short loc_180079435
0x180079428  mov     rax, 2B992DDFA233h
0x180079432  mov     rcx, rax
0x180079435  mov     cs:__security_cookie, rcx
0x18007943c  mov     rbx, [rsp+20h+arg_18]
0x180079441  not     rax
0x180079444  mov     cs:__security_cookie_complement, rax
0x18007944b  add     rsp, 20h
0x18007944f  pop     rbp
0x180079450  retn
```
