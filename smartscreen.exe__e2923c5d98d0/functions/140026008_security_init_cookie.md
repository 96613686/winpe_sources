# __security_init_cookie

- ea: `0x140026008`
- end: `0x1400260bd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140025a70`

## callees

- `0x140026008`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002604b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002604b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140026057`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140026057`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140026067`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140026067`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002603d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002603d`

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
0x140026008  mov     [rsp-8+arg_10], rbx
0x14002600d  push    rbp
0x14002600e  mov     rbp, rsp
0x140026011  sub     rsp, 30h
0x140026015  mov     rax, cs:__security_cookie
0x14002601c  mov     rbx, 2B992DDFA232h
0x140026026  cmp     rax, rbx
0x140026029  jnz     short loc_1400260A8
0x14002602b  xor     eax, eax
0x14002602d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140026031  mov     [rbp+var_10], rax
0x140026035  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140026039  mov     qword ptr [rbp+PerformanceCount], rax
0x14002603d  call    cs:__imp_GetSystemTimeAsFileTime
0x140026043  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140026047  mov     [rbp+var_10], rax
0x14002604b  call    cs:__imp_GetCurrentThreadId
0x140026051  mov     eax, eax
0x140026053  xor     [rbp+var_10], rax
0x140026057  call    cs:__imp_GetCurrentProcessId
0x14002605d  mov     eax, eax
0x14002605f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140026063  xor     [rbp+var_10], rax
0x140026067  call    cs:__imp_QueryPerformanceCounter
0x14002606d  mov     eax, dword ptr [rbp+PerformanceCount]
0x140026070  lea     rcx, [rbp+var_10]
0x140026074  shl     rax, 20h
0x140026078  xor     rax, qword ptr [rbp+PerformanceCount]
0x14002607c  xor     rax, [rbp+var_10]
0x140026080  xor     rax, rcx
0x140026083  mov     rcx, 0FFFFFFFFFFFFh
0x14002608d  and     rax, rcx
0x140026090  mov     rcx, 2B992DDFA233h
0x14002609a  cmp     rax, rbx
0x14002609d  cmovz   rax, rcx
0x1400260a1  mov     cs:__security_cookie, rax
0x1400260a8  mov     rbx, [rsp+30h+arg_10]
0x1400260ad  not     rax
0x1400260b0  mov     cs:__security_cookie_complement, rax
0x1400260b7  add     rsp, 30h
0x1400260bb  pop     rbp
0x1400260bc  retn
```
