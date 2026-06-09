# __security_init_cookie

- ea: `0x18003cf5c`
- end: `0x18003d011`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003cb10`

## callees

- `0x18003cf5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cf9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cf9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003cfab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003cfab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003cfbb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003cfbb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003cf91`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003cf91`

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
0x18003cf5c  mov     [rsp-8+arg_10], rbx
0x18003cf61  push    rbp
0x18003cf62  mov     rbp, rsp
0x18003cf65  sub     rsp, 30h
0x18003cf69  mov     rax, cs:__security_cookie
0x18003cf70  mov     rbx, 2B992DDFA232h
0x18003cf7a  cmp     rax, rbx
0x18003cf7d  jnz     short loc_18003CFFC
0x18003cf7f  xor     eax, eax
0x18003cf81  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003cf85  mov     [rbp+var_10], rax
0x18003cf89  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003cf8d  mov     qword ptr [rbp+PerformanceCount], rax
0x18003cf91  call    cs:__imp_GetSystemTimeAsFileTime
0x18003cf97  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003cf9b  mov     [rbp+var_10], rax
0x18003cf9f  call    cs:__imp_GetCurrentThreadId
0x18003cfa5  mov     eax, eax
0x18003cfa7  xor     [rbp+var_10], rax
0x18003cfab  call    cs:__imp_GetCurrentProcessId
0x18003cfb1  mov     eax, eax
0x18003cfb3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003cfb7  xor     [rbp+var_10], rax
0x18003cfbb  call    cs:__imp_QueryPerformanceCounter
0x18003cfc1  mov     eax, dword ptr [rbp+PerformanceCount]
0x18003cfc4  lea     rcx, [rbp+var_10]
0x18003cfc8  shl     rax, 20h
0x18003cfcc  xor     rax, qword ptr [rbp+PerformanceCount]
0x18003cfd0  xor     rax, [rbp+var_10]
0x18003cfd4  xor     rax, rcx
0x18003cfd7  mov     rcx, 0FFFFFFFFFFFFh
0x18003cfe1  and     rax, rcx
0x18003cfe4  mov     rcx, 2B992DDFA233h
0x18003cfee  cmp     rax, rbx
0x18003cff1  cmovz   rax, rcx
0x18003cff5  mov     cs:__security_cookie, rax
0x18003cffc  mov     rbx, [rsp+30h+arg_10]
0x18003d001  not     rax
0x18003d004  mov     cs:__security_cookie_complement, rax
0x18003d00b  add     rsp, 30h
0x18003d00f  pop     rbp
0x18003d010  retn
```
