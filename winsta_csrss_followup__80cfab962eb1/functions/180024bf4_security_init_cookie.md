# __security_init_cookie

- ea: `0x180024bf4`
- end: `0x180024cd1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800245a0`

## callees

- `0x180024bf4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024c47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024c47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024c3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024c3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180024c2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180024c2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180024c53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180024c63`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180024c53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180024c63`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180024c7e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180024c7e`

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
0x180024bf4  mov     [rsp-8+arg_18], rbx
0x180024bf9  push    rbp
0x180024bfa  mov     rbp, rsp
0x180024bfd  sub     rsp, 20h
0x180024c01  xor     eax, eax
0x180024c03  mov     rbx, 2B992DDFA232h
0x180024c0d  mov     [rbp+arg_0], rax
0x180024c11  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180024c15  mov     qword ptr [rbp+PerformanceCount], rax
0x180024c19  mov     rax, cs:__security_cookie
0x180024c20  cmp     rax, rbx
0x180024c23  jnz     loc_180024CBC
0x180024c29  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180024c2d  call    cs:__imp_GetSystemTimeAsFileTime
0x180024c33  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180024c37  mov     [rbp+arg_0], rax
0x180024c3b  call    cs:__imp_GetCurrentProcessId
0x180024c41  mov     eax, eax
0x180024c43  xor     [rbp+arg_0], rax
0x180024c47  call    cs:__imp_GetCurrentThreadId
0x180024c4d  mov     eax, eax
0x180024c4f  xor     [rbp+arg_0], rax
0x180024c53  call    cs:__imp_GetTickCount
0x180024c59  mov     eax, eax
0x180024c5b  shl     rax, 18h
0x180024c5f  xor     [rbp+arg_0], rax
0x180024c63  call    cs:__imp_GetTickCount
0x180024c69  mov     eax, eax
0x180024c6b  lea     rcx, [rbp+arg_0]
0x180024c6f  xor     rax, [rbp+arg_0]
0x180024c73  xor     rax, rcx
0x180024c76  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180024c7a  mov     [rbp+arg_0], rax
0x180024c7e  call    cs:__imp_QueryPerformanceCounter
0x180024c84  mov     eax, dword ptr [rbp+PerformanceCount]
0x180024c87  mov     rcx, 0FFFFFFFFFFFFh
0x180024c91  shl     rax, 20h
0x180024c95  xor     rax, qword ptr [rbp+PerformanceCount]
0x180024c99  xor     rax, [rbp+arg_0]
0x180024c9d  and     rax, rcx
0x180024ca0  mov     rcx, rax
0x180024ca3  cmp     rax, rbx
0x180024ca6  jnz     short loc_180024CB5
0x180024ca8  mov     rax, 2B992DDFA233h
0x180024cb2  mov     rcx, rax
0x180024cb5  mov     cs:__security_cookie, rcx
0x180024cbc  mov     rbx, [rsp+20h+arg_18]
0x180024cc1  not     rax
0x180024cc4  mov     cs:__security_cookie_complement, rax
0x180024ccb  add     rsp, 20h
0x180024ccf  pop     rbp
0x180024cd0  retn
```
