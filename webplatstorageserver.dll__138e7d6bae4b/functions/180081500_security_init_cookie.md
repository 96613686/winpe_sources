# __security_init_cookie

- ea: `0x180081500`
- end: `0x1800815b5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180080f50`

## callees

- `0x180081500`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180081543`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180081543`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008154f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008154f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180081535`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180081535`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18008155f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18008155f`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x180081500  mov     [rsp-8+arg_10], rbx
0x180081505  push    rbp
0x180081506  mov     rbp, rsp
0x180081509  sub     rsp, 30h
0x18008150d  mov     rax, cs:__security_cookie
0x180081514  mov     rbx, 2B992DDFA232h
0x18008151e  cmp     rax, rbx
0x180081521  jnz     short loc_1800815A0
0x180081523  xor     eax, eax
0x180081525  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180081529  mov     [rbp+var_10], rax
0x18008152d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180081531  mov     qword ptr [rbp+PerformanceCount], rax
0x180081535  call    cs:__imp_GetSystemTimeAsFileTime
0x18008153b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18008153f  mov     [rbp+var_10], rax
0x180081543  call    cs:__imp_GetCurrentThreadId
0x180081549  mov     eax, eax
0x18008154b  xor     [rbp+var_10], rax
0x18008154f  call    cs:__imp_GetCurrentProcessId
0x180081555  mov     eax, eax
0x180081557  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18008155b  xor     [rbp+var_10], rax
0x18008155f  call    cs:__imp_QueryPerformanceCounter
0x180081565  mov     eax, dword ptr [rbp+PerformanceCount]
0x180081568  lea     rcx, [rbp+var_10]
0x18008156c  shl     rax, 20h
0x180081570  xor     rax, qword ptr [rbp+PerformanceCount]
0x180081574  xor     rax, [rbp+var_10]
0x180081578  xor     rax, rcx
0x18008157b  mov     rcx, 0FFFFFFFFFFFFh
0x180081585  and     rax, rcx
0x180081588  mov     rcx, 2B992DDFA233h
0x180081592  cmp     rax, rbx
0x180081595  cmovz   rax, rcx
0x180081599  mov     cs:__security_cookie, rax
0x1800815a0  mov     rbx, [rsp+30h+arg_10]
0x1800815a5  not     rax
0x1800815a8  mov     cs:__security_cookie_complement, rax
0x1800815af  add     rsp, 30h
0x1800815b3  pop     rbp
0x1800815b4  retn
```
