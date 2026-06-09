# __security_init_cookie

- ea: `0x180002134`
- end: `0x180002211`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001c30`

## callees

- `0x180002134`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1800021be`
- `KERNEL32!QueryPerformanceCounter` at `0x1800021be`
- `KERNEL32!GetCurrentProcessId` at `0x18000217b`
- `KERNEL32!GetCurrentProcessId` at `0x18000217b`
- `KERNEL32!GetCurrentThreadId` at `0x180002187`
- `KERNEL32!GetCurrentThreadId` at `0x180002187`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000216d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000216d`
- `KERNEL32!GetTickCount` at `0x180002193`
- `KERNEL32!GetTickCount` at `0x1800021a3`
- `KERNEL32!GetTickCount` at `0x180002193`
- `KERNEL32!GetTickCount` at `0x1800021a3`

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
0x180002134  mov     [rsp-8+arg_18], rbx
0x180002139  push    rbp
0x18000213a  mov     rbp, rsp
0x18000213d  sub     rsp, 20h
0x180002141  xor     eax, eax
0x180002143  mov     rbx, 2B992DDFA232h
0x18000214d  mov     [rbp+arg_0], rax
0x180002151  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002155  mov     qword ptr [rbp+PerformanceCount], rax
0x180002159  mov     rax, cs:__security_cookie
0x180002160  cmp     rax, rbx
0x180002163  jnz     loc_1800021FC
0x180002169  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000216d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002173  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002177  mov     [rbp+arg_0], rax
0x18000217b  call    cs:__imp_GetCurrentProcessId
0x180002181  mov     eax, eax
0x180002183  xor     [rbp+arg_0], rax
0x180002187  call    cs:__imp_GetCurrentThreadId
0x18000218d  mov     eax, eax
0x18000218f  xor     [rbp+arg_0], rax
0x180002193  call    cs:__imp_GetTickCount
0x180002199  mov     eax, eax
0x18000219b  shl     rax, 18h
0x18000219f  xor     [rbp+arg_0], rax
0x1800021a3  call    cs:__imp_GetTickCount
0x1800021a9  mov     eax, eax
0x1800021ab  lea     rcx, [rbp+arg_0]
0x1800021af  xor     rax, [rbp+arg_0]
0x1800021b3  xor     rax, rcx
0x1800021b6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800021ba  mov     [rbp+arg_0], rax
0x1800021be  call    cs:__imp_QueryPerformanceCounter
0x1800021c4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800021c7  mov     rcx, 0FFFFFFFFFFFFh
0x1800021d1  shl     rax, 20h
0x1800021d5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800021d9  xor     rax, [rbp+arg_0]
0x1800021dd  and     rax, rcx
0x1800021e0  mov     rcx, rax
0x1800021e3  cmp     rax, rbx
0x1800021e6  jnz     short loc_1800021F5
0x1800021e8  mov     rax, 2B992DDFA233h
0x1800021f2  mov     rcx, rax
0x1800021f5  mov     cs:__security_cookie, rcx
0x1800021fc  mov     rbx, [rsp+20h+arg_18]
0x180002201  not     rax
0x180002204  mov     cs:__security_cookie_complement, rax
0x18000220b  add     rsp, 20h
0x18000220f  pop     rbp
0x180002210  retn
```
