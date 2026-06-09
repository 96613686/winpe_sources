# __security_init_cookie

- ea: `0x180001e04`
- end: `0x180001edd`
- name: `__security_init_cookie`
- size: `217`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800017a0`

## callees

- `0x180001e04`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180001e47`
- `KERNEL32!GetCurrentProcessId` at `0x180001e47`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001e39`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001e39`
- `KERNEL32!QueryPerformanceCounter` at `0x180001e8a`
- `KERNEL32!QueryPerformanceCounter` at `0x180001e8a`
- `KERNEL32!GetCurrentThreadId` at `0x180001e53`
- `KERNEL32!GetCurrentThreadId` at `0x180001e53`
- `KERNEL32!GetTickCount` at `0x180001e5f`
- `KERNEL32!GetTickCount` at `0x180001e6f`
- `KERNEL32!GetTickCount` at `0x180001e5f`
- `KERNEL32!GetTickCount` at `0x180001e6f`

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
0x180001e04  mov     [rsp-8+arg_18], rbx
0x180001e09  push    rbp
0x180001e0a  mov     rbp, rsp
0x180001e0d  sub     rsp, 20h
0x180001e11  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180001e16  mov     rbx, 2B992DDFA232h
0x180001e20  and     qword ptr [rbp+PerformanceCount], 0
0x180001e25  mov     rax, cs:__security_cookie
0x180001e2c  cmp     rax, rbx
0x180001e2f  jnz     loc_180001EC8
0x180001e35  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001e39  call    cs:__imp_GetSystemTimeAsFileTime
0x180001e3f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001e43  mov     [rbp+arg_0], rax
0x180001e47  call    cs:__imp_GetCurrentProcessId
0x180001e4d  mov     eax, eax
0x180001e4f  xor     [rbp+arg_0], rax
0x180001e53  call    cs:__imp_GetCurrentThreadId
0x180001e59  mov     eax, eax
0x180001e5b  xor     [rbp+arg_0], rax
0x180001e5f  call    cs:__imp_GetTickCount
0x180001e65  mov     eax, eax
0x180001e67  shl     rax, 18h
0x180001e6b  xor     [rbp+arg_0], rax
0x180001e6f  call    cs:__imp_GetTickCount
0x180001e75  mov     eax, eax
0x180001e77  lea     rcx, [rbp+arg_0]
0x180001e7b  xor     rax, [rbp+arg_0]
0x180001e7f  xor     rax, rcx
0x180001e82  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001e86  mov     [rbp+arg_0], rax
0x180001e8a  call    cs:__imp_QueryPerformanceCounter
0x180001e90  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001e93  mov     rcx, 0FFFFFFFFFFFFh
0x180001e9d  shl     rax, 20h
0x180001ea1  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001ea5  xor     rax, [rbp+arg_0]
0x180001ea9  and     rax, rcx
0x180001eac  mov     rcx, rax
0x180001eaf  cmp     rax, rbx
0x180001eb2  jnz     short loc_180001EC1
0x180001eb4  mov     rax, 2B992DDFA233h
0x180001ebe  mov     rcx, rax
0x180001ec1  mov     cs:__security_cookie, rcx
0x180001ec8  mov     rbx, [rsp+20h+arg_18]
0x180001ecd  not     rax
0x180001ed0  mov     cs:__security_cookie_complement, rax
0x180001ed7  add     rsp, 20h
0x180001edb  pop     rbp
0x180001edc  retn
```
