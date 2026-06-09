# __security_init_cookie

- ea: `0x180001f54`
- end: `0x180002031`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001620`

## callees

- `0x180001f54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001f9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001f9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001fa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001fa7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001fb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001fc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001fb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001fc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001f8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001f8d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001fde`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001fde`

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
0x180001f54  mov     [rsp-8+arg_18], rbx
0x180001f59  push    rbp
0x180001f5a  mov     rbp, rsp
0x180001f5d  sub     rsp, 20h
0x180001f61  xor     eax, eax
0x180001f63  mov     rbx, 2B992DDFA232h
0x180001f6d  mov     [rbp+arg_0], rax
0x180001f71  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001f75  mov     qword ptr [rbp+PerformanceCount], rax
0x180001f79  mov     rax, cs:__security_cookie
0x180001f80  cmp     rax, rbx
0x180001f83  jnz     loc_18000201C
0x180001f89  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001f8d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001f93  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001f97  mov     [rbp+arg_0], rax
0x180001f9b  call    cs:__imp_GetCurrentProcessId
0x180001fa1  mov     eax, eax
0x180001fa3  xor     [rbp+arg_0], rax
0x180001fa7  call    cs:__imp_GetCurrentThreadId
0x180001fad  mov     eax, eax
0x180001faf  xor     [rbp+arg_0], rax
0x180001fb3  call    cs:__imp_GetTickCount
0x180001fb9  mov     eax, eax
0x180001fbb  shl     rax, 18h
0x180001fbf  xor     [rbp+arg_0], rax
0x180001fc3  call    cs:__imp_GetTickCount
0x180001fc9  mov     eax, eax
0x180001fcb  lea     rcx, [rbp+arg_0]
0x180001fcf  xor     rax, [rbp+arg_0]
0x180001fd3  xor     rax, rcx
0x180001fd6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001fda  mov     [rbp+arg_0], rax
0x180001fde  call    cs:__imp_QueryPerformanceCounter
0x180001fe4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001fe7  mov     rcx, 0FFFFFFFFFFFFh
0x180001ff1  shl     rax, 20h
0x180001ff5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001ff9  xor     rax, [rbp+arg_0]
0x180001ffd  and     rax, rcx
0x180002000  mov     rcx, rax
0x180002003  cmp     rax, rbx
0x180002006  jnz     short loc_180002015
0x180002008  mov     rax, 2B992DDFA233h
0x180002012  mov     rcx, rax
0x180002015  mov     cs:__security_cookie, rcx
0x18000201c  mov     rbx, [rsp+20h+arg_18]
0x180002021  not     rax
0x180002024  mov     cs:__security_cookie_complement, rax
0x18000202b  add     rsp, 20h
0x18000202f  pop     rbp
0x180002030  retn
```
