# __security_init_cookie

- ea: `0x18000293c`
- end: `0x1800029f1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002490`

## callees

- `0x18000293c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000298b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000298b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000297f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000297f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000299b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000299b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002971`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002971`

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
0x18000293c  mov     [rsp-8+arg_10], rbx
0x180002941  push    rbp
0x180002942  mov     rbp, rsp
0x180002945  sub     rsp, 30h
0x180002949  mov     rax, cs:__security_cookie
0x180002950  mov     rbx, 2B992DDFA232h
0x18000295a  cmp     rax, rbx
0x18000295d  jnz     short loc_1800029DC
0x18000295f  xor     eax, eax
0x180002961  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002965  mov     [rbp+var_10], rax
0x180002969  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000296d  mov     qword ptr [rbp+PerformanceCount], rax
0x180002971  call    cs:__imp_GetSystemTimeAsFileTime
0x180002977  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000297b  mov     [rbp+var_10], rax
0x18000297f  call    cs:__imp_GetCurrentThreadId
0x180002985  mov     eax, eax
0x180002987  xor     [rbp+var_10], rax
0x18000298b  call    cs:__imp_GetCurrentProcessId
0x180002991  mov     eax, eax
0x180002993  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002997  xor     [rbp+var_10], rax
0x18000299b  call    cs:__imp_QueryPerformanceCounter
0x1800029a1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800029a4  lea     rcx, [rbp+var_10]
0x1800029a8  shl     rax, 20h
0x1800029ac  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800029b0  xor     rax, [rbp+var_10]
0x1800029b4  xor     rax, rcx
0x1800029b7  mov     rcx, 0FFFFFFFFFFFFh
0x1800029c1  and     rax, rcx
0x1800029c4  mov     rcx, 2B992DDFA233h
0x1800029ce  cmp     rax, rbx
0x1800029d1  cmovz   rax, rcx
0x1800029d5  mov     cs:__security_cookie, rax
0x1800029dc  mov     rbx, [rsp+30h+arg_10]
0x1800029e1  not     rax
0x1800029e4  mov     cs:__security_cookie_complement, rax
0x1800029eb  add     rsp, 30h
0x1800029ef  pop     rbp
0x1800029f0  retn
```
