# __security_init_cookie

- ea: `0x18000125c`
- end: `0x180001330`
- name: `__security_init_cookie`
- size: `212`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800010b8`

## callees

- `0x18000125c`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800012a8`
- `KERNEL32!GetCurrentProcessId` at `0x1800012a8`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000129a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000129a`
- `KERNEL32!GetCurrentThreadId` at `0x1800012b4`
- `KERNEL32!GetCurrentThreadId` at `0x1800012b4`
- `KERNEL32!QueryPerformanceCounter` at `0x1800012eb`
- `KERNEL32!QueryPerformanceCounter` at `0x1800012eb`
- `KERNEL32!GetTickCount` at `0x1800012c0`
- `KERNEL32!GetTickCount` at `0x1800012d0`
- `KERNEL32!GetTickCount` at `0x1800012c0`
- `KERNEL32!GetTickCount` at `0x1800012d0`

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
0x18000125c  mov     [rsp-8+arg_18], rbx
0x180001261  push    rbp
0x180001262  mov     rbp, rsp
0x180001265  sub     rsp, 20h
0x180001269  mov     rcx, cs:__security_cookie
0x180001270  xor     eax, eax
0x180001272  mov     [rbp+arg_0], rax
0x180001276  mov     rbx, 2B992DDFA232h
0x180001280  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001284  mov     qword ptr [rbp+PerformanceCount], rax
0x180001288  test    rcx, rcx
0x18000128b  jz      short loc_180001296
0x18000128d  cmp     rcx, rbx
0x180001290  jnz     loc_18000131B
0x180001296  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000129a  call    cs:__imp_GetSystemTimeAsFileTime
0x1800012a0  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800012a4  mov     [rbp+arg_0], rax
0x1800012a8  call    cs:__imp_GetCurrentProcessId
0x1800012ae  mov     eax, eax
0x1800012b0  xor     [rbp+arg_0], rax
0x1800012b4  call    cs:__imp_GetCurrentThreadId
0x1800012ba  mov     eax, eax
0x1800012bc  xor     [rbp+arg_0], rax
0x1800012c0  call    cs:__imp_GetTickCount
0x1800012c6  mov     eax, eax
0x1800012c8  shl     rax, 18h
0x1800012cc  xor     [rbp+arg_0], rax
0x1800012d0  call    cs:__imp_GetTickCount
0x1800012d6  mov     eax, eax
0x1800012d8  lea     rcx, [rbp+arg_0]
0x1800012dc  xor     rax, [rbp+arg_0]
0x1800012e0  xor     rax, rcx
0x1800012e3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800012e7  mov     [rbp+arg_0], rax
0x1800012eb  call    cs:__imp_QueryPerformanceCounter
0x1800012f1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800012f4  mov     rcx, 0FFFFFFFFFFFFh
0x1800012fe  shl     rax, 20h
0x180001302  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001306  xor     rax, [rbp+arg_0]
0x18000130a  and     rax, rcx
0x18000130d  mov     rcx, rbx
0x180001310  cmovnz  rcx, rax
0x180001314  mov     cs:__security_cookie, rcx
0x18000131b  mov     rbx, [rsp+20h+arg_18]
0x180001320  not     rcx
0x180001323  mov     cs:__security_cookie_complement, rcx
0x18000132a  add     rsp, 20h
0x18000132e  pop     rbp
0x18000132f  retn
```
