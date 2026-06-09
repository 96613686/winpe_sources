# __security_init_cookie

- ea: `0x1800026d4`
- end: `0x1800027b1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002350`

## callees

- `0x1800026d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002727`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002727`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000271b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000271b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000275e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000275e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002733`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002743`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002733`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002743`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000270d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000270d`

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
0x1800026d4  mov     [rsp-8+arg_18], rbx
0x1800026d9  push    rbp
0x1800026da  mov     rbp, rsp
0x1800026dd  sub     rsp, 20h
0x1800026e1  xor     eax, eax
0x1800026e3  mov     rbx, 2B992DDFA232h
0x1800026ed  mov     [rbp+arg_0], rax
0x1800026f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800026f5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800026f9  mov     rax, cs:__security_cookie
0x180002700  cmp     rax, rbx
0x180002703  jnz     loc_18000279C
0x180002709  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000270d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002713  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002717  mov     [rbp+arg_0], rax
0x18000271b  call    cs:__imp_GetCurrentProcessId
0x180002721  mov     eax, eax
0x180002723  xor     [rbp+arg_0], rax
0x180002727  call    cs:__imp_GetCurrentThreadId
0x18000272d  mov     eax, eax
0x18000272f  xor     [rbp+arg_0], rax
0x180002733  call    cs:__imp_GetTickCount
0x180002739  mov     eax, eax
0x18000273b  shl     rax, 18h
0x18000273f  xor     [rbp+arg_0], rax
0x180002743  call    cs:__imp_GetTickCount
0x180002749  mov     eax, eax
0x18000274b  lea     rcx, [rbp+arg_0]
0x18000274f  xor     rax, [rbp+arg_0]
0x180002753  xor     rax, rcx
0x180002756  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000275a  mov     [rbp+arg_0], rax
0x18000275e  call    cs:__imp_QueryPerformanceCounter
0x180002764  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002767  mov     rcx, 0FFFFFFFFFFFFh
0x180002771  shl     rax, 20h
0x180002775  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002779  xor     rax, [rbp+arg_0]
0x18000277d  and     rax, rcx
0x180002780  mov     rcx, rax
0x180002783  cmp     rax, rbx
0x180002786  jnz     short loc_180002795
0x180002788  mov     rax, 2B992DDFA233h
0x180002792  mov     rcx, rax
0x180002795  mov     cs:__security_cookie, rcx
0x18000279c  mov     rbx, [rsp+20h+arg_18]
0x1800027a1  not     rax
0x1800027a4  mov     cs:__security_cookie_complement, rax
0x1800027ab  add     rsp, 20h
0x1800027af  pop     rbp
0x1800027b0  retn
```
