# __security_init_cookie

- ea: `0x180001f24`
- end: `0x180002001`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001900`

## callees

- `0x180001f24`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001fae`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001fae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001f77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001f77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001f6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001f6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001f83`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001f93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001f83`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001f93`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001f5d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001f5d`

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
0x180001f24  mov     [rsp-8+arg_18], rbx
0x180001f29  push    rbp
0x180001f2a  mov     rbp, rsp
0x180001f2d  sub     rsp, 20h
0x180001f31  xor     eax, eax
0x180001f33  mov     rbx, 2B992DDFA232h
0x180001f3d  mov     [rbp+arg_0], rax
0x180001f41  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001f45  mov     qword ptr [rbp+PerformanceCount], rax
0x180001f49  mov     rax, cs:__security_cookie
0x180001f50  cmp     rax, rbx
0x180001f53  jnz     loc_180001FEC
0x180001f59  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001f5d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001f63  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001f67  mov     [rbp+arg_0], rax
0x180001f6b  call    cs:__imp_GetCurrentProcessId
0x180001f71  mov     eax, eax
0x180001f73  xor     [rbp+arg_0], rax
0x180001f77  call    cs:__imp_GetCurrentThreadId
0x180001f7d  mov     eax, eax
0x180001f7f  xor     [rbp+arg_0], rax
0x180001f83  call    cs:__imp_GetTickCount
0x180001f89  mov     eax, eax
0x180001f8b  shl     rax, 18h
0x180001f8f  xor     [rbp+arg_0], rax
0x180001f93  call    cs:__imp_GetTickCount
0x180001f99  mov     eax, eax
0x180001f9b  lea     rcx, [rbp+arg_0]
0x180001f9f  xor     rax, [rbp+arg_0]
0x180001fa3  xor     rax, rcx
0x180001fa6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001faa  mov     [rbp+arg_0], rax
0x180001fae  call    cs:__imp_QueryPerformanceCounter
0x180001fb4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001fb7  mov     rcx, 0FFFFFFFFFFFFh
0x180001fc1  shl     rax, 20h
0x180001fc5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001fc9  xor     rax, [rbp+arg_0]
0x180001fcd  and     rax, rcx
0x180001fd0  mov     rcx, rax
0x180001fd3  cmp     rax, rbx
0x180001fd6  jnz     short loc_180001FE5
0x180001fd8  mov     rax, 2B992DDFA233h
0x180001fe2  mov     rcx, rax
0x180001fe5  mov     cs:__security_cookie, rcx
0x180001fec  mov     rbx, [rsp+20h+arg_18]
0x180001ff1  not     rax
0x180001ff4  mov     cs:__security_cookie_complement, rax
0x180001ffb  add     rsp, 20h
0x180001fff  pop     rbp
0x180002000  retn
```
