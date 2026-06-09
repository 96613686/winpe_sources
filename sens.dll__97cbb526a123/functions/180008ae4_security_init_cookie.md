# __security_init_cookie

- ea: `0x180008ae4`
- end: `0x180008bc1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800085b0`

## callees

- `0x180008ae4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008b43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008b53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008b43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008b53`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008b1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008b1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008b2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008b2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008b37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008b37`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008b6e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008b6e`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x180008ae4  mov     [rsp-8+arg_18], rbx
0x180008ae9  push    rbp
0x180008aea  mov     rbp, rsp
0x180008aed  sub     rsp, 20h
0x180008af1  xor     eax, eax
0x180008af3  mov     rbx, 2B992DDFA232h
0x180008afd  mov     [rbp+arg_0], rax
0x180008b01  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180008b05  mov     qword ptr [rbp+PerformanceCount], rax
0x180008b09  mov     rax, cs:__security_cookie
0x180008b10  cmp     rax, rbx
0x180008b13  jnz     loc_180008BAC
0x180008b19  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180008b1d  call    cs:__imp_GetSystemTimeAsFileTime
0x180008b23  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180008b27  mov     [rbp+arg_0], rax
0x180008b2b  call    cs:__imp_GetCurrentProcessId
0x180008b31  mov     eax, eax
0x180008b33  xor     [rbp+arg_0], rax
0x180008b37  call    cs:__imp_GetCurrentThreadId
0x180008b3d  mov     eax, eax
0x180008b3f  xor     [rbp+arg_0], rax
0x180008b43  call    cs:__imp_GetTickCount
0x180008b49  mov     eax, eax
0x180008b4b  shl     rax, 18h
0x180008b4f  xor     [rbp+arg_0], rax
0x180008b53  call    cs:__imp_GetTickCount
0x180008b59  mov     eax, eax
0x180008b5b  lea     rcx, [rbp+arg_0]
0x180008b5f  xor     rax, [rbp+arg_0]
0x180008b63  xor     rax, rcx
0x180008b66  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180008b6a  mov     [rbp+arg_0], rax
0x180008b6e  call    cs:__imp_QueryPerformanceCounter
0x180008b74  mov     eax, dword ptr [rbp+PerformanceCount]
0x180008b77  mov     rcx, 0FFFFFFFFFFFFh
0x180008b81  shl     rax, 20h
0x180008b85  xor     rax, qword ptr [rbp+PerformanceCount]
0x180008b89  xor     rax, [rbp+arg_0]
0x180008b8d  and     rax, rcx
0x180008b90  mov     rcx, rax
0x180008b93  cmp     rax, rbx
0x180008b96  jnz     short loc_180008BA5
0x180008b98  mov     rax, 2B992DDFA233h
0x180008ba2  mov     rcx, rax
0x180008ba5  mov     cs:__security_cookie, rcx
0x180008bac  mov     rbx, [rsp+20h+arg_18]
0x180008bb1  not     rax
0x180008bb4  mov     cs:__security_cookie_complement, rax
0x180008bbb  add     rsp, 20h
0x180008bbf  pop     rbp
0x180008bc0  retn
```
