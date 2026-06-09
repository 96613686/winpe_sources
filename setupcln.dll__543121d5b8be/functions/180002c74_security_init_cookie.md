# __security_init_cookie

- ea: `0x180002c74`
- end: `0x180002d51`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002720`

## callees

- `0x180002c74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002cbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002cbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002cc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002cc7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002cfe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002cfe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002cd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002ce3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002cd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002ce3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002cad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002cad`

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
0x180002c74  mov     [rsp-8+arg_18], rbx
0x180002c79  push    rbp
0x180002c7a  mov     rbp, rsp
0x180002c7d  sub     rsp, 20h
0x180002c81  xor     eax, eax
0x180002c83  mov     rbx, 2B992DDFA232h
0x180002c8d  mov     [rbp+arg_0], rax
0x180002c91  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002c95  mov     qword ptr [rbp+PerformanceCount], rax
0x180002c99  mov     rax, cs:__security_cookie
0x180002ca0  cmp     rax, rbx
0x180002ca3  jnz     loc_180002D3C
0x180002ca9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002cad  call    cs:__imp_GetSystemTimeAsFileTime
0x180002cb3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002cb7  mov     [rbp+arg_0], rax
0x180002cbb  call    cs:__imp_GetCurrentProcessId
0x180002cc1  mov     eax, eax
0x180002cc3  xor     [rbp+arg_0], rax
0x180002cc7  call    cs:__imp_GetCurrentThreadId
0x180002ccd  mov     eax, eax
0x180002ccf  xor     [rbp+arg_0], rax
0x180002cd3  call    cs:__imp_GetTickCount
0x180002cd9  mov     eax, eax
0x180002cdb  shl     rax, 18h
0x180002cdf  xor     [rbp+arg_0], rax
0x180002ce3  call    cs:__imp_GetTickCount
0x180002ce9  mov     eax, eax
0x180002ceb  lea     rcx, [rbp+arg_0]
0x180002cef  xor     rax, [rbp+arg_0]
0x180002cf3  xor     rax, rcx
0x180002cf6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002cfa  mov     [rbp+arg_0], rax
0x180002cfe  call    cs:__imp_QueryPerformanceCounter
0x180002d04  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002d07  mov     rcx, 0FFFFFFFFFFFFh
0x180002d11  shl     rax, 20h
0x180002d15  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002d19  xor     rax, [rbp+arg_0]
0x180002d1d  and     rax, rcx
0x180002d20  mov     rcx, rax
0x180002d23  cmp     rax, rbx
0x180002d26  jnz     short loc_180002D35
0x180002d28  mov     rax, 2B992DDFA233h
0x180002d32  mov     rcx, rax
0x180002d35  mov     cs:__security_cookie, rcx
0x180002d3c  mov     rbx, [rsp+20h+arg_18]
0x180002d41  not     rax
0x180002d44  mov     cs:__security_cookie_complement, rax
0x180002d4b  add     rsp, 20h
0x180002d4f  pop     rbp
0x180002d50  retn
```
