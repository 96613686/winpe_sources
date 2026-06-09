# __security_init_cookie

- ea: `0x180033dfc`
- end: `0x180033ed9`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180033aa0`

## callees

- `0x180033dfc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180033e43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180033e43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033e4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033e4f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180033e86`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180033e86`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180033e35`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180033e35`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033e5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033e6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033e5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033e6b`

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
0x180033dfc  mov     [rsp-8+arg_18], rbx
0x180033e01  push    rbp
0x180033e02  mov     rbp, rsp
0x180033e05  sub     rsp, 20h
0x180033e09  xor     eax, eax
0x180033e0b  mov     rbx, 2B992DDFA232h
0x180033e15  mov     [rbp+arg_0], rax
0x180033e19  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180033e1d  mov     qword ptr [rbp+PerformanceCount], rax
0x180033e21  mov     rax, cs:__security_cookie
0x180033e28  cmp     rax, rbx
0x180033e2b  jnz     loc_180033EC4
0x180033e31  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180033e35  call    cs:__imp_GetSystemTimeAsFileTime
0x180033e3b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180033e3f  mov     [rbp+arg_0], rax
0x180033e43  call    cs:__imp_GetCurrentProcessId
0x180033e49  mov     eax, eax
0x180033e4b  xor     [rbp+arg_0], rax
0x180033e4f  call    cs:__imp_GetCurrentThreadId
0x180033e55  mov     eax, eax
0x180033e57  xor     [rbp+arg_0], rax
0x180033e5b  call    cs:__imp_GetTickCount
0x180033e61  mov     eax, eax
0x180033e63  shl     rax, 18h
0x180033e67  xor     [rbp+arg_0], rax
0x180033e6b  call    cs:__imp_GetTickCount
0x180033e71  mov     eax, eax
0x180033e73  lea     rcx, [rbp+arg_0]
0x180033e77  xor     rax, [rbp+arg_0]
0x180033e7b  xor     rax, rcx
0x180033e7e  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180033e82  mov     [rbp+arg_0], rax
0x180033e86  call    cs:__imp_QueryPerformanceCounter
0x180033e8c  mov     eax, dword ptr [rbp+PerformanceCount]
0x180033e8f  mov     rcx, 0FFFFFFFFFFFFh
0x180033e99  shl     rax, 20h
0x180033e9d  xor     rax, qword ptr [rbp+PerformanceCount]
0x180033ea1  xor     rax, [rbp+arg_0]
0x180033ea5  and     rax, rcx
0x180033ea8  mov     rcx, rax
0x180033eab  cmp     rax, rbx
0x180033eae  jnz     short loc_180033EBD
0x180033eb0  mov     rax, 2B992DDFA233h
0x180033eba  mov     rcx, rax
0x180033ebd  mov     cs:__security_cookie, rcx
0x180033ec4  mov     rbx, [rsp+20h+arg_18]
0x180033ec9  not     rax
0x180033ecc  mov     cs:__security_cookie_complement, rax
0x180033ed3  add     rsp, 20h
0x180033ed7  pop     rbp
0x180033ed8  retn
```
