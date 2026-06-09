# __security_init_cookie

- ea: `0x18000299c`
- end: `0x180002a51`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002520`

## callees

- `0x18000299c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800029d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800029d1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800029fb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800029fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800029df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800029df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800029eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800029eb`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x18000299c  mov     [rsp-8+arg_10], rbx
0x1800029a1  push    rbp
0x1800029a2  mov     rbp, rsp
0x1800029a5  sub     rsp, 30h
0x1800029a9  mov     rax, cs:__security_cookie
0x1800029b0  mov     rbx, 2B992DDFA232h
0x1800029ba  cmp     rax, rbx
0x1800029bd  jnz     short loc_180002A3C
0x1800029bf  xor     eax, eax
0x1800029c1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800029c5  mov     [rbp+var_10], rax
0x1800029c9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800029cd  mov     qword ptr [rbp+PerformanceCount], rax
0x1800029d1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800029d7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800029db  mov     [rbp+var_10], rax
0x1800029df  call    cs:__imp_GetCurrentThreadId
0x1800029e5  mov     eax, eax
0x1800029e7  xor     [rbp+var_10], rax
0x1800029eb  call    cs:__imp_GetCurrentProcessId
0x1800029f1  mov     eax, eax
0x1800029f3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800029f7  xor     [rbp+var_10], rax
0x1800029fb  call    cs:__imp_QueryPerformanceCounter
0x180002a01  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002a04  lea     rcx, [rbp+var_10]
0x180002a08  shl     rax, 20h
0x180002a0c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002a10  xor     rax, [rbp+var_10]
0x180002a14  xor     rax, rcx
0x180002a17  mov     rcx, 0FFFFFFFFFFFFh
0x180002a21  and     rax, rcx
0x180002a24  mov     rcx, 2B992DDFA233h
0x180002a2e  cmp     rax, rbx
0x180002a31  cmovz   rax, rcx
0x180002a35  mov     cs:__security_cookie, rax
0x180002a3c  mov     rbx, [rsp+30h+arg_10]
0x180002a41  not     rax
0x180002a44  mov     cs:__security_cookie_complement, rax
0x180002a4b  add     rsp, 30h
0x180002a4f  pop     rbp
0x180002a50  retn
```
