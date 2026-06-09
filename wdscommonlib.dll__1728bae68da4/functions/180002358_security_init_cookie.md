# __security_init_cookie

- ea: `0x180002358`
- end: `0x180002431`
- name: `__security_init_cookie`
- size: `217`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001ec0`
- `0x18002f648`

## callees

- `0x180002358`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000238d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000238d`
- `KERNEL32!GetTickCount` at `0x1800023b3`
- `KERNEL32!GetTickCount` at `0x1800023c3`
- `KERNEL32!GetTickCount` at `0x1800023b3`
- `KERNEL32!GetTickCount` at `0x1800023c3`
- `KERNEL32!QueryPerformanceCounter` at `0x1800023de`
- `KERNEL32!QueryPerformanceCounter` at `0x1800023de`
- `KERNEL32!GetCurrentThreadId` at `0x1800023a7`
- `KERNEL32!GetCurrentThreadId` at `0x1800023a7`
- `KERNEL32!GetCurrentProcessId` at `0x18000239b`
- `KERNEL32!GetCurrentProcessId` at `0x18000239b`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

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
0x180002358  mov     [rsp-8+arg_18], rbx
0x18000235d  push    rbp
0x18000235e  mov     rbp, rsp
0x180002361  sub     rsp, 20h
0x180002365  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000236a  mov     rbx, 2B992DDFA232h
0x180002374  and     qword ptr [rbp+PerformanceCount], 0
0x180002379  mov     rax, cs:__security_cookie
0x180002380  cmp     rax, rbx
0x180002383  jnz     loc_18000241C
0x180002389  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000238d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002393  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002397  mov     [rbp+arg_0], rax
0x18000239b  call    cs:__imp_GetCurrentProcessId
0x1800023a1  mov     eax, eax
0x1800023a3  xor     [rbp+arg_0], rax
0x1800023a7  call    cs:__imp_GetCurrentThreadId
0x1800023ad  mov     eax, eax
0x1800023af  xor     [rbp+arg_0], rax
0x1800023b3  call    cs:__imp_GetTickCount
0x1800023b9  mov     eax, eax
0x1800023bb  shl     rax, 18h
0x1800023bf  xor     [rbp+arg_0], rax
0x1800023c3  call    cs:__imp_GetTickCount
0x1800023c9  mov     eax, eax
0x1800023cb  lea     rcx, [rbp+arg_0]
0x1800023cf  xor     rax, [rbp+arg_0]
0x1800023d3  xor     rax, rcx
0x1800023d6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800023da  mov     [rbp+arg_0], rax
0x1800023de  call    cs:__imp_QueryPerformanceCounter
0x1800023e4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800023e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800023f1  shl     rax, 20h
0x1800023f5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800023f9  xor     rax, [rbp+arg_0]
0x1800023fd  and     rax, rcx
0x180002400  mov     rcx, rax
0x180002403  cmp     rax, rbx
0x180002406  jnz     short loc_180002415
0x180002408  mov     rax, 2B992DDFA233h
0x180002412  mov     rcx, rax
0x180002415  mov     cs:__security_cookie, rcx
0x18000241c  mov     rbx, [rsp+20h+arg_18]
0x180002421  not     rax
0x180002424  mov     cs:__security_cookie_complement, rax
0x18000242b  add     rsp, 20h
0x18000242f  pop     rbp
0x180002430  retn
```
