# __security_init_cookie

- ea: `0x180043918`
- end: `0x1800439cf`
- name: `__security_init_cookie`
- size: `183`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180042f70`

## callees

- `0x180043918`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180043969`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180043969`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004395d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004395d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004394f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004394f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180043979`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180043979`

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
0x180043918  mov     [rsp-8+arg_10], rbx
0x18004391d  push    rbp
0x18004391e  mov     rbp, rsp
0x180043921  sub     rsp, 30h
0x180043925  mov     rax, cs:__security_cookie
0x18004392c  mov     rbx, 2B992DDFA232h
0x180043936  cmp     rax, rbx
0x180043939  jnz     short loc_1800439BA
0x18004393b  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004393f  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180043947  mov     qword ptr [rbp+PerformanceCount], 0
0x18004394f  call    cs:__imp_GetSystemTimeAsFileTime
0x180043955  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180043959  mov     [rbp+var_10], rax
0x18004395d  call    cs:__imp_GetCurrentThreadId
0x180043963  mov     eax, eax
0x180043965  xor     [rbp+var_10], rax
0x180043969  call    cs:__imp_GetCurrentProcessId
0x18004396f  mov     eax, eax
0x180043971  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180043975  xor     [rbp+var_10], rax
0x180043979  call    cs:__imp_QueryPerformanceCounter
0x18004397f  mov     eax, dword ptr [rbp+PerformanceCount]
0x180043982  lea     rcx, [rbp+var_10]
0x180043986  shl     rax, 20h
0x18004398a  xor     rax, qword ptr [rbp+PerformanceCount]
0x18004398e  xor     rax, [rbp+var_10]
0x180043992  xor     rax, rcx
0x180043995  mov     rcx, 0FFFFFFFFFFFFh
0x18004399f  and     rax, rcx
0x1800439a2  mov     rcx, 2B992DDFA233h
0x1800439ac  cmp     rax, rbx
0x1800439af  cmovz   rax, rcx
0x1800439b3  mov     cs:__security_cookie, rax
0x1800439ba  mov     rbx, [rsp+30h+arg_10]
0x1800439bf  not     rax
0x1800439c2  mov     cs:__security_cookie_complement, rax
0x1800439c9  add     rsp, 30h
0x1800439cd  pop     rbp
0x1800439ce  retn
```
