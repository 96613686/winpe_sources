# __security_init_cookie

- ea: `0x180020680`
- end: `0x180020735`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001feb0`

## callees

- `0x180020680`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800206cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800206cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800206c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800206c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800206b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800206b5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800206df`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800206df`

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
0x180020680  mov     [rsp-8+arg_10], rbx
0x180020685  push    rbp
0x180020686  mov     rbp, rsp
0x180020689  sub     rsp, 30h
0x18002068d  mov     rax, cs:__security_cookie
0x180020694  mov     rbx, 2B992DDFA232h
0x18002069e  cmp     rax, rbx
0x1800206a1  jnz     short loc_180020720
0x1800206a3  xor     eax, eax
0x1800206a5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800206a9  mov     [rbp+var_10], rax
0x1800206ad  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800206b1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800206b5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800206bb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800206bf  mov     [rbp+var_10], rax
0x1800206c3  call    cs:__imp_GetCurrentThreadId
0x1800206c9  mov     eax, eax
0x1800206cb  xor     [rbp+var_10], rax
0x1800206cf  call    cs:__imp_GetCurrentProcessId
0x1800206d5  mov     eax, eax
0x1800206d7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800206db  xor     [rbp+var_10], rax
0x1800206df  call    cs:__imp_QueryPerformanceCounter
0x1800206e5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800206e8  lea     rcx, [rbp+var_10]
0x1800206ec  shl     rax, 20h
0x1800206f0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800206f4  xor     rax, [rbp+var_10]
0x1800206f8  xor     rax, rcx
0x1800206fb  mov     rcx, 0FFFFFFFFFFFFh
0x180020705  and     rax, rcx
0x180020708  mov     rcx, 2B992DDFA233h
0x180020712  cmp     rax, rbx
0x180020715  cmovz   rax, rcx
0x180020719  mov     cs:__security_cookie, rax
0x180020720  mov     rbx, [rsp+30h+arg_10]
0x180020725  not     rax
0x180020728  mov     cs:__security_cookie_complement, rax
0x18002072f  add     rsp, 30h
0x180020733  pop     rbp
0x180020734  retn
```
