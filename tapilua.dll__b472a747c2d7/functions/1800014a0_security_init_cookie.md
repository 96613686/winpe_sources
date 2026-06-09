# __security_init_cookie

- ea: `0x1800014a0`
- end: `0x180001555`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001420`

## callees

- `0x1800014a0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1800014ff`
- `KERNEL32!QueryPerformanceCounter` at `0x1800014ff`
- `KERNEL32!GetCurrentProcessId` at `0x1800014ef`
- `KERNEL32!GetCurrentProcessId` at `0x1800014ef`
- `KERNEL32!GetCurrentThreadId` at `0x1800014e3`
- `KERNEL32!GetCurrentThreadId` at `0x1800014e3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800014d5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800014d5`

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
0x1800014a0  mov     [rsp-8+arg_10], rbx
0x1800014a5  push    rbp
0x1800014a6  mov     rbp, rsp
0x1800014a9  sub     rsp, 30h
0x1800014ad  mov     rax, cs:__security_cookie
0x1800014b4  mov     rbx, 2B992DDFA232h
0x1800014be  cmp     rax, rbx
0x1800014c1  jnz     short loc_180001540
0x1800014c3  xor     eax, eax
0x1800014c5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800014c9  mov     [rbp+var_10], rax
0x1800014cd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800014d1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800014d5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800014db  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800014df  mov     [rbp+var_10], rax
0x1800014e3  call    cs:__imp_GetCurrentThreadId
0x1800014e9  mov     eax, eax
0x1800014eb  xor     [rbp+var_10], rax
0x1800014ef  call    cs:__imp_GetCurrentProcessId
0x1800014f5  mov     eax, eax
0x1800014f7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800014fb  xor     [rbp+var_10], rax
0x1800014ff  call    cs:__imp_QueryPerformanceCounter
0x180001505  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001508  lea     rcx, [rbp+var_10]
0x18000150c  shl     rax, 20h
0x180001510  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001514  xor     rax, [rbp+var_10]
0x180001518  xor     rax, rcx
0x18000151b  mov     rcx, 0FFFFFFFFFFFFh
0x180001525  and     rax, rcx
0x180001528  mov     rcx, 2B992DDFA233h
0x180001532  cmp     rax, rbx
0x180001535  cmovz   rax, rcx
0x180001539  mov     cs:__security_cookie, rax
0x180001540  mov     rbx, [rsp+30h+arg_10]
0x180001545  not     rax
0x180001548  mov     cs:__security_cookie_complement, rax
0x18000154f  add     rsp, 30h
0x180001553  pop     rbp
0x180001554  retn
```
