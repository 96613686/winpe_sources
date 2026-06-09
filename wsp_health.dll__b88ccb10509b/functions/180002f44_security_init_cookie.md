# __security_init_cookie

- ea: `0x180002f44`
- end: `0x180002ff9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002a80`

## callees

- `0x180002f44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002f93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002f93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f87`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002f79`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002f79`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002fa3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002fa3`

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
0x180002f44  mov     [rsp-8+arg_10], rbx
0x180002f49  push    rbp
0x180002f4a  mov     rbp, rsp
0x180002f4d  sub     rsp, 30h
0x180002f51  mov     rax, cs:__security_cookie
0x180002f58  mov     rbx, 2B992DDFA232h
0x180002f62  cmp     rax, rbx
0x180002f65  jnz     short loc_180002FE4
0x180002f67  xor     eax, eax
0x180002f69  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002f6d  mov     [rbp+var_10], rax
0x180002f71  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002f75  mov     qword ptr [rbp+PerformanceCount], rax
0x180002f79  call    cs:__imp_GetSystemTimeAsFileTime
0x180002f7f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002f83  mov     [rbp+var_10], rax
0x180002f87  call    cs:__imp_GetCurrentThreadId
0x180002f8d  mov     eax, eax
0x180002f8f  xor     [rbp+var_10], rax
0x180002f93  call    cs:__imp_GetCurrentProcessId
0x180002f99  mov     eax, eax
0x180002f9b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002f9f  xor     [rbp+var_10], rax
0x180002fa3  call    cs:__imp_QueryPerformanceCounter
0x180002fa9  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002fac  lea     rcx, [rbp+var_10]
0x180002fb0  shl     rax, 20h
0x180002fb4  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002fb8  xor     rax, [rbp+var_10]
0x180002fbc  xor     rax, rcx
0x180002fbf  mov     rcx, 0FFFFFFFFFFFFh
0x180002fc9  and     rax, rcx
0x180002fcc  mov     rcx, 2B992DDFA233h
0x180002fd6  cmp     rax, rbx
0x180002fd9  cmovz   rax, rcx
0x180002fdd  mov     cs:__security_cookie, rax
0x180002fe4  mov     rbx, [rsp+30h+arg_10]
0x180002fe9  not     rax
0x180002fec  mov     cs:__security_cookie_complement, rax
0x180002ff3  add     rsp, 30h
0x180002ff7  pop     rbp
0x180002ff8  retn
```
