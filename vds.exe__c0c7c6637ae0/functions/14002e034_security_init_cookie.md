# __security_init_cookie

- ea: `0x14002e034`
- end: `0x14002e111`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002d8f0`

## callees

- `0x14002e034`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14002e07b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14002e07b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002e087`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002e087`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14002e0be`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14002e0be`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002e06d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002e06d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002e093`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002e0a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002e093`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002e0a3`

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
0x14002e034  mov     [rsp-8+arg_18], rbx
0x14002e039  push    rbp
0x14002e03a  mov     rbp, rsp
0x14002e03d  sub     rsp, 20h
0x14002e041  xor     eax, eax
0x14002e043  mov     rbx, 2B992DDFA232h
0x14002e04d  mov     [rbp+arg_0], rax
0x14002e051  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x14002e055  mov     qword ptr [rbp+PerformanceCount], rax
0x14002e059  mov     rax, cs:__security_cookie
0x14002e060  cmp     rax, rbx
0x14002e063  jnz     loc_14002E0FC
0x14002e069  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14002e06d  call    cs:__imp_GetSystemTimeAsFileTime
0x14002e073  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14002e077  mov     [rbp+arg_0], rax
0x14002e07b  call    cs:__imp_GetCurrentProcessId
0x14002e081  mov     eax, eax
0x14002e083  xor     [rbp+arg_0], rax
0x14002e087  call    cs:__imp_GetCurrentThreadId
0x14002e08d  mov     eax, eax
0x14002e08f  xor     [rbp+arg_0], rax
0x14002e093  call    cs:__imp_GetTickCount
0x14002e099  mov     eax, eax
0x14002e09b  shl     rax, 18h
0x14002e09f  xor     [rbp+arg_0], rax
0x14002e0a3  call    cs:__imp_GetTickCount
0x14002e0a9  mov     eax, eax
0x14002e0ab  lea     rcx, [rbp+arg_0]
0x14002e0af  xor     rax, [rbp+arg_0]
0x14002e0b3  xor     rax, rcx
0x14002e0b6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14002e0ba  mov     [rbp+arg_0], rax
0x14002e0be  call    cs:__imp_QueryPerformanceCounter
0x14002e0c4  mov     eax, dword ptr [rbp+PerformanceCount]
0x14002e0c7  mov     rcx, 0FFFFFFFFFFFFh
0x14002e0d1  shl     rax, 20h
0x14002e0d5  xor     rax, qword ptr [rbp+PerformanceCount]
0x14002e0d9  xor     rax, [rbp+arg_0]
0x14002e0dd  and     rax, rcx
0x14002e0e0  mov     rcx, rax
0x14002e0e3  cmp     rax, rbx
0x14002e0e6  jnz     short loc_14002E0F5
0x14002e0e8  mov     rax, 2B992DDFA233h
0x14002e0f2  mov     rcx, rax
0x14002e0f5  mov     cs:__security_cookie, rcx
0x14002e0fc  mov     rbx, [rsp+20h+arg_18]
0x14002e101  not     rax
0x14002e104  mov     cs:__security_cookie_complement, rax
0x14002e10b  add     rsp, 20h
0x14002e10f  pop     rbp
0x14002e110  retn
```
