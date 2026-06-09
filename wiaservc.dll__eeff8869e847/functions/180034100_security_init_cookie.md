# __security_init_cookie

- ea: `0x180034100`
- end: `0x1800341b5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180033c70`

## callees

- `0x180034100`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180034135`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180034135`
- `KERNEL32!QueryPerformanceCounter` at `0x18003415f`
- `KERNEL32!QueryPerformanceCounter` at `0x18003415f`
- `KERNEL32!GetCurrentProcessId` at `0x18003414f`
- `KERNEL32!GetCurrentProcessId` at `0x18003414f`
- `KERNEL32!GetCurrentThreadId` at `0x180034143`
- `KERNEL32!GetCurrentThreadId` at `0x180034143`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x180034100  mov     [rsp-8+arg_10], rbx
0x180034105  push    rbp
0x180034106  mov     rbp, rsp
0x180034109  sub     rsp, 30h
0x18003410d  mov     rax, cs:__security_cookie
0x180034114  mov     rbx, 2B992DDFA232h
0x18003411e  cmp     rax, rbx
0x180034121  jnz     short loc_1800341A0
0x180034123  xor     eax, eax
0x180034125  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180034129  mov     [rbp+var_10], rax
0x18003412d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180034131  mov     qword ptr [rbp+PerformanceCount], rax
0x180034135  call    cs:__imp_GetSystemTimeAsFileTime
0x18003413b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003413f  mov     [rbp+var_10], rax
0x180034143  call    cs:__imp_GetCurrentThreadId
0x180034149  mov     eax, eax
0x18003414b  xor     [rbp+var_10], rax
0x18003414f  call    cs:__imp_GetCurrentProcessId
0x180034155  mov     eax, eax
0x180034157  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003415b  xor     [rbp+var_10], rax
0x18003415f  call    cs:__imp_QueryPerformanceCounter
0x180034165  mov     eax, dword ptr [rbp+PerformanceCount]
0x180034168  lea     rcx, [rbp+var_10]
0x18003416c  shl     rax, 20h
0x180034170  xor     rax, qword ptr [rbp+PerformanceCount]
0x180034174  xor     rax, [rbp+var_10]
0x180034178  xor     rax, rcx
0x18003417b  mov     rcx, 0FFFFFFFFFFFFh
0x180034185  and     rax, rcx
0x180034188  mov     rcx, 2B992DDFA233h
0x180034192  cmp     rax, rbx
0x180034195  cmovz   rax, rcx
0x180034199  mov     cs:__security_cookie, rax
0x1800341a0  mov     rbx, [rsp+30h+arg_10]
0x1800341a5  not     rax
0x1800341a8  mov     cs:__security_cookie_complement, rax
0x1800341af  add     rsp, 30h
0x1800341b3  pop     rbp
0x1800341b4  retn
```
