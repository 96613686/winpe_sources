# __security_init_cookie

- ea: `0x180002008`
- end: `0x1800020e5`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001e90`

## callees

- `0x180002008`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000205b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000205b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000204f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000204f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002092`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002092`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002067`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002077`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002067`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002077`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002041`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002041`

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
0x180002008  mov     [rsp-8+arg_18], rbx
0x18000200d  push    rbp
0x18000200e  mov     rbp, rsp
0x180002011  sub     rsp, 20h
0x180002015  xor     eax, eax
0x180002017  mov     rbx, 2B992DDFA232h
0x180002021  mov     [rbp+arg_0], rax
0x180002025  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002029  mov     qword ptr [rbp+PerformanceCount], rax
0x18000202d  mov     rax, cs:__security_cookie
0x180002034  cmp     rax, rbx
0x180002037  jnz     loc_1800020D0
0x18000203d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002041  call    cs:__imp_GetSystemTimeAsFileTime
0x180002047  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000204b  mov     [rbp+arg_0], rax
0x18000204f  call    cs:__imp_GetCurrentProcessId
0x180002055  mov     eax, eax
0x180002057  xor     [rbp+arg_0], rax
0x18000205b  call    cs:__imp_GetCurrentThreadId
0x180002061  mov     eax, eax
0x180002063  xor     [rbp+arg_0], rax
0x180002067  call    cs:__imp_GetTickCount
0x18000206d  mov     eax, eax
0x18000206f  shl     rax, 18h
0x180002073  xor     [rbp+arg_0], rax
0x180002077  call    cs:__imp_GetTickCount
0x18000207d  mov     eax, eax
0x18000207f  lea     rcx, [rbp+arg_0]
0x180002083  xor     rax, [rbp+arg_0]
0x180002087  xor     rax, rcx
0x18000208a  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000208e  mov     [rbp+arg_0], rax
0x180002092  call    cs:__imp_QueryPerformanceCounter
0x180002098  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000209b  mov     rcx, 0FFFFFFFFFFFFh
0x1800020a5  shl     rax, 20h
0x1800020a9  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800020ad  xor     rax, [rbp+arg_0]
0x1800020b1  and     rax, rcx
0x1800020b4  mov     rcx, rax
0x1800020b7  cmp     rax, rbx
0x1800020ba  jnz     short loc_1800020C9
0x1800020bc  mov     rax, 2B992DDFA233h
0x1800020c6  mov     rcx, rax
0x1800020c9  mov     cs:__security_cookie, rcx
0x1800020d0  mov     rbx, [rsp+20h+arg_18]
0x1800020d5  not     rax
0x1800020d8  mov     cs:__security_cookie_complement, rax
0x1800020df  add     rsp, 20h
0x1800020e3  pop     rbp
0x1800020e4  retn
```
