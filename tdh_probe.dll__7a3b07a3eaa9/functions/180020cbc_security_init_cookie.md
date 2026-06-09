# __security_init_cookie

- ea: `0x180020cbc`
- end: `0x180020d71`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020770`

## callees

- `0x180020cbc`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180020d1b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180020d1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020d0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020d0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020cff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020cff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180020cf1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180020cf1`

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
0x180020cbc  mov     [rsp-8+arg_10], rbx
0x180020cc1  push    rbp
0x180020cc2  mov     rbp, rsp
0x180020cc5  sub     rsp, 30h
0x180020cc9  mov     rax, cs:__security_cookie
0x180020cd0  mov     rbx, 2B992DDFA232h
0x180020cda  cmp     rax, rbx
0x180020cdd  jnz     short loc_180020D5C
0x180020cdf  xor     eax, eax
0x180020ce1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180020ce5  mov     [rbp+var_10], rax
0x180020ce9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180020ced  mov     qword ptr [rbp+PerformanceCount], rax
0x180020cf1  call    cs:__imp_GetSystemTimeAsFileTime
0x180020cf7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180020cfb  mov     [rbp+var_10], rax
0x180020cff  call    cs:__imp_GetCurrentThreadId
0x180020d05  mov     eax, eax
0x180020d07  xor     [rbp+var_10], rax
0x180020d0b  call    cs:__imp_GetCurrentProcessId
0x180020d11  mov     eax, eax
0x180020d13  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180020d17  xor     [rbp+var_10], rax
0x180020d1b  call    cs:__imp_QueryPerformanceCounter
0x180020d21  mov     eax, dword ptr [rbp+PerformanceCount]
0x180020d24  lea     rcx, [rbp+var_10]
0x180020d28  shl     rax, 20h
0x180020d2c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180020d30  xor     rax, [rbp+var_10]
0x180020d34  xor     rax, rcx
0x180020d37  mov     rcx, 0FFFFFFFFFFFFh
0x180020d41  and     rax, rcx
0x180020d44  mov     rcx, 2B992DDFA233h
0x180020d4e  cmp     rax, rbx
0x180020d51  cmovz   rax, rcx
0x180020d55  mov     cs:__security_cookie, rax
0x180020d5c  mov     rbx, [rsp+30h+arg_10]
0x180020d61  not     rax
0x180020d64  mov     cs:__security_cookie_complement, rax
0x180020d6b  add     rsp, 30h
0x180020d6f  pop     rbp
0x180020d70  retn
```
