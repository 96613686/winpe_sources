# __security_init_cookie

- ea: `0x180001520`
- end: `0x1800015d5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001490`

## callees

- `0x180001520`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001555`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001555`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000157f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000157f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000156f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000156f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001563`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001563`

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
0x180001520  mov     [rsp-8+arg_10], rbx
0x180001525  push    rbp
0x180001526  mov     rbp, rsp
0x180001529  sub     rsp, 30h
0x18000152d  mov     rax, cs:__security_cookie
0x180001534  mov     rbx, 2B992DDFA232h
0x18000153e  cmp     rax, rbx
0x180001541  jnz     short loc_1800015C0
0x180001543  xor     eax, eax
0x180001545  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001549  mov     [rbp+var_10], rax
0x18000154d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001551  mov     qword ptr [rbp+PerformanceCount], rax
0x180001555  call    cs:__imp_GetSystemTimeAsFileTime
0x18000155b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000155f  mov     [rbp+var_10], rax
0x180001563  call    cs:__imp_GetCurrentThreadId
0x180001569  mov     eax, eax
0x18000156b  xor     [rbp+var_10], rax
0x18000156f  call    cs:__imp_GetCurrentProcessId
0x180001575  mov     eax, eax
0x180001577  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000157b  xor     [rbp+var_10], rax
0x18000157f  call    cs:__imp_QueryPerformanceCounter
0x180001585  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001588  lea     rcx, [rbp+var_10]
0x18000158c  shl     rax, 20h
0x180001590  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001594  xor     rax, [rbp+var_10]
0x180001598  xor     rax, rcx
0x18000159b  mov     rcx, 0FFFFFFFFFFFFh
0x1800015a5  and     rax, rcx
0x1800015a8  mov     rcx, 2B992DDFA233h
0x1800015b2  cmp     rax, rbx
0x1800015b5  cmovz   rax, rcx
0x1800015b9  mov     cs:__security_cookie, rax
0x1800015c0  mov     rbx, [rsp+30h+arg_10]
0x1800015c5  not     rax
0x1800015c8  mov     cs:__security_cookie_complement, rax
0x1800015cf  add     rsp, 30h
0x1800015d3  pop     rbp
0x1800015d4  retn
```
