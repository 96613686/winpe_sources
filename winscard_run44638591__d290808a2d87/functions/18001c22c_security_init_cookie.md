# __security_init_cookie

- ea: `0x18001c22c`
- end: `0x18001c2e1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001bdc0`

## callees

- `0x18001c22c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c26f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c26f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c27b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c27b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001c28b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001c28b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c261`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c261`

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
0x18001c22c  mov     [rsp-8+arg_10], rbx
0x18001c231  push    rbp
0x18001c232  mov     rbp, rsp
0x18001c235  sub     rsp, 30h
0x18001c239  mov     rax, cs:__security_cookie
0x18001c240  mov     rbx, 2B992DDFA232h
0x18001c24a  cmp     rax, rbx
0x18001c24d  jnz     short loc_18001C2CC
0x18001c24f  xor     eax, eax
0x18001c251  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001c255  mov     [rbp+var_10], rax
0x18001c259  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001c25d  mov     qword ptr [rbp+PerformanceCount], rax
0x18001c261  call    cs:__imp_GetSystemTimeAsFileTime
0x18001c267  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001c26b  mov     [rbp+var_10], rax
0x18001c26f  call    cs:__imp_GetCurrentThreadId
0x18001c275  mov     eax, eax
0x18001c277  xor     [rbp+var_10], rax
0x18001c27b  call    cs:__imp_GetCurrentProcessId
0x18001c281  mov     eax, eax
0x18001c283  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001c287  xor     [rbp+var_10], rax
0x18001c28b  call    cs:__imp_QueryPerformanceCounter
0x18001c291  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001c294  lea     rcx, [rbp+var_10]
0x18001c298  shl     rax, 20h
0x18001c29c  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001c2a0  xor     rax, [rbp+var_10]
0x18001c2a4  xor     rax, rcx
0x18001c2a7  mov     rcx, 0FFFFFFFFFFFFh
0x18001c2b1  and     rax, rcx
0x18001c2b4  mov     rcx, 2B992DDFA233h
0x18001c2be  cmp     rax, rbx
0x18001c2c1  cmovz   rax, rcx
0x18001c2c5  mov     cs:__security_cookie, rax
0x18001c2cc  mov     rbx, [rsp+30h+arg_10]
0x18001c2d1  not     rax
0x18001c2d4  mov     cs:__security_cookie_complement, rax
0x18001c2db  add     rsp, 30h
0x18001c2df  pop     rbp
0x18001c2e0  retn
```
