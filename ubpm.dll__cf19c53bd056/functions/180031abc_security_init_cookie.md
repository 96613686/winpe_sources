# __security_init_cookie

- ea: `0x180031abc`
- end: `0x180031b99`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180031760`

## callees

- `0x180031abc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180031b03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180031b03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031b0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031b0f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180031b46`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180031b46`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180031af5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180031af5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180031b1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180031b2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180031b1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180031b2b`

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
0x180031abc  mov     [rsp-8+arg_18], rbx
0x180031ac1  push    rbp
0x180031ac2  mov     rbp, rsp
0x180031ac5  sub     rsp, 20h
0x180031ac9  xor     eax, eax
0x180031acb  mov     rbx, 2B992DDFA232h
0x180031ad5  mov     [rbp+arg_0], rax
0x180031ad9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180031add  mov     qword ptr [rbp+PerformanceCount], rax
0x180031ae1  mov     rax, cs:__security_cookie
0x180031ae8  cmp     rax, rbx
0x180031aeb  jnz     loc_180031B84
0x180031af1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180031af5  call    cs:__imp_GetSystemTimeAsFileTime
0x180031afb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180031aff  mov     [rbp+arg_0], rax
0x180031b03  call    cs:__imp_GetCurrentProcessId
0x180031b09  mov     eax, eax
0x180031b0b  xor     [rbp+arg_0], rax
0x180031b0f  call    cs:__imp_GetCurrentThreadId
0x180031b15  mov     eax, eax
0x180031b17  xor     [rbp+arg_0], rax
0x180031b1b  call    cs:__imp_GetTickCount
0x180031b21  mov     eax, eax
0x180031b23  shl     rax, 18h
0x180031b27  xor     [rbp+arg_0], rax
0x180031b2b  call    cs:__imp_GetTickCount
0x180031b31  mov     eax, eax
0x180031b33  lea     rcx, [rbp+arg_0]
0x180031b37  xor     rax, [rbp+arg_0]
0x180031b3b  xor     rax, rcx
0x180031b3e  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180031b42  mov     [rbp+arg_0], rax
0x180031b46  call    cs:__imp_QueryPerformanceCounter
0x180031b4c  mov     eax, dword ptr [rbp+PerformanceCount]
0x180031b4f  mov     rcx, 0FFFFFFFFFFFFh
0x180031b59  shl     rax, 20h
0x180031b5d  xor     rax, qword ptr [rbp+PerformanceCount]
0x180031b61  xor     rax, [rbp+arg_0]
0x180031b65  and     rax, rcx
0x180031b68  mov     rcx, rax
0x180031b6b  cmp     rax, rbx
0x180031b6e  jnz     short loc_180031B7D
0x180031b70  mov     rax, 2B992DDFA233h
0x180031b7a  mov     rcx, rax
0x180031b7d  mov     cs:__security_cookie, rcx
0x180031b84  mov     rbx, [rsp+20h+arg_18]
0x180031b89  not     rax
0x180031b8c  mov     cs:__security_cookie_complement, rax
0x180031b93  add     rsp, 20h
0x180031b97  pop     rbp
0x180031b98  retn
```
