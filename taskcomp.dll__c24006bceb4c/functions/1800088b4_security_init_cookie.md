# __security_init_cookie

- ea: `0x1800088b4`
- end: `0x180008991`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008080`

## callees

- `0x1800088b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800088fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800088fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008907`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008907`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800088ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800088ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008913`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008923`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008913`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008923`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000893e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000893e`

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
0x1800088b4  mov     [rsp-8+arg_18], rbx
0x1800088b9  push    rbp
0x1800088ba  mov     rbp, rsp
0x1800088bd  sub     rsp, 20h
0x1800088c1  xor     eax, eax
0x1800088c3  mov     rbx, 2B992DDFA232h
0x1800088cd  mov     [rbp+arg_0], rax
0x1800088d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800088d5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800088d9  mov     rax, cs:__security_cookie
0x1800088e0  cmp     rax, rbx
0x1800088e3  jnz     loc_18000897C
0x1800088e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800088ed  call    cs:__imp_GetSystemTimeAsFileTime
0x1800088f3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800088f7  mov     [rbp+arg_0], rax
0x1800088fb  call    cs:__imp_GetCurrentProcessId
0x180008901  mov     eax, eax
0x180008903  xor     [rbp+arg_0], rax
0x180008907  call    cs:__imp_GetCurrentThreadId
0x18000890d  mov     eax, eax
0x18000890f  xor     [rbp+arg_0], rax
0x180008913  call    cs:__imp_GetTickCount
0x180008919  mov     eax, eax
0x18000891b  shl     rax, 18h
0x18000891f  xor     [rbp+arg_0], rax
0x180008923  call    cs:__imp_GetTickCount
0x180008929  mov     eax, eax
0x18000892b  lea     rcx, [rbp+arg_0]
0x18000892f  xor     rax, [rbp+arg_0]
0x180008933  xor     rax, rcx
0x180008936  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000893a  mov     [rbp+arg_0], rax
0x18000893e  call    cs:__imp_QueryPerformanceCounter
0x180008944  mov     eax, dword ptr [rbp+PerformanceCount]
0x180008947  mov     rcx, 0FFFFFFFFFFFFh
0x180008951  shl     rax, 20h
0x180008955  xor     rax, qword ptr [rbp+PerformanceCount]
0x180008959  xor     rax, [rbp+arg_0]
0x18000895d  and     rax, rcx
0x180008960  mov     rcx, rax
0x180008963  cmp     rax, rbx
0x180008966  jnz     short loc_180008975
0x180008968  mov     rax, 2B992DDFA233h
0x180008972  mov     rcx, rax
0x180008975  mov     cs:__security_cookie, rcx
0x18000897c  mov     rbx, [rsp+20h+arg_18]
0x180008981  not     rax
0x180008984  mov     cs:__security_cookie_complement, rax
0x18000898b  add     rsp, 20h
0x18000898f  pop     rbp
0x180008990  retn
```
