# __security_init_cookie

- ea: `0x18000265c`
- end: `0x180002711`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800025b0`

## callees

- `0x18000265c`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800026bb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800026bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000269f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000269f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800026ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800026ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002691`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002691`

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
0x18000265c  mov     [rsp-8+arg_10], rbx
0x180002661  push    rbp
0x180002662  mov     rbp, rsp
0x180002665  sub     rsp, 30h
0x180002669  mov     rax, cs:__security_cookie
0x180002670  mov     rbx, 2B992DDFA232h
0x18000267a  cmp     rax, rbx
0x18000267d  jnz     short loc_1800026FC
0x18000267f  xor     eax, eax
0x180002681  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002685  mov     [rbp+var_10], rax
0x180002689  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000268d  mov     qword ptr [rbp+PerformanceCount], rax
0x180002691  call    cs:__imp_GetSystemTimeAsFileTime
0x180002697  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000269b  mov     [rbp+var_10], rax
0x18000269f  call    cs:__imp_GetCurrentThreadId
0x1800026a5  mov     eax, eax
0x1800026a7  xor     [rbp+var_10], rax
0x1800026ab  call    cs:__imp_GetCurrentProcessId
0x1800026b1  mov     eax, eax
0x1800026b3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800026b7  xor     [rbp+var_10], rax
0x1800026bb  call    cs:__imp_QueryPerformanceCounter
0x1800026c1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800026c4  lea     rcx, [rbp+var_10]
0x1800026c8  shl     rax, 20h
0x1800026cc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800026d0  xor     rax, [rbp+var_10]
0x1800026d4  xor     rax, rcx
0x1800026d7  mov     rcx, 0FFFFFFFFFFFFh
0x1800026e1  and     rax, rcx
0x1800026e4  mov     rcx, 2B992DDFA233h
0x1800026ee  cmp     rax, rbx
0x1800026f1  cmovz   rax, rcx
0x1800026f5  mov     cs:__security_cookie, rax
0x1800026fc  mov     rbx, [rsp+30h+arg_10]
0x180002701  not     rax
0x180002704  mov     cs:__security_cookie_complement, rax
0x18000270b  add     rsp, 30h
0x18000270f  pop     rbp
0x180002710  retn
```
