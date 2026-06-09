# __security_init_cookie

- ea: `0x180002fb4`
- end: `0x180003069`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002af0`

## callees

- `0x180002fb4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003003`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003003`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002ff7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002ff7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002fe9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002fe9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003013`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003013`

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
0x180002fb4  mov     [rsp-8+arg_10], rbx
0x180002fb9  push    rbp
0x180002fba  mov     rbp, rsp
0x180002fbd  sub     rsp, 30h
0x180002fc1  mov     rax, cs:__security_cookie
0x180002fc8  mov     rbx, 2B992DDFA232h
0x180002fd2  cmp     rax, rbx
0x180002fd5  jnz     short loc_180003054
0x180002fd7  xor     eax, eax
0x180002fd9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002fdd  mov     [rbp+var_10], rax
0x180002fe1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002fe5  mov     qword ptr [rbp+PerformanceCount], rax
0x180002fe9  call    cs:__imp_GetSystemTimeAsFileTime
0x180002fef  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002ff3  mov     [rbp+var_10], rax
0x180002ff7  call    cs:__imp_GetCurrentThreadId
0x180002ffd  mov     eax, eax
0x180002fff  xor     [rbp+var_10], rax
0x180003003  call    cs:__imp_GetCurrentProcessId
0x180003009  mov     eax, eax
0x18000300b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000300f  xor     [rbp+var_10], rax
0x180003013  call    cs:__imp_QueryPerformanceCounter
0x180003019  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000301c  lea     rcx, [rbp+var_10]
0x180003020  shl     rax, 20h
0x180003024  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003028  xor     rax, [rbp+var_10]
0x18000302c  xor     rax, rcx
0x18000302f  mov     rcx, 0FFFFFFFFFFFFh
0x180003039  and     rax, rcx
0x18000303c  mov     rcx, 2B992DDFA233h
0x180003046  cmp     rax, rbx
0x180003049  cmovz   rax, rcx
0x18000304d  mov     cs:__security_cookie, rax
0x180003054  mov     rbx, [rsp+30h+arg_10]
0x180003059  not     rax
0x18000305c  mov     cs:__security_cookie_complement, rax
0x180003063  add     rsp, 30h
0x180003067  pop     rbp
0x180003068  retn
```
