# __security_init_cookie

- ea: `0x18000c444`
- end: `0x18000c521`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bea0`

## callees

- `0x18000c444`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c4a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c4b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c4a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c4b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000c47d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000c47d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c48b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c48b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c497`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c497`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000c4ce`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000c4ce`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x18000c444  mov     [rsp-8+arg_18], rbx
0x18000c449  push    rbp
0x18000c44a  mov     rbp, rsp
0x18000c44d  sub     rsp, 20h
0x18000c451  xor     eax, eax
0x18000c453  mov     rbx, 2B992DDFA232h
0x18000c45d  mov     [rbp+arg_0], rax
0x18000c461  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000c465  mov     qword ptr [rbp+PerformanceCount], rax
0x18000c469  mov     rax, cs:__security_cookie
0x18000c470  cmp     rax, rbx
0x18000c473  jnz     loc_18000C50C
0x18000c479  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000c47d  call    cs:__imp_GetSystemTimeAsFileTime
0x18000c483  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000c487  mov     [rbp+arg_0], rax
0x18000c48b  call    cs:__imp_GetCurrentProcessId
0x18000c491  mov     eax, eax
0x18000c493  xor     [rbp+arg_0], rax
0x18000c497  call    cs:__imp_GetCurrentThreadId
0x18000c49d  mov     eax, eax
0x18000c49f  xor     [rbp+arg_0], rax
0x18000c4a3  call    cs:__imp_GetTickCount
0x18000c4a9  mov     eax, eax
0x18000c4ab  shl     rax, 18h
0x18000c4af  xor     [rbp+arg_0], rax
0x18000c4b3  call    cs:__imp_GetTickCount
0x18000c4b9  mov     eax, eax
0x18000c4bb  lea     rcx, [rbp+arg_0]
0x18000c4bf  xor     rax, [rbp+arg_0]
0x18000c4c3  xor     rax, rcx
0x18000c4c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000c4ca  mov     [rbp+arg_0], rax
0x18000c4ce  call    cs:__imp_QueryPerformanceCounter
0x18000c4d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000c4d7  mov     rcx, 0FFFFFFFFFFFFh
0x18000c4e1  shl     rax, 20h
0x18000c4e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000c4e9  xor     rax, [rbp+arg_0]
0x18000c4ed  and     rax, rcx
0x18000c4f0  mov     rcx, rax
0x18000c4f3  cmp     rax, rbx
0x18000c4f6  jnz     short loc_18000C505
0x18000c4f8  mov     rax, 2B992DDFA233h
0x18000c502  mov     rcx, rax
0x18000c505  mov     cs:__security_cookie, rcx
0x18000c50c  mov     rbx, [rsp+20h+arg_18]
0x18000c511  not     rax
0x18000c514  mov     cs:__security_cookie_complement, rax
0x18000c51b  add     rsp, 20h
0x18000c51f  pop     rbp
0x18000c520  retn
```
