# __security_init_cookie

- ea: `0x14002b0fc`
- end: `0x14002b1b1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002ab90`

## callees

- `0x14002b0fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002b13f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002b13f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14002b14b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14002b14b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002b131`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002b131`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14002b15b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14002b15b`

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
0x14002b0fc  mov     [rsp-8+arg_10], rbx
0x14002b101  push    rbp
0x14002b102  mov     rbp, rsp
0x14002b105  sub     rsp, 30h
0x14002b109  mov     rax, cs:__security_cookie
0x14002b110  mov     rbx, 2B992DDFA232h
0x14002b11a  cmp     rax, rbx
0x14002b11d  jnz     short loc_14002B19C
0x14002b11f  xor     eax, eax
0x14002b121  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14002b125  mov     [rbp+var_10], rax
0x14002b129  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x14002b12d  mov     qword ptr [rbp+PerformanceCount], rax
0x14002b131  call    cs:__imp_GetSystemTimeAsFileTime
0x14002b137  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14002b13b  mov     [rbp+var_10], rax
0x14002b13f  call    cs:__imp_GetCurrentThreadId
0x14002b145  mov     eax, eax
0x14002b147  xor     [rbp+var_10], rax
0x14002b14b  call    cs:__imp_GetCurrentProcessId
0x14002b151  mov     eax, eax
0x14002b153  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14002b157  xor     [rbp+var_10], rax
0x14002b15b  call    cs:__imp_QueryPerformanceCounter
0x14002b161  mov     eax, dword ptr [rbp+PerformanceCount]
0x14002b164  lea     rcx, [rbp+var_10]
0x14002b168  shl     rax, 20h
0x14002b16c  xor     rax, qword ptr [rbp+PerformanceCount]
0x14002b170  xor     rax, [rbp+var_10]
0x14002b174  xor     rax, rcx
0x14002b177  mov     rcx, 0FFFFFFFFFFFFh
0x14002b181  and     rax, rcx
0x14002b184  mov     rcx, 2B992DDFA233h
0x14002b18e  cmp     rax, rbx
0x14002b191  cmovz   rax, rcx
0x14002b195  mov     cs:__security_cookie, rax
0x14002b19c  mov     rbx, [rsp+30h+arg_10]
0x14002b1a1  not     rax
0x14002b1a4  mov     cs:__security_cookie_complement, rax
0x14002b1ab  add     rsp, 30h
0x14002b1af  pop     rbp
0x14002b1b0  retn
```
