# __security_init_cookie

- ea: `0x180002478`
- end: `0x18000252d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001e60`

## callees

- `0x180002478`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800024bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800024bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800024c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800024c7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800024d7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800024d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800024ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800024ad`

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
0x180002478  mov     [rsp-8+arg_10], rbx
0x18000247d  push    rbp
0x18000247e  mov     rbp, rsp
0x180002481  sub     rsp, 30h
0x180002485  mov     rax, cs:__security_cookie
0x18000248c  mov     rbx, 2B992DDFA232h
0x180002496  cmp     rax, rbx
0x180002499  jnz     short loc_180002518
0x18000249b  xor     eax, eax
0x18000249d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800024a1  mov     [rbp+var_10], rax
0x1800024a5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800024a9  mov     qword ptr [rbp+PerformanceCount], rax
0x1800024ad  call    cs:__imp_GetSystemTimeAsFileTime
0x1800024b3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800024b7  mov     [rbp+var_10], rax
0x1800024bb  call    cs:__imp_GetCurrentThreadId
0x1800024c1  mov     eax, eax
0x1800024c3  xor     [rbp+var_10], rax
0x1800024c7  call    cs:__imp_GetCurrentProcessId
0x1800024cd  mov     eax, eax
0x1800024cf  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800024d3  xor     [rbp+var_10], rax
0x1800024d7  call    cs:__imp_QueryPerformanceCounter
0x1800024dd  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800024e0  lea     rcx, [rbp+var_10]
0x1800024e4  shl     rax, 20h
0x1800024e8  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800024ec  xor     rax, [rbp+var_10]
0x1800024f0  xor     rax, rcx
0x1800024f3  mov     rcx, 0FFFFFFFFFFFFh
0x1800024fd  and     rax, rcx
0x180002500  mov     rcx, 2B992DDFA233h
0x18000250a  cmp     rax, rbx
0x18000250d  cmovz   rax, rcx
0x180002511  mov     cs:__security_cookie, rax
0x180002518  mov     rbx, [rsp+30h+arg_10]
0x18000251d  not     rax
0x180002520  mov     cs:__security_cookie_complement, rax
0x180002527  add     rsp, 30h
0x18000252b  pop     rbp
0x18000252c  retn
```
