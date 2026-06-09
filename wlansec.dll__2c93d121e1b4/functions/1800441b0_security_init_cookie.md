# __security_init_cookie

- ea: `0x1800441b0`
- end: `0x180044265`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800439e0`

## callees

- `0x1800441b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800441f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800441f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800441ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800441ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800441e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800441e5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004420f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004420f`

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
0x1800441b0  mov     [rsp-8+arg_10], rbx
0x1800441b5  push    rbp
0x1800441b6  mov     rbp, rsp
0x1800441b9  sub     rsp, 30h
0x1800441bd  mov     rax, cs:__security_cookie
0x1800441c4  mov     rbx, 2B992DDFA232h
0x1800441ce  cmp     rax, rbx
0x1800441d1  jnz     short loc_180044250
0x1800441d3  xor     eax, eax
0x1800441d5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800441d9  mov     [rbp+var_10], rax
0x1800441dd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800441e1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800441e5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800441eb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800441ef  mov     [rbp+var_10], rax
0x1800441f3  call    cs:__imp_GetCurrentThreadId
0x1800441f9  mov     eax, eax
0x1800441fb  xor     [rbp+var_10], rax
0x1800441ff  call    cs:__imp_GetCurrentProcessId
0x180044205  mov     eax, eax
0x180044207  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18004420b  xor     [rbp+var_10], rax
0x18004420f  call    cs:__imp_QueryPerformanceCounter
0x180044215  mov     eax, dword ptr [rbp+PerformanceCount]
0x180044218  lea     rcx, [rbp+var_10]
0x18004421c  shl     rax, 20h
0x180044220  xor     rax, qword ptr [rbp+PerformanceCount]
0x180044224  xor     rax, [rbp+var_10]
0x180044228  xor     rax, rcx
0x18004422b  mov     rcx, 0FFFFFFFFFFFFh
0x180044235  and     rax, rcx
0x180044238  mov     rcx, 2B992DDFA233h
0x180044242  cmp     rax, rbx
0x180044245  cmovz   rax, rcx
0x180044249  mov     cs:__security_cookie, rax
0x180044250  mov     rbx, [rsp+30h+arg_10]
0x180044255  not     rax
0x180044258  mov     cs:__security_cookie_complement, rax
0x18004425f  add     rsp, 30h
0x180044263  pop     rbp
0x180044264  retn
```
