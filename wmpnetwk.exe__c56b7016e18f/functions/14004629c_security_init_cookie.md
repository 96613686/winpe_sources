# __security_init_cookie

- ea: `0x14004629c`
- end: `0x140046351`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140045ef0`
- `0x1400479b0`

## callees

- `0x14004629c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400462df`
- `KERNEL32!GetCurrentThreadId` at `0x1400462df`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400462d1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400462d1`
- `KERNEL32!GetCurrentProcessId` at `0x1400462eb`
- `KERNEL32!GetCurrentProcessId` at `0x1400462eb`
- `KERNEL32!QueryPerformanceCounter` at `0x1400462fb`
- `KERNEL32!QueryPerformanceCounter` at `0x1400462fb`

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
0x14004629c  mov     [rsp-8+arg_10], rbx
0x1400462a1  push    rbp
0x1400462a2  mov     rbp, rsp
0x1400462a5  sub     rsp, 30h
0x1400462a9  mov     rax, cs:__security_cookie
0x1400462b0  mov     rbx, 2B992DDFA232h
0x1400462ba  cmp     rax, rbx
0x1400462bd  jnz     short loc_14004633C
0x1400462bf  xor     eax, eax
0x1400462c1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400462c5  mov     [rbp+var_10], rax
0x1400462c9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400462cd  mov     qword ptr [rbp+PerformanceCount], rax
0x1400462d1  call    cs:__imp_GetSystemTimeAsFileTime
0x1400462d7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400462db  mov     [rbp+var_10], rax
0x1400462df  call    cs:__imp_GetCurrentThreadId
0x1400462e5  mov     eax, eax
0x1400462e7  xor     [rbp+var_10], rax
0x1400462eb  call    cs:__imp_GetCurrentProcessId
0x1400462f1  mov     eax, eax
0x1400462f3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400462f7  xor     [rbp+var_10], rax
0x1400462fb  call    cs:__imp_QueryPerformanceCounter
0x140046301  mov     eax, dword ptr [rbp+PerformanceCount]
0x140046304  lea     rcx, [rbp+var_10]
0x140046308  shl     rax, 20h
0x14004630c  xor     rax, qword ptr [rbp+PerformanceCount]
0x140046310  xor     rax, [rbp+var_10]
0x140046314  xor     rax, rcx
0x140046317  mov     rcx, 0FFFFFFFFFFFFh
0x140046321  and     rax, rcx
0x140046324  mov     rcx, 2B992DDFA233h
0x14004632e  cmp     rax, rbx
0x140046331  cmovz   rax, rcx
0x140046335  mov     cs:__security_cookie, rax
0x14004633c  mov     rbx, [rsp+30h+arg_10]
0x140046341  not     rax
0x140046344  mov     cs:__security_cookie_complement, rax
0x14004634b  add     rsp, 30h
0x14004634f  pop     rbp
0x140046350  retn
```
