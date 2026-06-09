# __security_init_cookie

- ea: `0x180024f9c`
- end: `0x180025051`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024a00`

## callees

- `0x180024f9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024feb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024feb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024fdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024fdf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180024ffb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180024ffb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180024fd1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180024fd1`

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
0x180024f9c  mov     [rsp-8+arg_10], rbx
0x180024fa1  push    rbp
0x180024fa2  mov     rbp, rsp
0x180024fa5  sub     rsp, 30h
0x180024fa9  mov     rax, cs:__security_cookie
0x180024fb0  mov     rbx, 2B992DDFA232h
0x180024fba  cmp     rax, rbx
0x180024fbd  jnz     short loc_18002503C
0x180024fbf  xor     eax, eax
0x180024fc1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180024fc5  mov     [rbp+var_10], rax
0x180024fc9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180024fcd  mov     qword ptr [rbp+PerformanceCount], rax
0x180024fd1  call    cs:__imp_GetSystemTimeAsFileTime
0x180024fd7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180024fdb  mov     [rbp+var_10], rax
0x180024fdf  call    cs:__imp_GetCurrentThreadId
0x180024fe5  mov     eax, eax
0x180024fe7  xor     [rbp+var_10], rax
0x180024feb  call    cs:__imp_GetCurrentProcessId
0x180024ff1  mov     eax, eax
0x180024ff3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180024ff7  xor     [rbp+var_10], rax
0x180024ffb  call    cs:__imp_QueryPerformanceCounter
0x180025001  mov     eax, dword ptr [rbp+PerformanceCount]
0x180025004  lea     rcx, [rbp+var_10]
0x180025008  shl     rax, 20h
0x18002500c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180025010  xor     rax, [rbp+var_10]
0x180025014  xor     rax, rcx
0x180025017  mov     rcx, 0FFFFFFFFFFFFh
0x180025021  and     rax, rcx
0x180025024  mov     rcx, 2B992DDFA233h
0x18002502e  cmp     rax, rbx
0x180025031  cmovz   rax, rcx
0x180025035  mov     cs:__security_cookie, rax
0x18002503c  mov     rbx, [rsp+30h+arg_10]
0x180025041  not     rax
0x180025044  mov     cs:__security_cookie_complement, rax
0x18002504b  add     rsp, 30h
0x18002504f  pop     rbp
0x180025050  retn
```
