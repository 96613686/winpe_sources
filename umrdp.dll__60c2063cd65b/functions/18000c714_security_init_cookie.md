# __security_init_cookie

- ea: `0x18000c714`
- end: `0x18000c7f1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bfc0`

## callees

- `0x18000c714`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000c74d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000c74d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c773`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c783`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c773`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c783`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c767`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c767`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c75b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c75b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000c79e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000c79e`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x18000c714  mov     [rsp-8+arg_18], rbx
0x18000c719  push    rbp
0x18000c71a  mov     rbp, rsp
0x18000c71d  sub     rsp, 20h
0x18000c721  xor     eax, eax
0x18000c723  mov     rbx, 2B992DDFA232h
0x18000c72d  mov     [rbp+arg_0], rax
0x18000c731  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000c735  mov     qword ptr [rbp+PerformanceCount], rax
0x18000c739  mov     rax, cs:__security_cookie
0x18000c740  cmp     rax, rbx
0x18000c743  jnz     loc_18000C7DC
0x18000c749  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000c74d  call    cs:__imp_GetSystemTimeAsFileTime
0x18000c753  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000c757  mov     [rbp+arg_0], rax
0x18000c75b  call    cs:__imp_GetCurrentProcessId
0x18000c761  mov     eax, eax
0x18000c763  xor     [rbp+arg_0], rax
0x18000c767  call    cs:__imp_GetCurrentThreadId
0x18000c76d  mov     eax, eax
0x18000c76f  xor     [rbp+arg_0], rax
0x18000c773  call    cs:__imp_GetTickCount
0x18000c779  mov     eax, eax
0x18000c77b  shl     rax, 18h
0x18000c77f  xor     [rbp+arg_0], rax
0x18000c783  call    cs:__imp_GetTickCount
0x18000c789  mov     eax, eax
0x18000c78b  lea     rcx, [rbp+arg_0]
0x18000c78f  xor     rax, [rbp+arg_0]
0x18000c793  xor     rax, rcx
0x18000c796  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000c79a  mov     [rbp+arg_0], rax
0x18000c79e  call    cs:__imp_QueryPerformanceCounter
0x18000c7a4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000c7a7  mov     rcx, 0FFFFFFFFFFFFh
0x18000c7b1  shl     rax, 20h
0x18000c7b5  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000c7b9  xor     rax, [rbp+arg_0]
0x18000c7bd  and     rax, rcx
0x18000c7c0  mov     rcx, rax
0x18000c7c3  cmp     rax, rbx
0x18000c7c6  jnz     short loc_18000C7D5
0x18000c7c8  mov     rax, 2B992DDFA233h
0x18000c7d2  mov     rcx, rax
0x18000c7d5  mov     cs:__security_cookie, rcx
0x18000c7dc  mov     rbx, [rsp+20h+arg_18]
0x18000c7e1  not     rax
0x18000c7e4  mov     cs:__security_cookie_complement, rax
0x18000c7eb  add     rsp, 20h
0x18000c7ef  pop     rbp
0x18000c7f0  retn
```
