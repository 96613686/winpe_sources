# __security_init_cookie

- ea: `0x180001de4`
- end: `0x180001e99`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d70`

## callees

- `0x180001de4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001e27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001e27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001e33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001e33`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001e19`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001e19`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001e43`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001e43`

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
0x180001de4  mov     [rsp-8+arg_10], rbx
0x180001de9  push    rbp
0x180001dea  mov     rbp, rsp
0x180001ded  sub     rsp, 30h
0x180001df1  mov     rax, cs:__security_cookie
0x180001df8  mov     rbx, 2B992DDFA232h
0x180001e02  cmp     rax, rbx
0x180001e05  jnz     short loc_180001E84
0x180001e07  xor     eax, eax
0x180001e09  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001e0d  mov     [rbp+var_10], rax
0x180001e11  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001e15  mov     qword ptr [rbp+PerformanceCount], rax
0x180001e19  call    cs:__imp_GetSystemTimeAsFileTime
0x180001e1f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001e23  mov     [rbp+var_10], rax
0x180001e27  call    cs:__imp_GetCurrentThreadId
0x180001e2d  mov     eax, eax
0x180001e2f  xor     [rbp+var_10], rax
0x180001e33  call    cs:__imp_GetCurrentProcessId
0x180001e39  mov     eax, eax
0x180001e3b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001e3f  xor     [rbp+var_10], rax
0x180001e43  call    cs:__imp_QueryPerformanceCounter
0x180001e49  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001e4c  lea     rcx, [rbp+var_10]
0x180001e50  shl     rax, 20h
0x180001e54  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001e58  xor     rax, [rbp+var_10]
0x180001e5c  xor     rax, rcx
0x180001e5f  mov     rcx, 0FFFFFFFFFFFFh
0x180001e69  and     rax, rcx
0x180001e6c  mov     rcx, 2B992DDFA233h
0x180001e76  cmp     rax, rbx
0x180001e79  cmovz   rax, rcx
0x180001e7d  mov     cs:__security_cookie, rax
0x180001e84  mov     rbx, [rsp+30h+arg_10]
0x180001e89  not     rax
0x180001e8c  mov     cs:__security_cookie_complement, rax
0x180001e93  add     rsp, 30h
0x180001e97  pop     rbp
0x180001e98  retn
```
