# __security_init_cookie

- ea: `0x180057a40`
- end: `0x180057b1d`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180057520`

## callees

- `0x180057a40`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180057a79`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180057a79`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180057a9f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180057aaf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180057a9f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180057aaf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180057aca`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180057aca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180057a87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180057a87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057a93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057a93`

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
0x180057a40  mov     [rsp-8+arg_18], rbx
0x180057a45  push    rbp
0x180057a46  mov     rbp, rsp
0x180057a49  sub     rsp, 20h
0x180057a4d  xor     eax, eax
0x180057a4f  mov     rbx, 2B992DDFA232h
0x180057a59  mov     [rbp+arg_0], rax
0x180057a5d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180057a61  mov     qword ptr [rbp+PerformanceCount], rax
0x180057a65  mov     rax, cs:__security_cookie
0x180057a6c  cmp     rax, rbx
0x180057a6f  jnz     loc_180057B08
0x180057a75  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180057a79  call    cs:__imp_GetSystemTimeAsFileTime
0x180057a7f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180057a83  mov     [rbp+arg_0], rax
0x180057a87  call    cs:__imp_GetCurrentProcessId
0x180057a8d  mov     eax, eax
0x180057a8f  xor     [rbp+arg_0], rax
0x180057a93  call    cs:__imp_GetCurrentThreadId
0x180057a99  mov     eax, eax
0x180057a9b  xor     [rbp+arg_0], rax
0x180057a9f  call    cs:__imp_GetTickCount
0x180057aa5  mov     eax, eax
0x180057aa7  shl     rax, 18h
0x180057aab  xor     [rbp+arg_0], rax
0x180057aaf  call    cs:__imp_GetTickCount
0x180057ab5  mov     eax, eax
0x180057ab7  lea     rcx, [rbp+arg_0]
0x180057abb  xor     rax, [rbp+arg_0]
0x180057abf  xor     rax, rcx
0x180057ac2  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180057ac6  mov     [rbp+arg_0], rax
0x180057aca  call    cs:__imp_QueryPerformanceCounter
0x180057ad0  mov     eax, dword ptr [rbp+PerformanceCount]
0x180057ad3  mov     rcx, 0FFFFFFFFFFFFh
0x180057add  shl     rax, 20h
0x180057ae1  xor     rax, qword ptr [rbp+PerformanceCount]
0x180057ae5  xor     rax, [rbp+arg_0]
0x180057ae9  and     rax, rcx
0x180057aec  mov     rcx, rax
0x180057aef  cmp     rax, rbx
0x180057af2  jnz     short loc_180057B01
0x180057af4  mov     rax, 2B992DDFA233h
0x180057afe  mov     rcx, rax
0x180057b01  mov     cs:__security_cookie, rcx
0x180057b08  mov     rbx, [rsp+20h+arg_18]
0x180057b0d  not     rax
0x180057b10  mov     cs:__security_cookie_complement, rax
0x180057b17  add     rsp, 20h
0x180057b1b  pop     rbp
0x180057b1c  retn
```
