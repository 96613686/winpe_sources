# __security_init_cookie

- ea: `0x180006a24`
- end: `0x180006b01`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800063a0`

## callees

- `0x180006a24`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180006a83`
- `KERNEL32!GetTickCount` at `0x180006a93`
- `KERNEL32!GetTickCount` at `0x180006a83`
- `KERNEL32!GetTickCount` at `0x180006a93`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180006a5d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180006a5d`
- `KERNEL32!QueryPerformanceCounter` at `0x180006aae`
- `KERNEL32!QueryPerformanceCounter` at `0x180006aae`
- `KERNEL32!GetCurrentProcessId` at `0x180006a6b`
- `KERNEL32!GetCurrentProcessId` at `0x180006a6b`
- `KERNEL32!GetCurrentThreadId` at `0x180006a77`
- `KERNEL32!GetCurrentThreadId` at `0x180006a77`

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
0x180006a24  mov     [rsp-8+arg_18], rbx
0x180006a29  push    rbp
0x180006a2a  mov     rbp, rsp
0x180006a2d  sub     rsp, 20h
0x180006a31  xor     eax, eax
0x180006a33  mov     rbx, 2B992DDFA232h
0x180006a3d  mov     [rbp+arg_0], rax
0x180006a41  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180006a45  mov     qword ptr [rbp+PerformanceCount], rax
0x180006a49  mov     rax, cs:__security_cookie
0x180006a50  cmp     rax, rbx
0x180006a53  jnz     loc_180006AEC
0x180006a59  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180006a5d  call    cs:__imp_GetSystemTimeAsFileTime
0x180006a63  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180006a67  mov     [rbp+arg_0], rax
0x180006a6b  call    cs:__imp_GetCurrentProcessId
0x180006a71  mov     eax, eax
0x180006a73  xor     [rbp+arg_0], rax
0x180006a77  call    cs:__imp_GetCurrentThreadId
0x180006a7d  mov     eax, eax
0x180006a7f  xor     [rbp+arg_0], rax
0x180006a83  call    cs:__imp_GetTickCount
0x180006a89  mov     eax, eax
0x180006a8b  shl     rax, 18h
0x180006a8f  xor     [rbp+arg_0], rax
0x180006a93  call    cs:__imp_GetTickCount
0x180006a99  mov     eax, eax
0x180006a9b  lea     rcx, [rbp+arg_0]
0x180006a9f  xor     rax, [rbp+arg_0]
0x180006aa3  xor     rax, rcx
0x180006aa6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180006aaa  mov     [rbp+arg_0], rax
0x180006aae  call    cs:__imp_QueryPerformanceCounter
0x180006ab4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180006ab7  mov     rcx, 0FFFFFFFFFFFFh
0x180006ac1  shl     rax, 20h
0x180006ac5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180006ac9  xor     rax, [rbp+arg_0]
0x180006acd  and     rax, rcx
0x180006ad0  mov     rcx, rax
0x180006ad3  cmp     rax, rbx
0x180006ad6  jnz     short loc_180006AE5
0x180006ad8  mov     rax, 2B992DDFA233h
0x180006ae2  mov     rcx, rax
0x180006ae5  mov     cs:__security_cookie, rcx
0x180006aec  mov     rbx, [rsp+20h+arg_18]
0x180006af1  not     rax
0x180006af4  mov     cs:__security_cookie_complement, rax
0x180006afb  add     rsp, 20h
0x180006aff  pop     rbp
0x180006b00  retn
```
