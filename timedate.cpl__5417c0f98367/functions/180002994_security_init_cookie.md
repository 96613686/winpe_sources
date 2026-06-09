# __security_init_cookie

- ea: `0x180002994`
- end: `0x180002a71`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800020c0`

## callees

- `0x180002994`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800029f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002a03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800029f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002a03`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800029cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800029cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800029db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800029db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800029e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800029e7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002a1e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002a1e`

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
0x180002994  mov     [rsp-8+arg_18], rbx
0x180002999  push    rbp
0x18000299a  mov     rbp, rsp
0x18000299d  sub     rsp, 20h
0x1800029a1  xor     eax, eax
0x1800029a3  mov     rbx, 2B992DDFA232h
0x1800029ad  mov     [rbp+arg_0], rax
0x1800029b1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800029b5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800029b9  mov     rax, cs:__security_cookie
0x1800029c0  cmp     rax, rbx
0x1800029c3  jnz     loc_180002A5C
0x1800029c9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800029cd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800029d3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800029d7  mov     [rbp+arg_0], rax
0x1800029db  call    cs:__imp_GetCurrentProcessId
0x1800029e1  mov     eax, eax
0x1800029e3  xor     [rbp+arg_0], rax
0x1800029e7  call    cs:__imp_GetCurrentThreadId
0x1800029ed  mov     eax, eax
0x1800029ef  xor     [rbp+arg_0], rax
0x1800029f3  call    cs:__imp_GetTickCount
0x1800029f9  mov     eax, eax
0x1800029fb  shl     rax, 18h
0x1800029ff  xor     [rbp+arg_0], rax
0x180002a03  call    cs:__imp_GetTickCount
0x180002a09  mov     eax, eax
0x180002a0b  lea     rcx, [rbp+arg_0]
0x180002a0f  xor     rax, [rbp+arg_0]
0x180002a13  xor     rax, rcx
0x180002a16  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002a1a  mov     [rbp+arg_0], rax
0x180002a1e  call    cs:__imp_QueryPerformanceCounter
0x180002a24  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002a27  mov     rcx, 0FFFFFFFFFFFFh
0x180002a31  shl     rax, 20h
0x180002a35  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002a39  xor     rax, [rbp+arg_0]
0x180002a3d  and     rax, rcx
0x180002a40  mov     rcx, rax
0x180002a43  cmp     rax, rbx
0x180002a46  jnz     short loc_180002A55
0x180002a48  mov     rax, 2B992DDFA233h
0x180002a52  mov     rcx, rax
0x180002a55  mov     cs:__security_cookie, rcx
0x180002a5c  mov     rbx, [rsp+20h+arg_18]
0x180002a61  not     rax
0x180002a64  mov     cs:__security_cookie_complement, rax
0x180002a6b  add     rsp, 20h
0x180002a6f  pop     rbp
0x180002a70  retn
```
