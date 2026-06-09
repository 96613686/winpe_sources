# __security_init_cookie

- ea: `0x1800b9f0c`
- end: `0x1800b9fc1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b99a0`

## callees

- `0x1800b9f0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b9f5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b9f5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b9f4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b9f4f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b9f6b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b9f6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800b9f41`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800b9f41`

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
0x1800b9f0c  mov     [rsp-8+arg_10], rbx
0x1800b9f11  push    rbp
0x1800b9f12  mov     rbp, rsp
0x1800b9f15  sub     rsp, 30h
0x1800b9f19  mov     rax, cs:__security_cookie
0x1800b9f20  mov     rbx, 2B992DDFA232h
0x1800b9f2a  cmp     rax, rbx
0x1800b9f2d  jnz     short loc_1800B9FAC
0x1800b9f2f  xor     eax, eax
0x1800b9f31  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800b9f35  mov     [rbp+var_10], rax
0x1800b9f39  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800b9f3d  mov     qword ptr [rbp+PerformanceCount], rax
0x1800b9f41  call    cs:__imp_GetSystemTimeAsFileTime
0x1800b9f47  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800b9f4b  mov     [rbp+var_10], rax
0x1800b9f4f  call    cs:__imp_GetCurrentThreadId
0x1800b9f55  mov     eax, eax
0x1800b9f57  xor     [rbp+var_10], rax
0x1800b9f5b  call    cs:__imp_GetCurrentProcessId
0x1800b9f61  mov     eax, eax
0x1800b9f63  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800b9f67  xor     [rbp+var_10], rax
0x1800b9f6b  call    cs:__imp_QueryPerformanceCounter
0x1800b9f71  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800b9f74  lea     rcx, [rbp+var_10]
0x1800b9f78  shl     rax, 20h
0x1800b9f7c  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800b9f80  xor     rax, [rbp+var_10]
0x1800b9f84  xor     rax, rcx
0x1800b9f87  mov     rcx, 0FFFFFFFFFFFFh
0x1800b9f91  and     rax, rcx
0x1800b9f94  mov     rcx, 2B992DDFA233h
0x1800b9f9e  cmp     rax, rbx
0x1800b9fa1  cmovz   rax, rcx
0x1800b9fa5  mov     cs:__security_cookie, rax
0x1800b9fac  mov     rbx, [rsp+30h+arg_10]
0x1800b9fb1  not     rax
0x1800b9fb4  mov     cs:__security_cookie_complement, rax
0x1800b9fbb  add     rsp, 30h
0x1800b9fbf  pop     rbp
0x1800b9fc0  retn
```
