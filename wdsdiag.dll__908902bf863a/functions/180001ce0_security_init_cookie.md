# __security_init_cookie

- ea: `0x180001ce0`
- end: `0x180001db0`
- name: `__security_init_cookie`
- size: `208`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001890`

## callees

- `0x180001ce0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180001d61`
- `KERNEL32!QueryPerformanceCounter` at `0x180001d61`
- `KERNEL32!GetCurrentProcessId` at `0x180001d1e`
- `KERNEL32!GetCurrentProcessId` at `0x180001d1e`
- `KERNEL32!GetCurrentThreadId` at `0x180001d2a`
- `KERNEL32!GetCurrentThreadId` at `0x180001d2a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001d10`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001d10`
- `KERNEL32!GetTickCount` at `0x180001d36`
- `KERNEL32!GetTickCount` at `0x180001d46`
- `KERNEL32!GetTickCount` at `0x180001d36`
- `KERNEL32!GetTickCount` at `0x180001d46`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  SystemTimeAsFileTime = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v1);
    v1 = (_FILETIME)((unsigned __int64)&v1 ^ *(unsigned __int64 *)&v1 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v1
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
0x180001ce0  mov     [rsp-8+arg_18], rbx
0x180001ce5  push    rbp
0x180001ce6  mov     rbp, rsp
0x180001ce9  sub     rsp, 20h
0x180001ced  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180001cf2  mov     rbx, 2B992DDFA232h
0x180001cfc  mov     rax, cs:__security_cookie
0x180001d03  cmp     rax, rbx
0x180001d06  jnz     loc_180001D9B
0x180001d0c  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001d10  call    cs:__imp_GetSystemTimeAsFileTime
0x180001d16  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001d1a  mov     [rbp+arg_0], rax
0x180001d1e  call    cs:__imp_GetCurrentProcessId
0x180001d24  mov     eax, eax
0x180001d26  xor     [rbp+arg_0], rax
0x180001d2a  call    cs:__imp_GetCurrentThreadId
0x180001d30  mov     eax, eax
0x180001d32  xor     [rbp+arg_0], rax
0x180001d36  call    cs:__imp_GetTickCount
0x180001d3c  mov     eax, eax
0x180001d3e  shl     rax, 18h
0x180001d42  xor     [rbp+arg_0], rax
0x180001d46  call    cs:__imp_GetTickCount
0x180001d4c  mov     eax, eax
0x180001d4e  lea     rcx, [rbp+arg_0]
0x180001d52  xor     rax, [rbp+arg_0]
0x180001d56  xor     rax, rcx
0x180001d59  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001d5d  mov     [rbp+arg_0], rax
0x180001d61  call    cs:__imp_QueryPerformanceCounter
0x180001d67  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001d6a  mov     rcx, 0FFFFFFFFFFFFh
0x180001d74  shl     rax, 20h
0x180001d78  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001d7c  xor     rax, [rbp+arg_0]
0x180001d80  and     rax, rcx
0x180001d83  mov     rcx, 2B992DDFA233h
0x180001d8d  cmp     rax, rbx
0x180001d90  cmovz   rax, rcx
0x180001d94  mov     cs:__security_cookie, rax
0x180001d9b  mov     rbx, [rsp+20h+arg_18]
0x180001da0  not     rax
0x180001da3  mov     cs:__security_cookie_complement, rax
0x180001daa  add     rsp, 20h
0x180001dae  pop     rbp
0x180001daf  retn
```
