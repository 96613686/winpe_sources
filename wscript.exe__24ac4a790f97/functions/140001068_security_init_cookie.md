# __security_init_cookie

- ea: `0x140001068`
- end: `0x140001145`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400055b0`

## callees

- `0x140001068`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400010bb`
- `KERNEL32!GetCurrentThreadId` at `0x1400010bb`
- `KERNEL32!GetCurrentProcessId` at `0x1400010af`
- `KERNEL32!GetCurrentProcessId` at `0x1400010af`
- `KERNEL32!QueryPerformanceCounter` at `0x1400010f2`
- `KERNEL32!QueryPerformanceCounter` at `0x1400010f2`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400010a1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400010a1`
- `KERNEL32!GetTickCount` at `0x1400010c7`
- `KERNEL32!GetTickCount` at `0x1400010d7`
- `KERNEL32!GetTickCount` at `0x1400010c7`
- `KERNEL32!GetTickCount` at `0x1400010d7`

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
0x140001068  mov     [rsp-8+arg_18], rbx
0x14000106d  push    rbp
0x14000106e  mov     rbp, rsp
0x140001071  sub     rsp, 20h
0x140001075  xor     eax, eax
0x140001077  mov     rbx, 2B992DDFA232h
0x140001081  mov     [rbp+arg_0], rax
0x140001085  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001089  mov     qword ptr [rbp+PerformanceCount], rax
0x14000108d  mov     rax, cs:__security_cookie
0x140001094  cmp     rax, rbx
0x140001097  jnz     loc_140001130
0x14000109d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400010a1  call    cs:__imp_GetSystemTimeAsFileTime
0x1400010a7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400010ab  mov     [rbp+arg_0], rax
0x1400010af  call    cs:__imp_GetCurrentProcessId
0x1400010b5  mov     eax, eax
0x1400010b7  xor     [rbp+arg_0], rax
0x1400010bb  call    cs:__imp_GetCurrentThreadId
0x1400010c1  mov     eax, eax
0x1400010c3  xor     [rbp+arg_0], rax
0x1400010c7  call    cs:__imp_GetTickCount
0x1400010cd  mov     eax, eax
0x1400010cf  shl     rax, 18h
0x1400010d3  xor     [rbp+arg_0], rax
0x1400010d7  call    cs:__imp_GetTickCount
0x1400010dd  mov     eax, eax
0x1400010df  lea     rcx, [rbp+arg_0]
0x1400010e3  xor     rax, [rbp+arg_0]
0x1400010e7  xor     rax, rcx
0x1400010ea  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400010ee  mov     [rbp+arg_0], rax
0x1400010f2  call    cs:__imp_QueryPerformanceCounter
0x1400010f8  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400010fb  mov     rcx, 0FFFFFFFFFFFFh
0x140001105  shl     rax, 20h
0x140001109  xor     rax, qword ptr [rbp+PerformanceCount]
0x14000110d  xor     rax, [rbp+arg_0]
0x140001111  and     rax, rcx
0x140001114  mov     rcx, rax
0x140001117  cmp     rax, rbx
0x14000111a  jnz     short loc_140001129
0x14000111c  mov     rax, 2B992DDFA233h
0x140001126  mov     rcx, rax
0x140001129  mov     cs:__security_cookie, rcx
0x140001130  mov     rbx, [rsp+20h+arg_18]
0x140001135  not     rax
0x140001138  mov     cs:__security_cookie_complement, rax
0x14000113f  add     rsp, 20h
0x140001143  pop     rbp
0x140001144  retn
```
