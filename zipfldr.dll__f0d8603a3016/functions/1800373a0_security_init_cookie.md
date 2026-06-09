# __security_init_cookie

- ea: `0x1800373a0`
- end: `0x180037455`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180036f00`

## callees

- `0x1800373a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800373ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800373ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800373e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800373e3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800373ff`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800373ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800373d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800373d5`

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
0x1800373a0  mov     [rsp-8+arg_10], rbx
0x1800373a5  push    rbp
0x1800373a6  mov     rbp, rsp
0x1800373a9  sub     rsp, 30h
0x1800373ad  mov     rax, cs:__security_cookie
0x1800373b4  mov     rbx, 2B992DDFA232h
0x1800373be  cmp     rax, rbx
0x1800373c1  jnz     short loc_180037440
0x1800373c3  xor     eax, eax
0x1800373c5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800373c9  mov     [rbp+var_10], rax
0x1800373cd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800373d1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800373d5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800373db  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800373df  mov     [rbp+var_10], rax
0x1800373e3  call    cs:__imp_GetCurrentThreadId
0x1800373e9  mov     eax, eax
0x1800373eb  xor     [rbp+var_10], rax
0x1800373ef  call    cs:__imp_GetCurrentProcessId
0x1800373f5  mov     eax, eax
0x1800373f7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800373fb  xor     [rbp+var_10], rax
0x1800373ff  call    cs:__imp_QueryPerformanceCounter
0x180037405  mov     eax, dword ptr [rbp+PerformanceCount]
0x180037408  lea     rcx, [rbp+var_10]
0x18003740c  shl     rax, 20h
0x180037410  xor     rax, qword ptr [rbp+PerformanceCount]
0x180037414  xor     rax, [rbp+var_10]
0x180037418  xor     rax, rcx
0x18003741b  mov     rcx, 0FFFFFFFFFFFFh
0x180037425  and     rax, rcx
0x180037428  mov     rcx, 2B992DDFA233h
0x180037432  cmp     rax, rbx
0x180037435  cmovz   rax, rcx
0x180037439  mov     cs:__security_cookie, rax
0x180037440  mov     rbx, [rsp+30h+arg_10]
0x180037445  not     rax
0x180037448  mov     cs:__security_cookie_complement, rax
0x18003744f  add     rsp, 30h
0x180037453  pop     rbp
0x180037454  retn
```
