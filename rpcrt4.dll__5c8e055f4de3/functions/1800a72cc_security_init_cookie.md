# __security_init_cookie

- ea: `0x1800a72cc`
- end: `0x1800a73a0`
- name: `__security_init_cookie`
- size: `212`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a7128`

## callees

- `0x1800a72cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a7318`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a7318`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a7324`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a7324`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800a735b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800a735b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a730a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a730a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a7330`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a7340`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a7330`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a7340`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rcx
  struct _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  v1 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  if ( !_security_cookie || _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v1);
    v1 = (struct _FILETIME)((unsigned __int64)&v1 ^ *(unsigned __int64 *)&v1 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = 0x2B992DDFA232LL;
    if ( ((*(_QWORD *)&v1
         ^ PerformanceCount.QuadPart
         ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
        & 0xFFFFFFFFFFFFLL) != 0 )
      v0 = (*(_QWORD *)&v1
          ^ PerformanceCount.QuadPart
          ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
         & 0xFFFFFFFFFFFFLL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x1800a72cc  mov     [rsp-8+arg_18], rbx
0x1800a72d1  push    rbp
0x1800a72d2  mov     rbp, rsp
0x1800a72d5  sub     rsp, 20h
0x1800a72d9  mov     rcx, cs:__security_cookie
0x1800a72e0  xor     eax, eax
0x1800a72e2  mov     [rbp+arg_0], rax
0x1800a72e6  mov     rbx, 2B992DDFA232h
0x1800a72f0  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800a72f4  mov     qword ptr [rbp+PerformanceCount], rax
0x1800a72f8  test    rcx, rcx
0x1800a72fb  jz      short loc_1800A7306
0x1800a72fd  cmp     rcx, rbx
0x1800a7300  jnz     loc_1800A738B
0x1800a7306  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800a730a  call    cs:__imp_GetSystemTimeAsFileTime
0x1800a7310  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800a7314  mov     [rbp+arg_0], rax
0x1800a7318  call    cs:__imp_GetCurrentProcessId
0x1800a731e  mov     eax, eax
0x1800a7320  xor     [rbp+arg_0], rax
0x1800a7324  call    cs:__imp_GetCurrentThreadId
0x1800a732a  mov     eax, eax
0x1800a732c  xor     [rbp+arg_0], rax
0x1800a7330  call    cs:__imp_GetTickCount
0x1800a7336  mov     eax, eax
0x1800a7338  shl     rax, 18h
0x1800a733c  xor     [rbp+arg_0], rax
0x1800a7340  call    cs:__imp_GetTickCount
0x1800a7346  mov     eax, eax
0x1800a7348  lea     rcx, [rbp+arg_0]
0x1800a734c  xor     rax, [rbp+arg_0]
0x1800a7350  xor     rax, rcx
0x1800a7353  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800a7357  mov     [rbp+arg_0], rax
0x1800a735b  call    cs:__imp_QueryPerformanceCounter
0x1800a7361  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800a7364  mov     rcx, 0FFFFFFFFFFFFh
0x1800a736e  shl     rax, 20h
0x1800a7372  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800a7376  xor     rax, [rbp+arg_0]
0x1800a737a  and     rax, rcx
0x1800a737d  mov     rcx, rbx
0x1800a7380  cmovnz  rcx, rax
0x1800a7384  mov     cs:__security_cookie, rcx
0x1800a738b  mov     rbx, [rsp+20h+arg_18]
0x1800a7390  not     rcx
0x1800a7393  mov     cs:__security_cookie_complement, rcx
0x1800a739a  add     rsp, 20h
0x1800a739e  pop     rbp
0x1800a739f  retn
```
