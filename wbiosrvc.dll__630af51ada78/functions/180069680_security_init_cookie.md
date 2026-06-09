# __security_init_cookie

- ea: `0x180069680`
- end: `0x180069735`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180068f10`

## callees

- `0x180069680`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800696cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800696cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800696c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800696c3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800696df`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800696df`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800696b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800696b5`

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
0x180069680  mov     [rsp-8+arg_10], rbx
0x180069685  push    rbp
0x180069686  mov     rbp, rsp
0x180069689  sub     rsp, 30h
0x18006968d  mov     rax, cs:__security_cookie
0x180069694  mov     rbx, 2B992DDFA232h
0x18006969e  cmp     rax, rbx
0x1800696a1  jnz     short loc_180069720
0x1800696a3  xor     eax, eax
0x1800696a5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800696a9  mov     [rbp+var_10], rax
0x1800696ad  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800696b1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800696b5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800696bb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800696bf  mov     [rbp+var_10], rax
0x1800696c3  call    cs:__imp_GetCurrentThreadId
0x1800696c9  mov     eax, eax
0x1800696cb  xor     [rbp+var_10], rax
0x1800696cf  call    cs:__imp_GetCurrentProcessId
0x1800696d5  mov     eax, eax
0x1800696d7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800696db  xor     [rbp+var_10], rax
0x1800696df  call    cs:__imp_QueryPerformanceCounter
0x1800696e5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800696e8  lea     rcx, [rbp+var_10]
0x1800696ec  shl     rax, 20h
0x1800696f0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800696f4  xor     rax, [rbp+var_10]
0x1800696f8  xor     rax, rcx
0x1800696fb  mov     rcx, 0FFFFFFFFFFFFh
0x180069705  and     rax, rcx
0x180069708  mov     rcx, 2B992DDFA233h
0x180069712  cmp     rax, rbx
0x180069715  cmovz   rax, rcx
0x180069719  mov     cs:__security_cookie, rax
0x180069720  mov     rbx, [rsp+30h+arg_10]
0x180069725  not     rax
0x180069728  mov     cs:__security_cookie_complement, rax
0x18006972f  add     rsp, 30h
0x180069733  pop     rbp
0x180069734  retn
```
