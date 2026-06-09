# __security_init_cookie

- ea: `0x14002d5dc`
- end: `0x14002d691`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002d070`

## callees

- `0x14002d5dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002d61f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002d61f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14002d62b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14002d62b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002d611`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002d611`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14002d63b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14002d63b`

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
0x14002d5dc  mov     [rsp-8+arg_10], rbx
0x14002d5e1  push    rbp
0x14002d5e2  mov     rbp, rsp
0x14002d5e5  sub     rsp, 30h
0x14002d5e9  mov     rax, cs:__security_cookie
0x14002d5f0  mov     rbx, 2B992DDFA232h
0x14002d5fa  cmp     rax, rbx
0x14002d5fd  jnz     short loc_14002D67C
0x14002d5ff  xor     eax, eax
0x14002d601  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14002d605  mov     [rbp+var_10], rax
0x14002d609  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x14002d60d  mov     qword ptr [rbp+PerformanceCount], rax
0x14002d611  call    cs:__imp_GetSystemTimeAsFileTime
0x14002d617  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14002d61b  mov     [rbp+var_10], rax
0x14002d61f  call    cs:__imp_GetCurrentThreadId
0x14002d625  mov     eax, eax
0x14002d627  xor     [rbp+var_10], rax
0x14002d62b  call    cs:__imp_GetCurrentProcessId
0x14002d631  mov     eax, eax
0x14002d633  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14002d637  xor     [rbp+var_10], rax
0x14002d63b  call    cs:__imp_QueryPerformanceCounter
0x14002d641  mov     eax, dword ptr [rbp+PerformanceCount]
0x14002d644  lea     rcx, [rbp+var_10]
0x14002d648  shl     rax, 20h
0x14002d64c  xor     rax, qword ptr [rbp+PerformanceCount]
0x14002d650  xor     rax, [rbp+var_10]
0x14002d654  xor     rax, rcx
0x14002d657  mov     rcx, 0FFFFFFFFFFFFh
0x14002d661  and     rax, rcx
0x14002d664  mov     rcx, 2B992DDFA233h
0x14002d66e  cmp     rax, rbx
0x14002d671  cmovz   rax, rcx
0x14002d675  mov     cs:__security_cookie, rax
0x14002d67c  mov     rbx, [rsp+30h+arg_10]
0x14002d681  not     rax
0x14002d684  mov     cs:__security_cookie_complement, rax
0x14002d68b  add     rsp, 30h
0x14002d68f  pop     rbp
0x14002d690  retn
```
