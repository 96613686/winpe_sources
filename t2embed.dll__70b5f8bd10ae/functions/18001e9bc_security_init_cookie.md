# __security_init_cookie

- ea: `0x18001e9bc`
- end: `0x18001ea99`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e250`

## callees

- `0x18001e9bc`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001e9f5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001e9f5`
- `KERNEL32!QueryPerformanceCounter` at `0x18001ea46`
- `KERNEL32!QueryPerformanceCounter` at `0x18001ea46`
- `KERNEL32!GetTickCount` at `0x18001ea1b`
- `KERNEL32!GetTickCount` at `0x18001ea2b`
- `KERNEL32!GetTickCount` at `0x18001ea1b`
- `KERNEL32!GetTickCount` at `0x18001ea2b`
- `KERNEL32!GetCurrentThreadId` at `0x18001ea0f`
- `KERNEL32!GetCurrentThreadId` at `0x18001ea0f`
- `KERNEL32!GetCurrentProcessId` at `0x18001ea03`
- `KERNEL32!GetCurrentProcessId` at `0x18001ea03`

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
0x18001e9bc  mov     [rsp-8+arg_18], rbx
0x18001e9c1  push    rbp
0x18001e9c2  mov     rbp, rsp
0x18001e9c5  sub     rsp, 20h
0x18001e9c9  xor     eax, eax
0x18001e9cb  mov     rbx, 2B992DDFA232h
0x18001e9d5  mov     [rbp+arg_0], rax
0x18001e9d9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001e9dd  mov     qword ptr [rbp+PerformanceCount], rax
0x18001e9e1  mov     rax, cs:__security_cookie
0x18001e9e8  cmp     rax, rbx
0x18001e9eb  jnz     loc_18001EA84
0x18001e9f1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001e9f5  call    cs:__imp_GetSystemTimeAsFileTime
0x18001e9fb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001e9ff  mov     [rbp+arg_0], rax
0x18001ea03  call    cs:__imp_GetCurrentProcessId
0x18001ea09  mov     eax, eax
0x18001ea0b  xor     [rbp+arg_0], rax
0x18001ea0f  call    cs:__imp_GetCurrentThreadId
0x18001ea15  mov     eax, eax
0x18001ea17  xor     [rbp+arg_0], rax
0x18001ea1b  call    cs:__imp_GetTickCount
0x18001ea21  mov     eax, eax
0x18001ea23  shl     rax, 18h
0x18001ea27  xor     [rbp+arg_0], rax
0x18001ea2b  call    cs:__imp_GetTickCount
0x18001ea31  mov     eax, eax
0x18001ea33  lea     rcx, [rbp+arg_0]
0x18001ea37  xor     rax, [rbp+arg_0]
0x18001ea3b  xor     rax, rcx
0x18001ea3e  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001ea42  mov     [rbp+arg_0], rax
0x18001ea46  call    cs:__imp_QueryPerformanceCounter
0x18001ea4c  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001ea4f  mov     rcx, 0FFFFFFFFFFFFh
0x18001ea59  shl     rax, 20h
0x18001ea5d  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001ea61  xor     rax, [rbp+arg_0]
0x18001ea65  and     rax, rcx
0x18001ea68  mov     rcx, rax
0x18001ea6b  cmp     rax, rbx
0x18001ea6e  jnz     short loc_18001EA7D
0x18001ea70  mov     rax, 2B992DDFA233h
0x18001ea7a  mov     rcx, rax
0x18001ea7d  mov     cs:__security_cookie, rcx
0x18001ea84  mov     rbx, [rsp+20h+arg_18]
0x18001ea89  not     rax
0x18001ea8c  mov     cs:__security_cookie_complement, rax
0x18001ea93  add     rsp, 20h
0x18001ea97  pop     rbp
0x18001ea98  retn
```
