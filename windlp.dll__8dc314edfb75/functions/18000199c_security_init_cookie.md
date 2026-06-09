# __security_init_cookie

- ea: `0x18000199c`
- end: `0x180001a79`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001640`

## callees

- `0x18000199c`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001a26`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001a26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800019ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800019ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800019d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800019d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800019fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001a0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800019fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001a0b`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x18000199c  mov     [rsp-8+arg_18], rbx
0x1800019a1  push    rbp
0x1800019a2  mov     rbp, rsp
0x1800019a5  sub     rsp, 20h
0x1800019a9  xor     eax, eax
0x1800019ab  mov     rbx, 2B992DDFA232h
0x1800019b5  mov     [rbp+arg_0], rax
0x1800019b9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800019bd  mov     qword ptr [rbp+PerformanceCount], rax
0x1800019c1  mov     rax, cs:__security_cookie
0x1800019c8  cmp     rax, rbx
0x1800019cb  jnz     loc_180001A64
0x1800019d1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800019d5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800019db  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800019df  mov     [rbp+arg_0], rax
0x1800019e3  call    cs:__imp_GetCurrentProcessId
0x1800019e9  mov     eax, eax
0x1800019eb  xor     [rbp+arg_0], rax
0x1800019ef  call    cs:__imp_GetCurrentThreadId
0x1800019f5  mov     eax, eax
0x1800019f7  xor     [rbp+arg_0], rax
0x1800019fb  call    cs:__imp_GetTickCount
0x180001a01  mov     eax, eax
0x180001a03  shl     rax, 18h
0x180001a07  xor     [rbp+arg_0], rax
0x180001a0b  call    cs:__imp_GetTickCount
0x180001a11  mov     eax, eax
0x180001a13  lea     rcx, [rbp+arg_0]
0x180001a17  xor     rax, [rbp+arg_0]
0x180001a1b  xor     rax, rcx
0x180001a1e  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001a22  mov     [rbp+arg_0], rax
0x180001a26  call    cs:__imp_QueryPerformanceCounter
0x180001a2c  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001a2f  mov     rcx, 0FFFFFFFFFFFFh
0x180001a39  shl     rax, 20h
0x180001a3d  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001a41  xor     rax, [rbp+arg_0]
0x180001a45  and     rax, rcx
0x180001a48  mov     rcx, rax
0x180001a4b  cmp     rax, rbx
0x180001a4e  jnz     short loc_180001A5D
0x180001a50  mov     rax, 2B992DDFA233h
0x180001a5a  mov     rcx, rax
0x180001a5d  mov     cs:__security_cookie, rcx
0x180001a64  mov     rbx, [rsp+20h+arg_18]
0x180001a69  not     rax
0x180001a6c  mov     cs:__security_cookie_complement, rax
0x180001a73  add     rsp, 20h
0x180001a77  pop     rbp
0x180001a78  retn
```
