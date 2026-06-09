# __security_init_cookie

- ea: `0x180001704`
- end: `0x1800017e1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001330`

## callees

- `0x180001704`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000174b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000174b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001757`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001757`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000173d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000173d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001763`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001773`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001763`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001773`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000178e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000178e`

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
0x180001704  mov     [rsp-8+arg_18], rbx
0x180001709  push    rbp
0x18000170a  mov     rbp, rsp
0x18000170d  sub     rsp, 20h
0x180001711  xor     eax, eax
0x180001713  mov     rbx, 2B992DDFA232h
0x18000171d  mov     [rbp+arg_0], rax
0x180001721  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001725  mov     qword ptr [rbp+PerformanceCount], rax
0x180001729  mov     rax, cs:__security_cookie
0x180001730  cmp     rax, rbx
0x180001733  jnz     loc_1800017CC
0x180001739  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000173d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001743  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001747  mov     [rbp+arg_0], rax
0x18000174b  call    cs:__imp_GetCurrentProcessId
0x180001751  mov     eax, eax
0x180001753  xor     [rbp+arg_0], rax
0x180001757  call    cs:__imp_GetCurrentThreadId
0x18000175d  mov     eax, eax
0x18000175f  xor     [rbp+arg_0], rax
0x180001763  call    cs:__imp_GetTickCount
0x180001769  mov     eax, eax
0x18000176b  shl     rax, 18h
0x18000176f  xor     [rbp+arg_0], rax
0x180001773  call    cs:__imp_GetTickCount
0x180001779  mov     eax, eax
0x18000177b  lea     rcx, [rbp+arg_0]
0x18000177f  xor     rax, [rbp+arg_0]
0x180001783  xor     rax, rcx
0x180001786  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000178a  mov     [rbp+arg_0], rax
0x18000178e  call    cs:__imp_QueryPerformanceCounter
0x180001794  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001797  mov     rcx, 0FFFFFFFFFFFFh
0x1800017a1  shl     rax, 20h
0x1800017a5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800017a9  xor     rax, [rbp+arg_0]
0x1800017ad  and     rax, rcx
0x1800017b0  mov     rcx, rax
0x1800017b3  cmp     rax, rbx
0x1800017b6  jnz     short loc_1800017C5
0x1800017b8  mov     rax, 2B992DDFA233h
0x1800017c2  mov     rcx, rax
0x1800017c5  mov     cs:__security_cookie, rcx
0x1800017cc  mov     rbx, [rsp+20h+arg_18]
0x1800017d1  not     rax
0x1800017d4  mov     cs:__security_cookie_complement, rax
0x1800017db  add     rsp, 20h
0x1800017df  pop     rbp
0x1800017e0  retn
```
