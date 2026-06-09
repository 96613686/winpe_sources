# __security_init_cookie

- ea: `0x18005f4c4`
- end: `0x18005f5a1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005ef40`

## callees

- `0x18005f4c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f517`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f517`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005f50b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005f50b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005f54e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005f54e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005f4fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005f4fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005f523`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005f533`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005f523`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005f533`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x18005f4c4  mov     [rsp-8+arg_18], rbx
0x18005f4c9  push    rbp
0x18005f4ca  mov     rbp, rsp
0x18005f4cd  sub     rsp, 20h
0x18005f4d1  xor     eax, eax
0x18005f4d3  mov     rbx, 2B992DDFA232h
0x18005f4dd  mov     [rbp+arg_0], rax
0x18005f4e1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18005f4e5  mov     qword ptr [rbp+PerformanceCount], rax
0x18005f4e9  mov     rax, cs:__security_cookie
0x18005f4f0  cmp     rax, rbx
0x18005f4f3  jnz     loc_18005F58C
0x18005f4f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005f4fd  call    cs:__imp_GetSystemTimeAsFileTime
0x18005f503  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18005f507  mov     [rbp+arg_0], rax
0x18005f50b  call    cs:__imp_GetCurrentProcessId
0x18005f511  mov     eax, eax
0x18005f513  xor     [rbp+arg_0], rax
0x18005f517  call    cs:__imp_GetCurrentThreadId
0x18005f51d  mov     eax, eax
0x18005f51f  xor     [rbp+arg_0], rax
0x18005f523  call    cs:__imp_GetTickCount
0x18005f529  mov     eax, eax
0x18005f52b  shl     rax, 18h
0x18005f52f  xor     [rbp+arg_0], rax
0x18005f533  call    cs:__imp_GetTickCount
0x18005f539  mov     eax, eax
0x18005f53b  lea     rcx, [rbp+arg_0]
0x18005f53f  xor     rax, [rbp+arg_0]
0x18005f543  xor     rax, rcx
0x18005f546  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18005f54a  mov     [rbp+arg_0], rax
0x18005f54e  call    cs:__imp_QueryPerformanceCounter
0x18005f554  mov     eax, dword ptr [rbp+PerformanceCount]
0x18005f557  mov     rcx, 0FFFFFFFFFFFFh
0x18005f561  shl     rax, 20h
0x18005f565  xor     rax, qword ptr [rbp+PerformanceCount]
0x18005f569  xor     rax, [rbp+arg_0]
0x18005f56d  and     rax, rcx
0x18005f570  mov     rcx, rax
0x18005f573  cmp     rax, rbx
0x18005f576  jnz     short loc_18005F585
0x18005f578  mov     rax, 2B992DDFA233h
0x18005f582  mov     rcx, rax
0x18005f585  mov     cs:__security_cookie, rcx
0x18005f58c  mov     rbx, [rsp+20h+arg_18]
0x18005f591  not     rax
0x18005f594  mov     cs:__security_cookie_complement, rax
0x18005f59b  add     rsp, 20h
0x18005f59f  pop     rbp
0x18005f5a0  retn
```
