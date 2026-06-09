# __security_init_cookie

- ea: `0x1400024d0`
- end: `0x140002585`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002100`

## callees

- `0x1400024d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000251f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000251f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002513`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002513`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000252f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000252f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002505`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002505`

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
0x1400024d0  mov     [rsp-8+arg_10], rbx
0x1400024d5  push    rbp
0x1400024d6  mov     rbp, rsp
0x1400024d9  sub     rsp, 30h
0x1400024dd  mov     rax, cs:__security_cookie
0x1400024e4  mov     rbx, 2B992DDFA232h
0x1400024ee  cmp     rax, rbx
0x1400024f1  jnz     short loc_140002570
0x1400024f3  xor     eax, eax
0x1400024f5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400024f9  mov     [rbp+var_10], rax
0x1400024fd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002501  mov     qword ptr [rbp+PerformanceCount], rax
0x140002505  call    cs:__imp_GetSystemTimeAsFileTime
0x14000250b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000250f  mov     [rbp+var_10], rax
0x140002513  call    cs:__imp_GetCurrentThreadId
0x140002519  mov     eax, eax
0x14000251b  xor     [rbp+var_10], rax
0x14000251f  call    cs:__imp_GetCurrentProcessId
0x140002525  mov     eax, eax
0x140002527  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000252b  xor     [rbp+var_10], rax
0x14000252f  call    cs:__imp_QueryPerformanceCounter
0x140002535  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002538  lea     rcx, [rbp+var_10]
0x14000253c  shl     rax, 20h
0x140002540  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002544  xor     rax, [rbp+var_10]
0x140002548  xor     rax, rcx
0x14000254b  mov     rcx, 0FFFFFFFFFFFFh
0x140002555  and     rax, rcx
0x140002558  mov     rcx, 2B992DDFA233h
0x140002562  cmp     rax, rbx
0x140002565  cmovz   rax, rcx
0x140002569  mov     cs:__security_cookie, rax
0x140002570  mov     rbx, [rsp+30h+arg_10]
0x140002575  not     rax
0x140002578  mov     cs:__security_cookie_complement, rax
0x14000257f  add     rsp, 30h
0x140002583  pop     rbp
0x140002584  retn
```
