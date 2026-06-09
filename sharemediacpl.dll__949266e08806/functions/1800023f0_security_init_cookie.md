# __security_init_cookie

- ea: `0x1800023f0`
- end: `0x1800024a5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d10`

## callees

- `0x1800023f0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000244f`
- `KERNEL32!QueryPerformanceCounter` at `0x18000244f`
- `KERNEL32!GetCurrentProcessId` at `0x18000243f`
- `KERNEL32!GetCurrentProcessId` at `0x18000243f`
- `KERNEL32!GetCurrentThreadId` at `0x180002433`
- `KERNEL32!GetCurrentThreadId` at `0x180002433`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002425`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002425`

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
0x1800023f0  mov     [rsp-8+arg_10], rbx
0x1800023f5  push    rbp
0x1800023f6  mov     rbp, rsp
0x1800023f9  sub     rsp, 30h
0x1800023fd  mov     rax, cs:__security_cookie
0x180002404  mov     rbx, 2B992DDFA232h
0x18000240e  cmp     rax, rbx
0x180002411  jnz     short loc_180002490
0x180002413  xor     eax, eax
0x180002415  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002419  mov     [rbp+var_10], rax
0x18000241d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002421  mov     qword ptr [rbp+PerformanceCount], rax
0x180002425  call    cs:__imp_GetSystemTimeAsFileTime
0x18000242b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000242f  mov     [rbp+var_10], rax
0x180002433  call    cs:__imp_GetCurrentThreadId
0x180002439  mov     eax, eax
0x18000243b  xor     [rbp+var_10], rax
0x18000243f  call    cs:__imp_GetCurrentProcessId
0x180002445  mov     eax, eax
0x180002447  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000244b  xor     [rbp+var_10], rax
0x18000244f  call    cs:__imp_QueryPerformanceCounter
0x180002455  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002458  lea     rcx, [rbp+var_10]
0x18000245c  shl     rax, 20h
0x180002460  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002464  xor     rax, [rbp+var_10]
0x180002468  xor     rax, rcx
0x18000246b  mov     rcx, 0FFFFFFFFFFFFh
0x180002475  and     rax, rcx
0x180002478  mov     rcx, 2B992DDFA233h
0x180002482  cmp     rax, rbx
0x180002485  cmovz   rax, rcx
0x180002489  mov     cs:__security_cookie, rax
0x180002490  mov     rbx, [rsp+30h+arg_10]
0x180002495  not     rax
0x180002498  mov     cs:__security_cookie_complement, rax
0x18000249f  add     rsp, 30h
0x1800024a3  pop     rbp
0x1800024a4  retn
```
