# __security_init_cookie

- ea: `0x180006644`
- end: `0x1800066f9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800065d0`

## callees

- `0x180006644`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006679`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006679`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006687`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006687`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006693`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006693`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800066a3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800066a3`

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
0x180006644  mov     [rsp-8+arg_10], rbx
0x180006649  push    rbp
0x18000664a  mov     rbp, rsp
0x18000664d  sub     rsp, 30h
0x180006651  mov     rax, cs:__security_cookie
0x180006658  mov     rbx, 2B992DDFA232h
0x180006662  cmp     rax, rbx
0x180006665  jnz     short loc_1800066E4
0x180006667  xor     eax, eax
0x180006669  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000666d  mov     [rbp+var_10], rax
0x180006671  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180006675  mov     qword ptr [rbp+PerformanceCount], rax
0x180006679  call    cs:__imp_GetSystemTimeAsFileTime
0x18000667f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180006683  mov     [rbp+var_10], rax
0x180006687  call    cs:__imp_GetCurrentThreadId
0x18000668d  mov     eax, eax
0x18000668f  xor     [rbp+var_10], rax
0x180006693  call    cs:__imp_GetCurrentProcessId
0x180006699  mov     eax, eax
0x18000669b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000669f  xor     [rbp+var_10], rax
0x1800066a3  call    cs:__imp_QueryPerformanceCounter
0x1800066a9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800066ac  lea     rcx, [rbp+var_10]
0x1800066b0  shl     rax, 20h
0x1800066b4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800066b8  xor     rax, [rbp+var_10]
0x1800066bc  xor     rax, rcx
0x1800066bf  mov     rcx, 0FFFFFFFFFFFFh
0x1800066c9  and     rax, rcx
0x1800066cc  mov     rcx, 2B992DDFA233h
0x1800066d6  cmp     rax, rbx
0x1800066d9  cmovz   rax, rcx
0x1800066dd  mov     cs:__security_cookie, rax
0x1800066e4  mov     rbx, [rsp+30h+arg_10]
0x1800066e9  not     rax
0x1800066ec  mov     cs:__security_cookie_complement, rax
0x1800066f3  add     rsp, 30h
0x1800066f7  pop     rbp
0x1800066f8  retn
```
