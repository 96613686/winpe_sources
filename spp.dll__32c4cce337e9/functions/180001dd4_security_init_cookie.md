# __security_init_cookie

- ea: `0x180001dd4`
- end: `0x180001eb1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001610`

## callees

- `0x180001dd4`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001e0d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001e0d`
- `KERNEL32!QueryPerformanceCounter` at `0x180001e5e`
- `KERNEL32!QueryPerformanceCounter` at `0x180001e5e`
- `KERNEL32!GetCurrentProcessId` at `0x180001e1b`
- `KERNEL32!GetCurrentProcessId` at `0x180001e1b`
- `KERNEL32!GetCurrentThreadId` at `0x180001e27`
- `KERNEL32!GetCurrentThreadId` at `0x180001e27`
- `KERNEL32!GetTickCount` at `0x180001e33`
- `KERNEL32!GetTickCount` at `0x180001e43`
- `KERNEL32!GetTickCount` at `0x180001e33`
- `KERNEL32!GetTickCount` at `0x180001e43`

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
0x180001dd4  mov     [rsp-8+arg_18], rbx
0x180001dd9  push    rbp
0x180001dda  mov     rbp, rsp
0x180001ddd  sub     rsp, 20h
0x180001de1  xor     eax, eax
0x180001de3  mov     rbx, 2B992DDFA232h
0x180001ded  mov     [rbp+arg_0], rax
0x180001df1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001df5  mov     qword ptr [rbp+PerformanceCount], rax
0x180001df9  mov     rax, cs:__security_cookie
0x180001e00  cmp     rax, rbx
0x180001e03  jnz     loc_180001E9C
0x180001e09  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001e0d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001e13  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001e17  mov     [rbp+arg_0], rax
0x180001e1b  call    cs:__imp_GetCurrentProcessId
0x180001e21  mov     eax, eax
0x180001e23  xor     [rbp+arg_0], rax
0x180001e27  call    cs:__imp_GetCurrentThreadId
0x180001e2d  mov     eax, eax
0x180001e2f  xor     [rbp+arg_0], rax
0x180001e33  call    cs:__imp_GetTickCount
0x180001e39  mov     eax, eax
0x180001e3b  shl     rax, 18h
0x180001e3f  xor     [rbp+arg_0], rax
0x180001e43  call    cs:__imp_GetTickCount
0x180001e49  mov     eax, eax
0x180001e4b  lea     rcx, [rbp+arg_0]
0x180001e4f  xor     rax, [rbp+arg_0]
0x180001e53  xor     rax, rcx
0x180001e56  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001e5a  mov     [rbp+arg_0], rax
0x180001e5e  call    cs:__imp_QueryPerformanceCounter
0x180001e64  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001e67  mov     rcx, 0FFFFFFFFFFFFh
0x180001e71  shl     rax, 20h
0x180001e75  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001e79  xor     rax, [rbp+arg_0]
0x180001e7d  and     rax, rcx
0x180001e80  mov     rcx, rax
0x180001e83  cmp     rax, rbx
0x180001e86  jnz     short loc_180001E95
0x180001e88  mov     rax, 2B992DDFA233h
0x180001e92  mov     rcx, rax
0x180001e95  mov     cs:__security_cookie, rcx
0x180001e9c  mov     rbx, [rsp+20h+arg_18]
0x180001ea1  not     rax
0x180001ea4  mov     cs:__security_cookie_complement, rax
0x180001eab  add     rsp, 20h
0x180001eaf  pop     rbp
0x180001eb0  retn
```
