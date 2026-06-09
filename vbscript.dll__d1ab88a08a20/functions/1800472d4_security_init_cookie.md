# __security_init_cookie

- ea: `0x1800472d4`
- end: `0x1800473b1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180046b40`

## callees

- `0x1800472d4`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18004730d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18004730d`
- `KERNEL32!GetTickCount` at `0x180047333`
- `KERNEL32!GetTickCount` at `0x180047343`
- `KERNEL32!GetTickCount` at `0x180047333`
- `KERNEL32!GetTickCount` at `0x180047343`
- `KERNEL32!QueryPerformanceCounter` at `0x18004735e`
- `KERNEL32!QueryPerformanceCounter` at `0x18004735e`
- `KERNEL32!GetCurrentProcessId` at `0x18004731b`
- `KERNEL32!GetCurrentProcessId` at `0x18004731b`
- `KERNEL32!GetCurrentThreadId` at `0x180047327`
- `KERNEL32!GetCurrentThreadId` at `0x180047327`

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
0x1800472d4  mov     [rsp-8+arg_18], rbx
0x1800472d9  push    rbp
0x1800472da  mov     rbp, rsp
0x1800472dd  sub     rsp, 20h
0x1800472e1  xor     eax, eax
0x1800472e3  mov     rbx, 2B992DDFA232h
0x1800472ed  mov     [rbp+arg_0], rax
0x1800472f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800472f5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800472f9  mov     rax, cs:__security_cookie
0x180047300  cmp     rax, rbx
0x180047303  jnz     loc_18004739C
0x180047309  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004730d  call    cs:__imp_GetSystemTimeAsFileTime
0x180047313  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180047317  mov     [rbp+arg_0], rax
0x18004731b  call    cs:__imp_GetCurrentProcessId
0x180047321  mov     eax, eax
0x180047323  xor     [rbp+arg_0], rax
0x180047327  call    cs:__imp_GetCurrentThreadId
0x18004732d  mov     eax, eax
0x18004732f  xor     [rbp+arg_0], rax
0x180047333  call    cs:__imp_GetTickCount
0x180047339  mov     eax, eax
0x18004733b  shl     rax, 18h
0x18004733f  xor     [rbp+arg_0], rax
0x180047343  call    cs:__imp_GetTickCount
0x180047349  mov     eax, eax
0x18004734b  lea     rcx, [rbp+arg_0]
0x18004734f  xor     rax, [rbp+arg_0]
0x180047353  xor     rax, rcx
0x180047356  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18004735a  mov     [rbp+arg_0], rax
0x18004735e  call    cs:__imp_QueryPerformanceCounter
0x180047364  mov     eax, dword ptr [rbp+PerformanceCount]
0x180047367  mov     rcx, 0FFFFFFFFFFFFh
0x180047371  shl     rax, 20h
0x180047375  xor     rax, qword ptr [rbp+PerformanceCount]
0x180047379  xor     rax, [rbp+arg_0]
0x18004737d  and     rax, rcx
0x180047380  mov     rcx, rax
0x180047383  cmp     rax, rbx
0x180047386  jnz     short loc_180047395
0x180047388  mov     rax, 2B992DDFA233h
0x180047392  mov     rcx, rax
0x180047395  mov     cs:__security_cookie, rcx
0x18004739c  mov     rbx, [rsp+20h+arg_18]
0x1800473a1  not     rax
0x1800473a4  mov     cs:__security_cookie_complement, rax
0x1800473ab  add     rsp, 20h
0x1800473af  pop     rbp
0x1800473b0  retn
```
