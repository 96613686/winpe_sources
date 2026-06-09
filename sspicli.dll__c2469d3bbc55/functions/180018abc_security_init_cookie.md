# __security_init_cookie

- ea: `0x180018abc`
- end: `0x180018b99`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001870c`

## callees

- `0x180018abc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018b03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018b03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018b0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018b0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180018b1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180018b2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180018b1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180018b2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180018af5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180018af5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180018b46`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180018b46`

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
0x180018abc  mov     [rsp-8+arg_18], rbx
0x180018ac1  push    rbp
0x180018ac2  mov     rbp, rsp
0x180018ac5  sub     rsp, 20h
0x180018ac9  xor     eax, eax
0x180018acb  mov     rbx, 2B992DDFA232h
0x180018ad5  mov     [rbp+arg_0], rax
0x180018ad9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180018add  mov     qword ptr [rbp+PerformanceCount], rax
0x180018ae1  mov     rax, cs:__security_cookie
0x180018ae8  cmp     rax, rbx
0x180018aeb  jnz     loc_180018B84
0x180018af1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180018af5  call    cs:__imp_GetSystemTimeAsFileTime
0x180018afb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180018aff  mov     [rbp+arg_0], rax
0x180018b03  call    cs:__imp_GetCurrentProcessId
0x180018b09  mov     eax, eax
0x180018b0b  xor     [rbp+arg_0], rax
0x180018b0f  call    cs:__imp_GetCurrentThreadId
0x180018b15  mov     eax, eax
0x180018b17  xor     [rbp+arg_0], rax
0x180018b1b  call    cs:__imp_GetTickCount
0x180018b21  mov     eax, eax
0x180018b23  shl     rax, 18h
0x180018b27  xor     [rbp+arg_0], rax
0x180018b2b  call    cs:__imp_GetTickCount
0x180018b31  mov     eax, eax
0x180018b33  lea     rcx, [rbp+arg_0]
0x180018b37  xor     rax, [rbp+arg_0]
0x180018b3b  xor     rax, rcx
0x180018b3e  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180018b42  mov     [rbp+arg_0], rax
0x180018b46  call    cs:__imp_QueryPerformanceCounter
0x180018b4c  mov     eax, dword ptr [rbp+PerformanceCount]
0x180018b4f  mov     rcx, 0FFFFFFFFFFFFh
0x180018b59  shl     rax, 20h
0x180018b5d  xor     rax, qword ptr [rbp+PerformanceCount]
0x180018b61  xor     rax, [rbp+arg_0]
0x180018b65  and     rax, rcx
0x180018b68  mov     rcx, rax
0x180018b6b  cmp     rax, rbx
0x180018b6e  jnz     short loc_180018B7D
0x180018b70  mov     rax, 2B992DDFA233h
0x180018b7a  mov     rcx, rax
0x180018b7d  mov     cs:__security_cookie, rcx
0x180018b84  mov     rbx, [rsp+20h+arg_18]
0x180018b89  not     rax
0x180018b8c  mov     cs:__security_cookie_complement, rax
0x180018b93  add     rsp, 20h
0x180018b97  pop     rbp
0x180018b98  retn
```
