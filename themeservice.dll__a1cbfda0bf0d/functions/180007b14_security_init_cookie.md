# __security_init_cookie

- ea: `0x180007b14`
- end: `0x180007bf1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800076f0`

## callees

- `0x180007b14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007b5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007b5b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007b9e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007b9e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007b73`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007b83`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007b73`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007b83`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007b4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007b4d`

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
0x180007b14  mov     [rsp-8+arg_18], rbx
0x180007b19  push    rbp
0x180007b1a  mov     rbp, rsp
0x180007b1d  sub     rsp, 20h
0x180007b21  xor     eax, eax
0x180007b23  mov     rbx, 2B992DDFA232h
0x180007b2d  mov     [rbp+arg_0], rax
0x180007b31  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180007b35  mov     qword ptr [rbp+PerformanceCount], rax
0x180007b39  mov     rax, cs:__security_cookie
0x180007b40  cmp     rax, rbx
0x180007b43  jnz     loc_180007BDC
0x180007b49  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180007b4d  call    cs:__imp_GetSystemTimeAsFileTime
0x180007b53  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180007b57  mov     [rbp+arg_0], rax
0x180007b5b  call    cs:__imp_GetCurrentProcessId
0x180007b61  mov     eax, eax
0x180007b63  xor     [rbp+arg_0], rax
0x180007b67  call    cs:__imp_GetCurrentThreadId
0x180007b6d  mov     eax, eax
0x180007b6f  xor     [rbp+arg_0], rax
0x180007b73  call    cs:__imp_GetTickCount
0x180007b79  mov     eax, eax
0x180007b7b  shl     rax, 18h
0x180007b7f  xor     [rbp+arg_0], rax
0x180007b83  call    cs:__imp_GetTickCount
0x180007b89  mov     eax, eax
0x180007b8b  lea     rcx, [rbp+arg_0]
0x180007b8f  xor     rax, [rbp+arg_0]
0x180007b93  xor     rax, rcx
0x180007b96  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180007b9a  mov     [rbp+arg_0], rax
0x180007b9e  call    cs:__imp_QueryPerformanceCounter
0x180007ba4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180007ba7  mov     rcx, 0FFFFFFFFFFFFh
0x180007bb1  shl     rax, 20h
0x180007bb5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180007bb9  xor     rax, [rbp+arg_0]
0x180007bbd  and     rax, rcx
0x180007bc0  mov     rcx, rax
0x180007bc3  cmp     rax, rbx
0x180007bc6  jnz     short loc_180007BD5
0x180007bc8  mov     rax, 2B992DDFA233h
0x180007bd2  mov     rcx, rax
0x180007bd5  mov     cs:__security_cookie, rcx
0x180007bdc  mov     rbx, [rsp+20h+arg_18]
0x180007be1  not     rax
0x180007be4  mov     cs:__security_cookie_complement, rax
0x180007beb  add     rsp, 20h
0x180007bef  pop     rbp
0x180007bf0  retn
```
