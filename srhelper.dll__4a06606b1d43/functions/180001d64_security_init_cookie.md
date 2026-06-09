# __security_init_cookie

- ea: `0x180001d64`
- end: `0x180001e41`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800015b0`

## callees

- `0x180001d64`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001d9d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001d9d`
- `KERNEL32!QueryPerformanceCounter` at `0x180001dee`
- `KERNEL32!QueryPerformanceCounter` at `0x180001dee`
- `KERNEL32!GetCurrentProcessId` at `0x180001dab`
- `KERNEL32!GetCurrentProcessId` at `0x180001dab`
- `KERNEL32!GetCurrentThreadId` at `0x180001db7`
- `KERNEL32!GetCurrentThreadId` at `0x180001db7`
- `KERNEL32!GetTickCount` at `0x180001dc3`
- `KERNEL32!GetTickCount` at `0x180001dd3`
- `KERNEL32!GetTickCount` at `0x180001dc3`
- `KERNEL32!GetTickCount` at `0x180001dd3`

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
0x180001d64  mov     [rsp-8+arg_18], rbx
0x180001d69  push    rbp
0x180001d6a  mov     rbp, rsp
0x180001d6d  sub     rsp, 20h
0x180001d71  xor     eax, eax
0x180001d73  mov     rbx, 2B992DDFA232h
0x180001d7d  mov     [rbp+arg_0], rax
0x180001d81  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001d85  mov     qword ptr [rbp+PerformanceCount], rax
0x180001d89  mov     rax, cs:__security_cookie
0x180001d90  cmp     rax, rbx
0x180001d93  jnz     loc_180001E2C
0x180001d99  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001d9d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001da3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001da7  mov     [rbp+arg_0], rax
0x180001dab  call    cs:__imp_GetCurrentProcessId
0x180001db1  mov     eax, eax
0x180001db3  xor     [rbp+arg_0], rax
0x180001db7  call    cs:__imp_GetCurrentThreadId
0x180001dbd  mov     eax, eax
0x180001dbf  xor     [rbp+arg_0], rax
0x180001dc3  call    cs:__imp_GetTickCount
0x180001dc9  mov     eax, eax
0x180001dcb  shl     rax, 18h
0x180001dcf  xor     [rbp+arg_0], rax
0x180001dd3  call    cs:__imp_GetTickCount
0x180001dd9  mov     eax, eax
0x180001ddb  lea     rcx, [rbp+arg_0]
0x180001ddf  xor     rax, [rbp+arg_0]
0x180001de3  xor     rax, rcx
0x180001de6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001dea  mov     [rbp+arg_0], rax
0x180001dee  call    cs:__imp_QueryPerformanceCounter
0x180001df4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001df7  mov     rcx, 0FFFFFFFFFFFFh
0x180001e01  shl     rax, 20h
0x180001e05  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001e09  xor     rax, [rbp+arg_0]
0x180001e0d  and     rax, rcx
0x180001e10  mov     rcx, rax
0x180001e13  cmp     rax, rbx
0x180001e16  jnz     short loc_180001E25
0x180001e18  mov     rax, 2B992DDFA233h
0x180001e22  mov     rcx, rax
0x180001e25  mov     cs:__security_cookie, rcx
0x180001e2c  mov     rbx, [rsp+20h+arg_18]
0x180001e31  not     rax
0x180001e34  mov     cs:__security_cookie_complement, rax
0x180001e3b  add     rsp, 20h
0x180001e3f  pop     rbp
0x180001e40  retn
```
