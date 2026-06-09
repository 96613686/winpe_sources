# __security_init_cookie

- ea: `0x1800022dc`
- end: `0x180002391`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001de0`

## callees

- `0x1800022dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000231f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000231f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000232b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000232b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002311`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002311`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000233b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000233b`

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
0x1800022dc  mov     [rsp-8+arg_10], rbx
0x1800022e1  push    rbp
0x1800022e2  mov     rbp, rsp
0x1800022e5  sub     rsp, 30h
0x1800022e9  mov     rax, cs:__security_cookie
0x1800022f0  mov     rbx, 2B992DDFA232h
0x1800022fa  cmp     rax, rbx
0x1800022fd  jnz     short loc_18000237C
0x1800022ff  xor     eax, eax
0x180002301  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002305  mov     [rbp+var_10], rax
0x180002309  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000230d  mov     qword ptr [rbp+PerformanceCount], rax
0x180002311  call    cs:__imp_GetSystemTimeAsFileTime
0x180002317  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000231b  mov     [rbp+var_10], rax
0x18000231f  call    cs:__imp_GetCurrentThreadId
0x180002325  mov     eax, eax
0x180002327  xor     [rbp+var_10], rax
0x18000232b  call    cs:__imp_GetCurrentProcessId
0x180002331  mov     eax, eax
0x180002333  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002337  xor     [rbp+var_10], rax
0x18000233b  call    cs:__imp_QueryPerformanceCounter
0x180002341  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002344  lea     rcx, [rbp+var_10]
0x180002348  shl     rax, 20h
0x18000234c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002350  xor     rax, [rbp+var_10]
0x180002354  xor     rax, rcx
0x180002357  mov     rcx, 0FFFFFFFFFFFFh
0x180002361  and     rax, rcx
0x180002364  mov     rcx, 2B992DDFA233h
0x18000236e  cmp     rax, rbx
0x180002371  cmovz   rax, rcx
0x180002375  mov     cs:__security_cookie, rax
0x18000237c  mov     rbx, [rsp+30h+arg_10]
0x180002381  not     rax
0x180002384  mov     cs:__security_cookie_complement, rax
0x18000238b  add     rsp, 30h
0x18000238f  pop     rbp
0x180002390  retn
```
