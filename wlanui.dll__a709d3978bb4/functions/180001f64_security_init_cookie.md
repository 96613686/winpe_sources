# __security_init_cookie

- ea: `0x180001f64`
- end: `0x180002041`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800016d0`

## callees

- `0x180001f64`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180001fee`
- `KERNEL32!QueryPerformanceCounter` at `0x180001fee`
- `KERNEL32!GetCurrentProcessId` at `0x180001fab`
- `KERNEL32!GetCurrentProcessId` at `0x180001fab`
- `KERNEL32!GetCurrentThreadId` at `0x180001fb7`
- `KERNEL32!GetCurrentThreadId` at `0x180001fb7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001f9d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001f9d`
- `KERNEL32!GetTickCount` at `0x180001fc3`
- `KERNEL32!GetTickCount` at `0x180001fd3`
- `KERNEL32!GetTickCount` at `0x180001fc3`
- `KERNEL32!GetTickCount` at `0x180001fd3`

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
0x180001f64  mov     [rsp-8+arg_18], rbx
0x180001f69  push    rbp
0x180001f6a  mov     rbp, rsp
0x180001f6d  sub     rsp, 20h
0x180001f71  xor     eax, eax
0x180001f73  mov     rbx, 2B992DDFA232h
0x180001f7d  mov     [rbp+arg_0], rax
0x180001f81  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001f85  mov     qword ptr [rbp+PerformanceCount], rax
0x180001f89  mov     rax, cs:__security_cookie
0x180001f90  cmp     rax, rbx
0x180001f93  jnz     loc_18000202C
0x180001f99  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001f9d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001fa3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001fa7  mov     [rbp+arg_0], rax
0x180001fab  call    cs:__imp_GetCurrentProcessId
0x180001fb1  mov     eax, eax
0x180001fb3  xor     [rbp+arg_0], rax
0x180001fb7  call    cs:__imp_GetCurrentThreadId
0x180001fbd  mov     eax, eax
0x180001fbf  xor     [rbp+arg_0], rax
0x180001fc3  call    cs:__imp_GetTickCount
0x180001fc9  mov     eax, eax
0x180001fcb  shl     rax, 18h
0x180001fcf  xor     [rbp+arg_0], rax
0x180001fd3  call    cs:__imp_GetTickCount
0x180001fd9  mov     eax, eax
0x180001fdb  lea     rcx, [rbp+arg_0]
0x180001fdf  xor     rax, [rbp+arg_0]
0x180001fe3  xor     rax, rcx
0x180001fe6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001fea  mov     [rbp+arg_0], rax
0x180001fee  call    cs:__imp_QueryPerformanceCounter
0x180001ff4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001ff7  mov     rcx, 0FFFFFFFFFFFFh
0x180002001  shl     rax, 20h
0x180002005  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002009  xor     rax, [rbp+arg_0]
0x18000200d  and     rax, rcx
0x180002010  mov     rcx, rax
0x180002013  cmp     rax, rbx
0x180002016  jnz     short loc_180002025
0x180002018  mov     rax, 2B992DDFA233h
0x180002022  mov     rcx, rax
0x180002025  mov     cs:__security_cookie, rcx
0x18000202c  mov     rbx, [rsp+20h+arg_18]
0x180002031  not     rax
0x180002034  mov     cs:__security_cookie_complement, rax
0x18000203b  add     rsp, 20h
0x18000203f  pop     rbp
0x180002040  retn
```
