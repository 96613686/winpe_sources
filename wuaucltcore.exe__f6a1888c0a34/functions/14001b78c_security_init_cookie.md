# __security_init_cookie

- ea: `0x14001b78c`
- end: `0x14001b843`
- name: `__security_init_cookie`
- size: `183`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001b010`

## callees

- `0x14001b78c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001b7d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001b7d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14001b7dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14001b7dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001b7c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001b7c3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14001b7ed`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14001b7ed`

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
0x14001b78c  mov     [rsp-8+arg_10], rbx
0x14001b791  push    rbp
0x14001b792  mov     rbp, rsp
0x14001b795  sub     rsp, 30h
0x14001b799  mov     rax, cs:__security_cookie
0x14001b7a0  mov     rbx, 2B992DDFA232h
0x14001b7aa  cmp     rax, rbx
0x14001b7ad  jnz     short loc_14001B82E
0x14001b7af  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14001b7b3  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x14001b7bb  mov     qword ptr [rbp+PerformanceCount], 0
0x14001b7c3  call    cs:__imp_GetSystemTimeAsFileTime
0x14001b7c9  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14001b7cd  mov     [rbp+var_10], rax
0x14001b7d1  call    cs:__imp_GetCurrentThreadId
0x14001b7d7  mov     eax, eax
0x14001b7d9  xor     [rbp+var_10], rax
0x14001b7dd  call    cs:__imp_GetCurrentProcessId
0x14001b7e3  mov     eax, eax
0x14001b7e5  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14001b7e9  xor     [rbp+var_10], rax
0x14001b7ed  call    cs:__imp_QueryPerformanceCounter
0x14001b7f3  mov     eax, dword ptr [rbp+PerformanceCount]
0x14001b7f6  lea     rcx, [rbp+var_10]
0x14001b7fa  shl     rax, 20h
0x14001b7fe  xor     rax, qword ptr [rbp+PerformanceCount]
0x14001b802  xor     rax, [rbp+var_10]
0x14001b806  xor     rax, rcx
0x14001b809  mov     rcx, 0FFFFFFFFFFFFh
0x14001b813  and     rax, rcx
0x14001b816  mov     rcx, 2B992DDFA233h
0x14001b820  cmp     rax, rbx
0x14001b823  cmovz   rax, rcx
0x14001b827  mov     cs:__security_cookie, rax
0x14001b82e  mov     rbx, [rsp+30h+arg_10]
0x14001b833  not     rax
0x14001b836  mov     cs:__security_cookie_complement, rax
0x14001b83d  add     rsp, 30h
0x14001b841  pop     rbp
0x14001b842  retn
```
