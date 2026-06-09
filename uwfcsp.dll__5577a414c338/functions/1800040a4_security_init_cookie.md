# __security_init_cookie

- ea: `0x1800040a4`
- end: `0x180004181`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003830`

## callees

- `0x1800040a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800040f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800040f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800040eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800040eb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000412e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000412e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800040dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800040dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004103`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004113`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004103`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004113`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x1800040a4  mov     [rsp-8+arg_18], rbx
0x1800040a9  push    rbp
0x1800040aa  mov     rbp, rsp
0x1800040ad  sub     rsp, 20h
0x1800040b1  xor     eax, eax
0x1800040b3  mov     rbx, 2B992DDFA232h
0x1800040bd  mov     [rbp+arg_0], rax
0x1800040c1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800040c5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800040c9  mov     rax, cs:__security_cookie
0x1800040d0  cmp     rax, rbx
0x1800040d3  jnz     loc_18000416C
0x1800040d9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800040dd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800040e3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800040e7  mov     [rbp+arg_0], rax
0x1800040eb  call    cs:__imp_GetCurrentProcessId
0x1800040f1  mov     eax, eax
0x1800040f3  xor     [rbp+arg_0], rax
0x1800040f7  call    cs:__imp_GetCurrentThreadId
0x1800040fd  mov     eax, eax
0x1800040ff  xor     [rbp+arg_0], rax
0x180004103  call    cs:__imp_GetTickCount
0x180004109  mov     eax, eax
0x18000410b  shl     rax, 18h
0x18000410f  xor     [rbp+arg_0], rax
0x180004113  call    cs:__imp_GetTickCount
0x180004119  mov     eax, eax
0x18000411b  lea     rcx, [rbp+arg_0]
0x18000411f  xor     rax, [rbp+arg_0]
0x180004123  xor     rax, rcx
0x180004126  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000412a  mov     [rbp+arg_0], rax
0x18000412e  call    cs:__imp_QueryPerformanceCounter
0x180004134  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004137  mov     rcx, 0FFFFFFFFFFFFh
0x180004141  shl     rax, 20h
0x180004145  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004149  xor     rax, [rbp+arg_0]
0x18000414d  and     rax, rcx
0x180004150  mov     rcx, rax
0x180004153  cmp     rax, rbx
0x180004156  jnz     short loc_180004165
0x180004158  mov     rax, 2B992DDFA233h
0x180004162  mov     rcx, rax
0x180004165  mov     cs:__security_cookie, rcx
0x18000416c  mov     rbx, [rsp+20h+arg_18]
0x180004171  not     rax
0x180004174  mov     cs:__security_cookie_complement, rax
0x18000417b  add     rsp, 20h
0x18000417f  pop     rbp
0x180004180  retn
```
