# __security_init_cookie

- ea: `0x180001034`
- end: `0x180001108`
- name: `__security_init_cookie`
- size: `212`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x180001034`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1800010c3`
- `KERNEL32!QueryPerformanceCounter` at `0x1800010c3`
- `KERNEL32!GetCurrentProcessId` at `0x180001080`
- `KERNEL32!GetCurrentProcessId` at `0x180001080`
- `KERNEL32!GetCurrentThreadId` at `0x18000108c`
- `KERNEL32!GetCurrentThreadId` at `0x18000108c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001072`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001072`
- `KERNEL32!GetTickCount` at `0x180001098`
- `KERNEL32!GetTickCount` at `0x1800010a8`
- `KERNEL32!GetTickCount` at `0x180001098`
- `KERNEL32!GetTickCount` at `0x1800010a8`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rcx
  _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  v1 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  if ( !_security_cookie || _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v1);
    v1 = (_FILETIME)((unsigned __int64)&v1 ^ *(unsigned __int64 *)&v1 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = 0x2B992DDFA232LL;
    if ( ((*(_QWORD *)&v1
         ^ PerformanceCount.QuadPart
         ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
        & 0xFFFFFFFFFFFFLL) != 0 )
      v0 = (*(_QWORD *)&v1
          ^ PerformanceCount.QuadPart
          ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
         & 0xFFFFFFFFFFFFLL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180001034  mov     [rsp-8+arg_18], rbx
0x180001039  push    rbp
0x18000103a  mov     rbp, rsp
0x18000103d  sub     rsp, 20h
0x180001041  mov     rcx, cs:__security_cookie
0x180001048  xor     eax, eax
0x18000104a  mov     [rbp+arg_0], rax
0x18000104e  mov     rbx, 2B992DDFA232h
0x180001058  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000105c  mov     qword ptr [rbp+PerformanceCount], rax
0x180001060  test    rcx, rcx
0x180001063  jz      short loc_18000106E
0x180001065  cmp     rcx, rbx
0x180001068  jnz     loc_1800010F3
0x18000106e  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001072  call    cs:__imp_GetSystemTimeAsFileTime
0x180001078  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000107c  mov     [rbp+arg_0], rax
0x180001080  call    cs:__imp_GetCurrentProcessId
0x180001086  mov     eax, eax
0x180001088  xor     [rbp+arg_0], rax
0x18000108c  call    cs:__imp_GetCurrentThreadId
0x180001092  mov     eax, eax
0x180001094  xor     [rbp+arg_0], rax
0x180001098  call    cs:__imp_GetTickCount
0x18000109e  mov     eax, eax
0x1800010a0  shl     rax, 18h
0x1800010a4  xor     [rbp+arg_0], rax
0x1800010a8  call    cs:__imp_GetTickCount
0x1800010ae  mov     eax, eax
0x1800010b0  lea     rcx, [rbp+arg_0]
0x1800010b4  xor     rax, [rbp+arg_0]
0x1800010b8  xor     rax, rcx
0x1800010bb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800010bf  mov     [rbp+arg_0], rax
0x1800010c3  call    cs:__imp_QueryPerformanceCounter
0x1800010c9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800010cc  mov     rcx, 0FFFFFFFFFFFFh
0x1800010d6  shl     rax, 20h
0x1800010da  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800010de  xor     rax, [rbp+arg_0]
0x1800010e2  and     rax, rcx
0x1800010e5  mov     rcx, rbx
0x1800010e8  cmovnz  rcx, rax
0x1800010ec  mov     cs:__security_cookie, rcx
0x1800010f3  mov     rbx, [rsp+20h+arg_18]
0x1800010f8  not     rcx
0x1800010fb  mov     cs:__security_cookie_complement, rcx
0x180001102  add     rsp, 20h
0x180001106  pop     rbp
0x180001107  retn
```
