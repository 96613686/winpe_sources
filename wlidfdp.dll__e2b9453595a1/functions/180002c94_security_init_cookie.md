# __security_init_cookie

- ea: `0x180002c94`
- end: `0x180002d49`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002790`

## callees

- `0x180002c94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002cd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002cd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002ce3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002ce3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002cf3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002cf3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002cc9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002cc9`

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
0x180002c94  mov     [rsp-8+arg_10], rbx
0x180002c99  push    rbp
0x180002c9a  mov     rbp, rsp
0x180002c9d  sub     rsp, 30h
0x180002ca1  mov     rax, cs:__security_cookie
0x180002ca8  mov     rbx, 2B992DDFA232h
0x180002cb2  cmp     rax, rbx
0x180002cb5  jnz     short loc_180002D34
0x180002cb7  xor     eax, eax
0x180002cb9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002cbd  mov     [rbp+var_10], rax
0x180002cc1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002cc5  mov     qword ptr [rbp+PerformanceCount], rax
0x180002cc9  call    cs:__imp_GetSystemTimeAsFileTime
0x180002ccf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002cd3  mov     [rbp+var_10], rax
0x180002cd7  call    cs:__imp_GetCurrentThreadId
0x180002cdd  mov     eax, eax
0x180002cdf  xor     [rbp+var_10], rax
0x180002ce3  call    cs:__imp_GetCurrentProcessId
0x180002ce9  mov     eax, eax
0x180002ceb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002cef  xor     [rbp+var_10], rax
0x180002cf3  call    cs:__imp_QueryPerformanceCounter
0x180002cf9  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002cfc  lea     rcx, [rbp+var_10]
0x180002d00  shl     rax, 20h
0x180002d04  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002d08  xor     rax, [rbp+var_10]
0x180002d0c  xor     rax, rcx
0x180002d0f  mov     rcx, 0FFFFFFFFFFFFh
0x180002d19  and     rax, rcx
0x180002d1c  mov     rcx, 2B992DDFA233h
0x180002d26  cmp     rax, rbx
0x180002d29  cmovz   rax, rcx
0x180002d2d  mov     cs:__security_cookie, rax
0x180002d34  mov     rbx, [rsp+30h+arg_10]
0x180002d39  not     rax
0x180002d3c  mov     cs:__security_cookie_complement, rax
0x180002d43  add     rsp, 30h
0x180002d47  pop     rbp
0x180002d48  retn
```
