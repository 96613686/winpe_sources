# __security_init_cookie

- ea: `0x18003602c`
- end: `0x1800360e1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180035870`

## callees

- `0x18003602c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003607b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003607b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003606f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003606f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180036061`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180036061`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003608b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003608b`

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
0x18003602c  mov     [rsp-8+arg_10], rbx
0x180036031  push    rbp
0x180036032  mov     rbp, rsp
0x180036035  sub     rsp, 30h
0x180036039  mov     rax, cs:__security_cookie
0x180036040  mov     rbx, 2B992DDFA232h
0x18003604a  cmp     rax, rbx
0x18003604d  jnz     short loc_1800360CC
0x18003604f  xor     eax, eax
0x180036051  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180036055  mov     [rbp+var_10], rax
0x180036059  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003605d  mov     qword ptr [rbp+PerformanceCount], rax
0x180036061  call    cs:__imp_GetSystemTimeAsFileTime
0x180036067  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003606b  mov     [rbp+var_10], rax
0x18003606f  call    cs:__imp_GetCurrentThreadId
0x180036075  mov     eax, eax
0x180036077  xor     [rbp+var_10], rax
0x18003607b  call    cs:__imp_GetCurrentProcessId
0x180036081  mov     eax, eax
0x180036083  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180036087  xor     [rbp+var_10], rax
0x18003608b  call    cs:__imp_QueryPerformanceCounter
0x180036091  mov     eax, dword ptr [rbp+PerformanceCount]
0x180036094  lea     rcx, [rbp+var_10]
0x180036098  shl     rax, 20h
0x18003609c  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800360a0  xor     rax, [rbp+var_10]
0x1800360a4  xor     rax, rcx
0x1800360a7  mov     rcx, 0FFFFFFFFFFFFh
0x1800360b1  and     rax, rcx
0x1800360b4  mov     rcx, 2B992DDFA233h
0x1800360be  cmp     rax, rbx
0x1800360c1  cmovz   rax, rcx
0x1800360c5  mov     cs:__security_cookie, rax
0x1800360cc  mov     rbx, [rsp+30h+arg_10]
0x1800360d1  not     rax
0x1800360d4  mov     cs:__security_cookie_complement, rax
0x1800360db  add     rsp, 30h
0x1800360df  pop     rbp
0x1800360e0  retn
```
