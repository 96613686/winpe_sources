# __security_init_cookie

- ea: `0x18000194c`
- end: `0x180001a01`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800014b0`

## callees

- `0x18000194c`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800019ab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800019ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000199b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000199b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000198f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000198f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001981`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001981`

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
0x18000194c  mov     [rsp-8+arg_10], rbx
0x180001951  push    rbp
0x180001952  mov     rbp, rsp
0x180001955  sub     rsp, 30h
0x180001959  mov     rax, cs:__security_cookie
0x180001960  mov     rbx, 2B992DDFA232h
0x18000196a  cmp     rax, rbx
0x18000196d  jnz     short loc_1800019EC
0x18000196f  xor     eax, eax
0x180001971  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001975  mov     [rbp+var_10], rax
0x180001979  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000197d  mov     qword ptr [rbp+PerformanceCount], rax
0x180001981  call    cs:__imp_GetSystemTimeAsFileTime
0x180001987  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000198b  mov     [rbp+var_10], rax
0x18000198f  call    cs:__imp_GetCurrentThreadId
0x180001995  mov     eax, eax
0x180001997  xor     [rbp+var_10], rax
0x18000199b  call    cs:__imp_GetCurrentProcessId
0x1800019a1  mov     eax, eax
0x1800019a3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800019a7  xor     [rbp+var_10], rax
0x1800019ab  call    cs:__imp_QueryPerformanceCounter
0x1800019b1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800019b4  lea     rcx, [rbp+var_10]
0x1800019b8  shl     rax, 20h
0x1800019bc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800019c0  xor     rax, [rbp+var_10]
0x1800019c4  xor     rax, rcx
0x1800019c7  mov     rcx, 0FFFFFFFFFFFFh
0x1800019d1  and     rax, rcx
0x1800019d4  mov     rcx, 2B992DDFA233h
0x1800019de  cmp     rax, rbx
0x1800019e1  cmovz   rax, rcx
0x1800019e5  mov     cs:__security_cookie, rax
0x1800019ec  mov     rbx, [rsp+30h+arg_10]
0x1800019f1  not     rax
0x1800019f4  mov     cs:__security_cookie_complement, rax
0x1800019fb  add     rsp, 30h
0x1800019ff  pop     rbp
0x180001a00  retn
```
