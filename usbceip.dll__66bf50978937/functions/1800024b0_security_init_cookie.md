# __security_init_cookie

- ea: `0x1800024b0`
- end: `0x180002565`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800023b0`

## callees

- `0x1800024b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800024ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800024ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800024f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800024f3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000250f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000250f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800024e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800024e5`

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
0x1800024b0  mov     [rsp-8+arg_10], rbx
0x1800024b5  push    rbp
0x1800024b6  mov     rbp, rsp
0x1800024b9  sub     rsp, 30h
0x1800024bd  mov     rax, cs:__security_cookie
0x1800024c4  mov     rbx, 2B992DDFA232h
0x1800024ce  cmp     rax, rbx
0x1800024d1  jnz     short loc_180002550
0x1800024d3  xor     eax, eax
0x1800024d5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800024d9  mov     [rbp+var_10], rax
0x1800024dd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800024e1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800024e5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800024eb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800024ef  mov     [rbp+var_10], rax
0x1800024f3  call    cs:__imp_GetCurrentThreadId
0x1800024f9  mov     eax, eax
0x1800024fb  xor     [rbp+var_10], rax
0x1800024ff  call    cs:__imp_GetCurrentProcessId
0x180002505  mov     eax, eax
0x180002507  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000250b  xor     [rbp+var_10], rax
0x18000250f  call    cs:__imp_QueryPerformanceCounter
0x180002515  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002518  lea     rcx, [rbp+var_10]
0x18000251c  shl     rax, 20h
0x180002520  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002524  xor     rax, [rbp+var_10]
0x180002528  xor     rax, rcx
0x18000252b  mov     rcx, 0FFFFFFFFFFFFh
0x180002535  and     rax, rcx
0x180002538  mov     rcx, 2B992DDFA233h
0x180002542  cmp     rax, rbx
0x180002545  cmovz   rax, rcx
0x180002549  mov     cs:__security_cookie, rax
0x180002550  mov     rbx, [rsp+30h+arg_10]
0x180002555  not     rax
0x180002558  mov     cs:__security_cookie_complement, rax
0x18000255f  add     rsp, 30h
0x180002563  pop     rbp
0x180002564  retn
```
