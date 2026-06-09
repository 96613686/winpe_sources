# __security_init_cookie

- ea: `0x18001a618`
- end: `0x18001a6cd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a070`

## callees

- `0x18001a618`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a667`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a667`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a65b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a65b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001a677`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001a677`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001a64d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001a64d`

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
0x18001a618  mov     [rsp-8+arg_10], rbx
0x18001a61d  push    rbp
0x18001a61e  mov     rbp, rsp
0x18001a621  sub     rsp, 30h
0x18001a625  mov     rax, cs:__security_cookie
0x18001a62c  mov     rbx, 2B992DDFA232h
0x18001a636  cmp     rax, rbx
0x18001a639  jnz     short loc_18001A6B8
0x18001a63b  xor     eax, eax
0x18001a63d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001a641  mov     [rbp+var_10], rax
0x18001a645  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001a649  mov     qword ptr [rbp+PerformanceCount], rax
0x18001a64d  call    cs:__imp_GetSystemTimeAsFileTime
0x18001a653  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001a657  mov     [rbp+var_10], rax
0x18001a65b  call    cs:__imp_GetCurrentThreadId
0x18001a661  mov     eax, eax
0x18001a663  xor     [rbp+var_10], rax
0x18001a667  call    cs:__imp_GetCurrentProcessId
0x18001a66d  mov     eax, eax
0x18001a66f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001a673  xor     [rbp+var_10], rax
0x18001a677  call    cs:__imp_QueryPerformanceCounter
0x18001a67d  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001a680  lea     rcx, [rbp+var_10]
0x18001a684  shl     rax, 20h
0x18001a688  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001a68c  xor     rax, [rbp+var_10]
0x18001a690  xor     rax, rcx
0x18001a693  mov     rcx, 0FFFFFFFFFFFFh
0x18001a69d  and     rax, rcx
0x18001a6a0  mov     rcx, 2B992DDFA233h
0x18001a6aa  cmp     rax, rbx
0x18001a6ad  cmovz   rax, rcx
0x18001a6b1  mov     cs:__security_cookie, rax
0x18001a6b8  mov     rbx, [rsp+30h+arg_10]
0x18001a6bd  not     rax
0x18001a6c0  mov     cs:__security_cookie_complement, rax
0x18001a6c7  add     rsp, 30h
0x18001a6cb  pop     rbp
0x18001a6cc  retn
```
