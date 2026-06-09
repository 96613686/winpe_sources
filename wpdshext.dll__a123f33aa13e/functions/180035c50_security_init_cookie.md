# __security_init_cookie

- ea: `0x180035c50`
- end: `0x180035d05`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180035540`

## callees

- `0x180035c50`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180035c9f`
- `KERNEL32!GetCurrentProcessId` at `0x180035c9f`
- `KERNEL32!QueryPerformanceCounter` at `0x180035caf`
- `KERNEL32!QueryPerformanceCounter` at `0x180035caf`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180035c85`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180035c85`
- `KERNEL32!GetCurrentThreadId` at `0x180035c93`
- `KERNEL32!GetCurrentThreadId` at `0x180035c93`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
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
0x180035c50  mov     [rsp-8+arg_10], rbx
0x180035c55  push    rbp
0x180035c56  mov     rbp, rsp
0x180035c59  sub     rsp, 30h
0x180035c5d  mov     rax, cs:__security_cookie
0x180035c64  mov     rbx, 2B992DDFA232h
0x180035c6e  cmp     rax, rbx
0x180035c71  jnz     short loc_180035CF0
0x180035c73  xor     eax, eax
0x180035c75  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180035c79  mov     [rbp+var_10], rax
0x180035c7d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180035c81  mov     qword ptr [rbp+PerformanceCount], rax
0x180035c85  call    cs:__imp_GetSystemTimeAsFileTime
0x180035c8b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180035c8f  mov     [rbp+var_10], rax
0x180035c93  call    cs:__imp_GetCurrentThreadId
0x180035c99  mov     eax, eax
0x180035c9b  xor     [rbp+var_10], rax
0x180035c9f  call    cs:__imp_GetCurrentProcessId
0x180035ca5  mov     eax, eax
0x180035ca7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180035cab  xor     [rbp+var_10], rax
0x180035caf  call    cs:__imp_QueryPerformanceCounter
0x180035cb5  mov     eax, dword ptr [rbp+PerformanceCount]
0x180035cb8  lea     rcx, [rbp+var_10]
0x180035cbc  shl     rax, 20h
0x180035cc0  xor     rax, qword ptr [rbp+PerformanceCount]
0x180035cc4  xor     rax, [rbp+var_10]
0x180035cc8  xor     rax, rcx
0x180035ccb  mov     rcx, 0FFFFFFFFFFFFh
0x180035cd5  and     rax, rcx
0x180035cd8  mov     rcx, 2B992DDFA233h
0x180035ce2  cmp     rax, rbx
0x180035ce5  cmovz   rax, rcx
0x180035ce9  mov     cs:__security_cookie, rax
0x180035cf0  mov     rbx, [rsp+30h+arg_10]
0x180035cf5  not     rax
0x180035cf8  mov     cs:__security_cookie_complement, rax
0x180035cff  add     rsp, 30h
0x180035d03  pop     rbp
0x180035d04  retn
```
