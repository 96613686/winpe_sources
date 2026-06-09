# __security_init_cookie

- ea: `0x180003a58`
- end: `0x180003b0d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003460`

## callees

- `0x180003a58`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003a8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003a8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003a9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003a9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003aa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003aa7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003ab7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003ab7`

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
0x180003a58  mov     [rsp-8+arg_10], rbx
0x180003a5d  push    rbp
0x180003a5e  mov     rbp, rsp
0x180003a61  sub     rsp, 30h
0x180003a65  mov     rax, cs:__security_cookie
0x180003a6c  mov     rbx, 2B992DDFA232h
0x180003a76  cmp     rax, rbx
0x180003a79  jnz     short loc_180003AF8
0x180003a7b  xor     eax, eax
0x180003a7d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003a81  mov     [rbp+var_10], rax
0x180003a85  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003a89  mov     qword ptr [rbp+PerformanceCount], rax
0x180003a8d  call    cs:__imp_GetSystemTimeAsFileTime
0x180003a93  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003a97  mov     [rbp+var_10], rax
0x180003a9b  call    cs:__imp_GetCurrentThreadId
0x180003aa1  mov     eax, eax
0x180003aa3  xor     [rbp+var_10], rax
0x180003aa7  call    cs:__imp_GetCurrentProcessId
0x180003aad  mov     eax, eax
0x180003aaf  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003ab3  xor     [rbp+var_10], rax
0x180003ab7  call    cs:__imp_QueryPerformanceCounter
0x180003abd  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003ac0  lea     rcx, [rbp+var_10]
0x180003ac4  shl     rax, 20h
0x180003ac8  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003acc  xor     rax, [rbp+var_10]
0x180003ad0  xor     rax, rcx
0x180003ad3  mov     rcx, 0FFFFFFFFFFFFh
0x180003add  and     rax, rcx
0x180003ae0  mov     rcx, 2B992DDFA233h
0x180003aea  cmp     rax, rbx
0x180003aed  cmovz   rax, rcx
0x180003af1  mov     cs:__security_cookie, rax
0x180003af8  mov     rbx, [rsp+30h+arg_10]
0x180003afd  not     rax
0x180003b00  mov     cs:__security_cookie_complement, rax
0x180003b07  add     rsp, 30h
0x180003b0b  pop     rbp
0x180003b0c  retn
```
