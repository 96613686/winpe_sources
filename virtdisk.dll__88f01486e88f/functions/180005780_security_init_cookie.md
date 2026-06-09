# __security_init_cookie

- ea: `0x180005780`
- end: `0x180005835`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800056e0`

## callees

- `0x180005780`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800057b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800057b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800057cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800057cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800057c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800057c3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800057df`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800057df`

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
0x180005780  mov     [rsp-8+arg_10], rbx
0x180005785  push    rbp
0x180005786  mov     rbp, rsp
0x180005789  sub     rsp, 30h
0x18000578d  mov     rax, cs:__security_cookie
0x180005794  mov     rbx, 2B992DDFA232h
0x18000579e  cmp     rax, rbx
0x1800057a1  jnz     short loc_180005820
0x1800057a3  xor     eax, eax
0x1800057a5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800057a9  mov     [rbp+var_10], rax
0x1800057ad  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800057b1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800057b5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800057bb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800057bf  mov     [rbp+var_10], rax
0x1800057c3  call    cs:__imp_GetCurrentThreadId
0x1800057c9  mov     eax, eax
0x1800057cb  xor     [rbp+var_10], rax
0x1800057cf  call    cs:__imp_GetCurrentProcessId
0x1800057d5  mov     eax, eax
0x1800057d7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800057db  xor     [rbp+var_10], rax
0x1800057df  call    cs:__imp_QueryPerformanceCounter
0x1800057e5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800057e8  lea     rcx, [rbp+var_10]
0x1800057ec  shl     rax, 20h
0x1800057f0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800057f4  xor     rax, [rbp+var_10]
0x1800057f8  xor     rax, rcx
0x1800057fb  mov     rcx, 0FFFFFFFFFFFFh
0x180005805  and     rax, rcx
0x180005808  mov     rcx, 2B992DDFA233h
0x180005812  cmp     rax, rbx
0x180005815  cmovz   rax, rcx
0x180005819  mov     cs:__security_cookie, rax
0x180005820  mov     rbx, [rsp+30h+arg_10]
0x180005825  not     rax
0x180005828  mov     cs:__security_cookie_complement, rax
0x18000582f  add     rsp, 30h
0x180005833  pop     rbp
0x180005834  retn
```
