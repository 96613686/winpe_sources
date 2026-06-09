# __security_init_cookie

- ea: `0x140001b94`
- end: `0x140001c71`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400017a0`

## callees

- `0x140001b94`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140001bf3`
- `KERNEL32!GetTickCount` at `0x140001c03`
- `KERNEL32!GetTickCount` at `0x140001bf3`
- `KERNEL32!GetTickCount` at `0x140001c03`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140001bcd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140001bcd`
- `KERNEL32!GetCurrentThreadId` at `0x140001be7`
- `KERNEL32!GetCurrentThreadId` at `0x140001be7`
- `KERNEL32!GetCurrentProcessId` at `0x140001bdb`
- `KERNEL32!GetCurrentProcessId` at `0x140001bdb`
- `KERNEL32!QueryPerformanceCounter` at `0x140001c1e`
- `KERNEL32!QueryPerformanceCounter` at `0x140001c1e`

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
0x140001b94  mov     [rsp-8+arg_18], rbx
0x140001b99  push    rbp
0x140001b9a  mov     rbp, rsp
0x140001b9d  sub     rsp, 20h
0x140001ba1  xor     eax, eax
0x140001ba3  mov     rbx, 2B992DDFA232h
0x140001bad  mov     [rbp+arg_0], rax
0x140001bb1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001bb5  mov     qword ptr [rbp+PerformanceCount], rax
0x140001bb9  mov     rax, cs:__security_cookie
0x140001bc0  cmp     rax, rbx
0x140001bc3  jnz     loc_140001C5C
0x140001bc9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001bcd  call    cs:__imp_GetSystemTimeAsFileTime
0x140001bd3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001bd7  mov     [rbp+arg_0], rax
0x140001bdb  call    cs:__imp_GetCurrentProcessId
0x140001be1  mov     eax, eax
0x140001be3  xor     [rbp+arg_0], rax
0x140001be7  call    cs:__imp_GetCurrentThreadId
0x140001bed  mov     eax, eax
0x140001bef  xor     [rbp+arg_0], rax
0x140001bf3  call    cs:__imp_GetTickCount
0x140001bf9  mov     eax, eax
0x140001bfb  shl     rax, 18h
0x140001bff  xor     [rbp+arg_0], rax
0x140001c03  call    cs:__imp_GetTickCount
0x140001c09  mov     eax, eax
0x140001c0b  lea     rcx, [rbp+arg_0]
0x140001c0f  xor     rax, [rbp+arg_0]
0x140001c13  xor     rax, rcx
0x140001c16  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140001c1a  mov     [rbp+arg_0], rax
0x140001c1e  call    cs:__imp_QueryPerformanceCounter
0x140001c24  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001c27  mov     rcx, 0FFFFFFFFFFFFh
0x140001c31  shl     rax, 20h
0x140001c35  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001c39  xor     rax, [rbp+arg_0]
0x140001c3d  and     rax, rcx
0x140001c40  mov     rcx, rax
0x140001c43  cmp     rax, rbx
0x140001c46  jnz     short loc_140001C55
0x140001c48  mov     rax, 2B992DDFA233h
0x140001c52  mov     rcx, rax
0x140001c55  mov     cs:__security_cookie, rcx
0x140001c5c  mov     rbx, [rsp+20h+arg_18]
0x140001c61  not     rax
0x140001c64  mov     cs:__security_cookie_complement, rax
0x140001c6b  add     rsp, 20h
0x140001c6f  pop     rbp
0x140001c70  retn
```
