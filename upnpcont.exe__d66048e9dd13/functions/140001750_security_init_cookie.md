# __security_init_cookie

- ea: `0x140001750`
- end: `0x140001805`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001460`

## callees

- `0x140001750`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000179f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000179f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001793`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001793`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400017af`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400017af`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001785`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001785`

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
0x140001750  mov     [rsp-8+arg_10], rbx
0x140001755  push    rbp
0x140001756  mov     rbp, rsp
0x140001759  sub     rsp, 30h
0x14000175d  mov     rax, cs:__security_cookie
0x140001764  mov     rbx, 2B992DDFA232h
0x14000176e  cmp     rax, rbx
0x140001771  jnz     short loc_1400017F0
0x140001773  xor     eax, eax
0x140001775  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001779  mov     [rbp+var_10], rax
0x14000177d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001781  mov     qword ptr [rbp+PerformanceCount], rax
0x140001785  call    cs:__imp_GetSystemTimeAsFileTime
0x14000178b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000178f  mov     [rbp+var_10], rax
0x140001793  call    cs:__imp_GetCurrentThreadId
0x140001799  mov     eax, eax
0x14000179b  xor     [rbp+var_10], rax
0x14000179f  call    cs:__imp_GetCurrentProcessId
0x1400017a5  mov     eax, eax
0x1400017a7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400017ab  xor     [rbp+var_10], rax
0x1400017af  call    cs:__imp_QueryPerformanceCounter
0x1400017b5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400017b8  lea     rcx, [rbp+var_10]
0x1400017bc  shl     rax, 20h
0x1400017c0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400017c4  xor     rax, [rbp+var_10]
0x1400017c8  xor     rax, rcx
0x1400017cb  mov     rcx, 0FFFFFFFFFFFFh
0x1400017d5  and     rax, rcx
0x1400017d8  mov     rcx, 2B992DDFA233h
0x1400017e2  cmp     rax, rbx
0x1400017e5  cmovz   rax, rcx
0x1400017e9  mov     cs:__security_cookie, rax
0x1400017f0  mov     rbx, [rsp+30h+arg_10]
0x1400017f5  not     rax
0x1400017f8  mov     cs:__security_cookie_complement, rax
0x1400017ff  add     rsp, 30h
0x140001803  pop     rbp
0x140001804  retn
```
