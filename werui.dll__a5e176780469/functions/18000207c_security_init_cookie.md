# __security_init_cookie

- ea: `0x18000207c`
- end: `0x180002159`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d20`

## callees

- `0x18000207c`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180002106`
- `KERNEL32!QueryPerformanceCounter` at `0x180002106`
- `KERNEL32!GetCurrentProcessId` at `0x1800020c3`
- `KERNEL32!GetCurrentProcessId` at `0x1800020c3`
- `KERNEL32!GetCurrentThreadId` at `0x1800020cf`
- `KERNEL32!GetCurrentThreadId` at `0x1800020cf`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800020b5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800020b5`
- `KERNEL32!GetTickCount` at `0x1800020db`
- `KERNEL32!GetTickCount` at `0x1800020eb`
- `KERNEL32!GetTickCount` at `0x1800020db`
- `KERNEL32!GetTickCount` at `0x1800020eb`

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
0x18000207c  mov     [rsp-8+arg_18], rbx
0x180002081  push    rbp
0x180002082  mov     rbp, rsp
0x180002085  sub     rsp, 20h
0x180002089  xor     eax, eax
0x18000208b  mov     rbx, 2B992DDFA232h
0x180002095  mov     [rbp+arg_0], rax
0x180002099  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000209d  mov     qword ptr [rbp+PerformanceCount], rax
0x1800020a1  mov     rax, cs:__security_cookie
0x1800020a8  cmp     rax, rbx
0x1800020ab  jnz     loc_180002144
0x1800020b1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800020b5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800020bb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800020bf  mov     [rbp+arg_0], rax
0x1800020c3  call    cs:__imp_GetCurrentProcessId
0x1800020c9  mov     eax, eax
0x1800020cb  xor     [rbp+arg_0], rax
0x1800020cf  call    cs:__imp_GetCurrentThreadId
0x1800020d5  mov     eax, eax
0x1800020d7  xor     [rbp+arg_0], rax
0x1800020db  call    cs:__imp_GetTickCount
0x1800020e1  mov     eax, eax
0x1800020e3  shl     rax, 18h
0x1800020e7  xor     [rbp+arg_0], rax
0x1800020eb  call    cs:__imp_GetTickCount
0x1800020f1  mov     eax, eax
0x1800020f3  lea     rcx, [rbp+arg_0]
0x1800020f7  xor     rax, [rbp+arg_0]
0x1800020fb  xor     rax, rcx
0x1800020fe  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002102  mov     [rbp+arg_0], rax
0x180002106  call    cs:__imp_QueryPerformanceCounter
0x18000210c  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000210f  mov     rcx, 0FFFFFFFFFFFFh
0x180002119  shl     rax, 20h
0x18000211d  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002121  xor     rax, [rbp+arg_0]
0x180002125  and     rax, rcx
0x180002128  mov     rcx, rax
0x18000212b  cmp     rax, rbx
0x18000212e  jnz     short loc_18000213D
0x180002130  mov     rax, 2B992DDFA233h
0x18000213a  mov     rcx, rax
0x18000213d  mov     cs:__security_cookie, rcx
0x180002144  mov     rbx, [rsp+20h+arg_18]
0x180002149  not     rax
0x18000214c  mov     cs:__security_cookie_complement, rax
0x180002153  add     rsp, 20h
0x180002157  pop     rbp
0x180002158  retn
```
