# __security_init_cookie

- ea: `0x180001c24`
- end: `0x180001cd9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001bb0`
- `0x180002c4c`
- `0x180003974`

## callees

- `0x180001c24`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180001c67`
- `KERNEL32!GetCurrentThreadId` at `0x180001c67`
- `KERNEL32!QueryPerformanceCounter` at `0x180001c83`
- `KERNEL32!QueryPerformanceCounter` at `0x180001c83`
- `KERNEL32!GetCurrentProcessId` at `0x180001c73`
- `KERNEL32!GetCurrentProcessId` at `0x180001c73`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001c59`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001c59`

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
0x180001c24  mov     [rsp-8+arg_10], rbx
0x180001c29  push    rbp
0x180001c2a  mov     rbp, rsp
0x180001c2d  sub     rsp, 30h
0x180001c31  mov     rax, cs:__security_cookie
0x180001c38  mov     rbx, 2B992DDFA232h
0x180001c42  cmp     rax, rbx
0x180001c45  jnz     short loc_180001CC4
0x180001c47  xor     eax, eax
0x180001c49  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001c4d  mov     [rbp+var_10], rax
0x180001c51  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001c55  mov     qword ptr [rbp+PerformanceCount], rax
0x180001c59  call    cs:__imp_GetSystemTimeAsFileTime
0x180001c5f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001c63  mov     [rbp+var_10], rax
0x180001c67  call    cs:__imp_GetCurrentThreadId
0x180001c6d  mov     eax, eax
0x180001c6f  xor     [rbp+var_10], rax
0x180001c73  call    cs:__imp_GetCurrentProcessId
0x180001c79  mov     eax, eax
0x180001c7b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001c7f  xor     [rbp+var_10], rax
0x180001c83  call    cs:__imp_QueryPerformanceCounter
0x180001c89  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001c8c  lea     rcx, [rbp+var_10]
0x180001c90  shl     rax, 20h
0x180001c94  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001c98  xor     rax, [rbp+var_10]
0x180001c9c  xor     rax, rcx
0x180001c9f  mov     rcx, 0FFFFFFFFFFFFh
0x180001ca9  and     rax, rcx
0x180001cac  mov     rcx, 2B992DDFA233h
0x180001cb6  cmp     rax, rbx
0x180001cb9  cmovz   rax, rcx
0x180001cbd  mov     cs:__security_cookie, rax
0x180001cc4  mov     rbx, [rsp+30h+arg_10]
0x180001cc9  not     rax
0x180001ccc  mov     cs:__security_cookie_complement, rax
0x180001cd3  add     rsp, 30h
0x180001cd7  pop     rbp
0x180001cd8  retn
```
