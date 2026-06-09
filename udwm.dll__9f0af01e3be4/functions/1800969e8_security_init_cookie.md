# __security_init_cookie

- ea: `0x1800969e8`
- end: `0x180096a9d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800969a4`

## callees

- `0x1800969e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180096a2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180096a2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180096a37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180096a37`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180096a47`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180096a47`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180096a1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180096a1d`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x1800969e8  mov     [rsp-8+arg_10], rbx
0x1800969ed  push    rbp
0x1800969ee  mov     rbp, rsp
0x1800969f1  sub     rsp, 30h
0x1800969f5  mov     rax, cs:__security_cookie
0x1800969fc  mov     rbx, 2B992DDFA232h
0x180096a06  cmp     rax, rbx
0x180096a09  jnz     short loc_180096A88
0x180096a0b  xor     eax, eax
0x180096a0d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180096a11  mov     [rbp+var_10], rax
0x180096a15  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180096a19  mov     qword ptr [rbp+PerformanceCount], rax
0x180096a1d  call    cs:__imp_GetSystemTimeAsFileTime
0x180096a23  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180096a27  mov     [rbp+var_10], rax
0x180096a2b  call    cs:__imp_GetCurrentThreadId
0x180096a31  mov     eax, eax
0x180096a33  xor     [rbp+var_10], rax
0x180096a37  call    cs:__imp_GetCurrentProcessId
0x180096a3d  mov     eax, eax
0x180096a3f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180096a43  xor     [rbp+var_10], rax
0x180096a47  call    cs:__imp_QueryPerformanceCounter
0x180096a4d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180096a50  lea     rcx, [rbp+var_10]
0x180096a54  shl     rax, 20h
0x180096a58  xor     rax, qword ptr [rbp+PerformanceCount]
0x180096a5c  xor     rax, [rbp+var_10]
0x180096a60  xor     rax, rcx
0x180096a63  mov     rcx, 0FFFFFFFFFFFFh
0x180096a6d  and     rax, rcx
0x180096a70  mov     rcx, 2B992DDFA233h
0x180096a7a  cmp     rax, rbx
0x180096a7d  cmovz   rax, rcx
0x180096a81  mov     cs:__security_cookie, rax
0x180096a88  mov     rbx, [rsp+30h+arg_10]
0x180096a8d  not     rax
0x180096a90  mov     cs:__security_cookie_complement, rax
0x180096a97  add     rsp, 30h
0x180096a9b  pop     rbp
0x180096a9c  retn
```
