# __security_init_cookie

- ea: `0x1800048c4`
- end: `0x180004979`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800040d0`

## callees

- `0x1800048c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004907`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004907`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004913`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004913`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800048f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800048f9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004923`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004923`

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
0x1800048c4  mov     [rsp-8+arg_10], rbx
0x1800048c9  push    rbp
0x1800048ca  mov     rbp, rsp
0x1800048cd  sub     rsp, 30h
0x1800048d1  mov     rax, cs:__security_cookie
0x1800048d8  mov     rbx, 2B992DDFA232h
0x1800048e2  cmp     rax, rbx
0x1800048e5  jnz     short loc_180004964
0x1800048e7  xor     eax, eax
0x1800048e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800048ed  mov     [rbp+var_10], rax
0x1800048f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800048f5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800048f9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800048ff  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180004903  mov     [rbp+var_10], rax
0x180004907  call    cs:__imp_GetCurrentThreadId
0x18000490d  mov     eax, eax
0x18000490f  xor     [rbp+var_10], rax
0x180004913  call    cs:__imp_GetCurrentProcessId
0x180004919  mov     eax, eax
0x18000491b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000491f  xor     [rbp+var_10], rax
0x180004923  call    cs:__imp_QueryPerformanceCounter
0x180004929  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000492c  lea     rcx, [rbp+var_10]
0x180004930  shl     rax, 20h
0x180004934  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004938  xor     rax, [rbp+var_10]
0x18000493c  xor     rax, rcx
0x18000493f  mov     rcx, 0FFFFFFFFFFFFh
0x180004949  and     rax, rcx
0x18000494c  mov     rcx, 2B992DDFA233h
0x180004956  cmp     rax, rbx
0x180004959  cmovz   rax, rcx
0x18000495d  mov     cs:__security_cookie, rax
0x180004964  mov     rbx, [rsp+30h+arg_10]
0x180004969  not     rax
0x18000496c  mov     cs:__security_cookie_complement, rax
0x180004973  add     rsp, 30h
0x180004977  pop     rbp
0x180004978  retn
```
