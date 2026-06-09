# __security_init_cookie

- ea: `0x180001fc4`
- end: `0x1800020a1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800019a0`

## callees

- `0x180001fc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002017`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002017`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000200b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000200b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000204e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000204e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002023`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002033`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002023`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002033`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ffd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ffd`

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
0x180001fc4  mov     [rsp-8+arg_18], rbx
0x180001fc9  push    rbp
0x180001fca  mov     rbp, rsp
0x180001fcd  sub     rsp, 20h
0x180001fd1  xor     eax, eax
0x180001fd3  mov     rbx, 2B992DDFA232h
0x180001fdd  mov     [rbp+arg_0], rax
0x180001fe1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001fe5  mov     qword ptr [rbp+PerformanceCount], rax
0x180001fe9  mov     rax, cs:__security_cookie
0x180001ff0  cmp     rax, rbx
0x180001ff3  jnz     loc_18000208C
0x180001ff9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001ffd  call    cs:__imp_GetSystemTimeAsFileTime
0x180002003  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002007  mov     [rbp+arg_0], rax
0x18000200b  call    cs:__imp_GetCurrentProcessId
0x180002011  mov     eax, eax
0x180002013  xor     [rbp+arg_0], rax
0x180002017  call    cs:__imp_GetCurrentThreadId
0x18000201d  mov     eax, eax
0x18000201f  xor     [rbp+arg_0], rax
0x180002023  call    cs:__imp_GetTickCount
0x180002029  mov     eax, eax
0x18000202b  shl     rax, 18h
0x18000202f  xor     [rbp+arg_0], rax
0x180002033  call    cs:__imp_GetTickCount
0x180002039  mov     eax, eax
0x18000203b  lea     rcx, [rbp+arg_0]
0x18000203f  xor     rax, [rbp+arg_0]
0x180002043  xor     rax, rcx
0x180002046  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000204a  mov     [rbp+arg_0], rax
0x18000204e  call    cs:__imp_QueryPerformanceCounter
0x180002054  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002057  mov     rcx, 0FFFFFFFFFFFFh
0x180002061  shl     rax, 20h
0x180002065  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002069  xor     rax, [rbp+arg_0]
0x18000206d  and     rax, rcx
0x180002070  mov     rcx, rax
0x180002073  cmp     rax, rbx
0x180002076  jnz     short loc_180002085
0x180002078  mov     rax, 2B992DDFA233h
0x180002082  mov     rcx, rax
0x180002085  mov     cs:__security_cookie, rcx
0x18000208c  mov     rbx, [rsp+20h+arg_18]
0x180002091  not     rax
0x180002094  mov     cs:__security_cookie_complement, rax
0x18000209b  add     rsp, 20h
0x18000209f  pop     rbp
0x1800020a0  retn
```
