# __security_init_cookie

- ea: `0x18000c270`
- end: `0x18000c325`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c1f0`

## callees

- `0x18000c270`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000c2cf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000c2cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c2bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c2bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c2b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c2b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000c2a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000c2a5`

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
0x18000c270  mov     [rsp-8+arg_10], rbx
0x18000c275  push    rbp
0x18000c276  mov     rbp, rsp
0x18000c279  sub     rsp, 30h
0x18000c27d  mov     rax, cs:__security_cookie
0x18000c284  mov     rbx, 2B992DDFA232h
0x18000c28e  cmp     rax, rbx
0x18000c291  jnz     short loc_18000C310
0x18000c293  xor     eax, eax
0x18000c295  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000c299  mov     [rbp+var_10], rax
0x18000c29d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000c2a1  mov     qword ptr [rbp+PerformanceCount], rax
0x18000c2a5  call    cs:__imp_GetSystemTimeAsFileTime
0x18000c2ab  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000c2af  mov     [rbp+var_10], rax
0x18000c2b3  call    cs:__imp_GetCurrentThreadId
0x18000c2b9  mov     eax, eax
0x18000c2bb  xor     [rbp+var_10], rax
0x18000c2bf  call    cs:__imp_GetCurrentProcessId
0x18000c2c5  mov     eax, eax
0x18000c2c7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000c2cb  xor     [rbp+var_10], rax
0x18000c2cf  call    cs:__imp_QueryPerformanceCounter
0x18000c2d5  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000c2d8  lea     rcx, [rbp+var_10]
0x18000c2dc  shl     rax, 20h
0x18000c2e0  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000c2e4  xor     rax, [rbp+var_10]
0x18000c2e8  xor     rax, rcx
0x18000c2eb  mov     rcx, 0FFFFFFFFFFFFh
0x18000c2f5  and     rax, rcx
0x18000c2f8  mov     rcx, 2B992DDFA233h
0x18000c302  cmp     rax, rbx
0x18000c305  cmovz   rax, rcx
0x18000c309  mov     cs:__security_cookie, rax
0x18000c310  mov     rbx, [rsp+30h+arg_10]
0x18000c315  not     rax
0x18000c318  mov     cs:__security_cookie_complement, rax
0x18000c31f  add     rsp, 30h
0x18000c323  pop     rbp
0x18000c324  retn
```
