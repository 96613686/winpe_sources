# __security_init_cookie

- ea: `0x180001914`
- end: `0x1800019f1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001300`

## callees

- `0x180001914`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000194d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000194d`
- `KERNEL32!GetCurrentProcessId` at `0x18000195b`
- `KERNEL32!GetCurrentProcessId` at `0x18000195b`
- `KERNEL32!QueryPerformanceCounter` at `0x18000199e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000199e`
- `KERNEL32!GetTickCount` at `0x180001973`
- `KERNEL32!GetTickCount` at `0x180001983`
- `KERNEL32!GetTickCount` at `0x180001973`
- `KERNEL32!GetTickCount` at `0x180001983`
- `KERNEL32!GetCurrentThreadId` at `0x180001967`
- `KERNEL32!GetCurrentThreadId` at `0x180001967`

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
0x180001914  mov     [rsp-8+arg_18], rbx
0x180001919  push    rbp
0x18000191a  mov     rbp, rsp
0x18000191d  sub     rsp, 20h
0x180001921  xor     eax, eax
0x180001923  mov     rbx, 2B992DDFA232h
0x18000192d  mov     [rbp+arg_0], rax
0x180001931  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001935  mov     qword ptr [rbp+PerformanceCount], rax
0x180001939  mov     rax, cs:__security_cookie
0x180001940  cmp     rax, rbx
0x180001943  jnz     loc_1800019DC
0x180001949  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000194d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001953  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001957  mov     [rbp+arg_0], rax
0x18000195b  call    cs:__imp_GetCurrentProcessId
0x180001961  mov     eax, eax
0x180001963  xor     [rbp+arg_0], rax
0x180001967  call    cs:__imp_GetCurrentThreadId
0x18000196d  mov     eax, eax
0x18000196f  xor     [rbp+arg_0], rax
0x180001973  call    cs:__imp_GetTickCount
0x180001979  mov     eax, eax
0x18000197b  shl     rax, 18h
0x18000197f  xor     [rbp+arg_0], rax
0x180001983  call    cs:__imp_GetTickCount
0x180001989  mov     eax, eax
0x18000198b  lea     rcx, [rbp+arg_0]
0x18000198f  xor     rax, [rbp+arg_0]
0x180001993  xor     rax, rcx
0x180001996  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000199a  mov     [rbp+arg_0], rax
0x18000199e  call    cs:__imp_QueryPerformanceCounter
0x1800019a4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800019a7  mov     rcx, 0FFFFFFFFFFFFh
0x1800019b1  shl     rax, 20h
0x1800019b5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800019b9  xor     rax, [rbp+arg_0]
0x1800019bd  and     rax, rcx
0x1800019c0  mov     rcx, rax
0x1800019c3  cmp     rax, rbx
0x1800019c6  jnz     short loc_1800019D5
0x1800019c8  mov     rax, 2B992DDFA233h
0x1800019d2  mov     rcx, rax
0x1800019d5  mov     cs:__security_cookie, rcx
0x1800019dc  mov     rbx, [rsp+20h+arg_18]
0x1800019e1  not     rax
0x1800019e4  mov     cs:__security_cookie_complement, rax
0x1800019eb  add     rsp, 20h
0x1800019ef  pop     rbp
0x1800019f0  retn
```
