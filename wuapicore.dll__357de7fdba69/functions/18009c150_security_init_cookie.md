# __security_init_cookie

- ea: `0x18009c150`
- end: `0x18009c207`
- name: `__security_init_cookie`
- size: `183`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009bca0`

## callees

- `0x18009c150`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009c1a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009c1a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c195`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c195`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18009c187`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18009c187`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18009c1b1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18009c1b1`

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
0x18009c150  mov     [rsp-8+arg_10], rbx
0x18009c155  push    rbp
0x18009c156  mov     rbp, rsp
0x18009c159  sub     rsp, 30h
0x18009c15d  mov     rax, cs:__security_cookie
0x18009c164  mov     rbx, 2B992DDFA232h
0x18009c16e  cmp     rax, rbx
0x18009c171  jnz     short loc_18009C1F2
0x18009c173  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18009c177  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18009c17f  mov     qword ptr [rbp+PerformanceCount], 0
0x18009c187  call    cs:__imp_GetSystemTimeAsFileTime
0x18009c18d  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18009c191  mov     [rbp+var_10], rax
0x18009c195  call    cs:__imp_GetCurrentThreadId
0x18009c19b  mov     eax, eax
0x18009c19d  xor     [rbp+var_10], rax
0x18009c1a1  call    cs:__imp_GetCurrentProcessId
0x18009c1a7  mov     eax, eax
0x18009c1a9  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18009c1ad  xor     [rbp+var_10], rax
0x18009c1b1  call    cs:__imp_QueryPerformanceCounter
0x18009c1b7  mov     eax, dword ptr [rbp+PerformanceCount]
0x18009c1ba  lea     rcx, [rbp+var_10]
0x18009c1be  shl     rax, 20h
0x18009c1c2  xor     rax, qword ptr [rbp+PerformanceCount]
0x18009c1c6  xor     rax, [rbp+var_10]
0x18009c1ca  xor     rax, rcx
0x18009c1cd  mov     rcx, 0FFFFFFFFFFFFh
0x18009c1d7  and     rax, rcx
0x18009c1da  mov     rcx, 2B992DDFA233h
0x18009c1e4  cmp     rax, rbx
0x18009c1e7  cmovz   rax, rcx
0x18009c1eb  mov     cs:__security_cookie, rax
0x18009c1f2  mov     rbx, [rsp+30h+arg_10]
0x18009c1f7  not     rax
0x18009c1fa  mov     cs:__security_cookie_complement, rax
0x18009c201  add     rsp, 30h
0x18009c205  pop     rbp
0x18009c206  retn
```
