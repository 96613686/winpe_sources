# __security_init_cookie

- ea: `0x180012cd0`
- end: `0x180012d85`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012830`

## callees

- `0x180012cd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012d1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012d1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012d13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012d13`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012d05`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012d05`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012d2f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012d2f`

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
0x180012cd0  mov     [rsp-8+arg_10], rbx
0x180012cd5  push    rbp
0x180012cd6  mov     rbp, rsp
0x180012cd9  sub     rsp, 30h
0x180012cdd  mov     rax, cs:__security_cookie
0x180012ce4  mov     rbx, 2B992DDFA232h
0x180012cee  cmp     rax, rbx
0x180012cf1  jnz     short loc_180012D70
0x180012cf3  xor     eax, eax
0x180012cf5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180012cf9  mov     [rbp+var_10], rax
0x180012cfd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180012d01  mov     qword ptr [rbp+PerformanceCount], rax
0x180012d05  call    cs:__imp_GetSystemTimeAsFileTime
0x180012d0b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180012d0f  mov     [rbp+var_10], rax
0x180012d13  call    cs:__imp_GetCurrentThreadId
0x180012d19  mov     eax, eax
0x180012d1b  xor     [rbp+var_10], rax
0x180012d1f  call    cs:__imp_GetCurrentProcessId
0x180012d25  mov     eax, eax
0x180012d27  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180012d2b  xor     [rbp+var_10], rax
0x180012d2f  call    cs:__imp_QueryPerformanceCounter
0x180012d35  mov     eax, dword ptr [rbp+PerformanceCount]
0x180012d38  lea     rcx, [rbp+var_10]
0x180012d3c  shl     rax, 20h
0x180012d40  xor     rax, qword ptr [rbp+PerformanceCount]
0x180012d44  xor     rax, [rbp+var_10]
0x180012d48  xor     rax, rcx
0x180012d4b  mov     rcx, 0FFFFFFFFFFFFh
0x180012d55  and     rax, rcx
0x180012d58  mov     rcx, 2B992DDFA233h
0x180012d62  cmp     rax, rbx
0x180012d65  cmovz   rax, rcx
0x180012d69  mov     cs:__security_cookie, rax
0x180012d70  mov     rbx, [rsp+30h+arg_10]
0x180012d75  not     rax
0x180012d78  mov     cs:__security_cookie_complement, rax
0x180012d7f  add     rsp, 30h
0x180012d83  pop     rbp
0x180012d84  retn
```
