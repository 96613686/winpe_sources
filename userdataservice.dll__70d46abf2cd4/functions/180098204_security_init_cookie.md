# __security_init_cookie

- ea: `0x180098204`
- end: `0x1800982e1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180097a80`

## callees

- `0x180098204`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098257`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098257`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009824b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009824b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180098263`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180098273`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180098263`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180098273`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18009823d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18009823d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18009828e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18009828e`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x180098204  mov     [rsp-8+arg_18], rbx
0x180098209  push    rbp
0x18009820a  mov     rbp, rsp
0x18009820d  sub     rsp, 20h
0x180098211  xor     eax, eax
0x180098213  mov     rbx, 2B992DDFA232h
0x18009821d  mov     [rbp+arg_0], rax
0x180098221  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180098225  mov     qword ptr [rbp+PerformanceCount], rax
0x180098229  mov     rax, cs:__security_cookie
0x180098230  cmp     rax, rbx
0x180098233  jnz     loc_1800982CC
0x180098239  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18009823d  call    cs:__imp_GetSystemTimeAsFileTime
0x180098243  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180098247  mov     [rbp+arg_0], rax
0x18009824b  call    cs:__imp_GetCurrentProcessId
0x180098251  mov     eax, eax
0x180098253  xor     [rbp+arg_0], rax
0x180098257  call    cs:__imp_GetCurrentThreadId
0x18009825d  mov     eax, eax
0x18009825f  xor     [rbp+arg_0], rax
0x180098263  call    cs:__imp_GetTickCount
0x180098269  mov     eax, eax
0x18009826b  shl     rax, 18h
0x18009826f  xor     [rbp+arg_0], rax
0x180098273  call    cs:__imp_GetTickCount
0x180098279  mov     eax, eax
0x18009827b  lea     rcx, [rbp+arg_0]
0x18009827f  xor     rax, [rbp+arg_0]
0x180098283  xor     rax, rcx
0x180098286  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18009828a  mov     [rbp+arg_0], rax
0x18009828e  call    cs:__imp_QueryPerformanceCounter
0x180098294  mov     eax, dword ptr [rbp+PerformanceCount]
0x180098297  mov     rcx, 0FFFFFFFFFFFFh
0x1800982a1  shl     rax, 20h
0x1800982a5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800982a9  xor     rax, [rbp+arg_0]
0x1800982ad  and     rax, rcx
0x1800982b0  mov     rcx, rax
0x1800982b3  cmp     rax, rbx
0x1800982b6  jnz     short loc_1800982C5
0x1800982b8  mov     rax, 2B992DDFA233h
0x1800982c2  mov     rcx, rax
0x1800982c5  mov     cs:__security_cookie, rcx
0x1800982cc  mov     rbx, [rsp+20h+arg_18]
0x1800982d1  not     rax
0x1800982d4  mov     cs:__security_cookie_complement, rax
0x1800982db  add     rsp, 20h
0x1800982df  pop     rbp
0x1800982e0  retn
```
