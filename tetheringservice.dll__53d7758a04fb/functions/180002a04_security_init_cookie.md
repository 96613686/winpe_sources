# __security_init_cookie

- ea: `0x180002a04`
- end: `0x180002ab9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002530`

## callees

- `0x180002a04`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002a53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002a53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a47`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002a39`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002a39`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002a63`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002a63`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x180002a04  mov     [rsp-8+arg_10], rbx
0x180002a09  push    rbp
0x180002a0a  mov     rbp, rsp
0x180002a0d  sub     rsp, 30h
0x180002a11  mov     rax, cs:__security_cookie
0x180002a18  mov     rbx, 2B992DDFA232h
0x180002a22  cmp     rax, rbx
0x180002a25  jnz     short loc_180002AA4
0x180002a27  xor     eax, eax
0x180002a29  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002a2d  mov     [rbp+var_10], rax
0x180002a31  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002a35  mov     qword ptr [rbp+PerformanceCount], rax
0x180002a39  call    cs:__imp_GetSystemTimeAsFileTime
0x180002a3f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002a43  mov     [rbp+var_10], rax
0x180002a47  call    cs:__imp_GetCurrentThreadId
0x180002a4d  mov     eax, eax
0x180002a4f  xor     [rbp+var_10], rax
0x180002a53  call    cs:__imp_GetCurrentProcessId
0x180002a59  mov     eax, eax
0x180002a5b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002a5f  xor     [rbp+var_10], rax
0x180002a63  call    cs:__imp_QueryPerformanceCounter
0x180002a69  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002a6c  lea     rcx, [rbp+var_10]
0x180002a70  shl     rax, 20h
0x180002a74  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002a78  xor     rax, [rbp+var_10]
0x180002a7c  xor     rax, rcx
0x180002a7f  mov     rcx, 0FFFFFFFFFFFFh
0x180002a89  and     rax, rcx
0x180002a8c  mov     rcx, 2B992DDFA233h
0x180002a96  cmp     rax, rbx
0x180002a99  cmovz   rax, rcx
0x180002a9d  mov     cs:__security_cookie, rax
0x180002aa4  mov     rbx, [rsp+30h+arg_10]
0x180002aa9  not     rax
0x180002aac  mov     cs:__security_cookie_complement, rax
0x180002ab3  add     rsp, 30h
0x180002ab7  pop     rbp
0x180002ab8  retn
```
