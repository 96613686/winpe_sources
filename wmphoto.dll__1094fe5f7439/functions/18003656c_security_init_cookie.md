# __security_init_cookie

- ea: `0x18003656c`
- end: `0x180036621`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180035e00`

## callees

- `0x18003656c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800365bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800365bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800365af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800365af`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800365cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800365cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800365a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800365a1`

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
0x18003656c  mov     [rsp-8+arg_10], rbx
0x180036571  push    rbp
0x180036572  mov     rbp, rsp
0x180036575  sub     rsp, 30h
0x180036579  mov     rax, cs:__security_cookie
0x180036580  mov     rbx, 2B992DDFA232h
0x18003658a  cmp     rax, rbx
0x18003658d  jnz     short loc_18003660C
0x18003658f  xor     eax, eax
0x180036591  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180036595  mov     [rbp+var_10], rax
0x180036599  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003659d  mov     qword ptr [rbp+PerformanceCount], rax
0x1800365a1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800365a7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800365ab  mov     [rbp+var_10], rax
0x1800365af  call    cs:__imp_GetCurrentThreadId
0x1800365b5  mov     eax, eax
0x1800365b7  xor     [rbp+var_10], rax
0x1800365bb  call    cs:__imp_GetCurrentProcessId
0x1800365c1  mov     eax, eax
0x1800365c3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800365c7  xor     [rbp+var_10], rax
0x1800365cb  call    cs:__imp_QueryPerformanceCounter
0x1800365d1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800365d4  lea     rcx, [rbp+var_10]
0x1800365d8  shl     rax, 20h
0x1800365dc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800365e0  xor     rax, [rbp+var_10]
0x1800365e4  xor     rax, rcx
0x1800365e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800365f1  and     rax, rcx
0x1800365f4  mov     rcx, 2B992DDFA233h
0x1800365fe  cmp     rax, rbx
0x180036601  cmovz   rax, rcx
0x180036605  mov     cs:__security_cookie, rax
0x18003660c  mov     rbx, [rsp+30h+arg_10]
0x180036611  not     rax
0x180036614  mov     cs:__security_cookie_complement, rax
0x18003661b  add     rsp, 30h
0x18003661f  pop     rbp
0x180036620  retn
```
