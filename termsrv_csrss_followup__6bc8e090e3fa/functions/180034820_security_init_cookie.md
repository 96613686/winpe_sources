# __security_init_cookie

- ea: `0x180034820`
- end: `0x1800348d5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180033f00`

## callees

- `0x180034820`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003486f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003486f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034863`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034863`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180034855`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180034855`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003487f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003487f`

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
0x180034820  mov     [rsp-8+arg_10], rbx
0x180034825  push    rbp
0x180034826  mov     rbp, rsp
0x180034829  sub     rsp, 30h
0x18003482d  mov     rax, cs:__security_cookie
0x180034834  mov     rbx, 2B992DDFA232h
0x18003483e  cmp     rax, rbx
0x180034841  jnz     short loc_1800348C0
0x180034843  xor     eax, eax
0x180034845  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180034849  mov     [rbp+var_10], rax
0x18003484d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180034851  mov     qword ptr [rbp+PerformanceCount], rax
0x180034855  call    cs:__imp_GetSystemTimeAsFileTime
0x18003485b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003485f  mov     [rbp+var_10], rax
0x180034863  call    cs:__imp_GetCurrentThreadId
0x180034869  mov     eax, eax
0x18003486b  xor     [rbp+var_10], rax
0x18003486f  call    cs:__imp_GetCurrentProcessId
0x180034875  mov     eax, eax
0x180034877  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003487b  xor     [rbp+var_10], rax
0x18003487f  call    cs:__imp_QueryPerformanceCounter
0x180034885  mov     eax, dword ptr [rbp+PerformanceCount]
0x180034888  lea     rcx, [rbp+var_10]
0x18003488c  shl     rax, 20h
0x180034890  xor     rax, qword ptr [rbp+PerformanceCount]
0x180034894  xor     rax, [rbp+var_10]
0x180034898  xor     rax, rcx
0x18003489b  mov     rcx, 0FFFFFFFFFFFFh
0x1800348a5  and     rax, rcx
0x1800348a8  mov     rcx, 2B992DDFA233h
0x1800348b2  cmp     rax, rbx
0x1800348b5  cmovz   rax, rcx
0x1800348b9  mov     cs:__security_cookie, rax
0x1800348c0  mov     rbx, [rsp+30h+arg_10]
0x1800348c5  not     rax
0x1800348c8  mov     cs:__security_cookie_complement, rax
0x1800348cf  add     rsp, 30h
0x1800348d3  pop     rbp
0x1800348d4  retn
```
