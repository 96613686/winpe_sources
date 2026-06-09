# __security_init_cookie

- ea: `0x1800033c4`
- end: `0x180003479`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002d40`

## callees

- `0x1800033c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003413`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003413`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800033f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800033f9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003423`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003423`

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
0x1800033c4  mov     [rsp-8+arg_10], rbx
0x1800033c9  push    rbp
0x1800033ca  mov     rbp, rsp
0x1800033cd  sub     rsp, 30h
0x1800033d1  mov     rax, cs:__security_cookie
0x1800033d8  mov     rbx, 2B992DDFA232h
0x1800033e2  cmp     rax, rbx
0x1800033e5  jnz     short loc_180003464
0x1800033e7  xor     eax, eax
0x1800033e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800033ed  mov     [rbp+var_10], rax
0x1800033f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800033f5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800033f9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800033ff  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003403  mov     [rbp+var_10], rax
0x180003407  call    cs:__imp_GetCurrentThreadId
0x18000340d  mov     eax, eax
0x18000340f  xor     [rbp+var_10], rax
0x180003413  call    cs:__imp_GetCurrentProcessId
0x180003419  mov     eax, eax
0x18000341b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000341f  xor     [rbp+var_10], rax
0x180003423  call    cs:__imp_QueryPerformanceCounter
0x180003429  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000342c  lea     rcx, [rbp+var_10]
0x180003430  shl     rax, 20h
0x180003434  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003438  xor     rax, [rbp+var_10]
0x18000343c  xor     rax, rcx
0x18000343f  mov     rcx, 0FFFFFFFFFFFFh
0x180003449  and     rax, rcx
0x18000344c  mov     rcx, 2B992DDFA233h
0x180003456  cmp     rax, rbx
0x180003459  cmovz   rax, rcx
0x18000345d  mov     cs:__security_cookie, rax
0x180003464  mov     rbx, [rsp+30h+arg_10]
0x180003469  not     rax
0x18000346c  mov     cs:__security_cookie_complement, rax
0x180003473  add     rsp, 30h
0x180003477  pop     rbp
0x180003478  retn
```
