# __security_init_cookie

- ea: `0x180002630`
- end: `0x1800026e5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800021e0`

## callees

- `0x180002630`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002673`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002673`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000267f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000267f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000268f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000268f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002665`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002665`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x180002630  mov     [rsp-8+arg_10], rbx
0x180002635  push    rbp
0x180002636  mov     rbp, rsp
0x180002639  sub     rsp, 30h
0x18000263d  mov     rax, cs:__security_cookie
0x180002644  mov     rbx, 2B992DDFA232h
0x18000264e  cmp     rax, rbx
0x180002651  jnz     short loc_1800026D0
0x180002653  xor     eax, eax
0x180002655  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002659  mov     [rbp+var_10], rax
0x18000265d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002661  mov     qword ptr [rbp+PerformanceCount], rax
0x180002665  call    cs:__imp_GetSystemTimeAsFileTime
0x18000266b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000266f  mov     [rbp+var_10], rax
0x180002673  call    cs:__imp_GetCurrentThreadId
0x180002679  mov     eax, eax
0x18000267b  xor     [rbp+var_10], rax
0x18000267f  call    cs:__imp_GetCurrentProcessId
0x180002685  mov     eax, eax
0x180002687  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000268b  xor     [rbp+var_10], rax
0x18000268f  call    cs:__imp_QueryPerformanceCounter
0x180002695  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002698  lea     rcx, [rbp+var_10]
0x18000269c  shl     rax, 20h
0x1800026a0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800026a4  xor     rax, [rbp+var_10]
0x1800026a8  xor     rax, rcx
0x1800026ab  mov     rcx, 0FFFFFFFFFFFFh
0x1800026b5  and     rax, rcx
0x1800026b8  mov     rcx, 2B992DDFA233h
0x1800026c2  cmp     rax, rbx
0x1800026c5  cmovz   rax, rcx
0x1800026c9  mov     cs:__security_cookie, rax
0x1800026d0  mov     rbx, [rsp+30h+arg_10]
0x1800026d5  not     rax
0x1800026d8  mov     cs:__security_cookie_complement, rax
0x1800026df  add     rsp, 30h
0x1800026e3  pop     rbp
0x1800026e4  retn
```
