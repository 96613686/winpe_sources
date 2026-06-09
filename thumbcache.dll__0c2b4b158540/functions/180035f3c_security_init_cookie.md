# __security_init_cookie

- ea: `0x180035f3c`
- end: `0x180035ff1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800357e0`

## callees

- `0x180035f3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180035f8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180035f8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035f7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035f7f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180035f9b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180035f9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180035f71`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180035f71`

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
0x180035f3c  mov     [rsp-8+arg_10], rbx
0x180035f41  push    rbp
0x180035f42  mov     rbp, rsp
0x180035f45  sub     rsp, 30h
0x180035f49  mov     rax, cs:__security_cookie
0x180035f50  mov     rbx, 2B992DDFA232h
0x180035f5a  cmp     rax, rbx
0x180035f5d  jnz     short loc_180035FDC
0x180035f5f  xor     eax, eax
0x180035f61  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180035f65  mov     [rbp+var_10], rax
0x180035f69  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180035f6d  mov     qword ptr [rbp+PerformanceCount], rax
0x180035f71  call    cs:__imp_GetSystemTimeAsFileTime
0x180035f77  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180035f7b  mov     [rbp+var_10], rax
0x180035f7f  call    cs:__imp_GetCurrentThreadId
0x180035f85  mov     eax, eax
0x180035f87  xor     [rbp+var_10], rax
0x180035f8b  call    cs:__imp_GetCurrentProcessId
0x180035f91  mov     eax, eax
0x180035f93  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180035f97  xor     [rbp+var_10], rax
0x180035f9b  call    cs:__imp_QueryPerformanceCounter
0x180035fa1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180035fa4  lea     rcx, [rbp+var_10]
0x180035fa8  shl     rax, 20h
0x180035fac  xor     rax, qword ptr [rbp+PerformanceCount]
0x180035fb0  xor     rax, [rbp+var_10]
0x180035fb4  xor     rax, rcx
0x180035fb7  mov     rcx, 0FFFFFFFFFFFFh
0x180035fc1  and     rax, rcx
0x180035fc4  mov     rcx, 2B992DDFA233h
0x180035fce  cmp     rax, rbx
0x180035fd1  cmovz   rax, rcx
0x180035fd5  mov     cs:__security_cookie, rax
0x180035fdc  mov     rbx, [rsp+30h+arg_10]
0x180035fe1  not     rax
0x180035fe4  mov     cs:__security_cookie_complement, rax
0x180035feb  add     rsp, 30h
0x180035fef  pop     rbp
0x180035ff0  retn
```
