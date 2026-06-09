# __security_init_cookie

- ea: `0x10083e170`
- end: `0x10083e21c`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100422630`

## callees

- `0x10083e170`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x10083e1aa`
- `KERNEL32!GetCurrentThreadId` at `0x10083e1aa`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x10083e19c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x10083e19c`
- `KERNEL32!QueryPerformanceCounter` at `0x10083e1c6`
- `KERNEL32!QueryPerformanceCounter` at `0x10083e1c6`
- `KERNEL32!GetCurrentProcessId` at `0x10083e1b6`
- `KERNEL32!GetCurrentProcessId` at `0x10083e1b6`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
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
0x10083e170  mov     [rsp-8+arg_18], rbx
0x10083e175  push    rbp
0x10083e176  mov     rbp, rsp
0x10083e179  sub     rsp, 20h
0x10083e17d  mov     rax, cs:__security_cookie
0x10083e184  mov     rbx, 2B992DDFA232h
0x10083e18e  cmp     rax, rbx
0x10083e191  jnz     short loc_10083E207
0x10083e193  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x10083e198  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x10083e19c  call    cs:__imp_GetSystemTimeAsFileTime
0x10083e1a2  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x10083e1a6  mov     [rbp+arg_0], rax
0x10083e1aa  call    cs:__imp_GetCurrentThreadId
0x10083e1b0  mov     eax, eax
0x10083e1b2  xor     [rbp+arg_0], rax
0x10083e1b6  call    cs:__imp_GetCurrentProcessId
0x10083e1bc  mov     eax, eax
0x10083e1be  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x10083e1c2  xor     [rbp+arg_0], rax
0x10083e1c6  call    cs:__imp_QueryPerformanceCounter
0x10083e1cc  mov     eax, dword ptr [rbp+PerformanceCount]
0x10083e1cf  lea     rcx, [rbp+arg_0]
0x10083e1d3  shl     rax, 20h
0x10083e1d7  xor     rax, qword ptr [rbp+PerformanceCount]
0x10083e1db  xor     rax, [rbp+arg_0]
0x10083e1df  xor     rax, rcx
0x10083e1e2  mov     rcx, 0FFFFFFFFFFFFh
0x10083e1ec  and     rax, rcx
0x10083e1ef  mov     rcx, 2B992DDFA233h
0x10083e1f9  cmp     rax, rbx
0x10083e1fc  cmovz   rax, rcx
0x10083e200  mov     cs:__security_cookie, rax
0x10083e207  mov     rbx, [rsp+20h+arg_18]
0x10083e20c  not     rax
0x10083e20f  mov     cs:__security_cookie_complement, rax
0x10083e216  add     rsp, 20h
0x10083e21a  pop     rbp
0x10083e21b  retn
```
