# __security_init_cookie

- ea: `0x1800020b4`
- end: `0x180002191`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800019c0`

## callees

- `0x1800020b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002107`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002107`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800020fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800020fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002113`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002123`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002113`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002123`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800020ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800020ed`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000213e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000213e`

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
0x1800020b4  mov     [rsp-8+arg_18], rbx
0x1800020b9  push    rbp
0x1800020ba  mov     rbp, rsp
0x1800020bd  sub     rsp, 20h
0x1800020c1  xor     eax, eax
0x1800020c3  mov     rbx, 2B992DDFA232h
0x1800020cd  mov     [rbp+arg_0], rax
0x1800020d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800020d5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800020d9  mov     rax, cs:__security_cookie
0x1800020e0  cmp     rax, rbx
0x1800020e3  jnz     loc_18000217C
0x1800020e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800020ed  call    cs:__imp_GetSystemTimeAsFileTime
0x1800020f3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800020f7  mov     [rbp+arg_0], rax
0x1800020fb  call    cs:__imp_GetCurrentProcessId
0x180002101  mov     eax, eax
0x180002103  xor     [rbp+arg_0], rax
0x180002107  call    cs:__imp_GetCurrentThreadId
0x18000210d  mov     eax, eax
0x18000210f  xor     [rbp+arg_0], rax
0x180002113  call    cs:__imp_GetTickCount
0x180002119  mov     eax, eax
0x18000211b  shl     rax, 18h
0x18000211f  xor     [rbp+arg_0], rax
0x180002123  call    cs:__imp_GetTickCount
0x180002129  mov     eax, eax
0x18000212b  lea     rcx, [rbp+arg_0]
0x18000212f  xor     rax, [rbp+arg_0]
0x180002133  xor     rax, rcx
0x180002136  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000213a  mov     [rbp+arg_0], rax
0x18000213e  call    cs:__imp_QueryPerformanceCounter
0x180002144  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002147  mov     rcx, 0FFFFFFFFFFFFh
0x180002151  shl     rax, 20h
0x180002155  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002159  xor     rax, [rbp+arg_0]
0x18000215d  and     rax, rcx
0x180002160  mov     rcx, rax
0x180002163  cmp     rax, rbx
0x180002166  jnz     short loc_180002175
0x180002168  mov     rax, 2B992DDFA233h
0x180002172  mov     rcx, rax
0x180002175  mov     cs:__security_cookie, rcx
0x18000217c  mov     rbx, [rsp+20h+arg_18]
0x180002181  not     rax
0x180002184  mov     cs:__security_cookie_complement, rax
0x18000218b  add     rsp, 20h
0x18000218f  pop     rbp
0x180002190  retn
```
