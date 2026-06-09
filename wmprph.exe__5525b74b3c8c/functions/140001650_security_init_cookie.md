# __security_init_cookie

- ea: `0x140001650`
- end: `0x140001705`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001360`

## callees

- `0x140001650`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140001693`
- `KERNEL32!GetCurrentThreadId` at `0x140001693`
- `KERNEL32!QueryPerformanceCounter` at `0x1400016af`
- `KERNEL32!QueryPerformanceCounter` at `0x1400016af`
- `KERNEL32!GetCurrentProcessId` at `0x14000169f`
- `KERNEL32!GetCurrentProcessId` at `0x14000169f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140001685`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140001685`

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
0x140001650  mov     [rsp-8+arg_10], rbx
0x140001655  push    rbp
0x140001656  mov     rbp, rsp
0x140001659  sub     rsp, 30h
0x14000165d  mov     rax, cs:__security_cookie
0x140001664  mov     rbx, 2B992DDFA232h
0x14000166e  cmp     rax, rbx
0x140001671  jnz     short loc_1400016F0
0x140001673  xor     eax, eax
0x140001675  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001679  mov     [rbp+var_10], rax
0x14000167d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001681  mov     qword ptr [rbp+PerformanceCount], rax
0x140001685  call    cs:__imp_GetSystemTimeAsFileTime
0x14000168b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000168f  mov     [rbp+var_10], rax
0x140001693  call    cs:__imp_GetCurrentThreadId
0x140001699  mov     eax, eax
0x14000169b  xor     [rbp+var_10], rax
0x14000169f  call    cs:__imp_GetCurrentProcessId
0x1400016a5  mov     eax, eax
0x1400016a7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400016ab  xor     [rbp+var_10], rax
0x1400016af  call    cs:__imp_QueryPerformanceCounter
0x1400016b5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400016b8  lea     rcx, [rbp+var_10]
0x1400016bc  shl     rax, 20h
0x1400016c0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400016c4  xor     rax, [rbp+var_10]
0x1400016c8  xor     rax, rcx
0x1400016cb  mov     rcx, 0FFFFFFFFFFFFh
0x1400016d5  and     rax, rcx
0x1400016d8  mov     rcx, 2B992DDFA233h
0x1400016e2  cmp     rax, rbx
0x1400016e5  cmovz   rax, rcx
0x1400016e9  mov     cs:__security_cookie, rax
0x1400016f0  mov     rbx, [rsp+30h+arg_10]
0x1400016f5  not     rax
0x1400016f8  mov     cs:__security_cookie_complement, rax
0x1400016ff  add     rsp, 30h
0x140001703  pop     rbp
0x140001704  retn
```
