# __security_init_cookie

- ea: `0x1800aab8c`
- end: `0x1800aac60`
- name: `__security_init_cookie`
- size: `212`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800aa9e8`

## callees

- `0x1800aab8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800aabd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800aabd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aabe4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aabe4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800aac1b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800aac1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800aabca`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800aabca`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800aabf0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800aac00`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800aabf0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800aac00`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rcx
  struct _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  v1 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  if ( !_security_cookie || _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v1);
    v1 = (struct _FILETIME)((unsigned __int64)&v1 ^ *(unsigned __int64 *)&v1 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = 0x2B992DDFA232LL;
    if ( ((*(_QWORD *)&v1
         ^ PerformanceCount.QuadPart
         ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
        & 0xFFFFFFFFFFFFLL) != 0 )
      v0 = (*(_QWORD *)&v1
          ^ PerformanceCount.QuadPart
          ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
         & 0xFFFFFFFFFFFFLL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x1800aab8c  mov     [rsp-8+arg_18], rbx
0x1800aab91  push    rbp
0x1800aab92  mov     rbp, rsp
0x1800aab95  sub     rsp, 20h
0x1800aab99  mov     rcx, cs:__security_cookie
0x1800aaba0  xor     eax, eax
0x1800aaba2  mov     [rbp+arg_0], rax
0x1800aaba6  mov     rbx, 2B992DDFA232h
0x1800aabb0  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800aabb4  mov     qword ptr [rbp+PerformanceCount], rax
0x1800aabb8  test    rcx, rcx
0x1800aabbb  jz      short loc_1800AABC6
0x1800aabbd  cmp     rcx, rbx
0x1800aabc0  jnz     loc_1800AAC4B
0x1800aabc6  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800aabca  call    cs:__imp_GetSystemTimeAsFileTime
0x1800aabd0  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800aabd4  mov     [rbp+arg_0], rax
0x1800aabd8  call    cs:__imp_GetCurrentProcessId
0x1800aabde  mov     eax, eax
0x1800aabe0  xor     [rbp+arg_0], rax
0x1800aabe4  call    cs:__imp_GetCurrentThreadId
0x1800aabea  mov     eax, eax
0x1800aabec  xor     [rbp+arg_0], rax
0x1800aabf0  call    cs:__imp_GetTickCount
0x1800aabf6  mov     eax, eax
0x1800aabf8  shl     rax, 18h
0x1800aabfc  xor     [rbp+arg_0], rax
0x1800aac00  call    cs:__imp_GetTickCount
0x1800aac06  mov     eax, eax
0x1800aac08  lea     rcx, [rbp+arg_0]
0x1800aac0c  xor     rax, [rbp+arg_0]
0x1800aac10  xor     rax, rcx
0x1800aac13  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800aac17  mov     [rbp+arg_0], rax
0x1800aac1b  call    cs:__imp_QueryPerformanceCounter
0x1800aac21  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800aac24  mov     rcx, 0FFFFFFFFFFFFh
0x1800aac2e  shl     rax, 20h
0x1800aac32  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800aac36  xor     rax, [rbp+arg_0]
0x1800aac3a  and     rax, rcx
0x1800aac3d  mov     rcx, rbx
0x1800aac40  cmovnz  rcx, rax
0x1800aac44  mov     cs:__security_cookie, rcx
0x1800aac4b  mov     rbx, [rsp+20h+arg_18]
0x1800aac50  not     rcx
0x1800aac53  mov     cs:__security_cookie_complement, rcx
0x1800aac5a  add     rsp, 20h
0x1800aac5e  pop     rbp
0x1800aac5f  retn
```
