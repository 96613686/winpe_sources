# __security_init_cookie

- ea: `0x180002144`
- end: `0x180002221`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800018d0`

## callees

- `0x180002144`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18000218b`
- `KERNEL32!GetCurrentProcessId` at `0x18000218b`
- `KERNEL32!QueryPerformanceCounter` at `0x1800021ce`
- `KERNEL32!QueryPerformanceCounter` at `0x1800021ce`
- `KERNEL32!GetTickCount` at `0x1800021a3`
- `KERNEL32!GetTickCount` at `0x1800021b3`
- `KERNEL32!GetTickCount` at `0x1800021a3`
- `KERNEL32!GetTickCount` at `0x1800021b3`
- `KERNEL32!GetCurrentThreadId` at `0x180002197`
- `KERNEL32!GetCurrentThreadId` at `0x180002197`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000217d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000217d`

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
0x180002144  mov     [rsp-8+arg_18], rbx
0x180002149  push    rbp
0x18000214a  mov     rbp, rsp
0x18000214d  sub     rsp, 20h
0x180002151  xor     eax, eax
0x180002153  mov     rbx, 2B992DDFA232h
0x18000215d  mov     [rbp+arg_0], rax
0x180002161  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002165  mov     qword ptr [rbp+PerformanceCount], rax
0x180002169  mov     rax, cs:__security_cookie
0x180002170  cmp     rax, rbx
0x180002173  jnz     loc_18000220C
0x180002179  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000217d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002183  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002187  mov     [rbp+arg_0], rax
0x18000218b  call    cs:__imp_GetCurrentProcessId
0x180002191  mov     eax, eax
0x180002193  xor     [rbp+arg_0], rax
0x180002197  call    cs:__imp_GetCurrentThreadId
0x18000219d  mov     eax, eax
0x18000219f  xor     [rbp+arg_0], rax
0x1800021a3  call    cs:__imp_GetTickCount
0x1800021a9  mov     eax, eax
0x1800021ab  shl     rax, 18h
0x1800021af  xor     [rbp+arg_0], rax
0x1800021b3  call    cs:__imp_GetTickCount
0x1800021b9  mov     eax, eax
0x1800021bb  lea     rcx, [rbp+arg_0]
0x1800021bf  xor     rax, [rbp+arg_0]
0x1800021c3  xor     rax, rcx
0x1800021c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800021ca  mov     [rbp+arg_0], rax
0x1800021ce  call    cs:__imp_QueryPerformanceCounter
0x1800021d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800021d7  mov     rcx, 0FFFFFFFFFFFFh
0x1800021e1  shl     rax, 20h
0x1800021e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800021e9  xor     rax, [rbp+arg_0]
0x1800021ed  and     rax, rcx
0x1800021f0  mov     rcx, rax
0x1800021f3  cmp     rax, rbx
0x1800021f6  jnz     short loc_180002205
0x1800021f8  mov     rax, 2B992DDFA233h
0x180002202  mov     rcx, rax
0x180002205  mov     cs:__security_cookie, rcx
0x18000220c  mov     rbx, [rsp+20h+arg_18]
0x180002211  not     rax
0x180002214  mov     cs:__security_cookie_complement, rax
0x18000221b  add     rsp, 20h
0x18000221f  pop     rbp
0x180002220  retn
```
