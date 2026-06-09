# __security_init_cookie

- ea: `0x1800a2100`
- end: `0x1800a21b5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a1cc0`

## callees

- `0x1800a2100`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a214f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a214f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a2143`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a2143`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800a215f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800a215f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a2135`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a2135`

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
0x1800a2100  mov     [rsp-8+arg_10], rbx
0x1800a2105  push    rbp
0x1800a2106  mov     rbp, rsp
0x1800a2109  sub     rsp, 30h
0x1800a210d  mov     rax, cs:__security_cookie
0x1800a2114  mov     rbx, 2B992DDFA232h
0x1800a211e  cmp     rax, rbx
0x1800a2121  jnz     short loc_1800A21A0
0x1800a2123  xor     eax, eax
0x1800a2125  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800a2129  mov     [rbp+var_10], rax
0x1800a212d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800a2131  mov     qword ptr [rbp+PerformanceCount], rax
0x1800a2135  call    cs:__imp_GetSystemTimeAsFileTime
0x1800a213b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800a213f  mov     [rbp+var_10], rax
0x1800a2143  call    cs:__imp_GetCurrentThreadId
0x1800a2149  mov     eax, eax
0x1800a214b  xor     [rbp+var_10], rax
0x1800a214f  call    cs:__imp_GetCurrentProcessId
0x1800a2155  mov     eax, eax
0x1800a2157  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800a215b  xor     [rbp+var_10], rax
0x1800a215f  call    cs:__imp_QueryPerformanceCounter
0x1800a2165  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800a2168  lea     rcx, [rbp+var_10]
0x1800a216c  shl     rax, 20h
0x1800a2170  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800a2174  xor     rax, [rbp+var_10]
0x1800a2178  xor     rax, rcx
0x1800a217b  mov     rcx, 0FFFFFFFFFFFFh
0x1800a2185  and     rax, rcx
0x1800a2188  mov     rcx, 2B992DDFA233h
0x1800a2192  cmp     rax, rbx
0x1800a2195  cmovz   rax, rcx
0x1800a2199  mov     cs:__security_cookie, rax
0x1800a21a0  mov     rbx, [rsp+30h+arg_10]
0x1800a21a5  not     rax
0x1800a21a8  mov     cs:__security_cookie_complement, rax
0x1800a21af  add     rsp, 30h
0x1800a21b3  pop     rbp
0x1800a21b4  retn
```
