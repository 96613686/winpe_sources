# __security_init_cookie

- ea: `0x140133770`
- end: `0x140133825`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401332c0`

## callees

- `0x140133770`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401337b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401337b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1401337bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1401337bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1401337a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1401337a5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1401337cf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1401337cf`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x140133770  mov     [rsp-8+arg_10], rbx
0x140133775  push    rbp
0x140133776  mov     rbp, rsp
0x140133779  sub     rsp, 30h
0x14013377d  mov     rax, cs:__security_cookie
0x140133784  mov     rbx, 2B992DDFA232h
0x14013378e  cmp     rax, rbx
0x140133791  jnz     short loc_140133810
0x140133793  xor     eax, eax
0x140133795  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140133799  mov     [rbp+var_10], rax
0x14013379d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1401337a1  mov     qword ptr [rbp+PerformanceCount], rax
0x1401337a5  call    cs:__imp_GetSystemTimeAsFileTime
0x1401337ab  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1401337af  mov     [rbp+var_10], rax
0x1401337b3  call    cs:__imp_GetCurrentThreadId
0x1401337b9  mov     eax, eax
0x1401337bb  xor     [rbp+var_10], rax
0x1401337bf  call    cs:__imp_GetCurrentProcessId
0x1401337c5  mov     eax, eax
0x1401337c7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1401337cb  xor     [rbp+var_10], rax
0x1401337cf  call    cs:__imp_QueryPerformanceCounter
0x1401337d5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1401337d8  lea     rcx, [rbp+var_10]
0x1401337dc  shl     rax, 20h
0x1401337e0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1401337e4  xor     rax, [rbp+var_10]
0x1401337e8  xor     rax, rcx
0x1401337eb  mov     rcx, 0FFFFFFFFFFFFh
0x1401337f5  and     rax, rcx
0x1401337f8  mov     rcx, 2B992DDFA233h
0x140133802  cmp     rax, rbx
0x140133805  cmovz   rax, rcx
0x140133809  mov     cs:__security_cookie, rax
0x140133810  mov     rbx, [rsp+30h+arg_10]
0x140133815  not     rax
0x140133818  mov     cs:__security_cookie_complement, rax
0x14013381f  add     rsp, 30h
0x140133823  pop     rbp
0x140133824  retn
```
