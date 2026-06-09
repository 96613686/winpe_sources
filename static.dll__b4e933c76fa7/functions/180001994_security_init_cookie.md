# __security_init_cookie

- ea: `0x180001994`
- end: `0x180001a71`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001620`

## callees

- `0x180001994`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001a1e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001a1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800019e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800019e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019db`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800019cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800019cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800019f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001a03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800019f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001a03`

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
0x180001994  mov     [rsp-8+arg_18], rbx
0x180001999  push    rbp
0x18000199a  mov     rbp, rsp
0x18000199d  sub     rsp, 20h
0x1800019a1  xor     eax, eax
0x1800019a3  mov     rbx, 2B992DDFA232h
0x1800019ad  mov     [rbp+arg_0], rax
0x1800019b1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800019b5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800019b9  mov     rax, cs:__security_cookie
0x1800019c0  cmp     rax, rbx
0x1800019c3  jnz     loc_180001A5C
0x1800019c9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800019cd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800019d3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800019d7  mov     [rbp+arg_0], rax
0x1800019db  call    cs:__imp_GetCurrentProcessId
0x1800019e1  mov     eax, eax
0x1800019e3  xor     [rbp+arg_0], rax
0x1800019e7  call    cs:__imp_GetCurrentThreadId
0x1800019ed  mov     eax, eax
0x1800019ef  xor     [rbp+arg_0], rax
0x1800019f3  call    cs:__imp_GetTickCount
0x1800019f9  mov     eax, eax
0x1800019fb  shl     rax, 18h
0x1800019ff  xor     [rbp+arg_0], rax
0x180001a03  call    cs:__imp_GetTickCount
0x180001a09  mov     eax, eax
0x180001a0b  lea     rcx, [rbp+arg_0]
0x180001a0f  xor     rax, [rbp+arg_0]
0x180001a13  xor     rax, rcx
0x180001a16  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001a1a  mov     [rbp+arg_0], rax
0x180001a1e  call    cs:__imp_QueryPerformanceCounter
0x180001a24  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001a27  mov     rcx, 0FFFFFFFFFFFFh
0x180001a31  shl     rax, 20h
0x180001a35  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001a39  xor     rax, [rbp+arg_0]
0x180001a3d  and     rax, rcx
0x180001a40  mov     rcx, rax
0x180001a43  cmp     rax, rbx
0x180001a46  jnz     short loc_180001A55
0x180001a48  mov     rax, 2B992DDFA233h
0x180001a52  mov     rcx, rax
0x180001a55  mov     cs:__security_cookie, rcx
0x180001a5c  mov     rbx, [rsp+20h+arg_18]
0x180001a61  not     rax
0x180001a64  mov     cs:__security_cookie_complement, rax
0x180001a6b  add     rsp, 20h
0x180001a6f  pop     rbp
0x180001a70  retn
```
