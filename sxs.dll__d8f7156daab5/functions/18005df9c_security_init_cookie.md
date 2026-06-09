# __security_init_cookie

- ea: `0x18005df9c`
- end: `0x18005e070`
- name: `__security_init_cookie`
- size: `212`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005df7c`

## callees

- `0x18005df9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005dff4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005dff4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005dfe8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005dfe8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005dfda`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005dfda`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005e000`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005e010`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005e000`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005e010`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005e02b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005e02b`

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
0x18005df9c  mov     [rsp-8+arg_18], rbx
0x18005dfa1  push    rbp
0x18005dfa2  mov     rbp, rsp
0x18005dfa5  sub     rsp, 20h
0x18005dfa9  mov     rcx, cs:__security_cookie
0x18005dfb0  xor     eax, eax
0x18005dfb2  mov     [rbp+arg_0], rax
0x18005dfb6  mov     rbx, 2B992DDFA232h
0x18005dfc0  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18005dfc4  mov     qword ptr [rbp+PerformanceCount], rax
0x18005dfc8  test    rcx, rcx
0x18005dfcb  jz      short loc_18005DFD6
0x18005dfcd  cmp     rcx, rbx
0x18005dfd0  jnz     loc_18005E05B
0x18005dfd6  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005dfda  call    cs:__imp_GetSystemTimeAsFileTime
0x18005dfe0  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18005dfe4  mov     [rbp+arg_0], rax
0x18005dfe8  call    cs:__imp_GetCurrentProcessId
0x18005dfee  mov     eax, eax
0x18005dff0  xor     [rbp+arg_0], rax
0x18005dff4  call    cs:__imp_GetCurrentThreadId
0x18005dffa  mov     eax, eax
0x18005dffc  xor     [rbp+arg_0], rax
0x18005e000  call    cs:__imp_GetTickCount
0x18005e006  mov     eax, eax
0x18005e008  shl     rax, 18h
0x18005e00c  xor     [rbp+arg_0], rax
0x18005e010  call    cs:__imp_GetTickCount
0x18005e016  mov     eax, eax
0x18005e018  lea     rcx, [rbp+arg_0]
0x18005e01c  xor     rax, [rbp+arg_0]
0x18005e020  xor     rax, rcx
0x18005e023  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18005e027  mov     [rbp+arg_0], rax
0x18005e02b  call    cs:__imp_QueryPerformanceCounter
0x18005e031  mov     eax, dword ptr [rbp+PerformanceCount]
0x18005e034  mov     rcx, 0FFFFFFFFFFFFh
0x18005e03e  shl     rax, 20h
0x18005e042  xor     rax, qword ptr [rbp+PerformanceCount]
0x18005e046  xor     rax, [rbp+arg_0]
0x18005e04a  and     rax, rcx
0x18005e04d  mov     rcx, rbx
0x18005e050  cmovnz  rcx, rax
0x18005e054  mov     cs:__security_cookie, rcx
0x18005e05b  mov     rbx, [rsp+20h+arg_18]
0x18005e060  not     rcx
0x18005e063  mov     cs:__security_cookie_complement, rcx
0x18005e06a  add     rsp, 20h
0x18005e06e  pop     rbp
0x18005e06f  retn
```
