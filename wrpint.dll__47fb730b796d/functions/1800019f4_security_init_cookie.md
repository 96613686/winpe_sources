# __security_init_cookie

- ea: `0x1800019f4`
- end: `0x180001ad1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800015b0`

## callees

- `0x1800019f4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001a53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001a63`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001a53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001a63`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001a2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001a2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001a3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001a3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001a47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001a47`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001a7e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001a7e`

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
0x1800019f4  mov     [rsp-8+arg_18], rbx
0x1800019f9  push    rbp
0x1800019fa  mov     rbp, rsp
0x1800019fd  sub     rsp, 20h
0x180001a01  xor     eax, eax
0x180001a03  mov     rbx, 2B992DDFA232h
0x180001a0d  mov     [rbp+arg_0], rax
0x180001a11  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001a15  mov     qword ptr [rbp+PerformanceCount], rax
0x180001a19  mov     rax, cs:__security_cookie
0x180001a20  cmp     rax, rbx
0x180001a23  jnz     loc_180001ABC
0x180001a29  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001a2d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001a33  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001a37  mov     [rbp+arg_0], rax
0x180001a3b  call    cs:__imp_GetCurrentProcessId
0x180001a41  mov     eax, eax
0x180001a43  xor     [rbp+arg_0], rax
0x180001a47  call    cs:__imp_GetCurrentThreadId
0x180001a4d  mov     eax, eax
0x180001a4f  xor     [rbp+arg_0], rax
0x180001a53  call    cs:__imp_GetTickCount
0x180001a59  mov     eax, eax
0x180001a5b  shl     rax, 18h
0x180001a5f  xor     [rbp+arg_0], rax
0x180001a63  call    cs:__imp_GetTickCount
0x180001a69  mov     eax, eax
0x180001a6b  lea     rcx, [rbp+arg_0]
0x180001a6f  xor     rax, [rbp+arg_0]
0x180001a73  xor     rax, rcx
0x180001a76  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001a7a  mov     [rbp+arg_0], rax
0x180001a7e  call    cs:__imp_QueryPerformanceCounter
0x180001a84  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001a87  mov     rcx, 0FFFFFFFFFFFFh
0x180001a91  shl     rax, 20h
0x180001a95  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001a99  xor     rax, [rbp+arg_0]
0x180001a9d  and     rax, rcx
0x180001aa0  mov     rcx, rax
0x180001aa3  cmp     rax, rbx
0x180001aa6  jnz     short loc_180001AB5
0x180001aa8  mov     rax, 2B992DDFA233h
0x180001ab2  mov     rcx, rax
0x180001ab5  mov     cs:__security_cookie, rcx
0x180001abc  mov     rbx, [rsp+20h+arg_18]
0x180001ac1  not     rax
0x180001ac4  mov     cs:__security_cookie_complement, rax
0x180001acb  add     rsp, 20h
0x180001acf  pop     rbp
0x180001ad0  retn
```
