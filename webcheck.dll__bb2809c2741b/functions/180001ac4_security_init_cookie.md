# __security_init_cookie

- ea: `0x180001ac4`
- end: `0x180001ba1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800013e0`

## callees

- `0x180001ac4`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180001b23`
- `KERNEL32!GetTickCount` at `0x180001b33`
- `KERNEL32!GetTickCount` at `0x180001b23`
- `KERNEL32!GetTickCount` at `0x180001b33`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001afd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001afd`
- `KERNEL32!GetCurrentThreadId` at `0x180001b17`
- `KERNEL32!GetCurrentThreadId` at `0x180001b17`
- `KERNEL32!GetCurrentProcessId` at `0x180001b0b`
- `KERNEL32!GetCurrentProcessId` at `0x180001b0b`
- `KERNEL32!QueryPerformanceCounter` at `0x180001b4e`
- `KERNEL32!QueryPerformanceCounter` at `0x180001b4e`

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
0x180001ac4  mov     [rsp-8+arg_18], rbx
0x180001ac9  push    rbp
0x180001aca  mov     rbp, rsp
0x180001acd  sub     rsp, 20h
0x180001ad1  xor     eax, eax
0x180001ad3  mov     rbx, 2B992DDFA232h
0x180001add  mov     [rbp+arg_0], rax
0x180001ae1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001ae5  mov     qword ptr [rbp+PerformanceCount], rax
0x180001ae9  mov     rax, cs:__security_cookie
0x180001af0  cmp     rax, rbx
0x180001af3  jnz     loc_180001B8C
0x180001af9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001afd  call    cs:__imp_GetSystemTimeAsFileTime
0x180001b03  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001b07  mov     [rbp+arg_0], rax
0x180001b0b  call    cs:__imp_GetCurrentProcessId
0x180001b11  mov     eax, eax
0x180001b13  xor     [rbp+arg_0], rax
0x180001b17  call    cs:__imp_GetCurrentThreadId
0x180001b1d  mov     eax, eax
0x180001b1f  xor     [rbp+arg_0], rax
0x180001b23  call    cs:__imp_GetTickCount
0x180001b29  mov     eax, eax
0x180001b2b  shl     rax, 18h
0x180001b2f  xor     [rbp+arg_0], rax
0x180001b33  call    cs:__imp_GetTickCount
0x180001b39  mov     eax, eax
0x180001b3b  lea     rcx, [rbp+arg_0]
0x180001b3f  xor     rax, [rbp+arg_0]
0x180001b43  xor     rax, rcx
0x180001b46  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001b4a  mov     [rbp+arg_0], rax
0x180001b4e  call    cs:__imp_QueryPerformanceCounter
0x180001b54  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001b57  mov     rcx, 0FFFFFFFFFFFFh
0x180001b61  shl     rax, 20h
0x180001b65  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001b69  xor     rax, [rbp+arg_0]
0x180001b6d  and     rax, rcx
0x180001b70  mov     rcx, rax
0x180001b73  cmp     rax, rbx
0x180001b76  jnz     short loc_180001B85
0x180001b78  mov     rax, 2B992DDFA233h
0x180001b82  mov     rcx, rax
0x180001b85  mov     cs:__security_cookie, rcx
0x180001b8c  mov     rbx, [rsp+20h+arg_18]
0x180001b91  not     rax
0x180001b94  mov     cs:__security_cookie_complement, rax
0x180001b9b  add     rsp, 20h
0x180001b9f  pop     rbp
0x180001ba0  retn
```
