# __security_init_cookie

- ea: `0x180024304`
- end: `0x1800243e1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800237a0`

## callees

- `0x180024304`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180024363`
- `KERNEL32!GetTickCount` at `0x180024373`
- `KERNEL32!GetTickCount` at `0x180024363`
- `KERNEL32!GetTickCount` at `0x180024373`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002433d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002433d`
- `KERNEL32!GetCurrentThreadId` at `0x180024357`
- `KERNEL32!GetCurrentThreadId` at `0x180024357`
- `KERNEL32!GetCurrentProcessId` at `0x18002434b`
- `KERNEL32!GetCurrentProcessId` at `0x18002434b`
- `KERNEL32!QueryPerformanceCounter` at `0x18002438e`
- `KERNEL32!QueryPerformanceCounter` at `0x18002438e`

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
0x180024304  mov     [rsp-8+arg_18], rbx
0x180024309  push    rbp
0x18002430a  mov     rbp, rsp
0x18002430d  sub     rsp, 20h
0x180024311  xor     eax, eax
0x180024313  mov     rbx, 2B992DDFA232h
0x18002431d  mov     [rbp+arg_0], rax
0x180024321  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180024325  mov     qword ptr [rbp+PerformanceCount], rax
0x180024329  mov     rax, cs:__security_cookie
0x180024330  cmp     rax, rbx
0x180024333  jnz     loc_1800243CC
0x180024339  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002433d  call    cs:__imp_GetSystemTimeAsFileTime
0x180024343  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180024347  mov     [rbp+arg_0], rax
0x18002434b  call    cs:__imp_GetCurrentProcessId
0x180024351  mov     eax, eax
0x180024353  xor     [rbp+arg_0], rax
0x180024357  call    cs:__imp_GetCurrentThreadId
0x18002435d  mov     eax, eax
0x18002435f  xor     [rbp+arg_0], rax
0x180024363  call    cs:__imp_GetTickCount
0x180024369  mov     eax, eax
0x18002436b  shl     rax, 18h
0x18002436f  xor     [rbp+arg_0], rax
0x180024373  call    cs:__imp_GetTickCount
0x180024379  mov     eax, eax
0x18002437b  lea     rcx, [rbp+arg_0]
0x18002437f  xor     rax, [rbp+arg_0]
0x180024383  xor     rax, rcx
0x180024386  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002438a  mov     [rbp+arg_0], rax
0x18002438e  call    cs:__imp_QueryPerformanceCounter
0x180024394  mov     eax, dword ptr [rbp+PerformanceCount]
0x180024397  mov     rcx, 0FFFFFFFFFFFFh
0x1800243a1  shl     rax, 20h
0x1800243a5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800243a9  xor     rax, [rbp+arg_0]
0x1800243ad  and     rax, rcx
0x1800243b0  mov     rcx, rax
0x1800243b3  cmp     rax, rbx
0x1800243b6  jnz     short loc_1800243C5
0x1800243b8  mov     rax, 2B992DDFA233h
0x1800243c2  mov     rcx, rax
0x1800243c5  mov     cs:__security_cookie, rcx
0x1800243cc  mov     rbx, [rsp+20h+arg_18]
0x1800243d1  not     rax
0x1800243d4  mov     cs:__security_cookie_complement, rax
0x1800243db  add     rsp, 20h
0x1800243df  pop     rbp
0x1800243e0  retn
```
