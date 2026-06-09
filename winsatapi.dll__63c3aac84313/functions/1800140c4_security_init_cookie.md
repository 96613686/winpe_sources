# __security_init_cookie

- ea: `0x1800140c4`
- end: `0x1800141a1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800135f0`

## callees

- `0x1800140c4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014123`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014133`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014123`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014133`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800140fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800140fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014117`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014117`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001410b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001410b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001414e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001414e`

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
0x1800140c4  mov     [rsp-8+arg_18], rbx
0x1800140c9  push    rbp
0x1800140ca  mov     rbp, rsp
0x1800140cd  sub     rsp, 20h
0x1800140d1  xor     eax, eax
0x1800140d3  mov     rbx, 2B992DDFA232h
0x1800140dd  mov     [rbp+arg_0], rax
0x1800140e1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800140e5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800140e9  mov     rax, cs:__security_cookie
0x1800140f0  cmp     rax, rbx
0x1800140f3  jnz     loc_18001418C
0x1800140f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800140fd  call    cs:__imp_GetSystemTimeAsFileTime
0x180014103  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180014107  mov     [rbp+arg_0], rax
0x18001410b  call    cs:__imp_GetCurrentProcessId
0x180014111  mov     eax, eax
0x180014113  xor     [rbp+arg_0], rax
0x180014117  call    cs:__imp_GetCurrentThreadId
0x18001411d  mov     eax, eax
0x18001411f  xor     [rbp+arg_0], rax
0x180014123  call    cs:__imp_GetTickCount
0x180014129  mov     eax, eax
0x18001412b  shl     rax, 18h
0x18001412f  xor     [rbp+arg_0], rax
0x180014133  call    cs:__imp_GetTickCount
0x180014139  mov     eax, eax
0x18001413b  lea     rcx, [rbp+arg_0]
0x18001413f  xor     rax, [rbp+arg_0]
0x180014143  xor     rax, rcx
0x180014146  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001414a  mov     [rbp+arg_0], rax
0x18001414e  call    cs:__imp_QueryPerformanceCounter
0x180014154  mov     eax, dword ptr [rbp+PerformanceCount]
0x180014157  mov     rcx, 0FFFFFFFFFFFFh
0x180014161  shl     rax, 20h
0x180014165  xor     rax, qword ptr [rbp+PerformanceCount]
0x180014169  xor     rax, [rbp+arg_0]
0x18001416d  and     rax, rcx
0x180014170  mov     rcx, rax
0x180014173  cmp     rax, rbx
0x180014176  jnz     short loc_180014185
0x180014178  mov     rax, 2B992DDFA233h
0x180014182  mov     rcx, rax
0x180014185  mov     cs:__security_cookie, rcx
0x18001418c  mov     rbx, [rsp+20h+arg_18]
0x180014191  not     rax
0x180014194  mov     cs:__security_cookie_complement, rax
0x18001419b  add     rsp, 20h
0x18001419f  pop     rbp
0x1800141a0  retn
```
