# __security_init_cookie

- ea: `0x180189630`
- end: `0x1801896e5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180188d30`

## callees

- `0x180189630`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180189673`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180189673`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18018967f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18018967f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18018968f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18018968f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180189665`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180189665`

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
0x180189630  mov     [rsp-8+arg_10], rbx
0x180189635  push    rbp
0x180189636  mov     rbp, rsp
0x180189639  sub     rsp, 30h
0x18018963d  mov     rax, cs:__security_cookie
0x180189644  mov     rbx, 2B992DDFA232h
0x18018964e  cmp     rax, rbx
0x180189651  jnz     short loc_1801896D0
0x180189653  xor     eax, eax
0x180189655  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180189659  mov     [rbp+var_10], rax
0x18018965d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180189661  mov     qword ptr [rbp+PerformanceCount], rax
0x180189665  call    cs:__imp_GetSystemTimeAsFileTime
0x18018966b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18018966f  mov     [rbp+var_10], rax
0x180189673  call    cs:__imp_GetCurrentThreadId
0x180189679  mov     eax, eax
0x18018967b  xor     [rbp+var_10], rax
0x18018967f  call    cs:__imp_GetCurrentProcessId
0x180189685  mov     eax, eax
0x180189687  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18018968b  xor     [rbp+var_10], rax
0x18018968f  call    cs:__imp_QueryPerformanceCounter
0x180189695  mov     eax, dword ptr [rbp+PerformanceCount]
0x180189698  lea     rcx, [rbp+var_10]
0x18018969c  shl     rax, 20h
0x1801896a0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1801896a4  xor     rax, [rbp+var_10]
0x1801896a8  xor     rax, rcx
0x1801896ab  mov     rcx, 0FFFFFFFFFFFFh
0x1801896b5  and     rax, rcx
0x1801896b8  mov     rcx, 2B992DDFA233h
0x1801896c2  cmp     rax, rbx
0x1801896c5  cmovz   rax, rcx
0x1801896c9  mov     cs:__security_cookie, rax
0x1801896d0  mov     rbx, [rsp+30h+arg_10]
0x1801896d5  not     rax
0x1801896d8  mov     cs:__security_cookie_complement, rax
0x1801896df  add     rsp, 30h
0x1801896e3  pop     rbp
0x1801896e4  retn
```
