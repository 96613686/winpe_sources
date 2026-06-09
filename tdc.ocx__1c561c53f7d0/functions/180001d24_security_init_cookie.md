# __security_init_cookie

- ea: `0x180001d24`
- end: `0x180001e01`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001470`

## callees

- `0x180001d24`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180001d83`
- `KERNEL32!GetTickCount` at `0x180001d93`
- `KERNEL32!GetTickCount` at `0x180001d83`
- `KERNEL32!GetTickCount` at `0x180001d93`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001d5d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001d5d`
- `KERNEL32!GetCurrentProcessId` at `0x180001d6b`
- `KERNEL32!GetCurrentProcessId` at `0x180001d6b`
- `KERNEL32!QueryPerformanceCounter` at `0x180001dae`
- `KERNEL32!QueryPerformanceCounter` at `0x180001dae`
- `KERNEL32!GetCurrentThreadId` at `0x180001d77`
- `KERNEL32!GetCurrentThreadId` at `0x180001d77`

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
0x180001d24  mov     [rsp-8+arg_18], rbx
0x180001d29  push    rbp
0x180001d2a  mov     rbp, rsp
0x180001d2d  sub     rsp, 20h
0x180001d31  xor     eax, eax
0x180001d33  mov     rbx, 2B992DDFA232h
0x180001d3d  mov     [rbp+arg_0], rax
0x180001d41  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001d45  mov     qword ptr [rbp+PerformanceCount], rax
0x180001d49  mov     rax, cs:__security_cookie
0x180001d50  cmp     rax, rbx
0x180001d53  jnz     loc_180001DEC
0x180001d59  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001d5d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001d63  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001d67  mov     [rbp+arg_0], rax
0x180001d6b  call    cs:__imp_GetCurrentProcessId
0x180001d71  mov     eax, eax
0x180001d73  xor     [rbp+arg_0], rax
0x180001d77  call    cs:__imp_GetCurrentThreadId
0x180001d7d  mov     eax, eax
0x180001d7f  xor     [rbp+arg_0], rax
0x180001d83  call    cs:__imp_GetTickCount
0x180001d89  mov     eax, eax
0x180001d8b  shl     rax, 18h
0x180001d8f  xor     [rbp+arg_0], rax
0x180001d93  call    cs:__imp_GetTickCount
0x180001d99  mov     eax, eax
0x180001d9b  lea     rcx, [rbp+arg_0]
0x180001d9f  xor     rax, [rbp+arg_0]
0x180001da3  xor     rax, rcx
0x180001da6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001daa  mov     [rbp+arg_0], rax
0x180001dae  call    cs:__imp_QueryPerformanceCounter
0x180001db4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001db7  mov     rcx, 0FFFFFFFFFFFFh
0x180001dc1  shl     rax, 20h
0x180001dc5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001dc9  xor     rax, [rbp+arg_0]
0x180001dcd  and     rax, rcx
0x180001dd0  mov     rcx, rax
0x180001dd3  cmp     rax, rbx
0x180001dd6  jnz     short loc_180001DE5
0x180001dd8  mov     rax, 2B992DDFA233h
0x180001de2  mov     rcx, rax
0x180001de5  mov     cs:__security_cookie, rcx
0x180001dec  mov     rbx, [rsp+20h+arg_18]
0x180001df1  not     rax
0x180001df4  mov     cs:__security_cookie_complement, rax
0x180001dfb  add     rsp, 20h
0x180001dff  pop     rbp
0x180001e00  retn
```
