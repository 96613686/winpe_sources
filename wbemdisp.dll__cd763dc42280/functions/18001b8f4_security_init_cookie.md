# __security_init_cookie

- ea: `0x18001b8f4`
- end: `0x18001b9d1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b0e0`

## callees

- `0x18001b8f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b93b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b93b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b947`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b947`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001b92d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001b92d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001b953`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001b963`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001b953`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001b963`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b97e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b97e`

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
0x18001b8f4  mov     [rsp-8+arg_18], rbx
0x18001b8f9  push    rbp
0x18001b8fa  mov     rbp, rsp
0x18001b8fd  sub     rsp, 20h
0x18001b901  xor     eax, eax
0x18001b903  mov     rbx, 2B992DDFA232h
0x18001b90d  mov     [rbp+arg_0], rax
0x18001b911  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001b915  mov     qword ptr [rbp+PerformanceCount], rax
0x18001b919  mov     rax, cs:__security_cookie
0x18001b920  cmp     rax, rbx
0x18001b923  jnz     loc_18001B9BC
0x18001b929  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001b92d  call    cs:__imp_GetSystemTimeAsFileTime
0x18001b933  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001b937  mov     [rbp+arg_0], rax
0x18001b93b  call    cs:__imp_GetCurrentProcessId
0x18001b941  mov     eax, eax
0x18001b943  xor     [rbp+arg_0], rax
0x18001b947  call    cs:__imp_GetCurrentThreadId
0x18001b94d  mov     eax, eax
0x18001b94f  xor     [rbp+arg_0], rax
0x18001b953  call    cs:__imp_GetTickCount
0x18001b959  mov     eax, eax
0x18001b95b  shl     rax, 18h
0x18001b95f  xor     [rbp+arg_0], rax
0x18001b963  call    cs:__imp_GetTickCount
0x18001b969  mov     eax, eax
0x18001b96b  lea     rcx, [rbp+arg_0]
0x18001b96f  xor     rax, [rbp+arg_0]
0x18001b973  xor     rax, rcx
0x18001b976  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001b97a  mov     [rbp+arg_0], rax
0x18001b97e  call    cs:__imp_QueryPerformanceCounter
0x18001b984  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001b987  mov     rcx, 0FFFFFFFFFFFFh
0x18001b991  shl     rax, 20h
0x18001b995  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001b999  xor     rax, [rbp+arg_0]
0x18001b99d  and     rax, rcx
0x18001b9a0  mov     rcx, rax
0x18001b9a3  cmp     rax, rbx
0x18001b9a6  jnz     short loc_18001B9B5
0x18001b9a8  mov     rax, 2B992DDFA233h
0x18001b9b2  mov     rcx, rax
0x18001b9b5  mov     cs:__security_cookie, rcx
0x18001b9bc  mov     rbx, [rsp+20h+arg_18]
0x18001b9c1  not     rax
0x18001b9c4  mov     cs:__security_cookie_complement, rax
0x18001b9cb  add     rsp, 20h
0x18001b9cf  pop     rbp
0x18001b9d0  retn
```
