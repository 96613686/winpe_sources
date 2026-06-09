# __security_init_cookie

- ea: `0x180002ed0`
- end: `0x180002f85`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002a10`

## callees

- `0x180002ed0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002f1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002f1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002f05`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002f05`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002f2f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002f2f`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x180002ed0  mov     [rsp-8+arg_10], rbx
0x180002ed5  push    rbp
0x180002ed6  mov     rbp, rsp
0x180002ed9  sub     rsp, 30h
0x180002edd  mov     rax, cs:__security_cookie
0x180002ee4  mov     rbx, 2B992DDFA232h
0x180002eee  cmp     rax, rbx
0x180002ef1  jnz     short loc_180002F70
0x180002ef3  xor     eax, eax
0x180002ef5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002ef9  mov     [rbp+var_10], rax
0x180002efd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002f01  mov     qword ptr [rbp+PerformanceCount], rax
0x180002f05  call    cs:__imp_GetSystemTimeAsFileTime
0x180002f0b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002f0f  mov     [rbp+var_10], rax
0x180002f13  call    cs:__imp_GetCurrentThreadId
0x180002f19  mov     eax, eax
0x180002f1b  xor     [rbp+var_10], rax
0x180002f1f  call    cs:__imp_GetCurrentProcessId
0x180002f25  mov     eax, eax
0x180002f27  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002f2b  xor     [rbp+var_10], rax
0x180002f2f  call    cs:__imp_QueryPerformanceCounter
0x180002f35  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002f38  lea     rcx, [rbp+var_10]
0x180002f3c  shl     rax, 20h
0x180002f40  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002f44  xor     rax, [rbp+var_10]
0x180002f48  xor     rax, rcx
0x180002f4b  mov     rcx, 0FFFFFFFFFFFFh
0x180002f55  and     rax, rcx
0x180002f58  mov     rcx, 2B992DDFA233h
0x180002f62  cmp     rax, rbx
0x180002f65  cmovz   rax, rcx
0x180002f69  mov     cs:__security_cookie, rax
0x180002f70  mov     rbx, [rsp+30h+arg_10]
0x180002f75  not     rax
0x180002f78  mov     cs:__security_cookie_complement, rax
0x180002f7f  add     rsp, 30h
0x180002f83  pop     rbp
0x180002f84  retn
```
